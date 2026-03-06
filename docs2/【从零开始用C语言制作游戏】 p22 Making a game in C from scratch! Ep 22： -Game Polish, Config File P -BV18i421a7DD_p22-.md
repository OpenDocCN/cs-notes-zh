# 【从零开始用C语言制作游戏】 p22 Making a game in C from scratch! Ep 22： -Game Polish, Config File P -BV18i421a7DD_p22-

Hello everybody， welcome to this new live stream the series area we are creating an entire game in C from scratch we are almost done with a game you know I've been saying that for the past two streams but today this is correct because all we have to do is to polish what we have。

😊，Every feature is already implemented and we spent know the couple last streams getting the major systems finished and the gameplay done。

 but now we're going to do some tweaking as well as some improvements， general improvements。

And hopefully you're going to be ready， I'm not sure we're going to finish the game today。

 but we are going to get to get to a nice。Spot I think， as you can see， we have the bigger。

 the biggest piece of news we had in the wild， which is the game， has now a steam page。

Where can add to your wish list？And I check it out when it releases， just so you guys know。

 let me just put the calendar here。I'm pretty I'm going to release。220th September， September 2020th。

 yeah。Pretty sure so we're going do a big polishing pass this week。

 probably a polishing pass next week as well I don't know it depends on how it goes and it'll be done I can already play the L my team thing I'm going to show you guys just for fun。

So here's my steam。And the game is here and they can also download the source code there。And。🎼Yeah。😊。

That's that's awesome so I managed to get that working pretty cool so you can go to the store and add that to your wish list it's gonna be free the game the game yeah both on steam on HIO but if you want to follow along what we've been doing now you can go to the HIO page and the game is already there for it to download both the game and the source code so you can just click download now。



![](img/ab18094230a798259ac1baa49f82bf9c_1.png)

![](img/ab18094230a798259ac1baa49f82bf9c_2.png)

And then you can download every episode source code。

 we are in episode 22 and you can go all the way from the first episode。

 download every source code and you're welcome to give me a tip。

 but you can just click No thanks and just download the source code and also change the source page quite a bit。



![](img/ab18094230a798259ac1baa49f82bf9c_4.png)

Things way better now has some like some key features。



![](img/ab18094230a798259ac1baa49f82bf9c_6.png)

And。Yeah， everything's great and you can watch the previous live streams on YouTube。

Which is YouTubebe。 slash Dan Zan。If you go there， you can watch here making the game in see from scratch。

 this is the playlist。You can start you can start from the very first line of code and see everything being created all the way to where we are now。

😊，So I'm just going to。Just going to open up the game here。Go up going to open official studio。

 going to open a far coder。

![](img/ab18094230a798259ac1baa49f82bf9c_8.png)

![](img/ab18094230a798259ac1baa49f82bf9c_9.png)

So that just make that。Cover your whole screen。

![](img/ab18094230a798259ac1baa49f82bf9c_11.png)

And let's see game。It's been a while。Let's see， okay， so I'm going to build an optimized build。

 said development。To one。And okay， let's see。Yeah， so this is the game we have so far。🎼A。

🎼It's pretty much a breakout clone in the beginning。That was pretty cool I think。何？

But then we add a couple of crazy mechanics。Like we did this breakout thing。Where are。

Oh we have power ups。See like this one。And then we have。Break out clone break out palm。

Which is what if Pong was actually a breakout game？🎼That's pretty cool。

And then we did the same thing for Tetris and this one have to we have to improve a little bit today in terms of like tweaking the speed。

And think like that。And then' have break on space invades。

 so that's the game we build and build that everything on a live stream we can watch the entire process。

That'll be that'll be pretty。It'd be a great learning experience。

 I think to watch from the very first line of code。All the way to this team release。

 that's pretty cool。You know， I did some tests implementing this steam API， this team SDK。

And that was one major problem。Which is。呃。In order for this steam overlay to work。

We should have an open jailL or direct that context。🎼And we are doing shorter renderrring ourselves。

So unfortunately， we're not going to have this team overlaying the game when you press like shift tab。

 that's not going to happen unfortunately。But the game will be on steam。🎼You can already。Well。

I think I hear a bug。🎼Yeah， I can。 I can hear。🎼One sound loop， I'm not sure which sound is it。



![](img/ab18094230a798259ac1baa49f82bf9c_13.png)

Maybe it was a car up sound。We're going to have to improve that。

 So that's the plan part today So if you want to。

![](img/ab18094230a798259ac1baa49f82bf9c_15.png)

If you wantna。Go to the HIO page and download the source code now to follow along。

And you can also watch the previous episodes on YouTube。Yeah。

 the last time we did the asset system that was pretty cool， it was like one huge overtaking。

 but today's more like like an open thing， have tons of small stuff to do so。



![](img/ab18094230a798259ac1baa49f82bf9c_17.png)

We're going to do the polish fast and we're not going to do the online subsystem。

Because since you're not going to get the overlay， you're not going to add achievements because they're not going to have feedback for achievements。

And I'm not so I'm going to have CloudSa， I'm going to implement the online subysem just for the cloud save。

 so the polish ended release so I did a lot of notes。From last night，Can grab the notes from here。

Can get all the notes that I did based on。I play the game a little bit and think like that so these are the things that I think we should improve the game there's also these node so there's this is this wrong thing。

We're going to focus on these first。And then later we can。我括上啲一次。

Okay use's a refresh rate that we're going to do today。Make full screen launch prettier。

 I think it's working pretty nice I test that on steam， Let me show you guys again。



![](img/ab18094230a798259ac1baa49f82bf9c_19.png)

啊。On my team page and that was perfect。Let's see。🎼Yeah， it's really fast， though。 I mean。

 we do have a white screen really fast before。 I don't think anyone cares。



![](img/ab18094230a798259ac1baa49f82bf9c_21.png)

So we have more optimization， I don't think we're going to need more optimization。

 I did note a couple things to clean up。But in terms of like serious。

 like expanding the preamble thing that， we're not gonna to need I tested that on several systems and the game is working great。

 even up I don't think it changed， but I updated the storm page to say that we need to like it。😊。



![](img/ab18094230a798259ac1baa49f82bf9c_23.png)

In system requirements， let's say yeah pretty much any potato you have will be able to run the game。



![](img/ab18094230a798259ac1baa49f82bf9c_25.png)

Which means that we did a good job because it's not like a super gra intensive game。

 but we didn't use O and GL， we did everything ourselves， so that was a challenge。

So no need to do that， I think。CmdaA sync stuff， save one quit。

I'm not sure we're going to need that and make the player returns the mouse cursor。

And I don't anything think make the audio safer。 I think you've got a rare case of changing。

And the game。In ref。The audio thing I'm gonna， gonna， we were gonna work today。

 So because there was a crash， someone on each。On HIO based comm this scratch。

 they're going to have to fix that。And again， I're going to try to do this as well。

Review the size of player in the collision。Add a sound to that test the players scale like lower frame ratess。

Yeah， we're not going to need to do that because we're going to run pretty fast。

 so these are the things we need， I think for the Po pass。呃。

We may add some things and we may not do everything， but this is the basic plan we have。

And so the game really in like two weeks， we're going to work on most of these things。

 So the thing is there' is a game called Super great so let's start high suppose silver now with all that pream。

 but that was a pretty big pream but that was a。😊，That was necessary because a lot of news and we are now on a final stretch really to release the game it's going pretty cool I'm really happy with that with how it turned it out。

 I mean it wasn't expecting to be that interesting。



![](img/ab18094230a798259ac1baa49f82bf9c_27.png)

呃。🎼秋爷。The thing is theres a game called Super breakout over like an old art team game and it wasn't like this。

🎼So since we are not。Actually implementing that game's ideas like we are in like tism。And well。

 the other games。I'm not going to make it called to a breakout， so I'm going to change the name。



![](img/ab18094230a798259ac1baa49f82bf9c_29.png)

We'm going to change the name like two。 Let's see。 It's in the menu。



![](img/ab18094230a798259ac1baa49f82bf9c_31.png)

Super， yeah， going to change that to。Power breakout or something。

That should be good enough if you guys have any questions about anything。

 be sure to drop them on the chat。

![](img/ab18094230a798259ac1baa49f82bf9c_33.png)

And I'll answer it， so yeah， power breakout。Oh， the texts not centered。



![](img/ab18094230a798259ac1baa49f82bf9c_35.png)

So we probably want to have to change that center。center。Score next。Probably。So yeah。

 and there is also a typo。And the global variables then we had that for like forever。

Global fair well。萝萝卜。Y， yeah， very u， yeah。So I'm going to have to fix this。Variable。月工。

It's not really necessary but itist。😊，But真的。Dase is the code will be open sourced， I mean。

 it already is， but it's nice too。Make everything kind of cleaned up a little bit。So yeah。黐。Pla。

 okay。じ。Make Te slower， Okay， so we're going to spin。A little bit of time here。

 just make sure that the Tes game is cool。

![](img/ab18094230a798259ac1baa49f82bf9c_37.png)

I mean， it is cool， but I think it's too hard。I tried I tried when I record the trailer because I did a new trailer now your guys can check that trailer just。



![](img/ab18094230a798259ac1baa49f82bf9c_39.png)

Note， both on steam， I really like the way the trails turned out。

I added the soundtrack that I created for the game。Then I did this text thing。

It's pretty con just for anything and let it run for you guys。Hey， open this first game。

You can play around and make all sorts of different changes。

We are liking1 thousand billion frames per second。

![](img/ab18094230a798259ac1baa49f82bf9c_41.png)

🎼デスク？Pretty cool， right？😊，Yeah， and you can also watch that on YouTube。



![](img/ab18094230a798259ac1baa49f82bf9c_43.png)

And I like and subscribing stuff。So when I was recording that trailer。诶。



![](img/ab18094230a798259ac1baa49f82bf9c_45.png)

I had a really hard time to finish the Tees。🎼デも。Which probably means that's too hard。To be honest。

🎼It's pretty cool， I think。But it may be too fast I going to make。Maybe can start at this speed。

We're going to make it get really slowered about in the middle。🎼シーピクス。Way too fast at that point。

And we have a lot of shapes like this。Makes it really hard。Yeah。

 I see if you get like a couple of messes。Pretty much do， and I pretty much do。D once done twice。🎼C。



![](img/ab18094230a798259ac1baa49f82bf9c_47.png)

So that' that's not good， let's go to the levels。And let's see， Te。It's in the simulate level。

Similarly level， if you are with Te。I don't even remember。Okay， so。Yeah。

 so this is what we should tweak。We are going through every enemy。Open that up for you guys。

So for every end， you're gonna to add that initial。Why initial shape， I me see what's that。That's 60。

 okay， so。Yeah， plus。The enemy is right。 So this is how much。This is how much you moved， right。

 Time a very small number。 So if I try to print this。可以。



![](img/ab18094230a798259ac1baa49f82bf9c_49.png)

The spring function was really cool。 It's kind of a， we should really focus on。😊。



![](img/ab18094230a798259ac1baa49f82bf9c_51.png)

I mean， this is a small game， but the larger the game。The more interesting it is to spend time ora。

🎼超だ。So yeah， I can just focus on one of。This starts out as 180 and it goess all the way down to zero as suppose。

Well， I don't want to get it。Yeah， it starts out。🎼20I don't think it's going to get to zero。



![](img/ab18094230a798259ac1baa49f82bf9c_53.png)

Yeah， it goes to like 100。

![](img/ab18094230a798259ac1baa49f82bf9c_55.png)

So one thing we could do。We couldn't make this rate。

Like this enemyP have a bigger influence like this。

🎼So we're going to have a bigger range of motion like it's going to start faster and goes really slowly let's see start is 200 which is。



![](img/ab18094230a798259ac1baa49f82bf9c_57.png)

Pretty fast。But it should get slow wave over。Yeah I see it's already。いクリスト。🎼S 100。🎼Did。



![](img/ab18094230a798259ac1baa49f82bf9c_59.png)

Yeah， but at this point it's kind of impossible， but I kind of liked those values。

 but I think' going to tweak this value now。

![](img/ab18094230a798259ac1baa49f82bf9c_61.png)

Youan make even even。Which twices。

![](img/ab18094230a798259ac1baa49f82bf9c_63.png)

So but 60 was probably too much now， so 60。Can do like。



![](img/ab18094230a798259ac1baa49f82bf9c_65.png)

![](img/ab18094230a798259ac1baa49f82bf9c_66.png)

Yeah。You can try 55。And then。连没捋呢边咧。

![](img/ab18094230a798259ac1baa49f82bf9c_68.png)

Like。2。🎼Let's let me try to beat this game mode。 You guys， you guys can download that on H。

 even right now。

![](img/ab18094230a798259ac1baa49f82bf9c_70.png)

You guys are watching live。And tell me what you think about these。



![](img/ab18094230a798259ac1baa49f82bf9c_72.png)

These changes， I mean， if it's too hard， for instance。🎼Or if it's not， if it's okay。🎼也可。

Just a small note。🎼We are sleeping in terms of。🎼In terms of like frame rate。

 that's why it's like at 60。🎼However。We are not synced to the vertical。🎼Refresh it for book。Yeah。

 to the vertical code blank， we are not because for that word we need openGL。But。I mean。

It's not going to be that terrible。The worst case scenario， we're going to get a little bit time。

Yeah， see， I think now it's， yeah， now they got rotating shapes。Yeah， I really like that。🎼好了。

So this is hard enough。🎼Nice。Okay。I kind of like that。Maybe you can leave it like this for a while。

Just so we play and。め。🎼Maybe in orange。Nice。🎼Okay。Oh see。

 that was the other bug the see the having like a five second thing and it's not updating yeah。

 I wrote that other the bug。And then mouseing。Thiss going to be kind of hard when we go off the screen。

The mouse is activated。

![](img/ab18094230a798259ac1baa49f82bf9c_74.png)

And're probably going to have to avoid that。Let's leave it like this for now， listen just。

Open the window here， it's kind of hot。Okay， so I'm going to leave the ts here and like。Play test。

 tits。Okay， total not updating。 So we just saw that that was the problem and we're probably going to add。

What is the air the mouse？It's gonna be a little bit tricky。 Like get the mouse。Do not。Here。

If you leave the window。So for that slow， let's see， yeah， if it's slow player T is better than zero。

We drive the journal。诶。And。It's weird。Where does it get updated？Where the comment T gets updated。

Yeah， it's here。Yeah， I see。 I kind of just forgot， I kind of forgot。

 I kind of just forgot about that。😊，The turtle， yeah， the turtle， see。So， we'm going to add。T here。

Which is the low player T。Let's see vertical controls is here， strong blocks is here。

 comment is here， number， invincibility。Incent rising in。Yeah， municipal is in a different place。

Together with the rendering， that's okay。Hey， I see you streaming again。 Its the final stretch。

 It is the final stretch， man。😊，You know， I don't think you saw this， but we have a steam page。



![](img/ab18094230a798259ac1baa49f82bf9c_76.png)

So it is the final stretch， the final polish， I think is going to be like one or two more streams。

To get a game on steam because it's already now， it's already there for your to wish list。And yeah。

 it's really cool。 man。 I wasn't expecting to get to this point when I started live streaming this game。

 So it's really， really awesome to see the result。 And you can also see the whole process on YouTube。

 Wow， yeah， be the 3D。 Yeah， it's awesome。😊，So the game will be released on scene' that's really cool。

 I just finished adding the page and the trailer in the last few days。 that's why I didn't stream。😊。



![](img/ab18094230a798259ac1baa49f82bf9c_78.png)

So it is the final stretch we have just a few polishing things to do well yeah just a few things to do I think we'm going to run through that pretty quickly most of them it' pretty pretty easy。



![](img/ab18094230a798259ac1baa49f82bf9c_80.png)

We're gonna run through those polish passes and then it's gonna be released on steam and you can watch the whole process。

 I mean， on on my YouTube channel， you can watch from the very first line of code。

 the entire process not even that many it's like I can go to the playlist's like 21 episodes we have so far and told you're gonna be like 23 including the release episode So yeah。

 it's 21 episodes。😊，When when I programmed the entire thing， whole thing。

 you see all the mistakes I did， all the cool gameplay ideas that changed and yeah， that was awesome。



![](img/ab18094230a798259ac1baa49f82bf9c_82.png)

And now yeah， now it's the final stretch， man， I'm really， really excited， really happy。

It's kind of hard， you know， that's why making games is so awesome because it is really hard to not give up in the middle of the process。

 but when when you don't give up。

![](img/ab18094230a798259ac1baa49f82bf9c_84.png)

What is called breakout， it's called break Arcade Games Out。W's a pretty bad name。

 I'll admit you can already download the source code and HHI。

 you if you want to watch and play around the source code and on steam， it's the same thing。



![](img/ab18094230a798259ac1baa49f82bf9c_86.png)

It's a pretty bad name， but I don't know。 That's the name I came up with because I don't wantna。

 I don't want it called。To be called breakout， because there was an already a game called breakout。

 right。 However， calling break arcade games I was pretty cool because the idea of the game is that you play several acaded games like Po。

 space invades， Tes as breakout。 So the idea is what if every arcade game had to be like breakout。

 So that's the basic idea。 I'm not sure if you guys have any better name suggestions。 I'll take that。

 The game not released yet。 So we can change。 Yes， it's really cool。

 So we should be good to go in terms of the total bug。😊。



