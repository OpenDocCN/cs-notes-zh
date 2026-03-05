# 【从零开始用C语言制作游戏】 p07 Making a game in C from scratch! Ep 07： -Adding Juice to the Game ( -BV18i421a7DD_p7-

Hello everybody， welcome to my new live stream where we are creating an entire game in C from scratch。

😊，Well， if you have been following along our series。

 you'll see that we've come a long way ever since from the first episode weve started out with a blank file。

 no libraries， no nothing then we typed every code we needed and if' come here in the YouTube page。

 which is YouTube。tcom/ Danay Dan。You can watch all the episodes from the very first one。

They started out with nothing ever since the last episode。

Which was episode6 they started cleaning up the gameplay and getting like a game a little bit more cohesive。

 And that was pretty cool。 and also we debugged a lot of stuff that we accumulated in the other streams。

 If you want to come here in the HIO page， which is standsident do H dot Io you can click on this first game here。

😊。

![](img/06038cb1cd219389e961b5d06c0686c3_1.png)

Break Arcade games out。

![](img/06038cb1cd219389e961b5d06c0686c3_3.png)

I don't know if that would be the final name。And you can download each episode's executable and the source code。

So if you want to follow along， we can go to last episode。

 which us episode6 source code and download that's what I'll be using today。



![](img/06038cb1cd219389e961b5d06c0686c3_5.png)

Okay， so let me show you the game。

![](img/06038cb1cd219389e961b5d06c0686c3_7.png)

Show where we are at。So now I have a pretty solid gain in terms of the basic of the game。We have。

A breakout clone to start with。 And we have like we added a score system。 we added a live system and。

Yeah， so see， I just died there and。We did burn a lot of stuff last time about the mouse。

Input about the。Yeah， the mechanics overall so yeah， let me just try to get the ball there okay。

 so we again can get a lot of points by doing that and yeah so that's the basic idea。

We also added a lot more game modes， so this one。We do like a little bit of a different shape of blocks。

And then we have power ups and we finished all those last time see we have like。

The three shots are up。I see which one is this guy。Yeah。

 this is the comment that goes through all the guys。Yeah。Okay。Yeah。So， okay， so that's the。

The other game mode， let's put it that way。Yeah。And then we have our cool。

 interesting crazy game modes this one。Is pong， so we are playing pong as in a breakout game。So yeah。

 we should really， you know， start doing more interesting stuff with that。

 like pretty much just adding different acceleration for the。For the enemy bow。

 that'll be cool enough。And then it has space evaers。So yeah， that's what we did last time。

 what we are going to do now。You're going to make the game。Have a better feel to it。

 So that's a term that a lot of people use， like game feel and game juice。

Which is basically tuning both the visuals， the sound， but we don't have sound yet。And the overall。

The overall tweaks like acceleration and things like that to make the game not only more responsive。

 but more。I don't know like。Interesting to interact with。

 so it's going to be like a game as an interactive software kind of approach。



![](img/06038cb1cd219389e961b5d06c0686c3_9.png)

We noted a lot of stuff that we could add， I me just load the project here。

We noted a lot of stuff we could add in terms of。This game for stuff like you did。

Fix the ball and do like three ball colors， squashing stretch， show time with screen shape。

 make the walls move ball tray particle system。 Let's add a couple more。 Let's do like pun。呃。

Pong independent。Block movement that's going to feel nice。 And let's do like space invaders。呃。

Getting。Faster。Time。Loops。And， let's do， like， also p。嗯。最胖。Influence。TheAbout。不是。Yes。

 these are some of the ideas that we're going to do， not sure we're going to do all of them today。

Or this time around， because we also， we can do like a polished pass later。

But we're just going to start playing around and making the game for an answerr。



![](img/06038cb1cd219389e961b5d06c0686c3_11.png)

So the first thing I want to do is the squash stretch。



![](img/06038cb1cd219389e961b5d06c0686c3_13.png)

for the player， when we move the player。Okay。😊。

![](img/06038cb1cd219389e961b5d06c0686c3_15.png)

If you check out my other game， the one that we benchmarked as like the base game that we wanted to make at least as good as。

You can see that when you move the player。There's a nice squash and stretching going on and like if you collide。

 kind pops back。And because this is keyboard input。You can see a little deceleration when I stopped。

You know adding。When I stop accelerating him。That have you can't do because the mouse so I'm going to try to do a little bit more different this time。

 so the basic version we could do is just basically get the velocity and then influence the scale both vertically and horizontally。

That's what I did in this case， but I'm going to try to do something more interesting。



![](img/06038cb1cd219389e961b5d06c0686c3_17.png)

I am going to add， let's see we have the player key， I'm going to add like a player。Yeah。Viual P。

And player visual DP。Okay， and I want to， I want the visual part of the player to be sort of like a。

A spring thing。

![](img/06038cb1cd219389e961b5d06c0686c3_19.png)

So let me quickly draw that just so you guys understand the basic idea。

 so if I am here and I move here and I stop immediately， what I should do is something like this。书。系。



![](img/06038cb1cd219389e961b5d06c0686c3_21.png)

So that's the basic idea。For now， we're going to render a different guy。

Just so we can see the difference like let's see players。P还是 that？This guy。

Let's draw a different player P。 Can we do with the， let's add。The player visualty。

To like a010 guy just so we can。Were going to see something。 And let's make。Yellow。So it should be 0。

 zero， yeah， oh hes two。Similar， that's make。

![](img/06038cb1cd219389e961b5d06c0686c3_23.png)

To make a blue， I don't think we've ever do like a full blue guy。



![](img/06038cb1cd219389e961b5d06c0686c3_25.png)

Okay， so first of all， let's making a。Follow our guy。 So we have the player desired P， right？嗯。

And let's see。Yeah。EPX。Yeah， so let's make our player visual P。



![](img/06038cb1cd219389e961b5d06c0686c3_27.png)

Well， could just said that' the player decided who could do that as the first version， so see。

 that's the first version。

![](img/06038cb1cd219389e961b5d06c0686c3_29.png)

没有。What we want to do is we want to accelerate， so we're going to add like A。I can do like it。

Thank here。And we can do a like。Player visual DP。So we're going to accelerate the player。

 let's start out as a zero guy。And first of all， let's just focus on the X。

 I think we're only going to focus on the x， the other one we can pretty much straight up copy from the other guy。

 so the X。It's going to be。呃。Let's say we want to continuously go to this position， right？We have。

Like a target position。And a desired position。 So this one is a desired position of target position。

 right， And we are at the player。😊，Visual P。O。So this is our desired position。

 our target our current position， so current， and we can also do like a multiplier for this guy。

 we do like 10。Time for this guy， that'll be the acceleration。

 then could you like the the normal movement basic movement equation which is。The acceleration。

I think did that before the acceleration。Times。The Dt squared。Times half plus。

 So I'm going to do like。Me two player。啊，比如说P。Plus。The player。比说DP。Okay。

 and then we can also do it to play your visual DP。Which is going to be。

Going to add the old one clear visual D P。To the multiplication of the player。Visual GDP。

Time D T this time。能力支持。Okay。😊，And we should also like set the initial guys。

Two few arguments for aV2。Illegal forstruct。So I can do like。Player desired P。Un， yeah。是这个。



![](img/06038cb1cd219389e961b5d06c0686c3_31.png)

Okay。Now。诶。Hey man， ABX， I don't know what you mean by that。



![](img/06038cb1cd219389e961b5d06c0686c3_33.png)

Okay。

![](img/06038cb1cd219389e961b5d06c0686c3_35.png)

Okay， so。We are starting to get somewhere。 Let's just not do this。



![](img/06038cb1cd219389e961b5d06c0686c3_37.png)

Dude。Is that awesome or what？

![](img/06038cb1cd219389e961b5d06c0686c3_39.png)

So， the problem is。We have no daing。So we are like a frictionless， infinite dampless spring。

 that's a coolja adjectives。So what we want to do here is like the faster wer in one direction。

 we want to pull harder to the other direction， so're going to add as for like another coefficient as you like half。

The same thing， but for the DP。And the desired DP is zero， so we want to be static。

 right and the current DP that's this guy。

![](img/06038cb1cd219389e961b5d06c0686c3_41.png)

So that's the basic idea。No， we should。

![](img/06038cb1cd219389e961b5d06c0686c3_43.png)

![](img/06038cb1cd219389e961b5d06c0686c3_44.png)

嗯。That's you like really strong。你恤。

![](img/06038cb1cd219389e961b5d06c0686c3_46.png)

![](img/06038cb1cd219389e961b5d06c0686c3_47.png)

Dude。T about game feel， that's going to feel so awesome。



![](img/06038cb1cd219389e961b5d06c0686c3_49.png)

I'm going to end like a lot of dancing。

![](img/06038cb1cd219389e961b5d06c0686c3_51.png)

![](img/06038cb1cd219389e961b5d06c0686c3_52.png)

Yeah， but I'm also going to increase this guy。

![](img/06038cb1cd219389e961b5d06c0686c3_54.png)

![](img/06038cb1cd219389e961b5d06c0686c3_55.png)

Okay。Kind of good。Maybe decrease the density of it。



![](img/06038cb1cd219389e961b5d06c0686c3_57.png)

Okay。I don't know if you guys can see the difference。But I can certainly feel the difference。

Whenever I。

![](img/06038cb1cd219389e961b5d06c0686c3_59.png)

Okay， dude， this is awesome。 And the the visual P。I should just set it to like the desired P。

Why is going to do。Gい？

![](img/06038cb1cd219389e961b5d06c0686c3_61.png)

Yeah。So we got this。Dude， this is so much cooler。I think you guys can see that so much cooler to control this like a cool crazy jelly man。



![](img/06038cb1cd219389e961b5d06c0686c3_63.png)

Now， if we start playing around。With the size on top of that。



![](img/06038cb1cd219389e961b5d06c0686c3_65.png)

That's going to be wayco。Yeah， so I don't think I'm going to do all of this。

 Im going to clean up this a lot。So we're now going to have both。

 we're going to have the target position， which is the green guy。



![](img/06038cb1cd219389e961b5d06c0686c3_67.png)

![](img/06038cb1cd219389e961b5d06c0686c3_68.png)

And we'll have the desired creation， which is this guy。Okay， so。Let's do。Player half size。Right。

 dot x is going to be equal to。系于。DP。Dot X。Let's just see what the base halfh size is。

 that's a player。Half size。It's 10，2， so let's do like 10。Plus。This guy。We should go， well。

 that is our print， shall we now that we do have a print system that we implemented last time？Well。

 so far it's just print in， so you're going to hack。That a little bit。But that'll be okay。

 So let's see。From heat to float。

![](img/06038cb1cd219389e961b5d06c0686c3_70.png)

Let's see what we have。In termsm of speed。Yeah， we don't have negative。



![](img/06038cb1cd219389e961b5d06c0686c3_72.png)

We definitely have to improve that， but that's just like EBS。OrThe absolute value。

 just so you can see like a member。And actually， I'm not sure。If we have like a huge number or not。

So you're going to do like。

![](img/06038cb1cd219389e961b5d06c0686c3_74.png)

82 or maybe8。Yeah， so we have huge numbers。Let's see。 I think it's like。



![](img/06038cb1cd219389e961b5d06c0686c3_76.png)

It multipplied by 100， right， so let's not multiply it by 100。



![](img/06038cb1cd219389e961b5d06c0686c3_78.png)

