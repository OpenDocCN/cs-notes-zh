# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p126 42_XR研究前沿第二部分.zh_en -BV1jM4m1k73q_p126-

![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_0.png)

![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_1.png)

So for the remainder of this lecture I want to focus on a case study。

 This is the MRt crisis case study that we presented in our paper called AmRAt。

 the mixed reality analytics toolkit that was published at ChiI。

 What you see here is actually the end of the end result in some sense is one of our user studies we had a few students participate。

 We built two groups， we compared them a little bit。 they came to our lab。

 This is our lab and they were going through this prototype and they were trying to there was some confusion here like how does this actually work so you probably notice a few things you obviously don't see what they see but everybody is wearing a t-shirt here we have no takers in the background。

 they are trying to have just figured out something。And they're commenting on the usability。

 They're doing thinking a lot， even though we didn't really instruct them to do thinking a lot。

 They're using a number of devices。 It's called collaborative task。

Something must be visible to them that we don't see， obviously augmented reality。

 So I'm going to show you what they see。They have a task， it's really important。

In order for this research to be evaluated， there had to be a task。And。Yeah。

 the time it took them to leave that room。 It's an escape room scenario。 that was secondary。

 That was actually not that important。 it was important a little bit。 but we built in some。



![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_3.png)

Issues along the way， some obstacles along the way。

 so you could leave the room too early and you may accidentally die because you're in a war zone for example。

And or when only one person was allowed to leave the room we just saw， they left the room together。

 So that was interesting how they bend the rules。Anyway。

 so that's what happens when you study with users right， and it's interesting。

 So let's look a little bit more in detail what that means。😊。

So this case study I chose because it allows me to talk about four big issues， rapid prototyping。

 And yeah， I'm gonna to show you even in a relatively complex project like this。

 where the main target was the Hollolens。 we went through all the stages。

 I'm going to share this with you。 Then the Holollins has some more specific features。 spatial mesh。

 I talked a lot about this。 When I introduced AR technologies a long time ago。

 So that would be course one。 If you haven't taken all three courses。 Let's talk about it。

 spatial mapping is really cool。 but we wanted to use this to the advantage to our advantage in the experiment。

 and that was pretty hard。😊，You saw probably the tshirts。

 They had big randomly generatedbuhoria markers on them。 So we're gonna to talk about marker design。

 We actually did do custom markers we played around with all kinds of markers， black tshirt。

 white tshirt， even fluorescent markers， the goal was to make that room as dark as possible so that the augmentations are relatively visible and the whole experience for the students is kind of like in a crisis。

 maybe with some light flickering， etcter。 And well。

 couldn't really do that because no matter which marker design we tried。

 we couldn't make it super dark。 it does require for especially forbuhoria， it does require。

 obviously some light。Marker tracking。And then multi user， multi device。

 this allows me to talk about collaboration， which I think is very important。

 so we're going to do that as well。So I'm going to walk you through a few of the prototypes and I'm not going to explain so much what is actually going on and why we did it。

 you can read if you want， but I're going to talk to you more about the stages of prototyping so like with any project we did a physical prototype I asked my students to read some of my papers。

And create this really cool paper prototype。 And they prototyped。

How we're going to augment the lab here， had some initial ideas out there。

And so this is actually pretty cool。And next we did an immersive prototype。

 This is actually one that I created， I did this in Quill and so I was sketching out to my students and I asked actually each of my students to also go through the same exercise and we had this really cool activity。

 but we reviewed each other's prototype。 So this is mine and I wanted the room to be transformed there was supposed to be some fire and in this room scenario so we needed a door to escape obviously。



![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_5.png)

So this was already in VR， but obviously the final experience was an AI experience。

So here I show you the Unity prototype， we spend a lot of time on unity and playing with this prototype。

Has a bunch of features in there。 It starts the simulation， has a countdown。 it Windows explode。

 That one was hard with particle systems， etc cetera。 We have a burning building outside。

 We see some dead people。 And here's one of our key features。 These virtual windows that we created。

