# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p123 39_高级技术专题Ⅰ.zh_en -BV1jM4m1k73q_p123-

![](img/832dd33030b1646a81bd6fc722551ee8_0.png)

![](img/832dd33030b1646a81bd6fc722551ee8_1.png)

Welcome to this lecture on advanced techniques。 We are entering the last stages of this Xr Moc。

 I'm going to miss it。 but I wanted to talk about advanced techniques。

 so far we've been mostly playing with standard devices and I'm going to introduce you to a few techniques that I think are important So standard devices and standard SDks and everything standard。

 but in reality， for example， in lot of my work， I actually build a lot of my own stuff。

 actually build custom displays， custom controllers sometimes when necessary。

 and I wanted to share some of the more advanced techniques here。

 So we're going to go beyond some of these。 and I'll bring in some of these devices that I have here on the left as examples of how to make things more advanced。

 So let's get started。 So here is an overview of the advanced techniques。

 I'm going to have a block on a few topics that I think are'm mostly relevant for VR so procedure generation redirected walking and custom controllers I think。

😊，A lot of sense for VR。 Then we're going to do a little bit more advanced AR。

 So 3D reconstruction object tracking and custom displays is what I want to talk about here。

 And then I have a list of topics that are really crosscu。 So both VR and AR。

 And remember this is on advanced techniques。 So Michael。

 why did you put accessibility here under advanced techniques。

 Well I wish I didn't have to the problem is accessibility is really difficult to do at the moment。

 we're addressing the topic， I mean， we mention it throughout the。

 but we're actually really very limited means to really make the Xr stuff very accessible just because the tools including unity Un not really accessible。

 and obviously like using AR and VR displays VR is mostly predominantly visual and then AR while there are a lot of opportunities in research。

 it's not really designed with accessibility in mind Most of the AR devices that I know at this stage so。

We're going talk about this。 We're gonna talk about text input， right？

 How do you actually get things typed into AR and VR and collaboration， So multiuser。

 that's something that I think is very interesting。

 I'll expand upon this a little bit in my X research lecture following after this。

 we're going talk about adaptive layout and customization。

 So giving more control to the users or actually the system being smarter about how to actually adapt the layout of the scene to make it fit the physical environment of the user。

 key topic， actually， and not very well dressed in current implementations。 Pro Xr。

 this idea of building adaptivity into the interfaces so that they can actually adapt and interface can adapt to AR O to Vr depending on the task preference and whatever the user feels like。

 and so the context could also be a driving factor here。 And we're going talk about this。 Finally。

 mixed reality reality capture and virtual production。

 This is a topic that I'm especially interested in at the moment in my research。 And。😊。

Also this is something that you may be aware of from filmmaking。

 filmmaking making is changing radically， bringing AIVR techniques into the whole filmmaking world。

 and I think that's why is very interesting is's relevant to us because I've been demoing a lot throughout the MOOC and I wished I had more of these tools available。

 You saw a few examples of mixed reality capture and virtual production I'm going to expand upon that。

So this is my brief overview。And now we're going get started。 We're gonna jump right in。

 And so this lecture is really built around some of these concepts whenever I have like a really cool demo。

 a video， I'll plug it in。 otherwise we're gonna spend some time looking at some slides that I spent a lot of time actually designing to really get these concepts across the first one we're gonna to look at is procedural generation So you are in this physical world This is like this is your room you're looking this way and then in this world you see virtual content virtual reality here in blue。

 So the gray parts are the physical world。 okay and down here。

 so draw a line between these down here is actually a well kind of like a copy topdown what you see。

 So this is topdown view of your headset。 So if you walk this way here you would move that way here top down cool So now that we've established this let's say you're gonna interact with this world and maybe look a little bit you're coming closer here I'm going to let you walk in a second。

 but let's say you are getting。😊，Here well this idea of procedure generation is we' are loading more and more virtual content as you for example。

 move or spend more time could be lazy loading， but the whole idea of procedure generation is as the user explores more of the virtual world by being in the physical world。

 we can actually add to it。So that's going to be interesting so we could generate a maze here to have you walk through this。

 And this actually then brings me to the next concept， which is， well， redirected walking。

 So redirected walking starts with this impulse。 Did you notice， I'm going to go back。😊。

I'm going to give you this impulse。 That impulse will most likely trigger。

 It will catch your attention。 It's a visual cue。 It will catch your attention。

 It will will make you adjust your gaze。 And well， people walk where they look。

 It's like you're driving for your look。 And so be careful when you're driving and not looking。

 And so it's the same here。 Okay， so we have a little bit of an impact。 And we move this。

 And now as we are focused on this， were actually gonna to move the table。

 Did you notice just a little bit， I'm clearly exaggerating here， there might be smaller shifts。

 But anyway， So this shift is really important。 catches the user's attention。

 adapting their gaze and walking towards the object。 Did you see， rather than going straight。

 We actually walked what is more like a circle。😊，So while the user feels like， wow。

 I must be like at the end of this of this physical world now。

 we actually moved just this way in a circle， and that gives us well。

 more virtual space that we can cover in the same physical world， redirected walking。

