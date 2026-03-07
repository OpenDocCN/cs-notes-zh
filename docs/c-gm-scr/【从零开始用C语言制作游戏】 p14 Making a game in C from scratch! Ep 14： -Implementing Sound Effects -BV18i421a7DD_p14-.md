# 【从零开始用C语言制作游戏】 p14 Making a game in C from scratch! Ep 14： -Implementing Sound Effects -BV18i421a7DD_p14-

Hello， everybody。 welcomecom to my new live stream。

 where we're creating an entire game in C from scratch。 Well， our game is coming along pretty nicely。

😊，Ever since from the first day， we started with no load libraries， nothing just a blank file。

 and we typed every single line of code on stream， and you can watch the whole thing on YouTube。

 which is YouTube。 com slash Dan a Dan。 so much all those episodes have been 12 well。

13 episodes so far。😊。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_1.png)

I， let see if I played in the。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_3.png)

Yes， I have the playlist。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_5.png)

13 episodes， and the game has come along pretty nicely if you remember from last episode。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_7.png)

We started at Sun effects， we made a main menu with the game？🎼いフて music。

And now it's starting to look a little bit more complete。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_9.png)

🎼And。So。The mission for today。just to make the game a lot better。

 And we're gonna do that by adding the side effects that we didn't do last time。

 which you gonna can see here in the data folder。 There's a lot of side effects that I picked up where I like the bricks and the hits。

😊，In the fourth field， there's still a lot of sound effects to add。And， and also， a few things to。

To improve， I did play the game a lot when I was off stream and I made a few notes。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_11.png)

🎼Of things that we may want to do quickly， some are bugs， some are some are improvements overall。

 but because if you guys would remember， there was one known bug， which is a little。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_13.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_14.png)

What effects more noise that we added on our guy。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_16.png)

Okay， and we're going to fix that today as well and then implement all the other kind things so the first。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_18.png)

Bug， is that even though we are not like hovering over the， I'd say， third level？



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_20.png)

If I press the button。It goes the third mile。That's a pretty bad bug， right。

 but should be easy to fix at below。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_22.png)

Project。Let's go to。Me有。See if it's not locked。Yeah， the hot level is this。

 When I press the left mouse， but I check。If the level is locked or not。So。If it's not locked。

Howll do this。嗯。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_24.png)

I still hard来。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_26.png)

In fact， I me just get the。Compilation thing on the other side。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_28.png)

🎼Just so it's easier to see。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_30.png)

🎼うんうん。Yeah， so now I can't go to two， can go two。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_32.png)

🎼3 but chicken go。Okay， that was a small part。And another thing that I want to test。

 we' going to add to our audio system。 Let's go to audio。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_34.png)

I just right here， we clamped the audio， which was a very nice addition to make sure that it's not like too bad。

 but I'm also going to add。A like visual indicator。 if we， if we are clamping the audio。

Just to make it a little bit。A little bit easier to debuote things like that。

Because you're going to improve the level now。 So if the min is less than， well。If the。

 let's say if the left sample。Times 0。5 it less than the min。Or。

greaterd than the max or same thing for the right sample。That's up print。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_36.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_37.png)

🎼いし。I think you could hear as well， right？

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_39.png)

Yeah。So。😊，I have improved the sound in that case。The first thing I did to the sound。

Let go to the games。I created another side wave because the thing is。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_41.png)

If I go to like。Down here， and see。Let's see。Here。We are going all the way to eight times the speed of the sound。

And that's really problematic because at a time the speed。 Well， let's say the samples are like this。

Well dislike like the waveform and these are the samples。I mean。

 we have a lot more samples so that we draw like this。So when eight times the speed。

 we are ignoring like every， well， eight， seven and every eight guys， so we're go to like this guy。

 then we do like one， two， three， four， five， six， seven， and then we do this guy again。

So if this were the case， this whole wave pretty much just got clipped。Of our new， let's say。

A no wait for。And that's not what we want。So。One of the ways to quickly do it。

 or just another disclaimer。We could， we could add a sine wave in the program we could like。

Program a sine wave that way we could have like a more precise one。

 even at a higher and lower pitches， but I don't think they'll be necessary。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_43.png)

So I'm just not going to do that， but we could。That wouldn't be too complicated， I think。

So I have made a sign three。Which is like a lot deeper。Let me just remove。

This guy for this sound for the sign。So we can hear。Like。I'm also going to。It costs volume。

That's your what it sounds like this angle。So it's a little better。

 so we're going to play around with that， okay， but before we actually do that。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_45.png)

Let's just improve this guy。Overall， because it's。There are a few problems because we wrote that pretty quickly。

Okay， one of the problems is this guy， the volume。 We update the volume。Just once per audio update。

 this like one6 of a second。But。Our failing speed。Well， that should be really changed per sample。

So if we are supposed to like make this audio more intense， let's say。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_47.png)

This guy。Should be like this And。The next guy， even though he was already on the same chi。

 we should really make that more intense and this guy more intense as well。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_49.png)

So pretty is I'm going to take this sound up here and I'm going to place it。

Right here in the beginningkini。Maybe， maybe like this。But is off doing like the DT？

And well have to multiply by the samples per second。Okay。Samples for this sound。Perect。

Samples for seconds on the remember of loaded sound。No， we have to get that from the。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_51.png)

三个分。Okay。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_53.png)

Is that correct？

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_55.png)

No， should be divided by。Let's per second。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_57.png)

That's way better。Here let us take up in music。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_59.png)

And pay attention to the phian of the sound。嗯。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_61.png)

That was pretty cool， right， greening is wildlife， How are you doing？



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_63.png)

And let us go to the old system。And I'm going to hit some artifact。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_65.png)

四。😊，Perfect， so that was a nice improvement。Of the sound system。Another one that we should。

Fixed is this guy。Because we are also updating this guy wants per tick， which is the。The position。

 but we should also change the sound， the speed multiplier because in case I like synced sounds that are。

呃。See sounds that are pitch shifted。We should change not only the position。

 but also the speed multiplier。That was a small stake of our part。

Let's see yeah and the volume thing。 So these are my notes。

 a couple of other things since we added a lot of stuff in the sound， it maybe be like a good idea。

Just set the。The sound to life。0。What's up， Tim， Hello there。 Oh， I've been rated by a party of 17。

 what？Thanks， Tim， Thanks a lot。 How are you guys doing。😊，Oh， so many new people around。

 that's awesome。Thanks for that。 So I'm going to explain to guys what we're doing and maybe sure let me just put the music back on because we took that out。

😊，This look could fix a little bit on the audio， so。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_67.png)

Welcome， welcome clone Cls here already。 Welcome， everyone to the live stream。

 We are creating a game in C from scratch， so。😊，🎼Well。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_69.png)

I you also take out that。This sound that we are adding， the sine wave so。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_71.png)

We have a breakout kind of game and you start out pretty similar to the breakout。

They' even the side effects now。Because for the past， like a couple streams。

 we did the audio mixer from scratch。And now we're at a good point to start now making more interesting。

So we had music last time。🎼And now we're adding design effects and we're fixing like a couple of mixer bugs。

I love the hidden white and they better yeah。😊，And there also there are a couple of cool effects。

 it's not only widely， but it also has like a spring effect。🎼し？😊，And that's pretty cool。

Because it's a mouse movement so I didn't want to change the acceleration of the mouse。

 but I did want to have some kind of a visual effect for the acceleration and the deceleration and the way it feels it really feels like squashing and stretching for this guy。

And。And the follow through when you stopped， getting that animation is awesome， thanks。

What what I was adding that I' not 100% done yet is going to try to squish yourself against a wall。

 so let me go here， there's a wall here。I have to change the position。🎼But it's already， I know。

Moving like that so。This is going to be cool as well。But we didn't stop there。

 so after we did the breakout clone， started adding a couple more cool features like。This game mode。

Has power ups and power downs， so let's see you can get that up。So this is like force field。Soう。

I have to hit the ball for that。🎼And there are also sort。🎼Als， yeah， this one't triple shot。

And this one。The comments， yeah。And these guys， I should be boy those are the power down。

 so I got the power down for strong blocks。🎼So yeah， now I think it's right now and now it's right。

Okay。Yeah。Oh yeah， I see pretty cool， right？But the idea of the game is actually。

 what if all Arrcaded games were like breakout？So implemented breakout palm。🎼やな。Well。

I have to be careful not to。It all those hard downs。And we still have to do a lot of stuff here。

 but that's just kind of the basic idea。Break out space invadeders。 This one's really crazy。しし。

And the idea is to add。Like I dont know something like 10 Arrcade games。

Last stream we kind of discussed a lot of cool ideas， maybe you guys can have cool ideas too。🎼2。

To see what kind of acaded games would be fun as breakout clones， so to speak， right。

 breakout inspired games。所燕。That's the point where we are now。In terms of what we did。

And this game has been created entirely on a live stream。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_73.png)

So if you go to the YouTube channel， which is Youcom/D Z Dan。

You can watch from the very first episode that we started with a blank file。

All the way to where we are now。And it's been a long way， but it's been like 30 hours of programming。

 I think by adding all the hours together， 30 hours， we got from nothing。

To where we are now and we want to go beyond， we want to make it。Really cool game and ship it。

 maybe on a HO maybe steam later on， not sure。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_75.png)

And the game's already here on Hhi， if you want to download the game and the source code。

The source code is all for free。You can download the。They executable NS code for each day。

 So you can follow along and maybe add to the game and program your own things and。Learn a lot， too。

 Sake。 To the small apple and make the bowl a bit smaller every time。 Sake's pretty cool。

 I had the idea for a centip bit。😊。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_77.png)

Right。Sit a bit。 yeah， let's add snakes in that as well。That's gonna be cool。

 Looks like you use Viual studio Vim。 Do you use these sorts of libraries who help you create games。

 This is really cool and informative。 Thanks for sharing。 No problem， it's my pleasure。

 This is actually for codeder， which is tech editor。 It's pretty much like Vim or like inax。😊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_79.png)

But a very new kind of of。And you can go to fourth quarter HIO。

You try you and you can download it for free， there's a free version and there's also the customizable version。

 which is like $12。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_81.png)

But this was the free version。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_83.png)

And， but it's pretty cool。 So I use it this for a code editing。😊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_85.png)

In the Vi studio， I use it for just debugy and running the game。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_87.png)

But I unlike it for a code a lot， it has a lot of cool features like something he calls like ghost indentation like so if I keep adding like indentations here。

 it updates automatically and it runs great。😊，Yeah， and if I feel like can if。

This guy gets intended or if I do something like this。It prevent an。

Break for two who has the most core wins， both of you guys。Breaks so breaks them all the first one。

I'm not sure my got what you mean。But in terms of tools and libraries。

 all we're using now is SB image。To read the PNG。We are probably going to use SDB for us to read OGGs。

Yeah。😊，That's only it。 I mean， just that in the windows， stuff。We're losing theer。

 we did the renderer ourselves。And it's a software renderer。

 and it supports like transparency and rotate rotated rectangles for the particles in transparent rotated rectangles。

 which do like matrix stuff here。We also do we like draw bitn and we do like texture sampling。

Things like that。And that was all written in by hand。Oh， we also added something of accuracy。Oh。

 so he's just a two player both for breakout competitive。 So who has the most core wins， both has to。

😊。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_89.png)

Okay， so I suppose the players are like side by side that could be pretty cool right。

 I mean both of them down here。But since we are using the mouse。

One of them would have to be a keyboard player。Ill keep our play。I like a guitar player。

Like playing with the key。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_91.png)

🎼And。Or maybe we had joystick support。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_93.png)

I wonder， though， if you use any kind of libraries for managing Windows or something like that， no。

 we're not using our window stuff。I's just like my hand。 so let's go to like win main。We start out。

 this is our main。And we create a class and a window， this is our great window。

 right this is like the Windows call。😊，And we do some audio stuff。

 we use like direct sound for the audio。And yeah， we just get the window stuff for， for input。

 this big messages， windows。And then。Yeah， and then the drawing is also Windows stretch DI bits。

 that's the GTI call for the Windows Soer render。So yeah。

 it was really supposed to be a challenging and educational stream just for fun。

