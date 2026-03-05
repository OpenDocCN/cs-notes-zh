# 【从零开始用C语言制作游戏】 p04 Making a game in C from scratch! Ep 04： -Programming Game Mechanics -BV18i421a7DD_p4-

Hello everybody， welcome to my new live stream where we are creating an entire game in C from scratch。

Now， last time we started finally working on the game。

Itself and I implemented some mechanics some ideas that you guys had and I also had and this time around we're going to keep doing that。

 but now we're going to structure a little bit more because I had a lot of ideas in a couple of days that we didn't stream and hopefully we're going to start building a more interesting game。

Now we started from a blank fire from nothing so you can watch the whole process ever since we first started you know typing the code every line you saw here on stream or you didn't see in this case。

 you can go on our YouTube page and watch previous episodes there were three episodes until now and you can watch them all here on YouTubes YouTubebe。

com/ Dan Z Dan。

![](img/2d11af16ffb245ab1947921d1bfbeeda_1.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_2.png)

And they can also download the source code on each IO， which is dazam。h。o and can go to the game。



![](img/2d11af16ffb245ab1947921d1bfbeeda_4.png)

And。Yeah you can download the source code you're welcome to give me a little tip if you feel so inclined but you can just download the game also and there is separate for each episode you can download the executable or the source code so yeah hopefully everything is clear and let's see where we are at in terms of the game。



![](img/2d11af16ffb245ab1947921d1bfbeeda_6.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_7.png)

So， we started。By just creating a breakout clone， that was the first。Part of the idea。

And then we started slowly， but we did to implement some new ideas of our own。

 So you guys dropped my ideas from the chat。 I had some other ideas。And。

We made some notes based on that， let me just try to get the ball up there。Yeah， okay。Yeah。

 now we're talking。And today we're going to keep doing that and maybe advance the game a little bit more。

Okay， so yeah， we also tried different kinds of shapes for like。The wall， this one is。

There's like the bricks overlap each other in terms of the Y position， see。

 and we also started doing the power ups we didn't actually finish。

 we just started playing around with it and we tried some other weirder shapes here。



![](img/2d11af16ffb245ab1947921d1bfbeeda_9.png)

The first thing I want to do。Its actually changed how we structured。



![](img/2d11af16ffb245ab1947921d1bfbeeda_11.png)

The idea for the gameplay and the code， because I don't know if you guys remember from the previous stream。

 we created this idea of a game mode。And we starting out with the normal one and then you guys had the idea for the wall and then we did the wall。

 we did a couple other ones， then we started doing the power ups that you guys also came up with。And。

Yeah， some ideas based on that but。I think the way I'm going to structure it is more based on levels instead of game modes and each level can choose whatever mechanics it wants for the level。

So I made a few notes。Some ideas that I came up with。

Based on what we discussed last stream and some ideas that I had， I think I'm going to start。

With four basic mechanics。Plus two extra things， so the basic mechanic is going to be the power ups。

I was sorry to implement there's going to be， I， I don't know how to call it， let me。

 it's kind of about hazards。Which is like the inverted power ups。These you guys want to avoid right。

 the powers and the hazards， and then I'm doing let me get my little。Okay， life。

Which the one idea that you guys came up with last time was the。You know， make the。

Blocks randomly revived their neighbor， their neighbors when killed。And I think what we can do。

In this case， is actually make a life system。And if the block。Goes from Max。That's its five for now。

2，4， it adds。Close one for its neighbors。So the idea is， if you have like。



![](img/2d11af16ffb245ab1947921d1bfbeeda_13.png)

A block here and a block here and a block here。Okay， and this guy。

 let's say this guy's a five and these are all four。The idea is you want to destroy these guys。

Before destroying this one。Because let's let's say you destroy this guy and then you change this one to four。

 these all become fives。

![](img/2d11af16ffb245ab1947921d1bfbeeda_15.png)

So。Yeah， I think it adds a little bit of a gameplay just because this thing。

 I think I'm going to make you have to move the player to the position。

So you have to move towards something besides the ball， right。

 you have to move away from something besides the ball。

This one you have to choose which blocks to aim carefully。And the other one。

 which I think is the coolest one in terms of mechanics that we're going to implement is the。

I don't know how I call that。I call that rivals。Which is basically two。Types of blocks。And two balls。

And。一曲。T？Of宝。Of block， let's say。Can only。Be destroyed。Byuy its ball equivalent。



![](img/2d11af16ffb245ab1947921d1bfbeeda_17.png)

Okay， so the basic idea is that， let me draw this idea。You have。Like。😊，I say you have。A red。

You know block of blocks and a green one and then it'll be two balls at play and you have to I know throw the green blow。

 the red ones and the red ones that the green ones are the other way around whichever so that's going to be cool and you can we can really know at interested that like making a。

Like every other role is a different color。ind of play the around with that idea before。So like this。

So if you shoot like a red ball through here， it's going to do like this and the green level ones are going to avoid。

The the red ball， maybe visually， maybe maybe are just， you know not going to collide through that。

 So I think these four mechanics are going to give you give us enough space to create the levels。



![](img/2d11af16ffb245ab1947921d1bfbeeda_19.png)

In an interesting fashion， and I think that pretty much sums up some of the ideas that we came up with here。

呃。And then there are two extra things that we're going to modify。

 the first one we already did start with that， which is the block layout。



![](img/2d11af16ffb245ab1947921d1bfbeeda_21.png)

Like are going to have。Like yeah， we already did that let me just show you some of the ideas like this one's the normal one。

 then we have the wall one， then we have the every other role then we have the spaced ones and we can do pretty much all crazy stuff I drew a couple of ideas。



![](img/2d11af16ffb245ab1947921d1bfbeeda_23.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_24.png)

One is like a circle of blocks。Something like that， so if you get the ball inside。

It's going to be all crazy inside here that could be pretty cool。



![](img/2d11af16ffb245ab1947921d1bfbeeda_26.png)

And another one that I already discussed here in the comments is the kind of an angled one that kind of looks like an arena。

Th that'' going to be cool because know they can play around with the angle they hit。

Things like that， black layout。And the last one is the block movement。

Now this is the original idea for the game， and I think this is going to be really where it's going to shine。

Because we're going to add different movements to the blocks based on the level and it's going to be kind of a meaningful move if you get what I mean。

 I'm going to talk about that when we get to them， but the basic idea is we're going to start implementing these ideas if you guys have any any things that we could add this basic setup。

 but I think that will be enough to get it started and then this game mode system that we did is going to become a。

Level system。I think that's what we are going to do。Gameplay ideas。 Let's see。

 We the up for each row。 already already did that。 That's the wall。Likes say startups。Yeah。

 I'm going to keep the power of ideas。More， yeah。And keep that idea of power of our is also had a。

Another idea of this one's that like three shots。Free shot vicibility and the other one was a Com。

 that's pretty cool， which is I don't know if you guys remember。

 I think it was the second live stream that was a bug。Wherere呃。

The X and the y got switched when they collided with the blocks like this case。

 when we hit the block， it's going to change the y velocity right。

 it was going up and that's going down。

![](img/2d11af16ffb245ab1947921d1bfbeeda_28.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_29.png)

I think I'm going to create a power up where it switches， which axisxes it inverts。So kind of like。

Yes， swaps， the S aes。The collision。The ball block collision。Invers。



![](img/2d11af16ffb245ab1947921d1bfbeeda_31.png)

So this way， I don't know if you guys can see that， but in this case。

 if you have like few blocks like this。And we hit this one instead of going like this。

 we're going to go like this。 So we're going to hit this one。 And then instead of going like。This。

We're going to go like this。It's gonna be a a little bit chaotic。

 so you you have like a block like this。 then you can go keep doing that。

 Maybe if it's gonna be interesting。 Maybe all we want to do in the comment is just to not change the axisxes at all and let it go like straight through。

 That could be cool as well like this。😊。

![](img/2d11af16ffb245ab1947921d1bfbeeda_33.png)

Or you know we're going to play around with that， so these are the three part up ideas。Block trainer。

 okay， so the blocks render reviving is going to be the live system。

And largely respond more more balls when killed。 This one's gonna be one of the。

One of the hazard ideas， so the hazards， I had a couple ideas for that as well。

It's going to be like slow paddle。That could be cool slow player let's call it that so kind of you move the your mouse。

 but it takes a while for the player to get there or maybe that's going to be just frustrating I'm not surem going to play around this some ideas。

Strong blocks。So that's the opposite。Of the。On the disability。



![](img/2d11af16ffb245ab1947921d1bfbeeda_35.png)

Because in this case， we can't destroy the blocks， so like in the beginning of the level。



![](img/2d11af16ffb245ab1947921d1bfbeeda_37.png)

You it's going to be harder because it's going to collect that， no， but。



![](img/2d11af16ffb245ab1947921d1bfbeeda_39.png)

More frequently， I suppose。Ex see， not sure。And the other idea was reverse controls。 Oh。

 I kind of like this one， reverse controls。😊，呃。That could be really hard in this game， not sure。

Just some crazy ideas just start having fun in terms of mechanics and they're going to start building levels off bat。

At this point we are here， we are in the more complicated game modes。Let's call that game mechanics。

你食。😊，Game mechanics。And after we do that， we're going to know do a cleanup or are we going to do that。

 and we're going to do a small field pass， and then after the engine improvements we can do like the actual levels。

And more gameplay exploration， so for now we're going to do like few levels with a lot of mechanics just to show that we have the mechanics and then as we have more ideas on how to distribute those。

 we can do like the level system。Okay， is that clear， if you guys have any questions。

 be sure to drop them on the chat so I can answer them？Okay。

 so first thing we're going to do is we want to remove this game what idea and do like level。😊。

Okay so it' was going to be like。I don't know。That was01 normal。You know to do level。0ro，2， wall。

Life， let's。Let's called it just wall。 Then we're going to do level 3。A stadiumium。

W's going to use the。The rivals mechanic。The world is going to use like all the other ones。

 And then we're going to do a level 4， which is the。The front part， this one。But let's see。

 I'm not sure we're going to get to that today， but hopefully you can do the mechanics。

 Maybe not all of them。 Let's see。 Okay， so stuff current game mode。

 we're going to have a current level。😊，In the game old state， we are going to have a label state。

 but for now， I'm going to delete that。And yeah， I'm going to read that as well。Yeah。嗯。For that。

Switch on current level。 You're going to do a simulate level。And actually， this one。

 I can take that off here。And。Simulate game mode。Yeah。

 we can do like the power ups here are maybe before the blocks。Youm going to do。And I didt here。Yeah。

Looks good。Okay。呃。Spawn power up。just have like power ups is the game old estate powers because now every。

Level could potentially have the power up。So I also have to do like random systems today。

 which is not going to be hard。Okay， the next part up。Just cleaning some code here。对。

Current game mode， blocks destroyed。Yeah see now the block is destroyed。

 we have to save in the block now whether or not it's going to give a power up。So yeah。

 our kind is going to be in the block， so let's see。啊。Per kind。Fer up。嗯。いや。Okay。Because now。

What we are going to do in the block destroyed。What you do like here？The block。Has it power up。

We're going to spawn。Power up。On the black be case， fun。A up。

We're also going to take now the par up topon。I'm going to do like this。Power up。Kind。Okay kind。

Kind like this。Okay。😊，Aarrupbs is not a neighbor， I think I call it like power。The squareir of。Yeah。

 I think I'm going to keep just like。Just doing something clean up。The reverse order。

 that's what we did。Okay， start game， missing parentheses。Before an email。Yeah。

 am I going to take a game or going to take a level。小来锋来锋。Advance level。False。The level。L count。

Level0， then I're going to add like menus later anything like that For now， all we're doing is just。

Changing the old system for the new system。Level is the L。M-1 have to add that。Current level。

 it's gonna be level。Coming of that， okay。Let's see， advanced level。 So advanced。Advanced level。

 and we're also going to create the last level。呃。Which is alcohol。Okay， advance level true。

Switch on level。Okay， so in case we are level。ze1 normal， that's it。

We're not going to do a paste one for now。But we do have the system the capability of doing that pretty quickly。

Level two wall we going to keep the wall one， construction also not going to do that。

W's the one that skips， right。Yeah。嗯。Current。TheLe， this is the initialization。来不。Okay。

 almost done current。Okay， this is the bar system。Make sure we remove to demo stage now every demo。

Potentially power up game mode。Okay。Its这。If we are invincible， start game with a current。

It's the restarted， actually。And we are to advanced level。Going to advance if a level plus one。Okay。

 and then we do the current level minus1， this is our developer sheet sheets。

Just so we can like change levels easily and stuff。Okay， see you late to game mode。

Singly change it to simulate level。Okay， now let's see if we broke something。



![](img/2d11af16ffb245ab1947921d1bfbeeda_41.png)

Apparently， we did not。Which is good。Okay。Okay， nice just remember we have like a couple of of cheats if we hold。

 if you press up we toggle the invincibility and if you hold down， you go like super fast。

This contest test like winning need the game and things like。



![](img/2d11af16ffb245ab1947921d1bfbeeda_43.png)

ok。Not for bit， now we just changed how the same words， but I think that was great， a great call。

Because not going to be way cleaner， what we're going to start implementing actually finish implementing the power up system。

So what I'm going to try to do now is just。They create block block just for testing。

Or maybe you could do， yeah， I still here。 We're going to do like if。The X。Let's see， if why。

Itqus zero， so if it's the first row。We are going to hey Marcus， hey again。

 we're going to do some crazy stuff now like you know。

 you through a lot of ideas last time today we're going to implement them as game mechanics。

 not game modes。So every level could use pretty much all of the ideas。

 So we're going to focus on the game mechanics and。It's going to be pretty cool。

 So Andre now is just finishing the power system that we started last time。

 which is going to be like the first mechanic that we can play around with。 It's going to be cool。

 Okay， so I'm just going to hardco that every block is going to have like a power up。😊。

Every block in the first row is going to have a power up， which is like the invincibility。



![](img/2d11af16ffb245ab1947921d1bfbeeda_45.png)

I don't think weve programmed that。

![](img/2d11af16ffb245ab1947921d1bfbeeda_47.png)

But let's just see。Yeah， okay， in this really now the the other ones， the one in the role。

 actually it shouldn't have the invisibility。 Yeah， they don't。



![](img/2d11af16ffb245ab1947921d1bfbeeda_49.png)

Okay， now let's do more interesting stuff with the power ups。Okay， all we're doing now is testing。

All we do now is rendering， right， So now we're going to do a little bit of a。Make them fall， right？

Y' going to fall at Taanny Unsberg。

![](img/2d11af16ffb245ab1947921d1bfbeeda_51.png)

Second。😊，Not sure if this is fast or slow。 Let's see。



![](img/2d11af16ffb245ab1947921d1bfbeeda_53.png)

Yeah， maybe enough。

![](img/2d11af16ffb245ab1947921d1bfbeeda_55.png)

Or maybe a little bit slow。

![](img/2d11af16ffb245ab1947921d1bfbeeda_57.png)

I see like 15。Then I'll also do the collision with a player， so if we have ADB， A AB versus oh。

 we change the name， right？Now it' is colliding， Maybe I should just keep the AB。

 So if it's colliding。When did the player。To your屁。Player half size。With power up。诶第。

And let's do that's partcode the power of half size。Our own have size。 So if we are colliding。We can。

Just copy that， we can deactivate the power up。So， Kaara。あ。Kind。Going to be equal inactive。

 And then we' going make him。Invinible。Right so for that， I think we already created the variable。

 but we didn't actually use it in links， I think we comment that。Invisibility time。

 So let's say we can give like invinviscibility time。 We can give like。5ive seconds of immissibility。

I don't know。呃。全在。Okay， and actually we should。We should a switch， based on the。On the power up kind。

 yeah。All up kind。Okay， so case we are a power up。诶。In case you are a power up。Intensibility。

Go you this。And we can， yeah， just just this from that， I'm going to make it in。Deult case。Okay。

 T looks， I'm not sure I don't think I'm gonna render the the sky。Yeah。😊，And then we can like。

Recolllide。And this guy would have to create。The power up。Havelf size sorry。All right。Exercise。

We go to that， can I do that？Do that。That'sO。Power of tax size。Well。

 I thought I did that for the other variables， I can just check out。No。

Where did I set everybody's half size？Oh， in the start game。Yeah。

 I'm not sure I'm going to have to do that， okay。Power of half size is not a F 32。It's a。V2， okay。



![](img/2d11af16ffb245ab1947921d1bfbeeda_59.png)

Okay， hello， Timmy， how are you doing？Finishing the power up system。 let's see。



![](img/2d11af16ffb245ab1947921d1bfbeeda_61.png)