![](img/ab18094230a798259ac1baa49f82bf9c_88.png)

![](img/ab18094230a798259ac1baa49f82bf9c_89.png)

Let's just see if you get the。🎼ああ。Maybe the pond one can get a turtle free。🎼文じ？Tianti。

That's the inverse controls。Another TT， yeah， there's a turtle。Okay， so yeah， it updated。

 although I couldn't last long because it's kind of hard when you get the turtle， that's the turtle。

 it's kind of hard to say this slow player you can call that okay yeah。

 that was awesome strong blocks。🎼Everything's nice， T NT。Another one that's see let see。



![](img/ab18094230a798259ac1baa49f82bf9c_91.png)

Yeah。Perfect， so we fixed that bug， as you said， I find it hard to stay motivated on a project。

 any tips。You know， the biggest tip I have in this case is find a very small game jam for you to work on。

Like two days is great。Because you're probably not going to get demoivated on today's。

 I joined the community game jam last week， another reason I did the stream。



![](img/ab18094230a798259ac1baa49f82bf9c_93.png)

And you can watch my result in childhood that's a pretty crazy game I created。

 you can play that on my Z。😊。

![](img/ab18094230a798259ac1baa49f82bf9c_95.png)

We can play that here， Liars mapap。And。One week is a bit too much。

If you have motivation problems and everyone has it， so you have to really tame that beast。

 so I suggest two day projects most。

![](img/ab18094230a798259ac1baa49f82bf9c_97.png)

And if you come here in the Liar map and I did a video about why I love making games。

 so on also my YouTube channel， and I talk a little bit about this motivation thing there。



![](img/ab18094230a798259ac1baa49f82bf9c_99.png)

And because it is ups and downs and in my three and a half year game， I also。

 I also did a three and a half year project。Man， that was tough， man。I released that for PC and PS4。

Two and a half years is a long time。And I had several motivations problems along the way。

 thankfully I wasn't by myself on those projects。So we don't have a team。The motivation really know。

It's really cool because everyone motivates what Im another。

But the problem is I was alone in the first year and in the last year on this project and to be honest。

 even in the last year， which the game was already pretty much done。

 I thought about quitting the game In the last year。

 I was spent like two and a half years and even after that。

 I thought about quitting so it's not hard。😊，So the tip。

 the biggest tip is do a very small project and the great thing about making this game jam。

 the community game jam here。啊。

![](img/ab18094230a798259ac1baa49f82bf9c_101.png)

Is that I created a thread here in the community， I don't think it's going to be visible now because everyone change。

Let's see progress， I created a progress thread here。Well， it's pretty。Pretty deep down here。

 Congress。 Yeah， I'm not sure。But it was great because everyone was sure like screenshot and stuff。

 so whenever I was like， oh I don't know， man， skin's kind of hard， it's kind of weird。

 it's too abstractive， we're not going to get it。I kept you know reading people's progress and I was really motivated by that。

 so that's one way of doing by yourself， having a motivation of the team， right？

But one week is probably too much if you have motivation problems。

 so I suggest doing like two two day game jam is' great because then they're gonna to finish right and it's yeah。



![](img/ab18094230a798259ac1baa49f82bf9c_103.png)

That's the biggest step， it's pretty cool though， when you manage to。When you manage to win that。

 hello， I'm learning C and likes the game。And I think I don't see the hope and like to make a game like you did。

 how did you learn game development？Well， my journey was kind of weird。Because。I first。

I first just played around with tutorials and unity and stuff， then tutorials on Unre。

 and that was when I really started liking the game I was making So you know that this game。

 the three and a half year game I worked on Elioss Hunt。



![](img/ab18094230a798259ac1baa49f82bf9c_105.png)

I have all the progress on YouTube as well， so I started out just making characters。And like that。

 and then I just like watch the cho， how to make the character move。

 so I managed to make the character move like this。So yeah， in know Rio， I was like。

 how to make a character movie on Rio， how to make a movement stuff。

And then how to make a character8。And then I learned how to make it aim right and that was pretty hard at a time I was spent a long time figuring out how to do the whole 360 degree rotation that was pretty that was pretty tough。



![](img/ab18094230a798259ac1baa49f82bf9c_107.png)

Then I was like， okay， how to make a shoot to how to make an enemy。

 And I started building a game like this。

![](img/ab18094230a798259ac1baa49f82bf9c_109.png)

And like like Litic  Edigator asked。This process。The process I did for this game。

 which was my first commercial game。The big game， you really need a lot of motivation。

 So I'm not sure I recommend the way I did it。Because。It's really one step at a time， man。

 and then if you see a couple months later， this I was working by myself， right。

 I had this first level， which was pretty cool。😊，Already。Kind of had some interesting art。

 had some like progress and that system and some enemies that run at you。However， this is not a game。

That's a very small demo， right？Very small， it was like five minutes of gameplay。

 so in order to turn that into a game。That's the problem because I did this in like three months。

 I suppose without learning without learning previously。

 so I was like searching to stories how to make door animation。

And I learned about timelines in a how to make destructable objects， how to make particle systems。

 and I kept advancing that。 So this is the point I got， however， at this point I was like， oh my God。

 in order to make this a full playable game with our game with hours of gameplay。

' going I have a hard time so I started focusing on the alpha of the game。

 which is like feature completeness。😊，So at this point， I focus on just。AtDeigning levels。

 I learned a lot about game design at this point， so I built the level sketch without focusing on making it look good。

And at this point， I had a lot of people on the team because that's the thing once you have a prototype like this。

 I had like a vertical li so speak， that demo and and the alpha version。

Wwhich is this one that you could play the whole level it's a lot easier to get people on board with their game idea so I managed to get a lot of people also students。

 no experienced people， just people like me who were trying to learn。



![](img/ab18094230a798259ac1baa49f82bf9c_111.png)

To get together， so we built， but then it took a while， so it was like one year after that。

This is what we got。 So see how much improved， pretty much the safety thing， right。

 but was improved a lot because I had like people who do the 2 DR the 3DR to the animations。

 another programmer。😊，You know， people really got together and。

You this and that's pretty cool and that's not even the final thing。And yeah。

 I did an announcement trailer and then I did some like some bads hit by my name is Daniel A。

 that's me in 2016 it wasn't that long ago。And。Then we continue to improve the game and at that point we kind of got the base idea for the game。

 but the problem was we needed to make a lot of content and that's one big tip。

Don't make content rich games because。Games full of content is the strength of like bigger videos。

Like we had to do like desert levels and volcano levels and t and lab and sw levels。

 we had to do a lot of variations and it's a lot of work to add all those variations and I'm really focused right now on making like smaller games that you can take you get more bang of your bug so to speak。

So that was a progress we got together at this point that was 2016。So at this point， we' finished。

The basic game， basically at this point。So we finished the character， we proved animations。

 we managed to get the motiontion capture studio for free in the university here in a Belar Z to Brazil。

So we had a motion capture recession where I was the actor because you know into the games right and I recorded the animations and then we cleaned it up and program that was pretty cool man so the animations looked pretty great I was really proud of that yeah。

So we spent a long time like two years， yeah， the team worked on the game for two years。🎼And。Yeah。

 that was there was a lot of work to get out all these variations and amazing and things however。

 we wanted to release for the PS4 right so at this point we didn't have any money and we need to show that advance so we did a kickickstarter。

U so yeah， but we failed， but that was pretty cool though。

 we learned a lot so we got a partnership with people who would do the art book。

 should we managed to get the money。Although we did we did manage。

To to get a partnership and the guy the guy created is。See， this is actually little back。

We also have two statues， we managed get a real statue， I can really get that in the other stream。

 I don't know it's right in the other room， a physical statue for the。

 I'm going to get it just a second。So this is what we've built。For the Dickstarter。

And it looked really， really nice， the guy who did the statue is really。

 really talented and he actually redid the design improved a lot it's kind of kind of broke a little bit near this version。

😊，Yeah， here this mustache here。 But it was great。 So this is a real statue。 However。

 since we didn't get the kickstarter money and it was the only if we were last $15000。

 we're just to get the last push to release the game。 But since we didn't get the money。😊。

We only did like two or three stages， you know people。Couldn't't didn't get that。

 and we didn't release。For the Xbox one and stuff， however。Yeah。

 so so when we didn't get the kickickstar money， we were like， okay。

 we kind of dismantled the team and this was。July 2016， and the game released on August 2017， so。

For one year after the kick started where the team was kind of split up and stuff。

I worked on the game by myself， so that was that was even though we already had a lot of stuff in the game。



![](img/ab18094230a798259ac1baa49f82bf9c_113.png)

As you can see， inspired by crash Benoo， it's really hard， man， the motivation thing。

 it's really hard。

![](img/ab18094230a798259ac1baa49f82bf9c_115.png)

So I was by myself cell phone years was like， oh my God。

 the game's not going to sell the keep started people hated it and stuff。However。

 we did manage to launch that on the PS4。 So this is not the PlayStation channel。 So see August 15。

2017， we released that。On the PS4 and on the PC。So that was a huge victory。

So this is how I learned the game of oh this was the question was how I learned the game of that right。

 this is kind of a tangent， but okay， this is great man。

 is we're just launched the game right and and after I published this game。😊，It were very smart。

 Yeah， but this is where it gets good the story， man。

 it released the game and didn't sell a lot if you go， if you see that it seems like 38 reviews。

 So not not a lot of people play the game。😊，Which was kind of expected。 I mean。

 it was our first commercial game right， and we got some some some kind of negative reviews。 I mean。

 we've got a lot of positives， like 81 positive reviews，81%， which is kind of good when we released。

 we were like up to 90。😊，But since you got to it's pretty cheap。

 it's like 10 bucks and we got like 50% of promotions。People were like， okay， it's kind of buggy。

 I don't know the jump felt weird， the physics， oh， the final boss that was a bug。

 I don't know people complained about a lot of stuff because you know the first game， right？

So I was like， okay， I need to take one step back。

![](img/ab18094230a798259ac1baa49f82bf9c_117.png)

Because three and a half years for this game was great， I learned a lot by making this game。

But I need to take a step back， so I focused on actual learning how to program for real because that's the thing the way I started like I showed you。

Just like， oh how do I make move stuff？While it's an incremental thing to make the game actually work。

 which is awesome， which I managed to do， right， I didn't actually learn。😊。



![](img/ab18094230a798259ac1baa49f82bf9c_119.png)

For real， I was like cutting a copying code from place and since it was like a real blueprint。

 I didn't I didn't actually program It was all like visual scripting and stuff。

So that was like another thing， another point of making a。Making it less robust。

 so that's the thing I wasn't doing very much robust game at this point。

So I learned about handmade heroro。And Hemade Hero is a series tutorial series。



![](img/ab18094230a798259ac1baa49f82bf9c_121.png)

Made by Casey Morory， which is Hero handmade heroro。tor。



![](img/ab18094230a798259ac1baa49f82bf9c_123.png)

I'm going to throw that in the chat case you guys want to know more。And Casey is a very。

 very experienced game programmer who's been in the industry for probably longer than I've been alive。

 so yeah。😊，Certainly longer than I've been alive with。

And hi's decided to teach that through this tutorial series。So see he starts out， you know。

 setting there's an intro to C， so if you want to learn C。However。

 this is kind of advanced and that's the point I want to make， you know。

 so he has a lot of tutorials and by a lot I mean。😡，A lot。

About everything you can possibly imagine in game， pretty much game engine programming。

 not not so much in game design and gameplay， but in terms of programming。

 so I I did a lot of stories in this series and I learned a lot。

 but it was really hard so I really had to push myself because it's not like it's not like an easy introduction。

 it's not like beginner friendly， it's really， really hard。But I managed to do it。

 so if you go to my HIO page， you can see my progress。

 it's kind of funny because I managed to release the end 2017。



![](img/ab18094230a798259ac1baa49f82bf9c_125.png)

If you go to 2018， for instance， I will let me go to。



![](img/ab18094230a798259ac1baa49f82bf9c_127.png)

And you see the gains I released back then。It was like， really simpler， like。



![](img/ab18094230a798259ac1baa49f82bf9c_129.png)

哦，就 see诶。

![](img/ab18094230a798259ac1baa49f82bf9c_131.png)

You， I did like a paw game， which was pretty bad。And this was after releasing oh I don't know if you guys can see right and that was right after releasing the huge game so I took a huge step back to make sure I really understood the process So that was like September thought yeah that was one year after the game release So I spent one year learning programming for Rio So at this point starting to improve a little bit I did a more complicated pun guy。

😊。

![](img/ab18094230a798259ac1baa49f82bf9c_133.png)

![](img/ab18094230a798259ac1baa49f82bf9c_134.png)

Then I worked on a startup for a while。And then this the point where I am now now in'm pretty confident in program like I learned a lot and that was taking a step back so now I think I'm capable of tackling bigger projects again。

 not three and a half year loan projects for motivation and reasons because it's kind of a it's not like I'm not like a full time indie now at this point in my life。

But I am comfortable a lot in programming。 So that was kind of on my journey。

 It's kind of hard to recommend what to do。 I mean。

 if you really love making games and want to alert that。

 you should probably do what I did and go like grab grab an engine and start doing like a game step by step up like how do I make a character move and how do I do I' do the gaminging system。

 how do I make it shoot some animate all the way hopefully to a cool launch。😊。



![](img/ab18094230a798259ac1baa49f82bf9c_136.png)

![](img/ab18094230a798259ac1baa49f82bf9c_137.png)

![](img/ab18094230a798259ac1baa49f82bf9c_138.png)

![](img/ab18094230a798259ac1baa49f82bf9c_139.png)

But I wouldn't recommend that you spent three and a half years in the game， I really wouldn't。

But I don't know， I did， and I can't say I regret it， so I don't know。

 take that with a grain of salt。However， it's really important at some point and I did that after the game you could probably do that before so if you're starting in focusing on programming。

 maybe the best call would be to start learning programming for real and do incremental steps and that's going to help you a lot in the motivation thing so you can do a game in like two days pretty easily。

Even if you don't know a lot about programming。And then and then do a little bit more complex game in three days。

 then one week then two weeks then one month， and if you do that， if you do like 10 games。

 release that on HI for I don't even have 10 games in HIO。

 so I should really do with more games a lot， yeah。And then you focus on video games。

 you're going to be more confident， you're going to be more experienced。

 your games are going to be better， and you're not going to have motivation problems because you're going to see your improvements incrementally。



![](img/ab18094230a798259ac1baa49f82bf9c_141.png)

So I am well now was my plug， right I am working on to start a series about how the program are gained C++。

 which is very beginner friendly。It's not like。So if you haven't programmed anything in your life beginner friendly。

 but it is pretty beginner friendly， if you have any questions you can drop them on the comments and I'm going to try to answer that。

 so if you' go to my YouTube channel which is YouTube concigegan they Dan。If you go to。That。

You can go， you can watch that and you're going to learn a lot and you're going to do punk for thees I'm going to do a more complex one later on。

But yeah， if you do that to start a series， you can be able to get a palm clone。

And then you can do more complex games like。Well similar games like great cow pacing invadeers。

 things like that， and then maybe you can watch this series， which is the game in C。

 which is a lot more complicated， we did like acid training， we did remote threading。

 we did a lot of stuff。And then you can go and watch the handmade heroro charts。

 we're going to learn a lot， but this is pretty advanced and the problem is this is huge。

 this like hundreds and hundreds of hours of being played。



![](img/ab18094230a798259ac1baa49f82bf9c_143.png)

Of game play of tutorials so I don't know， I don't want to do that big， I mean。

 this star is pretty short the H program game in C plus plus。



![](img/ab18094230a798259ac1baa49f82bf9c_145.png)

This making a game you CCCs， this live stream is pretty open like we've been live stream for like 40 minutes。

And we didn't do a lot because it's kind of an open development kind of kind of thing it's a lot longer so thats two hours。

 four hours， two hours and stuff。But focusing on the tutorial series。

 you should be able to get one pretty nicely， I wanted you choose C for giving C++。

 well I like C way better than C++ because it's a lot simpler。

 I wish there were a couple of C++ features in C。But I don't really miss it a lot。

But the thing is for simplicity， I really don't like this crazy complicated code code is supposed to be the way you express。

 the more complicated it is， the harder it is to express and the more complicated it is to follow the game。

So not a big fan of C++ that's why I chose C for this project。 However。

 the tutorial signal'm doing C++ because that's what the industry uses。

 So I am the tutorial S I am using in the C++ and there's a couple problems with C as well。

 Like when I try to implement the steam SDK。😊，For our game now for the breakout game。



![](img/ab18094230a798259ac1baa49f82bf9c_147.png)

When I implemented this C K。Now was the problem of the CMSK actually being in C++？

And a couple things， like there were a couple of crazy templates used for callbacks and stuff。

So I had to create my own header files for those。And since we are softwareer rendering for this for this game。

 I ended up not even。

![](img/ab18094230a798259ac1baa49f82bf9c_149.png)