P number。Okay， so we go up to 1 thousand83 are super。



![](img/06038cb1cd219389e961b5d06c0686c3_80.png)

Super a。Super fast。Let's see if。In the1 thousand scenario， you want to be twice as fast。

 So this is going to be plus。This guy divided by。H0。Which is like。



![](img/06038cb1cd219389e961b5d06c0686c3_82.png)

Okay。

![](img/06038cb1cd219389e961b5d06c0686c3_84.png)

![](img/06038cb1cd219389e961b5d06c0686c3_85.png)

Yeah， it should really just be。Absolute， just like we did last time。



![](img/06038cb1cd219389e961b5d06c0686c3_87.png)

Yeah。Do this， that's like motion thereive。That's super cool。



![](img/06038cb1cd219389e961b5d06c0686c3_89.png)

But you know， I'm going to do instead of using that player， I'm going to use the visual DP。



![](img/06038cb1cd219389e961b5d06c0686c3_91.png)

Well。

![](img/06038cb1cd219389e961b5d06c0686c3_93.png)

I don't think that changed anything。Yeah， maybe this guy。



![](img/06038cb1cd219389e961b5d06c0686c3_95.png)

I guess。

![](img/06038cb1cd219389e961b5d06c0686c3_97.png)

The visual D P。Is the acceleration to match the other guy。



![](img/06038cb1cd219389e961b5d06c0686c3_99.png)

哎呀。😊，Not sure， though。Yeah， it's too much， yeah， but。



![](img/06038cb1cd219389e961b5d06c0686c3_101.png)

Yeah， I think I'm going to use like。This guy。Okay， now for the why。It's going to start off as two。

 they aren't going to do like minus。嗯。

![](img/06038cb1cd219389e961b5d06c0686c3_103.png)

And he's going to need two hand but let's see。

![](img/06038cb1cd219389e961b5d06c0686c3_105.png)

Way， way， too thin。Oh yeah。

![](img/06038cb1cd219389e961b5d06c0686c3_107.png)

![](img/06038cb1cd219389e961b5d06c0686c3_108.png)

是。是。Dude， this is so much better， you guys have no idea。😊。



![](img/06038cb1cd219389e961b5d06c0686c3_110.png)

Yeah， maybe it's a little bit too thin still。

![](img/06038cb1cd219389e961b5d06c0686c3_112.png)

But。This is like the coolest thing ever in terms of like the game。😊。



![](img/06038cb1cd219389e961b5d06c0686c3_114.png)

嗯。

![](img/06038cb1cd219389e961b5d06c0686c3_116.png)

The blue guy is so much fun to control。So jelly and stuff。And that motion there looks awesome。Yeah。

Sh。

![](img/06038cb1cd219389e961b5d06c0686c3_118.png)

Okay。Really， really， really cool stuff。 Now I'm going to clean up a lot of。😊。

Things that we were messing up， so we don't need。We don't need。 Well， first of all。

 we don need to draw the the other guy， right， So the player。Let's call this guy the player target P。

Yeah， let's change player P。Per。好。So this is the target position。And well， you know what？

I probably have to grow like。One by one。Just to make sure。That I know what I'm changing。

 so calculate speed adjustment for the ball。This is the playwground， this one doesn't matter。

Because it's the same。Maybe I should just split them。Yeah， you know what， I'm going to do that。

 I'm going to do like the player PY。Wehi just fixed。The player target。P， X。ok。

The player visual P and the player visual DP。So this one' is going to be a player of P later on。

So this guy is just a player keyY。Sponship or shot。I'm going to use the。Player。Yeah。

 this one I'm going to keep player Px， whichs going to be like。

The damned P and maybe I should do the same with Py so。Player P Y。Oh。

I can pretty much just do it like this。Yeah。Maybe it's gonna break a few things。They your visual P。

So this is just the player pe。Yeah。Yeah。And this going to be the desired to PX。

Like play your target Px。Yes。Oh， we do have the desired piece。Yeah。

 no this is going to be the desired P dot X。And the desired P。Well。

 not entirely sure this is correct。Well， no， let's。Let's keep the。



![](img/06038cb1cd219389e961b5d06c0686c3_120.png)

Let's keep two of them for now and let's see what we're going to do。呃。



![](img/06038cb1cd219389e961b5d06c0686c3_122.png)

Yeah， we're going to make the collision B with a visual P first。Yeah， let's change this guy。

Then calculate speed adjustment。Let's make it the visual P。

And then you can change the visual key back to the other guy， probably at it。Triple shot， visualee。

Yeah， people shut。你说P。Start game。This one's going to be this。Stadium。嗯。It doesn't even matter。

They'll be the same。Okay， simulate block per level。Yeah， doesn't even matter。

Because the why the same。Okay， play movement， so this is the complicated step to me。

We have to do this guy， yeah。Oh， wasn't that complicated。The desired P。

Just this guy and the usual P is going just yes straight copy。Update ball。 so if it's colliding。

With a visual P of the player， okay。Yeah。Then。We check out the visual P。As well as this。

If it's colliding。Oh yeah， now it's black。This is。Yeah， colliding with the power ups， same thing。比如说。

This guys going to play your render。So I'm going， yeah， the desired。Oh， no。

 this is the place's praying。Now， this is the play rangeer。 So the Dpx。

Is how much removed last frame？Yeah。😊，Okay。And set visual your P。



![](img/06038cb1cd219389e961b5d06c0686c3_124.png)

Yeah。Okay， let's see what we have。Yeah， so we are。

![](img/06038cb1cd219389e961b5d06c0686c3_126.png)

Yeah， now we can we。This guy。

![](img/06038cb1cd219389e961b5d06c0686c3_128.png)

I think I'm going to make this spring， I'll call that I don't mean it minus target。



![](img/06038cb1cd219389e961b5d06c0686c3_130.png)

下一个。And simulate our play movement movement。I called that。Here's pretty much。Okay， so this spring。

 I'm going to make the Dan a little bit less。

![](img/06038cb1cd219389e961b5d06c0686c3_132.png)

はい3。

![](img/06038cb1cd219389e961b5d06c0686c3_134.png)

那。And那是。And that's too twitchy。

![](img/06038cb1cd219389e961b5d06c0686c3_136.png)

Yeah。

![](img/06038cb1cd219389e961b5d06c0686c3_138.png)

ancy。Okay。

![](img/06038cb1cd219389e961b5d06c0686c3_140.png)

That's better， so this player P， we're going to call that target P player target P。

And then play your target Dp。So target P， yeah， I think pretty much just popular player。Player P。

P your target。The playerlayer DP。The player。T点。Are we even using the player to target？第皮。OER。



![](img/06038cb1cd219389e961b5d06c0686c3_142.png)

To get this spring motion。Now。I changed。

![](img/06038cb1cd219389e961b5d06c0686c3_144.png)

Yeah， let's just do a little bit more cleanup， so we have the player target P and the target Ep half size。

 the like the visual P。And the usual DP。I think that's okay。So。We did this squ stretching， oh。

 let's do like the player collision。This is going to be a little better work。呃。Too much work。

 I think。Because it's hard to get Hunt1 right， so let's just do something fun with the ball trade first。

So the ball tray， we want the tray for the ball， right？Easy enough。What are you going to do？

Like you have a ball let see。Yeah。Yeah。Each ball has a trail。So inside， I'm going to do like。S。嗯。

Blic trail。 All you're gonna have now is a pe。Ana life。So for every ball。

 I'm going to have a few ball trays。That's， I like 8。The night诶。Not好吃 you。W tray wall。

 let's just call it trays。Okay， so what we could do when we render balls。We just could。

After he set the position。We could add a new trail， right？Bll trail， trail。Equals ball trails。Plus。

 ball。嗯。Next trail。Next ball trade， oh， let's do like just now。It's like this next。Next trail。

Plus plus， if next trail is greater or equal than a array count， we did that a lot。Baow。呃。Trails。

Next tri is zero， so with the circular buffer we did that a lot。B next tray is zero。

Going to set the trail。P。To be the bally。And I said the trail。嗯。Is it life？Let's go。Life。I set that。

I said that to one。So let's draw the trails first and we should also draw that probably before everybody else。

Oh actually it doesn't matter。So。4 in I equals 0 I less than。A recount ball trade。H， plus plus。猫。

Prayial plus。はい。So if。Trail life is greater is less than or equal to 0。Con。Then I'm going to。

Secept the live minus the Dt。Theyre're going to set the。I'm going to draw the trigger， right？Yeah。

 this is like old stuff。We'm going to keep it for now。We're going to add like alpha to our colors。

But for now， let's do like a white trail。Okay， but this is the trail。皮。😊，And yeah。

 let's use the ball half size。Trail。Next trail。Highest superior local declaration。Yeah。

 we can call that new trading。

![](img/06038cb1cd219389e961b5d06c0686c3_146.png)

We're not going to do that every frame as you guys will see。

 we're probably not going to see anything。

![](img/06038cb1cd219389e961b5d06c0686c3_148.png)

Oh， we do see。Dude， that's cool enough already。

![](img/06038cb1cd219389e961b5d06c0686c3_150.png)

Yeah， the thing is， this is frame rate dependent。So if I' were running pretty slowly， I be make like。

 oh， I can't make full screen now。Oh， and I can't even change the size because of the mouse locks oh。

 that sucks。

![](img/06038cb1cd219389e961b5d06c0686c3_152.png)

嗯。Let's try to hack that in。Let's make it like。It's like a super small screen。To's make it like 7 20。

I'm2 divided by it。16 times。

![](img/06038cb1cd219389e961b5d06c0686c3_154.png)

So you pretty much can't see a trail。

![](img/06038cb1cd219389e961b5d06c0686c3_156.png)

All， okay， that's fair enough。Now。Let's do a bigger。



![](img/06038cb1cd219389e961b5d06c0686c3_158.png)

Stream。And you' probably see。A longer trail， is that correct？



![](img/06038cb1cd219389e961b5d06c0686c3_160.png)

Yes， this is correct， because since we have fewer frames。呃。This difference in the trail is bigger。

 So we don't want to spawn。A。Now let's just keep that for now。

We're not going to spawn every frame in the ball， we're going to see like a trail。Timer。

Soball trail tea。Trapon。一？We're going to make that。Less than。Yeah， we also don't need the life。

 but we are going to visually change it， so yeah。Hello， what does for each ball does。

 The for each ball is just a macro。Thatta is a four。Can I go through all the balls of the game？

My pointer。just I had to type that a lot and I excited okay me。Mecro for that。啊。Okay， so。

That we were subtract the transponder and if。The cheer partner， let's say one every。

A10th of a second so。いけ？0ro。If it's zero， we are going to respondwn a no trail， oh， this is wrong。

This should be like here， yeah。We're going to spawn a new trail if this guy is zero。

If it's less than R equal to 0， and then going to。Creeze that by 0。1。Yeah。

 I think that's good for note。Yeah， and then we have to create。Trails， Po tea。Yeah。

 so now it should be frame independent。

![](img/06038cb1cd219389e961b5d06c0686c3_162.png)

Yeah。But as you can see， it's not nearly as frequent as we need。

 but the size of the tray is pretty cool。That's gonna be nice。 Now。

 let's try the small screen again to see if we still see these guys。



![](img/06038cb1cd219389e961b5d06c0686c3_164.png)

嗯。You're like saying。