And because it's a small enough game， we can pretty much do everything ourselves， I mean。

If we really didn't want to use any libraries， you would probably like read VMPs。

Bit mapps with a B&D format and not use SDV image。But I don't know。I don't want to be that rigorous。

 but things like window and stuff， I like interfacing with Windows directly because it's really important and when we get to write more platform layers。

 well have a thorough understanding of what it actually takes to get it working。

 but SDL is a very valid choice for especially a little bit larger games like this one if you want to do like。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_95.png)

Something more robust， but since this is a very small kind of app。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_97.png)

Funan project。🎼呃。I didn't think it was really necessary。Yeah。

 and we also did some cool stuff we did like thread。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_99.png)

So our audio runs asynchronous asynchronously。 That's hard thing to say。😊，It runs in parallel， right。

 We added multi threatening support， and the audio is running。 So if we like。😊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_101.png)

If I stop the game。🎼That's just。🎼If I stop the game， I can。I change the size of the window。🎼ちま。

What up to the window？

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_103.png)

That was weird。Let's try it， change the site， yeah apparently I can't change the site。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_105.png)

🎼我们下见。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_107.png)

But if I like， move the window like this。Or like make it full screen and。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_109.png)

🎼All that stuff。And I go back to that。The audio keeps playing。Okay。

 then that was a long wide explanation for that。 Well。

 that's amazing never went lower than SDDL and glue or C since I really prefer simple。 Yeah。

 this project， I did that on C just because it's supposed to be really simple in terms like。😊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_111.png)

Both the source code and our experience， so you're really supposed to you know take a look at the game and kind of know exactly what it's doing like step by step。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_113.png)

But next games， when you get a little bit more complex than this。

 are' probably gonna use C plus plus， definitely， yeah。

Also because that's that what the industry uses right so you want to really learn that if you are to work on bigger games in other people's first code。

 but this' is just for fun just for a hobby so I'd say because I think it's cleaner and it's also compiled really fast I mean。

Yeah， pretty fast。Awesome。Okay， so let's start， let's go back to fixing the audio。

 so we did a lot of improvements already from of the volume problem we had。😊。

I can move the volume to here。Okay。Now， we still have a couple problems。

 And this one's a pretty simple problem。 If we overflow and we are supposed to loop。

 instead of just setting that to 0， I'm going to subtract this guy。To this guy， That's like a。

Clas classicalical thing there we got it wrong the first time。When we are ready。I see。I see。Yeah。

 see。 that's， that's awesome。😊，Okay so。So we fix that and this guy's also problematic， this guy。

Because that's the basic idea we have。 We have a sound position。

 which is where in the sample count we are， okay？And and we increment that by our speed multiplier。

 the default is one， so we go like one sample at a time。

 but if you want to speed up the sound or make it slower， we can make it like a fraction。Okay。

 and then this is our sampling where we transform this guy into an integer and then lup to like the two sounds like this one and the next one。

However， there is a problem that we didn't address， I mean。

 it's this guy if our next sample is overflowing just like our position is。

 we are supposed to you know go back to the first sample。Or do other things。

 but the problem is this guy is in sample units， which goes let let's say we are we have like a one second file so it's 44000 samples。

But if it's two channels， so it has a stereo system。We have like twice as much sample。

 but the sample count is how many samples they are not considering。The channel count。

 So when we go fetch the sample here， we multiply that by the number of channels。So far so good。

 So this guy should really be the sample count times。😊，The channel cut。ok。😊。

So that was a small mistake of our part。I didn't consider this。

 and we should also only do that if the sounds supposed to be looking。Where else。

We should really just set this guide。To the sample。So we pretty much get the less。

So that's really fixed a lot of stuff。系。Oh let's go back to our testing scenario now that you guys saw the game thanks for the rate that's awesome a lot of people I've never had that many people watching on the stream。

😊。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_115.png)

Hope you guys enjoy the game and the process as well。啊，O。So。Yeah。

 let's remove the sound volume and then let's add。This volume back in so。

You can hear our play movements out and this。This movement's not with the animation。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_117.png)

That you guys liked。 This is gonna be awesome because the sound is also going to emphasize this quoian stretch aspect。

 That's going to be really， really cool。😊，啊。Okay， so yeah。

 we' back to where we were if we are supposed to， you know， change the volume。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_119.png)

Based on what we did last time， we just is like。呃。you know。Pretty much the same thing。嗯。嗯。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_121.png)

嗯。ok。This will be cool， maybe we can tweak the values a little bit。Because I really go crazy。😊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_123.png)

屎。😊，Let me turn you guys volume a little bit down because I don't know if they cliped or not。😊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_125.png)

Yeah， anyway， that's see that zero that's the print we added earlier today。

 which means that we clip so we we will probably have to clamp。This guy let see。0 and。Let's say，2。

But also， let's make it a。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_127.png)

Campair， it's also make。嗯。Yeah。Yeah。Okay， that's good。 That's for the sound， which is perfect。

However， we also want to change the pitch。And this going to sound really bad。

 I'm going to turn your guys' body really down because these were the old values。う。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_129.png)

And we have that problem that I mentioned that since we are going all the way to eight。

This will create weird behaviors。 So if you go like all the way to 3。

And we could also like decrease this guy。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_131.png)

That would be a bit better。嗯。Oh。Yeah。うう。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_133.png)

ううう。Okay。😊，But let's also start。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_135.png)

被较 lower。Guy like this。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_137.png)

来 you。う。嗯。Yeah。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_139.png)

うん。Okay， that's way better， but。Let's try adding them both。

 I think that was still a little artifact there。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_141.png)

の？Yeah。It was kind of late for me wanted to go to sleep right after Tim St。

 but here did this scene so that's how I got here was nice to see our project and talk to you We'll subscribe to our channel keep。

 Okay， thanks a lot man。😊，I'm glad that you enjoyed this stream as well。Yeah， it was nice。

 getting to know you and hopefully you'll be back for it。

Hopefully the end of this game because we are getting there slowly， but we are oh， not that slowly。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_143.png)

So thanks for dropping by yeah， have a nice night， yeah。😊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_145.png)

So this is the kind of effect we want。そそ。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_147.png)

Let me turn your volume up now so you guys can hear exactly what we want。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_149.png)

。And that create like go。Very natural whoosh。🎼Kind of a。🎼うん。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_151.png)

Kind of side effect。Right， and that's really， really awesome to hear。😊，Really， really cool。

I think that's about it。Try to understand。That small problem that we're having。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_153.png)

ううう。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_155.png)

Let me go back to the 100% volume。Just sort you know if it's our speed change。A not。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_157.png)

啊。嗯嗯嗯。うん。Oh。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_159.png)

Maybe we can play around with these settings。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_161.png)

Like， if we make it slower。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_163.png)

， she doesn't solve it， let's go back to the audio just to make sure that。

Onio is make sure that everything。Is nice。We fix a lot of stuff。This guy's perfect， and we add it。

Go back。As we start， will it possible to change the compiler to DCCC？

I'm pretty sure you could compile the game when you download the source code， you have like。

This directory here， as well as the data What app， this directory。

And I have this buildc bat script here。Well。That be sure。That evokes like Microsoft's compiler。

 but you can do pretty much the same thing with GCC， I believe I'm just compiling this guy。

So the unity field to just compile one file and it includes all others。

And then these are the libraries I have to link to。Yeah， it should be able to do。

 I'm not using any compiler specific things。You just you know we're using Windows normally， right。

 but in terms of the compiler， we didn't do any compiler intrinsics or things like that。

So it should be good to go， I think， if you download on HIO。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_165.png)

Yeah。Which is dZD。h。io。Let me throw that link here for you guys。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_167.png)

But it should be good to go if there's anything you want me to do with the code to make it more friendly to all your compilers。

 you could just tell me and now I'll try to do that as quick as I can。Okay。

 so that's just a quick look at the audio again。So if we are synced。

 we're going to get the spin multiplier and the position from the sync sound， that sounds good。

And also， I'm going to put like a speed comment here， like we to be。More cash friendly。

We should iterate。Over。Samples inside。一曲。So maybe when we profile， we can optimize that。

 but should I then use a P3 instead of the Windows ones？Oh， but are you in Linux， Yeah， Oh okay。

 if you are in Linux， you do have to change this file entirely。 Yeah。

 didn't get what you mean what you said there。 So this file is all we do specific stuff。😊。

Like we are all in Windows La here， so you do you need in the platform common file。

 you see what you need we need you need to create like an OS read entire file。

 That's what the game uses OS3 file， OS read save file。OS write say5。And also the job system。

 so you do need to use your thread system， you need like OS add job to queue。Okay。

 and you see how these functions are implemented here on the。On side of things。

But what the game really wants is just call update game。

That's the only thing you need to do just call update game and you pass the input。

 which is structured specified here in the platform common， and then you'll pass like the delta time。

And the game may use these calls Mingji does have big threads。Part for Windows if， yeah， Okay。

 so if it does have like a nice window part in this case， let me just open the window。

It's kind of a hot in here。Okay。If it does have a。For Ts， then would be a lot easier think。Okay。

 so I don't know， I kind of bumpummed out by。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_169.png)

The non perfection of our sound。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_171.png)

Yeah， let's just take a look at the volume again。The fighting。If you are having a。

The volume is in here。And' moving like from this guy to the target volume。And we have a fading speed。

And we're dividing that by the samples per second， so this phase speech will be in seconds。Or yeah。

 because now it's in samples。Yeah， this is perfect， so if we do have a volume。Then we get the sample。

 this thing we didn' we don't need to change that。And if this well should do like greater or equal then。

This guy。If you're supposed to loop， we go back。My whole thing。And okay。

 and if you are not supposed to loop， we just set the sample to repeat。

That looks correct and this thing we didn't change today and we didn't change that。Yeah。

 everything looks。Nice。Thanks again。 I followed followed it。

 but we definitely start by again to see how it's going probably check out the videos to learn more。

 I know nothing about see best of luck。 Thanks a lot for your kind words， man。

 check out the videos I think you like a lot because I go。😊。

From the very beginning of the bathroom layer all the way to the crazy stuff like threading and audio asy stuff that we're doing。

Hopefully you learn about C as well， C is pretty cool。

 I really like it so yeah thanks for dropping by and thanks for following as well。😊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_173.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_174.png)

嗯 응。Okay， that fixes it。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_176.png)

Perfect。That's what I I needed。 So that was a small problem。 We were。If we had like。

If we were the same， if we reached the end of the channel account。

 we're still getting the sample and that was problematic。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_178.png)

응 응。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_180.png)

This is exactly what we need， now you can go back and make it a little bit faster。😊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_182.png)

Again。嗯。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_184.png)

And。Pro make the volume also dependent。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_186.png)

See， that's the sound we want with the animation， new guys saw the animation at the beginning of the stream we're like。

 oh， that's a cool animation。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_188.png)

Would this sound？It's like。😊，A lot better。And now when we do it play down。

 that's also not set according to zero。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_190.png)

🎼うん。That's really cool。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_192.png)

Awesome， so that's it for things that I wanted to fix。Or improve for today。

 so let's just keep adding tons of sounds， tons of sounds so we fixed the noisy glitch。

Thats implement。All the other sounds， we have a to sounds。Let's see， let's do a fireworks。

When we hit。The ball。 So let's do player ball collision。28号。Update balls。P collision with ball。

So wereuc colide。Well play sound。Would you like fireworks？So。Okay， and it's not going to repeat。

 Now let's add a。Lowed sound for fireworks。Fireworks。Yeah。Sounds， and when we load weight。

Let's do fireworks。 Sound going to be。 what is it called。It's go fireworks one， well。

 there's only one， I couldn't find any other ones。O， yeah。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_194.png)

That白。开始。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_196.png)

That's awesome， that's a little bit of variation just for the fun of it， let's add this guy like。😊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_198.png)

Yan， I you like， awesome。ExplIt sounded like a cool explosion， It was like a pop。And we'll do like。

Sound of volume。Ro's do like set body。For the sound， and we'll set that to a random。