Finishing the SDK。

![](img/ab18094230a798259ac1baa49f82bf9c_151.png)

It wasn't a problem， but if this game was supposed to use a lot of steam features。

 we're going to have a harder time just because it's in C and O C++。

 so I really don't recommend C for larger game project。



![](img/ab18094230a798259ac1baa49f82bf9c_153.png)

Certainly C plus plus is the best tool for that today。 But for smaller games like this breakout game。

 Certainly certain words。 Have you tried Zig or Oin， I。

 I really wanted to try O in because I think it's great。 It has some awesome ideas。😊。

And it feels great too。And yeah， a language that focuses in on the joy programming is really one focus it's really the goal right so but I haven't tried yet just because I'm in the hype train for JAI so I'm on the JAI team and I have been for a few years ever since I started learning for real programming which was 2017。

😊，I've been which is not that long ago it' like two to two years yeah。I've been on the hype train。

 so I'm patient， I've been on high train for a few things as well。So yeah。

 so I don't want to jump into Odlin and then jump into JI because switching languages。

 there's a small， there's a oh not not that small， there's kind of a。

Significant friction thing until you learn all the ins and outs of the language because I don't want to program like just like a program now in those language because they have a lot of cool meta features which I really want to use right so I really want to dedicate a lot in learning that。

But since。J I is going to launch。 and that's probably going to be the language。

 I'm kind of waiting for that。 So same thing for fourcode。 I really wanted to do like a。😊。



![](img/ab18094230a798259ac1baa49f82bf9c_155.png)

A custom layer for four codeder， but since the beta is going to launch the end of this year and then a wait so yeah。

 I'm not really in a hurry。Even to change languages because I really like C C is pretty pretty nice。

 And I'm， yeah， so finished tule not update getting the sleep granularular。 Okay。

 so that's a very small part。 It's the game you are working on complete from scratch。 No yes。

 mens completely from scratch。 It's not even not even open GL man。😊。

The whole renderry we did ourselves， so these are our draw rectangle in pixels。

And we are going to improve that， I think， today。The way we iterate through this pointer here。

 we don't need to multiply that every frame can just add the page。

We did the rotated rack that was that was a little bit harder to do。The Rotator Act。

 we did the bitmap support so we can draw bitmps in our software rendering。

 so we do texture manufacturinguring， calculate the Us and everything you can watch on YouTube。



![](img/ab18094230a798259ac1baa49f82bf9c_157.png)

See the first day we did basic rendering， then we focused on some gameplay， we did prototype。

 some gameplay more。And then some levels， the crazy ideas， some particle system。

And in some cool animations， then we went back to the graphics at a bitm support， at rotated support。

And an audio， which was pretty cool。Have had parallelism to the audio system and mixer？

Inment the menu， the transitions， the sound effects， those are pretty cool。

 we optimized the game and got that five times special games running great。😊。

We finished some animations。That was pretty cool as we all finished the level design at a camera shake collision and animation levels and the last stream we finished the asset system and now what we have to do is to do small things like small polish things to release the game on team guys gonna to be awesome when I program so yeah no agents at all when I programme the game sometimes。



![](img/ab18094230a798259ac1baa49f82bf9c_159.png)

Sometimes I leave your v and background running and I feel the same running now that I take a few minutes off to get re motivatedtated by watching our video album。

 I feel like I'm codinging someone that's awesome to hear man。

 I'm really glad that you're enjoying the live streams。

It's kind of hard to make the game entirely on a live stream because sometimes I really want to like search a bug offstream or I want to add something quickly I' really mo。

 I want to do something quickly， but I was really glad I stick to that plan until the end。

It's really worth it now that I'm pretty close to releasing it just finishing up some policy。

 I recommend CR or C++ but without using much of a C++ specific functionality functionality for any beginners。

 it might be hard with C at first or you really learn programming。😊，Yeah。

 I also agree of not using crazy C++ in the beginning。



![](img/ab18094230a798259ac1baa49f82bf9c_161.png)

Even even great like tutorials， like there's the great word from the Chno guide。确认个方向。Yeah。

 he has great tutorials， you know those are a bit on the long side though。



![](img/ab18094230a798259ac1baa49f82bf9c_163.png)

But to8 and it has also C+ tutorials as well， but it gets really crazy really fast and that's my problem with C++ man I mean C is so straightforward I mean you have those tools which are not that many and then you can do all sorts of crazy stuff with it。

So I really think a beginner programmer should learn C not S++。

 and then the bigger the projects you do， the more S++ features you add。Well。

 I'm maybe going to add some templates here and things like that。Why not open GL， Well。

 I could use open GL， nothing against it， but it's really awesome to write your game your your ranger from scratch。

 It's really cool to have。😊，First of all it's great to debug it right you can go like you can step into the pixels and see the values of like do we did alpha blending and we see where the love happened and we optimized it so it's a great learning experience。

So that was one of the goals， the other goals because it's it's kind of fun as well because we're not doing like crazy stuff like 3D and stuff or lighting。

 we're just doing some bitms drawing， rotating stuff that was pretty， pretty easy。😊，Uh。

 but next game， which I'm planning to do audit tutorial on， is going to be another simple game。

 but I'm not going to do as much live streams I think。



![](img/ab18094230a798259ac1baa49f82bf9c_165.png)

I'm going to focus more on this tutorial structure。

 apply step by step thing that I added later on stuff。

 then I'm going to use openGL people like OpenGL and stuff， so I'm going to use that。



![](img/ab18094230a798259ac1baa49f82bf9c_167.png)

Hello that guy has videos from S++ on PG and's making an engine in S+。

 I'm really excited for his engine because he。😊。

![](img/ab18094230a798259ac1baa49f82bf9c_169.png)

He's really experienced。 I mean， if you see kind of his rendering videos I don't know。

 I fixing skeal image。 Yeah， have forgot if you watch like some of his rendering， Yeah。

 so he wrote that rendering from scratch。😊。

![](img/ab18094230a798259ac1baa49f82bf9c_171.png)

And it's awesome。 I man SpR and he can control all sorts of crazy stuff。 So if he's really。

 really talented， he really knows his stuff。 Yeah， hiss his videos he's fixing a reflection but。

However， he uses like really modern C+ plus。 So that's why I'm not super excited for his engine per se。

 I mean， I don't think I'm going use the engine， but the destroyr is going be great。

 I I I'm really looking forward to getting like to this cool。😊。



![](img/ab18094230a798259ac1baa49f82bf9c_173.png)

Bin features because I think I'm going to learn a lot from him。

Would be going to have a mouse sensitivity config try to play on my setup was really hardm that was a good idea man。

I think I may， I may actually。开。I'm not sure how okay， I think I'm going to at least know that mouse。

Sensitive。三す。放飞。😊，I think I'm going to add that that's a good point， C++ is crazy。

 I kind of wish beginner programmers。Could it be in that during the days of starting with no as and just a blank basic cursor？

Those days are going， man， I didn't live in those days。And just to get an idea when I was born。

 there was already PS1 games running 3D with hardware。When I was born， when I started playing games。

 there's already like PS2 and like open to world 3D games。And when I started making games， oh man。

 that was crazy。Yeah， I didn't I didn't。 I didn't see that error。

 that era of programming with a No O or things like that。 I kind of wish I saw that as well。

Because I see people like Jonathan Lowe talking about that all the time。

Is it possible to program in a PC without OS just files？Yeah， it is possible。 You could。

You could do that， however， since everything runs on drivers today， especially like even USB。

 even mouse and keyboard， you're going to have a hard time。

In those elements like getting USB mouse to work， so it's not it's not。It's not that easy。

 unfortunately。So today is more complicated that there's a video about it， there's a 000 20 million。



![](img/ab18094230a798259ac1baa49f82bf9c_175.png)

20 million line。来一首头他。The 30 million not even2 the 30 me lines of code。

 You can watch that on this idea of like。😊，Programming， well。

 understanding the machine and be able to do that。So， yeah。



![](img/ab18094230a798259ac1baa49f82bf9c_177.png)

呃。Hey VZ AL， V AL， how do you suggest the mouse sensitivity thing， We could just add a text file。

That you can configurefig that off the game， that would be pretty easy you can do that even today。



![](img/ab18094230a798259ac1baa49f82bf9c_179.png)

Just to have a text contact file。

![](img/ab18094230a798259ac1baa49f82bf9c_181.png)

But if you want to do that in game， I'm not sure how we should do that because。

We don't really have an interface face for changing this here we could add a button like here in the side where're like you click。

You hold and then you slide， change it。🎼But that would be weird。

I don't know if I'm a fan of that or not， I think I'm just going to write a config file。

 let me know where to think about that if you think that's a good idea since you suggested mouse sensitivity。

Uh yeah， like。TXT file text file that comes with a me Yeah nowadayss really hard back back then it was all that you could do。

Wicard didn't use PCs， you could use a C。To some other computer model， man。

 it wouldn't be really cool。

![](img/ab18094230a798259ac1baa49f82bf9c_183.png)

To live that back then， I mean， to see all the crazy innovation in terms of hardware that'll be pretty cool that would have been pretty cool to see and live by and live through。

 yeah。Okay， he thinks it's okay， so we're going to add a config file。



![](img/ab18094230a798259ac1baa49f82bf9c_185.png)

Add a conflict file， you can probably to do that today。Change。And nowson David。

 they'll be pretty cool to do that today。Since there was a lot of people on stream， like 15 people。

 It's a lot。 So I think we're gonna add that。 Today stream is gonna run for a long time。 guys。

 It's kind of early。 So yeah， yeah， set the sleep gra。 okay， so this is the sleep graer thing。

 I tested on several， several computers and the performance is great。😊，However。

 we have a small problem。Of a。We have a small problem of a sleep thing。 Let's go back where we sleep。

Here。😊，We are sleeping in milliseconds， but some computers especially older computers。

 this computer we can't see any problems as well as well as other computers I tested。

 but other computers like other laptops and stuff。The sleep granularity is pretty high。

 it's probably like 10 milliseconds， so if you set to sleep like two milliseconds。

 you's can to leap for 10 milliseconds。And that's not what we want。So it's really easy。

Call this time to period functioning Windows in because go I can't test that on this PC。

 I'm going to have to test that offstream and then next stream you're going to see if that worked。

 but it's really easy， It's just a function that sets the resolution。



![](img/ab18094230a798259ac1baa49f82bf9c_187.png)

For sleeping and other things， so it just call time again period and say how much is the period so we should add like to one with a second。



![](img/ab18094230a798259ac1baa49f82bf9c_189.png)

That's basically it。Just when we start the game， I'm going to set the time to compare to one。



![](img/ab18094230a798259ac1baa49f82bf9c_191.png)

That's it。And I don't think I'm going to see any change like at all。



![](img/ab18094230a798259ac1baa49f82bf9c_193.png)

Yeah， well。

![](img/ab18094230a798259ac1baa49f82bf9c_195.png)

Okay， so we have to link against another Windows library。



![](img/ab18094230a798259ac1baa49f82bf9c_197.png)

I see， which is win MMm， okay， so let's link against that。

Lets see where do we have our libraries here？

![](img/ab18094230a798259ac1baa49f82bf9c_199.png)

Okay， so that's in this library and we should be good to go， let's see。



![](img/ab18094230a798259ac1baa49f82bf9c_201.png)

Yeah， see so no change， no apparent change。

![](img/ab18094230a798259ac1baa49f82bf9c_203.png)

But hopefully that solved the sleep engineering of the other computer that was like 10 minutesfactor。

O。😊，I was see these things are really easy。 Lock the frame to the device gaps。 Okay。

 so this is another。😊，hWe should be able to get the user refresh rate。



![](img/ab18094230a798259ac1baa49f82bf9c_205.png)

And now it's hard called this。Pretty easy as well， we have the， I think we have to get device gaps。

On MSDN， pretty sure。Which retrieves the device specific information， well， that's useful right。

 so we be in HC。And an index item to be returned。Well。Let's see， so driver version technology。

 horizontal size。Bs， planes， number brushes， number planes， colors， clip gaps， spellets。

It's another right call， oh yeah， B refresh， this is it， the current vertical refresh it。

We're going to call G device caps。

![](img/ab18094230a798259ac1baa49f82bf9c_207.png)

![](img/ab18094230a798259ac1baa49f82bf9c_208.png)

Bypasing the HTC and this guy。

![](img/ab18094230a798259ac1baa49f82bf9c_210.png)

So we should return an integer， which is like the refresh。Great。对。😊，And with that。

We can just set the the。The last DT。To be the refresh rate。Which is 60， for instance。As a float。

Divided by Zcor， divided by1000 because we want in seconds， so it's 60。Divided by1 thousand00。Now。

 that's not correct。 It's one over 60。 Yes， so it's one over 60。Yeah， just one。Okay。

And this guy's just going to the last。I'm going to step through this goal just to make sure that it is correct。



![](img/ab18094230a798259ac1baa49f82bf9c_212.png)

Let's see。Here。Refresh rate is 60 last DT。I think we got that optimized the last。Yeah。That's okay。

 the refresh rate was correct，60。

![](img/ab18094230a798259ac1baa49f82bf9c_214.png)

Perfect。So now people should be able to run on high refry monitors and I can't test that because I don't have a high refry monitor。

 but if you do， let me know if it works correctly or like some cr stuff happens。Okay。

 so now it should be locked to the correct。So they're correct？ItT to DT。

This really doesn't matter because this is the audio。

This is okay optimizing the real pixel pointer so this is a small optimization I don't think we need to do this。

 but it's kind of a good to note。Let's see， this is the the as well， oh we also bit a profile。

 I kind of forgot about that。

![](img/ab18094230a798259ac1baa49f82bf9c_216.png)

That's pretty cool， we got a profiler for the game， man， we did a lot of stuff on this side。😊。

On the series， when did the profile it。

![](img/ab18094230a798259ac1baa49f82bf9c_218.png)

Yeah， we programmed the profile and then optimized that on one stream。

 one four and a half hour stream， that was crazy。That's pretty cool。啊，ok。嗯。Let's see， I of lost my。

 okay。However， this is not well optimized because this is the thing for every row。

 this is just the draw， right？

![](img/ab18094230a798259ac1baa49f82bf9c_220.png)

Let me， let me draw in case or not， you don't remember。 but this is the thing。

 And I' if you want to draw。Let's see if we want to draw a rectangle。

Let's say you want to draw dis recectangle。Okay， so we set the pixel pointer here and then added。

Addded by one， which is okay， and then has to set the pixel point to here。

And this is what we're doing like for every rule， we calculate the new picks appointed。

 but the more effective way to do this。Would be to add。Fix the amount based on this pointer。

So instead of just having to do this all the time， like buffer with the time supply and stuff。



![](img/ab18094230a798259ac1baa49f82bf9c_222.png)

We just calculate the pitch or stride， which is the common name for this amount that we need to go to change。



![](img/ab18094230a798259ac1baa49f82bf9c_224.png)

![](img/ab18094230a798259ac1baa49f82bf9c_225.png)

Change like this。 and then you can just add a pixel pointer So the pixel is going to start out。

And this position。ok。😊，And then we also have a pitch。You can call that stride if these meta stride。

And the stride is going to be。The width。Since we are going by one in one pixel。

 so we don't have to multiply that。By this size of U 32。

 but we should have multiplied that by four if we're going like one byte at a time。

 but that's not the case。

![](img/ab18094230a798259ac1baa49f82bf9c_227.png)

So I update the pixel and then I should be at this point。



![](img/ab18094230a798259ac1baa49f82bf9c_229.png)

I should really just create like a role going to create a role。And then， I then set the。Oops。

And then here I'm going to set the pixel。The row。And then here I'm going to set the pixel。Well。

 grow plus equals right， yeah。And then pixel equals growth。

 so instead of doing that whole add and stuff and multiplication stuff， we're doing just one ad。

So this is more optimized， let's see if it didn't break anything。



![](img/ab18094230a798259ac1baa49f82bf9c_231.png)

No， it's super good story。

![](img/ab18094230a798259ac1baa49f82bf9c_233.png)

So it didn't change anything visually and probably the performance was very small。

 but it's a nice cleanup thing to do and there's also it's probably a better way to do this in terms of code。

Yeah。But I'm going to do these in the other cases as well。And add this guy， remove this guy。

Draw our rectangle transparent pixels。Okay。系啦。C。😊，Okay， okay， and let's see whenever I iterate。Again。

 this is the dessert。Number dry， very effective。Font fonts okay is the draw Act。See。

 this is the draw transparent data Act。Probably can do the same thing here。And at this point。

 I'm going to set the row plus equals the stripe。Se that a pixelel to the row。

And it should be good to go。And。Let see what else the rotated wreck Oh yeah， same thing。

 but it's not transparent See this winter we did a lot of stuff to be really specific in some cases。

So it's kind of confusing。If you really wanted to focus on making a good。So after rain。

 we have to clean this up a lot， the that's not the case here is just to make an educational and a fun thing to do。

I think it serveds its purpose pretty pretty well so okay， I do have this right。Striide。

But this stride is v times the bitment。Source pixels。Wass the stride？い？

isI'm going to call that the UV slide because I want to think too much about that。And let's see。嗯。