And that was very interesting。So。So there's a couple of things going on here now I'm injured in the simulation and I'm going to come back to these budget windows in a second。

 but I wanted to zoom out a little bit so that you can see this is it okay how does this actually work well。

 it'll look different when you play it on Holloins I'm going to talk you through it but it's also interesting for maybe for you to see how that final experience I'm going to share with you how that was actually designed。



![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_7.png)

So I'm going of fast forward a little bit， we already had a little bit of an advanced Unity prototype here with menus and all kinds of items in there and some of these objects are virtual and some of them are obviously actual physical objects but you can probably tell the difference and this is a Hollands one recording。



![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_9.png)

![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_10.png)

![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_11.png)

In this case， we didn't have spatial mapping enabled， so this led to a lot of issues。

 we wanted to have a multi user experience。We wanted to be able to perhaps choose the room in which it's going to take place' it shouldn't be hardcodeed or fixed for our lab and we knew that there will be people in the room and they will be in the way of each other and standing in front of augmentations and therefore occlude them and then it look weird if they have chairs。



![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_13.png)

And everything coming， shining through their bodies。

So here's a prototype with spatial mapping enabled where what you can see now is that obviously we're rendering occlusion and some of the objects are really under the table and you can only see them from certain perspectives。

And you already noticed some performance issues here。 And that's really the long story short。

 even though that v down there is pretty cool。 and the fire。😊，I think my student， Lucy。

 is running this prototype here and we had a really cool fellow students and interns visiting us and they are also。

Hardworking and debugging MRd at this stage。 And yeah。

 you can see how these things are coming together。 Anyway， we have spatial mapping enabled here。

 but it leads to some。😊，issuesssues。So one of the ideas I had was， hey。

 we wanted to create this really big building out there and here's an explosion and window explosion。

 and that was a really cool prototype that Schweta and the team created。



![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_15.png)

So if have if you want to show like a big building out there。

 how are we going to do it with a small fob that we have on the Hols and how we're going to do deal with the performance。

 we just notice issues in spatial mapping。

![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_17.png)

![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_18.png)

So you can never see that whole building anyway， so create why don't we create virtual windows was an idea。

 and we experimented with this a little bit， it helped us address performance issues。



![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_20.png)

![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_21.png)

I'm going to talk to market design now。 So we're going switch gears from spatial mapping to market design。

 I'm going to just continue my story about MRra， the research project。

What you can see here is a combination of different kinds of wounds， trigger warning。

 maybe this is not the one that you wanted to see。 Yes。

 so we were working with somebody from nursing and that person was a professional。

 and she knew how to create those wounds So she did it on mannequins and some of them here we had early prototypes。

 It does look well because we didn't do it right yet， it doesn't look believable。

 and this is like what we called bacon。 this should have been a burn anyway。

 you also see the other issue here quite clearly that the virtual objects are not behind the person。

 but the focus of this video was to introduce it to the marker design。

 So we actually spent some time on creating our own markers。

 and then we did fully custom marker design。 And then in the end we went for these markers because we had to build in identity into the markers。

 it was supposed to be a multiuser experience。But then in the end。

 what these marks allow us are is actually to know exactly who in the simulation is injured。

Because again， identity is built into these markers。 and we know exactly which kind of injury it is。

 We know the location。 and then we can。

![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_23.png)

We can actually do these kinds of scenarios where we triage people。

 It's a multius multi deviceev experience， so you can see these wounds both through the Hollolen and through the smartphone and we're using unity inbuuhoria for that。

 and then you can go through this triage protocol and assign labels， triage labels to people。



![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_25.png)

So that's pretty cool。

![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_27.png)

Then when we actually do a user study， we bring participants to our app。

 This is the whole core of Amd what was really focused on was like collecting these events and allowing you to filter them。

 So it's really cool when you obviously do research with these devices。

 you can collect a lot of the additional data， But then the issue is how do you visualize that data。

 How do you make sense of the data and that is still a little bit of an open question。

 but we did try out this in C2 exploration using an additional device like。😊。



![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_29.png)