How good is it， Okay， now let's collide， Okay， we do collide， but we are not invincible， right。

 we just set that variable。

![](img/2d11af16ffb245ab1947921d1bfbeeda_63.png)

So what we are going to do。Is where are we testing here if we are invinvincible？Or。

Not sure because we have a boolean for invincible， or maybe we could just hardcode that here because this is like test only。

 Yeah， so I think I'm going to。mGoing to delete the invincible。Variable and here if we press up。

You just to add like。I mean， while it was down。 Yeah， going to add。

Invincibility time going to add like。Lay tea。To that。Okay， so if invincibility time。

It's greaterter than0。We're going to draw us as invincible， right？

And we're also going to drain the visibilityibility time for the。呃，LDT。It's just DT。

 as suppose it's not last DT。Yeah， and invincible， if you're not invincible if。

Invinibility time is greater than zero。So we should actually do that。Or we test this after。



![](img/2d11af16ffb245ab1947921d1bfbeeda_65.png)

So now it should be invincible， I'm saying invisible， but I mean invincible。Okay， let's see。 Yes。

 There we go。 So if I let the ball go through， I lost。



![](img/2d11af16ffb245ab1947921d1bfbeeda_67.png)

Apparently this didn't work。If invincibility times greater than zero。No， I mean this。Yes是B shouldB。

If it's not。Ber than zero， right？Let's say less than equal。



![](img/2d11af16ffb245ab1947921d1bfbeeda_69.png)

Yeah， I still like。So you also should like add that to like the user interface to see how much time that you have see。

Okay， so we are working。 and let's just wait to see if we're going to。Stop being invincible or not。

After some time， yeah， we did。 Okay， looking good。 Now were do we're going to do the other part。



![](img/2d11af16ffb245ab1947921d1bfbeeda_71.png)

Which is the。Three shot。So the idea is when we have this power up。

 every time the ball bounces off us， it actually responds to extra balls that only live。For us。

They only help me， so they only go up if they start going down because they colled with something。

 they disappear。 So yeah I'm going to add I would have like a ball。

We have this kind of a ball system。As well as the bow speed multiplier。

Maybe I'm going to add now a ball struck， yeah。Let's start organizing that。Well， okay。

And it's going to have a P， a DP， a half size， a base speed， a speed multiplier。Okay。

 now we broke a lot of stuff。 right， now what we're going to do is going to have like a ball ball。

 Then we're going to have a ball。あ。Like power up。Balls， it's going to be two balls。I suppose。Okay。

 and this is going to be ball dot。Okay， so instead of ball， on this score is going to be ball dotted。

Yeah。Do that。You have signs， okay。Okay。Okay， yeah， I think we're going to have to change that code。

To work a little bit more genetically。Balls not a member of block。This one I shouldt have changed。嗯。

Paul desired P。Yeah。Either this one。But that's okay。在哪。What is I。First ball。どな？Oh， I think you did。

We did a lot more than we should have。I think， well， maybe not a lot more。Desire to pay。其实P其实。Okay。

 desire key。First ball movement。That's like ball dot design become ball dot。I only do quite a bit。

And both on remember block， same thing for ball。Well， not actually。Block。these to do by。嗯ん。😊。

If there are any questions， be sure to drop them in the chat。



![](img/2d11af16ffb245ab1947921d1bfbeeda_73.png)

But yeah， okay。 So now we probably didn't change anything， which is good， right， Let's see。 Okay。

 looks good。Now we're going to have to simulate the other balls。



![](img/2d11af16ffb245ab1947921d1bfbeeda_75.png)

First of all， let me think about this code because maybe you can reuse that you can do like a simulate ball function。

Oh， this's inside the block。So if we're not the first ball movement。Yeah。

 we want to have to change this collision thing。So we're going to do like block， collide。Yeah。

 we're going to do block collide with ball。I'm going to do it yeah。Okay。😊，Going to create。 Let's see。

And eternal。Let'd say B32。A do ball lot。很leaion。You don't receive a block。And a ball。Okay。😊。

And we're going to do， yeah， this is the bulb operation。That's what we're going to do。

I think I'm just going to straight up copy this code here。For now。Yeah。

 and then we're going to like do。Ball block collision and we're going to pass well。

 if we're doing ball block， we should pass actually the ball and block。Yeah。

 so ball is going to be the address of the ball and a block is just going to give be the block because that's a pointer。

Okay， now we're going to have to change everything back ball desired P， or we don't have that。嗯。

I may have to save that in thestruct， I's see。Alllow the desire to。Use that。Itll simulate。Game。Here。

嗯。Yeah。😊，Thing we're going to do like this。And then we can do like ball， let's see。

And then we do the I have the base speed， the speed multiplier。And let's do， like the。Desired。

I'mNot sure this is the best， though。But。Thing's going to work for now。It's going to be an arrow。

This one is not going to be a arrow， this one's going to be tall。冇。Yeah， okay。

Sourns out to be a very cleany， kind cleanup kind of day。Flow arrow。

But we need to structure from now that we have a more clear picture of what we're going to do in terms of gameplay。

 I mean， these mechanic and the levels。We have to create a nice structure so we can you know pretty much。

Do other things we want to do block， destroy redefinition。嗯。Where do we have a block destroyed？Oh。

He actually， we happy to。Yes。For this guy。pHere。So I is this paw power up。Okay。

 see test wind condition， samee thing。微信。三口了。哦到P啊到DP。Yes， okay。

 so that finish the blow to a collision。This。Let you take true。

Perhaps it's better to make the array contain all balls normally in bonus one and mark them as being bonus or not。

Yeah， I'm not sure about that。Because the behavior will be different enough。

That maybe you don't have to test it all the time。But that's a thing to keep in mind because we are going to have。

Let's see。

![](img/2d11af16ffb245ab1947921d1bfbeeda_77.png)

Maybe four types of balls definitely we're going to have three types of balls so we're going to have。

て know what？Yeah， I think that's going to be the best idea because the basic ideas are the normal balls。

 okay， the normal ball， the ball that only hits certain kinds of blocks。

Which is for the rivals mechanic。And then the ball that gets destroyed when hit and the ball that doesn't that that probably。

 I'm not sure， but the ball that。Guest destroyed。

![](img/2d11af16ffb245ab1947921d1bfbeeda_79.png)

When hit the block。So I think I'm going to do that。Your your idea now and yeah。

 we're going to do like。Des tried。This try。On。Let's say the stride on player on a。On D PY down。

Not sure that's the best name， though， but this， if we flag this ball as destroyed on DPY down when DPY is down。

Yeah， thanks that was a great idea that's the cool thing about streams， you know。

 because people some people really engage on that and that's the cool part I love when you got when you specifically give ideas because pretty much always good。

😊。

![](img/2d11af16ffb245ab1947921d1bfbeeda_81.png)

Let's see， so yeah， let's do that for now， so we have balls。



![](img/2d11af16ffb245ab1947921d1bfbeeda_83.png)

For now we have three balls and I'm going to do like the next bowl。嗯。

So that's the thing because when we free a all。We may have to tag that as not active。嗯嗯嗯。Yeah。😊。

So I think I'm going to do a。It fuels for flex， which is like the defined ball active。This兄的。

First one， going to do ball thestr。On DPY down， and you can do like a DPY up later on。So yeah。

 so we're going to have flags。太宝。Okay， I think that's going to be a cool system。And then。

That means that when we spawn new balls， we're going to have to go through the array。

But it's gonna be like a maximum six size or eight， I mean，7， right。Yeah， so not a big deal， I think。

So now whenever see ball。Maybe we should clean this up really， so we're going to start the game。

The ball， we're going to do like this one we're going to hard code。 We're going to do like the ball。

0。Do。Then we're also going to。Add the flag。朵啊包。Act。And then probably zero the array before。

 I'm going to do that we have a zero array。I think so zero array balls。

 have to change ball from balls as well。好。And then in the utilities。

 we have going to make a easy road。Like boy is 0。Alright， and maybe I maybe we can do like a。

Micro for that zero array is going to take the array。RightThen it's going to run a zero size。

 which're going to create。嗯。For the array count。No， we can do like the array size， size of array。

Yeah。😊，And then we have to do a zero size。And I went to hard coded for now。But。

Maybe later you can do like the meAT version of that。But yeah， not really important。Now。

 so this one is the， let's call it mam。 And then we have the。You 64 size。Yeah， I'm going do a names。

Who cares。I can just remember the man sets back。

![](img/2d11af16ffb245ab1947921d1bfbeeda_85.png)

Yeah， but I may have to draw the whole thing just for that。Pointer the value。And the size， okay。



![](img/2d11af16ffb245ab1947921d1bfbeeda_87.png)

So， ma'am。0 size。Andmes every definition。What。😮，I think I'm going to do a white star here。First。

 balls。Movement。Uneclar反译。Mamet redefinition。And not defining defining AM I'm using。



![](img/2d11af16ffb245ab1947921d1bfbeeda_89.png)

VC runtime train。Maybe I have to， maybe I didn't import it， yeah， that's where is it？

It doesn't see where it is。Oh， that's the answer for strings。I don't so I'm normally upset。Yeah。



![](img/2d11af16ffb245ab1947921d1bfbeeda_91.png)

Yeah， I don't。I think I'm just going to write my score one yeah。So four I equals0。

I less than size I plus plus。And I can do it like a U8 here， and I'm going to cast that as。Star。

Or maybe I can do it like a U8。A desk here。Yes。Li bit of about distraction here。

 but I think it's going to be important to have these helper functions。Okay。

 now Ill need to cast here， then to do test。Because 0。Just do that or maybe just dust。Yeah。一合心。

Ball undeclared， simulate， I just going to hard code。The ball as balls zero for now。

 then might have to think about it。Or maybe not， let's say， yeah。

 so this one they have to do for each active bulb。So yeah， I'm going to start working on that。嗯。

A recount balls。应不 just。To move。爆款。Ba not。A balls plus the red count ball。Ba。谁。😊，在。包片包皮。Yeah。

 and we're going to if。I see about flags。If we have the。Ball， active flag。OrIf we don't。We punch。嗯。

Missing parenthees before semicollon， where。嗯。Whats。If。You are。Ending。If that bit is set。

 that's pretty much all we ask。嗯。😊，No。嗯。Yeah， if that。equals0。すや。So we not active。No。

That's not a problem。It seems like coding here。Do think this is like an assignment version？

What is going on？What I'm trying to do is。I come。嗯。😊，What was the problem？Maybe it was like a cast。

Yeah， this is weird。Okay。And I have to staff through this code to make sure it works。

Pare with a ball。Okay， so for every ball。Okay。嗯。Oh。V dot's going to be ball error。Yeah。Okay。

 that's still bugging me。 But let's just keep going。 Do ball。 Yeah。

 this one has been hard codeed0 for now。Yeah， and then we set and then here we draw。

 So we're going to have to。Perhaps the compiler was confused by the use of。Yeah， single。

 single and inside if maybe， but that's correct， isnt it not， I think it is。Yes。

We bugged the compiler already。Okay。So ball is the desired key。

And then simulate level and then draw here。Maybe we can draw that before the simulate level we don't we don't do anything in the simulate level for now。

 so maybe。就种第。嗯。Where are we drawing the player？小定。To this。Yeah。感谢你。😊。

What to do then just for cleanup， so maybe when we have like。You're like players。Okay。ああ、そうです。好皮？ご。は。

Game over。We came over if any ball goes。 Maybe you can do that on the。On the ball movement。Yeah。

 when I do that。嗯。A is that？Here， as you like update。Well， maybe we can clean that up later。嗯。

Actually。We should not test it with the desired fee because maybe a block changed that。

But I think by this point， who cares？Yeah， who're going to test with the desired P。うん。Start。Game。

なってです。啊包。Re。好。Okay。Un initialized variable ball。啊。你喜欢。Just for my cleanliness of conscience。

 I'm going to set a breakpoint here。

![](img/2d11af16ffb245ab1947921d1bfbeeda_93.png)

At a game 317。Just so we can check out what was going on with that。

Because that's like a normal flag comparison thing。Is it not。Let's see。Ball， the flags are one。

 and the ball active is one。So comp is one。

![](img/2d11af16ffb245ab1947921d1bfbeeda_95.png)

Oh， yeah， she did not comp。See， what I wanted to do is this。If statement。See， now it now it's。Yeah。

 maybe all I should do like is。This？Let's see if this works inside Si8。And not the idea。Yeah。

 maybe it's just the compile confused， but。That's not like crazy code or anything like。



![](img/2d11af16ffb245ab1947921d1bfbeeda_97.png)

Okay。I guess that's correct， we can test that later on， but I think it's correct。Okay。

 so this case comp is 0。 and next time comp is  zero So comp。No， it's not correct。



![](img/2d11af16ffb245ab1947921d1bfbeeda_99.png)

Ending。Now， yeah， that's not it that's the basic idea。



![](img/2d11af16ffb245ab1947921d1bfbeeda_101.png)

Okay。That's sort of a fi expression thing。Yeah， the two day is the not。4 bits。

So let me see if you can see here in the watch window so we can experiment with that。

 Maybe you can come to a better understanding so。Yeah， so。呃。Oh，We lost the game。Okay。

Just going try the game here。Here， okay。So。If I do this test。

But I'm going to test with one just so we know the value。Yeah， this test this one because ball flags。

Is this in binary？You can't see that。 let me just few。 Yeah， see， it's the one。If we do not one。

 I don't know if that's possible， kind of stretching here。 Yes， okay， so if I do not this guy。

 see all bits are set except。The this guy。So we should really test。Yeah， I don't know。

 I'm going keep this test。 going to test if that bit is set， then we're going to do not。

 Maybe we should。 we could do like。If that bid is not set。Then we should， yeah。那是。



![](img/2d11af16ffb245ab1947921d1bfbeeda_103.png)

嗯。I don't know。

![](img/2d11af16ffb245ab1947921d1bfbeeda_105.png)

But I think you understood that part， Anna this is working， I think let's just test again。

 so its all good so the first ball。So one， it goes through the second ball。Yes。

Its zero and it doesn't go through okay。Okay。Now let's see if we are working， we are not working。



![](img/2d11af16ffb245ab1947921d1bfbeeda_107.png)

That's， oh yeah， because we didn't change the other condition。

So this has to be the same thing for the。Falls， let's do。I'm going to comment like Loendander Bas。



![](img/2d11af16ffb245ab1947921d1bfbeeda_109.png)

Yeah。

![](img/2d11af16ffb245ab1947921d1bfbeeda_111.png)

Yeah。So we are back at where we were。

![](img/2d11af16ffb245ab1947921d1bfbeeda_113.png)

But now we're going to do the thing that we wanted to do which is to spawn more balls。So。

I'm going to add the。Number of triple shots variable。Right。😊，And then， let's see the power of。

Everyone's going to have the power up， triple or shot。Right。And then。Here。

 if we collide with the power of triple shot。We are going to add a number。

A numberumber of triple shots。To add that。Okay。Part of tri。So if we collidide at the ball。Let's see。

 Play air collision with the ball。So if we do collect the ball。We're going to see if we have。

If we have the。Have a triple shot。We are going to decrease that。 And then we're going to do like。

 spa。Table。Shotballs。And I'm thinking where should we respond。

 I think we're going to do like a fixed position of triple shotss。

Like one for each side just to be more chaotic。Which is going to be more interesting visually。

And you can do them pretty fast， that's going to be cool too。So， yeah。Okay。So。Tnal。

Pide sponsorable shotballs。So we're going to do light for two balls。Yeah， it's just。

One phrase instance。We don't have to get the next free ball， right？Get。For example。好。😮，Okay。

 and then we're going to pretty much do the same thing we did when we initialized the first ball。

But we're going to do this for in this case here。So the Dp X。It's going to be。Let's see。I'm not sure。

Let's say 4045， I don't know， that's kind of random。The Px。

It's going to be whatever the first ball X for the player。You're going to get the player X。

So we'm going to do clear P X。Plus， the player half size X。 Oh， I'm sorry， DCD。

I am just going to get the play P and then for the。包。P，Y， I'm going to get the。Let's play your PY。

Plus， the player have size1。Okay， the ball based speed。

 I'm going to add a little bit more because the place is not going to collide with that。

 so it just for the visual purpose。Thevo DPY。That's just organize it。Well， DPY is going to be。

The ball base speed。75， yeah。And about Py robots have that half size。Case B multiplier， okay。

Maybe you can add like two or we could just get the first balls。It's beened multiplier。

But it's going to be faster anyway， so I'm not sure I'm going to set。

The ball active and actually just zero first。Which first 0。Just make sure getting。

 they arere going to that。The ball active。And the ball， I don't remember that destroyed on DPY down。

 Okay， we're going to have to program that as well。呃。