Let's do a random float in a range， let's do from 0。85。To point。15。😊，Okay， yeah。

 And then we're also going to do like the sound。S multiplied。

This is like a very fun part of making games。Is just adding one thing at a time to make the game even cooler。

 So now we're adding this sound effect。😊，Let's see trunkny from double what， Yeah。

 that's the message float。Adding one on a effect， they they're going to add a new one。

 then they're going to make it look a little bit better， things like that， let's see。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_200.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_201.png)

And a little bit more variation。Is it like 0。8？2 this scale is do。74 I to 0。75。25。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_203.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_204.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_205.png)

That's cool。 Maybe I can do even a little bit more。 Let's try 。5。 Let's go extreme。😊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_207.png)

Extreme variations。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_209.png)

Yeah， I like that now let's make whenever we change the whenever we hit the wall with a ball。

Let'd say update ball。嗯。Yeah， like this。Let's play sound。Let's play the spring sound。Which is a。

Pretty fun sound。let's actually do a。Let's do a functional of that， I think。' goinging to do like a。

I do。哇。I don't know。でね。W hit。Exffect。Yeah。Yeah， let's add that to the level。Okay。Tnalvo。

 do all hit effects。 And let's take a pe。And yeah。The ball is I。Okay， nice。

 and now let's start doing like play sound with the spring。And we should also。

 we should probably make this guy function， Mike。啊。This guy。Yeah， I'm gonna do like he。So like play。

Sound with variation。I'm going to do like 0。5 of variation and I'm going to play。

This one was the fireworks。手。Okay， and this one has to be with variation as well。

And I'm going to pass also， let's do like 0。3 for this。And in the audio， we have the play sound。

Let's do the internal。等下 play。Sound with variation， let's take same thing loaded sound pointer。呃。

But will take an F32。这样也行。确认。Sound， and so we do sound false。We do one。Minus variation。

And then one plus variation。And same thing here。Okay。Good。Re definitionfinition of sound。

turnur result。Spring sound。 Let's add the spring sound。Voldote it sound。Let's do this spring。So。

High worries。And。Let me see what is he called？Just pray。Lets do。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_211.png)

And I think that'll be a fun sound。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_213.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_214.png)

W。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_216.png)

啊。P。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_218.png)

I didn't hear anything。Okay。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_220.png)

It didn't compile they should be like a red error message that's really sad。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_222.png)

Okay， kind of like that。 Have a lot more sounds。Can do the comment the first few。

That's not the game over sound。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_224.png)

Yeah。In fact。Let's add a bunch of them。Game over。So。And， let's do。The lose life。都是。Life。😊，Sound。

 and let's also do the。He。Well， I'm not sure that's a good wind sound。Loose life。 Game over。And。

 let's try that sound。Start， lose life and game over。O， let's see。啊。Start sound。Gae over sound。

And lose life。Thoseose。来。多分的。So start start。Start。啊。😮，我哋我好似讲。Start game yet。Okay， now in the start。几。

😊，悟口。Student。Play sound。啊。Start。点声。ok。And when we lose life。If it is game over。Let's do play sound。

Game over sound。And here。If we just lose life， let's do a。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_226.png)

Lose来想。爱 see。😊，Okay。嗯。I think we miss failure， let's see like。No， I just export the sound， oh。

 the sounds were 48。48000 hertz。Just going to export them quickly here。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_228.png)

Which one was that， I suppose it was the。好 let me see。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_230.png)

I suppose it was the。啊，は。进出。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_232.png)

Game over， but I suppose all of them will be problematic。But it's going to be an easy fix。

an open reaper here。And let me see if you guys。Be able to see。Yeah， something like that。Okay。

 let's do the game over sound。Let's just drop it here。You make it shorter as well。Then。

Let's export that。To the sound effects， that's called that game over。And let's do。44。Hers stereo。

air opening。嗯。Oh， let's call that game。On this score over。And。Let's see if we crash。

Maybe you lose a life， he's also going to complain about that。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_234.png)

开始。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_236.png)

Yeah， lose life。Let's do best for this life as well。Life。😊，Okay。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_238.png)

Okay， that's see。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_240.png)

呃。We call start game at the beginning。I don't think we should。Oh yeah， we have to。Well。

 maybe you can。Because it does like。Let's see， yeah， player target P， player half size。 Well。

 this should really be here and。It should be here。In it all first movements。

I think that was the only problem。Play your life， yeah。Now， that wasn't the only problem。

Let's see what else we do with the player well。I don't know。The level state。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_242.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_243.png)

Arena， yeah， let me do the arena thing。As well。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_245.png)

🎼Yeah， I think the play is the for like condition， yeah。😊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_247.png)

Did you consider changing the bad script to SeeMake？I just didn't need to。呃。I mean。

 if we ask the point where we need a more complex build system， sure。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_249.png)

But I don't really like to put complexity unless I absolutely need it。And since like。

Did need it for this project， I just didn't use it。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_251.png)

🎼But that's okay if you have an experience with that and you're more comfortable I'm not very comfortable with this。

😊，🎼comし。Then呢又 be一个这个。🎼Just see。I'm not sure that that was correct collision behavior。

 I'm just going to note the timestamp here so then we can take a look at the fraud later。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_253.png)

Check。可离线。On last。Trees。30。That was a bit weird。Hi。

 maybe you can borrow some ideas for this simple fantasy console game。Sure。

 I'm going to take a look at that。Thanks for a。Did you make that game， Thanks for for the link。

I'm definitely going to check it out。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_255.png)

🎼Okay， I think not me， okay。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_257.png)

That was a bit too much。Like。Let's do later。Ping cells。我就是。关掉。Maybe can last。Let's do 35。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_259.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_260.png)

Okay， and we also have a redirect。But that really sounds like a， oh。

 I don't think we tested the lose of life。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_262.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_263.png)

Okay， that was kind of decent。Kindder， but that was too loud。Yes。😊，And we lose life。

 let's do the same thing。呃。Play the sound。です。一 can set volume。Pro any these graces。By the way。

 from Brazil， I am here not to here not to。I Pa。 I， I'm from Brazil， man， yeah。😊，Me too。

 where are you from， I'm from Mina Gers。Awesome， beella Dzoj， dude， I'm also from Bellazoch。

Maybe we know each other from like some event。Maybe we do， and I don't remember。啊什么。Yeah。

It's just small world， it is a small world。Because， yeah， awesome。😊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_265.png)

I'm also a game developer he said I'm not a game developer for。🎼给你三随便。

But you are interested in getting it out， are you not？炸什么？

Even though you haven't done anything yourself yet。🎼Does't take much to become game to help？



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_267.png)

Yeah，Okay。He said he was graduated on computer science， though okay。

 so you do have a foot at least inside the technological things， that's pretty cool。This sounds a it。

Too negative。Let's try to。I was thinking about theres a re sound。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_269.png)

Along with。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_271.png)

Along with the spring。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_273.png)

Maybe I'm going to add that。 just a touch like。Let's。No。Nice work， by the way， thanks， man。Yeah。

I think it is coming along pretty nicely as well。And you can watch the whole thing I mean if you want to you know programming probably right but if you want to go and do games you can watch the whole thing and then you'll see like the differences。

 I really like programming games I think it's a great challenge and it has its own kind of upwardquis which is the fun part and it gets to a point where it's just pure draw like this point where we're just playing around and that didn't sound okay same thing it's really really fun on me and the constraints are really hard technically so you get the best of both world to get like a lot of technical challenges。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_275.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_276.png)

And you also get a lot of odd。Get a lot of fun stuff just things for fun， yeah。Okay。

 let's do like the entire project。Now let's do like current time selection。

Time selection and this was the what sound was this redirect？Redirect sound。That's right that。

 and I could probably。I could probably change the。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_278.png)

Volume here。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_280.png)

Yeah， let me do that。We changed the flight。Yeah， okay， that'll be enough。It's redirect sound。Okay。开谢。

I got the full source code。 I will watch one episode per day that's a good pace because the episodes are full of information。

😊，啊。But a one per day should be a nice place and you should really you know get the source code and play around with it。

 really， you can do whatever you want。If you want to make your own games on top of that or if we just want to play around with this game。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_282.png)

It's all good。 I changed the name to red sound because I think because I just imported that from to Riper。

 it was complaining about the。OhAnd I should also use， right？I'm gonna add that sound when we do。

 like the。Aate thing。Whenever we yeah。Do all。 Yeah， let's also play。They're regular。

With a little bit of variation。 Maybe not sure there'll be too much。 And then when we hit。

When do we destroy block？Just try。啊啊。Oh yeah， I we probably changed。This fine。Blalock destroyed。Yeah。

😊，Will， also， let's see。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_284.png)

Yeah， also play this。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_286.png)

Okay， we are going along nicely， I think。There are just a few other。Ones that I think I need。

This whistle out。It sounds pretty bad。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_288.png)

But maybe I can get it sound good， I don't know。This is supposed to be the ball sound。

And we're also going to play that sound like。Forever。F1 to 0。Yeah。Wehi also do one per ball。So yeah。

We have the ball。Let's add。A plain sound。And would be， like，4。Each ball。Yeah， for each ball。

Let's set the balls。I don't sound。To play sound。Yeah， and then we do the。高上。Okay， now。

 which probably also set the flag to zero。And then inepate。Balls。Here。😊，Let's do the ball。Sound。

Target volume。Equals， let's say the。到。Do we have like the DP？Yeah， D P dot。Let's do the XDP。

 which is won the player can sequence so we can play around with that。

Okay we'll take the absolute of that。And。We should probably。Just see。

What value do we have before we go nuts？

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_290.png)

You' probably just claim that。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_292.png)

0ロ？Okay， we shouldnt， we should do like this guy。Plus。Theわか。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_294.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_295.png)

And it's probably like yeah， it's like 50。🎼607。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_297.png)

100， 100 was kind of fast。So let's make that。这发来看。ok，我 think到底。到底く。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_299.png)

Then。不事。Sound was a no pointer。Did we not？Do we not set everyone's proper sound？Here。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_301.png)

Okay， oh， we didn't load the sound嗯。Yeah， we've got to load the sound。No喂。张楼子箱。

You can't play this out， that's how it goes sometimes。In fact。啊。As就。

What sound was that the ball sound？It's going to be。The whistle。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_303.png)

Not sure， let's see if you guys think this's going to sound whether it or not。

 I can turn you guys bottom him down。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_305.png)

Is it going to go deathaf？

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_307.png)

Still no sound。Apparently notdge。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_309.png)

Let's see， ball sound。Is this guy。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_311.png)

Yeah， let's try to break online 203。Okay， so we do load this sound， which is nice。

Or maybe' we haven't initialized the balls yet。好。Okay， because we。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_313.png)

We zero the balls。Whenever we start game。I think。😊，Yeah， we zero the ball。

 So let's not zero the whole ball。 So You're saying you're using four quarterr for the editor or your thoughts。

 I really like it。😊，I really like it， it's really fast and it's very easy to use， I mean。

 the thing about them right that people spend time a whole bunch of time just getting used to it。

Not even forcoder， you can get used pretty quickly and you can get crazy fast at it too。

 and the thing about it that I don't really use but you can go crazy is the customization。

So you can customize like every single thing you can write whole C program that runs on top of4 quarterder if you want to do your own stuff。

 I haven't done that because I don't I don't want I don't like spending too much time doing things like that。

But if that's all thing， you can go crazy。 what I really like about it。

 first thing is that's pretty fast another thing is that the。😊，Is a。The ghost， like indentation。

Pretty much makes me not worry about indenttention like ever。

 I don't ever worry about indentcing code and that's just too boring for me。

 I think so if I have the chance，To not worry about it， I'll take that any day of the week。 So， yeah。

 I really like it。 You set of zeroing the balls like this。😊，Going to do， like， playing sound。

So equals balls at I。Dot sound， then I'm going to zero just the ball。 I'm going to do。好。来啊。Because。

All， say，0。And then， we can do。sound。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_315.png)

一口下。So just so we don't delete。ok。😊，That was。That was nice。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_317.png)

Apparently， there are more people who are zeroing the ball， right， So let's do like zero array。Yeah。

 just this one。A sound。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_319.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_320.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_321.png)