Yeah， we kind of optimize that away here。The transparent rotative pixelsels。Yeah。Mean bound。

 x plus one， mean bound， y plus one。Yeah， well。I'Not not sure saving that in a variable is going to make it better or worse and I don't want to。

Well， check out stream some other time， but I'll seen non needed the game programming without their regrets。

Of one level。Take for this tree， thanks man。Thanks， I'm glad you liked it。😊。

So same thing here should use the x bound。Otherwise ground as well。ok。



![](img/ab18094230a798259ac1baa49f82bf9c_235.png)

And let's just make sure we didn't break anything。Before we continue。



![](img/ab18094230a798259ac1baa49f82bf9c_237.png)

🎼Okay。🎼We didn't all let me just see them。 Yeah， we didn't break。



![](img/ab18094230a798259ac1baa49f82bf9c_239.png)

他这一月。Good啊。And here I'm going to go under the same thing。つ？Same thing here。Ifiglow。

 we' not to calculate that every frame。But here I am going to set the row plus the stripe and the pixels it's going to be equal to do it。

Inbalance。Well， in this case， I'm going to use。X0。And I why one。

 maybe we shouldn't do that and why I don't remember if that was a good optimization or not。嗯，迪。

Sureably run with the profiler on just to make sure we didn't do anything stupid。

It's also nice for you guys to see the profile it's not stuff like。



![](img/ab18094230a798259ac1baa49f82bf9c_241.png)

Greataper father would did that like 30 minutes or so one hour。Yeah， we're pretty good。

try making that full screen。

![](img/ab18094230a798259ac1baa49f82bf9c_243.png)

Okay turn the development mode off。That's。

![](img/ab18094230a798259ac1baa49f82bf9c_245.png)

🎼あ。Yeah， we're running jazz pretty， pretty well。

![](img/ab18094230a798259ac1baa49f82bf9c_247.png)

Okay， so I don't think it changed anything， to be honest。



![](img/ab18094230a798259ac1baa49f82bf9c_249.png)

I don't know' i'm going to test the performance again after those things Oh we also have the subtix rectangle oh it's just a transparent one and I think there's no。

No。Yeah， that's it， that's those are the rain calls， so we did the small cleanup。

I think it's a little bit better， it's not much difference， let's see， in the transition block。

 don't draw the blog， okay， so this is actually a problem。



![](img/ab18094230a798259ac1baa49f82bf9c_251.png)

So we have this cool animation， right？C。😊，11 transition。However。

 that's it' going to destroy a few blocks， take a look at those destroyed blocks。

I'm going to press the transition animation now。

![](img/ab18094230a798259ac1baa49f82bf9c_253.png)

See that they come back。That's because in the menu， when we do the transition。Draw out transition。

We through the blocks。That's where we are assert if the block is alive。I wasn't expecting that。

Expecting the blocked。Oh， maybe we we zero the blocks before I know， I don't know what's going on。

 let's see。I don't remember this code， let's go pointer to a block。If there's no life continue。

That's what we should do。There's no life。Drss a pixel dude。How come it's not working。Let see。Okay。

 I was。I was in the wrong one， this is the lever transition。Let's say， two。去点灰。

And this is the level transition to man and this one we're not checking and this one we should。

That was the problem。

![](img/ab18094230a798259ac1baa49f82bf9c_255.png)

Now it should be good to go I really like doing these polish passes。



![](img/ab18094230a798259ac1baa49f82bf9c_257.png)

But now we don't have an animation， why not？

![](img/ab18094230a798259ac1baa49f82bf9c_259.png)

Oh， because this not meant to。

![](img/ab18094230a798259ac1baa49f82bf9c_261.png)

I really like doing these small polish passes because it feels like we can bere doing such a huge amount of progress。

😊，Because we are across a lot of stuff out the list， those are pretty stuff。

 I really like doing like this huge things like we did less streamers about doing the asset system。

Well it's not working。I really like doing that， but doing these small things I really like well。

 so that was clearly not working。

![](img/ab18094230a798259ac1baa49f82bf9c_263.png)

Drss simulate blood level。

![](img/ab18094230a798259ac1baa49f82bf9c_265.png)

R right Excel block plus。If there's no life。

![](img/ab18094230a798259ac1baa49f82bf9c_267.png)

嗯。Yeah， this is weird。次。

![](img/ab18094230a798259ac1baa49f82bf9c_269.png)

一去来 say。When do we draw。Okay， yeah， because we're doing that iteration here， so block。Oh well。Okay。

 but now we can go back。This guy kind of forgot。I'm kind of forgetting all this stuff today。Okay。

Kind of worked。Well。何し？Good， but I think。One block I was supposed to draw to。D correctly。🎼Yeah。Well。

Mytro is going to be hard to be broad now。But it's not that big about just a small video thing。



![](img/ab18094230a798259ac1baa49f82bf9c_271.png)

I think this is okay。I think this is okay。Now。Optimize the overdraw in the transition to back them menu user is current correct。



![](img/ab18094230a798259ac1baa49f82bf9c_273.png)

I don't think I'm going to need to do this optimization because the thing is。

In the transition vitamin， yeah， in our transition back to the menu。They're doing a lot of overdr。



![](img/ab18094230a798259ac1baa49f82bf9c_275.png)

Because we have to draw the， let's see， exactly。Meニュ。To menu。

 first we cleared the screen with the arena collar。And then we do the transparent re。

On the whole arena， see this guy。So this problem， we are overdraing twice the screen。However。呃。

Using transparent res， the other option would be to add a transparent react for every。Every block。

 instead of like adding another solid on top of the blocks for them to fade out。

 I would have to make them fade out。I'm not sure which ones are going to be better in terms of performance。

But I don't think I care that much。I'm going to turn the development off。But I am going to。

Toull the georain rate here。Just so I can see the frame rate。And just to make sure it sees。



![](img/ab18094230a798259ac1baa49f82bf9c_277.png)

Just make sure I have a decent frame rate。It's really fair。 Yeah， I don't， I don't have a。

I lay out for like one frame for a couple frames。

![](img/ab18094230a798259ac1baa49f82bf9c_279.png)

But thiss not interactive。I really don't care that transition is not performing。



![](img/ab18094230a798259ac1baa49f82bf9c_281.png)

So。Yeah， this thing， I really don't care。Review colors。Yeah， this one's pretty， pretty needed。

 I think。Because the colors are really random and it's kind of funny because if you watch。

The I' I don't remember which one is it， but it's pretty early on。

 like here we already have some interesting colors。



![](img/ab18094230a798259ac1baa49f82bf9c_283.png)

These colors were like accidentally chosen and those were pretty random and even for the trailer。

 like for this image here， this image， see that I changed the colors to make them more interesting。



![](img/ab18094230a798259ac1baa49f82bf9c_285.png)

![](img/ab18094230a798259ac1baa49f82bf9c_286.png)

IPretty sure I'm going to do that。Pretty sure， let's see the levels I have the colors here if I'm not mistaken。

Oh， I have the level colors here。And the block color probably is going to be in the span。

Which is the block block。I really like this function name when I created， I was like。

 I'm not sure I like this function name blah， blah it's kind of weird。

 but it's really easy to search。 And there's a lot of value in that man。

 there's a lot of value when I worked in a larger color base code base。😊。

Its being able to search the functions that you want fast is really valuable。

I really like the create block function。So does it receive of a color？How's the color set？

Yeah make color。Its on K， yeah， this is hard coded here。But blackla， black。

And the other guy probably set their color。Yeah， so pong， pong is pretty nice I think。



![](img/ab18094230a798259ac1baa49f82bf9c_288.png)

So this guy should probably needs to bit more worried。🎼This guy I not mind， Im not sure。黄wood great。

🎼I really like college好。Tats is also good， I think。Basic beers I really like as well， so。

Probably this guy。Do you guys have any suggestions in terms of colors。

 let's see I took a print screen？

![](img/ab18094230a798259ac1baa49f82bf9c_290.png)

![](img/ab18094230a798259ac1baa49f82bf9c_291.png)

Let's see， I could search for like。Action colored palettes。



![](img/ab18094230a798259ac1baa49f82bf9c_293.png)

Let's see if you got a cool color palette。Yeah， something like this。

 but we already have green as the plate， it's not going to change。That's pretty cool。

 but I want like a color pette generator or something。I呀 see。

It's not action or in action in terms of like being used。啊，记。Let's search for like。

Let's search for like。Coed palelleette。按我汉0发的。Inspired by digital products。You just generate one。

 yeah， this is the one I kind of I like going sometimes to。See， these cars are pretty cool。



![](img/ab18094230a798259ac1baa49f82bf9c_295.png)

You try adding those。Which one is z this， this pretty ugly？



![](img/ab18094230a798259ac1baa49f82bf9c_297.png)

We have， I like kind of like the pink and the yellow。These guys。😊，I don't like the background though。

We can try adding green to the background。The players already agree。I'm going to try this red。

 these two reds， this red and this red。

![](img/ab18094230a798259ac1baa49f82bf9c_299.png)

So it's FA6775。A 6。はい。Well， I know what。I'm to comment this now。



![](img/ab18094230a798259ac1baa49f82bf9c_301.png)

7，7 F A 6，7，75。Then F5，2，5，49。

![](img/ab18094230a798259ac1baa49f82bf9c_303.png)

A five two，5， four a9。

![](img/ab18094230a798259ac1baa49f82bf9c_305.png)

Let's see。Let's see how that looks。

![](img/ab18094230a798259ac1baa49f82bf9c_307.png)

🎼Well要。I like the idea， but that's not very visible。



![](img/ab18094230a798259ac1baa49f82bf9c_309.png)

Let's try switching them around。

![](img/ab18094230a798259ac1baa49f82bf9c_311.png)

Maybe you can just tweak those colors。

![](img/ab18094230a798259ac1baa49f82bf9c_313.png)

🎼Yeah， oh my eyes。

![](img/ab18094230a798259ac1baa49f82bf9c_315.png)

The colors should be darker， really。Let me go to like afininity photo。You know what。

 I bought affinity photo thanks to an awesome donation on HIO。



![](img/ab18094230a798259ac1baa49f82bf9c_317.png)

So that was that was awesome。 I really like， I really liked software， you know。

 I couldn't afford like paying。😊，Photoshopping more。So yeah was great being able to。Pect awesome。

 thanks。 And if you guys like the content， you want to drop me a couple bucks and they try you。😊。

I really appreciate it。

![](img/ab18094230a798259ac1baa49f82bf9c_319.png)

Here on， let me just re the link。Sorry for the guys watching that later on on the stream。

Because I talk about each other like a thousand times， dzd。h。

o and you can download the source code for this game。



![](img/ab18094230a798259ac1baa49f82bf9c_321.png)

![](img/ab18094230a798259ac1baa49f82bf9c_322.png)

To learn and increment and play around the licenses， do whatever you want。

 you can do whatever you want with source code， no license。



![](img/ab18094230a798259ac1baa49f82bf9c_324.png)

Okay， so I'm going to start out， I'm going to start off with this color。还是。

And I'm going to make that a little bit darker just add a new。差的。Okay。Kind of like this。给。😊。

And let's see the other color， the other color be can be a little bit like well。

Try to keep the other color。

![](img/ab18094230a798259ac1baa49f82bf9c_326.png)

🎼可以。🎼力でいくぐらいす。🎼But I think you may actually use that for this night。



![](img/ab18094230a798259ac1baa49f82bf9c_328.png)

I can just try stretching them around。

![](img/ab18094230a798259ac1baa49f82bf9c_330.png)

I'mNot sure what you guys think， what do guys think， man， I need some feedback that's not really my。

My expertise。Oh， this ones really ugly。

![](img/ab18094230a798259ac1baa49f82bf9c_332.png)

Maybe I shouldn't do like this big thing。Just for the sake of comparison。

 let me go back to the colors we had。

![](img/ab18094230a798259ac1baa49f82bf9c_334.png)

Maybe all this color tweaking just to make a that。🎼Yeah。



![](img/ab18094230a798259ac1baa49f82bf9c_336.png)

I没。I don't like these colors， so I'm confident about changing them。



![](img/ab18094230a798259ac1baa49f82bf9c_338.png)

But。

![](img/ab18094230a798259ac1baa49f82bf9c_340.png)

But I don't like these colors either。Maybe they can make it like a darker color even。For this guy。

Like this。

![](img/ab18094230a798259ac1baa49f82bf9c_342.png)

是。

![](img/ab18094230a798259ac1baa49f82bf9c_344.png)

Okay， I kind of like where this is going。🎼Kind of like。



![](img/ab18094230a798259ac1baa49f82bf9c_346.png)

是。

![](img/ab18094230a798259ac1baa49f82bf9c_348.png)

I dont know， what do guys think， what do guys think about these colors？

I think the beck kind of k noggle。

![](img/ab18094230a798259ac1baa49f82bf9c_350.png)

Is it hard to see， it's probably hard to see if I put that black and white's going to be like impossible to see。

That mean I like a human saturation filter。Well， it's not that bad。What do I want in terms of。Like。

Brightness。Yeah， I want a darker， I want like this。Wow。😮，Mh。Let's see。Let's try these colors， maybe。

也是诶。This。This is a nice。 This is a great value。 I mean。

 you can really clearly see the ball of the player and the game player object。

 That's a nice tip for you guys。 if you want to see。😊，How clear it is visually。

 just put it black and white。But does that look good， I mean， we're not going to well try to make it。

It to be something like this。啊，C。😊，Yeah I don't know， I don't know， let's try these colors。

So this color would be the background。Is that it。Yeah， that's。



![](img/ab18094230a798259ac1baa49f82bf9c_352.png)

This color over the background。

![](img/ab18094230a798259ac1baa49f82bf9c_354.png)

And let's see this color。I kind of like this color， it's kind of a nice this saturric。



![](img/ab18094230a798259ac1baa49f82bf9c_356.png)

![](img/ab18094230a798259ac1baa49f82bf9c_357.png)

爱奇。🎼Okay， I think I liked it。I think I liked it， what do you guys think I liked it？



![](img/ab18094230a798259ac1baa49f82bf9c_359.png)

Yeah， I liked it。Just for the sake of comparison。

![](img/ab18094230a798259ac1baa49f82bf9c_361.png)

Let's just go back to where it was before。

![](img/ab18094230a798259ac1baa49f82bf9c_363.png)

Yeah， this is like this is really uglyny， thank God， I change it Okay， I think for the success。

 I think this this could be the final call。

![](img/ab18094230a798259ac1baa49f82bf9c_365.png)

![](img/ab18094230a798259ac1baa49f82bf9c_366.png)

With this like。For this level。

![](img/ab18094230a798259ac1baa49f82bf9c_368.png)

I can try switching the colors， I think that may be enough。



![](img/ab18094230a798259ac1baa49f82bf9c_370.png)

![](img/ab18094230a798259ac1baa49f82bf9c_371.png)

Okay， I kind of liked。

![](img/ab18094230a798259ac1baa49f82bf9c_373.png)

🎼The orange， maybe it's a bit。To light。This guy's maybe too dark。



![](img/ab18094230a798259ac1baa49f82bf9c_375.png)

So， let me。You get like a good meal round。

![](img/ab18094230a798259ac1baa49f82bf9c_377.png)

Oh。So。We just take out these adjustments here。 So this guy。

I think I'm going to try a little bit dark， just a little bit darker。Like this。Well要。

It wasn't much of a change， was it？Yeah， but I think I'm going to stay with it。

 I don't want to lose this high saturation。

![](img/ab18094230a798259ac1baa49f82bf9c_379.png)

Mark。

![](img/ab18094230a798259ac1baa49f82bf9c_381.png)

Okay。😊，And now this guy， I think this guy is a bit too darned。We， tried that。



![](img/ab18094230a798259ac1baa49f82bf9c_383.png)

Yeah， yeah， this one， I think。Okay。

![](img/ab18094230a798259ac1baa49f82bf9c_385.png)

Okay。Think。

![](img/ab18094230a798259ac1baa49f82bf9c_387.png)

This is。🎼Yeah， I' like it。Maybe a little bit too strong on the eyes。



![](img/ab18094230a798259ac1baa49f82bf9c_389.png)

You know what I'm going to do going to change？I'm going to change the colors here。Yeah。

 we're going to make that more of a purple color。So let me just try to increase this product。



![](img/ab18094230a798259ac1baa49f82bf9c_391.png)

This is already the。It wasn't much look purple。

![](img/ab18094230a798259ac1baa49f82bf9c_393.png)

So let's。

![](img/ab18094230a798259ac1baa49f82bf9c_395.png)

![](img/ab18094230a798259ac1baa49f82bf9c_396.png)

Kind of preferred the other one。🎼More belowish heart。



![](img/ab18094230a798259ac1baa49f82bf9c_398.png)

Yeah， but it may be too saturated like everything too saturated。



![](img/ab18094230a798259ac1baa49f82bf9c_400.png)

but I like I kind of like this one。🎼看到来哦。

![](img/ab18094230a798259ac1baa49f82bf9c_402.png)

Maybe let me try， let me try。 Let's see。 try this color。牛皮。



![](img/ab18094230a798259ac1baa49f82bf9c_404.png)