So if this word there is actually research that shows that people can feel like they are walking along this corridor。

 but what they're actually doing is they're walking in a circle and that is just very interesting。

 Just a little bit of perceptual tricks here and there。😊，Cool， so redirected walking。 we have that。

 Now we're gonna to go to custom controllers。 We're going to play virtual ping pong here。

 So it's gonna be a ping pong。😊，B and well， obviously we can give you normally a virtual reality controller。

 A lot of these experiences are like that， right？😊。

Usually you have some kind of like virtual controller， this one here and to be honest。

 this one feels pretty good。 So playing ping pong with this is not the worst thing that I've done so far。

 if it were different kinds of kind of experience like golf or something you would feel like well this doesn't feel like doesn't feel right so we're gonna explore a little what options we have and how could we build custom controllers。

So one thing we could do， and this is often done is we just give haptic feedback。

 We give you the illusion of actually holding a record。 Well。

 we give you the illusion of holding a racket， but we actually holding is the controller。

 the controller represented here by this cylinder in the top top view。 So haptic feedback。 we could。

 for example， use the vibration motors that are in most Vr controllers So give you that feel whenever you hit the ball or something we have a little bit of vibration feedback。

 So make the user feel like the use， the real object。 But in fact， they are not。

 they're just using a virtual reality controller。 So pal works quite well。

 So let's stick with this example。 and say we remove this And what we now actually give you is a physical a real physical controller that really matches a shape。

 it's a custom controller。 we actually give you a pedal。

 maybe we instrument it in some way so that we can track it or we do object recognition。

 I'll talk about this in a few slides as another concept。😊。

So this controller now actually has the physical affordances。

 It really makes the controller look and feel like the real object。

 It might actually be the real object， but maybe it's battery operated inside internally。

 It's a custom controller。 You need to think about that。

 It somehow us need to communicate with the headset。

 It probably needs an immer inertia measurement unit so that you can detect small tilts and maybe some kind of lights around it so we can track it。

 This is how most controllers actually work。 We can track it visually。 Then。 I mean。

 the computer sees the light。 You don't actually see that frequency。😊。

Here' is a custom controller It's not as advanced as I just talked about。

 but this is a project that my student Ruci and I have been working on。 It's an independent study。

 It was really a cool little project。 What we did here was build a well a custom 3D controller so that we call it watch pod in fact what we do is we take a watch。

 we remove the wristband。 we used the touchscreen of that a little watch。 we put it in this pod。😊。

And now as you can see， we are tracking some of the movements。

 the 3D movements with this controller now， and because we have a touch screen。

 we can also go into different modes like this is translation mode。

 Now we can move the cube to the right and to the left。

And so we have a combination of the touch display and some other things we cut this here and the physical movement of the custom controller to be honest just using the inertia measurement unit and the IMU on the smartwatch wasn't really great acceleration and gyosscope are it's really hard to play with those so building a custom controllers is actually quite a lot of work。

😊，And。I think this project could be cool。 Did you see how we manipulated the aframe scene。 Yeah。

 so unfortunately， Ruci is now somewhere else in the world。

 just like many other students successfully graduated。

 And this is an independent study that kind of I'm stuck with。 But it was a cool idea。

 And I hope that one day， maybe it'll， it'll make it into a paper or maybe into a little bit of a project that we can use in my lab。

 So this is an example of a custom controller。😊，Now we're going to enter a little bit more AR oriented contexts。

 want to talk about 3D reconstruction。Physical world， virtual world。

 but you're seeing it through an AR headset。 Okay， we have a physical table now， not a virtual table。

 and actually moved it into the real world if you noticed， and it' represented here by this box。

As you walk through this space， what we do is we actually I mean， not we。

 but the device actually scans the environment， and it does a realtime 3D reconstruction of this。

 not only the basic walls and seeings no increasingly we can build denser point clouds This is then a 3D point cloud that represents this kind of mesh and so we can also see at least the geometry of this table。

 what you and I call table a computer wouldn't be able at this stage just with 3D reconstruction spatial mapping。

 we can't actually call this aab， we just have a spatial mesh。

 so we scan the physical world as a dense 3D point cloud。😊，If you want to call it table。

 we need an additional process。 It's an important step。 We need object recognition。

 some kind of object segmentation， so recognition segmentation， classification。

 so giving it a label so then we can actually finally call it table。😊。

Most devices only do spatial mapping if at all， and then adding this object recognition thing isn't really part of current pipelines。

 It's a very expensive process unless it goes against some lookup tables。

 So if you're a search engine provider， you actually have a good chance at getting this right。😊。