You know what， that's not exactly what I want。诶。You're like。Instead up just doing like this。嗯。

Theyre up doing like this。You should advertise your streams and Henry H Discord channel。

 That's a good idea。 fact I I'm going to write it down talk。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_323.png)

Po stream。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_325.png)

Hemade network this， I try get a project on Hemade network。But for some reason， they didn't approve。

Actually， they didn't disprove， they just ignored it。Were I supposed to have a lot of things to do。

 especially with the handmade conference， handmade Seattle going on in a couple months。

So they probably are pretty busy with that。 So yeah。

 but the idea was to get some like some sort of form there， but I'm can talking about this card。

 Thanks， Nice call there。 What I want to do is multiply this guy。By the player distance。

 So I don't think I have a distance。I'm going to do like a distance。Player。I can do the distance。

 Yeah， let's do like the player P。They are people。Or we can do something simpler than that to avoid。

Doing like a square root。They still like distance。And。Thiss is going to be the player visual PY？

Let's see。Let's say， it's the。包。Desired。TY。Minus。Let me。Camp this guy。

Making our print work with floatat。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_327.png)

What was a great call。In't do hard。Thanks for the stream， I watched God the best Butfogu game， Okay。

 have a nice game。😊。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_329.png)

🎼Thanks for dropping by man was nice talking to you。 Nice meeting you as well。😊，Okay。

 so it's like the opposite of point。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_331.png)

Or we could make just add this guy could make like。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_333.png)

Let just make like distance。来这。Make like 50 minus this guy。O。😊，And。Yeah。

 what's your schedule for streaming I I am I do like to stream on a。Like normal days of the week。

 around 8 pm Brazilian time。Maybe a little bit earlier。But I do Saturday morning。

 Brazilian time and oh Saturday afternoon and Sunday morning。

 but this game is really coming to a close I don't know what I'm going to do after that if you follow me on Twitter I do say when I'm going to stream and likeking a few hours off in advance Tmer' Daniel I was 8。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_335.png)

Yeah。Because it's really a flexible time。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_337.png)

That's a bit bad。 So I'm going to do。Like， let's take times。int1。F。Okay， thanks， no problem man。

 thanks for watching， let's do times 0。25 and that's also clamp this guy。That's kind of like。Camp。

Let's do0。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_339.png)

🎼Itそが00 one。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_341.png)

Well要。Not exactly what we wanted。That's not。Well， let's climb like。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_343.png)

Can't be too much， they don can play around the multiply。🎼0。🎼Go to up to发。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_345.png)

So this， what I'm going to do， maybe' going multiply this by half。Quarter。And then this can be。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_347.png)

感紧。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_349.png)

Okay。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_351.png)

That's better， I think。But also going to make this guy even a little bit smaller。

 And let's now play around with the sound。 It's going to be this guy。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_353.png)

Plus， the distance。Let's see。😊，St right。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_355.png)

Maybe I should make the。Well， this guy， we can do it like the set body。We don't need to。

You couldn't do the set volume on the player。Because。You couldn't do the set volume on the player。

Because the mouse is really a crazy like input device and we don't have like smooth coordinates。

 this guy pretty much have smooth coordinates so we can。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_357.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_358.png)

This multipliers maybe a bit too much。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_360.png)

没行。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_362.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_363.png)

And the distance should be a bit。も。Let me try just doing the business factor。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_365.png)

Just to see how it sounds。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_367.png)

Lets go back to 50， we don't see much of a change。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_369.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_370.png)

狐理。60。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_372.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_373.png)

I think I'm going to do this distance squared。If I square this guy。If I square this guy。I suppose。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_375.png)

I'm going to get like that。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_377.png)

And I can probably remove this guy。Cl。9920。I I'll probably have too many。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_379.png)

Yes。爱。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_381.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_382.png)

Okay， this is like exactly what we want。The other way around。Maybe Ta was too much that too。6 or 5。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_384.png)

Yeah， this is what we want。 I see。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_386.png)

啊。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_388.png)

I don't know， man， we're not quite there yet。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_390.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_391.png)

Let's just see the value。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_393.png)

Yeah， claming by5。Not a very good call， at least not。Well what did I do there？



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_395.png)

Okay。来 see。😊。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_397.png)

🎼So。Like we start off。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_399.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_400.png)

Try to pause the。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_402.png)

Like 6000 sounds like a decent number。That's just like 7，000。If we do 7，000。Minus this guy。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_404.png)

Let's see what kind of values is we have。Yeah。Start off with zero。But， I don't know。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_406.png)

That's not what I expected。 I expected it to be。Maybe you should actually take this cr route。

Not the square。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_408.png)

Let's see what values。看。And we were trying to print， I see what the number we were trying to print。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_410.png)

Yeah。A weird number。是。😊，O。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_412.png)

Let's try to look at their valuesties。8ight。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_414.png)

I don't know， let me just draw this out， maybe you guys can be also。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_416.png)

I want a scale that goes like。Let's say this is like zero then sn。

 I want it to be like two with three。4 or 5。Something like that。We have the distance。

 Let's say this guy is like 10。All thats do like。Yeah， 10。And a minus 40。 so the distance is 30。50。呃。

Yeah。Like if you were divided by 10， we got five， okay， but。If。The distance。Yeah， actually。

 it's the other way around should be zero， right。So if you do like 10 divide it by this guy。

 let's say you got。Yeah， it's got  point。2， okay。Okay， now if we， if we have， let's say。呃。-30。

-450 distance is 10。God one。But this is like a linear scale， and I want a linear scale。This is。

 I think it is just a squared one。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_418.png)

I know why the squared didn't work。Maybe it did work， but it was too large。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_420.png)

Yeah， maybe that was the case。Let's make that smaller。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_422.png)

And that's also。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_424.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_425.png)

I don't know。Maybe they'll be good enough。Why did it change。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_427.png)

Let' see我看下。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_429.png)

St one。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_431.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_432.png)

Yeah， I think they'll be they'll be good。 So let's go back to setting the volume to this guy。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_434.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_435.png)

Let's see if you got a weird。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_437.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_438.png)

嗯。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_440.png)

I。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_442.png)

Two don't like this。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_444.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_445.png)

Let's try one over this one。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_447.png)

Yeah。🎼感情。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_449.png)

Yeah。Okay， that is， that is a limit。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_451.png)

I think debug that。🎼Without a nice positive pitch， we've going to use it for once。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_453.png)

🎼呃。Why is that？

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_455.png)

381。🎼do。です。Okay， that didn't work。Nice， should for like a normal break。😊，Okay。哼。This guy。

Distance is 17。And that was 17 squared。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_457.png)

It's this number one over this。 Oh， it's just because it's super small。

I don't know what kind of kind of like that。 I think we got the what we wanted， this guy。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_459.png)

One over， maybe we don't even need to square。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_461.png)

The problem was getting the one over。 Yeah， I think that's it。 That's it。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_463.png)

Yes， perfect。Yeah， and I should probably clamp。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_465.png)

That。Let's clamp that to one。And now let's hear， I think it'll be a lot better。A lot。Matter。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_467.png)

Like Beth。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_469.png)

I really like that， I think。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_471.png)

I really like that。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_473.png)

Nice， now we can go back and add a little bit。Of the speed。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_475.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_476.png)

Yeah。Okay， I think that'll be a nice ball sound。 And I don't think it was a。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_478.png)

Bad one calling the whistle。Yeah， I kind of like that。I also going to try changing the pitch。来C好下。

With a three shot。WithThe three shots， we crash because the sound ist old。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_480.png)

Okay， because we probably。Let' see the three shots。Wherehy do we do the three shot？あ。

Is it not called the sweet shot， What is it called。'来电件事。It's called number of triple shots。

Trile shots。Sponship for shot。嗯。We got a pointer to a ball。Next， again， next available ball and zero。

 Yeah， so instead of just zero，re going to do the same thing。Going to do the plain sound。Tim。

Itals ball sound， you can zero that。And we zero the ball and' gonna go ball sound equal still。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_482.png)

Nice。Let's see。🎼The ship shut again。Surely have a cheat code。🎼For anything like。啊。啊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_484.png)

You gonna have a cheat coatat。We kind of have cheap codes already。If we press up。

I think it's ability could press down。Number of triple shots。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_486.png)

来吃。😊，Like。And you know what？

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_488.png)

Then I think will be pretty cool。啊。Whenever was set。We never set the volume for the ball。

I'm thinking。If the ball。D p。Thiss going to be pretty cool thing with the ball Dp。Do why。

It's positive， so if it's going up。We probably don't need to do， we probably set the ball。So。Target。

Target to broaden。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_490.png)

Else we give this， I think that'll be cool。They'll have more of a fireworks effect。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_492.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_493.png)

And I may even just do the same thing and just set the。Ding。啊。好。T that。先说你。就0咯。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_495.png)

ABC。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_497.png)

Pretty cool， I'm going to set the volume to like a very low number。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_499.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_500.png)

Nice， but let's。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_502.png)

You put like this guy。Strong。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_504.png)

See， that was， that was a super weird collision problem。 I don't know what happened， dude。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_506.png)

Let's。Also check this mark。Oh no it was weird。Okay， but I kind of like the sound。

 but I think I want to say that。Like a ball。P点Y。I think I need to say that。Like。A little bit， maybe。

Like。When I change the direction。Yeah， I think we're going to do like the。

Not going to do the sound of an issue like。The tribe is what do you think？But。But I'm going to set。

I had a like us。Whats that fading speed？Let's at a fade speed。啊。哦。I don't。Yeah。Oh。W。This guy。😊。

Fading speed。That's take10。Just a little bit of fading。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_508.png)

But not too much。Not instantaneous。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_510.png)

Yeah， this is getting， this is getting cool， I think I still like seven。And the distance factor。

Can be a little bit。Stronger， like 2。5 less。Let's go up to 1。5。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_512.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_513.png)

And let's also change the pitch because I don't know we are in for it， right？



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_515.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_516.png)

Yeah， perfect now I don't think I need to clamp necessarily。嗯。I don't know， but I am going to set。

The speed。What'squi。To， like a。Distance factor。Let's clamp that to like。in3 F。Maybe yeah， that's 3。

3 yeah。Thisst manufactured。To inspect is not a function。Yeah啊。😊，Os。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_518.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_519.png)

That was a weird。But I will get somewhere。Let's see player。Movement sound。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_521.png)

Let me just get the bulb movement sound。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_523.png)

That's weird， I thought by clamping that。To one。I wouldn't get。That high pitched sound。スピ？This guy。

Let me print it。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_525.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_526.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_527.png)

That's weird if I， I think just the relative。Perception of it， if I do like one one。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_529.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_530.png)

对啊。😊，So maybe this guy I'm not going to do the inverted。Maybey I Joe's going to straight up to that。

I do have to multiply that。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_532.png)

Byy something。I'm not sure what。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_534.png)

I'm going to do the 50 minus。对。Because this guy a need like？Okay's， so 50 minus this guy。

That you give me like zero if you are here。And a lawn。If we down here。Yeah。

 and then I'm going to clamp that。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_536.png)

To some。Let's see maybe you should have a smoother。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_538.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_539.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_540.png)

あ。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_542.png)

Well was just one。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_544.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_545.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_546.png)

Maybe I misinterpreted numbers。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_548.png)

Because I thought was subtracting 50。I need to be like zero winnings up in the top。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_550.png)

If I do。Let'd say 70 minus this guy。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_552.png)

Let see what numbers we got。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_554.png)

Yeah， okay。And then we defied that nicely。呢个。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_556.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_557.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_558.png)

That's perfect。Okay， this is what we want。Then we clamp that。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_560.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_561.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_562.png)

Yeah。😊，Maybe。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_564.png)

。int3。To much。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_566.png)

For all that was like one of my best runs， Joe， just because I said that I。🎼一。🎼ですか。Oh my God。

 just tried to complete so I get the high score。I'm going to try to move that。🎼Like个 art。

Conutciously soed。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_568.png)

🎼We do have to turn the volume to zero。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_570.png)

Whenever we load the menu。Which is like。Change。Change game mode。If you go to the menu。

