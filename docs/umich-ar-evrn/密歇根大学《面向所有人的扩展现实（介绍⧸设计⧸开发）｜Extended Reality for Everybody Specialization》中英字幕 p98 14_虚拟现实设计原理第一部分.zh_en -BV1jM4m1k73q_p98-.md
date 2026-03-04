# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p98 14_虚拟现实设计原理第一部分.zh_en -BV1jM4m1k73q_p98-

![](img/4e352869b1c48d5dc7d31d81766d21c1_0.png)

![](img/4e352869b1c48d5dc7d31d81766d21c1_1.png)

Welcome to this lecture on designing a virtual reality。Are you confused？Well。I just thought。

What a funny way to kick off this lecture being in virtual reality In fact。

 I was just looking at a virtual reality desk。 So the Oculus kind of like area that you see when when you start and you know wanted to play a trick on you here No this is really this week is going to be quite cool you're going to learn about a lot of the basics when it comes to virtual reality design I'm going to share a few techniques I'm actually quite excited So the way I've structured it is like this is the intro to virtual reality but development just assume you know about the concept and you know about the technologies。

 if you feel like you have some refreshing to do please look at other MOoc the first one is part of the XMOoc the first course really provides this foundation in depth review of VR and AR both the concepts and the technology So designing a virtual reality and as I said initially in week one we are going to have two case。

😊，Studies throughout this entire MOC contributed by two of my students， Kara and Sweta。

 and they are obviously great students， but also they contributed really cool case studies for us。😊。

This one that we're gonna focus on this week is a zoo。 It's a virtual reality version of well。

 it is modeled in some extent after the Detroit Zoo。

 but I have to be very careful here the Detroit Zoo this is not affiliated with them The Detroit zoo was not a client of ours。

 there's a different story behind it。 I was doing an online office hour on Twitch as part of my residential teaching and I felt like hey I should do I should really design a virtual reality and I should probably model it after some reality。

 even though I'm not a strong believer that we need to copy the real world。

 but I wanted to have a zoo。 and I started out with a basic layout and the animals。

 And now well then later at some stage I thought， hey this would be a really cool case study for us for the MOoc so I asked Kara carriating my student who help me who was a course course design system as part of this Moc in the background。

 but we are going to interview her as well。😊，Helped us create this really cool case study。 In fact。

 she satAT down and implemented all this。 So we actually going to learn about a number of things。

 We're going to focus a lot on environmental design， just in this lecture。

 But later were also going to learn how to travel in virtual reality You see elements of this already in some of the videos I show and we're going learn about object manipulation。

 So traveling in a zoo， you can imagine right， you want to see all the animals So you go to different areas in a zoo that makes sense。

😊，So then we were thinking what kind of manipulation could we do and so we have this petting and feeding area it's actually quite a scary area because we have like really big gorillas there。

 so you want to be careful， not so much petting and more feeding and probably more about far manipulation that's a term that I introduced later than anything coming too close to them。

😊，AndI want to be also again very careful here， we're going to look at this。

 I do say Detroit zoo from time to time because again this is what it was modeled after it just started in an office hour。

 as I said， this is not approved or somehow affiliated with the Detroit zoo。In fact， at Detroit Zoo。

 we talk to them， they have very high values and a pedding and feeding area is actually a logo。 Now。

 I thought。That is very important for us to know。 I totally understand animal welfare。

 they're making a really good case there。 It would be very disruptive to the animals。

 and it would be actually not good。But。We can do this in virtual reality。Without harming anybody。

 So here is a screenshot of what's gonna， What are you going to see in a second。

 I'm gonna actually walk through different stages of design。 In the end， it became a night safari。

 but it didn't start out as a night safari。 It looked really quite sad。

This is what I produced as part of my office R， so this is what I had。