Look at Google Ls， for example。So object tracking is now something that we can do， right。

 if we can do object recognition， we can do object tracking。 So let's bring in a ping pong racket。

 Now we have that and its actually a physical one。 Okay， we're playing a ping pong in A R now。

 so that's fine。😊，Now， we actually scan this object。 We recognize this object。 Did you see the blue。

 I hope you noticed this was tedious。 Anyway， So object recognition to detect the physical object in the real world。

 we scanned it。 And now as the user moves it。 So I'm gonna play。😊，Hit the ball。

 And we can actually register。 That means the 3D location and track it。

 which means if you build this over time， we can actually determine the velocity at which you hit the ball。

 And now we're gonna hit the ball。 and the ball is gonna bounce off the table。 Pretty cool。😊。

Remember， it's a virtual ping pong ball。 Okay， we used the physical object to hit a virtual ping pong ball that was then bouncing around using the idea of object recognition。

And then also registration and tracking。Pretty cool。😊。

These are some of the concepts that I think are pretty fundamental， but also advanced。

 you can build these kinds of things with this place。 So obviously with elite motion。

 you could track hands go that go that are above this field of view so you place it on a table has a little window。

 you can track your hands。 you can start building some kind of more virtual controllers。

 I've also seen it mounted and like mounted in some interesting ways and scan the hand。

 Now we have inbuil hand tracking in a lot of the devices。

 including the archs quest and obviously the Holloands too。😊，Yeah， so not so important anymore。

 but if you want to build your custom tracking solutions。

 you would actually need to have a depth camera， for example。

 not the one that's built into the Hollands the Interre sense or the Connect that was showing off earlier over there the Connect would also fit the bill and then we can actually implement some of these concepts that I was just talking about conceptually we could actually implement them with technologies I do this all the time so in a lot of my projects and it's actually quite fun。

😊，What I don't do that much is actually custom displays。

 I wanted to talk about custom displays along the reality virtual reality continuum or the mixed reality spectrum。

 we actually have a number of displays that we can just put out here。 and so we have tangible。

 spatial， so projective AR。 We have handheld AR。 we also have headw AR。

 So it's probably like somewhere here。 we can have room size， So cave VR displays。

 if you will and then head mounted VR。 so it's pretty standard。

So the displays that you are probably most familiar with are handheld AR since we spend quite some time with them in this course and then maybe head mounted either the cardboard or maybe some kind ofoccus or HT5 virtual reality headset。

 What you haven't thought so much about is like where are these other kinds of displays。

 And so I wanted to give a few examples here。 One is Lightform which in some ways is a shout out to a research project called rumor life from friends and colleagues at Microsoft Research and is now more or less like a little spin spinoff and startup。

 So Lightform is a combination of a projector and a camera。

 it's like a procam setup and that allows you to build spatial or projective AR experiences。

 pretty cool。😊，And then looking glass， maybe that's something you've come across。

 I haven't actually played with it myself。 I've seen it in a few installations when I visited the friends at Disney or actually at Michigan。

 we have a few people experimenting with it。 Think of it as like a window。

 It's like kind of like a small comes in different sizes。 It's a a holographic AR display。

 So to give you a sense of what this is。 I'm going to show you a research prototype。

 which is a room sized A mirrors。 actually this doesn't really like monitor-based AR some here。

 but doing room sized monitor-based A。 that is really interesting。

 So I wanted to show you my little project here AR mirrors。

 It was one of my before the holidays projects， let's build this。 I just want to see how this feels。

 Okay so this is me in the lab。 I have screens everywhere。

 it's a good and bad decision because I also have ridable walls， but that's a different story。

 anyway， on each of these screens， actually have a connect。 connect here， connect here。

 This can track me and each of these actually show a mirror like a virtual。😊。

We actually have a 3D model of my lab， a virtual copy of what I'm doing in this lab so we can obviously then do skeletar tracking。

 both the easy parts， the joints that are highly visible and then some that are harder to see for some let's say for this display for that display actually these would be harder to see。

😊。

![](img/832dd33030b1646a81bd6fc722551ee8_3.png)

And I just wanted to color code this a little differently。

So this is how this looks when I'm like in the room。 And this really now works like a mirror。

 as you're going towards it， it actually changes the perspective。 It render as it differently。

 And if you do this in front of a mirror。 Like you're going to the left or going to the right。

 You actually get to see more a better angle at what's behind you。

 And so this is what I wanted to mimic here。 And for that。

 we obviously need to create but it's not really a custom display technology。

 Like maybe you were thinking， hey， Mike you're building your own display。

 I have actually done that as well。 with 45 degree tilt setups， Pes ghost and all this kind of stuff。

 pretty cool。 but it's hard to actually demonstrate this kind of stuff。

 And so that it looks like a cool experience for you。😊。



![](img/832dd33030b1646a81bd6fc722551ee8_5.png)

![](img/832dd33030b1646a81bd6fc722551ee8_6.png)