Would you like for ball？Bs。Ie just plus。Both I。That sound。s do like set volume。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_572.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_573.png)

Pfect。Perfect， we are coming along really nicely can write an AI to play this game。Well。

Depends on what you mean by Ryan and I to play this game。You probably do a night to play this game。

 but if we're talking about those neural network things， I have never done that。But I don't know。

 a lot of people have done that， so it's not impossible。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_575.png)

So I could， but。It's not really my thing。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_577.png)

🎼But if you mean like， yeah， a canural network kind of AI。

More generic want to play like super optimizeized， but we could write a pretty stupid game AI to do what we're doing。

バラ。What's the point man， the games for people to have fun， not AIs to have fun。

 I thought it would be fun yeah。🎼Well， it's pretty cool to see the result， I'll give you that。😊。

To see those videos where in the eye plays like perfectly。That's pretty awesome。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_579.png)

I think the volume' is a bit too much。呃。嗯。So I'm just going to multiply that。By 75。High thought。

 Yeah， the results pretty cool， yeah。😊。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_581.png)

Let's see。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_583.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_584.png)

Oh， you know what？呃。Cole thanks。The ball。Only one ball now has the sound。

 which is the ball that can hits you， so I'm going to do like just for the one ball。

Those fading effects are nice， thanks。 Yeah， we have been a。Improving the effects a lot lately。

 we get a lot of particle systems now we're doing audio effects and I'm really happy with that it's turning out。

😊，Well， I know， I'm not going to optimize this later， but I am going to comment。

Like we only actually。Made sound for the ball。 See。Because。Well， it not's not true， it's not true。

Butら。あ。That's not true， however。Do ball sound， however。

 let's add a little bit more sound for the ball。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_586.png)

I forgot it keep as the default ones。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_588.png)

My4 colorder bindings are just the default ones。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_590.png)

🎼I got used to them。 I think I can。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_592.png)

TPro enough， but let's do something a lot cooler when we do the triple shot in terms of sound。

 spawn triple shot ball。Let's do like。呃。I want to try it from them。 I really liked it。

 You seem very productive。 Thanks。 Yeah， I， I really liked it。 I think。😊。

It's really easy to get started。 I think that's important。 And then if you you go all crazy。

 you can get the customization layer from from Ho whichs like 12 bucks and then you can。

You can try to be even more productive， but the way I use the default ones。It's pretty。Pretty nice。

 I think。In the default。To pull short balls， I'm going to do something like this。

 I'm going to play the sound。With variation。Which is the。Fireworks sound。And thats at like 0。5。

Or you're going to add like a couple of times。YeahI're going to do it like this。

When I spawn the ball， but when I also destroy the ball， like DP。Was that ball？Let's try it。On thePI。

If we destroy the ball， press the ball and。Yeah。I am also going to play that sound。

Just for extra fireworks goodness， and we can add even through more stuff。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_594.png)

And we clip there with the audio。し。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_596.png)

I am kind of inclined because I really liked that sound effect。

To add even when the blocks get destroyed。There's a little。Okay。Detroy。When the blocks get destroyed。

Let's try。Let's try I that sound as well。So we add。I'd say we play a lot of sounds。

Let's play this guy。 but let's， let's set like。That's， it's like the fireworks。I works。

And let's set it。Seets。Let's set its volume。To be whatever the target volume is。in-2。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_598.png)

🎼Are your students are you working， I am working。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_600.png)

Let's decrease even more。I I was a student like a couple years ago， but I actually quit college， so。

I wasn't a very good student， I suppose。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_602.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_603.png)

Okay， kind of like that。' going I track up， oh there is a mosquito here and it's kind of annoying。

The variation is 0。5， let's make it like 0。3 so it goes from like。7。

And then we're going to subtract points。Yeah。Let do like。Think about no variation actually， yeah。

 let's do no variation。Isplay sound。Oh， let's do a little variation。 Okay。

 let's do the plate time variation 1。Then we'll go into minus8， I say minus7。

And then I'm also going to change the pitch。Which is a speed multiplier。I'm going to increase that。

To be like。Plus。This point。So we got like a call and response kind of effect。Thanks for the source。

 by the way， no problem man， if you have any question about the source。啊。It look buys。

There's something called being multipl。I'm not sure what。Let's see。Well。

Ball speed I think everything is called speed mode Oh， it' the ball speed mode supplier。Yeah。Oh。

 this is gonna。 I's call a multi blur。It to apply it。Okay， no more typos around。

I love what you're doing here。 More people who need to realize it' like to reality really。

 really write game code and a bunch of eight guide tracks。 also I a lot of case motor practice。😊。

Thanks， man'am， awesome。呃。I really like。第二。Your comment。 Thanks。 Yeah， I mean。

 I learned a lot from Casey with Ham made hero。 I mean。

 I pretty much learned how to program from him。😊，I'm going to straight up say that。I。

 I programmed before， and I really got into programming， and I really studied through Hemade heroro。

 So yeah， a lot of stuff kind of was consumed， which is great because he's。

 I think he's the best programmer I've ever seen， not that I've seen a lot of good programmers。

 but he's the best one。😊，And yeah， and it's， it's a lot of fun。

 I think that's what people need to take from this stream， I think most， mostly it's just awesome。

 even if we have like hard things to do， which we did like a couple of stream ago， was pretty hard。😊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_605.png)

It's， it's all part of the process to get the game going。 And it's not really that work。

 We've been doing like this for like 30 hours， I think。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_607.png)

For all these episodes。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_609.png)

And the big difference between hey made a hero in this game。It's because I wanted to be。

I wanted to release the game quicker because Casey did all sorts of crazyaz stuff with the engine right。

 3D and awesome lighting， things like that not only kind not kind not do that yet。

 but I wanted to be quicker just so people could get the idea of like making a game from scratch publishing it kind of get started and then if you want to do like how complicated games。

 he made a hero is the go to no no question about that。Yeah。

 there's a spell story thanks and the thing is。😊，About the stories that I released a game for the PS4 in 2017。

 and you guys can check it out。 it's called Iosis huntt。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_611.png)

It's on steamam and on PS4。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_613.png)

And I was the main developer， know I had a couple of people helping me out throughout the process。

But。I was pretty much， pretty much my project when I started， I started out by myself。

 and in actually in the YouTube pitch channel it was pretty funny。 You can see the whole process。

 So I started out by myself。 So this is a couple the couple models I did then I like， oh。

 now I can move the character in unreal。 look at how cool this is in that now I did the shooting system。

😊，Now， can I shoot。Some enemies。All the way to like this point， which I was just by myself again。

But I had a little bit more of a game at this point。So but I was like， okay。

 maybe I should really get more people involved， so we are starting to go so a lot of people who could model and animate do a better job at me。

In terms of like concept art， things like that。 And we did。This game， so we kept improving。

 kept improving， and this is the launch trailer on the PlayStation channel。 so that's pretty cool。

 is it not？Is it a real unity， that was a real engine， so that's the tricky thing。When来呀。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_615.png)

When I released the game， I pretty much only programmed using blueprints。

So I didn't know what the heck I was doing， but to get the game released on PS4 I did had to go to the C plus plus things and integrate with F mod to integrate with SDKs and then upgrade the unreal version and then get the engine compiling。

 And that was crazy。 And I really felt that I wasn't prepared for that certainly So I really。

 after I release， But I managed to release right that was the important part。 So after I did release。

 I was like， okay， let me take a step back。 and let me really learn about programming。

 Let me really get。😊，This whole thing So that's where I found out about Casey and it's also a cool story about how I found out I got about him made here。

 I was watching a Jonathan blow live stream。About the shadow maps and it was like a seven and a half hour live stream。

And I was watching W of him some set dressing on like one of the levels for the game。And yeah。

 this level， and I was just watching， casually watching doing the set dressing。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_617.png)

And then。Some he said， oh， this is not case I'm not going to explain the whole thing otherwise I'm gonna be like 400 episodes in。

 I was like okay， who's Casey then I looked at the chat and then I managed to find out aboutham hero right and that tree got deleted off Twitch and YouTube so you can't watch that shadowow map stream again that seven and a half hours shadow Ma stream I can't watch that again。

Luckily I watched like a couple days after he he twitched he streamed right and so I managed to learn about Casey so that was pretty cool then after released the game I learned all about programming I really fell in love with it actually programming you know。

 that's pretty cool to understand Win PI did you read Charles Betson book or Winsper no， I didn't。

U I really pretty much got everything from Hemade heroro in。

The way he taught about how I should learn more about the Win API。

 that's how I learned the rest of it。 So yeah， so this first like few days are all win API stuff。

And then I really really got the hang of searching， you know MSdN stuff and watching。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_619.png)

More specific things like when I did the web server in C。

 I learned about sockets through the MSDN and watched a couple of YouTube videos。

So I'm not a big fan of programming books。Although I did read Game major architectureure two times。

 and I think it was definitely worth it。That was pretty cool。

 but I don't know the page scene is kind of different because when I watch a video。

 I can watch pretty， I watch like a little bit faster。

Just to get most out of the content and sometimes that's low down when you guys do a more complicated thing。

So yeah， so that's that's my big commercial game I released 2017。 So the year。

 So I spent one year after I released the game just really studying programs like watching himm the hero and programming all day long for like a whole year。

😊，And after that， I start doing like some startup stuff。But that's pretty cool。Okay。

I think we are getting to an end of what we wanted to do。 I mean， still have to do a lot of stuff。

 but let's try to get that。It'll be more under control， but I am enjoying。

The way what we manage to let' do。What we managed to do with the audio。Motive blur。

Multiplies the member block。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_621.png)

Okay， I also type both。开始。😊，Awesome， set up triangle pattern。后面。Let me cheat and get a couple ofra。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_623.png)

You know what？I also， I think I also want。That are。ACo have fun。 Okay， thanks， man'。

 was awesome talking to you。 Thanks for dropping by。😊，啊。Let me see the play sound variation。

The fireworks sound， no， not this one。This one。I think I can like。Do a little bit louder。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_625.png)

I think I'm also going to play this kind of a firework sound。Whenever we。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_627.png)

Hit like the walls。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_629.png)

Yeah。So let's do the spring sound。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_631.png)

In no the re sound， I may just take that out maybe。自う。The fireworks are so cool， the sound effect。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_633.png)

And I think one point。5。Maybe a bit too much still， for the。Oh， yeah， point。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_635.png)

For the ball， let's hear that。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_637.png)

Yeah。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_639.png)

Oh， dude took that out。 Oh God， we have to remember when we take our things to test。

 have to remember to put them back in。A movement。Oh my god， let's do the big movement sound。

I set the volume， what。This guy。So。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_641.png)

Dude。That's what we want， right？I think that's perfect， that's pretty much exactly what we want。Oh。

 we also't add the pickup sounds。Do look at thoseホワす。Oh， that really savedd me。

Doude that sound so cool？The very high pitched explosion。I think this is really us oh。

 I start to look at chat。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_643.png)

I really， really like the way this is turning out。 I think I'm just going to add the power up and power down。

😊，S effects。Oh， then we can do this。 This would be pretty cool。

This would be like an ancient optimization。So I'm going to drop that in this。Awesome。好的。Pause man。

As well， implement on， okay， let's do the power。I see the power up。Sound and a power down sound。ok。

Okay， so low wave。So we have the。Power up。像。😊，And a power down。给。😊，Let me see the power up。

I don't know if that's gonna fit too well， honestly。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_645.png)

And I think both of them will crash again。So we may play around with a pitch little bit here unable to just do it。

So the power up should be a little bit happier。 This game is a happy game。

 Don't you guys see the happy vibes all around the game。😊，As you're not snackping。See。

 I think I'm going to run a equalizer。Because I think there's a pretty。Yeah。

 see how there's a huge base sound， which after Z number was in the shadow matting， no。

 the shadow ma was Ja glow stream。We haven't done Oh， you're talking about a handmade hero。 Yeah。

 the shadow Ma stream was from Jonathan below， not even me， not even Hemade hero。

 I I don't know if Hammade heroro has a shadow mapping episode。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_647.png)