Let me try this color here， well， situated more。Something like this here。



![](img/ab18094230a798259ac1baa49f82bf9c_406.png)

Okay。

![](img/ab18094230a798259ac1baa49f82bf9c_408.png)

This year。And a little bit darker， not that dark， but not that light。Yeah。



![](img/ab18094230a798259ac1baa49f82bf9c_410.png)

Something like this。

![](img/ab18094230a798259ac1baa49f82bf9c_412.png)

🎼Okay， kind of I yeah， I think I like it。

![](img/ab18094230a798259ac1baa49f82bf9c_414.png)

I can just see how it looks。The levels of stuff。Yeah， maybe I should add a little bit more contrast。

Yeah， maybe the sky should be a little bit darker。同时。Add me other curves。Adjustment。Yeah。Yeah。

 these are the colors I want。Okay。

![](img/ab18094230a798259ac1baa49f82bf9c_416.png)

These are the color， I think。

![](img/ab18094230a798259ac1baa49f82bf9c_418.png)

And this color。

![](img/ab18094230a798259ac1baa49f82bf9c_420.png)

Nice。And the other two are good。

![](img/ab18094230a798259ac1baa49f82bf9c_422.png)

The other three， the other three levels。What do you guys think？Yeah， it's not that hard on the ice。

🎼O。Nice， there's nice variation， this level looks great。🎼Yeah。



![](img/ab18094230a798259ac1baa49f82bf9c_424.png)

Okay。

![](img/ab18094230a798259ac1baa49f82bf9c_426.png)

See， it's not 100%， though。The transition I mean。

![](img/ab18094230a798259ac1baa49f82bf9c_428.png)

Yeah。I don't know it'd be hard to debu， but not。还会查。Okay。

 so we review the colors I think those cars will be final now。



![](img/ab18094230a798259ac1baa49f82bf9c_430.png)

Let me know if you guys think it's really ugly are really， I don't know。RMB。



![](img/ab18094230a798259ac1baa49f82bf9c_432.png)

But I'm not going to change the trailer。

![](img/ab18094230a798259ac1baa49f82bf9c_434.png)

Not that big of a problem。I think I'm change the screenshot though。

 try making the mountain movement the same despite the screen size。

I'm not sure how much of a problem is this。

![](img/ab18094230a798259ac1baa49f82bf9c_436.png)

🎼But the basic idea is now let me see if F1 targetss for swing who does。😊。

🎼And we're trying to make the sink mouses movementment to Gal。From one to the last。

 you guys will not be able to see this， but if I go full screen。

That mouth movement doesn't go all the way there。

![](img/ab18094230a798259ac1baa49f82bf9c_438.png)

But。I'm going to not do this and I'm going to make the configurable thing with that。Comfi。

Add the complete file。 So I'm not going to add。' going add this got15。O。

So let's add the compute file， it's not going to be that hard I。We have the。The slow player。

We have a speed multiplier speed。Multipli it。Mo to liner， and it's only being set。

 let's see in the beginning to 0。8。Well， no that' not it's not， it's not the same speed multily。

 this the speed multiplly。Let's see where it's being used。Here I set that to 0。1， if I'm slow。

And here I use it， is that it？I suppose that's it。So， it's really easy。Really。

 so what I'm going to do。Instead of setting that to 0。1。I'm going to multiply that by 0。1。不要。

Let's see slow speed multiplier， Yeah， things you know。And I add those happening。

 I'm going to have a full speed multiline here。スピ？Which call like mouse sensitivity。

 right So instead of like I'm going to keep that spin multiplier and we'm going to create a mouse。

Sensitive to。现是这个以。Very go。Okay。Not going to do the yeah， and let's say the player。Here。

I'm going to add that here and on the in。When I load， let's load。Load game， load safety。

 I'm also going to do the load conflict stuff。Yeah。So， I'm gonna set the。Mouse sensitivityly to one。

 let's see if this is working just before we program。Taxt file stuff。

And if I change that to point points should be really slow。



![](img/ab18094230a798259ac1baa49f82bf9c_440.png)

Oh， but this is sensitivity， right？

![](img/ab18094230a798259ac1baa49f82bf9c_442.png)

So if you make them more sensible。Yeah， this is correct。Or is it inverted？Sensitivity。

 low sensitivity， yeah。Yeah， this is correct。Okay， now let's， let's see we have in the OS。L 32。

We have a。Save game。Write save file and read Sa file。请 make。A read config file。And right here。

 I'm going to do the， can you teach me C so I can become a proficient hacker？嗯。

What do you want to hack？How are do today， hundred grade， how are you？So I'm going to load the con。

Now sensitivity and right here。And do the internal void。L config。AndThen I'm going to file。

OS read config files。And if we got a file。We should should parse that。I'm doing amazing。

 That's awesome man。Doing amazing is awesome do you have a goy setup for the game。

 let me show you the game the games and a lot stuff going on。



![](img/ab18094230a798259ac1baa49f82bf9c_444.png)

This is the game。You have more than you have like particle systems。Explosions and menus animation。

And we have like bit maps that have pe。Fes， you have audio。 We have motor thready。We have a profiler。

 we have so much stuff， man， and we added everything on stream。You can watch the whole thing。

Maybe able to learn see by just watching that， I also have a beginner C+ plus Sky on my YouTube channel。

YouTe dot com flash Danayd。So that should be awesome to get started。Mmji， this is amazing， thanks。

I'm glad you liked it and we have like spacing beers， break out。Then I title to their programming。

 dude， you should really learn programming， programming is awesome。You know。

 when I first started making games I wasn't a programmer，''t I didn't tell you guys that。

Because there's a little bit of sorry before I started in that game that I showed you guys over here。

And the story is， I worked。a lot of people's project online as a 3D artist。So I wasn't programme。

 I didn't know how to program it， I didn't really care much about that。

 I want to make games and I was like， okay， to make games。

 I need to learn how to program so I learned that kind of a。



![](img/ab18094230a798259ac1baa49f82bf9c_446.png)

Because I need it， but then I fell in love with it。You should really learn， man。

 there are a lot of like very beginner， C++ things on YouTube and stuff。

 I suggest that you watch a super beginner one and if you have like you know what a variable and a function is you can watch my tutorial series。



![](img/ab18094230a798259ac1baa49f82bf9c_448.png)

I'm doing my， like a。Game audio series is C++ for beginners， it's not like 10010 beginner。

 but's for pretty beginners。And you can watch that on。do you recommend Python or something else。

 I would recommend that you learn C first it's kind of a。Bit unusual， nowadays。

But C is the only language that really stood a test of time really， I mean， people improved it。

 people change it， people make better languages in different languages and slightly better languages。

 people try all sort sorts of different stuff and no one could beat C because it's really simple because it really gets the job done and it's really powerful and you want a simple thing because you are learning but you also want something that you should be able to really invest or timing in think about Python and these things they're really dependent on libraries and libraries are arbitrary you you're gonna learn how to use libraries and that's what I did for like three years I learn how to use libraries and it's suck because。

You learn learn how to program。But but when I stopped and learned how how to program in one year I could program like a lot of stuff then I program like web or a program I already did like a。

A web server in C。I already did all sorts of crazy stuff like I did web。

 I did enterprisese structure， I did RPA， I did all sorts of crazy stuff why because I focused on learning how to program and if I continue that path of learning how to use libraries。

 I wouldn't be able to do that so I wouldn't suggest a very library focused thing。

That's why thisor is pretty cool because it's from scratch， making a game from scratch and C++。Yeah。

 and watch like watch a very simple C tutorial on YouTube， like what's variable， what's function？

And things like that， and then you can watch to start if it's hard to follow along。

 let me know and now I can answer your questions。I do want to make a very beginner like I never programming in my life。

Tutial series， kind of a tutorial series。For absolute beginners， that's the word。

 for absolute beginners。But I think we're going to do that maybe in the end of the year。

When I finished this game and stuff。Because it's a lot of work。

 it's hard to make it right and I really want to make it right but then it'll be the whole process man。

 although the ways more advanced like we're doing now we do some pretty cool stuff。

 I mean not fully advanced but somewhat on advanced let's finish this sct file with thing。

OS reconfigug file。It's in your platform common。OS read config file。Oh yeah。

 we're about to spec the file， let's spec the file。I'm going to add that in the raw thing。

 I'm going to on something like config。The TxT for people to know that they can edit。

We're going to do something like mouse sensitivity。S sensitivity equals。1。0。

Does that look good to you， does that look like a nice interface for users？

I don't think I don't know if there's anything else you want to， well。

 we could do like a wow to true。That's really。我有。I really didn't expect。To do this kind of stuff。

onstream， but thatll be cool。T Imo parser。

![](img/ab18094230a798259ac1baa49f82bf9c_450.png)

Okay。Let's， let's make a confi。Fig。That's really unexpected，😊。

Let's do that not like unexpected stuff。Comefig see。So。呃。If we have a file， were do something like。

Get next。Keyword。Kword。Go get the next keyword。You that like the plasma pointer。And then。



![](img/ab18094230a798259ac1baa49f82bf9c_452.png)

it's going to be really hard coded because they're a very simple thing。



![](img/ab18094230a798259ac1baa49f82bf9c_454.png)

If the。The keyword still is strings match， we have strings match。

 I don't think we know we don't have any string function and I have to add a couple string functions。

A strings match。Keyword。And we're all at thead。A mouse。Sensivity。String。Equals。Mouse。下次接个镜。

And well let's do by hand one， two， three， four， five，6，7，8，9，10， 11， 12， 13，14， 15， 16，17。

17 characters， long nurse。And that's also the way we know it。We know need。

So you can probably read that before。🤢，Yeah know。I know we're going to do window。So one， two， three。

 four， five， six， seven， eight。8 categoriesers。 So we you find。The mouse sensitivity strain。

I'm going to do like a parse。Float valueacy。Value。Ours float value。白。And then I'm going to do。I see。

 value is。I'm going to set。The mouth sensitivity。To a clamp Beth。So the minimum is like 0。1。

And that stayed them while it's to 0。1。 Oh， it's going to be。换一说。And I say the maximum is 10。

And this is the value。给。😊，So we're going to need these。

 oh and the same thing will be for like strings match。Keyword。Wdowed。Sttrain。

And then we we're going to par a ball。Value par。Value。 and then we're going to set。The window。To the。

Okay， let's see if we managed do get in a reasonable amount of time。Stream keyword， get next keyword。

We need the depth next keyword。It's yeah， can call that screen。We need the。Cararse。Float value。

And the parse。Are we using。I don't think we are using any libraries for like print type and stuff。

So I think I'm going to have to write that by hand。

Just because I don't want to add a library just for this。It's going bes going to be fun to try out。

Fone parel。Okay， and of parse total value。That's what we want， this returns it full。

 this returns it float。And here in the string， we're going to have a internal void strings match。

Strering D， that's a string match， if。A dot size， B dot size。Tur to fls。This is actually a D32。Okay。

 so four let's， let's do the。At a。It a dot data。Saimply for B。



![](img/ab18094230a798259ac1baa49f82bf9c_456.png)

Hopefully people outsize not making a lot of noise for you guys。



![](img/ab18094230a798259ac1baa49f82bf9c_458.png)

There's a lot of unnoisy people outside here。Oh， let's see A dot size， A plus plus。Alle。

 please close I knee。So， if。At a at。As different。From add B。We want to return false。

If it's not different， we're just going to increment them both。And I'm going to return。shouldB没这个。

Now。We don't have a window。So I'm just going to do like。If。Value。啊OS。Toggle for screen。茶沟。

A last call。Oh， I need to pass the window。So I'm going to make the window variable global。Yeah。So。1。

91。5。Go back to like。H to a window。了得起。Here。Se me 32 window。Did this。

We're going to talk the full screen from not development。I can toggle that back I am。啊。

That's from common and I can talk that back。Tnal boy。Okay。So from inch。

 I suppose it's the other way around， it's data。Size。It is same thing here。啊，看见。够呛安全。

But a small parel here。Can I convert from Vo to string。 Yeah， get next keyword。 It's gonna。

So you the keyword， understanding the keyword， ending then advance the hundred。window。

Unclared because now it's 30。To know。Let's see， no， yes， no。Yes， yes， yes， yes， yes， no， yes。Window。

 this is。Again， I'm only 32 window。Dude， I， I can't imagine programming。 Oh。

 I can because I did that a lot。 but imagine a programming a。You some language is not strongly typed。

You really become afraid of the code， right？Result。So。We have to program these functions。

 these parsan functions。给。😊，So。The value equals。So。And。Value。So。し。Sbed， sn and bewined by default。

T result。Okay。Re。オ。あ。B 32 Okay， so let's， let's do the next get next keyword。

 What we are going to do。 first of all， we're going to eat white space， so eat。Wite spaces。And then。

 we're gonna。Like。Result get。

![](img/ab18094230a798259ac1baa49f82bf9c_460.png)

Next word。Well， we should we just do the get next word thing。はい。然后。嗯。😊，Yeah， that's really like this。

 I don't know。

![](img/ab18094230a798259ac1baa49f82bf9c_462.png)

かから。Maybe unnecessary abstraction， so to speak。

![](img/ab18094230a798259ac1baa49f82bf9c_464.png)

So you got that nice keyword。And。

![](img/ab18094230a798259ac1baa49f82bf9c_466.png)

You probably to do it like consume。

![](img/ab18094230a798259ac1baa49f82bf9c_468.png)

know next key word。What's your next word？

![](img/ab18094230a798259ac1baa49f82bf9c_470.png)

So we should be here and then that's it return results， okay？So。

We're going to have to do the internal string， consume。Next word。So the idea is。

I'm just going to old which probably do， it's going be easier。Internal。

Probably do the E white spaces。Ting and well。For i equals zero well。

It's not going to be the best parsel in the world。But it'll do the trick。

And people are talking to me。Let me not care about it for now。As data。あ。Let's plus okay， so if。At。

It's different。This。And。Or。Or Android and。Ats different。From this。And let's do a couple。

If it's different from。This technology not return。Return。Well， no， it's not true we have to consume。

Okay， so if it's difference we just returned if it's not different。We should set the data。Plus。

 plus instead the size， minuss mind。Perfect。😊，And。We don't need this app。And instead of at。

 we can just set the data， so add the。Illegal opera has typed Sha。If it's different。

Everything we ate out the white space， yeah， this looks okay。Okay next keyword。

Saying something is illegal。I don't know what。Let's try just adding this one。Okay。

 this is correct and。Sight。Oh， yeah， I listen。Which edited this I'm only using visual。

 this is forcodeder。For a quote is a great editor， you can。



![](img/ab18094230a798259ac1baa49f82bf9c_472.png)

Download the demo version for free on HIO。

![](img/ab18094230a798259ac1baa49f82bf9c_474.png)

Try for cold。Here you can download that， you can buy the full customizer version。

 you can do all sorts of crazy stuff for this， I haven't customize it yet。

 but you can download the demo， which is the one I'm using here。😊。



![](img/ab18094230a798259ac1baa49f82bf9c_476.png)

This is version。4。0。28。I really like this version。Because the other version that I really want to customize that。

 the thing I like the most， like the， it's really fast。

 it really reliable and it has like awesome virtual white spacing。😊。

So I don't really ever have to care virtual about white spacing。很凶。Next keyword。Consume next word。

 Okay， so we finish to eat white space， not sure it's working， though。

 but when we consume the next word。It's basically the same thing here。

But it's as soon as we find a white space， we exit。And Ire going to have to do a string。Results。

It equals S。Inter S。 and if we。Are equal to this。Or。Are equal to this so if you see any white space。

If we see any white space， we return。没啥。Okay。😊，And the result。It will start out here。

 but the size would be zero。And right here， I'm going to set。The result。Dot size， plus， plus。

And'm also going to remove the right to remove the， yeah， I think this is right。

Now return the string pointer。Okay， how do you use multiple files in C++ just multiple or different classes see this is not entirely correct you can use files however you want in C++ in fact you can you can create a class。

Class a。And a class B in the same C++ file， it really doesn't have anything to do with classes files the way it's already next。

 you can do whatever you want。 You can do the whole programming in one file in C++， you can。



![](img/ab18094230a798259ac1baa49f82bf9c_478.png)

啊。I'm going to draw really quickly， but if you want to learn more。

 I have a tutorial on how C++ compilation works， you can watch that on my YouTube channel。

Which is unity builds， C+ post completion explained。

What are you need to do you can go to the YouTube channel Dan they Dan on YouTube the idea is。



![](img/ab18094230a798259ac1baa49f82bf9c_480.png)

When we， when you compile file。So right now we are passing to the C， which is the compile command。



![](img/ab18094230a798259ac1baa49f82bf9c_482.png)

The W 32 platform。c。When you create a visual Studio project？



![](img/ab18094230a798259ac1baa49f82bf9c_484.png)

And you can watch that on this tutorial series， the C++4 beginners。Well in this case。

 you use C++ so you can watch and understand exactly how you can compile or not compile on this series。



![](img/ab18094230a798259ac1baa49f82bf9c_486.png)

When you create a new file here， it automatically gets added here， so like new file。