And I was basically just creating a map where he had a little bit of interaction in there so you could use the controllers and you could teleport around。

 It's relatively easy to do。 But then Kara came in and Kara then actually turned it into something beautiful。

 you can see the basic elements that I had。 They're still there。 But now we have animals in there。

 lots of animals。 actually， Everything here is based on three public publicly available models。

 So we didn't actually model anything in here。😊，We created a menu so we can actually navigate in this world。

 This is the part where we learn more about object selection and travel。

 So navigation and menus and then object selection is here and manipulations。 So we have this。

 as I say， feeding area。 We have monster bananas that you can give to really big monkeys。😊。

Yum is what I say here。 I'm gonna share this case study with you as well。

 if you want to I'm gonna do a walkthrough。 I'm gonna take you on a 10 minute safari。

 you can listen to me and learn a little bit more about the ideas behind this project。

 And it's a cool case study。 I'm so glad we have it。 So I'm just gonna say thanks again to Kara。

 We're gonna to talk to her later as well。 This is a beautiful aviary。

 So we have really nice birds here and really quite cool areas to explore。

 And coming putting it together with this night safari。

 which is something I really insisted on inspired from a few trips to zoous I'm a big fan。

 And so the night safari is also that idea of the night safari。

 So turning this into a torchlight and also having a laser come out of it。😊。



![](img/4e352869b1c48d5dc7d31d81766d21c1_3.png)

![](img/4e352869b1c48d5dc7d31d81766d21c1_4.png)

That was actually pretty good for our case study because youll learn more about light and this idea of really giving agency to users and it adds to this explorative nature of virtual reality。

 And even though everything in there， you probably now say this Michael， if this is it。

 if this is your zoo， then that's a little disappointing。😊，Okay。

 then maybe you have very high standards。 Maybe you're used to going to the movies and watching Disney movies。

 So keep in mind。That was not the goal here This is a not designed for aesthetics。

 although I do think it looks quite pleasing， it's not high quality high polygon count。

 it actually all three models。But I suspect that when you get started in this space。

 this is how you will work。 You won't be this Disney artist， maybe if you are as's cool for you。

I'm jealous but the majority of us are just you know throwing things together and that we can find we need this model and that model and maybe we work with somebody who can model things for us so remember my what doing XR actually involves lecture I was talking about Disney project so I was just thinking back to that if you don't know what I'm talking about second course Wig one check it out。

😊，Allright， let's go and talk about what we're gonna learn。 So virtual reality content。 Okay。

 so we're gonna learn about a few things。 What does it actually entail to create a virtual reality。

 So if you think about it in terms of just content。 Yeah， 3 d models and animations。 Sure。

 we're gonna put some 3D characters in our world， we're gonna have a story that way。

 these 3 characters are actually the main ingredients。

 they can be in the foreground and in the background。 In fact。

 they can actually play a really cool role in the background just for atmosphere。

 lights and shadows required for rendering， obviously well， I say obviously。

 but that's something you've touched on in the 3D lecture last week。 So yes。

 we need light in order to see something in ambient light， and then we have directional light。

 and then we can have spotlight like we do for the touchrch light here。

 can give visual cues to use as very important。 The environment So really the terrain or like whatever you walk on or what you see。

 and this environment like trees， rocks， lots of things， really cool tools in unity， but even。😊。

A frame has an environment component that can be configured in many different interesting ways。

 so that's usually sufficient to create this kind of like presence in a virtual world physics。

Physics are really important。 Like if you want a model after the real world， where we have physics。

 at least on those planets that I've been to， which is actually just make or break the VR experience。

 So if you don't get the physics right， if they are missing and users are expecting them to be there not so believable。

 So that's really something to take into account spatial sound， So audio， 3D audio。

 whatever you may call it spatial sounds so more than stereo okay really truly specialized sound would let's say if there were an object in between us right now。