![](img/06038cb1cd219389e961b5d06c0686c3_166.png)

Okay。Let's see， yeah。It's the same thing。Although。Our damp is not the same thing。



![](img/06038cb1cd219389e961b5d06c0686c3_168.png)

Yeah。😊，So this one is correct。But our spring is not correct。

I've probably missed a DP multiplies somewhere。The D TP， Oh， yeah， here the。

We're to apply the DP times the Dt and the DDP times the Dt is squared。Divided by two。



![](img/06038cb1cd219389e961b5d06c0686c3_170.png)

So so we're back。Now' normal， oh， now're stuck， oh we're not stuck， but it're super slow， dude。



![](img/06038cb1cd219389e961b5d06c0686c3_172.png)

Okay。

![](img/06038cb1cd219389e961b5d06c0686c3_174.png)

Okay， so you have to tweak those values again。

![](img/06038cb1cd219389e961b5d06c0686c3_176.png)

Now， dude now like。 Yeah， let's。Let's take this damping out。



![](img/06038cb1cd219389e961b5d06c0686c3_178.png)

Let's go back to make that。

![](img/06038cb1cd219389e961b5d06c0686c3_180.png)

嗯。It's going to be tough to tweak， you know what？The draw player。Laeranger。

I'm going to draw the player target key。

![](img/06038cb1cd219389e961b5d06c0686c3_182.png)

Same thing you did。I'm going to do that。Just so you can tweak these value again。



![](img/06038cb1cd219389e961b5d06c0686c3_184.png)

Yeah。See， this delay。

![](img/06038cb1cd219389e961b5d06c0686c3_186.png)

We don't want that。So it's spring。Let's make this guy like。Really stronger。

So this pretty much should be stuck yeah。But now let's。



![](img/06038cb1cd219389e961b5d06c0686c3_188.png)

Remove a little bit。Up the down。

![](img/06038cb1cd219389e961b5d06c0686c3_190.png)

Okay， starting to get better。

![](img/06038cb1cd219389e961b5d06c0686c3_192.png)

嗯。

![](img/06038cb1cd219389e961b5d06c0686c3_194.png)

Yeah。I thought we had a nice value there。

![](img/06038cb1cd219389e961b5d06c0686c3_196.png)

We're not going to stick so much， okay。

![](img/06038cb1cd219389e961b5d06c0686c3_198.png)

This is better。But。Martin。

![](img/06038cb1cd219389e961b5d06c0686c3_200.png)

![](img/06038cb1cd219389e961b5d06c0686c3_201.png)

Okay， not so much damping。喂。Those value tweaks。

![](img/06038cb1cd219389e961b5d06c0686c3_203.png)

Are not the most fun thing ever。

![](img/06038cb1cd219389e961b5d06c0686c3_205.png)

Okay， I kind of like that。Kd of liked。

![](img/06038cb1cd219389e961b5d06c0686c3_207.png)

Okay。

![](img/06038cb1cd219389e961b5d06c0686c3_209.png)

Yeah， it's not 100%。You know what， I think I'm going to keep。This guy。



![](img/06038cb1cd219389e961b5d06c0686c3_211.png)

For a while。

![](img/06038cb1cd219389e961b5d06c0686c3_213.png)

Yeah。Just going to tweak these values a little bit more。 It's going to make this guy stronger。



![](img/06038cb1cd219389e961b5d06c0686c3_215.png)

Okay， I think。think that's， that's good。You know what， maybe we can keep them both。Let's see。

Let's see if I managed to print anything。

![](img/06038cb1cd219389e961b5d06c0686c3_217.png)

I think we'm going to keep them both because that's going to work as a trail。



![](img/06038cb1cd219389e961b5d06c0686c3_219.png)

Oh， boy， we have to fix the collision for that as well。



![](img/06038cb1cd219389e961b5d06c0686c3_221.png)

Let's just say visually what happens if we put them in the same color。Which is。



![](img/06038cb1cd219389e961b5d06c0686c3_223.png)

Kind of like that。

![](img/06038cb1cd219389e961b5d06c0686c3_225.png)

Let's remove this one， just for reference。

![](img/06038cb1cd219389e961b5d06c0686c3_227.png)

Yeah， but this is， I don't know this feels a little bit better。Yeah， the other one is prettier。

This one feels more。Responsive。Yeah， okay。

![](img/06038cb1cd219389e961b5d06c0686c3_229.png)

So I'm going to remove this guy。Okay， now back to the trail。 so first things we see that 0。1。

It's not a lot。

![](img/06038cb1cd219389e961b5d06c0686c3_231.png)

That's like 0。01。Okay， so this is better， still not 100%， but I think that'll be enough。



![](img/06038cb1cd219389e961b5d06c0686c3_233.png)

So we probably have to add like a lot more。T you guys。And in life， let's just not。

That's just not disconside because of the line so we see like the photo is' the right C++ in our daily job。

 it depends my daily job is basically I solve problems using programming。



![](img/06038cb1cd219389e961b5d06c0686c3_235.png)

So sometimes I use C++， I use C， sometimes it's like weird scripty stuff that I really don't like。

 sometimes I do web stuff。There's not a rule， I don't have like a fixed job by just kind of a get a。



![](img/06038cb1cd219389e961b5d06c0686c3_237.png)

See what opportunities are having to solve problems with programming， random stuff， not game related。



![](img/06038cb1cd219389e961b5d06c0686c3_239.png)

That was pretty cool thing， but we're not dense enough we are going to add。We are going to add。

Let's see。The rotation later on so。

![](img/06038cb1cd219389e961b5d06c0686c3_241.png)

This is going to be better。But considering a frame is this long， oh， it's not actually。



![](img/06038cb1cd219389e961b5d06c0686c3_243.png)

嗯，最跟。We're going to have to do some more interesting stuff with that。When we。

When we lock our frame rate。that's pretty cool， you know， the faster we go， the longer the trail。嗯。

Okay。Yeah。Okay。This is starting to be nice。Okay， so PB， not really PhB。

 I haven't used PhP for like a long time。

![](img/06038cb1cd219389e961b5d06c0686c3_245.png)

Okay， now let's make the trail softer。How are we're going to do that our arrangeer and go back to the life system？

Have to treat that Our renderer doesn't support。Alphaed values。So we' we have to change that。

 so we have a draw。Reacting pixels。You're going to have to do like a draw。Rect pixelels alpha。

Like transparent draw transparent react。Okay now instead of just setting the color straight up here。

I'm going to do a lu， Do we have alert， I don't think we do。I'm going to do a blurb color。

This is the target color。This。Is the a color。And alpha。Okay。Yeah， I think thiss right。

 we could optimize this later。And。Yeah， maybe like curse。But we're not going to have that much。

Alpha guys， so color and alpha。Lurb color， Yeah， I think we have lu， but not learned color。Learn。So。

 learn color。We'll take U 32 a。FT U 32 B。And then you're probably going to have to alert every guy。

 correct？Yeah。So like RRT， let's see。All right yeah， T for target。The target。I。I just like a。

Is going to be。诶。😊，Masked。With this guy。Shift。I'm not sure how low this is going to be。

 you have to profile that later。Masked by this guy shifted。By rightshift。By 16。Okay， so。She to by8。

And。AB等于 A。Mass。With this guy。That's it。Okay， so A与BB。ok。Now we're going to return a make color。

With Lp， you wait。Right， yeah， A R。嗯T。BR。Okay， so this is going to be G。実かリピ。

And I don't think we have a alert P8。I think we can just like。Yeah。哎。32， you wait。

Leark true definition， you。Okay。😊，Conversion from F32 to UH possible loss of data。Oh， because。

This guy。She's still the at 32。How am I supposed to do that。

 am I supposed to to do the lup in F 32 and then？Yeah， I'm going to do that。

Not going to do the pen weight。But I am going to straight up cast to U age。So。Yeah。

This is likely to be， it should have floating point colors。You're going to put that in that you do。

For a， rotated racks。啊。Loloating point colors。Yeah， because this is like。

It'sry to hack a lot of stuff。Cversionion from呃。Return， Okay， yeah。T。

Iitialized conversion from U 32 to U8。Oh， we。Yeah， so I might as well cast that draft。So F 32。

And these guys。い guysす。We have 32s。Then I have to cast anyways。Wow。

 that's really a lot of code editing。Like。😊，Cold as tax。 not code as。Things to make the game work。

One more。Okay。Let's see， oh， we have to， yeah， so that was the first part。

Draw transparent rack in pixels now in the draw rack。We should have a drive to transparent to act。

That takes an alpha。And then calls the draw。Transparent。Pixels and in the game， when we the trail。

 let's do trails。Rrier balls。I'm going to enter the trails。靠的。You're going to do draw。

We were transparent。Everybody close， I'm going go to pass the trail。Life。That is it now。Under thefin。

Trans。You transparent。T hope something。Oh， yeah。嗯。Trannce。Yeah， okay， so this one is。

And then they're going to pass out。

![](img/06038cb1cd219389e961b5d06c0686c3_247.png)

好。Now let's see what we have。Well， nothing apparently。Let's do a little more controlled experiment。



![](img/06038cb1cd219389e961b5d06c0686c3_249.png)

In the game， when we draw the player。Last you draw transparency draw。



![](img/06038cb1cd219389e961b5d06c0686c3_251.png)

And pass half。 Well， let's pass 0。And， so zero is transparent half。



![](img/06038cb1cd219389e961b5d06c0686c3_253.png)

Okay， so our transparent remainder works。

![](img/06038cb1cd219389e961b5d06c0686c3_255.png)

Nice。So the problem is not。Our render， it is stove the trails。Yes， true life。

I think I have to multiply that by a bigger number， like 10。

Because he didn't actually see any difference。

![](img/06038cb1cd219389e961b5d06c0686c3_257.png)

嗯。

![](img/06038cb1cd219389e961b5d06c0686c3_259.png)

This is a bit weird。 Let me print。We can analyze the frame。Okay， this is going to look pretty cool。诶。



![](img/06038cb1cd219389e961b5d06c0686c3_261.png)

Okay， so when it's zero or less than zero， it's glitched out。



![](img/06038cb1cd219389e961b5d06c0686c3_263.png)

And it's taking a long time to be transparent。

![](img/06038cb1cd219389e961b5d06c0686c3_265.png)

嗯。Yeah， let's do like this so we don't pass negative numbers。And Aunt T was too much。



![](img/06038cb1cd219389e961b5d06c0686c3_267.png)

Letice do too。How does that look？

![](img/06038cb1cd219389e961b5d06c0686c3_269.png)

If we do like 0。2。

![](img/06038cb1cd219389e961b5d06c0686c3_271.png)

We should probably。N see them fade， yeah。

![](img/06038cb1cd219389e961b5d06c0686c3_273.png)

We can do like a little bit of math。Respon one for every， 0。001 seconds。

And it half that a array size。Let's call that。Let's do 0。001 f。Times。E a count。穿的包。

That should be a constant really， but who cares for now？



![](img/06038cb1cd219389e961b5d06c0686c3_275.png)

Brow trails。

![](img/06038cb1cd219389e961b5d06c0686c3_277.png)

Okay， so I did nothing。嗯。Oh， actually， this should just be the DT。And this one actually cut。



![](img/06038cb1cd219389e961b5d06c0686c3_279.png)

I think it's going to be easier to understand。

![](img/06038cb1cd219389e961b5d06c0686c3_281.png)