![](img/ab18094230a798259ac1baa49f82bf9c_488.png)

And the way it works is each file is compiled separately into an object file。



![](img/ab18094230a798259ac1baa49f82bf9c_490.png)

Whi is pretty much a compile， but there's a few missing things in this file and so you have a bunch of OBJ files。

 so this is the normal conilation。And then they are linked together into the executable。

What's inside an OBJ file， it's arbitrary in the way one one file。



![](img/ab18094230a798259ac1baa49f82bf9c_492.png)

Look into the other files through header files because they need the function prototype this is what we're doing here。

 you needs the function prototypes。But not the declaration because it can't be clear twice in the same。



![](img/ab18094230a798259ac1baa49f82bf9c_494.png)

ALiing face。But you need every compilation unit， which is separate。To see everyone's prototypes。

 so we need the H five for that。So this is the normal thing， you can do however everyone。

 you can have like two classes per five you can do however don't have a rule for that。

 it's not specified C++。So the way we're doing now and see。

 which is the same way I do in this tutorial so you can do that in C++ it's way better in fact Ham here also does that also does this。

Which is you need to build and you can watch that video for money info。

 but the idea is instead of doing。Several OBJ files。We， we include。

All our C or C++ files into one giant doc file and then send this guy to the compiler。

And then it gets linked to the schedule so if if you see here in our。



![](img/ab18094230a798259ac1baa49f82bf9c_496.png)

Tme here in our build。We are only asking it to compile with one file because in this file。

 we are including all the other files。And I think我给你造成可。对Yes。So this is way we were doing。

 this is uniquebu， it's way better， it's way easier because you don't need like tons of header files so we spend like a lot of time stping sync thing。

 every time sucks， really sucks。

![](img/ab18094230a798259ac1baa49f82bf9c_498.png)

![](img/ab18094230a798259ac1baa49f82bf9c_499.png)

Right now was just the CC， I think it， I don't know if you saw the beginning of the complete file we did was like。

Begin a file， configurefi。Added here， added here to the game6。

And then this like this is the same thing as if we were writing this thing in this file so it's like we're doing like one huge file。

 but we just break for convenience so this is convenient to be separate because I have like parsing stuff here and I don't want to clear the game with that。

So yeah。So arbitrary arbitrary is the way that I files the way I think it easier。

 so I think this is correct when I have to debug that。And the parts float value。



![](img/ab18094230a798259ac1baa49f82bf9c_501.png)

I'm going to have to， I'm going to parse。啊。And I'm going to barse one keyword。



![](img/ab18094230a798259ac1baa49f82bf9c_503.png)

You know what？あ。I'm going to remove this keyword thing。It's going to be the same thing。

 so I'm going to eat white spaces。And gonna then。E by space here and here。



![](img/ab18094230a798259ac1baa49f82bf9c_505.png)

And Ill leave for this guy。So this is the basic idea。

 so the parse float for now all I'm going to do is read two。



![](img/ab18094230a798259ac1baa49f82bf9c_507.png)

Words， so。それから。し？Next keyword。S。Two words。Okay。Strange， not id S。Same thing。Let's see mask。

 It's all just work。Assume， next word。

![](img/ab18094230a798259ac1baa49f82bf9c_509.png)

ok。Now。Do you guys think？Then we're going to get that working for the first time or not， so file， oh。

 I should probably turn off。

![](img/ab18094230a798259ac1baa49f82bf9c_511.png)

The optimizations。

![](img/ab18094230a798259ac1baa49f82bf9c_513.png)

So we can debug car。That's our file， looks correct。WeHave our strengths。So consume next， oh。

 I don't know if you guys can see that， let me increase the font size a little bit。

So I consume next keywords， I'm going to eat the white spaces。I see。Let's see the data here。Well。

 this is wrong， I suppose。Why is the data one， this is a text file。



![](img/ab18094230a798259ac1baa49f82bf9c_515.png)

It's funny in red。We at 44 K。Which looks about right。Oh， no， this is wrong。

We're probably reading the wrong file。

![](img/ab18094230a798259ac1baa49f82bf9c_517.png)

We are probably。Yeah， we read the save file。完せ？对吧。

![](img/ab18094230a798259ac1baa49f82bf9c_519.png)

Okay。Okay， now we don't read a file。

![](img/ab18094230a798259ac1baa49f82bf9c_521.png)

Config dot TXT。We misheld it。

![](img/ab18094230a798259ac1baa49f82bf9c_523.png)

Let's go。 Let's see。So we didn't get that in the first try。Equified spaces， so S。

 this our file perfect mouse sensitivityivity one， we know the false。Let's see。

 we don't have white space， so we exit right off the bat。And then you copy the results。

 so now we're going to the next word， right？Okay， so。So we increase the size here and the result。

 let's say the result。This guy and Alex it one， this is going to work great， I think。1，2。Yeah。

 I'm going to add a breakpoint here or here， let's see which ones come first。

 so we find a wide space。This would be called profound the end of the file。

 so we don't need to eat the white spaces， but who cares？I'm not going to find the end of the file。

Okay， so。Now we're going to eat the white spaces。Perfect。😊，And have 17 miles sensitivityens。

 so we should be able to match strings and we do， so that's working。We're not par the floatat yet。

 so we should。We should just。Get one here， which we do。So what master do do still want？Well。

I don't know if we， if we are。Okay， we should loop through that。



![](img/ab18094230a798259ac1baa49f82bf9c_525.png)

嗯 so。Small problem。We've just read of one keyword。So I'm going to have to do like while。

Why do we have a file size？

![](img/ab18094230a798259ac1baa49f82bf9c_527.png)

行。

![](img/ab18094230a798259ac1baa49f82bf9c_529.png)

Let's see I'm going to remove all those breakpoints。So so we read one word， we read the other word。

But we don't have a match。Okay， this is wrong。啊，那行。We read a key word。Small sensitivity。

 then we parse everything。And the file is。That's nice we note， okay。So。



![](img/ab18094230a798259ac1baa49f82bf9c_531.png)

WeConse the next keyword。Keywords， oh is backlash。 So before the consume next keyword。っぱ你。Oh。

 we didn't change that back slash R， backslash and and backslash T that those were the ones I meant to add。

What are your thoughts on allocating more memory than you know you will need。

 let's say you you won't need 30 or allocate 40 and then delete the unused addresses。

Not idea for memory intensive stuff， but for simple things。嗯。Sorry you'll need 3。 Yeah。

 I got what you mean in L 40。When you are developing the project。

You should really allocate a lot more than you need。

But we should be able to track that in this game since were not allocating memory at all。

 except when we read a file， which like。Three times in the entire game and we don't even free it we don't really care it's like a a 40 megabyte 40 kilobyte file and a four megabyte file the biggest one is four megabytes those are the only ones that we allocate。

So we don't care about that in this game in a bigger project probably youll need an allocator so we probably have a memory arena that have a huge amount of memory like say you have 500 megabytes for the development and then you keep track out the memory so you'll know on each level uses how much memory you use and things like that and parsing a stream stream and allocating the memory just by loop into。

Yeah， in this case。If don' if you know how much memory you need。Like you need 30 so to get 40。Uh。

 if you know， like if you're reading a file， like in this case here。

We know how much maybe because we get the file size here。

So we know how much we need to we just allocate that file science。And oh。

 we are actually allocating in other cases that weocating in the audio and the pixels。

 so we do allocate a lot of memory。But in all cases， we know exactly how much we need。In this case。

 we allocate the number of samples we need， which is like one two seconds worth at。

And the pixel is the size of the screen so when its size changes we free the memory and we are looking that so this is correct I forgot about that but we did the file thing the first day day one。



![](img/ab18094230a798259ac1baa49f82bf9c_533.png)

![](img/ab18094230a798259ac1baa49f82bf9c_534.png)

The video thing they want。呃。But if you don't know how much memory you have。

 you usually allocate a big block and then you have an allocator for that。

 like a stack allocator or things like that。Did you make that class with no。

 everything's made from scratch， man。You couldn watch the whole thing on YouTube。

 everything was made on live stream， everything could watch the whole thing。

 and right now we're writing the parsel for the config file and that wasn't planned since we were doing like small things。

He was like oh it' would be nice to add a config file so we were parsing that and it's pretty easy not we're not allocating any memory at all except for reading a file got I C the first time in four years and having up and I've forgotten so much Yeah。

 C++ does changes a lot。See that does change， I suppose， to the correct place saying。

 but we're not allocating anything here in the parer。

 We have the memory and we're just pointing at the things that we want like wecr pointers and track。

Things like that。So yeah， we found the bug。

![](img/ab18094230a798259ac1baa49f82bf9c_536.png)

On the on the on the year。sizing yeah， so this correct now our keyword is windowed。

 so wewined the files would be。It be two， so we read a keyword， which is like。Yeah。

 it's kind of weird to consume next keyword。

![](img/ab18094230a798259ac1baa49f82bf9c_538.png)

It's not 100%。

![](img/ab18094230a798259ac1baa49f82bf9c_540.png)

Let's see， I'm not sure。 we got。We don't and then。We parsed file and the end was S over false。

That's funny， I thought we consumed two words here。So。The value is equal false。

 so now the value should be false， it is false， and we consume the next keyword， let's see。

 sorry8 white spaces no difference。So， we go ahead。What we find。What did we find to read？Oh。

 because we are decrementing the size here。

![](img/ab18094230a798259ac1baa49f82bf9c_542.png)

Okay。This is wrong since we are decrementing the size， we need to increment I。So yeah。



![](img/ab18094230a798259ac1baa49f82bf9c_544.png)

So， yeah。This is a really bad parser， it's not really organized。

But since we're just doing this for crazy fun。😊，And。

And it's not meant to be like production ready question stuff just for the configs， who cares if。

It's not working or something like that。Well。The windowowed now， the key word。

 the file should be equals 0 perfect。 So now it's working。 All you have to do is to read。

Bows and floats， boths will be easy。Boos， not bulls。So we have a string。Let's say true。

 because that's the one that we hear if it's windowled or not。抽水。It's going to be equal to。Te。

And let's see one， two， three， four， four。Character belong。If strings match。嗯。It's the value。

And the true string matches。Then we return true as we return false。So now if everything is working。

 we should。Launch。Well， we should。20。It should be weowed because we are in the development build。

 right？But if I say it to true， I'm going to toggle。So it should be full screen。And it's not。So。

Something's wrong。Let's see what's wrong。True true is true。 Our vow is false， what？Did I not say it？

Why is the jelly false？This is weird。Oh， because I have two config files。对。O。Because I named it。

When it was opened， okay， let's see if it's oh， it's full screen。😊。



![](img/ab18094230a798259ac1baa49f82bf9c_546.png)

Awesome， all that was really weird Oh because we are。



![](img/ab18094230a798259ac1baa49f82bf9c_548.png)

Since we are not the debug build， we're running really slowly。



![](img/ab18094230a798259ac1baa49f82bf9c_550.png)

So it's going all over the craze， hell the cr， so let me go to an optimized non developer build and let's go back to the game and let's remove the I。

😊。

![](img/ab18094230a798259ac1baa49f82bf9c_552.png)

That。So now it should be widowed。And now it should be。Fll screen。Asome。

We implemented afiIg file and a parser。That was awesome in like 40 minutes。

 what does the internal keyword do， the internal is just static。😊。



![](img/ab18094230a798259ac1baa49f82bf9c_554.png)

Let me show you guys here。Since a。Since everything is one。Compilation unit or translation unit。

We don't need to export everything outside trans， so adding a static keyword is a great optimization。

 meaning that it's internal for this completion file。So yeah， the compiler。

 the compiler can optimize that in terms of like generating the OBJ and linking。

 although I don't remember what happens it was something like，Two or three streams ago。

 something happened that we got really slow in the compiler time。本来哎呀。But yeah。

 this keyword just for for cleanup。 So that was awesome， man， adding these。😊。

It's going to big file that we have to parse the float though。Oh thank you， I thought I was like。

 well， this is a column practice to rename statictic。Well。I didn't invent that。

 so I learned that from aCasey Muari。Sos not it's not that uncommon because static means three different things to you to really add。

Like local。Persist。When you' are inside a function of a static means that this variable persists locally。

 if you add that in a global scope static means that it'll be a global variable。

 and if you add that to a function means that it's internal to the completion。

 so it means three different things。Yeah， so white Wn is right because static means a lot of different stuff。

 it's a nice practice to rename it。know exactly what you mean by static and it's also great to search right if I search for like global variable。

 I know how many I have my program because if I search for static and every function is static I'd have like tons of static and I wouldn't know if that's a global variable or a functions so I go have to go line by line so。

😊，Yeah， dude。 It was so awesome to implementfi file。 I don't know。 I don't know if， let me see。😊。

If V Zamarel is still here。Because he suggested， I don't know if you've got to see。

The implementation， but that was really cool。 Like I even 100 lines。

 Let's implement the the parts flow really easily here。 So this。😊，the float strain。Okay。

 so I'm going to go character by character and I have like32 result equals 0。

So I'm gonna go character my character in this guy。 I less than floats train that size。Okay， i plus。

嗯哼ん。😊，Okay， so。啊啊。If floatstream dot data， well， yeah。I， I'm going to do it like this。

 not the best thing， but it's going to be so quick that nobody nobody is going to care that's a super small five to pars it's not like a full production parc it's just。

Small concrete thing first fun it would be nice and we're going to have to test for errors to like what if the file is missing。

 everything should be working but what if we miss type and things like that。So。Well。

 I'm going to add like ours。I个 add来。So float data。一是。😊，嗯。If this guy。Is greater 2 or equal to 0。

And this guy。Spiritual are equal。To9。This is in digit， right？So we can do like。Digit。This guy。

Minus 0。Okay， so that's the digit。And then I'm going to do like value plus equals。Oh times equals 10。

And then value。不是在讲。Okay， so we should be able to parse ins for now。

And we're going to make sure that this works。あも。Okay， and I'm going to add this else here。

I return one just because it unknown because we're going have to add the dot here。

 let's see if we get the brief cars corner。Well， one is too boring， I still like one to three。



![](img/ab18094230a798259ac1baa49f82bf9c_556.png)

![](img/ab18094230a798259ac1baa49f82bf9c_557.png)

东西。Let's。Let's go back to building the unoptimized。



![](img/ab18094230a798259ac1baa49f82bf9c_559.png)

Development。O。Now the float string is one to three。Perfect。Now we should be able to get one。

 so value is going to be。1。Next time I'm going to get two， so the that is going to be 12。

And next time I'm going to get three in the value is going to be one，2， three。 That's it。

 man we par par the integer oh， we didn't change that。



![](img/ab18094230a798259ac1baa49f82bf9c_561.png)

Yeah， I'm going to set a result here。So one to three perfect。不105。不不是。Result， result。



![](img/ab18094230a798259ac1baa49f82bf9c_563.png)

Perfect。😊，Let's see what else？

![](img/ab18094230a798259ac1baa49f82bf9c_565.png)

Okay， now we should add the dot。Let's see， one， two， dot3，2。Let's try parsing that。Well。

 we should also try before I do that， do leading zeros。Because this。



![](img/ab18094230a798259ac1baa49f82bf9c_567.png)

Not sure this is going to work。We find zero， so we add0。Next one to final answer we yet one。So yeah。

 I've got 12， 8 zeros， we got that for free。Okay。Now we're going to have to do， let's try 1。

2 for now。

![](img/ab18094230a798259ac1baa49f82bf9c_569.png)

And the thing is if we find a one point， I mean。This guy is a dot。

 but should also add a comma because in places like Brazil。People specify decimal。With。卡吗？

And our point。And we don't really care either way。So if that's the case。If we found a pointer。

Instead of。Yeah， I'm gonna add something like。Yesmal equals。是咯。O。😊，And if decimal equals 0。

Okay'm I have this else。好啊。If I don't have a decimal， this is how I'll process the number。

 if I do have a decimal。If I do have a decimal， I'm going to。It's going to be result。Plus。

Equals F to digit。Divided。买 decimal。That's it， I suppose。Returned。



![](img/ab18094230a798259ac1baa49f82bf9c_571.png)

Yeah。Yeah， I think， well， I'm not sure that he's going to worry， but who knows did。

 we found we find one， so we add that， that's one。We find points so dec'sal now one， find two。

 and we've got one that's mostly we're going to add two divided by one。



![](img/ab18094230a798259ac1baa49f82bf9c_573.png)

Oh， this is wrong。This is wrong。 It's not2 divided by one。 This is not。 this is divided by。啊。Well。请。

T0 to the power of the decimal， so instead of saving the decimal， well I can save the decimal。

 all right。So I'm going to actually do this guy。It goess 10。And then， when to do。Dimmal。Time equal。



![](img/ab18094230a798259ac1baa49f82bf9c_575.png)

Okay。Okay， let's see。The result。Perfect， 1。2， the 00，005 here you got the full precision。

So we read Wal printer successfully。And now we should be more assert， let's see if this works。



![](img/ab18094230a798259ac1baa49f82bf9c_577.png)

Oh manan， we got really lucky。

![](img/ab18094230a798259ac1baa49f82bf9c_579.png)

With things working nicely today。开始。😊，I's that 10。 well， that's at 5。2。