😊，Any And then as the object goes， I was just saying you wouldn't hear me really anymore。

 that would make a difference。 Okay， so bringing an object an obstacle in here would manipulate modulate the sound。

 And if you like in a big room， you would expect it to echo for example。

 And if you're in a small constrained room you can make it feel very tight。

 So all these things coming together， don't forget about the sound， not just the visual。

 So it's actually key to immersion。 your experiences with sound much more believable。

 and actually something is really missing。 But initially when you start out and you're designing for ablebodied and you yourself are ablebodied。

 you probably predominantly designed for the visual senses but don't forget about audio。

 So menus in Hu really they work actually different VR。

 So heads up to space is something that really just makes a sense in virtual reality and also in augmented reality。

 So we're gonna learn about this as well as we go through these。😊，the content this week。

 so allow users to trigger functions， navigate and customize the virtual reality experience。

Especially the menus。So another way to think about it。

 And these are also some things that well actually learn about is virtual reality interactions。 Okay。

 so we need to distinguish at the highest level between selection and manipulation。

 So on the selection side， very common is to have kind of like a virtual hand。

 So your controller it can show the controller or an actual approximation of that physical controller。

 but we can also give you a hand model。 It's very common。 And now we actually have hand tracking。

 So it will almost look like a real hand you know。😊，Like a hand instead of a virtual copy of this。

And the in between solution has been that you show the controller or you then replace it like remember when you were entering virtual reality。

 where I'm not sure whether you've seen my first lecture really on on VR concepts。

 but I was going in the Oculus lounge， I was going through the Ocus tutorial actually。

And then due to the controller design and how the buttons are placed。

 we know roughly which finger is where we can detect we can make these sensitive。

 which is what they did。 And so we can detect where the fingers are。

 so we can actually render a hand model that does interesting pointing thumbs up or whatever kinds of interactions。

 even if we don't have hand tracking yet， but hand tracking is becoming more or less in standard。😊。

You can have a laser pointer we're going to talk about that。

 we're going to talk about different kinds of manipulation or grasping to really change objects in the world。

 that's really exciting It's a little bit more challenging but it's possible and then navigation or travel so it can be gazebased So what I mean by that is you travel where you look so we're going to learn about this in halflife eds they actually really did this where you're looking is where you're walking it's very interesting but what I'm also thinking about is like。

😊，Let's assume you're not rich。 We don't have all this stuff here， which is。

 I wouldn't have all this stuff if University of Michigan didn't give it to me。

 I would probably just have this And and many of us would just have maybe not even the virtual reality head that I show from time to time like the archcus rift or the rift as or the quest。

 maybe many of us would just have this。 And so gazebased travel。

 so even just three degrees of freedom is something we can implement。

 And it's still a form of virtual reality。 And you can still have quite immersive experiences in there or in the archculus go。

 which has been discontinued， just like the daydream。 So no more thread of。😊，Teleporting。

 so use the controller to activate the travel function。 That's something you can do。

 And then obviously you can do menus。 and we learn about menu designs。 You can fix them。

 So anchor them in the world or attach them to the camera。

 they can follow So it's a little bit of delay。 It's like you moving your head and then it's coming rather than you moving your head It it's attached to your gaze So it's always there。

 I like this following more。 So it's very common。 for example， on the archers。 not so much。

 but they actually have a fixed menu， at least in the latest version。

 there are S changes all the time。 Design patterns， design patterns， design patterns。😊。



![](img/4e352869b1c48d5dc7d31d81766d21c1_6.png)

On the Hollens， we have this follow menu and so some of these ideas and concepts really translate nicely between AR and VR and then some some of the things we talk about are really just unique to VR or AR。

So we're going to do this case study， we're gonna look at it step by step okay so here in many when you're designing a virtual reality。

 one of the things I did was actually just put in an environment just to have a little bit of fear for that I actually enabled to travel so allowing teleportation and then I was thinking in terms of zones and so I was just planning out the map and then gradually Kara came in and she made it beautiful。

 gave me some animals played more with light。😊。

![](img/4e352869b1c48d5dc7d31d81766d21c1_8.png)