Okay， now we're getting a nice result。Not sure we have a correct result， though。But it's pretty cool。



![](img/06038cb1cd219389e961b5d06c0686c3_283.png)

Let's see if we can。知得。

![](img/06038cb1cd219389e961b5d06c0686c3_285.png)

I didn't actually print the screen okay。呃。But you know what the life should be one。Yeah。So。

The life should be one because we want life fully transparent in the start in the beginning or not。

 yeah， but we can play around with that。Yeah， kind of know。 I maybe we can just。

Keep them like that for now。

![](img/06038cb1cd219389e961b5d06c0686c3_287.png)

![](img/06038cb1cd219389e961b5d06c0686c3_288.png)

Oh， not like that。

![](img/06038cb1cd219389e961b5d06c0686c3_290.png)

![](img/06038cb1cd219389e961b5d06c0686c3_291.png)

![](img/06038cb1cd219389e961b5d06c0686c3_292.png)

Okay。This is a bit better。

![](img/06038cb1cd219389e961b5d06c0686c3_294.png)

Yeah， but instead of white now we can do like the normal ball color。think。



![](img/06038cb1cd219389e961b5d06c0686c3_296.png)

Yeah。好企。When we get rotated racks， this is going to look better。But。Yes see。



![](img/06038cb1cd219389e961b5d06c0686c3_298.png)

Maybe we should do like。And后。

![](img/06038cb1cd219389e961b5d06c0686c3_300.png)

A little bit wider。Yeah。Yeah， I can definitely play around with that way。Okay。Looking good。

 looking good now let's see what else。

![](img/06038cb1cd219389e961b5d06c0686c3_302.png)

We can do。

![](img/06038cb1cd219389e961b5d06c0686c3_304.png)

Ball trade player condition， yeah that's。This has been a long time coming。



![](img/06038cb1cd219389e961b5d06c0686c3_306.png)

You want to stop the player at this。This sounds easy， but there'll be a few complications， I think。嗯。

Yeah， we can also do like a lot of stuff here。Make animation like block。Detri。Animation。Makeイク？Start。

来不。Animation。Yeah。Yes。Maybe you can like reduce that a lot。Like。好 much他是这样。



![](img/06038cb1cd219389e961b5d06c0686c3_308.png)

To like 64 see。Dude， that's pretty cool， but no。

![](img/06038cb1cd219389e961b5d06c0686c3_310.png)

来显示一下。

![](img/06038cb1cd219389e961b5d06c0686c3_312.png)

Now that was too much。

![](img/06038cb1cd219389e961b5d06c0686c3_314.png)

And maybe。Maybe the ball。The actual ball should be white。



![](img/06038cb1cd219389e961b5d06c0686c3_316.png)

These guys。The sign案。

![](img/06038cb1cd219389e961b5d06c0686c3_318.png)

I think that's。Okay。Yeah。Starting to be like 100% better。Yeah， just a ball trail that was。

Let's see if you can get like a lot of。Actuallyction going on。Well， apparently can't。Yeah， see that。

That me be feasible for a while just so you can。I've got it。Dude。Okay， I think I're going to give up。



![](img/06038cb1cd219389e961b5d06c0686c3_320.png)

Yeah， well。Okay， now the play collision， yeah。We have the desired。He for the player。I still like。

系 player。Things are peak。We just。Straight up。Do the calculations and set the desired P。Oh。

 it is one frame behind。

![](img/06038cb1cd219389e961b5d06c0686c3_322.png)

Yeah， well， it's not such big a deal， I think。

![](img/06038cb1cd219389e961b5d06c0686c3_324.png)

Because it is supposed to be likely， but we can。You do like。The game robustness pass。啊。Preme。Creates。

我。Frame。Movement like。Let's go back to the play movement。Okay， so。This pretty is like if the player。

 oh that's the base idea， right， desires P。Is less than。Let's do。Minus arena half psi dot x。Plus。

 the players。Size that x。If that's the case， the player。Desirre to pe。It's going to be equal to that。

 Well， let's see。Yeah。

![](img/06038cb1cd219389e961b5d06c0686c3_326.png)

Okay。

![](img/06038cb1cd219389e961b5d06c0686c3_328.png)

So this is the yeah， that's that's why I said this was going to be complicated。

 the basic idea is this。But。We're not basic。This is C。



![](img/06038cb1cd219389e961b5d06c0686c3_330.png)

M joke。We're not doing basic anymore， okay。And we can still get off the screen。



![](img/06038cb1cd219389e961b5d06c0686c3_332.png)

Where are we。Glad to do like print in。Player。Desirreed P dot x。



![](img/06038cb1cd219389e961b5d06c0686c3_334.png)

![](img/06038cb1cd219389e961b5d06c0686c3_335.png)

Dude。Have to do negative numbers quickly。是。You know what' going to do that。

Because this turned out to be enough of a headache。In our。Draw a number。Like。If number is less。0。

Number times equals。1。And then I have to draw like。Let's get the8。Have a little dash。Like this。Yeah。

I don't know。Tax square size。

![](img/06038cb1cd219389e961b5d06c0686c3_337.png)

![](img/06038cb1cd219389e961b5d06c0686c3_338.png)

Yeah， but this is not the correct position。Since we move them left。

 we should actually like delete that like。你知道。Minus。Okay。😊，And at the very end。

If we are supposed to draw minus while we draw the minus。



![](img/06038cb1cd219389e961b5d06c0686c3_340.png)

Okay， now this is nice， but we're drawing a square。



![](img/06038cb1cd219389e961b5d06c0686c3_342.png)

Let's make like times。2。

![](img/06038cb1cd219389e961b5d06c0686c3_344.png)

Okay。Just wanted to not crash when he had the minds guy， looks good I think。

So this is kind of correct， this springs all crazy。



![](img/06038cb1cd219389e961b5d06c0686c3_346.png)

But if you。If you go crazy。First of all， we crashed。Second of all。Yeah。

 it was a huge desire to piece maybe maybe we're going to cap that remember that we capped。



![](img/06038cb1cd219389e961b5d06c0686c3_348.png)

And that was a bug last time around。Let's do the cap here。呃。This player， D P。To world。

Let's draw this guy。Let's draw this guy。Just to see its range。



![](img/06038cb1cd219389e961b5d06c0686c3_350.png)

Yeah， so it goes from two first super fast。It was like 10。



![](img/06038cb1cd219389e961b5d06c0686c3_352.png)

But we want to be able to go fast。Let's trycap that at Tim0。And-10。So let's call that。李题。李皮。Yeah。

 that's called RDP， mouse RDP。It's going to be this guy。M repeat。4リ。Yeah。😊，But this one。

 we're going to clamp that。Let's say we clam that at minus 10。In10。可以的。



![](img/06038cb1cd219389e961b5d06c0686c3_354.png)

Okay， this is better。This is wrong， but this is like。クシい。



![](img/06038cb1cd219389e961b5d06c0686c3_356.png)

Yeah， let's just fix this guy。shouldnn't be too hard。To get a little bit better。

They don't get incrementally better。Okay， so。When we do the， let's call that player。我靠那。

If we do collide with the wall。We might as well set。Let's try setting the player。Target。DP。



![](img/06038cb1cd219389e961b5d06c0686c3_358.png)

0。Don don't know if that's going to be like too much。多axy。



![](img/06038cb1cd219389e961b5d06c0686c3_360.png)

![](img/06038cb1cd219389e961b5d06c0686c3_361.png)

啊。Yeah， let's say what this takes into account the player target P。Which is last frames。P？This。Oh。

 I know，' the DPY。Got that wrong。We use the desired piece。So I don't think we are one frame behind。嗯。

😊，The target P。The desire to P now that yeah， this is not。It does not。So that mystery was solved now。

We are still doing all sorts of crazy stuff。Maybe we should also remove the visual V。

And just for the record， we may want a little bit of a ricoochet of the wall。



![](img/06038cb1cd219389e961b5d06c0686c3_363.png)

Maybe a little bit， but not this much so。Wow this。

![](img/06038cb1cd219389e961b5d06c0686c3_365.png)

Now is adding to the wall。 that's not， that's not cool。Oh yeah。

 we are usually the player of visual DP。Were setting the target P， maybe we the desired。Oh。

 we have website the desired P and the desired target。



![](img/06038cb1cd219389e961b5d06c0686c3_367.png)

See why I said this collision thing was going to be a little bit of a headache。



![](img/06038cb1cd219389e961b5d06c0686c3_369.png)

I'm going to turn back。That are。This guy again。Like。以外？Which is the target。



![](img/06038cb1cd219389e961b5d06c0686c3_371.png)

![](img/06038cb1cd219389e961b5d06c0686c3_372.png)

And that's just actually not to draw。Our green guy。



![](img/06038cb1cd219389e961b5d06c0686c3_374.png)

Okay。Yeah， so the target P is wrong。

![](img/06038cb1cd219389e961b5d06c0686c3_376.png)

So we can start with that。Target P。Because the desire to be。Oh， but， yeah。

So the thing is the design piece so let's。We shouldn like debug this， but we can do like code first。

 so we set that to how much we want to go。Then we're going to cap that at the arena half size x。Plus。

 the player have S x。So this is just the visual we don't care about that for now。For each ball。

 balls are。It should just like players。So play in the enemy rangeer。Not sure who's mess that。

So I suppose now it's debugging time。

![](img/06038cb1cd219389e961b5d06c0686c3_378.png)

Okay， now。嗯。Let's go to the simulate game。And then we're going to put a break point。ち。Okay。

So the desired P is minus 56， but we should actually be kept。At。Mus 62。Okay， thanks good enough。

So now we set that to minus 52。the DP to zero。Okay。

 it doesn't matter that we're sending the Dp to zero。Yeah， but。Okay， let's go step by step now。

We could put a data break point in this guy。And I'm also going to run the game until we start drawing。

はいです。Yeah， so nobody changed， oh， he did know。And。No， it's still minus 52 okay。Now the target。P。

He's this guy。Then we're drawing the target P。Can we check out what this looks like。

 So this is what it looks like。嗯。Yeah， well， I'm not going to complain too much。Yeah。

 maybe the thing is just size calculation。那。Yeah， because the size is spring， right。

 so we hit a break point。Did a3 point， where's that？GDI。Okay。Let's see now it's minus 62。

And then we kept that at minus 62， yeah because we are smaller。嗯。Yeah， you know what？I'm going to。

People are using our print system。

![](img/06038cb1cd219389e961b5d06c0686c3_380.png)

Fri。P your target。Yeah， I'm not going to I don't think I'm going to get too stuck with this。



![](img/06038cb1cd219389e961b5d06c0686c3_382.png)

Yeah， see， the problem is the size。

![](img/06038cb1cd219389e961b5d06c0686c3_384.png)

So I think， yeah。

![](img/06038cb1cd219389e961b5d06c0686c3_386.png)

Yeah， just to clarify who the problem is。The first frame。

 let's say we collide like this because we move super fast。

So the next frame we are here and we can go a little bit more so we do。

 so it goes like this so we go from here to here so the size is smaller。But next frame。No。

 you know what？No， yeah， yeah， okay。So we're going like from this to here and we stop like this。



![](img/06038cb1cd219389e961b5d06c0686c3_388.png)

So next time you can go a lot more。But it still doesn't explain why we go the other way。



![](img/06038cb1cd219389e961b5d06c0686c3_390.png)