I think it is justdirectly animationmination Let's do like shadow。Oh。

 he does have a shadow mapping envelope introduction to lighting， oh it explains about。出咗咩啊。Yeah。

s not， he doesn't have a flip， but he does have the explanation。I want to link it to this， oh。

 I'm not sure if this will go all the way， now it's just hand here slash watch。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_649.png)

Yeah， this is episode 96， where he explains about shadow Maing。

 but the full episode that I watched was Jonathanna B's video。

Where he implementeded the shuttle map from scratch， that was awesome。

The video was related for some reason。Yeah。😊，That was really a bummer， but I got to know Casey， okay。

 thanks， no problem， man。Okay， so let's equalize this guy， so see how basic that sounds。Oh。

 you guys can't hear the South Aton， but let me just。Just show guys here。See。

 there's I don't like that sounds too basic， let's just equalize that down。No。I。

 I may even remove the first。Yeah， and then I also am going to bit shift this guy just a little bit。

Okay， that's a little bit better， maybe not the best pickup sign in the world。Yeah。

 but I think I'll do Im call that pickup power up。Sounds too robotic， I think。Pre of sound。Steo。

A wavea time selection， okay。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_651.png)

So we'll do the par up sound。That listen to the part of down one。Okay。

 the power down is kind of okay。But I am going to。I'm going to make it up。And want believe。Oh。

 not the pan。Okay。King going do the power down sound。 that was， that was a little bit better。

 So yeah。Per down。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_653.png)

Now， let's。Take a listen。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_655.png)

🎼To that。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_657.png)

Oh啊。Of course， we didn't implement it。呵。Well。Let's do， like， a。Power blood。

I think it's just here in the player as。P玩。Block。Yeah， if you're gl with a player。啊。

Let's do play sound。Power。Power。啊。Sound false or power down， let's see。We could do like a quick test。

 like if。Power。Kind， if the kind is last then， or you go to the last。P blast， power。

Up last and replace sound power up。Ban will play。A down。是的。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_659.png)

对。Good hearing。Dude， that was awesome。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_661.png)

Okay。Yeah， I did hear， but that was。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_663.png)

Yeah， that was。Let's make like just for testing all the lock。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_665.png)

你来不。对多。Let's make everyone spawn a。Ourer black。Let's make everyone's spa power down。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_667.png)

Power slow player lets make everyone slow the player down。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_669.png)

Yeah。I don't know why Alice。We。Okay。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_671.png)

Let's try。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_673.png)

That was way better。Now let's try getting the power up。

Can I control Z all the way back to the power up？I think it can。Okay。ok 啊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_675.png)

Let's see。 what we have。Were also。We make like the power。

The triple shot I really liked the salad vegetable triple shot。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_677.png)

🎼It was a。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_679.png)

Okay， cool， let's say I think we are done in terms of sounds。诶。你 see。😊，We did the bricks comet。

 oh oh， you should do the comet。So。Le。Oh， maybe we should just。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_681.png)

🎼快要他。How we have a limited number of products。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_683.png)

🎼いや。Let's add the comment sound。 The way I did this， I had two sounds。 I have the comment begin。

And the comment loop。I think。Thatll just work， so in the audio。Oh， no， and the levels。

We have just some worry。We have the comment， let's see。 we have the。Oh。

We have called that maybe Bay sound。Call that comment sound。

And maybe everyone's going to have a come sound。Yeah， I mean， it's kind of stupid。

But let's just do that like first version。呃。So check see。

And the real breaks sound effect we did that reward player with power when you get an score maybe because。

When do we do like the。We're all I didn' know。Let's just comment， like a。

Let me just see where I type bulb I think。Think you comment of that。好没啊。As you like。Do I need。2。

Have a ball to our commentt。And the normal sound for every。我对。I don't know， probably not。

 but let's just implement that。So we have sound。Let's do a commentt。Again in comments loop。不是。Wait。

Could you comment。天。😊，Comect you。Okay， I think just comment again。 Let's see。Yeah， and comment。Okay。

 these are， I already processed them。 so not going to need to do reprocessing so。Yeah。

 for every ball， same thing gonna do。I'm going to play the comet。Loop。And I'm going to do it like。

And I think you can have like a little bit more fad for this。ok。Now。

Lets see whenever I draw the particles， which is like。啊。Here。Yeah for every ball。Yeah。😊，Oh。

 this is for every Travis Po。I'm just going to。Do this。Here。If we are commentt。She is going to。Yeah。

 whatever。Set target volume。To one， maybe。And else。That sorry。Yeah。Sound。

And whenever we get the power up， I say comment tea。This point。Let's do the play sound。

I should it play sound。Play sound comment。They can。O。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_685.png)

Now， let's see what we have。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_687.png)

嗯。Yeah， well， same thing。We can't whenever we are。Did you like a ball。0。We can't do。Sound。

So I'm starting to think that maybe I should have like a。Smarmalter way。ToDo that。But I don't know。

 it's not a。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_689.png)

爱奇。😊。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_691.png)

结数。That was really problematic， for some reason。Well， something that smells really nice here。

I don't know what。Com路。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_693.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_694.png)

Maybe I just don't have a。Enough sound。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_696.png)

I can just here again with the problem。We heard the ball。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_698.png)

P the ball pretty loudly。Would you like。connect is less than。Big sound。Yeah。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_700.png)

And we don't hear the loop。So this is all busted。I feel like。

 let's see where we got the comment though， so come again， come in。We set them。Here。

Then set the come sound to the place sound loop。But we set the volume to zero。Okay。で。

It's kind of wrong。But I'm。That's。Okay， now if we got to comment， this is working。呃。

If we have a comment。We set that volume to0 to1， the charity volume。 If you don't set it0。

That looks correct。And then right。I know。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_702.png)

Everything looks okay from here。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_704.png)

Yeah， definitely hear。I think some pointer is being set incorrect me just。Now set these guys。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_706.png)

Yeah。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_708.png)

嗯。好 well。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_710.png)

Just pause the game。Let can check out the plain sound stuff。So。Let's see our playing sounds。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_712.png)

Well， it will be kind of hard to see honestly， so we are full。Yeah。诶。Okay， this is the ball sound。

 is the first one。Comment loop。They got ball sound and a comment loop， so these are the first ones。

Yeah， forest field。Sound。I've got another comment loop。Ball sound。Comd loop。A ball of sound。看来都。

I think that was too much。Oh， sound。And you come a loop。Yeah。系。

So I'm pretty sure this was not the problem。And I'm pretty sure the problem is when we spawn these guys。

Right here。We're doing that supposedly just three times。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_714.png)

I you like comment loop。Yeah。Put a break point there。The game。As。Here。Yeah。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_716.png)

So in fact。Are a b sounds？Gameplay music， okay？A man music。AThe sign， which is a player guy。

Loaded forest field。 That's perfect。Okay， now。W should I like one guy and then another guy。

 then I do two more and then two more。Perfect， now we should exit the loop。

 why we're not exiting the loop， how many balls do we have？I have 16 balls。Oh， because。Yeah。

 we have 16 balls。Because we may have。Several。Triple shots at once。Sorry， know what？

I think I'm going to do this now。啊。That should have comments。This guy。😊。

And we're going to do this guy just for the first one。Maybe I'm going to do this for the first three。

ok。And。And I have to assert that's not going to crash。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_718.png)

Okay， so the first three may have these tab， the other ones。So just in fact。Anyway。

I am going to increase this guy。Because。🎼Maybe maybe 16。Okay， oh did I crash？Yeah， I did。 Let's see。

Set。Yeah。When I go to the menu， set game mode。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_720.png)

You know what， just to be quicker about this？In the levels。I'm just going to change the name。

And just going to go everywhere I use these guys now it can be an also。This guy doesn't matter。Yeah。

Oh， this is the。I should also do like come sound。So I suppose there were three places we were using。

Okay， now。When we start the level。想 thing。啊。Sa飞。Here， so。Do like。For all sound， we do this。And also。

 if。我看一下。Okay， so this one's the first guy。Yeah， and。We should play around with this as well。

 So this will only happen if we have。A ball sound。Okay。And this should only also happen if we have。

Sa football comment sound。Good， perfect。 Now， let's go back and name these guys。To where they work。

して个。好吧。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_722.png)

I may have to get some water I ran out of water now。Stre is going nice， this one just keep going。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_724.png)

Yeah， this is way too loud。Let me just open a reaper here。Unless。Should the comment begin。哦，系。

I'm not sure how to snap to these guys。I'm after to Google a。And in fact。

 I'm super slow for some reason。Maybe I should just get like the timing from here and Is do that。Oh。

0。 Yeah， nice。没有。It's not shift out or。Let's just try to Google search like creepaper。Snap。To。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_726.png)

呃。What。Reaper。How was useless。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_728.png)

Well， you know what？

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_730.png)

I'm just going to do that。By hand。S me。Yes your I。あ。So。This guy going to set the volume。

It it' was just a chart。 So on that sound。Just this guy， Yeah， oh pretty easy。

And also when we sat like the comment。Start。啊。见。Let's also do like。

And reason my keyboard changed to Portuguese， I know this would happen eventually because there's a weird Windows shortcut that sometimes I press and makes the apple。

I'm not sure。Which shortcut is that？Sound。Set volume。Do we do03， let's try  point4。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_732.png)

With this guy。I really like that。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_734.png)

I really liked it。 I think we are good to go in terms of sounds。Let me just go back。And remove， like。

The level is do the block block。Ting lets remove this guy。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_736.png)

Let's just play for a game。It tries plentyium bunch。I think everything is nice。

Although when we had like super comments。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_738.png)

Let me also。最后再。For now。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_740.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_741.png)

Okay，Yeah， not shutting down when we destroy。Then we destroy like the。Bad destroy that。

All destroyed on Xia。When we destroy the block， the ball， we should also。Set like the set volume。哦。

电歌。Sound。We set that volume to  zero。And if the ball climate it sound。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_743.png)

He said that。Okay。And I think we're going to have to optimize our particle Oh。

 this is the debu built， right， but we may have to optimize our particle。Ginery。

Which is a rotate rectangle box。Even though it's a pretty small part of cream。

 but I guess it happens a lot。🎼Oh。You haven't got a single triple shot， I think it' be cheat。

Just that you shut。When never brain got it。Well。せの。All worries my look。

 I think you'm going to change the random。🎼Agoism in the。🎼To respond。

Because I think it's wrong because yeah， it was using our own way。

 which is kind of a hard coded way before we had a random tape I don't know。给。

I think that was perfect。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_745.png)

Perfect， let me just quickly change the。The wall。Spawn。Yeah we were yeah。

 we were only getting the random choice now。It's correct。 If the y is less than or equal to one。

This is correct。Yeah。I don't know， so let me just go back and see if there's any sound that we want to add that we didn't add or for some reason。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_747.png)

Remo it。7。Let's go back， Okay， let's see some things。Brick， we did that， come begin， come in。

 come loop。Fiworks， for us who came over， hit， did all those lose life。Yeah。Oh sad， well。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_749.png)

This old sound， I think I'm going to add a certain case like。Sound。Like， old sound。看。

Which is so weird。Name old sounds supposed to be like old school sound。I suppose， so。All the sound。

Right now， I think I'm just going to add that sound。On our space invaders game mode。Space。

 I think just in do。Yeah。So， whenever。Remo the guys。Yeah。😊，To play sound。李有强。那事。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_751.png)

First of all。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_753.png)

威脸的玩意。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_755.png)

And I may actually speed up the sound。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_757.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_758.png)

Yeah， I am going to speed up the sound in the space。Levels， let's see。Yeah。

 we have like movement team， moving target， moving down。 Let's do like。Number of changes。

Every time you change。Like in the end， let's see this guy。Let's do， like， level state。Number。好。

Changes。Plus， plus。And then here we're going to set the pitch， so sound。S multiplier。

It's going to be like。Let's say one。Minus the number of changes。Divided by 20。Oh。

 but actually we should increase it's going to be one plus。Number of changes。Level state。Leal state。

谁得写。Okay。Number。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_760.png)

Okay。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_762.png)