We added the menu， we're going to talk about this in more detail in the next lecture focused on menus and navigation。

 So this menu then allowed us to navigate in this world in addition to teleportation function。

 so common travel functions and then we also have built as I said into the zoo a feed the animals area。

 this is completely fictional， nothing that you can do in the Detroit zoo that this was modeled after and then we put the experience together and it actually looks really beautiful。

so， I mean， from my perspective， who as someone who is not a true 3D artist。

 I enjoy working with people who are really good at 3D artists，3 3D art and 3D design。

 but I'm personally not， I'm more of a，Developer and engineer。

 So were also going to learn about object placement。

We have actually really important key terms here that we need to learn about when you place things in the virtual world。

 we have basically at the highest level four different ways to do this especially when we're using Web XR so and this is not just related to virtual reality。

 This is a little bit more some of it doesn't make so much sense in virtual reality。

 So it's more like Xr based。 So anyway， you can place things in the world。

 So the object actually exists within the 3D world。 this is called diegetic。

 they are part of the story so they can be anchored in a fixed position or just like somehow floating in the world and then following you。

 but they are like essentially in world rather than in screen space So screen space means the menus would actually be floating So the object is in 2D over the 3D scene so could be attached to your heads of display to the virtual camera。

And this would be non diegietic。 It doesn't participate in the story。 It's just visible to you。

 So in half life， when you look at the menu that is really a nondiaegetic menu。

s really separate from the story。 It's just there that you bring it up to configure the game and that makes sense。

Then we also have obviously options of putting objects in 2D and the web page。

 And so while you're thinking， hey， but this is not in virtual reality， well。

 on the web when you're working with virtual reality on the web。

 you can always exit out of VR and enter VR。 and you can actually have very interesting transitions between the 2D web and the 3D web and then especially virtual reality。

 And so any kind of placement in the dom or page means it's actually not visible in virtual reality。

 So it's actually separate， it's separate from the canvas that renders the 3D scene。

 So keep that in mind。 if you're like working on a Web Xr solution and using a frame。

 put the stuff inside the a scene， not outside the A scene。 and this is part of the honest track。

 So it's an invitation to come there。 we're gonna hack a little and understand this better。😊。

And then attached， so you could actually， it's a combination of the above。

 so you could have the object anchored within the user's gaze， controller or hand。😊。

So it could be head gaze。 You could even do eye gaze very soon。 I mean， it's not that standard yet。

 but it is coming into two VR devices as well as AR devices。

We really deal with object positioning and sizing a lot。

 I think this is one of the key things when you're transitioning from 3D just plain 3D from last week to this week。

 thinking about Vr and just porting your scene in seeing it the first time in virtual reality is going be cool。

 but what actually be catastrophic because stuff might be just too big。

 So we really need to think about the position， the rotation and the scale of objects。

 and really have to understand how these things are defined。

 a unit of one may translate at least per default depends on how on the resolution of your virtual reality。

 it can translate one to one to the real world。 This is what we expect at least an augmented reality。

 but we can usually scale the virtual world。 And so that scale and then the world scale determines the resolution。

 And so that's when things get messed up。 But it allows us to overcome portions of that world。

 So it's interesting。 In any case， the location of the object and absolute 3D coordinates。

 when I say position， this is what I mean。 So think meters away。😊。

From the camera's calibrated startup location。 Its especially true in AR。 but also in VR。

 sometimes it's not really clear where the world starts。

 It has to do with what you do sometimes when you press the home button on the archcus。

 press the home button like put forward， press the home button longer。

 it recentcenters everything this way。 So this would be a starting location And then the scene will be laid out in front of you this way。

 And if I go like this then everything will be appearing this way。 This would then be zero degrees。

 not like 30 degrees from that previous example。😊，So keep that in mind。Votation。

 the angle of the object。 so this is really when we're doing moving objects around the y axis。

 So I'm gonna give you this example。 moving objects around the y axis would be this way right okay and then X and Z is a little bit more complicated to show。

 I'm not gonna do that now。 So just stick with Y for now。

 but this is something you've learned last week。 and probably I'm sure we need a bit more more time。

 I think in terms of degrees or radiance and radiance is a little bit of a harder concept mathematically it's used a lot internally。

 So maybe something you come across， especially when you move out of a frame into3 Js。😊。