I don't know what's going on with a bitwise operators。They're all giving the weird error。 Oh。

 maybe because they are a macro。Oh， because I added a semicolon。What a stupid mistake。

I have to click that for a super mistake， wow。That was stupid way。That common thing。Yeah。😊。

No' need to do that。So the problem was I had a semicol in here。See， macros， Yeah。

 macros give weird errors。 So the we solve the problem here。😊，Because it ended on a semicolon。

 so just had like an extra one and the competitor doesn't care。So。哇哦。

Thank goodness we saw that problem now， right？Because that's an annoying thing to have lyinging around your code base。

 right？Okay， so let's go back at what we were doing。Yeah。

 so the problem wasn't with the B rights operators was with these guys。😊，Okay。😊，呃。

Get next available ball and zero strip。Let's go to utilities， we have zero size。

And we have zero arrays。Zerostruct。It's going to pass and we're going to receive thestruct。

We're going to do a zero size。Of that strut like this。And the size of that script。Re called it。1，2。1。

One， two， one， two， one， two， okay。Some people make practical jokes。

 reallyfin things with macros for the wow。That must be really a headache， right？

Yeah macros are not the most fun thing， but they are pretty useful。Wes then when we need it。So。

 internal。Well， we are going to end up having to do a separate file in a bit。

 but since we didn't rush and do that separate file last time around。

 we created like a game modes file， we ended up not doing a game mode at all so kind of ended up more interesting in terms of structure so we have to wait for the final structure of the gameplay base in order to do these compression things for now we're just going to dump everything in the game。

 C file okay， so get next available ball。I'm going to run through the bolt and probably we do a macro for that speaking of macros。

 we should do a macro for this guy。Because that's a headache having to copy that already writing all the time。

 right？So。Yeah， if ball。Pasm sorry， if ball flags。Ball active。So if the bow's not active。

Maybe you should zero thisstruct here。Like assuming they get next variable go block zeros for us。

good idea。嗯。Is it this。Okay， and if we are， I'm sorry， if we are not active。

We zero thestruct and then we return the ball。And here we can assert， I don't know if yeah。

 we do have a search， we can assert。Zero because that's in， we're going to do like infil code path。

That's also used for invalid code path。And I think we have to return anyway so I'm going to return zero just for the compiler。

Just like we did the invalid default case， which is nice to write instead doing a third zero。

 I'm going to do like an invalid。Code path。Lets go time。Which is just the assertt。

And I'm not sure whether or not I share the ad。呃。No， I shouldn't。Yeah。At curly braces。

 I was thinking about the kids where we do like a lot of es and stuff。

 But that's why we should use the comma operator here。 But if we get to that。

 we kind of to do that for now。For now this should work so we get the next available。

And then we do all these stuff。Looks good now。I'm going to do that twice。And set the first one。Yeah。

 I think I'm gonna。I're going to add a ball here。It's kind of an ugly hack， but just so we can。

Just so we can set this guy later without having to do an if for whatever reason。Thank you。Yeah。

 so we have to program this and actively。

![](img/2d11af16ffb245ab1947921d1bfbeeda_115.png)

So ball， oh， actually， just see what happens。

![](img/2d11af16ffb245ab1947921d1bfbeeda_117.png)

Yeah， we crash ball was no。嘿。Yes。😊，So yeah， let's do that again。That was weird。Okay， the first ball。

Should you run， okay， the second ba is zero and it is zero。So zero and return ball。

What fuck balls no。Sorry for curising。哦。

![](img/2d11af16ffb245ab1947921d1bfbeeda_119.png)

Yeah。Because we are， oh， that was weird。 We should pass this and not the pointer for that。Okay。

 let's do if you have like a zero stroke。

![](img/2d11af16ffb245ab1947921d1bfbeeda_121.png)

That was problem。We were passing the pointer of a pointer and then zero that zero in that。Okay oh。

 we have to reset that。Pick ups。When when do we die， okay？

First one goes through the second one and return the ball， it is a valid ball， okay？So yeah。

 let's see what happens。Oh， yeah。屎。😊，Okay。Now， we were out of balls。But that's okay， I'm sorry。

 that's not okay。This is wrong， I thought you couldn't have like two at a time。

But we can get a lot of r ups。😡，And in this case， we should have a lot of balls。嗯。😊。



![](img/2d11af16ffb245ab1947921d1bfbeeda_123.png)

Now， this makes me wonder if we have like we should have a more interesting。Thing like this。Not sure。

 so。So I'm not sure I like that。😊，I mean， that other array was going to have the same problem。

But in this case， what happens when we don't have more balls？Should we just return zero？

And see that we couldn't find a ball or we should just keep a list。

Of the balls in order they were respond so we can like reuse that， I think we're going to do that。

It's kind of ugly， but at least for now， just so we don't crash。

 Let's just go back to three and test that。 Okay， so I'm going to have a ball over then have to。

B it link to the other bars。嗯ん。Not sure I like this so。Thing is。



![](img/2d11af16ffb245ab1947921d1bfbeeda_125.png)

We have， were creating more balls if we have it part up but。

If we create like a lot more balls like this， it ran out of race size。



![](img/2d11af16ffb245ab1947921d1bfbeeda_127.png)

So what should we do that oh， maybe we don't have to worry too much about that because we're not going to be able to。

 yeah。

![](img/2d11af16ffb245ab1947921d1bfbeeda_129.png)

I think I'm not going to worry too much about that to add like a larger array size because the thing is the bug going got destroyed。

 we didn't do that yet。That's why we crashed on that case。

 so we added a little bit of an error margin， let's put it that way， our safety margin。

And we should be okay， okay， ball destroyed on the EPI down。When we collide。

When we collide with a block block。Do about block collision if we， if we are changing。The D PY。

 and if it's positive。It's negative now， so instead of just setting it to negative。

We're doing it here。We have to test well。Yes。The ball。I suppose。To be destroyed on DPI down。

We are going to destroy the ball。小包。Flas。诶。Ball active is not going to be set。

Okay so this is the trick Marcus that we can use。To unset a set bit。

So were kind of making a mask of every other bit except that one and ending that with the flags。

So that way can un that。 well， you could also。Yeah。😊，And that's what you're supposed to do。



![](img/2d11af16ffb245ab1947921d1bfbeeda_131.png)

Okay。Let's see if we delete the balls when we collide， and' see。



![](img/2d11af16ffb245ab1947921d1bfbeeda_133.png)

Okay。And we don't。

![](img/2d11af16ffb245ab1947921d1bfbeeda_135.png)

Funny thing， I think the balls disappeared when we lost， but I don't know why that happened。



![](img/2d11af16ffb245ab1947921d1bfbeeda_137.png)

Oh， we are zero in the array， okay， yeah so we should also zero the pickup array。



![](img/2d11af16ffb245ab1947921d1bfbeeda_139.png)

0 ball，0。Take upプ。Okay， that's nice。呃。But I'm still not sure。Why this didn't work。

Let's just for the break here then， I don't know。

![](img/2d11af16ffb245ab1947921d1bfbeeda_141.png)

No no patience to try to guess， that's just C。

![](img/2d11af16ffb245ab1947921d1bfbeeda_143.png)

If the value is wrong， for some reason。

![](img/2d11af16ffb245ab1947921d1bfbeeda_145.png)

Oh。Were put in the wrong place。有啥错没事呃啊。Actually， several problems that， first of all。No。

 we didn't put in the wrong place， but why didn't that break， I think that's correct， right should。



![](img/2d11af16ffb245ab1947921d1bfbeeda_147.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_148.png)

should have stopped here。Let's put a break point here。

 but the other problem is we're not calling that on the other balls， that's one problem， right？Yeah。

😊，And we should also test in case the DPUI changes because of the top collision， okay， thats。



![](img/2d11af16ffb245ab1947921d1bfbeeda_150.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_151.png)

More things to do。 Let's just see。It's funny， we're not hitting that breakpoint at all。I wonder。And。

嗯。

![](img/2d11af16ffb245ab1947921d1bfbeeda_153.png)

I know。I don't know that doesn't look good Yeah， I don't think yeah。

 for some reason we don't have break points enabled。



![](img/2d11af16ffb245ab1947921d1bfbeeda_155.png)

I don't know， it should be like a compiling thing。Pick ups。It's not picks。Out paradise。Yeah。

 now okay， now we can test the break point。 That was well we already find out a lot of problems。

 I just see if it breaks here。 Okay， does。 So the placement is correct， but we're not testing that。

 So let's do like do。

![](img/2d11af16ffb245ab1947921d1bfbeeda_157.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_158.png)

Yeah。😊，I to do that for every ball。So balls for every active ball。

So we may not want to do like full 32 of them。Because。We're doing that for every。

We're doing that for every。Movement guy。 you know what， I think I'm gonna to do a macro for the。

 What engine is this， We're doing it from scratch bam。 We started out with a blank C file。

And we didn't use any libraries， whatsoever， not even the C runtime one。

 we almost use that C runtime library today for MIMSAT， we said what the heck， let's not use it。

And yeah， now we are， I don't know if it's going to run because we' were changing the ball thing。



![](img/2d11af16ffb245ab1947921d1bfbeeda_160.png)

So yeah we did everything ourselves and we have some pretty cool stuff like we have game over and have wind condition and we are changing the blocks okay so we don't have more game modes。

 so that crashes。

![](img/2d11af16ffb245ab1947921d1bfbeeda_162.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_163.png)

We can do like invincibility mode。

![](img/2d11af16ffb245ab1947921d1bfbeeda_165.png)

And then the。啊。I press the wrong button miss little mode and then you can do like really fast stuff。



![](img/2d11af16ffb245ab1947921d1bfbeeda_167.png)

Oh， and then the ball move back， so we are going to crash at some point here because we I have a ton of balls。

 right？If get like more。

![](img/2d11af16ffb245ab1947921d1bfbeeda_169.png)

Yeah， I have to。But that was a tangent to answer your question。

 so no engine and you can watch the whole process of starting out with a blank file and getting to this point on YouTube because I streamed the whole thing。



![](img/2d11af16ffb245ab1947921d1bfbeeda_171.png)

So。If if you get this， this the first episode， we did three episodes so far。

 this is the fourth one that we're doing live now， you can watch from the very beginning of doing like a blank file and then we do the platform layer。

 we do the render， then we do some gameplay， then we do some collision。

 and then we start doing some gameplay exploration stuff and now we're doing the actual mechanics。啊。

Mart has asked， wouldn't be clear to use a separate booth for each flag。

 I know you use the last member， perhaps for the ball that important because there are only a few are using details。



![](img/2d11af16ffb245ab1947921d1bfbeeda_173.png)

Yeah， the thing about Bfield is that we should actually do like a helper function。

Wech you do like is。Active。😊，And fast involved。I think that's what I'm going to do。So。

 so it's nice to use because yeah， doing this kind of stuff。It's not so。Clear， but I don't know。Yeah。

 anyways， I want to do a。I want to do a microphonet this one。Going do like a4 each ball。

Just because I'm writing that a lot and I think pretty much， oh but that。Yeah。

 and I do like this for each all。😊，For each ball。So I don't know。

 maybe at some point we're going to do helper functions， Marcus to。

To don't do like the bid operations ourselves。But I know it's not too much work I think。

And unless we get like weird bit bugs， we did get that one that we the semicolon right。

 but that was a very stupid bugs， so it doesn't count。Okay， so we're going to do like for each。

Now here。Yeah， that's it。And then， let's。For each ball。啊。What did I do here？Did I。

Do you something wrong。Yeah the game got see。Yeah。It did do something wrong。Here it。Yeah。

 a four Oh because I yeah， this four， I shouldn't really open the。So for each。あ？For each ball。

 for each ball。Yeah。😊，That's going。Okay。

![](img/2d11af16ffb245ab1947921d1bfbeeda_175.png)

Oh， in just a Dan in case you want to check out the YouTube channel discipline link got here tell the link。

 YouTubebe。com/dayam。

![](img/2d11af16ffb245ab1947921d1bfbeeda_177.png)

Okay。

![](img/2d11af16ffb245ab1947921d1bfbeeda_179.png)

Now。Let's check out what happens with the balls， Okay， we respond。And they don't collide。



![](img/2d11af16ffb245ab1947921d1bfbeeda_181.png)

呃。Did't we didn't we do the？For not in the first ball movement。For every goal， oh yeah。

Preeveror bowl， do good test with the bowl and if。If it's also active。It's not active。



![](img/2d11af16ffb245ab1947921d1bfbeeda_183.png)

嗯。Now， let's see what we have。 Then we should also do the top collision part。 That's gonna be easy。

 Okay， see， that was cool。😊，Oh， that's pretty cool。 Maybe she change like the color。

So it's not as confusing。But it's already pretty nice， I think。

 what do you guys think about that part up？I mean， it's not the most useful thing ever。

Because the thing about breakout is that you want to get a lot of points without doing much。But hey。

 you don't do much right by doing this part thing。You just stand there。

And it may be interesting in that case where you don't want to destroy certain blocks because of the order of the blacks。

嗯ん。Yeah， I'm not sure about that， but you're just playing around， okay？



![](img/2d11af16ffb245ab1947921d1bfbeeda_185.png)

So let's just finish by doing the let's just set the ball。包。What was that called？Let try to one。

 yeah， let's do this test。Let's do this test also on the ball wall collision。F， yeah。So if the ball。

Yes。😊。

![](img/2d11af16ffb245ab1947921d1bfbeeda_187.png)

Okay。I don't think we should be able to， oh， let's test that without doing the。



![](img/2d11af16ffb245ab1947921d1bfbeeda_189.png)

Change to the back。

![](img/2d11af16ffb245ab1947921d1bfbeeda_191.png)

How it was just for us to see what happens when the ball hits。The top part there。Yeah， okay。

 they disappear looks good， looks good and they don't render the frame they disappear。

 which I'm not sure。

![](img/2d11af16ffb245ab1947921d1bfbeeda_193.png)

If that's good or not。Maybe you render the very last frame they colled。

Or maybe we should that like an explosion and we don't even care right， yeah。

 I think we're not going to care about that。Okay。

![](img/2d11af16ffb245ab1947921d1bfbeeda_195.png)

嗯。😊。

![](img/2d11af16ffb245ab1947921d1bfbeeda_197.png)

So you have two power ups， the other power up， I don't even remember what that was。Comment。Okay。

 this is going to be interesting。So the comment is going to be a timer as well。

That the idea is that you should like。Help us destroy a lot of blocks。

Is Farcoder your main editorctor now， if so， when did you make the switch and made a switch pretty much when I discovered Farcodeder because that was when I really started programming for real。

So I started using Iax because that was what I was being taught at handmade Hero。

But I didn't even like EmX that much。 I didn't get just the key findings I thought that was weird and things like that。

😊，So at that point， Forgo was already out。So I was watching some episodes from the future and then I realized that Casey did the switch later on。

 so I was like， okay， let me check that out and I loved it so I made a switch pretty much immediately so。

It's beenI don't know how much time it's spent。Maybe a year。Yeah， actually。

 I think it's been more than a year。Yeah， maybe a year and a half。Maybe a little bit more than that。

Now， temperature has been an year and a half。Then I've been using for code， yeah。Or two years。

 I'm not sure， but yeah， it's my main editor， I really like it， Okay， the comment。😊。

So we have like an instibility time in seconds。Left do the comment type， time。Comment。

 so it's pretty much the same thing as the invincibility so。We have now oops， yeah。

We have like the comment。We're going to add the comments type。Invincibility。Comment。Finally。

 we're doing things quickly now and okay， that's it。

And we're going to change the test to triple shot。People shot。To comment。Okay。Good。

 thanks for doing like， oh， no problem。 sugar， sugar hey。呃。

If you have any other question about the game about anything else， the program， brief。

 be free to ask。Okay， so the comment。We just added the time now this going to be。

This is going to be interesting because we have to do like the update comment here。Down here。

 for instance。If the comment time。Is greater than0， or maybe you should just decrease it。 Yeah， no。

 its greater than 0 Come time plus equal D T。I'm sorry， minus equals Dt， right？Yeah。

 so we decrease every frame that we do have a come time。And the thing is。呃。When we do the ball。

 so do ball col block， this is where we want to play around with the comment， right。

 So the most simple thing we should do with a comet。It's like。Don't worry about this part at all。

 I mean， this part， which is changing the direction， right？But。Yeah， just for the fun of it。

 I'm going to do that。M if that， if。if come times less than or equal。But the problem is。

This guy should do should should。Should you know。Should be tested despite the commentt thing。Why not。



![](img/2d11af16ffb245ab1947921d1bfbeeda_199.png)