![](img/ab18094230a798259ac1baa49f82bf9c_581.png)

We should be really sensitive， and we are。

![](img/ab18094230a798259ac1baa49f82bf9c_583.png)

Let's add 0。2 and not sure if 0。2 is going to work， so just for the let's see。Oh。

 we couldn repeat that。

![](img/ab18094230a798259ac1baa49f82bf9c_585.png)

Let's spread that。Print F2 results。

![](img/ab18094230a798259ac1baa49f82bf9c_587.png)

Yeah let's see if you par that correctly。Perfect。

![](img/ab18094230a798259ac1baa49f82bf9c_589.png)

So that's it。0。23。2。12， we only print to a decimal。Let's do 62。Perfect， that' st。This number。Oh。

 I don't think we have。No， I don't know it。wo points okay。From01， so this one。

 I don't think we managed to get working。But I think we care honestly。

If we do something like this or maybe we did work， yeah，2 to11 because of float precision。呃。



![](img/ab18094230a798259ac1baa49f82bf9c_591.png)

Yeah， I's see 0。2 that's 0。2 Yeah， we are working see。

 but we're not precise in our printing is not perfect either way， so I don't know dude。



![](img/ab18094230a798259ac1baa49f82bf9c_593.png)

I really want to make a programming language， I already did like small scripting thing just for fun comp to see because it's really awesome man to do a parsing things。

 awesome， it was really easy。So now we make a complete file with options for。不。And float。

In 90 lines of code。 and in another， I'd say one hour， let's say we did like that in one hour。

 That was super， super easy， man。 That was so easy。And that was really awesome as well。

It would be as a value to have like a parer thing。So instead of going Fig。tc。

 I'm going to rename this file。Just make it clear， like onfi file parser。Yes。

 so people can see what's going to expect from this complete file。Per ending the game。

It's going to be con。Awesome。😊，Now let's just see what happens if we don't find a config file。

 let's see if we explode。We should be good to go， to be honest。



![](img/ab18094230a798259ac1baa49f82bf9c_595.png)

じ。

![](img/ab18094230a798259ac1baa49f82bf9c_597.png)

Yeah， everything's too perfect。Let's see if we find a config file with problematic information。

Everything is so perfect。And let's make full screen。 This will toggle the window。

 so let make full screen。 Yeah， so we couldn't read this guy， but we read this guys。

 as a teeth fatigue。

![](img/ab18094230a798259ac1baa49f82bf9c_599.png)

Let's add like。V' information here。Oh， let me go back to not because。ice to see so if you read like。



![](img/ab18094230a798259ac1baa49f82bf9c_601.png)

Bad numbers。呃。

![](img/ab18094230a798259ac1baa49f82bf9c_603.png)

It still works perfectly same thing here。're going to be a window。



![](img/ab18094230a798259ac1baa49f82bf9c_605.png)

If we read something like this， we have to read true。Do you have full screen perfect。

Let's see if we have like extra things here and here。And here。Perfect。😊，It is bird， let's try it。



![](img/ab18094230a798259ac1baa49f82bf9c_607.png)

Straight10。Perfect， super fast。

![](img/ab18094230a798259ac1baa49f82bf9c_609.png)

People are trying， people going to break this。For sure， but that's fun and true。Yeah。😊，Oh man。

 that was so cool things long， but that's deskroom man， it was really fun to program this。



![](img/ab18094230a798259ac1baa49f82bf9c_611.png)

Thanks a lot。 Really。 That was really， really cool。 Look F5 was done， done， done， done。 Let's add。

 let's add more so today。s kind of getting tired。😊，But I think we can do so much。

Probably when the comet hits strong blocks， he's the game over。Let's see。Well， let's first of all。

 remove that print。65。And then let's go to the level and then the block block。

 and then it let's make every block。It's like every block。How hard to remember， yeah， power block。

power b。Alright down。Per。Slow player。 Yeah， it's actually strong blocks。Let's see what happens。

The bug said。Problem when comet hits strong blocks， so this kind of sucks。

I kind of need to make comments from blocks。

![](img/ab18094230a798259ac1baa49f82bf9c_613.png)

Okay， let's see。Okay， so we've got a comet and that's strong blocks， let's see comet works nicely。

 strong blocks。I don't know， man。Instant game over。啊。Got it do some game over。

But that was only when the comment was going up。So let's， yeah。



![](img/ab18094230a798259ac1baa49f82bf9c_615.png)

That's weird。

![](img/ab18094230a798259ac1baa49f82bf9c_617.png)

Lose life， Let's go to lose life。Yes。Why do we lose a life， Who thinks us life。Update balls。So。

 if the。Bish。All desired PY minus 36。Ball have size，3，23。So we've got a， yeah。

 so we've got a huge ball。That's why I would think。Got the end of the。 The question is， why。

You've got a huge call。

![](img/ab18094230a798259ac1baa49f82bf9c_619.png)

啊。包。Have size。So we have increased ball size。Sponshipshop， Du ball block collision。 Yeah。

 so this is the thing。This is the problem。Where we do。AB block collision。

 Is see when I research with strong blocks。Well， don't search it here。When we hit a block。🤢。

Where is this， this is the update box。When we hit a block。And we're not from boards。

 well lose a life。This is weird。Where does it say？Where are we using the strong blocks？Strong blocks。

 D T。Okay， yes， so this。So when we hit a block here。We already did the do block collision test。

 if we not， yeah。So if we hit the block， yeah， I'm going to have to change the do block collision test。

Asion test。Now I can't find it。Whats he called。It it's not tests， it's just blood collision。

Let's see I increase the size， I don't increase the size。I'm really confused。



![](img/ab18094230a798259ac1baa49f82bf9c_621.png)

Let's see who increases the size。Crease ball signs。爱次。Okay， increase the ball size。



![](img/ab18094230a798259ac1baa49f82bf9c_623.png)

Its going be hard to play。Yes it's going to be kind of impossible to play。We search for that。So。

We increase the ball size player collision with ball。W with wall wall wall。Here。So just the problem。

You just see where。So this is the problem。啊。If I hit the block。

I'm not going to increase the ball size only。Well， I need the old signs。So。Update ball axis。 Yeah。

 let me see it just by not increasing the ball size this word。

 I don't think this will going to work because I think the collision is still happening。



![](img/ab18094230a798259ac1baa49f82bf9c_625.png)

I think it's right on top of thet。Okay， so now we're infinite looking for some reason。

He the block well。All we do is not increase the ball size。啊 we leave lift咗边啊。



![](img/ab18094230a798259ac1baa49f82bf9c_627.png)

Well， because we have movement left， okay？It's weird just by doing this。Oh， I suppose we were， yeah。

 if we didn't。If you didn't lose the game， we wouldnt even loop。不。Yeah。免积第三个。

The ball is already inside the block。嗯。We're trying to do a sweet bath。Yeah， this is only invalid。

 I don't know。 I may cheat here。Instead that the ball movement left。It know if strong blockss。

 I'm going to cheat that for now。G than0。

![](img/ab18094230a798259ac1baa49f82bf9c_629.png)

Just to see the result and a the bit better the system。给你。😊，Yeah to have。



![](img/ab18094230a798259ac1baa49f82bf9c_631.png)

ok。Okay， so。We have to change the ball direction， why is the ball direction not changing？Here。

Fll a date。Aes。It's one or zero valid code path off topic Did you try rust Lang。

 I'm using it for a while in the series， but bearing。

The fur loop play still't see much gaming for using。For games。Its speed off the distinguish to see。

 but the bug is really low emotion， yeah。I haven't tried rust。

 so take my opinion with a grain of salt。But I'm not。Very interested in rust。For the reason that。

A compiler that tries to outsmart the programmer。It's not very useful， in my opinion。

I want compiler to be a helpful tool， so don't take me wrong in this case。But it should be a tool。

 it shouldn't tell you that this code is wrong and it shouldn't compile it。

 even if this code makes sense。Right， so that's my problem with rust。

 I don't like a compiler that rejects code just because it doesn't follow his standard of。

Correctness。That's my problem so that's why I don't go into Ru very much。

A lot of people have a lot of problems with that， but I don't， I don't have a lot of problems。

By having a compiler， by having a， I don't know， wrong call in this sense。

 so maybe it's not's not for me， I suppose。But it's probably going to be a lot slower comp rust。

Not sure a lot lower than C+ load because C++ is already lower。

But since it's going to do a lot of compile time check on our code， it is going to be slower。

 And I don't know。 I really like fast builds。 I think this good slow enough。

Takes like almost a second。Yeah， I don't know， why is the ball of date axis here if the ball's going to be the sweep。

Caathly。It's1 is0， so what I'm going to do is I'm going to change the ball update date axis。因为。

Set that to the opposite of that。In case。We are here。So we should go I'm going to add this anyways。

 but we should go now to the opposite direction。

![](img/ab18094230a798259ac1baa49f82bf9c_633.png)

So that was the problem。What？😮，He didn't change directions。



![](img/ab18094230a798259ac1baa49f82bf9c_635.png)

Why didn't it change directions？The strongng blocks is less。 Yeah， also should be read。



![](img/ab18094230a798259ac1baa49f82bf9c_637.png)

Nice。

![](img/ab18094230a798259ac1baa49f82bf9c_639.png)

Come on， man。We should really change direction only if we are a comet because comment。

 for some reason， let's see。I'm going to put a break point。



![](img/ab18094230a798259ac1baa49f82bf9c_641.png)

行了。I'm going to put a break point lets see here。Let's see here。



![](img/ab18094230a798259ac1baa49f82bf9c_643.png)

![](img/ab18094230a798259ac1baa49f82bf9c_644.png)

还行。So， if we hit the。If you hit the block with a strong block， let's see。Well。

 that's not what I want， I want the strong block first。ok。So the update axis is one。So， if we。

Don't have a comment to reverse。But if we have a strong block， ah， this is perfect。😊。



![](img/ab18094230a798259ac1baa49f82bf9c_646.png)

Like。😊，Has。Strong。对吧。好死。But if we have a strong lock。You know what you can go back。downown here。

Because the problem wasn't this。Problem was this。

![](img/ab18094230a798259ac1baa49f82bf9c_648.png)

I'm confident that this will solve the problem。Let see， well， let me try some random things。

 so random comment looks good， comment。

![](img/ab18094230a798259ac1baa49f82bf9c_650.png)

This strong block。Yeah， the sound is crashing， we have to take a look at that。Probably today。



![](img/ab18094230a798259ac1baa49f82bf9c_652.png)

But。I'm going to change the way sound is processed a bit see strong block looks good。Oh。

 but now we can't。Now we can't get comment we have to get a strong blocks and then a comment immediately let' see。

怎。Yeah， see， this is perfect， this is what we want。Asome。

Let's see if we still have the correct comment behavior。We don't。 We do。

Let's see if you have this correct strong white behavior without the comment。

And I think we do as well。Yeah。

![](img/ab18094230a798259ac1baa49f82bf9c_654.png)

Nice， so we solved this bug。Solve this bug。Let's do the audio thing。

Because it would be good because I'll be able to。To test that before last stream next range， yeah。

 I can see that point I'm just trying now because of the hype。For now。

 the compiler times are actually good。 It's like a slow， slower than C。

 but I think it's it's because museum millions and P is no the dependencies。

 a compiler rose program that takes 15 minutes to compile with。

I compile a row program that takes 50 minutes to compile with 200 dependencies。

Do hundred0 lines of gold， by the way。Really。Oh， man。 that's territory。 I really don't want to。

Thread， so to speak。Because。I mean， but I don't know 200 painting sounds like a lot， right。

 an open source too okay。Okay， okay， yeah。Yeah， no。

 because when you start talking about like really long compile times， man， I programmed like a game。

Using the unreal S++ stuff。And。It takes a long time to compile even with incremental builds。

 even with like DLL optimizations and stuff。I don't know， I hate programming like this。

And I hate programming if I hate programming， right。

 so if I don't want to hate programming because I love programming。And I don't know， man。

Speaking of friction， that's a huge friction， so I don't know if that's a problem with rust or the problem with the weight structure because I mean unrealre takes a lot longer than that compile。

So I'm taking not bashing Ru for that and bashing long compile times。But。Yeah。

 thing is that the thing about Ru for me is the compiler rejecting code that I want to write if I want to write that code。

 if I make a mistake。In terms of like the parsing and the waxing and the cementmaning stuff okay yeah sure。

 but don't don't add arbitrary stuff like program is hard enough without limiting the programmer and that's why I don't like higher level languages as well program is hard without limiting the programmer that's kind of a。

A nice statement。So you should limit the programmer so let him do this thing so we finished this bug。

I the place spring tighter。Make the fail and wean more evident。

I think we're going to do these next time。 Oh， our searchs on the release field。

 I think we're gonna to do this just before we do the。Do you add？And。

Just before we do the audio thing， I'm going to do the asserts。

Because I think the asserts are under release field and that sucks。 So I'm going to assert zero。



![](img/ab18094230a798259ac1baa49f82bf9c_656.png)

And we are on the development， so we should assert。You should， yeah， we do a。



![](img/ab18094230a798259ac1baa49f82bf9c_658.png)

Nice。But if we go to the not11， we shouldn't assert。 but the problem is。



![](img/ab18094230a798259ac1baa49f82bf9c_660.png)

![](img/ab18094230a798259ac1baa49f82bf9c_661.png)

Yeah， see we do a search。And the problem is。

![](img/ab18094230a798259ac1baa49f82bf9c_663.png)

Somewhere we use like two libraries， one for P&G and one for OGG files。

One of them or two of them both include assert。h。And a dot age， for some reason。Well。

 they include a3 age despite this distinction。And I want to mess around with this。

 all I want is I want to have control over a search myself。

So what I really want to do is something like this。If development。Include assert dot age。

Right and if you're not， I want to assert nothing， but this is still going to be problematic。



![](img/ab18094230a798259ac1baa49f82bf9c_665.png)

Because they include a certain age unit for our development， so let's see that age。



![](img/ab18094230a798259ac1baa49f82bf9c_667.png)

This file is Iro， so doesn't include anything。Image， yeah， assert。You can define。Yeah。

 see you can define a SDB assert。Before C age。So， assert。So it's exactly what we want。

So we define as the insert that's。ラジに店ムい。So we defineance the assert to be assert。

That's in as the image， let's see， where is that image order？Here。Define STDI。Asert。To be a suit。

Perfect。But I think the OGG reader doesn't do this。F out state see， it doesn't。

So I'm just going to remove that。

![](img/ab18094230a798259ac1baa49f82bf9c_669.png)

Hey， what is a function pointer and what it these use for it do better a random question。

 a function function pointer just a variable that points to a memory address of a function。



![](img/ab18094230a798259ac1baa49f82bf9c_671.png)

If you want to know more about pointers。We're going to link to my pointer video。

 which is pretty useful。Because if you know what a pointer is， a function pointer is kind of obvious。



![](img/ab18094230a798259ac1baa49f82bf9c_673.png)

ok。So that's the video， so watch that video and after that。

I understand this and you can watch this later on in the pod。

A function exists memory right so you can hold a point to that so and if you do hold a pointer what can you be useful for well the most useful thing is by creating virtual functions like C++ right you have a virtual table that links like call this function which function I don't know it depends it depends on what so you can set that function pointer to point a different function based on what criteria you want like I have an update monster thing and I call the update function for the monster which is a function pointer variable inside the monster right。



![](img/ab18094230a798259ac1baa49f82bf9c_675.png)

If the monster is work， I call this function， so I set the function pointer to point at a different function。

 right so this is the basic use for function pointers。It's also useful for loading DLLs。

 I'm not using this in this case， but if you have to open a DLL。

 you can get the function address by doing the get track address function in the windows。

 so get the function pointer to the DLL and then you can just call it the function with a function pointer。



![](img/ab18094230a798259ac1baa49f82bf9c_677.png)

That's another very common use as well， and the last common use is to build like an API。

And past that through DLL barriers himself。And that's also useful。



![](img/ab18094230a798259ac1baa49f82bf9c_679.png)

Okay， so I think shouldn be we shouldn't crash now。And we don't。



![](img/ab18094230a798259ac1baa49f82bf9c_681.png)

Perfect。So that was the problem， our libraries use see。😊，This library， the other ones。

 you could this is perfect， but this library， for some reason even though it was Sean Bart wrote both of them。

 for some reason， this library doesn't have this nice interface。So it just uses a search directly。

 see。But that was easy enough to change and if you have like 200 no problem， man。

 if you have 200 dependencies。ButLike White Wolfin commented。

And you have to worry about 200 possibilities of people including things that you don't want to include on your code。

 right？That's why you should really consciously use libraries and stuff。

So that was it now if I remove。Now let's go back to the bill。 that。Go back to the development build。



![](img/ab18094230a798259ac1baa49f82bf9c_683.png)

I can do optimize here for now。Is see， yeah， now I assert。



![](img/ab18094230a798259ac1baa49f82bf9c_685.png)

But now I should be able to。Remove the insert。诶 see。哦，请这边你。



![](img/ab18094230a798259ac1baa49f82bf9c_687.png)

Yeah。So now should be back to normal and asserts will not trigger when the player is running the game because they shouldn't。