So it'ss essentially the in degrees the difference from the model's orientation and keep that in mind。

 it's going to be very important。 let's say you have a virtual reality model of Michael and we put the peO point here and then you rotate me around X or something then that would be where we rotate if you put it at the bottom of my feet。

 then it's more like the whole body is like moving like if it's here okay， Pvo point here。😊。

People point here， you see the difference。So keep that in mind。 if this doesn't make sense right now。

 then you haven't actually done anything in VR yet。 This is really key when you start。

 especially in 3D in general。 but especially in VR keep that in mind。

 especially when you work with lots of different models。 Kara can sing a song about that。

 So then that is really key scale， finally， nobody really knows what one0 scale is with models。

 every every model comes in their own scale and their own original scale。

 So while we have this really nice zoo here， if I put everything at  one0 scale。

 This is what it would look like。 I actually went in there and looked at some of the issues when Kara was struggling。

 she wasnt really struggling。 little complaining， maybe about some of it， these Google Po models。

 why they are cool and hard to work with this is everything normalized。

 okay but this doesn't mean that they all have one zero scale。 if we normalized it in 3D software。

 then yes。😊。

![](img/4e352869b1c48d5dc7d31d81766d21c1_10.png)

But because these were modeled by various different 3D artists in whatever software they were using。

 probably blocks。Yeah， nobody seems to pay attention to coordinate systems in pivot points and scale。

 and so this can be very painful， so keep that in mind。😊。



![](img/4e352869b1c48d5dc7d31d81766d21c1_12.png)

Alright， I think I want to give you a few tips at the end。 So when you design your virtual reality。

 you should think of it in terms of designing in terms of layers。

 Okay so there's a foreground where you put the 3D models， spatial sounds。

 So that's really the stuff that you see really close up。 as's a midground。

 that is already adding to the atmosphere。 So in terms of visual I would say that's a terrain。

 any kind of environment， maybe some trees in the background， maybe trees that say in the mountains。

 the rocks like I grew up in the als in Germany。 So that would be the background the background here would be a skybox。

 So a 360s sphere 360s sphere iss usually the outer bounds of all virtual reality or a cube depending on which software you're using could also be a cube box。

 but it's like a skybox in general And so ambient music I would put so it's not like like if you're putting an animal that's foreground。

 if you have some。😊，Kind of birds in the background or whatever we have this rainforest sound。

 that would be ambient music。 It's usually on loop。 It doesn't react much。

 and you could still have some kind of additional background sound as well。

 so I would distinguish this I was trying to explain these layers in terms of what that means for the 3D models and the 3 d content and and then also the sound。

 These are all the things you put in the foreground。 These are the animals。

 you can see some nice tree offs This iss the first thing I always look at all this zoo played here。

 and then we have the midground。 Okay you bring terrain。 In this case， this terrain comes with trees。

 they call this dressing It's part of the a frame environment component。

 you can configure that you can that doesn't have to be green can be winter can be。



![](img/4e352869b1c48d5dc7d31d81766d21c1_14.png)

Whatever it can be more abstract， but you see the difference。

Creating more atmosphere and then we're bringing in all the light and additional actually a skybox so we're changing the skybox here and then also we're doing a little bit more to be honest this is the final design were also bringing in some of the light here and it does it's like I mean it doesn't exactly look like these really cool when they show you how they made the marvel movies but it's close isn't it。

😊，Okay， this is when we really put everything together。

 an additional layer to really have some kind of light in the background and we' changing the skybox a little more。

 So this is when you can then tune forever， but we also had a deadline。

 so I'm really happy with this example。😊。

![](img/4e352869b1c48d5dc7d31d81766d21c1_16.png)