# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p115 31_无标记AR开发第一部分.zh_en -BV1jM4m1k73q_p115-

![](img/5843a1e58ee536344c12b32b6e65cb08_0.png)

![](img/5843a1e58ee536344c12b32b6e65cb08_1.png)

In this lecture， we're going to focus on Marker less AR， so augmented reality without marker。

 at least fis visible markers the whole story behind Maless AR is that it's now on the device to find its own markers。

😊，And that's something I've talked about in the foundational lectures in the first course as part of this XMO and that's something that's going to come back here a little bit。

 and we're going to learn about Mac less AR in terms of frameworks and toolkits based on top of smartphone phonebased AR。

 so Aircore and AirK are some of the examples that we use here。

We're also gonna use our case study because well， Schweer actually also implemented and mark less AR version of Kepller's laws。

 So， and that's what I'm showing you here。 So the first thing you need to do is actually decide where you're gonna place the content。

😊，And even that moving the device initially was very important for the device to do initial plane detection and figuring out a little bit of the environment。

 And then we have it there。And then you have the first law。

 and we changed a little bit of the design here。 We have this tab interface。

 and you can actually click these tabs or tap them。

 and then you can actually switch between the visualizations。 So no more paper involved。

 I'm just using the same table and to show you to illustrated to you。

 And then the interactions are actually here thats still lean touch It's still the same。

Keep in mind that this actually is the version that we had implemented first before we did Macbase。

 A are。 So it's funny when I say it's still the same， but。Depending on， you know。

 that's how you perceive the content， so。And I don't think it would have made a big difference had we designed this second。

 maybe we would have kept the tab interface horizontally more aligned with the paper or with a tabletop on which we placed the surface on which we placed it。

Also， all this stuff is still working。 The interactions are very similar。

 So you can tap you to pause this simulation， for example。

 I just enjoy watching these planets so you can just tap on screen。 And that actually pauses。😊。

We can learn about this law of equal areas。 the second law。

 My goal was not so much that you actually learn about Ke's law of planetary emotions。

 It's just a use case。 It's a case study for us。 You want to learn about AR。 just like with a zoo。

 the zoo was a technological case study for us。 And this is a technological case study， as well。

So the love of harmonies is also interesting。And it， it's cool how we can actually move multiple。

 adjust the orbit of multiple of these planets at once。 I think that's a cool。😊。

Part of the interface。 And because it's Mars， I don't have to pay attention to anything。 Well。

 the surface， to be honest， if I were just using this plain white surface rather than putting things on top of that table。

 that tracking wouldn't have worked that well。 So that's why I put。

 it's not that I really wanted to have my notebook there and all that stuff there。

 but I needed to have some visual features on that white plane， that surface that I'm using here。

And I wanted it to look nice for you。 So tidy， see how nicely I've arranged the pens in the background。

😊，Yes， so it's all fake， but it is。 it is not too far away from what a desk。

 a nice and clean desk could look like。😊，And then yeah。 so pay attention to the surface tracking。

 So a monotone surface or monochromatic surface， like a green screen would actually be the worst case scenario。

 And then you can actually， in this case， tracking works pretty well。

 And I can actually really follow these planets。 I just really like how this looks。 And it's。

 it's pretty cool。 And so thanks again for that case study， Schta that we can actually learn from。

 So Mar S A R。😊。

![](img/5843a1e58ee536344c12b32b6e65cb08_3.png)

So here we， we're gonna talk about Mac less tracking。 Okay， we still track。

 So how does it differ from Macpae。 What's the magic， We're gonna talk about that。

 We're gonna learn about the basic user experience through some examples。

 So that changes quite a bit。 so we need to actually design more digitally now。

 And cannot upload too much into the Mac design。 So we need to concern ourselves more with basic user experience。

 Obviously， you need to do this with both， But part of this lecture。

 I can focus more on what happens on screen So in the world or on screen on device。😊。

And so then we're also gonna learn about Mac S applications。 So really， what are the limitations。

 or at least the advanced technical requirements when it comes to Mac S A R。

 Are we still reaching the same amount of devices， The answer is no。 So compared to Mac based。

 you're reaching a much smaller subset of the population。

 But most latest generation smartphones actually supported。 So it's pretty good。So macros tracking。

 we you think of a layered approach， as I say here to macs tracking It's not just plane detection。

 So not just horizontal and vertical planes as the primary means to represent the environment。 No。

 the environment is much richer， not just doesn't consist of just planar surfaces。

 So more advanced spatial mapping。 So would allow it to really do a three mesh reconstruction。

 including texture mapping in some of the advanced devices like the holens， for example。

 and then on top of that that is not also supported by the iPad with Liar scene understanding。

 So actually really doing semantic scene understanding。

 So allowing you to classify portions of the mesh using semantic labels like phase， walls， floors。

 tables， seat， windows， ceilings。 These are some of the labels that are commonly supported at the moment。

 and then we can do segmentation based on that。 So we can do background foreground extraction。

 we can do sky extraction。 we can actually segment people。

 the thing that I'm gonna to show here the sky is something that you there are some really impressive demos。