I guess the other way。Yeah， we don't go the other way。



![](img/06038cb1cd219389e961b5d06c0686c3_392.png)

嗯。Draw。Okay， so what I'm going to do， just close this paint。What I'm going to do。I。

Not consider the player。Half size。When we do the collision。Now we're going to hard code。

T let's do like。Da。Player。Yes。Equals。So， we hard code。This to avoid。The size。Changes。Fel。唔拿啊。



![](img/06038cb1cd219389e961b5d06c0686c3_394.png)

小孩子。That was a description。Okay， so。W was nice， yeah。This is what we wanted。This is perfect。We do go。

A little bit to decide。Let's see how it looks in the。



![](img/06038cb1cd219389e961b5d06c0686c3_396.png)

The spring ring。

![](img/06038cb1cd219389e961b5d06c0686c3_398.png)

May look a little bit weird。Yeah。

![](img/06038cb1cd219389e961b5d06c0686c3_400.png)

Maybe I think it's a bit too much springy。

![](img/06038cb1cd219389e961b5d06c0686c3_402.png)

So that's just。

![](img/06038cb1cd219389e961b5d06c0686c3_404.png)

I'm going to keep。Playing around with these values until the game releases。This is bad。



![](img/06038cb1cd219389e961b5d06c0686c3_406.png)

So but you guys saw the problem， right？

![](img/06038cb1cd219389e961b5d06c0686c3_408.png)

The problem was。Okay， I wanted to see that。The time。Okay。

 so the problem was we go a little bit inside these guys。

I think you'm going to hack that pretty ugly， ugly。



![](img/06038cb1cd219389e961b5d06c0686c3_410.png)

第。😊，嗯。😊，Like this is the favorite light。 Yeah， I think I'm going to do that so。I'm going to。

Clear screen。Clear arena screen。Yeah， I'm going to split this functioning too。A clear screen。So we。

And a's bit。The clear screen。So we actually do。First， this guy。And then the other guy。

So we're going to do here。Arena。Screen。😊，And then， draw arena racks。It's going to be better。

First of all， we just do the clear。Actually， this is the other way around。So， clear screen。

Should be the initial act。Which is the clear。Which is this guy。This guy。Okay。

The clear the first color。So first we clear that with the first color。

And then I're going to call the drawer arena。Correct。We don't need a。We can know。

To bit better than this so。When we clear， we don't need that It's going to be zero。 Oh， yeah。嗯。No。

 we don't。我啊。We're going to keep that because want we may want to use that when you do a camera。

Things like that， okay？So that's all you want to do。For this guy， so。Yeah。For the other guy。

 we don't want to do this one。All I want to do is this one。



![](img/06038cb1cd219389e961b5d06c0686c3_412.png)

く？And now， well， nothing， nothing should have changed。



![](img/06038cb1cd219389e961b5d06c0686c3_414.png)

And it did。嗯。

![](img/06038cb1cd219389e961b5d06c0686c3_416.png)

Yeah， I got these guys wrong。是。哦，这一天。So actually， this one's the one we want to keep。These two guys。

Which is like。So we're going to start out this guy。Go all the way。I'm going to start out at this guy。

Go all the way to the other guy。 And then I'm going to start at zero and go。To one。

ToDraw or interact to a few arguments。This one I think is correct and this one we don't need。

These guys。So we draw the two bars and the one on top。Okay， think this works。

If you guys have any questions， just drop them in the chat and I'll try to answer them。啊。Okay。

 so nothing changed now what you're going to do is do the this guy。



![](img/06038cb1cd219389e961b5d06c0686c3_418.png)

After we draw the player， so we're going to pretty much click that this is like。This is like a hack。

But yeah。

![](img/06038cb1cd219389e961b5d06c0686c3_420.png)

Cool， now。

![](img/06038cb1cd219389e961b5d06c0686c3_422.png)

What we are going to do。Is make the player a little bit taller。When they era compresses。



![](img/06038cb1cd219389e961b5d06c0686c3_424.png)

Now this is going to be the we stretch， this is going to be the squashing part。No， girl。

 it's going to be the squashing stretching again。Then in the player movement。

Prety collision with the wall。We set the player half size y to this。

I'm also going to add another thing here， so。

![](img/06038cb1cd219389e961b5d06c0686c3_426.png)

We start with two plus the feet， so we super fast， we super thin。Now， if we are。

If our rightmost position。Yeah， it's in this side of the wall。



![](img/06038cb1cd219389e961b5d06c0686c3_428.png)

So let's do that。Al right mouse position， which is player target key。Plus。Player half size。

We're doing the X。

![](img/06038cb1cd219389e961b5d06c0686c3_430.png)

So。Okay， so if this guy。

![](img/06038cb1cd219389e961b5d06c0686c3_432.png)

Let's subtract the right most thing， which is this guy。This guy's the right most things。Have to。

Make that more clear later on， but for now。So this guy is the di。You know what。

 I think I'm going to print that。I feel like printing a lot of stuff today。After all， we did that。

That system， did we not。Conversion from。

![](img/06038cb1cd219389e961b5d06c0686c3_434.png)

Okay。Now， this should be。

![](img/06038cb1cd219389e961b5d06c0686c3_436.png)

I think I run。Da guy。Mイスで square。

![](img/06038cb1cd219389e961b5d06c0686c3_438.png)

Yeah， well， not sure。Okay， yeah。10。是。

![](img/06038cb1cd219389e961b5d06c0686c3_440.png)

I was expecting zero， honestly。Because the target P plus the player half size。Well。

 let you like this。This guy。好的。If Gu。

![](img/06038cb1cd219389e961b5d06c0686c3_442.png)

Sre then。

![](img/06038cb1cd219389e961b5d06c0686c3_444.png)

Yeah， okay。So。

![](img/06038cb1cd219389e961b5d06c0686c3_446.png)

So the if it's actually greater then。So呀。Do you like。F 32。That's called that。

I don't know what how to say that in English， I'm going to translate that。



![](img/06038cb1cd219389e961b5d06c0686c3_448.png)

![](img/06038cb1cd219389e961b5d06c0686c3_449.png)

It's put me Portuguese， I think it's pretty much just it like squashing。Squeeze， yeah。

 squeeze is the correct word。 So this is the squeeze factor。



![](img/06038cb1cd219389e961b5d06c0686c3_451.png)

スク。Okay， so if the squeeze factor， we should like to squeeze factor。嗯呃。Yeah。

 I think the squeeze factor is greater。Then the base。What you you call that this。Have size。

Then we print。Okay。

![](img/06038cb1cd219389e961b5d06c0686c3_453.png)

The squeeze factor。

![](img/06038cb1cd219389e961b5d06c0686c3_455.png)

Okay。

![](img/06038cb1cd219389e961b5d06c0686c3_457.png)

Nice。Now just for kicks， they are going to increase the player you have size。



![](img/06038cb1cd219389e961b5d06c0686c3_459.png)

Byナス。

![](img/06038cb1cd219389e961b5d06c0686c3_461.png)

Okay， that's like。Not。Or you want？At all。She like when we try to squeeze。



![](img/06038cb1cd219389e961b5d06c0686c3_463.png)

AndSo this I think this is wrong。So the thing is， if we do collide， we should do something here， Oh。

 okay， okay， yeah， if we do collide。Let's call that。Left most position。 Left most P。

Now I think this is clear。Lemost P。Okay， now。The difference between our desired。

And the leftmost position， right， yeah。Should be thisqueing detectorctic squeeze。So。

This is all wrong。Okay。Se factor equals zero。And then。



![](img/06038cb1cd219389e961b5d06c0686c3_465.png)

![](img/06038cb1cd219389e961b5d06c0686c3_466.png)

Let's try multiplying that by aigma。不好。Maybe I enjoyed this too much。

But just so we can see you're going to do light slowly。



![](img/06038cb1cd219389e961b5d06c0686c3_468.png)

是。

![](img/06038cb1cd219389e961b5d06c0686c3_470.png)

Yeah， we did that in the wrong guy。We're testing。有。As you that both。Left。Right。This guy。Is。

Rightite most P。 This guy should be the right most P。



![](img/06038cb1cd219389e961b5d06c0686c3_472.png)

And this guy's the right。Okay。

![](img/06038cb1cd219389e961b5d06c0686c3_474.png)

Yeah， I'm just going to be too much。

![](img/06038cb1cd219389e961b5d06c0686c3_476.png)

Dude， come on。The blade is Px。Okay， now。

![](img/06038cb1cd219389e961b5d06c0686c3_478.png)

This is like。あれ？This is here。 This is like minus-10。 This is like minus5。



![](img/06038cb1cd219389e961b5d06c0686c3_480.png)

We are doing this guy plus five， we have minus five。Yeah， well， I suppose this is correct。

Except it's the other way around， which is negative but。Don't see how this should be wrong。



![](img/06038cb1cd219389e961b5d06c0686c3_482.png)

Okay， so。And I had a break point。Here。If we are more than。That's a discrete factor。Negative， okay。

 the desired P。76， right， mostly be 75。 so the one minus the other one。



![](img/06038cb1cd219389e961b5d06c0686c3_484.png)

So。Yeah， this one is correct and this one is minus。



![](img/06038cb1cd219389e961b5d06c0686c3_486.png)

Yeah， oh okay， I draw that correctly， but yeah， apparently。



![](img/06038cb1cd219389e961b5d06c0686c3_488.png)

I couldn't write Pro， okay。

![](img/06038cb1cd219389e961b5d06c0686c3_490.png)

Okay， that's what we want。K着。😊。

![](img/06038cb1cd219389e961b5d06c0686c3_492.png)

下次。

![](img/06038cb1cd219389e961b5d06c0686c3_494.png)

This is like way too much。I think we are getting somewhere。

We also have to make us get inside a little bit of the wall。



![](img/06038cb1cd219389e961b5d06c0686c3_496.png)

![](img/06038cb1cd219389e961b5d06c0686c3_497.png)

So this guy is going to be minus this squeeze value。



![](img/06038cb1cd219389e961b5d06c0686c3_499.png)

![](img/06038cb1cd219389e961b5d06c0686c3_500.png)

And I also have to move in by the squeeze factor。So the desired P is the rightmost P。Plus the。

Divided by two， I suppose。

![](img/06038cb1cd219389e961b5d06c0686c3_502.png)

Okay。

![](img/06038cb1cd219389e961b5d06c0686c3_504.png)

Yeah see。

![](img/06038cb1cd219389e961b5d06c0686c3_506.png)

Maybe not divided by two。I was thinking that because we are adding that。To the half size。



![](img/06038cb1cd219389e961b5d06c0686c3_508.png)

嗯。But it indicates it's not such a big deal。To， you know。Go a little bit overboard。



![](img/06038cb1cd219389e961b5d06c0686c3_510.png)

Because。Now， visually we're clicking so。

![](img/06038cb1cd219389e961b5d06c0686c3_512.png)

Okay， well we're not creeping， we're just。Join the other guy on top。Okay。



![](img/06038cb1cd219389e961b5d06c0686c3_514.png)

This is starting to look nice。

![](img/06038cb1cd219389e961b5d06c0686c3_516.png)

IThink I can add a little bit more squeeze butter dirt。



![](img/06038cb1cd219389e961b5d06c0686c3_518.png)

![](img/06038cb1cd219389e961b5d06c0686c3_519.png)