The iPad and the hos， And I think there are some cool opportunities。 And obviously。

 once we collect data， we can visualize it in very interesting ways。

 So here you see a step by step playback in the center area。 you actually see a timeline。

 It may not be exactly obvious right now。 And on the right， you see a floor plan。😊。

And then we can filter these events and anything you filter here。

 you can then also immediately preview on the holiday so you can go back to the location where that research study was conducted and analyzed it that way。



![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_31.png)

So I shared a lot of the design process。 It was really quick rundown。

 I talked about a lot of issues that we had to solve and obviously there is more in the paper。

 I was able to show you some of the prototypes that we created both regarding the world experimenting with spatial mapping and in the end。

 that story didn't finish right but the spatial mapping。

 we just had to dis it for performance reasons but that's also where we put dead bodies outside and said to the users stay away from the windows by introducing a scenario。

 you can also guide that we didn't work with one of the participants。 She really went to the window。

 but then another participant was like， hey， you should stay away from the windows don't get killed。

 and that was really interesting how our users our participants really then played that story and they were really cool participants。

 So that was really fun。😊，On the T-shirt side， yeah， so we couldn't get the room super dark。

 we still last trekking quite a bit， the Hollands was actually。

 you know we were using an older version of Unity 2017 that work was well started in 17。

 but it continued until 19 it was published in 20。That's maybe the other story to be thought about this research。

 Why did this take long Michael。 But so with the unity and the spatial mapping and mixed reality toolkit that we used。

 yeah， there were some issues we debated whether we should update。 I mean。

 it was the latest mixed reality Tookit was already version2 for the Hollands and yeah we didn't get the Hollands2 in time。

 I now have it It's there but it was an interesting kind of thing like we were developing a prototype。

 we had kind of almost running And so even had we gotten the latest Hollands。

 we would probably not have switched and debated it heavily with my team and we considered it too expensive to upgrade to the latest version of unity and and Hols。

 the market tracking would have been a little bit more robust。

 We made experiments by the side whether before you has improved and it was interesting because were building such a significant project over two years almost。

That led to interesting new issues that I never that you will not experience in your project and that I never really had to deal with before。

 Now， that's the advantage of living in the research world right。

 we don't have to maintain our products so。Yeah， that was that thought。

 And overall the marker design was still very interesting to me。

 we experimented through rescent markers。 I really wanted to make them shine and blink in the dark。

 maybe just to do the device could we do this could be experiment。

 This It was a lot of room for experimentation。 so many different ideas coming together in this research project in the end。

 the focus was how we presented it obviously using that case study to illustrate the usage and the use of that tool。

 MRRA， which allows you to collect data and in order to be able to do more research in the future。

 we need tools like this not only collect data， but also visualize and then when you collect data。

 we want to be smart and actually responsible when it comes to collecting data one of the last issues that I dealt with a lot and that project was like how do we illustrate these wounds to people and we had like a comic-based version。

 the bacon version and we had a more realistic version and whole idea was like hey。

 it could be different generation。😊，Of medical students using this and then those that are more advanced。

 So you for or something， you know， they need to see something in order for them to feel like， wow。

 this is really a crisis。 And yeah， we did not。 but theres a really cool opportunity to do more research there。

 right you could have different generations of students work together through that experience。

 finally。😊，Whether or not our mixed reality version。

 and that's what I'm talking a little bit more about in the paper。

 whether that improved over the original classroom experience that the instructor that we were working with was using。

 whether that learning experience is better with mixed reality technologies。

Can't say it We have a really big XR initiative here at Michigan now to figure this out and there is some research that gives us some pointers。

 but yeah everybody seems to be targeting tiny little applications and then because nobody can really say whether it generally improve learning so maybe over the next few years we will see more of this tools like MRt will probably allow us to make more progress there as well。

So。Quite an impressive work from my students。 So I wanted to thank you as well for believing in this work and doing it continuing to do it with me until it was finally published as a best paper in the end school。

 so， but I want to talk about good and bad questions in the context of this work and maybe our larger understanding of X R development and then also research and development。

😊。

![](img/f3fb107ad6357e7ae8bdb2b4fdbbcbf2_33.png)