Maybe not。Then have three comments。 That's going to be pretty cool。Yeah。

 that's going let's do that for now， so let's see what happens when I get a comment。Okay， see。

That was pretty cool。Wow， that was a bit unpredictable Too much unpredictable， I suppose。 Oh we。

 we should also reset the guys。 Yeah， we should reset the。



![](img/2d11af16ffb245ab1947921d1bfbeeda_201.png)

When we do like game over？Start game。Yeah， I'm going to reset the insability time。'Goon to reset the。

Number of triple shots。 and the economy。

![](img/2d11af16ffb245ab1947921d1bfbeeda_203.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_204.png)

Okay， so that's kind of a cool idea for the comet。Because if you do like straight up comment， yeah。

 see。but it's too unpredictable， I mean because it's pretty fast and by the very end。

 it changed its direction。Maybe I should just do the X。When going up。

Or maybe just do the commentment going up。

![](img/2d11af16ffb245ab1947921d1bfbeeda_206.png)

And then it。Okay， that could be cool。 Okay， let's do the comment thing。😊。

I'm only going to test a comment if the ball is going up。Okay。So the basic idea is when it goes up。

 it goes like crazy when it goes down。

![](img/2d11af16ffb245ab1947921d1bfbeeda_208.png)

You're going to do the normal path。I think think。Let's try that。Okay。Okay。See， that's pretty cool。

Maybe it's going to be a bit too easy with a comment。Because it pretty much just punches a hole。

And then keeps going like this。It's okay， yeah， we have a lot of comments right， so it's not。啊。

I don't know， I think going to be， I think it's going to be cool。Maybe if it's too strong。

 we can like。Yeah， well， I was pretty bad at that。ok。It's pretty cool， I think， yeah。

 when it's going down， it's not oh， it's a little bit unpredictable right， so yeah。Okay。

I think I enjoy that。For comment。At least for now。So yeah， so we did the。Power of mechanics。

 now we're going to do the headers mechanics。So the idea is having these mechanics in hand you're going to build like three simple levels。

Just that play around a little bit with these mechanics。And then we can do a full on。

Pass on the engine。Before we do the。Or the levels。Yeah。



![](img/2d11af16ffb245ab1947921d1bfbeeda_210.png)

Okay。Yeah， I， I'm not like a hundredunch and happy with that。 but let's just see what's gonna happen。

 Power up ideas。 You did all the power up ideas， hazards， slowlow player， strong blocks。

 Let's do strong blocks first， Re controls。 Re control is gonna be weird。😊。

Not sure if that's going to be fun， let's try that after strong blocks S。

 I think that was another idea that I had。うん。😊，嗯。Yeah， we could do instant that。

The one that you have to avoid， but the problem of doing is a death hazard is that if it get stucked between an instant death hazard and the balls like here。



![](img/2d11af16ffb245ab1947921d1bfbeeda_212.png)

You have to go through I don't know， maybe if you're fast enough。



![](img/2d11af16ffb245ab1947921d1bfbeeda_214.png)

Foling blocks。You wait for it Marcus， you wait for it， you know。

 we are going to do the block movement part。Because that's the basic idea that I decided to split the gameplay。

 we're going to have four major mechanics， which is the power ups the hazards， the life system。

 which is going to include the idea that you gave last stream。

 which was the if the blog goes from Max。Life， let's say it's five to four。

 it adds one to its neighbors， So it's going to be a pretty interesting system where if you have like this。

 let's say it's a five block and this is a four block and a four block。



![](img/2d11af16ffb245ab1947921d1bfbeeda_216.png)

And for a block like this。If you hit this guy。These become five blocks。

So it pretty much made the problem worse， right， so you have to first hit these guys and then this guy。



![](img/2d11af16ffb245ab1947921d1bfbeeda_218.png)

I think that's going to be pretty cool。 So yeah， after。😊，Yeah。

 so that's the other namely idea we could add blocks that change size when hit。

To the license system as well， I mean， if the block， like if the block。Goes from from。

 let's say the max is5， so54 it has one to negative if it goes。Let's say。The block goes from four。3。

Itll decrease the size。That was a cool idea。And then we could do like one for each of a live。

 I don't know point。That could be cool and do like two more。And then the other mechanic。

 the rivals one， which is you have to destroy the block with a specific type of ball。

 then there'll be two balls at play， a minute it's going to be pretty cool。Then okay。

 so those are the mechanics let's say and then we have the block layout and that's what we played around with last time that we have like the raw idea and we have like the idea and things like that。

 so that's going to be available for us to change in a level by level basis。😊。

And then I have block movement and following block is going to be the just the starting point。

 I have so much cool idea， cool ideas for that system。😊。

And I think that's going to be the charm of the game， you know， playing around。

With how the block movement play， I know， integrates with the other mechanics and things like that。

 that's gonna to be really cool。 So yeah， blocks， following blocks。😊。



![](img/2d11af16ffb245ab1947921d1bfbeeda_220.png)

Are a major thing in this game， I'm pretty sure it's going to be a lot of fun。



![](img/2d11af16ffb245ab1947921d1bfbeeda_222.png)

Okay， so hazards。So all I want to do is pretty much copy。The power system。

 And maybe we can try doing the， the。Thanks to death。Okay， so I'm just going to change from power up。

To hazard， I don't know if hazard is the best name。I don't know。Hazard。It's called intaill。

Then we have what was that again？Strong blocks， reverse controls in slow player， okay？So。

 it's strong。Blockox。Reverse。Controls。And I still clear。Not just lopeping is going to be fun， though。

Per downs。Okay。F downs。I think that's better than hazards because hazards are a different thing。

 right？Yeah， so far down kind。And you know what， maybe we should have the same thing for the power up and power town。

So we can make like them， think anything like that。So you know what。

 I think I'm just going to call the power。And。Consider that they are the same thing。

I think I'm going to do that， let's call them。Power ups。And there's going to be the power downuns。

I just had down ups。Power downs。 Okay， that was a cool idea。Okay。

 so no power down kind just power kind。What kind of power do we have in our game？Okay， so power。

 just power is weird， right。Maybe you should call them collectibles then。I don't know。

 let's deep power for now。Power。Yes。Not sure how with that。Collectible， I'm going to do collectible。

Drugs so good so bad。 You're telling you that。 I don't know anything about that。ふふふ。😊。

I'm going to do like coal with。2 else， cold。Collectibles。公開。Yeah，Our pills。Yeah， feels like peman。

 right？Yeah， so it's kind of a drug， right？I'， let's do like collectibles for now。

Then we can play around with the。With a subliminal message part of it， right？好嘞。Oh。

 col is also two else， I thought it was one also。Collectibles。Yeah。嗯ん。

I think we' call them power block that I'm taking too much time。😊，With this。But I don't know。

 part of black。😊，Far block is a nice thing。Har block。Okay。Because after all， it is a。

Block kind of game for power blocks， next par block。And power block。

Size row line makes more sense right， power block have size， but it's a block。Power block kind。

So whenever we see up， I think we can do that， we're going to change。To block。Yeah， let's do。 Okay。

 Yeah， that word。To many of them。Power block。Kind。Itspon Bar block。Our lot。

Power blocks plus next point block。Power b， a power helmet。Our black。可以。And power inactive。

I think I like that。Then we can probably do like the separate functions。Part black kind。

Its course inactive， okay？I'm going to do the first。

 let's just check out if it's working already if we broke something。



![](img/2d11af16ffb245ab1947921d1bfbeeda_224.png)

Let's see。Okay， that's the client looks good。は。Yeah。So we do have to keep an eye on the comment。

 right， because it is pretty crazy。But it is good， right？The area too unpredictable。Okay。Okay。

 now we're back to normal。啊。

![](img/2d11af16ffb245ab1947921d1bfbeeda_226.png)

Imagine a triple commentt yeah， I want to try that。Just for the fun of it。Yeah。😊，Let's do like。Co't。

Okay。I'm going to hack a if。X。Two we're going to do this。Else we're going to do。結構。



![](img/2d11af16ffb245ab1947921d1bfbeeda_228.png)

Partars to be compos。 yeah， that's the thing。 Okay， all good Oh， I， I missed it。 Oh。

 that was very stupid to me。 Okay， so let's do。Okay， so that's triple。 and that's a comment。 Wow。

 that was crazy。 Let's see。 triple comment。And it gets so fast when it reaches higher speeds。Wow。

 this is crazy。That was really fun。Thats great。That was pretty cool。

That's if you can get another one。missed it， okay。

![](img/2d11af16ffb245ab1947921d1bfbeeda_230.png)

That was cool。し。嗯。We should probably do like the。Probably do the rendering so you know which one is which。

Not for now。 Okay， so power。We're going to do the power catch of things to death used to kill one。

The more powerful powers could be connected to this yes exactly。

 and I think they're going to be higher on the wall and at one point they're going to become。

Per down。So when you destroy the higher block， it's going to be power downs that fall and another one wants power ups or the other way around。

yeah， we can try both。But that's going to be on the level。Expermentation part， you know。

 when we get the the mechanics down， you guys can， you know download the source code on HIO and just play around with the levels and create a couple levels yourself that thatll be pretty cool yourselves So insta kill when we collide。

😊，I'm going to。嗯。Let's see， I don't think I can do like a start game at that point。

s word red game over that。Over分。We don't have。Did comment the game over。

 I do like start the level start。ケ？Current level。Yeah。😊，Just come to that。Okay。

 so this is in a simulate game。So I guess we can do that。嗯。



![](img/2d11af16ffb245ab1947921d1bfbeeda_232.png)

Actually， I'm not sure because I don't know if you guys remember last time around I have a problem if。



![](img/2d11af16ffb245ab1947921d1bfbeeda_234.png)

If we started the game。哦对的的。Start game， they'll next start game， does it？No it does。

 it sets the advanced level to false。Maybe， maybe。Yeah。

 maybe the advanced level should be like next level。是。I don't know。

I don't want to work worry too much about that for now， not sure how it's going to turn out。

 but maybe I'll just hard code that the。The start game current level。

We should do like start level instead of start game。



![](img/2d11af16ffb245ab1947921d1bfbeeda_236.png)

Let's see oh we should also do like that。

![](img/2d11af16ffb245ab1947921d1bfbeeda_238.png)

Let's do。Power is。

![](img/2d11af16ffb245ab1947921d1bfbeeda_240.png)

哦。Yesす。

![](img/2d11af16ffb245ab1947921d1bfbeeda_242.png)

Okay。You should also change the color， at least。Yeah。😊，Yeah， okay， oh。

 because we didn't reset that the yeah， that was the problem。



![](img/2d11af16ffb245ab1947921d1bfbeeda_244.png)

If we set the。Start game here。The ball。This thing changes， which is the ball。Or yeah。

 I think what I'm going to do is a little bit of a heck。But you need to start game。

I'm going to also set。钱包。Desired P。To be the， the ballpe。And we also have to do that with a player。

Player desired P equals。Yeah， it's a bit of an ugly hack。T that P on thelar fire。 Okay， so。

Let's take this as a hack so we can think about that later。



![](img/2d11af16ffb245ab1947921d1bfbeeda_246.png)

O。

![](img/2d11af16ffb245ab1947921d1bfbeeda_248.png)

Okay， now it's better。So it the queue， that was easy enough。Now， let's do the。I don't even remember。

Once。Strong blocks， let's say strong blocks。That to like strong。And by strong， I mean invincible。

Strong blocks。t。Yeah。Plus equals 5。 I'm going to change time to2。Yeah， so invincibility。ok。😊。

It's going to be the strong。Rox tea， I have to go。 I'll watch the rest later。 Good luck。

 watch all those semi Cols。 Okay， Marcus， thanks， gladla to drop by in the stream。😊，呃。Yes。

 stroke blocks。And now we're going to do。Bow block col test。And we're not going to do this。

And also it a test like a block。Okay， so we are only doing this。If the。Strong blocks。

 T is less or equal than20。It's less two are equal to zero， it's less than r equal to zero。

That's Englishlish problems not programming once。Okay。I guess that's it。 and all I have to do is。

Same thing did with a comment。Comit strong。

![](img/2d11af16ffb245ab1947921d1bfbeeda_250.png)

Bs， see once you get the hang of the probe of the。

![](img/2d11af16ffb245ab1947921d1bfbeeda_252.png)

Gameplay programming。Really starts。 Oh， I think I have Easter to kill。 Yeah， I do。



![](img/2d11af16ffb245ab1947921d1bfbeeda_254.png)

呃。

![](img/2d11af16ffb245ab1947921d1bfbeeda_256.png)

Strong black。Once we had the hang of the gameplay thing and the cohorts to form nice structures。See。

 now we're， now we're doomed。You can't do anything except wait for the timer。Yeah。

It's not as problematic。

![](img/2d11af16ffb245ab1947921d1bfbeeda_258.png)

That one would think。Maybe you should also add like a super fast vow one。Just have the fun of it。

Reverse control is located at Ana Sonica。I don't know。

 the ball is pretty fast by the end of the game， so I'm not going to do that one because we have slow player already。

But a look later， I guess you can compensate with that by doing a lot of mouse movement。

Guess there'll be a point of it。Yeah， strong blocks， reverse controls。Let's try that one。

I am a bad person， maybe we can take those out if it' it turns out to be not fun。

 but that's when we start doing the lot of things。Now its just two。

Just because I had these ideas and just want to pay around some of those。 Okay。

 I don't remember where the T。 Okay， strong blocks T。 and now we have the。

I don't think I need to comment themselves silence。 Let's just assume every underscore T。Me。Okay。

 the strong blocks。Now。Will be the。Reverse controls。The reverse are inverse controls。いverse？

Invert inverse invert control。Yeah， inverter controls。TK。So same thing we're going to do。Blocks。

Would be。Controls。And in case we hit。C controls。Oh。How that reverse control。Inveritive controls。

Contros。Inverted。Cse。Because that。还是的。Power。Another core thing。Very good controls。

And then here we're going to do。Okay， now。When we do the player of movement， let's do a player。

Desire to pe。Yeah。I didn't know， man。Let's see what happens。That's true if。呃。

Inverted control C is greater2。0。It's greater than zero。It's better than zero。 we do this。

I think I'm going to do a like bit less。And are equal to zero。



![](img/2d11af16ffb245ab1947921d1bfbeeda_260.png)

I don't know， that's Jey， it's probably going to be impossible。哦。Okay， it's not like。

And I have to reset all those guys。

![](img/2d11af16ffb245ab1947921d1bfbeeda_262.png)

Yeah。It's not like impossible。Yeah。But it is mad me。Okay。



![](img/2d11af16ffb245ab1947921d1bfbeeda_264.png)

And I think in order to make that work better instead of just reversing the position。

 like if you see now what happens？

![](img/2d11af16ffb245ab1947921d1bfbeeda_266.png)

I'm going to move him by setting the DP see so we don't snap。



![](img/2d11af16ffb245ab1947921d1bfbeeda_268.png)

诶。Oh， that was crazy。Okay。Let's do the let's dis revert that。Let we start the game。Insibility。

Comment a number of shots。The we're going to do is strong blocks。Go zero and inverted controls。



![](img/2d11af16ffb245ab1947921d1bfbeeda_270.png)

こ自。Yeah， I just try one more time just for the fun of it or the not fun of it。Yeah。

 the thing is want to avoid these guys， right， isnsn't that the point？



![](img/2d11af16ffb245ab1947921d1bfbeeda_272.png)

yeah。Okay， let's try。Doing the mouse Dp。So in the Windows platform。When I set the mouse pointer guy。

I'm also going to keep do we keep the old input？So。Oh， now we don'。

I'm going to keep the old mouse around， oh we do have the old mouse， which is the input mouse， okay。

So we're gonna to do。Eput mouse， which is the old mouse。Good do。Olold。

 I'm going to do like the mouse DP。Okay， so the mouse D P。It's going to be equal to。The new one。

 which is mouse pointer。Minus。有的 guy。ok。And I think I'm going to do this operation on the mouse pointer itself。

So I can just like set。Okay， so。Mouse pointer dot y。To be that transformed。MallesDp， no。

 let's make a mouse Dp。Oh， we are in pixels。Oh yeah， I guess we have to be。A mouse。

You' I call this mouse。嗯。Mouse mouseuse。Same thing here。Oh， we're going to do a sub V2 I。

Cannot convert。Every doing youre having a sub feet， subnormal feet。So。你就I。Okay。

Can't convert from point to B2。嗯。Mouse pointer。嗯。Yeah。😊，Okay。B2 I。

Cannot convert from the O at missed。Ofp this part。Mouse is not a manual of input， Now it's mouse P。