呵。😊，Dude， this is cool now。Okay， but this is not correct。This is time to get cool。



![](img/06038cb1cd219389e961b5d06c0686c3_521.png)

We should do more。嗯。

![](img/06038cb1cd219389e961b5d06c0686c3_523.png)

![](img/06038cb1cd219389e961b5d06c0686c3_524.png)

Actually， we should just like we shouldn't do the frame that we hit。



![](img/06038cb1cd219389e961b5d06c0686c3_526.png)

嗯。I don't know if you guys could see the problem， that was pretty fast。Well。But we do snack。



![](img/06038cb1cd219389e961b5d06c0686c3_528.png)

Well。Yeah。Maybe。Well。来 see。

![](img/06038cb1cd219389e961b5d06c0686c3_530.png)

Okay， I think I got a pretty good frame。

![](img/06038cb1cd219389e961b5d06c0686c3_532.png)

Yeah， so。We don't want that case。But why did that happen？Why did that happen， I mean。



![](img/06038cb1cd219389e961b5d06c0686c3_534.png)

If we add a squeeze factor。This should only happen in the frame that we hit。And if we hit。We moved。

That is the desire to pe。Oh， but we don't yet。How long have you been coding。

 you mean this game or like in my life， this game， you can go to my YouTube page， which is YouTubebe。

com slash Danay Dan。

![](img/06038cb1cd219389e961b5d06c0686c3_536.png)

You can watch the whole thing， I stream the whole thing。

 you can watch it from the very first episode。Start it out with nothing。We didn't use any lever。

 just a blank file， then every line of code you can see。In my life。Well， in my life， I don't know。

 I started casually coding when I was。I don't know， 13， maybe。

Maybe a little bit younger than that I I did some animations in flash。

 so I did like go to this frame and when you press this button do that。

That was the first thing I programmed then I tried to learn C at that point but I couldn't。

 so I I just focus on more of the art side， so I spent a long time doing like 3D art。Visual effects。

 things like that， just for fun， just to learn。And then when I decided。

To do like a big commercial game and see this is the big commercial game I released。



![](img/06038cb1cd219389e961b5d06c0686c3_538.png)

For the PC and the PS4。It's called Iosis Hunt。

![](img/06038cb1cd219389e961b5d06c0686c3_540.png)

You guys can check it out on e steam。This game I actually learned how to program that's put it that way using a unrealreo engine and visual programming。

 so I connected notes， things like that， and I released that in 2017。

But I didn't actually know how to program at that point， I was just hacking things together， man。

 really， so after we released the game， I realized that I didn't know what to do。What I was doing。

 so I took。Like a full year to study really heavily。Its like。Yeah。😊。

Let's say a little bit less than a year， let's say from November 2000。17 to like July， 2018。

Then I really studied a lot programming。I'd say I've been programming for real。For like。

Almost two years， a little bit less than two years。

It's incredible how much you can improve if really put your will to it。Don't call me late for dinner。

 or what editor are you using？This is for codeder， DX editor。Pretty cool， pretty cool text editor。

 I really like it。But I'm debugging and。Running the game on Vi Studio， but I'm just not using it。

To edit。So yeah， for codeed， pretty cool。

![](img/06038cb1cd219389e961b5d06c0686c3_542.png)

So， were。We have this。There's a problem。

![](img/06038cb1cd219389e961b5d06c0686c3_544.png)

Where we do have one frame of delay here。The squeeze factor。呃。Because the target piece is that。

 but we don't move that immediately to that point。So the thing is lets me figure what I。



![](img/06038cb1cd219389e961b5d06c0686c3_546.png)

If I remove this guy， which is the screen version。

![](img/06038cb1cd219389e961b5d06c0686c3_548.png)

呃。This should， yeah， this should be perfect。Yeah， this is brilliant。This is pretty fun。



![](img/06038cb1cd219389e961b5d06c0686c3_550.png)

Yeah， but the this version， which is our。Sreme version， there's the delay。No。

 there's a lag because it's a s， so imagine a。This guy is the target one。

So it moves like all the way to this side， this one doesn't snap kind of a go like this and then goes a little bit over like this。

So。We kind of have to consider that for the size， I suppose， at least the squeeze factor。

So we should like add damp to the squeeze factor as well。嗯。😊，Yeah。Let's do that player。Iや。

I're going to add。Players， squeeze。Tectture P。And players squeeze factor D P。Do that。We are adding。

A squeeze， you know what？kind of thinking whether or not should spend the time with that。

 oh let's do it。Let's do it。那啊。Let's not do it。We can do that later on。But。Yeah。

 this is like more detailed stuff， so。You're going to throw it like a note here。Spacinggators。

 that do like。没。The squeeze。Factor， also consider。Also。Have。Let's spring look。So， don't。Have。As。

Notice yeah， not， not have a squeeze。Selectctor。Acing。To early。Maybe。We should just。Add a。

Size Dp think that's going to be the best call。Okay。嗯。



![](img/06038cb1cd219389e961b5d06c0686c3_552.png)

Let's see where we are at。Okay，It's starting to get better。Yeah， definitely。Okay。Yeah。

 it's pretty cool。Let's see what else we can do， we can play around with the colors。



![](img/06038cb1cd219389e961b5d06c0686c3_554.png)

To make the wall move， it is going to be fun。And doesn't make the walls move。



![](img/06038cb1cd219389e961b5d06c0686c3_556.png)

The idea is。When we hit a wall like this， it moves ever so slightly。



![](img/06038cb1cd219389e961b5d06c0686c3_558.png)

Yeah。😊。

![](img/06038cb1cd219389e961b5d06c0686c3_560.png)

So instead of having an arena half size。Well， we should have arena。Havelf size for the base。

 right because。We need that， like a lot。You have to get the middle point， things like that。

And the collision。Yeah。So I'm going have like。系啊。Arena， left。W，你说。And the right wall。So。

 and we also should add a Dp。Yeah， arena have size when you start a game， set the arena。Left wall。

 visual D。2 minus arena。Have size of X。And the right wall。Canry set the。Yeah， this should be the key。

你下 the这批确实了。There should also like a top wall。As first did that。し。Okay。

 this is only going to be considered when we draw。So I think I can just remove a lot of these calls that we did in the software rendering we don't need。

All that stuff。All we need now。Is to draw。Inrect。Whi is this guy？And this guy I'm going to draw。

Erect。Well。No， actually， this is wrong。 I still， well， I don't need， I don't need。

This guy can be the direct。Well， not really。Because if we do that。



![](img/06038cb1cd219389e961b5d06c0686c3_562.png)

We break。In the case， there we are not like。

![](img/06038cb1cd219389e961b5d06c0686c3_564.png)

Correct in terms of like screen position stuff。Can't test that anymore。

Because of the mouse lock thing we did。But it's basically the。



![](img/06038cb1cd219389e961b5d06c0686c3_566.png)

It's basically the the。The position changes based on the size， like super wide。

Expectual ratio that was what I was looking for。Okay， but we're going to change this guy。So。

Here drawing interacts， you're going to take the arena half size。We should actually take。

 instead of the。Instead of taking the half size？We should just change each one individually。

 so we have this guy。As the。Like left most。And this is the right most。That's called that。Okay。X， Y。

Then we do like the left。The right。Okay， then we do like the half size。喂。Time's this guy。

Let we do the leftmost。And the right。Okay， so this is going to be the arena left。Arena， bright。



![](img/06038cb1cd219389e961b5d06c0686c3_568.png)

This guy， so we shouldn't see any difference。However。And we do。



![](img/06038cb1cd219389e961b5d06c0686c3_570.png)

。Okay。Let's break at this。Right most is zero。

![](img/06038cb1cd219389e961b5d06c0686c3_572.png)

I is it0。I thought to initialize these guys。Arena。来。What。No， this。



![](img/06038cb1cd219389e961b5d06c0686c3_574.png)

Yeah， okay， so。That was weird， but I think now it's correct。

I kind of thought something I just thought， okay， this is wrong。



![](img/06038cb1cd219389e961b5d06c0686c3_576.png)

This is wrong。Dude， what's going on， start game？

![](img/06038cb1cd219389e961b5d06c0686c3_578.png)

in-84， minus-85 and 85， let's add a couple of data break pointss。嗯。

Have you are passing the wrong values？Arena left。

![](img/06038cb1cd219389e961b5d06c0686c3_580.png)

Yeahger' facing的 DP。

![](img/06038cb1cd219389e961b5d06c0686c3_582.png)

You guys should have caught that on chat。Well， I'm not trying to throw the responsibility onto you guys。

 but。Just saying I'm kidding， okay。呃。Well， I think we are more correct。Let's see 84。 Okay。

 this is nice。

![](img/06038cb1cd219389e961b5d06c0686c3_584.png)

Okay， so now we don't need to do。

![](img/06038cb1cd219389e961b5d06c0686c3_586.png)

This guy。Because it's already negative。Not working yet。Leftmost， 85 now it's like。Yeah。

 the pixelel thing。

![](img/06038cb1cd219389e961b5d06c0686c3_588.png)

Okay， I see the problem。

![](img/06038cb1cd219389e961b5d06c0686c3_590.png)

No， I don't。 I thought I couldn't。I thought， well， I thought I couldn't work on this space with。

Negative numbers， but I think that's not a problem。So， Px。Minus left most。



![](img/06038cb1cd219389e961b5d06c0686c3_592.png)

I'll generally compile the code。Oh， I changed the wrong guy。



![](img/06038cb1cd219389e961b5d06c0686c3_594.png)

This is the ones who have changed。

![](img/06038cb1cd219389e961b5d06c0686c3_596.png)

Okay， we are back。Now we should be able to play around with these guys。In an interesting way。

That do like。Wow movement。And just for the record， the simulation order is all over the place。

But things like wall movement， we don't really care， so I think spares be organized。

Then to be like a frame perfecting the wall movement。But well， I think we are forerfect。

 but we're just。Doing like simulate rangeer， simulate rangeer。

 simulate rangeer stuff doing all the simulations， and then all the renderings。So。

 we're going to do the。Arena left。 visual P。Good to do is spraying on this guy as well。啊。

The P is going to be。Go， let's add， let's do a DDP。EDP， which is going to be the target position。

Which is this guy。I'm sorry， this guy。For the left is。Is this guy？Minus the current one。

 which is this guy。Okay。😊，Yeah， let's start with that and then we have the arena。Left， while Dp。

Which。It's going to be plus equals this guy。Times the DP。And the arena， P。Yes。The GDP。Times the。

Dt squared times half。Plus。The Dp times DT。That's it。And we'm going to do that for。ですか。

The target is actually minus this guy， I don't think I'm not sure we can do that。That's try。好， ok。

That。And this is where left maybe be right。F 32。

![](img/06038cb1cd219389e961b5d06c0686c3_598.png)

Okay， let's see if we are the same。Yeah， we are the same now what we should be able to do now it's the fun part。

 is it not？

![](img/06038cb1cd219389e961b5d06c0686c3_600.png)

We should be able to add。😡，The DPAA velocity， when we hit the let's say ball。Wow。😮，Wow。😮。

Update falses。if we hit。The right side。We should do like an arena。Havelf size。 are arena， right。

Viual DP。Minus equals。然后穿。And they should do the same thing。Or the left side。

 but it's going to be plus equal。

![](img/06038cb1cd219389e961b5d06c0686c3_602.png)

Let's see what we have。ok。Isn't that cool？Okay， couple problems。We think they are going like。