![](img/ab18094230a798259ac1baa49f82bf9c_689.png)

Nice。Sound crash， yeah， so I think I'm gonna the last thing for today。

I am going to work on the Gu mouse，Reappear，3。Up here。We up here。Yeah， think。

So I'm going to take a small look at the audio thing。Okay。

 and I'm probably going to do like one more。One more polish stream and then you can finish the game。

订标到比。We can do like display test more。Especially。T。Where are you from and'm from Brazil？Okay。

So the sound crashed。We， we could have deoteed at that point， to be honest。

 because it's a very rare crash。So it kind of sucks。

 but I got this screenshot and you crashed online this。This is third trigger。So。

It's not going to be that much of a problem because we're not going to assert this， right？

On the development but we should have a sound。Because if you do give。Oh， you know what。

 I know if we true。Honestly， I don't know if you forgot about sal because we early out。

Was it really dislike 106 yeah？So I'm not sure this should be asserting。But anyways。

 I want to change。The weight structured。Because the thing you are very。They are very cruel in Brazil。

 especially cartels and prisons。Dude， what do you mean？

There's crime everywhere in the world it's not different here。呃。So the thing we're doing。

 we're iterating for every sample， we're going through every sound。And that's not very cash friendly。

And so we want to do the other way。 We want to do like for every sound。

 we want to go through every sample because they are sequenced。

 right and finish the same thing of doing the iterations to the。

Same thing for looping over the buffer Y first and thenX。Because this is tightly packed。

 so we want to iterate that inside the other one just as this is tightly packed。

 so we want to iterate inside this tightly packed the samples。

 so we want to iterate this inside here and not the sounds。Very。

 very cruel I don't know if you had some experience man with that， but。😊，Yeah， they are。

 just like any criminals， man， criminals aren't very nice。Okay。

I think I'm going to just copy this function。Normally I would just commit to the source control。

 but since I'm just committing between streams。I'm just going to make a cold backup here for this function because we are going to break it。

And the idea is for every sound。And I did do this for my game jam game。



![](img/ab18094230a798259ac1baa49f82bf9c_691.png)

So if you have a hard time because I'm really tired to be honest。

 but I want to do this because I want to play the game a little bit offstream just to make sure that everything's working。

 And since this is a big change， I want to play in the the other。



![](img/ab18094230a798259ac1baa49f82bf9c_693.png)

The new system as well。And this game， I did for the game jam。



![](img/ab18094230a798259ac1baa49f82bf9c_695.png)

II worked on the audio like this， but it' not I understand the audio that a lot of people said that they couldn't hear any audio。

 which that was problematic， to be honest。

![](img/ab18094230a798259ac1baa49f82bf9c_697.png)

Okay。So the idea is I'm going to iterate。Through。The sounds。Okay。Rry through the sounds。

And if the sound is not active， I'm going to continue， so I'll need to that sound。

If the sun is active， but yeah I see， that's the thing， if the sun's active。

 it shouldn't have a sound。But because of some racing conditions maybe doesn't have。

 but I can just skip that there's no problem， sounding samples， same thing。

I'm not going to do the volume here the volume has to be done for sample。So yeah。

 and the sound volume。If you have a volume thing， so this is it。This is it。

Now I'm going to have to it for the samples。For every sample。Y。Yeah， yeah， for every sample。

I'm going to move the volume。嗯。And then if there's volume， yeah。

 it should be pretty much the same thing。O。Now， let's。How do you get graduates in C？



![](img/ab18094230a798259ac1baa49f82bf9c_699.png)

Well。We just ask Windows to display a buffer for us。



![](img/ab18094230a798259ac1baa49f82bf9c_701.png)

You can watch。You can watch the first live stream。

![](img/ab18094230a798259ac1baa49f82bf9c_703.png)

On YouTube， I'm going to link the YouTube channel。On the comments。

You can go to my YouTube channel if you are the first stream。

 which is a making a game in see from scratch episode one。

You can see we created the renderer from scratch there。

There's also a tutorial about how to get join graphics in C++。

 which is the same thing we do in C in this case。Y。How to learn C。I learned C++。

 or C likes C++ through handmade Hero， which is pretty cool。



![](img/ab18094230a798259ac1baa49f82bf9c_705.png)

Hamadehero。org， but it's kind of a not very friendly for super beginners。

 that's why I'm making these tutorials it's kind of a handmade heroro for more beginners。

But yeah it's super cool， but it's not very friendly for beginners that's why I'm making my how to program a Game++ for beginner series and this series reached is a little bit more advanced。



![](img/ab18094230a798259ac1baa49f82bf9c_707.png)

And I'm also going to do like a superner super beginner friendly series later on and stuff。



![](img/ab18094230a798259ac1baa49f82bf9c_709.png)

To have people to have a program now。O。So。Since。This。Oh， so I do have to zero the buffer。

Every frame now。

![](img/ab18094230a798259ac1baa49f82bf9c_711.png)

啊你 are要。I could zero them up there or I can zero them up here。

 I think I'm going to do this here right right before。Oh， I I have the。Ive played the game audio。

I'm going to me。This sound buffer for。Dot what is it， is it samples， Yeah， samples。0， I'm gonna set。

Is it correct the nameet？

![](img/ab18094230a798259ac1baa49f82bf9c_713.png)

Yeah， sees the value and then the account。 I'm going do the number of。



![](img/ab18094230a798259ac1baa49f82bf9c_715.png)

Bights to lock。 So oops， so sound。Bffer samples straight right。Samples to write。Times。

The channel count。Time the size of it。Over S 60。What does a basic game require like very。

 very basic game through things？It requires somewhere to draw pixelels two。

 so it requires a drawing buffer。some memory to drop pixelsels it requires the input。



![](img/ab18094230a798259ac1baa49f82bf9c_717.png)

You know what that did only two things and if you watch that series。

 I think you really enjoyed my how to program again C++ series think that before you， man。😊。

Because it's a very simple game it's super quick， it's almost over half done the game， I mean。

 the last tutorial we added the gameplay。So you have to do is some do some polishing。

 there'll be like two or three more tutorials because it want to add like an AI and a menu and stuff。

 but this is super simple and you're going to get the whole thing like understand exactly what it needs。



![](img/ab18094230a798259ac1baa49f82bf9c_719.png)

Size off sound buffer。嗯。Times。The channel count。 Chanel count。Okay， okay。

 so instead of adding that to the left sample。I'm going to。I'm going to add that to the a。Plus。

You can do like at。Es this。哎，做错。And plus equals this。Right。And add was please。

And at is just the sound samples。Just like we were doing before。

So we're going to iterate through every sound sample for every guy。Okay。

 conversion from F two to yeah， to be honest， this is wrong， this is what we should be doing。So。Yeah。

This is the last sample。And this is the right sample。Right sample。Okay。😊，And then we set the。

And the next man can be。From the setup up here。Sound。あめや。

Move towards the how we did this now we're probably going to break everything， to be honest。

 which sucks， but we're going have to I suck now should be getting oh。I don't monetize YouTube yet。

 I I don't have you need a0 subscribers。

![](img/ab18094230a798259ac1baa49f82bf9c_721.png)

So sorry。If you want to give me0。001。You could have to do so on my HRIO page。



![](img/ab18094230a798259ac1baa49f82bf9c_723.png)

But where you can download the source code so you can download the source code for all these products there。



![](img/ab18094230a798259ac1baa49f82bf9c_725.png)

This project， break our game games out。St for free， you are welcome to give me a tip。Like 0 dot 0，0。

1。 I don't think you can give 0 do 0。 You can give one cent。



![](img/ab18094230a798259ac1baa49f82bf9c_727.png)

呃。

![](img/ab18094230a798259ac1baa49f82bf9c_729.png)

And the tutorial series for begininners， which is this one。

 the games look like this now it's pretty cool pun。



![](img/ab18094230a798259ac1baa49f82bf9c_731.png)

Okay。Let's get compiling。M said samples。O。It's not a cornerer。I don't know。I don't know， let's hope。

 let's hope the audio works。

![](img/ab18094230a798259ac1baa49f82bf9c_733.png)

I'm going to put my speakers here I'm going to turn on your volume only if you guys。



![](img/ab18094230a798259ac1baa49f82bf9c_735.png)

呃。Only a you guy， only a few words， Brazilian chicks have big buts， they have big butts。

 they do thankfully。

![](img/ab18094230a798259ac1baa49f82bf9c_737.png)

So we don't hear anything。Well， maybe I'm do， I'm just going to because my speaker sometimes go to sleep mode I'm going to make sure I can hear。

Oh， so I can do here。I heard something。Yeah。😊，给唔感其。



![](img/ab18094230a798259ac1baa49f82bf9c_739.png)

Suppose you heard。But the problem is mixing。

![](img/ab18094230a798259ac1baa49f82bf9c_741.png)

But I suppose that's expected because we didn't change 100%， to be honest。that was good。

 that was a good error for the first time instead of just adding I'm going to plus equals。

Because there should be already information on the ad， so it just added the last sound。That's why。

It didn't work。Permission denied what？

![](img/ab18094230a798259ac1baa49f82bf9c_743.png)

Let's see。Yeah。Okay， it's not。100% mixing， though。Yeah。can guys here that was pretty funny。

And between our volume， you're not going to be deaf， hopefully。Okay， so we crashed。

Reminds me of D X balls。 I don't。 I don't know if I know this。At was zero。With 0。1 left。Update the。

 did I take you the wrong function？

![](img/ab18094230a798259ac1baa49f82bf9c_745.png)

Oh， oh no， I didn't change your infection， but this is wrong。I don't know， maybe I did。Oh， I did。

I did。Okay。Okay， so I'm going to add that， then I'm going to add the sample position。I frame。

I am going to have， I am going to have to think about this as well， the synced sound。

Do we have sneak sounds？Oh we do have the two music are things。 Let me see。The link。



![](img/ab18094230a798259ac1baa49f82bf9c_747.png)

Let me show you guys。

![](img/ab18094230a798259ac1baa49f82bf9c_749.png)

The link Herney sent。Oh， that's pretty cool。Yeah， that game mode was pretty was was u I don'。

 I don't if I don't know if I got to show you guys the other game modes。



![](img/ab18094230a798259ac1baa49f82bf9c_751.png)

啊。Yeah， so we start out as a clonal breakout。Like this。And we got free audio。That's awesome。🎼来抓死。

And then we have breakout with Arabs， so it's like the wanted to show。Okay， so。A is a no pointer。

Why is at a low pointer？Sound samples is not an old pointer。At plus equals。Yes。W did。

ItCame a no pointer。去聘。

![](img/ab18094230a798259ac1baa49f82bf9c_753.png)

That doesn't make any sense。What happened？I've probably played a lot of sounds at this point。

I know Java I want to use it to make games， there's a great tutorial。A great thin matrix。

Has a great open GL series using Java， I also learn a lot from that because you know OpenGL is open GL。

 right？Open。Open GL。So it shows how do we make games with a Java。

 a lightweight game library or something like this。I agree pretty useful。



![](img/ab18094230a798259ac1baa49f82bf9c_755.png)

Dude， that's so weird。Well， but I wanted to show the game。So I'm just going to make sure that。At。呃。

It's not zero。At these points， so assert。

![](img/ab18094230a798259ac1baa49f82bf9c_757.png)

And while I showed the other game modes， the interesting thing about the game。This point。We play the。

Oh， there arecade games。As if they were。I'll break out。🎼不买 god。

So that's the cool thing about the game， didn't have tes。Then have space invades。Yeah。🎼嗯。

So that's the idea about this game。Okay， so weve crashed again， oh my God。

 crashed so many times in this audio there no audio system。Exit violation reading。Location is zero。

 which one location is zero？嗯。Is it sound？Sound is undefined。



![](img/ab18094230a798259ac1baa49f82bf9c_759.png)

Am I optimized or what？

![](img/ab18094230a798259ac1baa49f82bf9c_761.png)

I am optimized。It's kind of weird that sound。It's not defined。Oh maybe I'm here， no， at at is okay。

This one。Then I add position。To some what。So weird， man， why don't I see sound？



![](img/ab18094230a798259ac1baa49f82bf9c_763.png)

I'm going to run a debug build and try to get these crashes。



![](img/ab18094230a798259ac1baa49f82bf9c_765.png)

I know that's why sure it was good to add business sound system。The other one was crashy also。

🎼It's not a problem that this one scratch。So probably next time I'm going to do an audio cleanup。

So we may have like two more feet out of us。I was planning for like 25 episodes。So， 20。

🎼24 review O K 23。Oh， we also have a sound not finishing。When we're back to the menu。

 did you hear that？Yeah， so let's fix that really quickly。



![](img/ab18094230a798259ac1baa49f82bf9c_767.png)

So。Ge。Whenever we， we transition， let's see。Change game Mo change to the menu。

We need to set the well， set the force seal to0。What forest field。Sound。是。It's funny。

Re're playing that twice。So suppose that's the one problem。Wse。See。

So we set that in the invincibility alpha， so I'm going to set the invincibility alpha。

 which the heck is。有点视。好死。Yeah， I'm going to say that to zero here。



![](img/ab18094230a798259ac1baa49f82bf9c_769.png)

2。Okay。

![](img/ab18094230a798259ac1baa49f82bf9c_771.png)

う。あ。I don't think I can hear the course of it now。Yeah。Okay， sound was a no point。

 that's so weird man。Sound。It says the sound was a no pointer。🤢，And it totally wasn't。四。

He's telling me that it's one。I don't know what's going on。Exception throne。So。Sound。

 sound is a no pointer。Except it wasn't。Read。I don't know， Anne。I think I'm not going to。

I think I'm not going to do this sound system thing。Because。Sound。Plain sounds。I don't know。

DoesThat make sense to you guys？Sound， sound was a no pointer。But sound sound is not an open pointer。

See， if I set the next statement， everything works。I think this may be a multi thread part。I' know。

I'm going to leave it like this for today。🎼う。And because I'm really tired to give up this maybe next week you're going to do。

没发你。And maybe。We're going to read you the audio system。Oh， maybe do人。



![](img/ab18094230a798259ac1baa49f82bf9c_773.png)

Prove the previous word and not do it。It's funny now it doesn't crash。



![](img/ab18094230a798259ac1baa49f82bf9c_775.png)

Yeah， I am going to actually test that a little bit。Yeah， this sound doesn't sound nice。五鱼。Yeah see。

There were吓跑了。I白。

![](img/ab18094230a798259ac1baa49f82bf9c_777.png)

Yeah。Okay， but I think that was great， though。I agree you， I agree with you audio。

We did a lot of stuff。We David cleanup。Is the watch Win on Vi Studio per thread or is it global？



![](img/ab18094230a798259ac1baa49f82bf9c_779.png)

Well， that's a nice point。I have to assume it's per thread。And。But it was weird。That。

That even though。Let's see if I have like which thread is this。Yeah， it has to be the birth thread。

Because if I change it。Well， no， it's global。I suppose。Oh， now sound is grayed out。

So I'm not entirely sure。Yeah was school， Yeah， and I'm going to tell you sure。



![](img/ab18094230a798259ac1baa49f82bf9c_781.png)

I could just add a bunch of certs as well。But。I don't know。A search。Let's see， this is certain。

We can assert life。Sound， sound。 We are already asserting it， but whatever。



![](img/ab18094230a798259ac1baa49f82bf9c_783.png)

🎼よ。This is perfect。Sometimes it's not working。It's the worst kind of bug。🎼い。Yes思。Very young牌。Yeah。

 I appreciate it has to do with Brad。Have to make the other more thread safe next time。

I think just by making。Or a to cops on the audio， we wear better。



![](img/ab18094230a798259ac1baa49f82bf9c_785.png)

![](img/ab18094230a798259ac1baa49f82bf9c_786.png)

Yeah， I think we're going to do that next time。Thank you。Okay。

 it was awesome to write a person today that was pretty cool。 That was pretty unexpected and cool。😊。

Okay， so I hope you enjoyed watching this tutorial as I did。😊。



![](img/ab18094230a798259ac1baa49f82bf9c_788.png)

This live stream really， because kind of was an open development kind of thing。

You can follow me on YouTube on YouTubetube。com/dzadan to see every video I'm making I'm doing not only the live streams。

 but also like dev log stuff。And tutorials now for CQ++ for beginners。

 I'm going to do some some crazy， more advanced charts later on。



![](img/ab18094230a798259ac1baa49f82bf9c_790.png)

You can go to my HO page， which download。h。o and download this game with the source code and all my other tutorial games。



![](img/ab18094230a798259ac1baa49f82bf9c_792.png)

And now you can also go to the team page of the game and Ralist and please do because。It's awesome。

 we are going to release this game on steam and you can see the whole process of creating it。

So you can watch the whole thing。Up until the steam release， so you can actually a wish list。

Why don't you have Instagram？ Well， why would I have an Instagram。

You can answer your wish list and that would be pretty cool as well。



![](img/ab18094230a798259ac1baa49f82bf9c_794.png)

And this my other game， as well， if you want to buy it， it's pretty cheap。Okay。

 so I hope you enjoyed it， and I'll see you next time， bye。😊。