Awesome， but it's going really fast。I think。But this is going to be awesome， I think。诶 maybe。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_764.png)

By 200。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_766.png)

And in fact， I'm going to maybe like。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_768.png)

。int3。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_770.png)

啊。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_772.png)

By there I just cheating。天是不雷。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_774.png)

And this is kind of good。 I am also。Going to decrease the movement target。Just a bit。Try， we see。

 how much is that。It's 1。25。Let me。Let me decrease that， like。Just so it gets a little bit faster。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_776.png)

But not too much though because it's already kind of hard。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_778.png)

Okay。We crashed。At the sample plus one。Which sound is this？This is a fireworks sound。

I thought fireworks were a mono。And it is mono。Yeah， okay， so it's just sample。And a simple。Plus，2。

You see how many samples we have。66。Tst。Aent validation reading。Yeah， okay， we are way overboard。

What's the position， position 0。后期。Well， I guess you found one problem。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_780.png)

Let me see which frame you crashed。Nothing seems particularly wrong。Accept。啊。On our。Play sound。

With variation， we do like one minus variation。And one plus variation。But in the level。

 we should also do like。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_782.png)

Oh， the position is0。 Okay， now I， I was confused for it。 It's no problem。 The position being0。

I was super confused。So。Position is 0。So this guy should have been zero， then we got zero。-0。

Times 12 be 0。Next should be one。 Okay， maybe。Yeah， I don't know what。For us to get such a weird。

 get it fracs， not zero。This guy didn't become zero， but now。That's weird。 Let's see。

So the position must have been zero at this point。But guessing 0。That's a super weird bug。

I have no idea what happened。Our sample is a giant number and our next sample is that number plus two。

But our position is 0。And we couldn't have changed the position。In this time。I have no idea。

And this is an int， it's not a rapping problem。The f was this guy。I really don't know。Hey， Rocky。

 how are you doing。We got to a great point in terms of sound。But we came across a very weird bug man。

See if you can help me out here。We crashed here。At this line。Because we tried getting the sample 73。

000 and we don't have 73，000 samples。Now， the question is， why did we try to get 7 3，000 samples？If。

😊，Because the sample like this， the sample is the position。I'm good at you， I'm great， I'm great。

The position is 0。Casting zero to n should be zero， but for some reason， this guy got to 73，000。

Then they got the position minus this guy。 So the position wasn't  zero at this point。

 That's for sure。 something changed。De position。What could have changed the position between the here and here？

That makes no sense at all。We don't change the position， Oh。

 maybe another thread changes the position。But nobody touches the position。We may change， well。

 this is like the fireworks。嗯。We may have changed the volume I think。Yeah。😊，Okay， yeah。

 I think this is a threading problem。Man， thanks for the tips last time I march such from him。

 It is just amazing。 Do， that's awesome to hear。 I really， really enjoyed those stories as well。

 Those was was what got me started， you know。😊，Into programming really for real， yeah。

You know what I think I'm going to do， I think I'm just going to。

Think Im just going to cheat my way around here。Or maybe I。I know。Yeah。

 I don't know what the best thing。 I mean， I could。

I could make these guys more thread safe I'm going to。Cheat my way around for now。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_784.png)

啊。Then I'm probably going to make a note for me in the future。Like。嗯你。The audio。Safer。哎。We got。

A rare case。Of the game。全一经。The sound。Uデ？第。Sound position。And。Untentionally。Yeah。

And then here in the audio。All I'm going to do is just make sure that the sample。Is proper。Like。

Then we' going do a plan。So the first sample was zero and the last sample was going to be sound。

Sound。あ。Sample count。Minus。This guy。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_786.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_787.png)

Dude， listen to those shouts man。The games starting to be awesome。I was playing with GTB those days。

 it is fun， but I guess。We liked you and they got Ramy here or you can use it versus Pre Studio GI versus yeah man。

 come on， I mean。呃。A coie debugger is hard enough to use。

So I wouldn't imagine doing a tax based to bugger， I don't know。🎼Yeah， it should really stick to。

 to bad these week， in fact。Apparently， you haven't used molecular Vi Studio。

 so I would recommend because that's something I want to do。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_789.png)

I want to change to remedy， remedy。B g b。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_791.png)

Rey did be， I think。Remedy。弟弟。Re。I highly suggest take look at this debuger。

Hlo because is I love the sound effects。 Yeah， the sound effects。 I really turn turn out its nice。😊。

Remember BG， I suggest take a look at this， I really want to take a look at that as， but you know。

 I'm a little bit enerished in visual art studio。And it's looking pretty nice， I think。

 and it's great and fast， easy to use just debuer if you don't have to worry about having tons of features。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_793.png)

Yeah， let's see if there's anything we're missing， but all hit。We're not going to add that sound。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_795.png)

Maybe that could be the power up sound。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_797.png)

Oh， maybe oh， that should be the interface sound ha ha。😊，Let's do that。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_799.png)

Interface sound， nice。😊，Because I didn't think about interface sound when I I got them。So I was。

 okay， maybe you're doing it next time， but interface sound。Awesome。😊，Interface how。

 So whenever we change in the menu， whenever we change。Looks pretty cool too yeah。

 I think it looks pretty cool I saw the guy talking about this one and read it。😊，Nice。

Reddit is a lot of good place for programming stuff， I think Im enjoy some of this up there。

Let's say， old hot。It goes hot。No hot。 If old heart。It's even from hot。Going to play sound。eat。对下。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_801.png)

Header was no point。One more time。Yeah， we have to run that through the。This guy。

Because it's a different。Seeverate。Turn the flight。I think I'm going to make。Yeah。Also。

 I may smooth down in a little bit。Okay。IThink it's better。

 do you think it's possible to apply solid principles in C or this is a more U thing？

What do it mean by solid principles， exactly， I'm not sure what you mean。Interface。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_803.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_804.png)

Dude！

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_806.png)

The game is starting to become awesome。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_808.png)

Really awesome。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_810.png)

Really awesome， I think， let's see if there's any other sounds or forgot。Lose life。

We added old sound， we added play a wall。That's add display Ro sound。

 I reading a book called clean Code and often。In the book， the Southern Pri are referred。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_812.png)

Yeah， I'm sorry I haven't heard of it， so I'm not sure what it means exactly。But。

You can probably apply most principles in C first， I mean， not like ored principles。But。

I kind of try to make like a more。Free kind of a structure in small games。

Because I learned how to structure projects like this。

 so if I try to be too structured on these kind of projects。I end up not exploring in。

Knowing how how to structure myself。But in big projects， no， these guides usually help a lot。Hi。

 I just came here and I wonder if you're using SDL2 for import wave。 No， the wavy import， I wrote it。

 I wrote it like myself。 I didn't roll that on stream because I already had that。

 and I don't didn't see a point in rewriting that on stream。😊，But it's a pretty simple wave importer。

See， I wave， I import like PCM 16 bits， one or two channels， and then I inter leave them right left。

 right left。That's the way the game meet。So yes， just see make sure it's BCM。

 check out the sample rate。So， yeah。Just。Wing that from scratch， oh， this is like old stuff， I think。

It' for adding。It leave it that but。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_814.png)

You can download and chat and play around the wavaving part yourself。

 you can just download the game source scholar HIO。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_816.png)

デデ点。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_818.png)

You can just download， I don't remember which day， let's see you can come here on the YouTube page。

And let's see。And let's see。I think it was first was the first audio date， so it was absolutely 11。

Amazing， I try to do that myself。 That's awesome。 It's not too hard。 There's a hand a hero。

 There's a。😊，Ibs absolutely don' where your files。IfBut you can also see my version， well。

 I didn't actually explain the way Fire button you can download the source code on episode 11。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_820.png)

This hard scope。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_822.png)

Yeah， that was pretty cool。 It's not， it's not too hard， but it's not easy。 It's not like。

It's a weird format， I think。Could have been simple。ok啊。Let's add the。

 I think that's the last sound I know。So have to get tired， but I do want to do something else today。

 which is pretty cool thing， so we're going to add to play a role。Let's do。Player wall。Sound。

Wall sound。And whenever we do， like player。Well coalition。来。想 later。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_824.png)

Sound。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_826.png)

Oh， my god。啊。Sorry， if。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_828.png)

That was too love for you guys as well， but that was too love for me。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_830.png)

嗯。Well， if the player keeps pushing the mouse， this is going to keep happening。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_832.png)

So。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_834.png)

I don't think I'm going to do this guy here。And。Maybe we we review the play movement code for the last time。

We can have that sound。I am going to add that in a third collision with a bottle。来讲。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_836.png)

就烦。But I think that's a cool sound to add in these cases。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_838.png)

I think I'm good， just going to add this sound。The player Dp player target。DP。

x is greater than I don't know。Let's strike，10。And let's print this guy。谁。O嗯。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_840.png)

Let's see what the value is。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_842.png)

🎼0。5。700。Yeah， un say if it's greater than  a thousand0。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_844.png)

If it's greater than 1 thousand。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_846.png)

Willll add。That small sound。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_848.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_849.png)

Pretty cool。 And now we'll be able to。We like when we finish the player， like。Review the size。

And the player wall condition。To that。So the。I had one frame rate。Okay， so yeah。Let's see what else？

Per down， power up， redirect， sign， spring， start game and whistle。

That means we have added all the sound effects that we wanted。At least for this first pass。

 maybe we're going to add more sounds， less sounds or whatever。That was， that was cool。🎼アみ。

🎼I think it's really， really cool。I'm just going to change a small thing。Like in the level， in the。

Destroyed。When we spawn like we other block particle。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_851.png)

I'm going to make its life a little bit。Bigger like。2。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_853.png)

Maybe too much too much。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_855.png)

Yeah， two is too much， but that's like 1。25， maybe。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_857.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_858.png)

🎼Things good。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_860.png)

Okay。But now that we finish the main audio files， what we want to do is this。

 this is gonna be pretty cool。 We want to make the player a listener in certain sounds。

 So we hear a statue。😊，Steo system， stereo system。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_862.png)

That's what we want like u， we want to hear the ball coming from this way like or u we want to hear like the blocks exploding differently。

And based on our position。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_864.png)

🎼笑。They certainly want that。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_866.png)

呃。I think I'm going to spend like half an hour trying to do that。Because I'm kind of tired。

 it's kind of 1130 already。And I like to program and I'm tired， but I really want to do this。

 so I'm going to push it a little bit further。But if I get stuck and if I don't manage to do this you。

I don't know。Fluid manner， I am going to maybe do that next next time， but if we managed do that。

 we can fix this plug last time。Next time， and then we can start doing the UI and at better levels that would be pretty cool then we can make like the hotel levels or 11 levels that we want to play around with。

啊。I have run out of water。So I asked like for a two minute break yeah， two minute break。

To get some water。Okay， two minute break， I got some water。

 maybe you guys's going to get some water too， and when we come back we're going to do the player。

 the listener so we hear a statue sound。Based on the player position to a certain sounds。

I think they'll be awesome， okay。Okay， see you guys in two minutes。Okay， the cup has been refilled。

 the brain has been reset， I think we are ready for a new feature in our game。

This kind of a engine feature。I don't know。But。I think that'll be pretty cool。Let's just a。

To be able to test the feature， let's do something like。Play a sound from a certain position。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_868.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_869.png)

Yeah。So the way I'm thinking is that maybe。Maybe the plain sound。Has a。Like source X。Pointer。

And if we do have a source X pointer。We then calculate， yeah， the pan。I think I'm going to do that。

I don't think that'll be too hard。Let's just test by creating。A sound。Let's， let's say like。

F 32 x equals 0。Then we can do like a draw wreck。Torrect。Then I'm going to do V2 x。0。

And then the the size。Will be， I don't know you by three。The the color is going to be red。🎼Okay。

 let's see if we got red rectangle。 we do。 And that's also do a。I'm going to add that as a global。

Game。Ggle test X。Es 0。And then whenever we do the play sound。As to a play。Sound。Playing sound。Sound。

Let's do a sign。What is it called。小衫。Let's do that。 And let's set it to looping。

 and let's do the test sound。A source， X。It's going to be the address。The test。Okay。😊，那找什来。