![](img/06038cb1cd219389e961b5d06c0686c3_604.png)

Like this， but。It's a little bit misleading。Because when we do。Here， in the。In the softer rendering。

 when you do the clear screen。We are cap that at the half size x， we should really cap that。At the。

Left and the right。So。Let's call that left。Most。And right， most same thing we did。

 the other guy in this one can just have size Y。I why。F size y plus。The leftmost。Plus。Right。Okay。

 I need to do that。 This one is the Y。That most。And right。And this is an F32。Okay， so right。Ana。

Right。Ana， I'm sorry， is arena left。Ana right。Then we do the the Y guy。



![](img/06038cb1cd219389e961b5d06c0686c3_606.png)

Okay， now we should see the real thing， which is an undamned s， what？



![](img/06038cb1cd219389e961b5d06c0686c3_608.png)

No， no we're not。Or not actually。

![](img/06038cb1cd219389e961b5d06c0686c3_610.png)

We're not actually doing anything。

![](img/06038cb1cd219389e961b5d06c0686c3_612.png)

嗯。嗯。Left yeah， we had to do it like。Plus leftmost， this looks about correct。嗯。Yeah。

 that's debug that。

![](img/06038cb1cd219389e961b5d06c0686c3_614.png)

Let's see what kind of values do we have。

![](img/06038cb1cd219389e961b5d06c0686c3_616.png)

Zero again， we did the same thing， we passed the G P each except the P。



![](img/06038cb1cd219389e961b5d06c0686c3_618.png)

Same thing should have learned the first time。

![](img/06038cb1cd219389e961b5d06c0686c3_620.png)

Okay。Well， is that a little glitch？

![](img/06038cb1cd219389e961b5d06c0686c3_622.png)

Oh no， that's the break point。

![](img/06038cb1cd219389e961b5d06c0686c3_624.png)

Yeah，对。Now let's see what we have。Now we should have an undamed spring。



![](img/06038cb1cd219389e961b5d06c0686c3_626.png)

See what happens now it goes to the other side because it's undamned。



![](img/06038cb1cd219389e961b5d06c0686c3_628.png)

So we're going to do the same thing we did。Last time around we did the spring。

 which was we have to add a multiplier to this guy， which is like coefficient。

 then we have the target Dp， which is0 so zero minus。The current D arena。Left DP。

Wech also also add a multiplier。The coefficientです。Okay。😊，And we did that previously today。

 so it's same thing。Yeah。

![](img/06038cb1cd219389e961b5d06c0686c3_630.png)

历史。Dude。Yes。That's so cool。And how much work was that？And maybe we should add the。



![](img/06038cb1cd219389e961b5d06c0686c3_632.png)

Maybe you're going to。I don't know。Let's add a little bit more of a content。

 But I'm thinking about doing the player collision with these guys， so。



![](img/06038cb1cd219389e961b5d06c0686c3_634.png)

Nate's going to push me a little bit。

![](img/06038cb1cd219389e961b5d06c0686c3_636.png)

was too too much。900米。Nice to like。

![](img/06038cb1cd219389e961b5d06c0686c3_638.png)

![](img/06038cb1cd219389e961b5d06c0686c3_639.png)

![](img/06038cb1cd219389e961b5d06c0686c3_640.png)

No， that was way too much。

![](img/06038cb1cd219389e961b5d06c0686c3_642.png)

Oh， I put 100 here。

![](img/06038cb1cd219389e961b5d06c0686c3_644.png)

For。What did I do？

![](img/06038cb1cd219389e961b5d06c0686c3_646.png)

Okay， let's go。嗯。Not sure I like that。

![](img/06038cb1cd219389e961b5d06c0686c3_648.png)

Yeah， maybe I should be a little that lasting。5 now that we change that。



![](img/06038cb1cd219389e961b5d06c0686c3_650.png)

![](img/06038cb1cd219389e961b5d06c0686c3_651.png)

Yeah。😊，But this should be stronger。And this should be a little bit stronger。

And then we should also like。In the ball of date ball， yeah。起 make。



![](img/06038cb1cd219389e961b5d06c0686c3_653.png)

W strong。Has to be really snappy to feel good。口？Okay。Okay， now that's cool。Okay。

 I think this is looking nice。

![](img/06038cb1cd219389e961b5d06c0686c3_655.png)

Maybe it's a bit too much。

![](img/06038cb1cd219389e961b5d06c0686c3_657.png)

Yeah， we can play around with these values like forever。



![](img/06038cb1cd219389e961b5d06c0686c3_659.png)

But for now， all I'm going to do。

![](img/06038cb1cd219389e961b5d06c0686c3_661.png)

I'm going to change both collisions， bar collision。Yeah third collision with。Thirdly， player。

Here stop doing like theyre neither and a half size。It's less than。Arena left most left walls stuff。



![](img/06038cb1cd219389e961b5d06c0686c3_663.png)

We a rifle。So now the ball will collide， not sure if it's going to be like a weird behavior。



![](img/06038cb1cd219389e961b5d06c0686c3_665.png)

是。不道。

![](img/06038cb1cd219389e961b5d06c0686c3_667.png)

It was a weird behavior， but。I think we are wrong， like before even。



![](img/06038cb1cd219389e961b5d06c0686c3_669.png)

Okay。This guy， minus half size x should really just be。During like。



![](img/06038cb1cd219389e961b5d06c0686c3_671.png)

Let's try doing it。

![](img/06038cb1cd219389e961b5d06c0686c3_673.png)

Was it desire to pe lastly arena？Oh， dude， I have to rename these guys。 This is the third time。

And I had the same error。Third time。

![](img/06038cb1cd219389e961b5d06c0686c3_675.png)

Let's keep counting。That was stupid。Okay。Yeah。

![](img/06038cb1cd219389e961b5d06c0686c3_677.png)

You can't really do that。 Oh， okay， well。It should。Also use down here。If we are to do that。



![](img/06038cb1cd219389e961b5d06c0686c3_679.png)

Okay。What？😮，That was really wrong。TheRight side。 Let's review that。 Well。

 no one's gonna die if we don't actually use the wall。



![](img/06038cb1cd219389e961b5d06c0686c3_681.png)

But let's see。If we are greater than the half。

![](img/06038cb1cd219389e961b5d06c0686c3_683.png)

Nい。嗯。I know that doesn't look robust。You guys saw that bug， right？Yeah， okay。

 let's do that of the top wall。

![](img/06038cb1cd219389e961b5d06c0686c3_685.png)

And。Ona top wall。Okay now。In the rendering， okay， let's do that。Marna left。

When we initialize these guys， I also initialize the talk wall。Top walls might be this guy。Yeah， now。

 if we collide with the。查。P。啊。About that。Okay。😊，Left in the clearest creed。Yeah。

 we also have to consider that。This guy's going to be。他。And。In fact。I didn't know if I actually。

 yeah I did the P there。Right top。Yeah， and then whenever we do the ball。Here。You should add。



![](img/06038cb1cd219389e961b5d06c0686c3_687.png)

M。To the top ball， feature DP。

![](img/06038cb1cd219389e961b5d06c0686c3_689.png)

Maybe I should just like the。Block，那个是 just not。Create in blocks just so you can play around the ball。



![](img/06038cb1cd219389e961b5d06c0686c3_691.png)

![](img/06038cb1cd219389e961b5d06c0686c3_692.png)

Well。

![](img/06038cb1cd219389e961b5d06c0686c3_694.png)

I was really wrong。Half size。嗯。Yeah。So it's going to be the target is the half size wide。



![](img/06038cb1cd219389e961b5d06c0686c3_696.png)

![](img/06038cb1cd219389e961b5d06c0686c3_697.png)

Okay， nice。Ill getting doing it。Something is wrong with a right wall。



![](img/06038cb1cd219389e961b5d06c0686c3_699.png)

And a top wall。Top all D have size wide， top P。就topDDP。Top1 d p。插薄片。Yeah。Be a top宝 P宝 D p。Yeah。

 put that in the wrong place。

![](img/06038cb1cd219389e961b5d06c0686c3_701.png)

Okay， that's pretty cool。Now if we get off the screen， we go back。Just better than we were， suppose。

Still weird。D， that was awesome。That's really cool。嗯。



![](img/06038cb1cd219389e961b5d06c0686c3_703.png)

So we have this problem。Oh， the problem is when we add too much， I suppose。When this hit。Yeah。

 because yeah， since we are moving。Yeah， thing is we are moving the wall when we collide the ball。

 but we are also moving the ball， so we keep pushing and for every time we add 30。

 so we should just set 30 minus 30。Plus， has no effect。



![](img/06038cb1cd219389e961b5d06c0686c3_705.png)

す。

![](img/06038cb1cd219389e961b5d06c0686c3_707.png)

Okay， now actually solve that bug， I suppose let's see。It kind hard to get the same。

The sameme behavior because the problem was it was like close enough。So it would keep colliding like。

Let me try to get that to work。So I have to do like a collision with not much as as like this。Yeah。

I think this is cool。Yeah。Like。The ball doesn't want the ball。Ya。What do you guys think about that？

Maybe we should just。Add。An next velocity， the ball when we hit it。



![](img/06038cb1cd219389e961b5d06c0686c3_709.png)

Okay， so this is good。But I'm gonna嗯。I see you're going to invert the ball X。

Maybe you should do like you the ball X then you say that the ball。DP，X。This one is negative， right。

 so this is the maximum。Let's do that。Before we invert， let's say we are like like one。

So we want a little bit more， so this one's going to be the min。Maybe 30， 30 is too much。

Think there is。That you like。F， this is3。30 andD Px。Because the idea is。



![](img/06038cb1cd219389e961b5d06c0686c3_711.png)

If we， if the ball is pretty low， like you guys saw。

Just going to add a little bit of velocity like let's see。Oh， that didn't do much， did it？



![](img/06038cb1cd219389e961b5d06c0686c3_713.png)

It actually， it was slower。嗯。So it's the minimum of 30。



![](img/06038cb1cd219389e961b5d06c0686c3_715.png)

Yeah， I think I got it wrong。This。

![](img/06038cb1cd219389e961b5d06c0686c3_717.png)

Yeah， okay， An let's see。嗯。

![](img/06038cb1cd219389e961b5d06c0686c3_719.png)

Not sure。I'mNot sure that is correct。So， the ball。Oh， she just clamked it。然第一句。So I'm going to clamp。

 clamp F。Mus30val D P。Well it can be zero， that's the problem。In this case。

I'm going to add a breakpoint here， game 835。

![](img/06038cb1cd219389e961b5d06c0686c3_721.png)

Game  a 35。Let's see。So， the ball。DPX is 36。

![](img/06038cb1cd219389e961b5d06c0686c3_723.png)

So it should be still 36。

![](img/06038cb1cd219389e961b5d06c0686c3_725.png)

So。That was stupid。

![](img/06038cb1cd219389e961b5d06c0686c3_727.png)

That's see。Okay。And I think this is going to work nicely。This is called getting rejected。



![](img/06038cb1cd219389e961b5d06c0686c3_729.png)

Maybe 3 is too much。Still。Maybe we should make it like。好啊。ですか。



![](img/06038cb1cd219389e961b5d06c0686c3_731.png)

Because we want a little bit and if if the ball pushes it a bit， it's okay， it does look nice now。

 it's not like a ledch like the other the other time。Yeah。企点。嗯。So the left wall you do it。

 but the print is super cool， yeah， the left floor is not working。😊。