Muskey mouse比 O。Yeah， we're going to do the same trick。Actually， maybe we should just， I know。

 I'm not going to cast because。Maybe the spec changes and then our mouse pointers dos。Be right。Okay。

 that was。Grant work。

![](img/2d11af16ffb245ab1947921d1bfbeeda_274.png)

Now。Let's see， well， nothing should change really because we're not really using the DP。



![](img/2d11af16ffb245ab1947921d1bfbeeda_276.png)

But now instead of doing this。We're going to add。To the mouse pe。在地比。

I think that's the only thing we should do on initial lines variable。Yeah。

 the player desired P is going to be the player P。Dot X plus this guy， oh I'm turning minus。Yeah。

 if it's word。And here is going to be the player。あ。No， that was right。This one's plusli the O one。



![](img/2d11af16ffb245ab1947921d1bfbeeda_278.png)

Okay。Now we shouldn't snap the position， oh or not。



![](img/2d11af16ffb245ab1947921d1bfbeeda_280.png)

Or the initial position must be set。The initial exposition。



![](img/2d11af16ffb245ab1947921d1bfbeeda_282.png)

I think that's going to break a lot of stuff， actually。



![](img/2d11af16ffb245ab1947921d1bfbeeda_284.png)

Let's go to the game and initialize them。Yeah， here。The start game， actually， yeah， the start game。

Yeah， sure， yeah， I should set it zero， but it's already zero。



![](img/2d11af16ffb245ab1947921d1bfbeeda_286.png)

They P X。

![](img/2d11af16ffb245ab1947921d1bfbeeda_288.png)

Yeah， didn't change anything。Maybe these values are wrong。

I'm going to take out the inverted controls for now。



![](img/2d11af16ffb245ab1947921d1bfbeeda_290.png)

Just so we can test。We trying to do。And yeah， let's just see。



![](img/2d11af16ffb245ab1947921d1bfbeeda_292.png)

It's weird because I didn't move the mouse at all。

![](img/2d11af16ffb245ab1947921d1bfbeeda_294.png)

And the guy。Yeah， I'm not sure。

![](img/2d11af16ffb245ab1947921d1bfbeeda_296.png)

I' got a break point here， three，7 seconds。其实。The Blair P is zero。



![](img/2d11af16ffb245ab1947921d1bfbeeda_298.png)

The DP。Oh， the Dp is 355 because。We don't have a old mouth， right？This guys zero。

 so it's assuming we started out like here in the middle of the screen and then we just moved。

So what I have to do is。The beginning， I'm going to set the mouse。几。Yeah， so now at D P。



![](img/2d11af16ffb245ab1947921d1bfbeeda_300.png)

Okay。Let's just check out the breakpoint。

![](img/2d11af16ffb245ab1947921d1bfbeeda_302.png)

0， LCCP，0。 So it's going to be。It's going to be minus。Can be minus。Oh。Yeah。It's minus 92， I think。

Okay， let me try and do that again。Mo D P is 0，0。Oh， because  zero， zero。

I have to change that now it's not it's not pixels to anymore。Unless we do the calculations here。

 just a a little bit better。 Yeah， that was a。

![](img/2d11af16ffb245ab1947921d1bfbeeda_304.png)

What I am going to do。Do not save the mouse Dp in pixels。嗯。I'm thinking about it。

 so my options are I either save the mouse deep being pixels and fix this converter here。

Because we don't have to offset。We don't have to offset the standard because now it's just the direction right in the。

That's a factor， not a point。So it'll have to offset that。Maybe we should just do that。

So in our renderer， we have pixels。Tool world， yeah。And we're going to do like an internal。V2。诶。

Big saless， D P。To world。She's pretty much the same thing。But I'm not going to change。

The center position。

![](img/2d11af16ffb245ab1947921d1bfbeeda_306.png)

Yeah。Okay， I think it's going to work。Yeah， I thought the break just to。Okay。

 so the mouse P is0 and this guy is minus92。 Why was that？Oh， we didn't call it。



![](img/2d11af16ffb245ab1947921d1bfbeeda_308.png)

That was pretty smart， right？Excels sleep B to world。That's a bad name。But we can see that later on。

An initialized variable result。the result is the pixelel coordinate。不知道。But I'm not going to do this。



![](img/2d11af16ffb245ab1947921d1bfbeeda_310.png)

ction to center that okay。Okay， let's see what we have。Mz P is0， desired is0， lets see。

Do guys thinks going to work？Okay。Okay， looks perfect thing is now if you go off the screen。Oh。

 it's do the same thing， okay。Now we are limited。Okay， that's perfect。



![](img/2d11af16ffb245ab1947921d1bfbeeda_312.png)

Now， if we get the reverse control thing， I've probably gotten an dividend test right if oh。

 I think that's a bug。

![](img/2d11af16ffb245ab1947921d1bfbeeda_314.png)

Yeah， we're not， I don't know，m not sure if that's a problem or not， but if we reverse the controls。

 oh we have to。

![](img/2d11af16ffb245ab1947921d1bfbeeda_316.png)

AhIt's frustrating because。We want fast results， keep forgetting to do some small stuff。



![](img/2d11af16ffb245ab1947921d1bfbeeda_318.png)

Okay， let's see。Okay。Okay。Okay， that worked。 I think I'm not going to worry about about the mouse not being。

Not being exactly on the oh。So this is a problem。If we reach the end of the screen。

We can' to actually。

![](img/2d11af16ffb245ab1947921d1bfbeeda_320.png)

So maybe G to pause is not the best call for that。

![](img/2d11af16ffb245ab1947921d1bfbeeda_322.png)

I'm not sure which one is。So I'm going to do like MSDN。Get。Psor。 there should be a call like this。

Get not moving to the outdoor to see like ice cream curchet。There's no way to do that。啊。

So maybe there isn't a way to do that。Micellaneous mouse operation。

 maybe we can just like the get cursor position。Position。

And then we see there are any like relatable calls。啊。Cllip cursor， cursors， get cursor info。

 get message pause， Se cursor， step cursor pause， short cursor。Okay。Clip cursor， copy cursor。

 create cursor， strike cursor。Get clip cursor。Get cury， get cur info， get cury pass。

Physical cursor pass， load cursor。Set cursor， Sa physical cursor。Curing through short cur。Yeah。

So maybe that wasn't such a good idea。

![](img/2d11af16ffb245ab1947921d1bfbeeda_324.png)

可是诶。Just in case you guys didn't understand the problem was。

 I'm using all the delta right to move the mouse。

![](img/2d11af16ffb245ab1947921d1bfbeeda_326.png)

But this is the inverted mouse。When I hit that power down， right？And its inverted。

 but the problem is， if I inverted close to the edge of the screen， see。I can't go。More to the left。

嗯。There should probably be a way to fix that I'm just not sure what it is。



![](img/2d11af16ffb245ab1947921d1bfbeeda_328.png)

So。

![](img/2d11af16ffb245ab1947921d1bfbeeda_330.png)

So for now。I'll just do the。The cheap version and I'll put it to do。So。So I'm going to do。

I too like this one's the normal one。This one。Thiss the urgent one。 Yeah。

 I'm going to get the mouse picture actually just like we were doing before。



![](img/2d11af16ffb245ab1947921d1bfbeeda_332.png)

We're going to see a， yeah， now it doesn't have that problem now。If we see。Like this， see。

 we snapped。But at least we didn't go off the screen。Hey， Timmy， how you doing？Nice to see you， man。

We do some crazy gameplay stuff like inverting their mouse controls。Okay。Yeah。

 I don't know if I want to keep that。I'll keep that just to experiment with the levels， but。

I know that's pretty frustrating。Yeah， you want to control a lot more when you have that par down。

Yeah。

![](img/2d11af16ffb245ab1947921d1bfbeeda_334.png)

Not sure。Not sure just going to keep adding to do。Maybe。呃。Maybe try。去ge。F Delta。Because if。Mouse is。

At the edge。It's inverted。It gets blocked。Indeed， it becomes black。It becomes blocked。Yeah。

 it was a very bad description。So different now was it。Okay。Now let's do the final one。

Which is this low player。See， the thing is this local player depends。One of the mouse Dt。

Because if you only had a position in pixel space， yeah。So we have to use the DT。



![](img/2d11af16ffb245ab1947921d1bfbeeda_336.png)

It really should be a way do you guys know any way to get them？Csor， yeah。

 we do have like a window mouse move。Weow message， right？And I think returns the deelta。No。

 he doesn't。They trying of position。D coordinate and why coordinate。

Because it can take negative values to them multiple monitors。

Can was make points to obtain a point structure。嗯。Yeah， so。It doesn't really help much。

That's real right because I don't think we'll be able to do that。But then how do games do you like？

Mouse。What are your thoughts on coding boot camps？I've never been to one。 I've never。



![](img/2d11af16ffb245ab1947921d1bfbeeda_338.png)

Did this kind of a stuff， I mean。Maybe it's nice， maybe it isn' in China and I have to ask someone else。



![](img/2d11af16ffb245ab1947921d1bfbeeda_340.png)

Sorry about that。Yeah， so I'm not sure。What's the best solution here？To like change the mouse speed。

Yeah， I'll just have to search that because there's probably a way to do that so I'm going to put like a。



![](img/2d11af16ffb245ab1947921d1bfbeeda_342.png)

I'm going to keep the way it was before we changed back。Because it was working like this。Yeah。

 the mouse deep pizza world， okay I'm going to keep that working and then'm going to put it to do。

On these hazards。It low player and the inverted controls。Go do， like。To do how。先来。Get the actual。B皮。

Yeah。I'm not sure so we finished kind of finished the mechanics or the the Arabs and the。

Powered down mechanics。Now we could do the live system。But I think I'm going to do the rivals first。

 just where things is going to be more fun。The life ones， just no。

We're going to banging our heads against the wall for a little bit， not not really。

Because we have to do like neighbors。Yeah， that's not fun。I think。こ knows。The problem of going back。

 the problem of changing size from three to four。🤢，Is that？If this guy increases this guy back to 4。

说来。If it increases back to four。Then he goes again， it's going to be a smaller still。

Or maybe you' just going to be capped， I don't know， maybe maybe it's going to be a hard coat small。

And not just like size plus let' critic the size two。可以。Okay， the rivals， the idea of this mechanic。

 that's a pretty cool mechanic， I think。

![](img/2d11af16ffb245ab1947921d1bfbeeda_344.png)

Please， we have two kinds of blocks， I say the red ones and the orange ones。

And you have two kinds of balls， let's say the orange one and the red one。

You can only destroy this kinds of blocks。It is about。Or the other ball， maybe the other ball。

And this ball and this block with this ball。

![](img/2d11af16ffb245ab1947921d1bfbeeda_346.png)

So that's the basic idea， so pretty easy。We're going to win the ball。We could do a flag。Yeah。

Like ball rival a。And then we do rival be。Yeah。诶。Yeah， that looks good。So。Again。

 just test things out。

![](img/2d11af16ffb245ab1947921d1bfbeeda_348.png)

And also， just for the。啊。I don't think I'm going to keep the DT for now。



![](img/2d11af16ffb245ab1947921d1bfbeeda_350.png)

Just because it's really problematic。Yeah。😊，Going to do pixelixels toolor。Of the input mousepiece。



![](img/2d11af16ffb245ab1947921d1bfbeeda_352.png)

Yeah， we can search about that later on， okay。

![](img/2d11af16ffb245ab1947921d1bfbeeda_354.png)

So。So when we create the blocks。I'm not going to give more power。What I am going to do。

It to set them all。As the arrival。Let's say every other block is a different rival yeah。If X。

My you two。Block。Flas。就啦。嗯。I I did when I said ball rival away。We also need the bulb。

 but we also need the block。To know。So yeah， I'm going to do the blocks。Flas as well。So， block rival。

A。And a block cry be。Okay。诶。Yeah。Block rival a。Else， like。Rrival笔。Okay。

 so now flags on number blocks。Now， it is。Okay， now we're going to draw the block。You。Where is that？

Oh， we do have the collar， do we not？The block color。 Yeah， we do。嗯。Yeah。

 I'm going to change the color just so we know which blocks are which。

And we can start doing some nice colors now， I think。Like。



![](img/2d11af16ffb245ab1947921d1bfbeeda_356.png)

I she like color wheel。Yeah。Let's try to do the complementary colors。啊。Yeah。Yeah。Are。Yeah。

 these ones are the only ones I'm looking for。So I kind of want to。Let me think。An orange block。

And a purple one， yeah。How about that？That looks rival enough。

Or should you like just like full compliment color？Yeah， that can be cool， too。



![](img/2d11af16ffb245ab1947921d1bfbeeda_358.png)

ok。

![](img/2d11af16ffb245ab1947921d1bfbeeda_360.png)

Alex。

![](img/2d11af16ffb245ab1947921d1bfbeeda_362.png)

This one。Okay。

![](img/2d11af16ffb245ab1947921d1bfbeeda_364.png)

Okay， let's see what we have。Isn't that way better？And we didn't do like。



![](img/2d11af16ffb245ab1947921d1bfbeeda_366.png)

Oh， that's pretty cool when we work on inno。I think I'm going to do a weird thing I'm going to do if this guy。



![](img/2d11af16ffb245ab1947921d1bfbeeda_368.png)

Equals。This guy， I wanted to like every other role it changes I'm not sure Yes， this is correct Okay。

 so it has the check check pattern。 We're going to play around with which patterns to use。

 but for now just going to do that。😊。

![](img/2d11af16ffb245ab1947921d1bfbeeda_370.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_371.png)

Okay， that's pretty good。Yes。Now， the ball。I'm going to set now hard coded the ball0。啊为龙。

Do we do a balls 0。Yeah， I'm going to set the flags to be active and。Ball rival， A for。

And I should also。确你靠的。Go do like。Pranical a color。えな？IB考的。Color。Rivval。



![](img/2d11af16ffb245ab1947921d1bfbeeda_373.png)

企。😊。

![](img/2d11af16ffb245ab1947921d1bfbeeda_375.png)

And now I have change。The ball color。So we do包。し？Let's see where。Drrect。If？Oh。Flas， if we have。

The ball rival。诶。😊，Color， we're going to do。The rival B color。Ill see if above。Llaags。Rival E color。

I going to do this。A。Else。Okay以。That's it。Let's see。 scopepe missing。Close one to。



![](img/2d11af16ffb245ab1947921d1bfbeeda_377.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_378.png)

Yeah， that's not very visible， though。Yeah， I'm not sure。I'm sure I like that color。

And I should probably do the match thing。

![](img/2d11af16ffb245ab1947921d1bfbeeda_380.png)

To hit。They wanted the same color， so。It's going to keep。A。So， thing is。When we are destroying。

 so do ball block collision when we are destroying them。If。We're just going to ignore for now， right？

So。If the ball。Slag。The ball ball flags， a ball。Rival。A。You should do like a team。对。If black。Flaex。

Block right away。And。We are a ballalbi。We return。O。That looks reasonable。Now， this is the other way。



![](img/2d11af16ffb245ab1947921d1bfbeeda_382.png)

Okay， so let's see。几。Okay， now。We can't just ignore collision， right， or we can't。

But I don't think that's the point。Yeah。

![](img/2d11af16ffb245ab1947921d1bfbeeda_384.png)

Yeah， I'm just going to remove that a crash for a second， because that's because the last level。

It's not actually the last level。We just have wall and stadium。 We don't have the。



![](img/2d11af16ffb245ab1947921d1bfbeeda_386.png)

You don't have the other ones。Yeah， we just have normal and。



![](img/2d11af16ffb245ab1947921d1bfbeeda_388.png)

嗯。ok。

![](img/2d11af16ffb245ab1947921d1bfbeeda_390.png)

Oh， we didn't reset the flags。What chant game war？That's weird。Start game。嗯。Blocks， fair block。

We're just resetting the life。Okay I'm going to reset them all so。Where do we have the。0 rate。

0 array。

![](img/2d11af16ffb245ab1947921d1bfbeeda_392.png)

Okay。Now we should be able to destroy all of them。Okay， now。



![](img/2d11af16ffb245ab1947921d1bfbeeda_394.png)

Still doesn't help us that much。Because。Yeah， actually。What we want to do is not to just ignore。

 right？We want to ignore this part， we want to make it strong， right？

Or I think we want to go straight through。Not sure， so this is what I'm thinking。

Let me show you guide if you have like a block。哇。I'm going to do like for every other row I'm going to change the color so this is the result that I want。



![](img/2d11af16ffb245ab1947921d1bfbeeda_396.png)

Okay。Yeah， I think this is correct。 This is what I'm going to do with Yeah， see this is what I want。

😊，Just ignoring， yeah。

![](img/2d11af16ffb245ab1947921d1bfbeeda_398.png)

y， ok。嗯。Yeah。😊。