😊，On the magic leap and then also Snapchat has the support for this kind of segmentation。



![](img/5843a1e58ee536344c12b32b6e65cb08_5.png)

That's Mar tracking。 And here I'm gonna show you an example of plane detection。 just using Webex R。

 and when I say just using Webex R to be honest， this is the latest really just like hot out of the press。

 the latest Chrome on Android the latest Webex are an evolving standard。

 So it's actually still the specification is still being written as I'm like designing this mo and recording this。

 So I'm proud that I can show you this。 it's not too different from some of the other demos that I'm gonna show you。

 But this is actually a webbased So using the latest Webex R bringing air core into the browser。

 And what you can do here is plane detection。 And so I visualize the plane detection not by visualizing the plane but by visualizing how that cube would be appearing once I pick the plane。

 And I thought that's actually a good way to visualize it。 Most of the time later examples。

 you would just see the planes visualized like this way。😊，But this is， I mean。

 while it is relatively useful because I still match the content to the plane， most of the time。

 it will be too abstract。 So think a little bit more about whether you could have a preview like a wire frame or some kind of transparent copy of the content So that you get a sense for the scale because where you detect the plane similar to markase tracking。

 it will actually determine the size So the scale of the content and also constrain a little bit how you can move it inside that plane before you jump to the next plane。

 So there's something to keep in mind。

![](img/5843a1e58ee536344c12b32b6e65cb08_7.png)

Here I'm going to show you an example using AR foundation。 So that is now an abstraction in unity。

 an abstraction over both A kit and A core。 I'm running it on an AR core phone。

 I'm going visualize you。 we're gonna visualize the point cloud here。

 So these are all the little feature points， the key points that we keep tracking。

And we can kind of like show the whole point cloud as it builds。

 So that's like how the device understands the environment。 So that is spatial mapping。

 And this is a point cloud。😊，And then we can detect surfaces。 So planar surfaces。

 we can actually approximate it to planes and detect those in the point cloud。

And I can also show just like per frame what we see per frame。

 So rather than the whole point code as is collected over a sequence of a series of frames。

Here you just see in each frame， you just see the individual per frame on a frame per frame basis。

 And you can see how we are refining some of the points。

 And sometimes we just can't find those points again。 So we're building new features。

 we're picking new features so that we overall have like a constant number of features that we are tracking so that we can relatively reliably understand how the device is actually moving through 3D space。

So these were some of the more fundamental features。 So plane detection and then point cloud。

 how does it work。 Let's talk a little bit more about basic user experience。

 So the basic user experience example that I have here。



![](img/5843a1e58ee536344c12b32b6e65cb08_9.png)

Is this one。 So it's actually also from A Foundation。 So I compiled it and tried it out。

 And so it shows these feathered planes down there。 And then when you touch。

 when you touch the screen， it does the surface detection。 And when it works。

 So when it actually detect the plane， then you can actually place an object there。

And the object will appear larger。 obviously， if it's like on that plane and if。

 if it's like in the background war， as if it's further away， then it'll appear smaller。

I think I was trying to attach it to the screen。 And it's like it's a vertical plane。

 So vertical planes used to be hard。 horizontal planes， we got， we got we had that first。

 but vertical planes like this one on the TV that only was introduced later in an airco air kit。

 But now we have it。 And so we can detect both walls and the floor。😊，So， and， as you can see。

 everything is still there and it's actually still spatially。Like really anchor。

 So that was the basic user experience。 So basic user experience is really like this。 Okay。

 bring on your phone。😊，The app asks you to move a little bit left and right。

 And that's not just because it wants you to exercise。 No it needs to see more of the space。

 It needs to be able to do triangulation。 So it needs to be able to see a few frames from different angles。

 slightly different angles。 then we can actually figure out， okay， through triangulation。

 we can estimate depth。 we can figure out these points。

 then actually together are like at that distance。 So there is a rough surface here。

 Bam And that's how this works。 So basically like tell the user to move around a little bit once the tracking is established。

 It probably removes that animation that initially we start visualizing the planes。 in this case。

 was this feathered planes visualization。 I like my preview of where was gonna' biasased。

 implement it and design it this way。 But I think it' it's useful anyway。

 and then once the planes are there then the user can tap。 And as the user tabs。

 we can actually do intersection with these planes。

 so we can actually understand how that part works。😊，So that was basic user experience。

 And let's look at how to make it a little bit less basic。 No， a little bit more advanced。

 I'm gonna bring an inclusion through the depth API。 Now。

 the depth API is a relatively new feature in A core。 I mean。

 relatively at the time of the recording。😊，And I'm actually placing objects。

 once I enable the depth API， I'm able to place objects。 And these objects will actually right now。

 But I don't realize initially， as I was giving the demo。

 I didn't realize that the objects were actually placed。

 but they were placed on the plane that that chair is actually occruding。😊。