Visit time specify。X。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_871.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_872.png)

🎼Okay。Now let's try to make。That pan based on the player position。Now， in the audio。We'll do that。

 let's see。Do that once per frame。Not sure we should do it like once per sample。

I don't think we need to do that。I think one per frame is going to be precise。Yeah。

 we don't even update a player once per。So I'm going to do like if。Sound source X。

We're going to do a sound pan。She's going to be。The source X。Minus the player。Visual P dot X。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_874.png)

Let's see。If this guy is in a minus-10 and if the player is like zero。Should be。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_876.png)

This guy am minus this guy。ok。😊，But let's add， like， a point to1。Of a multiplier。

And I think that is just it。Player visual P。I don't know how I'm gonna。

I want to have access to this guy。7。Maybe I're just going to cheat pretty badly。従来？Player。也说。P。

 X pointer。Yeah。Well。Player。The usual Px pointer is going to be the player。Visual P。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_878.png)

This is a point。Okay。😊，Let's see， I'm going to turn you guys bottom down and mind because I don't know what's going to happen。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_880.png)

Okay apparently we are standard perfectly。Listen to that。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_882.png)

I don't think you are 100% pure though。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_884.png)

But， well。This is nice。はい啊。Let's do。 like， the。Player。Lets see the play sound。Let's。Turn。

The main music off。And let's do like the player movement sound。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_886.png)

Thats。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_888.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_889.png)

Yeah， whenever you get the transition。It's， I think it pretty much the same problem we had in the beginning。

 well， today's live stream is pretty big， right in the beginning of today's live stream。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_891.png)

And I think we going to fix that by just making that for sample and not per tick。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_893.png)

That's going to be great。Maybe we don't need to do like a full stereo。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_895.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_896.png)

I like that。So I think we're going to do this。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_898.png)

Same thing we did for the fall in the beginning of today's stream。And do it like here。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_900.png)

I think we were better， but I don't think we are 100%， though。Oh。

 it's because the player Dp is all crazy。So yeah。So I think we can keep that here。

AndBut I'm going to change the sound。To do the move towards。Move towards。soundund。

And I'm going to move toward this guy。At the speed of this case， let's say Dt。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_902.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_903.png)

I think we are perfect， Let me do remove the。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_905.png)

This plays sound a guy。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_907.png)

We are not perfect。嗯。Let me again trying to do me that。Sd。Onces for a sample。Then let's do like。玩。

Divided by。呃想 buffer prefer。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_909.png)

Samples per。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_911.png)

Perfect。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_913.png)

Now let's do that a little bit。Here。5。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_915.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_916.png)

This is perfect， perfect， perfect， I say。Now let's go back to the game how it was。

Get all these guys back。 and let's remove。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_918.png)

To draw our rack， let's remove this guy。Let's remove test sound。And， let's also remove。这钱。

So that's if you've got normal guy。Okay。Now， there are a few sounds that we're going to make that。

Source， so for the for the bow in a comet， I'm going to do that so。Ball sound。Source， x。

W to be the edge of balls。I dot P。Dot X。See， if that's it。Same thing for the comic sound。

Let's see if the ball is now stereo。It is。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_920.png)

Great， great， see how easy it is to use。😊，啊 man。I really like this。Awesome。

Let's keep going and let's keep going now what else？The ball， let's do the spring action。

It's pretty much everything lampse， let's do when the blocks get destroyed。Detried。嗯。Here。Let's set。

All these guys。This firework sound。嗯。But this's the thing。Some sounds。Like the block。🤢。

When that like log。Destroyed like all the e soundss。离箱。诶。

I technically can't set that to the block P because the block was destroyed。

But I don't think we care。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_922.png)

So I'm a kind of a bad person for doing this。But。Fireworks。So our sex。I这 the block。X。Okay， in to。

The others sound。Sound。And that's also red。香。Let's see。😊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_924.png)

Awesome， let's， let's do that to the spring。😊，诶。And the redirect， I's do like。

Maybe I should make a helper function。 See this is where。Deult defaultult arguments come into play。

Because the play， let's see。来。😊，This function， the play。S of variation。I think that can take。Pointer。

 yeah。佢系。Sound variation。 take a pointer。To a source。我们就搜。Source， x。Eals。

And let's just fix these guys。Fireworks。Same thing。And well， this guy has to do it by hand。

Do wall hit。Let's do。Left。A ring a leg。Well， we don't know if or have the piece of P do。Oh。

 but this pieces on a stack。D wall hit effects。I'm going to take a point or to a you too。Yeah。嗯。Okay。

 now。Same thing。This guy。And this guy。This is the， this is the spring。 Alright， This is the right。

Okay， process ball went D P down when the。When the ball gets destroyed， let's do the ball。He X。

ItFly triple shotballs。Well， the fireworks。Maybe this right neighbors。Okay。

 let me just make sure this fireworks， yes， it's when we spawn the ball。We should be the player p。

PlayerP。Block， destroyed。Yeah， this guy should be at the block P。嗯。Put down the wrong place。

Player collision with ball。Shouldn't care。 Shouldn't care。Oh， yeah， actually kind have sets as zero。

0。0。Yeah， and this is going to pass the address of the talk。I should pass。

The address of the arena right。诶 time。Think I'm going to pass this guy and a separate leg。Sound。

Source。And this guy's going to be a normal。Oh， sound source。Okay。

Now this guy is going to be this guy， going to pass the addresss of arena， right。And this guy。

It's going to be。The arena。来。😊，And the top one。Top one， I don't really care。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_926.png)

Okay， let's see how the game sounds。 I'm going to turn your volume a little bit up so you guys can make sure we have like headset or some sort of a stereo system so you can clearly see if you're in the right direction。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_928.png)

Okay， apparently we are inverted。That's weird。If we are less， then they're in a left。

Why did that sound ferted？

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_930.png)

Well。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_932.png)

Pretty sure that's for。 Let me try just changing to see what it sounds like。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_934.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_935.png)

Now， that sounds worth。I actually I don't think。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_937.png)

And I changed。Let's go to the levels in the do wall collision sound source。

Addressing a sound source to every guy。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_939.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_940.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_941.png)

It's kind of hard to hear。All that stuff。Go to a cheat。And like。I'm going to tag。Theload sound as。

Active。😊，And I all。I'm only going to set the spring。Too active。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_943.png)

And then I'm going to do on the audio。Like。And I was showing we had this。No， I think that's correct。

Yeah。😊，That sounds correct。I don't know what I was thinking。Okay。Let's put a little bit more。

Maybe the spring should be mono。And that's so unlucky with this guy。啊啊啊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_945.png)

Okay， so when we lose a life hours， I also want to reset。They also啊。The menu。嗯。That's。Call this like。

Set false。Sound。And in the levels。Re said。宝箱。Yeah， I think this is correct。 And whenever we are。

Every set like the。哦。0。Maybe actually should have it just like a reset ball call。Yeah， reset ball。

Every everys a life。We said。Fs。In this case。This is a start game。哦。That's it， so。Reset balls。

So for every ball， if we do have a sound。Go to set the volume。These guys。😊，That sounds receptful。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_947.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_948.png)

Okay。Let's play p。Oh， correct。Now zippers is slowughh。Should be almost done。

Go strong blocks and I still slow how much time Oh my God， how much time do I keep slow？



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_950.png)

Snow。Player tea。5 seconds。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_952.png)

That felt a lot longer than five seconds。🎼Let's do Space invades。Oh my god。

 I had so much cool partups。No all those are very bad power。Okay。Now， they are pretty fast already。

Oh， they''re fast now。啊哈哈。Wow。ううん。是是是是。Well， that was weird。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_954.png)

That was cool。But that's not playable too much。其实。😊，Well， let's fix that。Movement target。

Still of doing this。I'm going to decrease， like。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_956.png)

15% of this guy。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_958.png)

She've gotten。Less。Like a lot less。Like。需要。With this guy。I' going do like。Oh。

 because we are increasing the， No， we are decreasing。嗯。Minus。Okay。Minus。Yeah。

 but this was just too much。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_960.png)

But sounded that looks pretty wrong。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_962.png)

I don't know， man。Maybe we should just。Well。And a movement target。We should also like start that。

Pretty slowly now。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_964.png)

啊。Oh， crap。Okay，s what's more？Play a out。I love it how the world。Give us like a little push。

🎼Of the ball and I just like， reflects it。啊。Oh， that was really lucky。IThat was really unlucky。

I think this is going to be the hardest level of the game。

🎼Just because the sheer number of blocks and their size。And the time limit。I mean。

 I'm sorry if you're just were watching me play again。For a long time。

 like come on part of making a game is playing the game， right？Besides。The sounds are awesome。

Think we got to a great feel of the game。哦。🎼Okay。That's life。I think I made cheat。

🎼Just because I want to see the time。🎼They're starting to pick up speed。Yeah。

 it's going to be really hard。But I know the speed is okay for now， at least。It's just hard。

 that it's hard。🎼But its not like。Okay， last block。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_966.png)

Victory！Doude。I think the game is pretty much perfect， but in terms of like the bass。

We built the base， we built a lot of stuff。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_968.png)

Let's take this moment to appreciate what we've done。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_970.png)

Because we did a lot， I mean， you can just congratulate。😊，Can feel a little bit happy。 Good job。

 Yeah。 Thanks， Rachel。 I think now this is a moment just to feel a little bit happy。😊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_972.png)

Because I mean， how many we've done like 14 episode， this is the 14 episode。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_974.png)

And we did the listener。 And that's awesome。 We had so many cool stuff in the game。

 I think every cool stuff they wanted that we added。😊，And we still want to add more cool stuff。

 I mean， especially to make the acade game ideas， but I think we are in a great point to start focusing on 100% on the game。

I mean， we had been doing that probably。Since the beginning that I'm talking about。😊，The the kind。

Stream you had today。Where we we played the game and we had an idea we implemented that that things we going to do that till the end。

And well， maybe not in the the end， they're going to do like some cleanup and polished pass on the ancient insect。

But let's also add full screen to the engine。啊。But for now， and let's also put the profiler like。

Up here in terms of priority。Okay。😊。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_976.png)

Now， let so that's it for this stream。 Come on done a lot。 Let me just go back to YouTube page。

 You can access all streams on YouTube dot com s Dan day Dan。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_978.png)

You can watch the whole thing from the very first line of code all the way to where we are now with all sorts of cool acclaim based stuff and animations and particles and sound and bitmaps I don't know。

 whatever we did a lot of stuff so you can watch the whole thing。On YouTube。

 and you can also download the game and the source code for free on HIO。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_980.png)

So if you can come here on dzd。h。o， download the whole thing， play around with it， whatever you want。

Hopefully learn a bit as well， we're going update the pages now that we have sound。I don't know。Okay。

 and。Yeah， well we can also play my other game。 big game that release for the PC and D for。

 that'll be cool too。 Okay， so thank you for watching this stream。 Next stream， we are going to。

 yeah， we're going to do more game list that we're going to make the better all sorts of crazy stuff and also start doing more levels like Teris。

😊。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_982.png)

Froger， Froger going pretty cool。 Siip pet snake。Have to think about snake。

 someone through that on the chat today。But I'm not 100% clear how that would work。Tank。

Which the tanks are going to shoot you with power downs， that'll be called Detcon。And for Dr。 Kong。

 we're going to need。呃。And I think spacing majorters have been the last one。And for Dr Kong。

 I think we'll need a。For Donkey Kong and for Hubert。Going to need OBB coaldition。Okay。

 so that's what we're going to do just just going to comment。This， like， make。This the last。来不。😊。

I think that's it。So thank you all for coming。 I hope you enjoyed the stream as much as I did。

 The game is really coming awesomely along。 I'm really excited I have to hold myself not to program offstream。

😊，Because I know it's so much fun。 And I really want to。

 to get along now that we are like in a final stretch。 There's still a lot of stuff to do。

 But in terms of like or like seeing things iterating quickly， we're not not in final stretch。

 So thanks for watching。 and I hope to see you next time， cheers。😊。



![](img/35cc7b407d7f4707e0d68b6c750d9e6f_984.png)