![](img/2d11af16ffb245ab1947921d1bfbeeda_400.png)

都。The same color didn't I can't have the same color for the ball。Like。I don't know。

 it's not as visible。嗯。That was pretty cool。Yeah， so I guess it is successful in a way。

Now I have to do two balls。And Ire gonna have to be careful。

So it doesn't become like impossible to play。Which might as well become， if should be told。

Or we should just have a。Pick up。To change the color with ball。I know it it feels weird。

Or maybe it should change over time。ok。

![](img/2d11af16ffb245ab1947921d1bfbeeda_402.png)

That sounds nice。Gameplay ideas， blockss， plum more balls when it killed。We can do that。

Blalocks will take to phase clear on science。We going to do that。嗯。We are going to do a。宝晒。Changes。

A rivalries。Every。し？But for now， let's try to do two balls。Let's see what happened。

So I have balls zero。Yeah。What I'm going to do is I'm going to do the same thing for ball one。

Let's just。And then I'm going to change it to ET。And we're going to start going up。



![](img/2d11af16ffb245ab1947921d1bfbeeda_404.png)

Just so he doesn't know for that， we are going to have to change a few things about that。

You know what， maybe it's not that crazy。Well， it is really crazy。Yeah。

 what I want to do is I want to make sure that doesn't have like an impossible situation like like this or maybe not impossible。

But like undesirable， yeah， I like this one。Otherwise， it is going to be pretty much impossible。

And not。interesting确。I mean。Yeah， see， I'm not even， I'm just trying to survive at this point。



![](img/2d11af16ffb245ab1947921d1bfbeeda_406.png)

So。😊，If you have two balls。I'm going to flag this guy as a。I it secondary？包。

Or maybe a secondary ball， I call as adjust。Speed。Based on zero， that's kind of hard coded。But。Yeah。

 not sure。Just going to do like a hack for now。嗯。😊，Yeah。The basic idea is。Let's。

 let's do this to the。DPY thing。Yeah。If。I'm going to actually create a function out of this， I think。

Which is changed direction to face the player。嗯。Process ball。When it。Process ball。DP。来。Yeah that's。

That name。Okay。Hey， extremely horny old man。Are you an next extremely hoy old man？Hope not。Okay。

 internal avoid process following D P negative。然后。NowLet me show you what I'm doing。

 extremely horny old man。

![](img/2d11af16ffb245ab1947921d1bfbeeda_408.png)

We are making， we started out making a breakout clone。From scratch and see。You're yeah。

 you're pretty old at 48， I think I'm 22， so're pretty much an old man。Thanksice Jimmy War。

 I don't know if you say so。 I'm just going to believe you。😊。

So we started out doing a breakout clone。

![](img/2d11af16ffb245ab1947921d1bfbeeda_410.png)

We are doing this game。From scratch on stream， so if you start from the YouTube page。

 you can watch like the very first stream where started out with the blank file。

 no libraries or nothing。

![](img/2d11af16ffb245ab1947921d1bfbeeda_412.png)

And we started cool the game。And at this point， like last episode， we had a breakout clone。



![](img/2d11af16ffb245ab1947921d1bfbeeda_414.png)

And then I started playing around with some crazy gameplay ideas， right？



![](img/2d11af16ffb245ab1947921d1bfbeeda_416.png)

And so far。We did like art ups and power downs and life， but we didn't implement like life mechanics。

 just life。Now we're doing like this thing where each ball can only destroy a certain kind of block and you can you have to know two balls。



![](img/2d11af16ffb245ab1947921d1bfbeeda_418.png)

Why are you making a breakout？ Well， breakout a fun game， dude。



![](img/2d11af16ffb245ab1947921d1bfbeeda_420.png)

そそうそううん。Okay。So， yeah。So what I'm doing here at this point。

II'm going to try and make controlling two balls more。Mageable， I suppose。So if when we change。

 right， that was。When we change the direction， I change。DP啊。

II just forgot the name of function great。Process bow and DP negative。I should go。

When DPY down makes more sense。So process。あす。包？When D PI down。呃。

What I'm going to do is change the this ones what I was been doing right so destroy。

On the same thing。I'm going to call process ball when D P change line ball， okay。So at this point。

 we should have no change， right？And we should also add that flag ball adjust speed。The pine bow。

I think we didn't call it while we just call it just。一啲同波。I just。What was that？We spelled it wrong。

 actually， ball adjust。第一。Based on what。And based on0。case of this study。好。This gonna be10。

I like your color though， yeah。ok。He's making a breakout in C which is awesome well it was several decades ago dude and not sure it was several decades ago。

 I mean all triple games are made in either C or C++。I mean。

 most of the higher level code is C++ or some scripting language， visual programming language。

 but the angels are pretty much C++ with parts and C。

If were' to learn how to make a game from scratch。You're pretty much at options。

 pretty much C or C plus plus if you want to know。You improve that over time because that's the point。

 this is the very first game I'm streaming。But the idea is we are going to stream some crazy stuff later on。

 hopefully we don't get to that， but we have to finish this one first and we don't want to get stuck for too long。

Doing that。But we want to make it interesting。 So it's a nice balance between that。 Okay。

 so ball adjust。面包。I just。How long have you been working， If you go to it， but it's been like 2，6。

8 plus 2， It's been 10 hours。

![](img/2d11af16ffb245ab1947921d1bfbeeda_422.png)

ThatWe've been working on this game。

![](img/2d11af16ffb245ab1947921d1bfbeeda_424.png)

10 hours like a one day。Worth of programming。To make it from scratch。

 and I didn't even reuse code for for my other games， that was a challenge I wanted for the stream。

So yeah， and we start for col for like two hours， but that was fun because we learned that a lot。

 so it's part of the process。Okay。Yeah， so now what we have to do is when we process the ball。

 if we are supposed to adjust speed。

![](img/2d11af16ffb245ab1947921d1bfbeeda_426.png)

Yeah， we may have to do some crazy math here for a second。Do you work in code or games？

Not sure what that means。I mean， you can work in games programming， right？

I used to work in games programming。But now I do like programming。In other areas other than games。ok。

So so that's why I'm doing this stream because I want to program games。

So you have a career in code or games， yeah。I did have a career in games。

 but now I have a career in other stuff with programming。

But I do like to programming games from time to time because games are really fun。

 I think games are really more fun to make than to play nowadays， so honestly yeah。😊，So the idea is。

 if you have two balls， let's save this ball。Has changed direction。

And this ball is already coming down， so yeah。

![](img/2d11af16ffb245ab1947921d1bfbeeda_428.png)

That's what we're going to test if。We are suppose。To change directions。And the other bow。

To change action now， if we are supposed to。To adjust。Based on。To just。

If you're supposed to adjust DP。And the other ball。呃。



![](img/2d11af16ffb245ab1947921d1bfbeeda_430.png)

Yes。😊，Going down。So this is the situation we want to play around with。

 we want to make sure that when we hit that player。We don't hit them。

 we don't hit them at the same time。So that's the challenge。See， so the thing is at this point。

 let's see this first example here。

![](img/2d11af16ffb245ab1947921d1bfbeeda_432.png)

So the blue ball at that point should decide， okay， I'm not actually。Going to。To do that speed。

 and' going to be slower than that。

![](img/2d11af16ffb245ab1947921d1bfbeeda_434.png)

I don't think that's going to work。Well。But it might as well well try， right。

 It is a crazy gameplay idea。 If it doesn't work， maybe we were。

 we're not going to do two balls and we just do the。The ball flickering thing。

If you are supposed to adjust DPY， okay， so if。This ball has a flag。呃。包。Ajust speed based on。

 let's say， zero。Going to hard code the laws for now。And then， we cannot do。

And then we can do like a cleaner version after that。 So if we're doing that and。嗯。And the balls，0。

Dot flags， sorry， dot。DP。Is less than 0。 So if it's already also going down。We should。

 We should destroy we。心 be slow。Okay。😊，Okay， so that's the plan。It doesn't seem too complicated。

 right？Then all we're going to do here's change， right。

And right now we do have a bow speed multiplier。Right。嗯。

But I think you're going to have to make another one。Oh， we can change the base speed。Yeah。

' going to do that。So， yeah， base speed。We should also do。呃。Yeah， it basically sounds good。For now。

 I'm just going to hardcode balls。I'm sorry， ball DPY。Let's make it half。Of what it is。

Illegal construct， yeah， it's supposed to be DPY。

![](img/2d11af16ffb245ab1947921d1bfbeeda_436.png)

Okay， so the idea is， remember that that。We shoot them both up and then the blue ball。



![](img/2d11af16ffb245ab1947921d1bfbeeda_438.png)

Get the same。Place as the other one， we should expect it to be really slowly and it's already slower。

 okay？嗯。Yeah， that totally wasn't what I expected。

![](img/2d11af16ffb245ab1947921d1bfbeeda_440.png)

So， if we。

![](img/2d11af16ffb245ab1947921d1bfbeeda_442.png)

Yeah， I'm going to add a couple break points because that was a bit weird and I just play it one more time。



![](img/2d11af16ffb245ab1947921d1bfbeeda_444.png)

So the blue ball was slow and then now it's fast again。



![](img/2d11af16ffb245ab1947921d1bfbeeda_446.png)

That was totally weird。Do we calculate the ball EE every frame？嗯。P up line equals。No。

 see only when we。When is that when we do only when we do the block collision？

So suppose that's correct。Oh， but that's the problem。

We changed the DP and then we immediately changed it back。So we have to do that after this guy。O。



![](img/2d11af16ffb245ab1947921d1bfbeeda_448.png)

Okay， that's what happens。One fast and one slow， yeah， but the problem is。

 even if it's one fast and one slow at some point， they may coincide。



![](img/2d11af16ffb245ab1947921d1bfbeeda_450.png)

Yeah， well， maybe maybe that's not a problem。 but the thing I want to avoid is let's say when it's really thiss low and one it's super fast。

 See， they're not going， Yeah， problem solved， right， Not exactly。

 if this guy like hits a block like this and this guy is still going down slowly。

 then it goes down fast， but this one's coming down slowly。

They're going to end up hitting the player twice at the same time。

Twice at the same time in different places， that's the problem， right。

 so that's what I want to avoid in this case。They should be like。Let's say they are the same。Yeah。😊。

In this case， when it hits back this guy， this one's like Nos speeded， this one realize， oh。

 it should be slow and then I can calculate how slow it it should be。

 which in this case would be pretty slow。Then it's going to give enough time for the player to reach this ball and this ball。



![](img/2d11af16ffb245ab1947921d1bfbeeda_452.png)

Yeah。😊，That's what I plan。

![](img/2d11af16ffb245ab1947921d1bfbeeda_454.png)

Let's see what we have now。At this point。So for some reason， the blue ball starts off slow， yeah。

You know what， I think？This is working。知。😊，I mean， it's not 100% yet。But。

I haven't had the problem of having to。Oh， then that was that was okay。So， maybe。

The orange was supposed to be slower at the time。Yeah。嗯。This is not actually correct， I mean。

 for several reasons。I see you need to do some math with the velocity of the boss to slow down。

When it's moving down or up exactly。That's the thing， I mean。



![](img/2d11af16ffb245ab1947921d1bfbeeda_456.png)

嗯。Its exactly the the place where we have to do， but this not right。

 But I don't want to focus on the math for now。 I just want to focus on the。Moment。

 this is triggered， right， because if you are supposed to just deeply know the other bars going down。

Maybe we should just reset this。The base beat。See， because when we are supposed to like reset the ball speed。

 we are supposed to use the base speed。Like we're doing here。

 we set the DPY to the base speed times the speed multiplier， right？

I don't think I'm doing that in all cases。Like， for instance， when you collectllide the player。啊。

That dude is colliding。Yeah， see， we just changed the ball direction。

 so we should should just do the same thing， we should change the ball。嗯ん。Reverse and。

Reset and reverse。Yeah。😊，Pet and reverse。Sounds。So what I'm going to do now。呃。

I this was set and reverse。We're going to take a point to an F32。Let's call it It know。嗯。

And what we're going to do is， oh， I think I'm going to have to take the whole。后去了。Yeah。

And then what we're going to do here is let's see the。包。Do they speed。Yeah。

 this is what we're going to do。啊。Set and reverse。哦。DPY。好。Okay。Think that was a good structure。

Re second revible PI。Oh， I actually didn't know if I was supposed to do that。Yes。的PI。Ex bit。

Now base speed， let's see where else。嗯。Yeah， so this I'm going to do the。Reset and reverse body PY。

And here as well。Yeah， this is a little repetitive， but I just want to keep the。

I just want to keep the consistency of calls so everything goes through there。

Reset and reverse ball D PI and collision with the ball and the。HDP。Why， yeah。Yeah， okay。 these two。

Reset and。Compatible type。 Yeah， I won take the whole ball。



![](img/2d11af16ffb245ab1947921d1bfbeeda_458.png)

Okay。Now， let's see if you get a little bit of a better behavior， well certainly don't。



![](img/2d11af16ffb245ab1947921d1bfbeeda_460.png)

What was。That。嗯。Reverse， reset and reverse quality P。Well， let's just try to do the ball。EPY。



![](img/2d11af16ffb245ab1947921d1bfbeeda_462.png)

Times minus one thing。That was weird。哦。Let's see。

![](img/2d11af16ffb245ab1947921d1bfbeeda_464.png)

Okay， that's better。

![](img/2d11af16ffb245ab1947921d1bfbeeda_466.png)

But why didn't it work the other time？If the ball is greater than zero。

 ball DPUI is going to be the ball based speed。Time space both be multiplly。Else， body D P。

It's going to be equal。To the minus guy well。Check out one e columnists in the debugger。



![](img/2d11af16ffb245ab1947921d1bfbeeda_468.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_469.png)

嗯。Okay， apparently。

![](img/2d11af16ffb245ab1947921d1bfbeeda_471.png)

While， you being an update properly。意。停。B D PI， I don't know why I called that。嗯。

Because mounts are the arena。Really。不し。对。Why's the blue ball outside the arena？



![](img/2d11af16ffb245ab1947921d1bfbeeda_473.png)

Just。Check that。we're're going to have to make some major cleanup later on。We start out at a P。

Why of 40。

![](img/2d11af16ffb245ab1947921d1bfbeeda_475.png)

Right。小。啊，O， let's see。P44。Why。Okay， that was weird。嗯。Yeah yeah。These are people are oh。

 because you're already at the velocity。Yeah， they're supposed to be doing going downwards， right？

Or the other one supposed to be going up？Yeah， the other one's going on。



![](img/2d11af16ffb245ab1947921d1bfbeeda_477.png)

So that's fine， that's the problem。So， start。Game。And not going to make a go。呃。Or is that？

Face speed 50。No， it is correct。I think。Okay， yeah， no at no it's wrong。



![](img/2d11af16ffb245ab1947921d1bfbeeda_479.png)

Yeah， so now they're in exactly the same place。 And let's see if we reverse properly，-50。us50。in-15。

If the buzz greater in zero， it is not。The base is 50 times one。The ball D皮。高地 p。Why is -50 still。嗯。

😊。

![](img/2d11af16ffb245ab1947921d1bfbeeda_481.png)

I remember that problem because we ran twice。That's probably it。

 So what I'm going to do it for now is' going to remove one wall。



![](img/2d11af16ffb245ab1947921d1bfbeeda_483.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_484.png)

Yeah。This is easier to test。And then I're going to see when this guy's called。So we hit it there。We。

 we have the ball。DP-50。O。Is it still minus？So we're it's not even the problem of running twice。

 no it's not we're not running twice。The problem is really it's not changing for some reason。

If it is greater than0。嗯。😊。

![](img/2d11af16ffb245ab1947921d1bfbeeda_486.png)

Because actually it looks like it's the other way around。Looks like it's。If it's greater than zero。

We're going to make it negative。

![](img/2d11af16ffb245ab1947921d1bfbeeda_488.png)

But why was that right in the first place？Let see。妈的屁。I minus 50， 50， okay， that's correct。Okay。Yeah。

 okay。

![](img/2d11af16ffb245ab1947921d1bfbeeda_490.png)

That's turning cool now， let's start doing the other。



![](img/2d11af16ffb245ab1947921d1bfbeeda_492.png)

And I's see they're probably going to be in the same exact place in the first one。

But it's going to change。 okay， let's see。

![](img/2d11af16ffb245ab1947921d1bfbeeda_494.png)

Okay， I think we're getting there。 let's solve that problem we had in the first place。



![](img/2d11af16ffb245ab1947921d1bfbeeda_496.png)

I'm going to try to be as steelless as I can。To the left。Yes。That was a total failure。呃。

remember that I managed to do that the first try， I don't know how I did that。