![](img/06038cb1cd219389e961b5d06c0686c3_733.png)

Max it again。

![](img/06038cb1cd219389e961b5d06c0686c3_735.png)

Yeah， that's1。数。Looking nice。And do need to do that in the top。Just because。Yes to the left。

It's not working。Because the top also always have have a speed。

 like this okay so both of them are not worse。

![](img/06038cb1cd219389e961b5d06c0686c3_737.png)

You get the match between 10。And a Dp。Maybe it should be dirty。But I can just。



![](img/06038cb1cd219389e961b5d06c0686c3_739.png)

But once again。Because I'm not very I。 I wasn't very confident with that visual result。 let's see。

The D P is 22， so it should still be 22。 It is。Let's see what it looks like。

I can't see what it looks。42， to 42， yeah。

![](img/06038cb1cd219389e961b5d06c0686c3_741.png)

Yeah， I think it's going to have to be 30 or maybe have this guy be like 25 or something。



![](img/06038cb1cd219389e961b5d06c0686c3_743.png)

Now， let's do 30。The ball gets pushed a little bit when it hits the wall。



![](img/06038cb1cd219389e961b5d06c0686c3_745.png)

If it's not fast， if it's not a， yeah， if it's not fast enough。Yeah， I see。 That was pretty cool。



![](img/06038cb1cd219389e961b5d06c0686c3_747.png)

Okay， so now we have movie walls。Looking nice。 What can we do now， We can do。Color。

Timer screen shake， make。Oh， yeah， let's do though。Black。Well， game is looking like way better。

 that's the particle system back then。

![](img/06038cb1cd219389e961b5d06c0686c3_749.png)

![](img/06038cb1cd219389e961b5d06c0686c3_750.png)

Oh yeah， we also need to do the position with the player， so player。Movement。Player well collision。

I'm going to do arena left。Right。Well， that was。

![](img/06038cb1cd219389e961b5d06c0686c3_752.png)

开 was写。Yeah， that's it。いになす。

![](img/06038cb1cd219389e961b5d06c0686c3_754.png)

一时候。How that works。Yeah， we do get pushed。That's pretty funny。Yeah。Yeah。

 so this kind of makes the player not want to。Stick to the edges， which is great。Kind of， I think it。

Next。Let's go。Oh no， yeah， see。 So the bow is not going to keep the edge too much。

 which is more challenging and more interesting。Do commands go。Yeah， it is more challenging。

Yes suppose。Yeah。Okay。Let's see these guys。Do that awesome。



![](img/06038cb1cd219389e961b5d06c0686c3_756.png)

Let before doing particle systems， let's do three ball collar pretty easily here。

We have the destroyed on DPI down。So let's do like the trail。Rer balls。Let's call that a trail color。

A caller is this guy。If。The包。Flas， if the ball is supposed to。

They write an DPI down the trail collar。Let's made it like full Marine。

Or maybe yellow because of the。All up。Missing semico before constant。



![](img/06038cb1cd219389e961b5d06c0686c3_758.png)

No， that's not the problem I was missing in equals。



![](img/06038cb1cd219389e961b5d06c0686c3_760.png)

Okay， let's see。Yeah， if we speed up the DP。Which is what we did there。Menally， I mean。

 it's not going to be a final game， but if we do。The player position gets all crazy。

 I don't know why。Could also change the comment color。



![](img/06038cb1cd219389e961b5d06c0686c3_762.png)

然后。

![](img/06038cb1cd219389e961b5d06c0686c3_764.png)

嗯。Yes。啊。If the bow comment。Or we don't do that we do like。Comectテ。Its greaterter than0。

Would you like for red。Comect。I'm thinking about。

![](img/06038cb1cd219389e961b5d06c0686c3_766.png)

Yeah， now okay， this is， okay。

![](img/06038cb1cd219389e961b5d06c0686c3_768.png)

ですか。Yeah， the sprinkles nuts if we speed out the Dp。Dude that was awesome。N Ket is awesome。

this is so so cool。Oh， strong blocks。Oh， strong box and comet。That was cool。

strongtrong ball's pretty quick， I think I'm going to remove the inta kill one because it's not that fun to me。

 oh we shouldn't， yeah， the trail should last a little bit longer even though the ball isn't alive。

 I suppose。Yeah， we got three con of what？What is that？



![](img/06038cb1cd219389e961b5d06c0686c3_770.png)

Okay， so few things。If the ball is not active。😡，I should maybe still draw trails。嗯。嗯。

Let's do it like this if the bus's not active。And。😊，Oh well。嗯。道。Well， anyways， let's just。

What type so like make？2。3。All trails。Not yet destroyed。When宝。De stride。And then a weird bug。

Let's see， let's see what time add to。5。Absode， is it7。呃。为。Pop。Maybe it wasn't just fast enough。

We're going to assume that was the problem。I'm going to do the same thing。Likeike。差。

So it's going to be the DPY。Right。Yeah。Okay， but we do have to make the three balls。

 I don't know if we put it like a flag。Oh， you can do like if's not active， yeah， do that。

 we use the destroyed online。Yeah。Okay， so if the ball is not active。And。It's not。A呀。嗯。

This is kind of hacky。So this is what we want to do。As it like this， if the ball is not active。

IfThe ball is active， yeah absolutely like this。If the ball is active。

 we're going to do all of that stuff。not。We're still going to render。These guys。Yeah。

And this is probably temporary so。Oh no， this is actually the ball rendering。嗯。No。

 I not going to do this， we' going to do it if the ball's not active。And。The ball。Flas。

All destroyed on the APIPI down。If it's not the starting you lie down， then we continue， okay。

 so most balls are not going to be。I'm to pass for that。 now I can， I can do that Oh， not， not this。

Since I'm going to spawn this guy on the ball position， I can do this after the。This is that。

Now I'm going to test if it the ball。Flas。ball active。



![](img/06038cb1cd219389e961b5d06c0686c3_772.png)

Yeah， then can do all this。Dpar。Okay， nice。And we should probably。Change them。The bow color。

 the shared color。The individual trail collar I suppose。Do that was awesome for the comment。

 but I don't know who cares for him。Yeah。Okay， no， this is just pure wrong。



![](img/06038cb1cd219389e961b5d06c0686c3_774.png)

We're going to keep that。But。30 guy。going to keep this， right？Which is positive。

Then it becomes negative， yeah。Keep that。But that's not the problem。

The problem was the coming back of the brain。W movement。DDP is the target。 is the half size y。Yeah。

I don't know。Let's do the block block。

![](img/06038cb1cd219389e961b5d06c0686c3_776.png)

Let's see if the target is the。Let's try just the one bounce thing， let's see what happens。Okay。

 one balance is good so。

![](img/06038cb1cd219389e961b5d06c0686c3_778.png)

I don't know what's the problem。

![](img/06038cb1cd219389e961b5d06c0686c3_780.png)

Let's try。Oh， maybe we're going to get really fast。But that shouldn cause that problem。Yeah。

Let's move everything。To left。Okay， accidentally。Do this hard。 Yeah， okay。That was pretty cool。

So I don't know what the problem is there， but I have to watch the video。



![](img/06038cb1cd219389e961b5d06c0686c3_782.png)

So yeah。A top 12 speed。Problem。InDo like episode 7。225。

Can make the three balls straight or not get started when blocked， or I didn't actually check that。



![](img/06038cb1cd219389e961b5d06c0686c3_784.png)

I'm not sure if we fixed that because I was watching for the weird bug。

Let's see it's going to be really subtle。 So it's hard to see。

And we're going to add a lot more of these few things just for us to get our。Our feet wes so speak。

Yeah。That trail was。Awesome。😊，Oh， you heard the controls， oh and。The school。

 please just survived for a little bit。Do this game modes curiosity。Let's see B。

 We didn't actually do anything with Bong today。 I think we' to have like one more stream of game field stuff before we go back to the engine because。

There are a lot of cool stuff you to do like we can do like change both sides。



![](img/06038cb1cd219389e961b5d06c0686c3_786.png)

This one。And。Let's see， color。Show timers， screen shake， make block destroyed animation。

Make Star live animation particle systems should do this first， basically。

And maybe it's screen shape after that。You can do like。Inrease。About sizeize。

Then we can do color show timers。Make block destroyed animation。Make start level。Animation。

Po independent yeah they're going to see the game pondg independent black movement。

 that's going to be really cool。Fing influence the ball speed。

 space invaders getting faster time moves， make a squeeze factor also have the s look。



![](img/06038cb1cd219389e961b5d06c0686c3_788.png)

So don't have a discrete factor acting too early， maybe you just have a site。 Yeah。

 this is like this thing you can actually see the square。In the middle， that should happen。

We are already like。A way better field gain。In this。And we did like for two and a half hours。

I think when we start playing around with the blocks animations。

 that's going to be way better and the thing about fuel is just add a lot of small animations， man。

Because。Animation is nice。 We love seeing animation like draws the attention， I mean。

 for this kind of。Game right that you want， it's an action game full of stuff going on so you want every little things will be animated。

And also have to change the colors this greens pretty ugly player green。行。The triism。

 the trio was like the best addition， also this question stretch， but。Just breakout more of like a。

Yeah， I know the trail was a nice。See， see that。And we need have rotated racks in our rangeer。

It's going to look way better the trail。 now it's kind of a pixelated。

 I don't know if pixelated is the best。Name for it。



![](img/06038cb1cd219389e961b5d06c0686c3_790.png)

Okay， this one's great。Okay， I think I'm going to answer for today's stream。It。



![](img/06038cb1cd219389e961b5d06c0686c3_792.png)

You enjoyed， you can definitely download the game， I'm going to post today's episode here on HO it dzd。

h。o and can also download the source code and play around with that。

And you can also watch all the streams， you started out， let me go back to my YouTube。



![](img/06038cb1cd219389e961b5d06c0686c3_794.png)

YouTube。com/ Dan day Dan。

![](img/06038cb1cd219389e961b5d06c0686c3_796.png)

We showed everything here on the stream。 We started out with the blank file and line by line。

 we typed and you saw。

![](img/06038cb1cd219389e961b5d06c0686c3_798.png)

From the very first beginning， and you can watch the whole thing here and now have a pretty cool game。

 don't be， come on。This is a pretty cool breakout loan。And it's going to get way cool。

 especially when we add audio。Things like that。Yeah， and with the paras， it becomes way cooler。And。

These crazy guys， right？When we had particle systems。It's going to be crazy the space invades one。

Let's see I think yeah。嗯， c。I don't know what's going on。With the arena。嗯。😊。

Maybe you should like live stream and chase this bug down。



![](img/06038cb1cd219389e961b5d06c0686c3_800.png)

I don't know。I think I'm just going to watch the video and then I'm going to start out with that bug。



![](img/06038cb1cd219389e961b5d06c0686c3_802.png)

We also found that bug on 22。36。Okay so that's it， I hope you liked it and be sure to check out the YouTube channel and the E page。

 just click download now it's for free， you can just take it to the download or if you want to drop me a tip。

 it's really appreciated。

![](img/06038cb1cd219389e961b5d06c0686c3_804.png)

![](img/06038cb1cd219389e961b5d06c0686c3_805.png)

And I'll see you guys next time， thanks for watching。



![](img/06038cb1cd219389e961b5d06c0686c3_807.png)