And so this is the cool part about the depth API。 it does have that understanding。

 and it automatically applies occlusion rendering to these objects。

So then I have to walk around the chair to see more of these objects。 I mean。

 the fun thing about doing AR things is like you get so excited when things feel more like they should feel when you merge the physical and the virtual。

 So acclusion is a key part。 Light estimation would be another key part。

 but I don't have a good demo there。😊，And I'm just keeping play around here with this。

So occlusion works pretty well despite and there are obviously some issues with that chair。

 you can see in this you can see this heat map， how the the netting of that chair and the the back seat side is hard to to realize it's actually supposed to be like a surface。

But you can see nicely how it does the it generate a heat map here visualizes how it does the tracking。

 so heat map things that are further away are red and things that are closer are blue。

And so dark blue would be really close。 And so in some sense， it's an inverse heat map， if you will。

And I can enable and disable it in this demo。 It's a pretty cool demo。 A core demo。

 I didn't implement it。 I just implement， I just ran it。 So it's。It's one of the air core samples。

 It's pretty cool。And yeah， I think it's， it's pretty advanced and works actually really well。

 Now we're gonna do even a little bit more advanced user experience。

 So one thing that is very important is， as you interact and walk around with these objects。

 here we have a spatial mesh as before。😊，But in this case， we're using the iPad with Lidar。

 And I've done this demo in course 1。 but this is now a demo where we can talk a little bit more technically about this。

 because we are in course 3。 So what happens is we have a lidar inbuilt into the iPad。

 That's actually pretty exciting。 So Liar is like a 3D scanner。 And then on top of that。

 we're running actually a mesh classification algorithm。 So that is actually coming with air kit now。

 And it supports a few basic classification labels like table， seat， window， wall chair。 I mean。

 not chair。 It says seat。😊，So this is actually then finally working here for the window。

 Some of the previous examples didn't work so well。 a black surface table。

 it's pretty hard to tell whether it's a black surface table or whether it's some shade that we're looking at some shadow that we're looking at The glass table is hard。

 I have too many hard objects in my little studio here。 The mouse pet works well。

 but we don't know what it is。The screen， we have no idea what it is。 So the。

 it's not really like object recognition is really just very basic labels like wall。

 And so it looks cool。 I think this is the beginning of this vocabulary of objects that it can detect will grow。

 especially when paired with a search engine。😊，So that's why I expect more advances from Air coreps very soon。

 which is done by Google。But we are， we are getting there。 And this is done on device。

 That's something to keep in mind。 It's done on device。

 So it actually has the classification built into。 the algorithms are run on device， pre trained。



![](img/5843a1e58ee536344c12b32b6e65cb08_11.png)

If you wanted to combine with the search engine， which I think is going to be the next step。

 just think of Google Ins and we can detect such a variety of objects and you have this growing corpus of things。

 you actually then do it via the cloud， whether people will be comfortable with that or not that really has to do with how you think about these vendors and how you think about your privacy and security。

In any case， it is useful。 I'm gonna show you people segmentation。

 People segmentation is something you can now do with Air Ki。

 I expect very soon that we have a similar solution for A core。

 probably at when you're watching this it' probably probably already out anyway。

 So this just came out recently。 And I actually Schweta help me with this demo as well。

 She precompiled it and deployed it on the iPad。 And then we did like this。😊。

CoVD 19 save exchange of devices so that I can actually record this in one day and give it back to her we needed before a user study。

Anyway， so this is pretty cool。 what you see here， side story。

 I know I do this in normal lectures all the time。 So what you see here is how I'm going through this virtual object。

 There's a virtual vase。 It's not real。 You can see this by looking at the real world。

 as opposed to looking at the iPad。😊，And then at some stage， it detects it。 My hand is closer。

 so it does peoples segmentation and then actually does it really nicely occludes my hand then starts occluding the bases。



![](img/5843a1e58ee536344c12b32b6e65cb08_13.png)