![](img/2d11af16ffb245ab1947921d1bfbeeda_498.png)

Yeah， but anyways what I want to do。Is reset this guy。嗯嗯。Process ball and D P down。



![](img/2d11af16ffb245ab1947921d1bfbeeda_500.png)

Yeah， well， I suppose we are doing that already， Okay， so we're cool。So at this point。

 all we have to do is change the equation。To make sure that it's actually a reasonable number。

 not just slowing down for the sakega slowing down。y。Like that。So what I can do to test。

 which I think is going to be pretty cool。

![](img/2d11af16ffb245ab1947921d1bfbeeda_502.png)

Is I'm going to change both。

![](img/2d11af16ffb245ab1947921d1bfbeeda_504.png)

To be positive， so they're both going up。

![](img/2d11af16ffb245ab1947921d1bfbeeda_506.png)

So they should， yeah， one fast， one slow now。Yeah。

![](img/2d11af16ffb245ab1947921d1bfbeeda_508.png)

Yeah， the idea is nice， but it's not working。

![](img/2d11af16ffb245ab1947921d1bfbeeda_510.png)

I'm going to have to change this equation， so now let's think math for a second。呃。We are here。

 let's say， at a Px。PY。And we can calculate how much time it's going to take for us to hit the player。

And how much the other ball is is going to take to hit the player so you can calculate that。

The thing is， if these guys。I can just like do an equation based on。

The difference in sizes of these guys。😊。

![](img/2d11af16ffb245ab1947921d1bfbeeda_512.png)

Okay。Yeah， sounds sounds good。 So what I'm going to do is。Calculate。Speed damp。Based on。

And let's do calculates。Let's just calculate speed。I just。And I'm going to do， in this case， ball。

Ball 0。Actually， we just going to do false。And in this case， I'm going to do it a calculate。好。

Falls plus。Okay， so internal。Do calculate。It' speed adjustment。The包。To adjust。包。



![](img/2d11af16ffb245ab1947921d1bfbeeda_514.png)

Reference， yeah。Math， I'm not like the strong point of math。

 but I think this is going to be simple enough， even if you don't have like 100%。



![](img/2d11af16ffb245ab1947921d1bfbeeda_516.png)

Fur it out just enough so we can get an approximation of speed。



![](img/2d11af16ffb245ab1947921d1bfbeeda_518.png)

So the thing is。

![](img/2d11af16ffb245ab1947921d1bfbeeda_520.png)

If。😊，The other ball。I's already slow。Yeah， I don't think we care， so we care。Distance。2 player。呃。え。

Let's call it。Which is to adjust P。5。So that's where we're at。 let's say we are at， I don't know。

 let's say this is。

![](img/2d11af16ffb245ab1947921d1bfbeeda_522.png)

The player， let's say the player is minus 40， this is 30， this is 20。So our distance is 30。Mイus。



![](img/2d11af16ffb245ab1947921d1bfbeeda_524.png)

-4， yeah。So。Let's do where is the game over we're seeing？So，-50。No， it's not， yeah。

 I'm going to do to play it up like。playlayer p dot。So this is the distance to player， say distance。

A player。Dance speed。Okay。Yeah， and this is the ref。



![](img/2d11af16ffb245ab1947921d1bfbeeda_526.png)

So I have the two of them， now we're going to have like 70 here。And60 here。

The thing is we want to get the difference between these guys Okay， now we're getting there。



![](img/2d11af16ffb245ab1947921d1bfbeeda_528.png)

So it's going to be 70 minus 60。So it's going to be distance。A minus distance。阿比。



![](img/2d11af16ffb245ab1947921d1bfbeeda_530.png)

Okay， so we have Timm， so they're going to reach the player。In a offset of 10。Well。

 they are actually Ta for。That was kind of stupid， we should have just。



![](img/2d11af16ffb245ab1947921d1bfbeeda_532.png)

I'm stupid stupid。I don't know why was it。What was I thinking di is the one minus the other one。



![](img/2d11af16ffb245ab1947921d1bfbeeda_534.png)

你先不用。Because I'm not sure what I'm making， so I'm kind of doing these two。

What we have actually is 10， so they are 10 units apart that makes more sense now， right？呃。If we。

Are like。Really close， oh， but no， I'm sorry， that's not correct。And neither is this。

We have to consider the amount of time it's going to take first us together。



![](img/2d11af16ffb245ab1947921d1bfbeeda_536.png)

Right。嗯。😊，So that was wrong， both of them was wrong。



![](img/2d11af16ffb245ab1947921d1bfbeeda_538.png)

So what I want to do， like I met 30。And I'm going， like minus。呃。Let's say minus 15。

And I want to get to minus 40。So the thing is 30。Plus，-15 times x。

And this x is going to be in seconds。E equals minus 40， okay， now we're doing a math， to me。啊。

So we're going to do like minus， yeah， we can do like 70，15 x。イコセリ。And in this case。

X is going to be equal2。

![](img/2d11af16ffb245ab1947921d1bfbeeda_540.png)

Yeah。😊，That's say time to player， Time A to player。It's going to be。The distance to player。

Divided by the speed。To adjust。DP。ok。Okay， we're getting there。And A to B。 Oh， that was a。Okay b。A。

This one is the red。Okay。So we got this number， which is how much time it's going to take for us to reach the player。



![](img/2d11af16ffb245ab1947921d1bfbeeda_542.png)

So let's say this guy's going to take two seconds。And these guys are going to take just seconds too。

 so we see that we want to change this guy's speed。And if this is like let's say。

 200 and this is one second， maybe it's okay。So how are we going to change that？We can change Okay。

 so this。

![](img/2d11af16ffb245ab1947921d1bfbeeda_544.png)

We have to change this guy in our equation this。Time to time A to player， is this X。And this beat。

We're going to change the deep beat here。

![](img/2d11af16ffb245ab1947921d1bfbeeda_546.png)

Yeah。😊，We are going to change the DP。To be。Well， what we can do， which would be kind of stupid。

 but would work。Is。If。We are。啊。If we do like this guy。Minus this guy。

Whi is we are going to go one second after him。No， I'm kind of confused。



![](img/2d11af16ffb245ab1947921d1bfbeeda_548.png)

Okay。Let me put a break point here。

![](img/2d11af16ffb245ab1947921d1bfbeeda_550.png)

Just to see that we made a mistake so far。Or we're not event call it。



![](img/2d11af16ffb245ab1947921d1bfbeeda_552.png)

Okay， so that doesn't help much。嗯。

![](img/2d11af16ffb245ab1947921d1bfbeeda_554.png)

Oh， we are calling it calculate speed adjustment。

![](img/2d11af16ffb245ab1947921d1bfbeeda_556.png)

嗯。Okay you guys。

![](img/2d11af16ffb245ab1947921d1bfbeeda_558.png)

Yeah， for to compilely。Illegal。Let's type4 it。Let's return 0。5 for now。



![](img/2d11af16ffb245ab1947921d1bfbeeda_560.png)

Now。Let's go back。This guy， okay， now we want to adjust。This， this ball is going 50 up。

And this one is going 50。 Oh， I'm sorry， it's going minus-50。This one is also minus 50。So。

The distance to the player is 84。 Sound okay。 The distance is 84 sounds okay。 time。

 time minus-1 second。

![](img/2d11af16ffb245ab1947921d1bfbeeda_562.png)

Tim， I think we got the other way around。70 divided by 15。



![](img/2d11af16ffb245ab1947921d1bfbeeda_564.png)

Andition negative。Okay， anyway。The diff。Zero， so they're going to reach the player at the same time。

So what I'm thinking about doing？

![](img/2d11af16ffb245ab1947921d1bfbeeda_566.png)

Oh and I forget the different time out in different distance。😊。



![](img/2d11af16ffb245ab1947921d1bfbeeda_568.png)

Yeah， so time。A good player。Minus。

![](img/2d11af16ffb245ab1947921d1bfbeeda_570.png)

O。

![](img/2d11af16ffb245ab1947921d1bfbeeda_572.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_573.png)

Yeah。Now， if they are the same。How much this guy be。

I should do like a map inter range thing where I get like。



![](img/2d11af16ffb245ab1947921d1bfbeeda_575.png)

If it's  zero， yeah， that's it like this。 If it's 0。

Which means that we're going to hit that at the same time。



![](img/2d11af16ffb245ab1947921d1bfbeeda_577.png)

I should also hit， I should actually hit twice as low。 So if it's zero。



![](img/2d11af16ffb245ab1947921d1bfbeeda_579.png)

We're going to be0。5。Okay， we're starting to get somewhere if di is 0， we're going to go 0。5。

If the diff is like one second。We can do one。

![](img/2d11af16ffb245ab1947921d1bfbeeda_581.png)

And everything after one second， we're going to ignore。 So the day。 So we're going to return。



![](img/2d11af16ffb245ab1947921d1bfbeeda_583.png)

Oh， and we have。What if it's negative？What if it's minus-1。

 minus1 means that we are going to get there first。Yeah， I think we should just。Mat。

 these guys into range。If it's -1， we should just do like not zero， but Yeah， let's do a clamp。

 So we're going to。

![](img/2d11af16ffb245ab1947921d1bfbeeda_585.png)

We're going to clamp。那姐。Okay。

![](img/2d11af16ffb245ab1947921d1bfbeeda_587.png)

Yeah， so it's 0 to one。Maybe it's not going to work in all cases， but we're going to fix that later。

0， to，1。

![](img/2d11af16ffb245ab1947921d1bfbeeda_589.png)

呃。Time 0。5 plus 0。5。Camp。

![](img/2d11af16ffb245ab1947921d1bfbeeda_591.png)

Yeah， we have to do like clamps zero。Let's see what we had Okay， that was， that was a better speed。

 I think okay。Okay。Okay。Okay， for speed。Okay， I to get really fast。Okay。

 that's a little bit unpredictable at that didn't work that was the case that didn't work probably was negative。

Because we are going faster than the other ball。But I think that's not entirely bad。

But I don't think that's good either， to be honest。That looks like really crazy for me。

Like too unpredictable。But at least we can play now。We the progress。know what I'm going to do。

I want to build。Like three levels。Just so you can experiment。

And then I think I'm going to call it a day。O。Yeah。That's not very good， that's pretty， pretty crazy。



![](img/2d11af16ffb245ab1947921d1bfbeeda_593.png)

So we're going to create the levels， but I'm just going get some water， so。I'll be back。听完没。Okay。

 one minute， I'll be back。Okay。So I'm back。Let's create some levels to show up these mechanics。

 and I'm also going to show up the life system， although we didn't have implement these parts。

And we have the block layout so the next thing we're going to do。See， we did pickups。

We're going to do the block。Definitely for a next stream。

 and that's going to be a really game changer， I think。

And we have somewhat of a nice place we can play around with。

Because the levels are going to be what's going to show off these mechanics， right。

 just make mechanics for the sake of making mechanics doesn't make much sense。Okay， so。

First level is going to be the breakout clone。Let's just plan this thing out。

 is we're going to do a normal， we're going to do it well。啊。Yeah， we're gonna do a a。Very go那就。

It's called the stadiumium。And let's do like the。The chess one， yeah， just for fun。うん。😊，Yeah。Okay。

So these are the game mosts we're going to do now。呃。The normal one， all I have to do is to I'm sorry。

Start。Start game。I'm going to if zero this guy out。And make this guy go downwards again。

And they create black block。I'm not going to make them right。



![](img/2d11af16ffb245ab1947921d1bfbeeda_595.png)

Okay。😊。

![](img/2d11af16ffb245ab1947921d1bfbeeda_597.png)

We should have good punback。And we do Oh， the ball。 I'm going to remove the， the。



![](img/2d11af16ffb245ab1947921d1bfbeeda_599.png)

Rriivvalness of the ball。And we shouldn't just speed based on。



![](img/2d11af16ffb245ab1947921d1bfbeeda_601.png)

I see。 very pink。

![](img/2d11af16ffb245ab1947921d1bfbeeda_603.png)

Yeah， back to what we had， is that the normal color we did？



![](img/2d11af16ffb245ab1947921d1bfbeeda_605.png)

是么。If。Rivy， Al if rival B。No， should be yellow， why are we。Why are we rival B colored。



![](img/2d11af16ffb245ab1947921d1bfbeeda_607.png)

Okay。Great point here and that。50。Oh， really flags1， Oh rival B， I forgot it should be ball rival B。



![](img/2d11af16ffb245ab1947921d1bfbeeda_609.png)

Yeah， I know these probably coincide to avoid errors like that。嗯。



![](img/2d11af16ffb245ab1947921d1bfbeeda_611.png)

Yeah。Oh， but I typed like rip B colors， so that was a stupid mistake honestly。



![](img/2d11af16ffb245ab1947921d1bfbeeda_613.png)

Okay， we're back over Scan， actually not yellow， okay。So this is normal upon。

 that's going to be the first level。Normal pun， normal breakout。

We should just change the colors as well。

![](img/2d11af16ffb245ab1947921d1bfbeeda_615.png)

Let me see if you can get like a pallet just for it just be a little bit different。啊，B。Well。

 these are some ugly colors。Let me get like the this guy。Oh， this is pretty ugly too。Okay。

 this is a little bit better。系。

![](img/2d11af16ffb245ab1947921d1bfbeeda_617.png)

Like that。I think I'm not sure it's going to be way too colorful thing。

These black eyes are not and this black to white。

![](img/2d11af16ffb245ab1947921d1bfbeeda_619.png)

Blocks aren't very interesting honestly， so great。Or maybe we don't care about the colors yet。

 what does that supposed need？

![](img/2d11af16ffb245ab1947921d1bfbeeda_621.png)

Breakout。嗯。

![](img/2d11af16ffb245ab1947921d1bfbeeda_623.png)

Yeah。😊，I don't know。

![](img/2d11af16ffb245ab1947921d1bfbeeda_625.png)

啊。I'll just keep the colors like that。

![](img/2d11af16ffb245ab1947921d1bfbeeda_627.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_628.png)

Or just yeah， no， I think we're going to do something more interesting， okay？So。

 but we're going to code the color。 So it's not going to be the like a final color palette。

Handmade color palette stuff， so' got to be just。I might say， okay， so color。Make color。

I'm not going to make color from gray。 I'm going to。卡住。So great， I'm going to like make color。

 make color。We're going to pass our。And G and B。Okay， this is B。471。So we're going to make color。

And are going to pass。嗯。It prepares like 255。For the red， and this guy，'s let's call it K。Do that。嗯。

😊，Oh。No， I'm sorry， this is great。嗯。

![](img/2d11af16ffb245ab1947921d1bfbeeda_630.png)

And this。It's hard to be。

![](img/2d11af16ffb245ab1947921d1bfbeeda_632.png)

Qu those to layers。Dude， I say everything wrong。So I'm going to offset B by 0 G by I trying to get tired in R 16。

 This is。We by zero， we by8， we by 16。Make color from gray。Already has a body of case of this。



![](img/2d11af16ffb245ab1947921d1bfbeeda_634.png)

Okay。

![](img/2d11af16ffb245ab1947921d1bfbeeda_636.png)

Yeah， well。That didn't work。Let's see， block。好多人。Oh， because we sat in the wrong place。This。

 we should probably delete。

![](img/2d11af16ffb245ab1947921d1bfbeeda_638.png)

Oh， oh， this is the walk code。 Oh， so we see the walk code。 we should should see， okay。



![](img/2d11af16ffb245ab1947921d1bfbeeda_640.png)

Now， that's more interesting， right？

![](img/2d11af16ffb245ab1947921d1bfbeeda_642.png)

I mean， it's still kind of weird。But it is interesting。If you do like something。



![](img/2d11af16ffb245ab1947921d1bfbeeda_644.png)

be like a pinkish coin。Yeah， now we're talking， that's pretty cool。Okay。



![](img/2d11af16ffb245ab1947921d1bfbeeda_646.png)

I like these colors。But not for the one， I'm going to do them for the normal block。

Which is like here。Just to add a variety。And then for the wall。The wall might as well be gray。But。

Yeah。I don't know。Let's do。Stupated by it by two。話してれないです。K， undefined。因为。That fine。In this case。



![](img/2d11af16ffb245ab1947921d1bfbeeda_648.png)

Okay， let's see what we have。Yeah， we have。Yeah， I think that's okay。Okay。Okay， now for the wall。

 we're going to start adding the mechanics we program today。



![](img/2d11af16ffb245ab1947921d1bfbeeda_650.png)

So first thing we're going to do。Is to add like the power ups and stuff。So yeah。

Not sure how I'm going to do this because。We could。We do have the generated block block thing。Oh。

 you can just pass， like。Now， the wall has its something， okay。So we don't have to worry about that。

