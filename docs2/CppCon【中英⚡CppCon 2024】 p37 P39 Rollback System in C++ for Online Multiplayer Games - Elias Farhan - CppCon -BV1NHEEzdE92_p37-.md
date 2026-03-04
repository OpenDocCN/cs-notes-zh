# CppCon【中英⚡CppCon 2024】 p37 P39 Rollback System in C++ for Online Multiplayer Games - Elias Farhan - CppCon -BV1NHEEzdE92_p37-

From game development to high frequency trading， thanks to QDC， the Qua Develop Cer。

Like we had the Belgian guy giving。 was it a beer he gave， but in Switzerland， we bring wine。



![](img/7b5f33cea8d824590ad960db624f6f72_1.png)

I have chocolate as well with you。Give a good question or give a good good remarks。

 You get Swiss structure。 So I hope it， it can motivate you。So hi everyone。

 welcomee to my presentation。 It's my first time at'm CPPCon。

 I'm really looking forward it to be here。 It was a bit stressful putting up all those slides but I'm looking forward for you to get it in。

😊，So quick summary of the presentation。 I'm just going to do a little introduction about the context of how I came up with this talk。

 I'm going to talk about how it is， why is it hard to make fast pace online multiplayer game why we need the determinministic simulation。

 what is rollback， then we're gonna go in the details of the implementation。

 how you can debug such implementation， Because， of course。

 when you do everything online things get way funnier for debugging and some improvement on the on the on the。

😊，System that I'm showing。So first， I'm just gonna introduce myself。

 I'm Elias Sha I'm the head of the head instructor of games programming at theI Institute in Geneva。

 we're multimedia school that is deliver bachelor， I'm also the co-founder of Indie Game studio。

 team Kqua。 So I know some people here are working in the game industry like bigger company。

 some smaller。 So it's more on the smaller side that I'm working in。

 and I'm also the organizer of the Swiss hormonemon game developer meetup。

 We had a little meeting earlier about bringing game developer to C plus plus community。

 but I'm the one organizing the game dev one， which is more multidisciplinary with art game design and other kind of really amazing things that we do。

 The funny thing as a teacher， unlike a lot of people working fulltime in the game industry is I'm in the privileged position where I can work on my game engines on my technologies without any customer whatsoever。

😊，Without any deadline， I can have a lot of fun。 And that's why I really love this job。

 And then I can share that to my student。 And， of course。

 those kind of technology that I try and develop then often end up in。😊，My games。

 our games at at Timkaqua。The project I'm going focus on for this presentation is this game splash Lapanic。

 It's a game we released in 2018 on Steam Xbox1， PS4 and Nintendo Switch。 It's a unity game。

 So sorry it's a CP comment。 but bringing up a unity game。 It's a local multiplayer game。

 That's really important detail。 with physics based movement。

 It was actually our first game on unity also with cartoony character like you can see with Jetpack Watergon。

 And this game is important because。😊，U。Because we tried to make it online。 And the thing is。

We did it like sort of the wrong way。 We tried to implement an online multiplayer game using a photon pun framework。

 So I worked on it like for several months。 And I was sort of a bit like tongue before。

 when you want to do something。 you really want to go to the end。

 And I needed to have my artist saying stop。 you're just working on something that is not working to stop。

 We cut the multi online multiplayer game， and we release local only。

 And I hope that you can learn from our mistake because I'm gonna show some of them。Well。

 so it's C sharp， but it's really close to C plus plus So I hope you won't mind， but。

The problem that we had in our game is we started to do a local multiplayer game without thinking at all about online。

 mixing all the states。 So， for example， it's typically you see the player character as gameplay。

 physics， audio and graphic object。 That sort of works when you do local game because well things happen instantly。

 the thing is afterward， if you try to do online with those kind of architecture。

 what you're gonna have to do is with input delay， try to interpolate to extrapolate。

 and you could becomes really complicated and obviously for us。

 it means that we failed miserably to do online multiplayer。😊。

So my summer toy project this year was to make an online version of the basic gameplay of Sp blastpans。

 So not the whole gameplay that we had， just like the basic movements。

 which is like jetpack and Wargan。 and I did a C plus+ 20 implementation using STL2 spine photon。

 F mod， DM Gu and a lot of FMT also the whole sourcequad is open source since today。

 it's still a bit boy you'll see and it works for some Nintendo switchitch。 So it's a PC Linux Linux。

 my old Mac book Air and Nintendo switch cross platformat game。😊，嗯。

And what is interesting in this context is you take some C sharp code and you have to sort of translate it to C plus first。

 which has a lot of advantages。 For example， I had this chronometer class that I switched name to timer because it's a bit more clear where I had two attributes。

😊，It's disgusting code。 I'm really sorry for the， for the last one with a period and a time。

 So this chometer was used as sort of a simple timer。 when I needed an amount of time。

 And then when this time was over， I was doing an action， for example。

But when I realized doing this sport on C plus plus is。Most of my periods were constant。

 Like I was never changing them。 So having a floating point number just for to have a constant was not a good idea。

 So I was like， okay， let's try to to put it in compile time as a non type template argument。

 The thing is， it's a floating point number。 So when I did it。 So first。

 I was trying to use my own type as well。 It didn't work out because my type was not once non structural non structural。

So I put a float that could then incomp time convert to my type。 And I was happy it works on M SVC。

 and then I switched to Kang， and it didn't work because it was not yet implemented on Kang 17。

 I know Kang 19 released last week， but I， I was not using this。

 because I was working on a platform that has a custom compiler。

 and I can't change it automatically like I want。😊。

And so I switched to using Integer as milliseconds that you can divide as with like you can put yourself the the dividend。

 But I just put 1000 to say it's millisecond。 And then it worked。

 So I sometimes in games I think Jo said that a lot。 We are better try class。 It's like。

 I need this to work。 I just make it work。 And it's my project。

 Sorry for the people who will have to read this。😊，嗯。

But let's go back now to online multiplayer game。 Why is it so hard to make fast pace online multiplay game。

 When we talk about fast pace， we usually talk about game with not that much entities。 So。

 for example， a big R T S game with tens of thousands of unity is gonna be harder to put in this category。

 I'm more thinking about fighting games。 FPS S football with cars。

Physics based with low latency kind of games。 it's not like very specific with it's like not that much entities because the technique we're going to use require that it's not too big for a poor computer。

So let's talk about the Internet。Because when we have online multiplayer。

 we have to go through this big thing。 that is the internet。

 and we have what we call network latency。 So let's just define the kind of delay that we have to deal with the first one is propagation delay where it simply the limitation of the speed of flight。

 your information cannot go as fast as the speed of light。

 it would be great if it was the only delay it's not the case。

 when your packet packet is going through the network is' going be processed by routers that adds more delay。

 in the router is gonna be other packet because you're not the only one using the internet with your game。

 So your packet is gonna be waiting for other packet to be sent by the routers。 and of course。

 you have the transmission delay is like this bandwidth limitation on all the cables that are going through the Internet and you're gonna be also limited by that。

 And all those delays add up to create this big network latency。😊，What it means is your game。

Is going wait for the other player inputs because this delay is an impact。

 unlike local multiplayer game， where you have a delay。

 but you consider everything is instant when you're implementing your game。In other words。

 we are working with input data from the past。And this time window。 So locally。

 when you're playing your game， you're gonna be at this current frame， like in local multiplay game。

 when you're only in local multiplayer game， you just care about this local local current frame。

But you're going to have only。

![](img/7b5f33cea8d824590ad960db624f6f72_3.png)