Let's it if we are on the first row。You're going to randomly have a par up。

And if we are on the last row， we're good well。Just so I don't think we're going to add randomM now。

I'm just going to add a par up。I block。Oh， we do have you do need vampire par at least。

Maybe I can just partcode that。嗯。いや。

![](img/2d11af16ffb245ab1947921d1bfbeeda_652.png)

I think I'm going to do that， but let's just see how many blocks you have。



![](img/2d11af16ffb245ab1947921d1bfbeeda_654.png)

One， you， have a ton have like。20 blocks， so if you do like for 10 of them。So if we are in this guy。

Yeah， and we are like， let's see multiple of。So we do five for world。We're going to set the block。

Power。I see the block is still called par up。It it's called power blocklock okay it's a power block。

I'm going to set it to like a power block， I'm going to create the variablebook。

And it's going to start zero。And then I'm going to add it here， and if we are at the last bar block。

All right， then to start。If we are。That's okay， let's do like our count。Yeah。嗯。😊，Let's do 3。No，20。

2 divided by 3。6， I do 6。So we've got three guys。So we're going to do three。Fer blocks。

It's going to be like this， this and this。那边。And no， this is enough now。Else， if。Y equals to。

Let's say，8。And then we're going to do。Yeah8， or。Y equal goes to。7。Yeah。

 so you're going to do like six or seven。We're going to do the same thing。Bs。

Hopefully you don't crash。

![](img/2d11af16ffb245ab1947921d1bfbeeda_656.png)

This is just to make sure that。Some guys respond， Arabs。Actually， all of them want pars。



![](img/2d11af16ffb245ab1947921d1bfbeeda_658.png)

想个。If the sky is used to 0。嗯。Oh， I should do like not。



![](img/2d11af16ffb245ab1947921d1bfbeeda_660.png)

いや。

![](img/2d11af16ffb245ab1947921d1bfbeeda_662.png)

ok。Okay， nothing， nothing you let's see if we got a power up。 Okay， we did。ex次。See which part？

I think you can know oh we got oh。That was a disaster。We got the triple shot。But。It didn't actually。

Or because you start start testing that。care about this place。And we got comment。Okay， that's nice。

Now these we should avoid， but I don't know if we should avoid that or not。



![](img/2d11af16ffb245ab1947921d1bfbeeda_664.png)

In the， the block。The block P guy。Here。I'm actually going to do like if it's。I should like。Power。

Upcount。Because， power to。Okay。If。This guy。Slesss than。R equal to。Acount。actually。

Coun is it for a blast。Or a last。Okay， we're gonna change like this else。

We're going to do like a full red。This is just so we can。



![](img/2d11af16ffb245ab1947921d1bfbeeda_666.png)

No， if we should avoid them or not， right， okay？开ち。I see， now it worked。That's not good， I suppose。

Okayive the comment， nice。ok， ok。ok。I think now that's getting pretty interesting。Maybe。

 maybe that was like。If there weren't。Enough part of maybe6 was too few。I mean。

 you can do that on different roles， I think I'm going to do that。



![](img/2d11af16ffb245ab1947921d1bfbeeda_668.png)

Okay， I think that's pretty cool。Let's just do that on more ruless。Yeah。Yeah， if we are on row 0 or。

Let's say， row 3。Let's say， too。

![](img/2d11af16ffb245ab1947921d1bfbeeda_670.png)

Zero or two。We to do that， okay。Yeah。Why didn't that collide。See， now it didn't work。

Things are a bit weird， I think。Oh， and we also。Oh good， that saved me。



![](img/2d11af16ffb245ab1947921d1bfbeeda_672.png)

Okay， so yeah， we have a ton of legs。H。嗯。Yes。Power block。Its greater than。Power up the less。



![](img/2d11af16ffb245ab1947921d1bfbeeda_674.png)

Park block。

![](img/2d11af16ffb245ab1947921d1bfbeeda_676.png)

Okay， but that's not。But least are our concerns。Our in our。Creek block。Here's Sp power blocklock。

No no sponsorship or shot yet。Get next available。包。Yeah， for some reason， didn't collide。Just for。

Just be sure if we're not fitting at this point。 We should add add like a console or something today the。

What we're going to do here is you just going to search。



![](img/2d11af16ffb245ab1947921d1bfbeeda_678.png)

Since we're not using our arrival mechanic in this level， we shouldn't trigger that。Okay。

 that worked perfectly， but we didn't do anything actually。Oh， this can be hard。Okay。

 yeah invinexibility， nice。Okay， I'm enjoying this when when you do have random numbers。

It's going to be way bad。Yeah， we lost to avoid the other one。We lost the power by need。



![](img/2d11af16ffb245ab1947921d1bfbeeda_680.png)

屎。😊，See， we have a lot of bugs。I think we're going to have to debug this next time。

So that's not the problem， at least。Not sure。How much we should celebrate？嗯。Yeah。

 because in due collision。We are actually failing。嗯。Yeah。

 I been test where we're changing the other mechanic。When you're changing the appd。A theDP我Y。This。

Deep you eye down。Process ball and deep down。Sure。Yeah。啊。B and Dp down。

Calling that when we hit the ball。On the Dp down。Yeah， I should probably call that。说定。

You should probably this try， no。No， you are correct here。Yeah。I think this is correct。



![](img/2d11af16ffb245ab1947921d1bfbeeda_682.png)

We're going to put a break point。At this point。160。不行。嗯。想可る。Okay。なち？Flag one， Yeah。

 I was sure didn do it like。I think。That is Rick。屎。This is correct。This is like hi correct。Okay。Okay。

Now， let's analyze this。The ball on the right is the normal ball and the ball that just hits is supposed to be deactivated。

So I suppose that's going to happen。Yeah。嗯。Yeah。Okay。Next frame。Next frame， not next frame。啊。Fex 3。

What ball is this。嗯。Not sure this is correct。是啊。Oh， we are the third ball。Yeah。This is not correct。

We're not supposed to be active。Oh。No， I thought it。Where do we test the balls， We test the balls。

 I think this is supposed to be correct。I don't know。We deactivated both of them。

 Let's see next frame。 Well， next collision。Oh， I suppose you are correct。You know， were correct。

Because the timing is a bit different because we're debugging okay。Okay， so that was perfect。Yeah。

I think it's correct。But this is hard to tell which bottle is which。Yeah。Yeah， I'm pretty sure。No。No。

 that was not correct。She probably recorded this well， it is recorded is enough。Yeah。

 I think I'm going to take a look at the recording next time。In light slow motion。

Just to see what happened。Because I'm not entirely sure。So I'm going to just note that we have a bug。

 let's see what kind of a。faced。I don't know what consequence。What what we did。See。

 sometimes it works perfectly。See， the comment didn't work this time， see。This is really weird。

 I'm going to have to。Save that for next time。Although， the colors are pretty nice。



![](img/2d11af16ffb245ab1947921d1bfbeeda_684.png)

嗯。Yeah， so I'm going to note。To do。De bug。Comment。Stoping in the middle。Of a run。And thebug。嗯。

Possible weird。对宝。Behavior。C。You're not British。 see。See episode 4 at， let's see。Approximately。

This time。Okay。Now， let's do the final one， right， just because we did already。

 I think I'm going to straight out and do the， the。I know youre supposed to do two more when we。

你 see that else。Yeah， the stadium， the chess and account。Yeah， no it account doesn't count。

The stadium'm going to create。I I'm going to hardcode the stadium。No you know what， no I'm not。

 I'm going to treat like black black Christ。Case level。Three stadium。Break。

You want to create a block block， let's do like a eight by eight。y。And then。The create block block。

 I'm going to add a。A like。啊，上到。X。Offset。Do you like that？O。So，0。And this is going to do like。20。

みてぐらい。-1。

![](img/2d11af16ffb245ab1947921d1bfbeeda_686.png)

ok。Yeah， 20 it was。

![](img/2d11af16ffb245ab1947921d1bfbeeda_688.png)

But actually， I think that was not correct。

![](img/2d11af16ffb245ab1947921d1bfbeeda_690.png)

Okay， that was correct， Okay， this is pretty cool。

![](img/2d11af16ffb245ab1947921d1bfbeeda_692.png)

Now what am we going to do？

![](img/2d11af16ffb245ab1947921d1bfbeeda_694.png)

Is。Cas like a。Let's say rivalry。我。I say if it's one。We're going to do this。Else， if rivalries， too。

 we're going do this。And then I'm going to pass。0ero for rivalry for for the normal one。

 Now we're going to do one。ok。

![](img/2d11af16ffb245ab1947921d1bfbeeda_696.png)

I think we're starting to get somewhere in terms of levels。



![](img/2d11af16ffb245ab1947921d1bfbeeda_698.png)

Okay， now this is pretty cool， right？Yeah。Yeah， okay， now I'm going to have two balls。



![](img/2d11af16ffb245ab1947921d1bfbeeda_700.png)

I already have。Set up。This one。Okay， now in the。Stadium。We're going to do this。Then。

 I'm going to set the balls。0 dot flex。It's already active。Go to be right A。



![](img/2d11af16ffb245ab1947921d1bfbeeda_702.png)

And just possibly based on one。 So we're going to see a lot of plugs， a lot of。



![](img/2d11af16ffb245ab1947921d1bfbeeda_704.png)

Extra bucks。Okay。See so you just ignore and this one collides。Okay。

I think that's going to be cool see。Oh， it going to be hard， Yeah。

 I don't think this is going to end up。In a game， actually。

I don't know you guyss going to have to play and tell me。What do you think？Yeah。It's not。

 there's not enough time。But we can start tweaking that， maybe。Yeah。

 I think all we have to do is tweak。

![](img/2d11af16ffb245ab1947921d1bfbeeda_706.png)

So I think we're going to do。

![](img/2d11af16ffb245ab1947921d1bfbeeda_708.png)

Hard to do。We are going to debug these guys and we're going to add a print console。

At least for numbers， just so we can。More easily fed。First， I'm going to do the console。

Then I'm going to。And print。Then we'rem going to debug the comments。

 we're going to see debug the tree， the three ball behavior。And they're going to improve。

And they are' going to improve。The riflery。And then I'm going to add block。At life。嗯。Lets do。对。可以。

Initial gameplay。And then we're going to the nice。I pull game play I need that。

And small fuel paths and the engine improvement。Yeah， I think that's a good plan。

I should also do the。我不屌得系。The chess。Yeah。So。For the block block。Also going to add the Y offset。

And just do the same thing。可以。And yeah，0 as a Y offset。And'm going to do the same thing。

For the chess。L 0，4 chess。These are not fine levels， these are just for fun。

Just for us to get to know the game more。Let's see。In the spacing of。

 I wanted to change the spacing to be like X to Y。Ex and Y space。Or I could just like you。

I could do a like。清楚。Yeah。没表对的。嗯。No X offset。But I'm going to add for why offset've set。

 I'm going to have add a。Do we have like the block， yeah， we have the block have size to add block。

Have size。Thanks to。Yeah。And then， I'm going to add。I you like what。L add to。Yes。lect minus-8。

Blalock cap size。Oh， we don't have block half size。I're gonna have to hardcode that。



![](img/2d11af16ffb245ab1947921d1bfbeeda_710.png)

ok。Oh， this is wrong。But that's not， that's not。啊。

![](img/2d11af16ffb245ab1947921d1bfbeeda_712.png)

It's pretty bad。Let's do like。

![](img/2d11af16ffb245ab1947921d1bfbeeda_714.png)

我。

![](img/2d11af16ffb245ab1947921d1bfbeeda_716.png)

Yeah。

![](img/2d11af16ffb245ab1947921d1bfbeeda_718.png)

Now。It's going to be a pretty crazy call to work on every single case。

 maybe maybe I should just copy this for each function。Not sure， but what I want to do。Is for now。

 at least is to make。The space in。Yeah。一跟人比背心。A vector。Okay。2。Okay。Now好。I'm going to do a two。

Spaccing等。

![](img/2d11af16ffb245ab1947921d1bfbeeda_720.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_721.png)

let次。Yeah， I think two is too much， but that's the basic idea。



![](img/2d11af16ffb245ab1947921d1bfbeeda_723.png)

That's just a too I should make the offset also a factor too。Yeah， to。



![](img/2d11af16ffb245ab1947921d1bfbeeda_725.png)

Before me。And spacecing许可。

![](img/2d11af16ffb245ab1947921d1bfbeeda_727.png)

I think， okay， that's what I wanted。I think we're going to do that for now， not that chest thing。



![](img/2d11af16ffb245ab1947921d1bfbeeda_729.png)

Yeah。But。Yes。嗯。Okay， then I'm going to like minus6。I can do more like at minus 12。And then。

 no spacing。We're going to do two rules。 Then we're going to change the life。

 That's the point of this guy。 I'm to change the life。



![](img/2d11af16ffb245ab1947921d1bfbeeda_731.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_732.png)

For the。

![](img/2d11af16ffb245ab1947921d1bfbeeda_734.png)

Too much。No， that was all right。Oh， that's pretty cool。



![](img/2d11af16ffb245ab1947921d1bfbeeda_736.png)

Okay。嗯。Okay。

![](img/2d11af16ffb245ab1947921d1bfbeeda_738.png)

Yeah， I don't want to play around the life yet。Okay了 see。Yeah。Not sure。 Maybe。

 maybe the point will be kind of a to control。Have the balls close to each other。Yeah。

 see that was entirely wrong。But I want at least be able to test。不 cheat。Yeah。

Just to see that the collision worked properly。Yeah。

 I think I'm going to end up doing like one ball that changes its state。Maybe a pickup。



![](img/2d11af16ffb245ab1947921d1bfbeeda_740.png)

Make change state。Yeah， but I think that is it for today。



![](img/2d11af16ffb245ab1947921d1bfbeeda_742.png)

We did a lot， actually， a lot of gameplay playing around with stuff。啊。

I think you could have won that one。Yeah， this doesn't look like a normal breakout because of the colors。

It kind of， it kind of。And it looked like it。Has something special。This one with the pickups。

 the pickups， I think was the thing that worked the best。And the normal breakout too， to be honest。

Yeah。Oh with us。

![](img/2d11af16ffb245ab1947921d1bfbeeda_744.png)

啊。Okay。😊，So that's it for today， we have a ton of stuff to do。Right。And。

Maybe just maybe I'm going to do this first。Jessica， I think that's going to dictate。

A lot about the game。So yeah， first of all， I'm going to do the a black movement part。

And then I'm going to play around with it。And then I'm going to go ahead and finish。

 finish the problems that we have。Then create more levels and then you can go back and do the cleanup and feel anything like that。

Okay。Okay， so if you want to download the source code for free。There we wrote today。

 if you want to download that source code， you can go to my HO page Im going to throw that on the chat。

 but it's dzd。h。o you can look for this game or the latest game that we're building now。



![](img/2d11af16ffb245ab1947921d1bfbeeda_746.png)

And then you can download for each day source code。I'm going to post today's SA code later。

So you can download that。

![](img/2d11af16ffb245ab1947921d1bfbeeda_748.png)

And you can also watch the previous episodes on YouTube with three episodes so far。

 this is the fourth one that we're finishing now。And yeah。

 you can watch from the very first line that we wrote and every line that we wrote in this game isn' in there。

 so there's no like magic thing that happens。 you can write you can see the whole thing from scratch。

And hopefully next time we are going to do the crazy gameplay thing that we've been willinging to do without further。

 you know， I don't know tangents， gameplay tangs， but those things are good because itll allow us to understand more about the game and what makes it interesting or not you can also play the game now and change the levels and。



![](img/2d11af16ffb245ab1947921d1bfbeeda_750.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_751.png)

Check out the know。The pickups and。And the avoidable things。And。



![](img/2d11af16ffb245ab1947921d1bfbeeda_753.png)

I think the problem， yeah。I think the problem may be the same problem just because I just noticed something。



![](img/2d11af16ffb245ab1947921d1bfbeeda_755.png)

Debug。迪。2 bugs down。Here might be。When the collision， I think that's the problem happens。1 x。Yeah。

 I think that's the problem that's going on。 Oh， you know what。

 it is the problem because when it happens on X， I don't think we test。I don't think we， yeah。

 we don't test。This guy。The ball destroyed tried under a apply。But that's okay， but we don't test。No。

 I'm not sure。Not going to pretend to know I'm not going to solve the problem now。 Okay。

 so watch the other episodes on YouTube。 Check out the source code on HIO。

 and I'll see you the next stream here twitch。

![](img/2d11af16ffb245ab1947921d1bfbeeda_757.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_758.png)

See you guys later， thanks。

![](img/2d11af16ffb245ab1947921d1bfbeeda_760.png)