# 【从零开始用C语言制作游戏】 p13 Making a game in C from scratch! Ep 13： -Main Menu, Save System, Im -BV18i421a7DD_p13-

Hello everybody， welcome to my new live stream where we are creating an entire game inC from scratch。

 you can see the whole process ever from the first ever line of code all the way through the gameplay and the engine and the rendering and the audio。

 all sorts of crazy stuff。😊，All the way to the final game， I hope， and it's released。

Let me show you how the game is so far because it's coming along， it's coming along pretty nicely。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_1.png)

So。Well。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_3.png)

Okay so。We changed the controls last time。To help debugy。And apparently it kind of broke the game。

The lock mouse。Well。Okay， that was weird because the mouse was locked。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_5.png)

Okay。That's my life。I think I I。I didn't compile it last time。哼。😊，Back to normal。

 we are creating this game， which starts off as a breakout clone。

But then I started creating cool things like。First idea was to add some powerups。Yeah。

🎼So we already started implementing。Inesting ideas。

But the major idea of thinking that I played around with。🎼Was heavy。

Different arcade games as breakout， so here we have prom breakout。🎼Yeah。

And we have spacecing beers break out。Yeah。Okay， and in the past few streams。

 we've been improving the game engine。Support kind of the final pass in gameplay because you guys remember from the first from the first ever stream。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_7.png)

We kind of a that。 We kind of explained the plan， and we are coming far along it pretty well。 So。

 first of all， we did like。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_9.png)

Small engine。To get started。Did that in a couple in the first couple of days。

 they really did like first。Game play pass and both both of those。Are okay。And then we。

 we are almost done with the。Like engine improvements。To support。Final。Gammeplay。

And now we are almost done with that。 We're going to finish that today， hopefully。

 and then we can do like。😊，gameplay。C。Then we can do it like a polished pair。

Polish on both the game and the age。 So we are almost that if you go to the YouTube page。

 which is YouTube dot com flash Dan and Dan。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_11.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_12.png)

You can see that the last restrains we did， like implemented。Rotated rectangles for graphics。

 and we also did like particle systems before that。

 And we did bit mapps and a s rendering and we added audio and mixer。

 and we also added parallel programming。 We made a job system so we can make not only the audio parallel。

 which we already did last time， but maybe the rendering in the polish path like that。

 And just a quick note， I have been I have been uploading these highlights。😊，Videos。Because well。

 the streams can get pretty long， like two and a half hours， four hours， two hours。

 three three hours。 And if you want to get like the basic idea and the like the best moments。

 so to speak， you can just watch the highlights。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_14.png)

And you can also download the full game and the source code on HO so you can here to the HO page。

 which is Dandenth。o， you can see there are a couple other cool gifts。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_16.png)

And。You can just come here and download。Every day， the executable and the source code。

 you couldn't come from every the first day that we wrote like。

Started out with pretty much not much of a game， right， all the way to what we have now。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_18.png)

So that's the basic plan we're going to finish the engine improvements and we should do the last thing we have to do in the engine improvements。

And this past is the safe system。 So that's what I'm built today。

 And then are also some things that I want to do because I started out。

I started creating the music for the game。 and we' want to show you guys because the last music that we we played this music。

😊。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_20.png)

🎼That I did implemented last time around， that was for my old game。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_22.png)

That I， have also created。 But this one， I think is a lot cool。 I'm gonna play for you guys。😊。

And I maybe you can guys and tell me what you think。Rachel says I liked it， thanks。

I'm still very much learning about you know making music and composing things like that。🎼But。

I also liked it so I'm glad you did。So the challenge for today is a lot actually I made a couple notes so first thing these are some of the ideas that I want to implement in the other gameplay pass。

 these are the games that I want to at least try to do in a breakout mode。

And there are also a few bugs that I found by。Just playing the game。

And I was also want to implement things like a policy system for dev， we're going to do that today。

 and then we're going to finish the engine by doing the safe system which we're going to save the high score and the unlock levels。

 and then maybe if we do that we can not we can do the side effects because I have also。

Like downloaded and organized a lot of side effects here so they have brick side effects。

And a Com sound effect。It's kind of where youre down to know fireworks。Forest he。You like game over。

It hits。And I got a lot of them and they increase pitch and that actually matches sound the scale of the music。

Cl style， Hey， man， how are you doing。Uh so I think by adding that。

 we can do some pretty cool things as well as like power ups。Pre downs。And our sign， yeah， spring。

That's going to be fun so hopefully going to get to implement those today。

 so this is a basic plan let me just open far codeder。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_24.png)

诶。So the engine improvements is the last thing that we need to do for the engine。

 which is the safe system。And I'm going to also going to。

Fixed those crashes or not crashed like the bugs that I found out。Okay。

 and then maybe we can go back and do like the gameplay ID。ok。😊，So how's it going for you。

 it's going doing great man， hopefully have a beginning a beginning of a nice week and hopefully it's going to be great。

😊，For you as well， for me， it's been doing pretty pretty well， okay， so there was a bug。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_26.png)

That it was kind of hard。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_28.png)

🎼2。To get get to happen again when I was pretty much done with this level when I was when I finished。

UP it， they were like， I don't know， like three blocks remaining。

And one of them wouldn't get destroyed like I really hit it， hit it in a ball like reflected off it。

 but it didn't get destroyed so I was like， okay， that's a weird bug let me try to understand it a little bit more and it turns out。

That when I destroyed the other two blocks， I won the level。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_30.png)

So I was like， okay， this is weird。 so I investigated a little a little bit。

 but I wanted to fix it on screen and the problem was。They do could。Do ball col test。This guy。

 if we hit the ball on a block， right， we lose a life。

And then we may be called destroyed and things like that。However， this is called inside a loop。

And because we're going to have more than a ball right。

 and the problem was I hit that block with two goalss at the same time at the same frame。

So one ball said， okay。Removed own life。 and the other block also removed own life。

So when I compared the block's life。2。To 0。Well。Not sure where compared it to0。Let see。Yeah。

 like this。If not， block life。呃。The life got to minus1， right？So what effect。

 what I'm going to do instead of just changing this if I'm going to assert。That this guy is greater。

Then0。And that case would crash right the bug that I found out。

 so we're going to have to fix that and order to fix that。If in the do well， in this case。

 if we were destroyed， which that's going to return， I'm just going to break out of this book。

 so I don't need to。Do that again because I was a distract so that'll stop that bug。

And we're going to have to。To work a little bit more on the return value of this guy because it does return on bull 32。

But I returned if it collided， what we're actually going to return。Is that a。If it was destroyed。

Yeah。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_32.png)

Okay， now we should have the same thing， but that case， which is hard to reproduce。

Should be for a egg。Yeah， so apparently everything。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_34.png)

🎼This how it was。Let's see if then I'll fix it。 Okay， now。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_36.png)

呃。Yeah。😊，Don't test collisionition with other balls and phone balls and strike test。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_38.png)

And another thing that I don't know where it happened。

 I think was in the when we fixed the risk center。The pond guy shouldn't be touching the top of the screen because that way we can't get the ball behind him。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_40.png)

I'm going to do really quickly。Is just to。Like change， let's see， yeah， change the Y offset。

Why upset。Which is like rather facing x and y offset so。This guy has do， like -25。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_42.png)

🎼To make it了。🎼Yeah。That's a little bit better not only is it a bit harder。

 but it's easier to get the ball behind him maybe。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_44.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_45.png)

30 which is no kind of what breakout is about， right？



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_47.png)

I'm going to turn audio off for you guys just so。bother you till we go and implement Yeah。

 this is a little bit better。 Let me try and get the ball behind it and。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_49.png)

Because it's challenging enough。But it's also， I don't know。Not like impossible。That's true。Well。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_51.png)

It may be pretty hard last deal。If you can play around that。

 I just want to do a little bit of that and also going to do in the first level。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_53.png)

I'm also going to throw the blocks a little bit。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_55.png)

Down as well。啊。At a little bit of why offset。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_57.png)

Throughout like， maybe。3。Just so it's a little bit easier yet to get。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_59.png)

To get a go。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_61.png)

Okay， now these are our small gameplay chain it's going to do a lot of more game that that was。

 however， a pixelel crash。At some point， I was playing the game and it's hard to reproduce things that so when it happened。

 I kind of had to investigate that for a bit。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_63.png)

I was playing the game， I don't remember which level that was， but at some point I crashed。

And I was like， what？

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_65.png)

So I investigated a little bit， and I found out that our。We have a typo in our renderry。Yeah。

 it was the mean and max balance。嚟。Here。系诶。Yeah， the transparent rotate rack here。

 we're losing the width。For all of those。This is like wrong， so。X， I'm going to clamp that to zero。

And the width and the max went to clamp。From zero to the height。So that was an annoying crash。Okay。

 and let's just try to see。If therere any improper use of like width and height， so width height。嗯。

Yeah， this is correct。At the height。ok。T night。Okay。Okay， this what we fixed。啊 yeah。Okay。

 so apparently that was the only problem。Nice。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_67.png)

Another thing I wanted to add for the game was in the development mode。A pause button。

Because sometimes when you know。Especially because we locked the mouse as you can see like。

 oh we can't see because of because of my head and my head's on the way， but we locked， see。

 trying to escape there my head。We locked the mouse。

So we could get like a proper wrapping in when we got slow down or。You a different cases， right？



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_69.png)

But。😊，It's hard for us to， you know。Come here and pause that。

 So what I'm going to do in just a deeper case。 I'm gonna to do like。A key。That， let's see。

Will not simulate the game。I think that's the only thing。Then I want to stop doing。Toight if。

Do we have the development？Go I don't think we do， Yeah。

 we do because we just serve so if you are developing。We are going to test like if132 paused。

So if you are not paused， we update the game。爱 mean。Yeah， we don't need to get that。

 but we are going to。Change this case。That's do， if it felt。没。And， let's see。

What key should we buy into pause and let's do like。F1。Do with2 pause equals 2。Well。

 let's just toggle that。And then。Well do a 32 pause equals pause。Yeah call that paused。Okay。😊。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_71.png)

Well， if I could type。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_73.png)

I see， so we' were playing， then I pressF1。Okay， so。is诶。If。Yeah， if we press it one。

And the button is down。And is down is different。From Lewistown。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_75.png)

对。😊，Only when it press。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_77.png)

Nice， so in this case， in know， in fact， I'm also going to。Tigle the light。 Oh， let's say， like if。

Mouse lock。lot mouse。Cold。We 32 like me。I'd say well， if we are paused。We are paused。Well。Yeah。

 I just title that。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_79.png)

Block mouse。Okay， so we're going to freedomdom mouse and we're going to。Be able to。Okay。

 so now we can do all sorts of stuff like increased size， decrease it。And then it can go back。

Awesome。😊，So this will help debugging。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_81.png)

We're going to get to problems like that。So we can pause inspect spec and things like that。

 but that was pretty easy and that was pretty cool。So。Now let's go。

 let's do the last thing we need to do to improve our engine。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_83.png)

Which is a safe power game because we have the high scores。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_85.png)

And we wish to save that， and we also should do like A。I lock。A lock。

It likes the level kind of system， right？There will be a main menu and then be able to select levels。

 we could also do that。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_87.png)

Yeah。Let's do like the first version of the main menu。It's going to be pretty bad at first。

 but I don't know。Everything starts pretty bad， so I'm going to create a menu。夹起。In the simulate。

Let's see。Update game。So you have all sorts of crazy stuff going on here。And。I am going to。

Do they play movement？In both， because the way you'll control the menu will be with the player。

I think that would be interesting， so I think just from everything from down here。

 like simulate the level and the update the ball。Yeah， everything from down here I'm going to do。

Later on。Maybe I'll keep the draw messages。呃。I think I'm just going to delete this guy。Well。

 not going to that yet。And yeah。Everything from here I'm also going to delete。

 but the player render I'm going to keep。So。And the comment in strong blogs on advanced level。

You play your life。And they draw core。This。😊，Do like， simulate。I do like updates。Many will S DT。O。😊。

And yeah， and this guy is going to be like。If let's call that game mode。

 I love watching our thought process in this game engine program it's really helpful， thanks。Yeah。

 the idea is to show the whole thing。You know， even starting with small stuff of like making a window appear。

 which was the first episode all the way through my complicated stuff。

 like we did a threading last time that was pretty tough。Oh， not too hard， though。

 but that was pretty hard。And things like that。 So I try to talk a lot about what I think to help you guys because that's not a very complicated game。

 So I think you guys can follow along as well。 you can go to the H page and like download on the source code whenever you feel you want to follow along and maybe you gonna try。

Your own game with that。 that'll be pretty cool because there are awesome series like this one。

 but it's usually a huge game， so it doesn't get finished like ever。 And we are， we are。

 I'm I'm already seeing the light at the end of the tunnel。😊，So let's call that games game。

I don't know if game mode that's the best idea。Maybe game state， I say game mode equals gameplay。

Okay， and I'm going to create a game mode kind of stuff。云辉。And。Meニュ。Okay， again。

 I'm going to have a game mode， which is。In the initialized。I'm going to set。

 I'm not going to do start game。Not going to do that。But I am going to load stuff。

 but I'm going to set the game mode。救命。Now。Let's do the mail update。

And I'm going to do like if pressed up。嗯。Let's change the game mode。To8。Okay。

And we are also going to take these guys out as well。But I want step out of time， so input。

And but I also have to take things。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_89.png)

Okay， now let's see what we have。Wuse。That's like some abstract art stuff。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_91.png)

We are not surrender enteringing。Let's。That's render。佢。I think I'm just going to clear the screen。

With black。To have like the old school feel？

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_93.png)

Okay， but the player is all wrong。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_95.png)

I' am guessing the updates is not being done here so。The desired P。And then we do the renderer。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_97.png)

嗯。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_99.png)

Okay， that's weird。 Let's see。Oh， I guess these guys do not think except like the invincibility。啊。I。

Well， let's try to do the。When we initialize。Let's try doing this start game。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_101.png)

Even though we're not going to use it。Yeah， so we had like initialize variables， things like that。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_103.png)

Okay， so this will be an opportunity for the player to get used to the controllers and then also be the title screens thing that that so。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_105.png)

What I'm going to do here。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_107.png)

Oh， let's try you can get to the gameplay。Yeah。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_109.png)

But if I remove this disability sheet。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_111.png)

Yeah。Take night。 now， let's do the proper levels stuff， so。We have。 Let's see。 going to create now。

The levels。Do file。Thats doxy。And I'm going to like copy a whole bunch of stuff。

Like all that arena stuff， the ball， sh stuff， the ball。Particle。The maybe not the place to。Yeah。

 not do the taste。And then let's do like the score touchless bonus。Touch this mouse。

That was a really bad name。The block。P up stuff。The arena current level， Bimap is going to keep。

 well， maybe current level I'm also going to keep。Well， now let's take that。Okay now。Sponwn particle。

Increase ball size。 that's。Let's move all that stuff。Test to wind condition， block destroyed。

 do above block collision， calculate neighbors， space invade stuff。Reset power in the goal。

 start game。Lose life simulate level。S make block。For level， and they're going to keep up thinking。

Gets removed。Like most of the stuff。Then we' want to think about moving what's inside symbolim game but。

And I'm probably going and do that after the player。Okay。This is a little bit more organized now。

 what we can do。Is in the。Well， in the menu， I should have like the level info， yeah。

So let's go to the menu and let's also compare。So。I'm going to do。Is like for。Each level。

I'm going to draw， let's say， just a number for now。 So I'm going to do like draw。Number。I。

 and let's see。I take so。A P， will do the position。Size， that's a pretty big number。Color。

 let's do white。All let's do gray and this light of the one will be white。Number of leading zeros。

 No leading zero。你的P for theP。We start off as being。Let's say zero well。We'll have to tune that。

A lot。But then would you like it。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_113.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_114.png)

没道鞋。Now let's give。我对着看一下。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_116.png)

ok。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_118.png)

Now we're getting some。Did the draw number return？The spa。You had the new PY。Let's do that。OPX。

I suppose。Yeah， yeah。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_120.png)

Then let's start off like minus。S？Well。3，2，1。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_122.png)

Okay。Well， I don't know， that's just。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_124.png)

We're going to do like the level name later on。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_126.png)

A little bit more spacing。Maybe。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_128.png)

Okay， now the idea is we're going to select the level with our guide。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_130.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_131.png)

So in fact。Let me think。Should we do like a little bit more generic thing。 so we're going to do like。

嗯。啊。Like， first。And then we learn do， like the。Geltapy。Okay， and the first。

 let's say it's always minus 60。In the deelta， I want to go like 120 units divided by the LC。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_133.png)

来起。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_135.png)

Well。Probably probably going to be late。This guy minus 60 right。我要。120 divided by L plus one。

I suppose。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_137.png)

Because elbowst。So I think it would be either plus or minus the。Okay。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_139.png)

So this would we want。 Now we can now refer to our position in a more programmable way， let's say。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_141.png)

Like hot level。It's going to be the player。Visual P done X。Right。So let's draw that。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_143.png)

Let's say，-60。I don't know， I's do like。-30，30。Let's say we are 20。Okay。

 so first thing we need to do。This may divide our position。Yeah， maybe yeah， we're going to subtract。

I was just， yeah， I'm just going to divide that。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_145.png)

By the the。Let's called that。呃。Range。And theyll divide that by the end。Think。😊，And I feel like。H啊 I。

Equals hot level。Then dry， dry it as a。White。Okay， and Dan。Oh just。感じ。Just a cold。Okay， not working。

Particularly well， let's take this out。And。That's just print。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_147.png)

O。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_149.png)

We're just zero。 And for some reason， we broke。We broke the。The book we had before。Oh， okay。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_151.png)

Okay， now our hot guy isn't calculated properly。 let's say in this case。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_153.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_154.png)

If we are doing like 20。Divided by。Well， yeah， that was wrong， we don't want to do that。

You want to do this guy？How much of this guy like six， no， this is wrong。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_156.png)

Oh， we actually go。 Yeah， I'm sorry， have to divide by the。Delta P。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_158.png)

Let's see that in this case， is' 30， so they made 20。Divided by 30。No， should'll be oh。

 thats do like this if we are on minus 60， we want to get zero。Right。So， she would like。-60。Plus，60。

We broke what we had before programming in nutshe。Exactly。But that's part of the challenge， right。

 I mean， can you build， how much can you build？Before that becomes too complicated and when it does get to that point。

 we should do what we're starting to do now which like making things a different file。

 making it easier to understand things like that。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_160.png)

The next one。Okay。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_162.png)

I'm not sure the math behind this， let's do like one more time。Let's do the other way。

 if we are at position 2。We're going to do like two。Times the deelta。Time， the Delta。

 let's say it's 30。Yeah， plus there's a guy。Plus， the first B。Yeah， okay， equals P。

So what we need is。Well。It's like the index。 And this is like the delta。

So now let's separate the index from the other guys。 So I'm going to。

I'm goinging to do index times Delta， index times Delta。Would be P minus Fb。Divided by。

F by the deelta。 Okay， so hopefully thatll works。 So be。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_164.png)

P， which is like the player visual P minus the other P minus the first P。Dived by， okay。

And then we can get any art of that so yeah， sometimes you just have to sit down and work with man。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_166.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_167.png)

1，2，3。 Okay， I think that's working。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_169.png)

But only when you go past the level， so instead of offsetting。I'm just going to。Offet that。By half。

Of theta。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_171.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_172.png)

Okay， that was wrong。Okay， yeah， this guy has go。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_174.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_175.png)

Okay， zero。Yeah， actually。Okay，0，1，2，3。Yeah， that looks perfect。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_177.png)

And that's just for our ease of conscience， let's a。At a hot level。piritatory equal than zero and。

It's also less than L count。Now we can start。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_179.png)

Select yourself。Dude， how cool is that main menu， Oh， crap。so嗯。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_181.png)

Yeah。I think。I'm just going to clamp。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_183.png)

So about asserting that。Because I know。Yeah， there may be some like crazy mouse movement that a player。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_185.png)

K do。And we don't really care， I mean， as long as we don't go past， okay， awesome。Now。

How should we make him select。Because the only interaction we have。Is with the ball。

 That's so awesome。 Yeah， thinks going to be a great menu， yeah。😊，The only interaction， I think。

Maybe you can do like the old breakout thing。That he starts out with a ball attached to him。

 but that's kind of ugly。Let's just do a mouse click， maybe shoot。Whatever you want。

 you mean like have the ball interact like this？Like he the ball。Like drop and then have two。Well。

I think that' would be really inconvenient。For the player。

 because maybe he'll get the wrong one or maybe he just wants to quickly get to the other point。

So I don't know about that， I don't know。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_187.png)

I'm going to use the mouse click for now， and we're going to keep。That on the back of our。Mind。

 let's see。Okay。呃。LetLet me think。Well the mouse clip。

 well I think you'm just going to steal the mouse clip from another project。

Because it's not really that interesting， it' still like。This code's really bad， by the way。

 I do likeos。G mouse is down。I don't think this guy does click。It's kind of confusing。Let me see。

Well， let's just。Search for that。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_189.png)

And get the。Lets do MSDN。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_191.png)

I think it's just an event。That's not what I want。Al button， yeah， it's a window event。Okay。😊，W。

 wild the cursor is in there。Plant area off your window。I don't think we' will capture that。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_193.png)

You know what since？I'm not going to spend too much time with that for now， let's just do like B。

Let's just do the up key。Start game。 Well let's do set set of current。嗯，lettle。To the hot level。

And then I it's talking。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_195.png)

Okay， so let's see if we start level two， we do。Let's see you start level three， we do。Yeah。

 I want to do， I think the mouse clickick would be a nice one。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_197.png)

We should also work on a transition， proper transition。Okay。

 but now let's do some more interesting things with that， first of all。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_199.png)

Let's。Yeah， see the mouse click。Well， I'm assuming you're going to play full screen。But for now。

If the window is offset from the center， that's kind of bad。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_201.png)

Yeah， I think I'm going to fix that real really。Stuff like like mouse instead。

Setting to the center of the screen。I think I'm going to do the center of the window。

Get window racked。Yeah， I'm not going to do that。嗯。I'm going to do it like this。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_203.png)

Now you're always entereded， yeah。Okay， so now we can do the this guy， the last button down。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_205.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_206.png)

Message。Let's do here in the input。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_208.png)

O。😊，Yeah。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_210.png)

Let prints。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_212.png)

ああ。here just to make sure that we want to get that。我要佢。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_214.png)

Yeah。So we can pretty much。Like。The platform common。Do you like but。Left mouse button。

And then we set the button。Let's say， you。Not。In puts dot button。black mouth button。Dot is down。

It true。And。It changed。Also， it goes true。And then。When we did the button up。对个。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_216.png)

Okay。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_218.png)

没有。Let's go back and do if we press， we should really do like。Maybe we should do after。This guy。

Just because we may change in this frame， but who really cares and let's do button。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_220.png)

That mouse。Let's see you get them out， but okay， okay， perfect。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_222.png)

Nice。Now it kind of became a priority too。To hide the mouse cursor。

Now that it's in the middle of the game。Let's try and do that pretty quickly。I don't know。

Because we can do like。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_224.png)

Set cursor and pass 0。But I don't think they'll be enough。 Well， well， that's enough。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_226.png)

哼屎知。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_228.png)

And。In our debugging pause guy。Let's set the cursor to。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_230.png)

Thearrow。Let's do set。What can we pass？We can you load the cursor。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_232.png)

Wow， that kind suck。It's just for de purposes。Chris Sir。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_234.png)

Then here we'll do。H。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_236.png)

OfThat。cur。Lo。诶。嗯。H icon， No variable declared before。What。😮。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_238.png)

Competible type。Okay， yeah。I have to pass the。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_240.png)

Do have what we call the instance。Call that the windows name。Okay。

 that was a very weird error message。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_242.png)

But let's see if we pause the game。Well， we don't precisely get mass。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_244.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_245.png)

嗯。Saad cursor to zero light if。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_247.png)

Pas。I don't think that would change much。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_249.png)

Well， if we are not。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_251.png)

Yeah， you know what， seems is just deep de code。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_253.png)

I'm going to say that's good enough for now， I think in his show cursory。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_255.png)

Oh。And pass a bull。I think you are right。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_257.png)

So cursor， Let's see。Thanks for the tip。Yeah。That's awesome。嗯。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_259.png)

You like。So I suppose the other one that we did， which was Se cursor。

Maybe you could just do show cursor here as well。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_261.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_262.png)

Yeah， well we well， maybe if you do。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_264.png)

Show cursor here。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_266.png)

We don't see， yeah。I don't know why you don't see that。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_268.png)

When we press the phone， see， I just press the phone。

 so I have to move the mouse up and then when I go down。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_270.png)

But I don't know， that's not really a problem。But。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_272.png)

Oh， thanks anyway。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_274.png)

But well， got what we wanted， basically， right？So。Pretty good now we have our menu now let's do what we came here for。

Which is our safe system。I'm going to create， maybe here。Or do you like a level info？

And all I have now is like block。Lot。And a high score。I already have a level info。I'll do， like。

 a level。Levels save。Okay。Yeah。And right here。说那个。Here。I'll do an array。Of level counts。

WeCall that level saves。O可以。And in the initialize。I like。😊，Load， save。

But the first one will always be true so I can do like level。

Safes at the first level position dot block。あ lot。Es falses。Well， they should all be true， right。

 so a load safe。Let's just initialize it。Recount。Level saves。I plus plus。And let's do the level。Yeah。

 well， that's just do。That all saves。I got locked。次ビ？

Should maybe should do like the other way around just to get the initialized version。 But okay。

 now in the menu， oh we should really。Okay， so we should probably。Have this guy declared。

Before everything。In the menu。诶。Let's go。For each level， can you like。If。Level saves。A lot。

 so the lever is locked。Else。几。😊，It's locked。 Let's do like a very dark gray。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_276.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_277.png)

Nice。Nice， so。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_279.png)

嗯。We also create like。Nonex functions， like。This is really problematic。 I wanted the。

 maybe I'll have to create like a Hader file because I don't I don't really like those I wanted。嗯。

Now let's just going I'm going to create an internal。Vid。Which is like load save。Internal void。Save。

 save， save。Load， let's say， load gain。啊谢谢。几。😊，And。Now。Whenever。We we。Yes。When condition啊 win。Dctory。

We're going to set to advance and we're going to set the level saves。知。😊，Read the level。

Save at this point。At a current level。Plus one。Well have to cap that。Yeah。嗯。

I always if current level。Is less than。Count -1。 So if you're not in the last level。

 we're going to set the next one。To not locked。Now one' just safe。Yeah。Maybe this guy。

I declare a appear。And then， yeah， I think。So I kind of don't declare the levels which levels exist inside the levels。

Filile， but I' noticed that's。Big it a power。That big of a problem。

 So let's do it like this when I press the。Ask key yourself going back to the game。啊。

Well instead of leaving the game， let's go back to the menu。Platform common。 Let's add the。

But escape。Then， here。Let's do the process。Process button。Thats prices the。Is it called escape key。

Yes。But。Firstscape。Instead of。Clloose the game。Maybe we should， I don' was closing the game。

I'm going to。啊。Go back to the menu so okay。电冇。If we pressed。你 ask you。

Profes ask going set the game mode。To。Meual。Yeah。But maybe I want to test。Up here。

So if I press the S key。Go to see this guy is the gameplay。ISe it to the menu。Else。

How could be so running？

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_281.png)

好。Okay， so ask should quit， now ask should go back to the meeting perfect。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_283.png)

Now。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_285.png)

You know what？So。I removed that sheet， let them put it back。The。Invincibility。Cheat。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_287.png)

Just so I can finish this level quickly。And。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_289.png)

Okay， so that didn't work。If I press。Down。I increase。 yeah， the DT can't go like times 10 anymore。

And that's also removed this。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_291.png)

DT can't。Can go out crazy。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_293.png)

啊。Yeah， the player kind of disappears。So let's丢了。If。Right。Pressed。Butom right。

What is the test phone condition？Blocks destroyed。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_295.png)

ok。So if you press for， now it should win。Well。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_297.png)

It's going to take a while out two。They is depressing twice at the escape key。

I press the right keep blocks destroyed。You the number of blocks well。Should be minus1。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_299.png)

Because we're testing if it's exactly like。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_301.png)

Okay， now if I go back to the menu。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_303.png)

Level one is。Available and you can go like play one again， Okay， now let's just save。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_305.png)

highigh score。Okay， so whenever we start game。What I'm going to do。Is set。The current games。

 high score。To the high score。嗯。Maybe I should just like us。Save high score。

Call and I'll do like the level。Saves at the current level dot high scores and people to the。Square。

But you have only。Score。Let's do， yeah。Okay， high scores。ok。😊，Now。

When do we need to save the high school Well， first of all， when to go？

And we should probably also set the score。And。Whenever we。Go back to the menu。

We should save the high score。In， in fact。Go to put this guy。Put in like。

And whenever I save the high score， I'm going to。No。Okay， and whenever I。Ever I win， so。

That's for wind condition。Whenever I win before saving the game。I'm going to。Save high school。 Well。

 let's call that maybe save high score。你必未。Update。I score。Do the Jonathan blow notation。

Of maybe doing stuff。Yeah。呃。Maybe destroy not maybe destroy neighbors， maybe update high score。Okay。

 and let's also。Well， we don't have this score。Sure you put that near the player。

Or we don't have current level。Yeah， maybe I'll just keep it there like。呢啲。嗯。Okay。

Now instead of saving high school， I'm going to do like maybe。High score。If we go back to the menu。

Or if we close the game。Not sure what we should do if in this case， we don't care。

 but if we close the game with the all four， which probably。I don't know if we should save or not。

I't know。Maybe see， let's。Sa。Think about that。Yeah， I'm pretty sure I how to do that。

 but I's not do it now。But that's also right， like the polish pants。Aine flip collarers。very quick。

Because you can do liking a window event。Think they'll get better。But I'm not sure if yout do that。

 though。 The last thing it was like。Yeah， I don't know。Let's cross that bridge when we get to。We。

 let's also do women lose legs。Game over。lose life。Okay， so we set this。We are。Maybe。L high school。

And this guy should return whether or not we updated the high scores so we can do it。Like this。

I score。Okay。Now， let's see。Where， where are we calling so。This case。

 we can always save because we updated the other well。Not really。Yeah。

 let's do this optimization thing。Safe game。And。This case， let's say if。This guy is locked。

We are not going to lock it anymore in they're them to save game。Whats true。Ifs。This guy。

Or save game。They should say， well， save。啊。How that shoulds it。

So should I save the game while I a know， let's see。Okay。I think we are in a good point。

Let's just turn in the load。We can do， like。老。Lad safe， load B。As you like。我。

For loading and0 for saving。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_307.png)

Because we don't have like print characters。One， so we load。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_309.png)

As's if we save。Well， we didn't save。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_311.png)

Re press and okay， yeah。Depress when maybe。If we update。We should say点。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_313.png)

I see， one。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_315.png)

Let's see。3，0， nice。 Now， if I only get like three again， I should， and I don't。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_317.png)

Okay， now I， I go back。 Okay， I saved the game。 nice。

 Now all you have to do is actually save the game， and load the game。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_319.png)

Okay， all I'm going to do is save like an array of these guys。

But I'm going to save like the array count。The level count。And the array。

Maybe I should just like a version。嗯。😊，I'm not sure if I want to do with something like。Yeah。

 I'll do a hardcod thing， so let's first add we have the OS read entire file。

Let's do an internal O S。Right。Entire file。And。嗯。😊，Yeah， I know what just to make our lives easier。

Let's make it like stroke。Safeing。Save data。Un do like。Levels， see let's call that levels。

And let's do a。Now， we're going do like。B version。Okay， yeah。So whenever we see。Level save。

 You're going to do。Save data， dot levels。I see。Yeah。首先。I was。Okay。いて。楽し。Oh。啊。Save data filess。Okay。

Reefinition。Okay now。我 gonna take个。A string， which is a pointer and a size。

And it's the same thing that we did and stuff。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_321.png)

Calling read file， I want to call write file。And we need to handle anything like that。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_323.png)

This is the call when the one is。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_325.png)

Right5 in returns。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_327.png)

If succeeds， okay， so。そそ。Hes this guy。Result。F， okay。So we need a file handle。

So we're going to do a pretty much same thing。But I start generic to read I I do a generically write。

Filepath I'm going to hard code data。诶。Save。Dot。Great。Couch。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_329.png)

系一下。呃。And let's do the create file。This guy。You want to do like。I could see you， probably。

Security action build zero。Create， always。Create new only if does not already exist。

 open always existing。Let's do create always。And we passed， I don't know。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_331.png)

flags or attributes， okay？File path， undecled identifier。Well。I suppose that was wrong。ok。

Not here or。Okay， so now that we do have a handle。Let's just call。

The fiO the buffer are going to be data dot。Data。And the number of bytes。To cast a D word。

 is going to be data。Size。And that number of bys is written。So， bys。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_333.png)

Overlapped。I don't think we care about that at all。 Let's see if you can pass zero。Can be null， okay。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_335.png)

Okay， actually， the result is going to be this。And。The bytes written equals to data dot size。し。Nice。

Actually。I don't know if we should like hardcode this or not。SoInstead of doing right entire file。

 I'm going to do right save file。Just so the game doesn't worry about your factory stuff。

Because that's like a platform specific。Sa。😊，If we want。To。If you want to save like more。

Kind of files， like if you want to save。I don't know what would we want to save？But in any case。

 there's a word for now。This is the right file， so let's do like the save game。In the save game。

I'm going to build a string。All that data data dot data will be the address of save data。

And data dot size is going to be。Size of sea， safety。Okay， then we're going to call that OS， right？

Say file pass that。Okay。That's it， and we probably want to do that in parallel。Like。And the load。

It's gonna be pretty。Easy， let's do like save。Version。So， we're gonna do the。Yeah。O。Read entire file。

And， you know， let's。Let's also do like。Internal。String O S。Bre save file。Again。

 just so the game doesn't worry about。Where the guys。Where， where the。

Where is the safe happening thing like that because like came the PS4。

 you don't do you do that and the game don't want to change that。 So let's just。

Just not worry about that at all。In this case， I'm going to return。The OS read entire file。

Passing the data， save。To have breakout。Okay， okay。 now let's add this guy。To the platform。

 common service。Okay， and I'm going to read。死块。And we're going to do the level。First of all， if data。

The size。这个问题就。That's one several times this do version。Equals。This guy。

Versions same as save version。Well， I should also set this guy， really。Yeah。This guy's the same。

Then we can read the whole state of the level state going to be equal to the same thing。

 so it's going to be a pointer。To a level， save。Oh。Save data。Okay。Now， whenever we load。

Save load game。嗯。Actually， in this， this case。We should already set。Thes save data。 version。

To the same。Great。Okay。Well， I think。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_337.png)

We are pretty much good to go。If I haven't done anything wrong， which probably did。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_339.png)

Let's test these two guys。 Let's go to the。Safe。😊，Again。Save game。Andload点。可以。😊。

Now well try to load the game and this is probably oil。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_341.png)

So I suppose now it's okay。To have invalid。We could also， we could also test if it， if it a。

If it exists。Why did you create OS Read Sa file if it doesn't call any OS specific functions directly？

Well， the thing is。The game shouldn't have to worry about where the save lives。Because on Windows。

 we are Sanet data slash save， right？But let's say on Linux， you want to save on that users。

 whatever。Fold is。What if on PS4， we don't have like a say search like this and we have to do an entirely different thing for Sa。

Because honestly， this call will not be called by the game。

We're only doing this because we're loading the resources like this directly。

 and that's not how we're going to do for the shift version of the game。

Like the game shouldn't have to worry about that。 All the game is going to do is like tell the operating system loads resources for me。

 and if they are。Like if they are on this place， it's going to load from this place if it's like。

From whatever else。Like。The cloud or whatever it's going to do other things if it has to decompress the data or load that asynously。

 whatever in this case， this is very simple we could do this directly。But it use。

But you use double slash and update game， which isnt， yeah， you mean like this， right， yes， this。

 we're not going to do the final game。This is just for us to load stuff quickly and we're going to do more stuff we're going to do like the sound effects like this。

 but when we build our acid cooker， which is on the polish pass， we're going to build an acid cooker。

 which is going to be pretty cool thing。We're not going to load that on the game。

 the game won't worry about the assets individually。

All game will worry about specifying what assets it wants to use and the O can worry about how to load that。

Because maybe we will extract that from the executable file。Like in the other game。

 if I can show you in the other game。The one that I saw cha wrote this game。This guy。

 the two handedpong ya？Let's see， crazy。The final version that I released is just the executable。

All the files that inates like the。The music and stuff is inside the executable pact。so。

If the game calls like load data and the Windows manage to do this。

're going to unload from Excutable， but let's say on the PS4 that doesn't happen。so诶。

It's going to be differently， so I'm just preparing things to be more platform dependent。

This case it's not， but since it's just test code， we don't really care。By the way。

 it's easy a small game。And we're probably just going to using a couple of platforms。

I could probably do that。Here and just if death。I hit those。

But yeah I'm just trying to make it like clear。Starting do to get an engine out of this game because this is like game development。

 that's not engine development， but hopefully you can do like some engine stuff。

After we do this game， and then we'll extrapolate and do things more solid。Yeah。

I think that'll be good， so if I think I deleted the wrong thing here。No， this is correct。

 this guy should assert。And yeah， this the other guy I want， so hopefully that was clear。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_343.png)

So， let's see。What do we have？We're trying to load the game and we probably didn't load anything because we don't have a load file。

 that's okay， no problem。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_345.png)

And let's say if we started playing around。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_347.png)

Let's how complete this level。So the data that we want to save is let's just go back to the。好。

I was correct。36 bikes long。And this is our memory。Should have like a one in the beginning。

And then if it's blocked， not blocked， then a high score of like 16。

How do you handle unor we don't do unicor yet。I don't think we're will， honestly， for this game。

Because that's not really fun and since it's a very small game and we do like lots past stuff。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_349.png)

Because you use the Win 328， yeah， we do use the Win 328。

Because we don't we don't do like absolute paths for anyone。

 so we' we don't have the risk of the user having a unode folder。

Because since these are relatively fast， there's no problem。And that going excuse you go pay Yeah。

 but we don't really care about that。 This is just windowow stuff。

 So when we get to to write the Linux platform C。Then we can do like full unicorder or whatever in this case we don't really care about that because this is like relative paths。

But like I said， in the full version of an engine， we should probably do like UTF 180 Uniicors for it。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_351.png)

Okay， let's see if we write the file， that was pretty instantaneous right。

 because it's such a small file？And， let's see。If we save， well， we did save。

 but we saved zero bitetes， that's not good。That's not very good let's。

 let's go back to this breakpoint。Oh did I save twice？Notm sure。Let's see the file handle is invalid。

Well， that was only the second time around， wasn't it？那行。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_353.png)

Well， but what？I thought we managed to load something。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_355.png)

Oh， because we didn't close the file handle。 Yeah， did we close the file handle here？No。

 we didn't close the handle in the read as well。That's a stupid mistake。In the read T file。

 I'm going to close the remainder。The handle。I handle。We should also close the line。

Because when we call write file， it doesn't actually write the file。But when we close the handle。

 it writes the title。So it kind of worked， right？

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_357.png)

But it kind of didn't at the same time。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_359.png)

Let's see。Okay。We were trying to save the game， oh， okay， so yeah， we are doing it twice。Yeah。So。

First of all， let's fix that problem。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_361.png)

In the levels。C音。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_363.png)

对。😊，Now， let's see。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_365.png)

Wow， now for some reason， we don't， we still have a cursor。So save game。From getting calls from here。

 that's perfect。And we're going to write the file。See。😊。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_367.png)

And we do have a five。Nice。So， now we can play。Game as always。

Then let's try go into the menu and it saves。Again。Okay。😊，Where's that。Okay， now。

Let's try loading the date oh， and we probably zero the power up， so'm going to go to the menu yeah。

So now we have some data， the version is one， so it matches。And now， we。

Let's see the save data version one。Levels， first level is unlocked。 I suppose，18 skies，15。

 This looks perfect。😊，I think。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_369.png)

Well， except for a couple things， which was the the powerout should be。We have like。

 we set power ups。Ourer。I think we had like a reset。All that's do liked。It equals your reset power。

We should call reset power。Whenever we。Well， we do， we start the game。Every we change the game mode。

Yeah。Which is like。Not sure。 I like this structure。That it。Maybe。

 maybe should have like an init menu。Yeah。clean up。Probably。Okay。

Now I don't think we're going to need to make that on another thread。😡。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_371.png)

Because that was super quick。Maybe。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_373.png)

Yeah， that was awesome， so。Maybe we'll do that。When we need to， let's see， yeah。

 I didn't I didn't feel anything， but when we changed。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_375.png)

I should when you start game。SheSe the score to zero， we want to be saying the score to zero。

Only when I update the high score。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_377.png)

Well， I should probably have changed this scar to zero。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_379.png)

When I。Okay， now I did。Oh， because I went back。No。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_381.png)

Not sure what happened。To keep an eye on that。But anyways。In the menu。

That's also show the high scores。呃。If it's not locked。Well。

 we should only save the high score if we succeed exceed the level， not if we quit the level。

That makes more sense， right？Okay， draw number， let's just if it's locked if it's not locked。Yeah。

 let's just draw the high score。Going to like， maybe the size。And we'm going to do。Save data levels。

 I don't。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_383.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_384.png)

Nice。But。包。I do like this color equals。1，2，3。Like colored。Color。好了。O。And let's also do likes。主超。To0。

 and let's say，10。Bye。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_386.png)

Okay。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_388.png)

Well， she really be like。Is do。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_390.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_391.png)

We shouldn't make it like a drawn number。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_393.png)

Make like a draw number from the center。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_395.png)

Maybe we should just add lid zeros。Yeah， but the one's not standard。Yeah， let's not worry about that。

But let's not save the high score if we quit the game like。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_397.png)

Maybe update Ecar。 if we， if we go。Yeah。If we go。From the games。

 the menu shouldn't actually update high score。And let's also see other case， like update。

 high score。Test for condition is okay， lose a life I're not going to do that。いいあ？Yeah， so。

Should only try to update。Let me test for the wind condition， that looks correct。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_399.png)

Yeah， okay。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_401.png)

So。I think our sadism is done。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_403.png)

So start out with。This guy。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_405.png)

Zero because we haven't finished it。 so I'd say we're going to play a little bit。Then。Succeed。

Let's say we succeeded。 Let's say，2031。 Okay， so we're now in the next level。

 if you go back to the menu，34。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_407.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_408.png)

Oh， because we have this core。Yeah， this is kind of artificial because。

AndThis is just a heck to complete the level without actually being the level。

I's not worry about that。So 34 now see， it's still seven。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_410.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_411.png)

Yeah， because I'm not resetting the score。Only when I tried to update high far。

 so this is the wind condition。I actually do like in a lot of cases。InIn the wind condition。

I'm gonna play like victory。And in fact， now that we're not using that anywhere else。No。

 that's be a function。But。Okay， so whenever you win， whenever we lose， so game over。

Also going to set the score to 0。And whenever we go back to the menu。So。Here， we set this part to。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_413.png)

Okay。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_415.png)

Think that'll be better。 Let's see。Oh， should also see if the lights are。 So6 went back。Yeah。

 perfect， because the start game， start game， yeah。So let's see。K。Let's just play for a bit。Nice。啊。

Okay。Let's see47，9。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_417.png)

48 something。Let's go back。嗯。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_419.png)

Okay， so now we're not saving。Like Rachel said， right， the art。Of。You know。

Having something in work then not work。If you succeed。

 you go back to this guy maybe should go back to the menu。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_421.png)

But we're not saving for some reason。啊。い update？I square。Like if the next one is locked。

 we unlock them and then said that we should save。If we are the last one。

We're going to set the game mode。To the menu， or maybe like a。Like， I don' know。Special screen。

Not 100% sure。啊。But yeah， why didn't we save the high score？



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_423.png)

I know let's put a break point on the maybe。Date。Square。See。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_425.png)

Score is， oh， because we are 0 that。Oh went。When we lose a life or in avi period。At the very end。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_427.png)

Let's see if we can like， get a few points up。And if you do manage to get this guy behind the other one。

It's really awesome， because。The movement will make it be like， but it's kind of hard。Let's see。

 Yeah， maybe I'm going to move him down even a bit。Okay， 13。是。14， yeah。But if we just leave。

 we don't get an update。7even。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_429.png)

3。😊，0。Okay， perfect now for some reason we stopped。Oh， it's going to be all tapped no。

When do we lose our cursor thing？

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_431.png)

Yeah， it's going to be all tab。嗯。😊，Do that's。That's。That's。

It kind of a robustness thing that's kind of hard to do like。There are so many cases， cursor。はい。Set。

Csor。You' do that。On the哎。State and。I think we also， yeah， we are。To clear the input。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_433.png)

ok。See。And if you really love our users， which we don't， I'm kidding。

We should save like the old mouse peak。So that when we all tap。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_435.png)

We changed that back。Let miss事。Yeah。If we are unlocking the mouse。I'm going to set cursor。Pa。

To the opposition。So if he's like all taing all the time， we don't change his mouth。嗯。Yeah， we。

Its where we are unlucky。We unlock the mouse。 then we said to like。Win 32。Safe mouse。对。😊，S let's do。

Centers。Yeah， whenever we set the position。Like。Give。Which are these。Three cases。First of all。

 I'm not to get the cur。Yeah。うん。I don't think we're going to worry about e now。

 I going put that as a to do。Just， because this is kind of。This is the kind of stuff that。It's。

Ca a of corn cases。I don't。What I just created。And I don't want to deal with those corner cases now。

I want to add some audio， but I want to set the size to zoo。Send your screen。

Just make sure we delete it。And we did， Okay， so we got to a perfect point。

 we finished our engine improvements， the fire writing system。

Save the unlocked levels in high scores。That's it。I'm just going to note in a push engine pass。

Let's do， like， maybe return。The player mouse cursor to。It was。4。We said it。来首。Oh yeah。

 we did in the United States system。Now。Nice， yeah。 It was nice。

 Our engine is pretty much done in terms of features。 Actually， it is done in terms of features。😊。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_437.png)

oh， not exactly， because when we do the game modes。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_439.png)

I think I may want to do rotated blocks。And， but we added rotated。Rining already， so that is done。

But we don't have rotated collision。So we're probably going to spend some time doing that。

Whenever we want to do the game mode then requires rotated blocks。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_441.png)

But that'll certainly not be now。 So the engine， I'd say the engine is like 9% but。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_443.png)

The most of our stuff is that。So let's do。All stuff that we want to do。

 we want to implement the music and some effects make the volume have a target volume。

So you can fade things in and out。Easily， make the player of the listener thatll be pretty cool。

 I think， and make the Async ODG reader。Let's see we are one hour and 46 minutes and let's try to do that today。

I'm feeling excited what you guys think about。I have to the whole thing。

 then we can go back and just start making like Ui stuff。Better levels。Marfield。Cleanup， well。

 kind of did the cleanup almost。It wasn't too nice， but at least sort of cleanup。UmPolish pass。

That sounds perfect， what do you guys think let's do the audio now。But before I do the audio。

Let's do like what one。Okay， I makega for more。 Well， I'm gonna get some water。

 Maybe she got some water， too， but I don't know if you've been talking as much as I have。

 But when I go back in one minute。😊，One minute。We'll do the idea stuff， so prepare your headphones。😡。

Okay， I'll be back in a minute。Okay， I'm back。Now let's implement music and sound effects。

First of all， let me put my earphones here。And I'm going to turn audio on for you guys as well。

So let's see what we have for audio right now。We are playing the。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_445.png)

The other gate was framework， dude， we're not using any framework。

We are making a game from scratch if you go to the YouTube channel， which is YouTube。com sd Zan。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_447.png)

You can see the whole process， we started out with a blank file and just our courage。

And then start doing like the Windows stuff， the graphics stuff with no libraries。And all the way。

 the gameplay， then we did like rendering， particle systems and audio when threading and bitmps。

And all sorts of crazy stuff。 it's pretty cool， and we'll drop that on the chat so you can take a look later on。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_449.png)

Let me show you the state of the game now， the game， well， we just even made it a main menu。

🎼Which is pretty cool。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_451.png)

And right now。The game， well， it's kind of a breakout kind of game。

 so it starts out as a pretty much a breakout breakout clone。And this music that you can hear。

That I was looking at if you guys could hear。That music is my other games music so today I' going implement the actual music for the game and then we can like finish the game and go to the other levels like to like breakout space invaders so that's the kind of the cool idea of the games that you play。

Other like arcade games as B Council。That's the idea and we did like space invaders。

 which was the more interesting one and a punk， let's do pun， which still has a lot of work to do。

But starting to get cool the thing about palm。Is that you can't just do it like this。

You can't just stand right。🎼没有。Even if I I couldn't because he keeps dropping you know。

P downs and want to wipe those。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_453.png)

🎼So。That's the game we have now and it was all from scratch and I think the main going to be pretty cool how long have I been using C？

See specifically。你边。Pretty much exactly one year。I have been using C++ for a little bit longer。

 but not too long though。Why are you making a game me CNL C++？

This is a simple enough game that we don't need the S plus features， and I think C is a very。

 I know is a more beautiful language for the lack of a better word。😊。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_455.png)

It's way better because it's easier to see the code saying it pretty easily。

We cant know exactly what's going on。 There's no like crazy features that we need to overs the compiler doing then crazy error messages。

 no complication like that， pretty simple，'s most simple language and simple and powerful Yeah。

 so we need to be both And I think sees both So I think C is more fun And since the goal of this game is just to have fun and make games and not worry about too much。

😊，I just going to use for the next project， if I decide to make a little bit bigger and。Yeah。

 maybe more complicated use like open GL stuff Raing and our stuff。

 maybe I'll do C++ because that's the interface standard and it's also nice to be really good at that。

I started learning see this week， this feels great but I have no idea what to do and there's like no C tutorials on YouTube do there are a couple C tutorials。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_457.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_458.png)

I mean， a pretty good one。 Well， it's technically Cus plus。

 but it's a very sea like Cus plus if you go to handmade hero。😊。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_460.png)

That's a great source of for learning how to do engine development。

 and he goes like all the way to 3D and lighting and all of those crazy stuff。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_462.png)

呃。His game is like really more advanced than mine， and he goes all the way through optimizations that he has an intro to C course。

And you go to handmhero。org and go to the intro to see here。You can watch those it's only five days。

So it's just an introduction， but it's really cool and itll give you all the tools that you need be kind of will be a lot for the beginning。

 you have to practice that， but my series， I think that'll be useful if you want to learn how to make games and see because you go from the very first episode which is usually our comeslash Dan day Dan。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_464.png)

You can see all the code that we wrote and how we set the search there to make a game。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_466.png)

And you can download the source code to follow along， too。 So if you go to Danz then dot H doto。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_468.png)

You can download the source code for each of the apps separately。

 so if you do like the first day and then you download then play around with it。

 maybe add a little bit of gameplay yourself， do all sorts of stuff all the way to where we are now。

Like I learned see like six years ago， it was a great introduction to understanding the fundamentals of programming。

 switched of Python node GS though when I even。诶。Yeah， so Haer linked a YouTube video。

 let me check out。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_470.png)

He says was a great eat to see。Yeah， oh， Harvard， have functionality。

Print F still he uses the scratch as an example， fair enough。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_472.png)

はは。😊，Yeah， see， that's the problem。 The fundamentals。

 there are a lot of stuff on Google on YouTube about the fundamentals of programming of C of everything。

😊，But intermediate and advanced stuff you really don't see that's one of the reasons I'm doing this series。

 which is kind of an intermediate level。It's not like advanced。

 but it's not like super beginning either， so I think this feels a pretty cool gap。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_474.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_475.png)

Handmade heroes a little bit more advanced。 Like if could go to the full one to the full episodes。

 That's a little bit more advanced than my series。 But I really want to do like a whole from beginning to advanced series later on because there's already leg the way I learned to minute stuff is doing challenges projects and psycho。

 Yeah， you do have to do。😊。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_477.png)

Projects yourself well， even if you are doing like the beginning or the advanced stuff。

 you do have to to do projects yourself， but it also helps， you know。

 to see people doing more advanced kind stuff and not just。

very basics like pref kind of stuff and then switch to like a fullwork project you know that's or like using a library that does all sorts of great stuff and you don't understand what the library does that's why this game from scratch I mean in the other games we've got to when maybe we're going to use libraries。

Well have an understanding of what the game does like the whole thing。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_479.png)

Okay， so yeah， those are a couple of nice features， so as you do audio。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_481.png)

First thing， let's change the music to our music， which is breakout Ma。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_483.png)

Do wait。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_485.png)

🎼哼。I really like the kind ofese， I don't know if you guys enjoyed that。

 I did this music and'm kind of learning。How to do music still So maybe you guys are going to feel like this is a pretty bad music and maybe you can guys say why you think so and then I can improve later on。

But I really liked it。It way turned out。🎼Yeah。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_487.png)

Okay， nice。 However， I did2。Pieces of is， I mean， it's the same one。

 but also exported a menu version。Which doesn't have as so many instruments。

And the idea is to have them play in the menu， so we're going to have to expand our audio system to do that far stuff。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_489.png)

Right now， if we do like main and menu。And I do like gameplay。Music， and we do menu。休息。😊。

He calls this guy， if you do like this。And we do like gameplay music。就。Er volume equals0。

 We should have like the audience。M来次。Okay。😊，Play music。What was the skin called， okay？Nice。Yeah。

 breakout。Yeah，抓ing呃。Okay， yeah， this actually should be。In a play sound。So going to play the music。

And I do like。搂这。Gameplay music and loaded menu music。And this would be。They gameplay music。

And this will be the main。Then we can turn the gameplay music volume。这几个。

Yeah I'm learning C tos being to C possibly C sharp， I probably won't touch again。

 Yeah C I think is a great language to learn because it's really not that complicated。

Because all those other languages have tons and tons of features and you really don't want to spend your time learning the language in the beginning。

 you should really learn how to program first。😊，And then you can focus on the language。

So I really like it as a way to introduction yeah， it likes the best language to learn how to program if you do like a simple high level language though。

 you kind of miss some kind of important things。That you kind of don't get when you are programming high level and it's hard to go back and learn。

 easier if you start learning that， I think。Go to gameplay music。您。😊，嗯。But I know。

 I also thought I wouldn't like see again， but I fell in love with it pretty much。

So this guy is actually the little bit sound。He convert from loaded sound to loaded。That's a pointer。

But that's。Okay， that should be a plain sound。Pointer as well。But if from learning seeingness。

 it was pleasure or unlearning。All this stuff。Well， what you mean。If you learning E C and then++。

 C++， you just have to learn more stuff。Like objects oriented programming。And I don't know。

 there's a template。Like typecast confusion。I'm not sure you're going to use like static cast。

Like this。For some cases， they're going to learn new casts。so。Yeah。😊。

And there are so few elements in see programmers。Tend to write global functions that's true Yeah so you yeah you have a nice point there the style of your program will have to change based on the new feature that you get like namespaces and objects。

 things like that the style will have to change probably。バラ。But that's the thing。

 the language shouldn't dictate the style。Well。The language didn't dictate the programmer。I think。

So as a program you should know what the computer the corporation dictate right so as a program you should learn what the computer is doing that see that what's。

Cs good for， I think。And then when you go， C++ dictate like the flow of the program and things like that。

They don't know what their computer is doing， even if you're doing like higher level features。

You you have to reorganize that。I think it's worth and I don't think you're going to， I don't know。

Unlearn， I think you learn new styles， and you can also program C++ like C if you want。Two， yeah。

Though people don't recommend that。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_491.png)

So this is the menu music。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_493.png)

And we want to change that when we go to the gameplay right， so when we switch to the gameplay mode。

 which is like here。Yeah， we're gonna do。嗯。メニュー musicー。Volume equals 0。And then we're going to do。

Ginly。Your6 volume， equals one。Many music。Yeah， we all let's do。Yeah let's这。I mean。

 it's never bad to learn new stuff， I just think that we're going to learn when you're seeing and when you're supposed to it's better just strengthen for two years。

Yeah， well， if you know you really want to do C++， like get a job and work in C++。

 then I I will like agree with you。But just want to learn programming。Like。

How to be a good programmer。I think starting out with a simpler language is better。 you。

 it's easier to understand C+ like way easier。 C++ is crazy。

 man Once you get like the no features like mope semantics。And copy constructs andwls。

lots of crazy things things there that have to think so much when they're justtyping code that。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_495.png)

I don't know。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_497.png)

哼。🎼I'm a little bit biased， I don't really like super。🎼Okay， let's see if we get gameplay news。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_499.png)

But I don't know if you guys could to hear that。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_501.png)

It's not synced perfectly。🎼Well。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_503.png)

It was kind of perfect， but it's not perfectly saint。And the reason is。Since we are。A think。Right。

This is where we increment the playing sound position here， this not 100% reliable。

When't you make the use again， I use Reaper。And I used to use Ableton Live。

But because that was what I got the free version with my equipment。But。I want to try it out Reaper。

 so this was the first one I did in Reaper， and I really liked it。

So this is the problem we can't if we want them synced， we can't add the position separately。

I just starts we can kiss and， well， I don't know about that。う。

So I'm going to possibly save a plank sound here。Its to be think。呃。Saint。Okay， and when I create the。

menunu。Music。I'm going to set its sink sound。And your music。てす。To the gameplay music。

So if we do have a sync sound。This is issue。If we do have a sink sound。Our sound position。

It's going to be our sink south。Sings sound。好。Yeah。Okay。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_505.png)

有一次。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_507.png)

Perfect。Let's go back to the other。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_509.png)

But another thing we want to do， we want to fade。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_511.png)

A slide fade， but we want to fade。So instead of just setting the volume like this， straight up。

 setting the volume20 or two1， I'm going to do a target volume system。And the way it works。

Is that I'll have a volume an a target volume？And whenever I get the volume here， oh。

Set target volume to one。Ass the default value。But here。不好意。In the end here。

 I'm going to set the sound。抓紧。To be the sound target volume。Maybe I'm going to do that earlier。

 right。Oh， but this。I'm going to do a prepass。Because this is actually being run。Yeah。

This is actually for every sample， so I'm going to pre pass like this， so I'm going to do the sound。

vololume。It's going to be a move towards。I'm going move the sound volume。Towards the sound。差给刷紧。

At the speed of let's AT。Times。嗯。3。Dude。So， okay。In this case。

I don't need to do this because they'll be there done just once per frame the sample needs to be done for every sample。

 this is for every sample， okay？Now。If there's no， if there's no。There's no volume。

I could actually skip this whole thing。And I'm not going to skip。if there is volume。

 but I'm not going to keep the position changing。Actually， this is a little bit wrong as well。

Ca this has to be done every friend， Iivory。Every。Because this is not reliable， so well。Yeah。

 I think it'll be reliable enough。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_513.png)

SSTS第。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_515.png)

Oh now at the beginning， we have to set both the volume。And the chart flood。

Maybe we can do a hyper function to do this。That's。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_517.png)

Let's go back now。And change them back whenever I go to the menu， so menu。I should probably。

Do we call like。宣疑区。楼。Yeah， that'll be better。So， current。Going to gain。

Okay I'm gonna switch on the game mode。Case we are。Now。更优秀。电 mode。In case you are in the menu。

Now I'm going to do this。Actually， the other way around。Okay。And I'm also going to。Said the。say。

This guy。Nice， so this will be。Change game mode。C。😊，It's nice writing， know。

 the first version of the code quickly， writing a comment like cleanup and then actually do the cleanup。

That's really cool。So that's the menu case we are a going to the gameplay。

C were going to the gameplay。呃。是。确定这个。Start the game。てうこです。Cha mode。Now in the game。

 we're also going back to the menu。TheLe have will retestable reconditioned。

You're going to go back to the menu of change。Be load the menu and maybe you're going to a special screen later on。

And this one I'm just going to forward declare， I think。Or， you know what。Yeah，那。Here。New game mode。

And I press well。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_519.png)

没声。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_521.png)

g let' see。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_523.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_524.png)

That is really cool。 Really， really， really， really cool。

 I don't think you're gonna do more music for the other levels。

 I'm thinking about 10 levels or something。 And1， I don't know it gets boring with。😊。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_526.png)

，Okay。If we went to music， we did now sound effects。think if I have a title decline already did that。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_528.png)

Sign effects are going to be a little bit more complicated because there is a bunch of them。Right。So。

Yeah， just for reference， you just。This kind of a reference stuff。S fix。That I created。诶 ok。

And so these are the sound effects that we want to add。We have bricks。And we have hits。

That's our the hits。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_530.png)

And it's going to be， pretty bad code at first， but going hang on。

 we're going to do a little bit better later on， but。So loaded sound， let's do a loaded sound。H。呃。🤢。

It sell。Bner have 16 hit sounds。And we added a bit shifting to our engine。

 but the bit shifting also changes the length of the volume and I' I didn't want these hits to be really quick。

But I wanted them to change like pitch a lot， so that's why I'm doing different sounds。But well。老喂。

Then I'm going to do them by hand。啊。It sounds equals loadly。Data。Sound effects。Okay。我。Just对。听。Okay。

13。我听啊。And 15。Nice， now let's do this。Okay。是。Now whenever we， let's go to the levels。

 whenever we destroy block。Block the strike。And if you have neighbors。

 I don't want to play the sound for everyone， including the neighbors because that's too chaotic。So。

I say if we are going to destroy the neighbors。Maybebe。I'm going to。Play sound。

And let's do hit sounds。个 random。En range。0。看一下。😊，It's going to be pretty。Pretty long call， but。Open。

 close。 Open， open， open。Play sound。待会 we道是 also。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_532.png)

Let's see if you get some science。🎼オッケー。I at。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_534.png)

IsBecause we just added three sounds。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_536.png)

Three play sounds。And we want to change that because that was just for testing， really。

Let's make it like 32 sounds。And we weren't sure how to do this thing。

 like if we wanted to play moretown。And we thought about just ignoring and asserting what I think I'm going to do。

Yes。I'm going to set the next place sound。I can't do it like zero because they'll overwride the music。

And I could hard code like three， which is like the music plus the movement and stuff。

But I'm going to do like a。Like a plane。Sound。I'd say。Imutable sounds。Sound count。ok然后。

Uable sound count。And。Yeah， whenever we play the initial sounds。game？Here。I'm going do， like。

Imutable some count。The next。So whenever we go all the way to the end of the array。

 let have a immutable sound count or the。next plain sound back to the immable sound count。

And I think that's just。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_538.png)

怎样的。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_540.png)

Well， we've got a wrong sound there。For some reason。Oh， because the random is inclusive。

This random is inclusive I should do like my。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_542.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_543.png)

Oh， and actually this is wrong。Why did I write that， I don't want the random sounds。

I will want random sounds for like the bricks。But for this guy， I want to actually increment。不是か。

I' going to do like next， it's sound。To play。Yeah。We're going to start up with zero。And。

And that's also do like。Last。Its south played。So， if the current time。Mine is the last time。

 Let's says like。Ha a second。Yeah， I'm going to increment。The next hit tap。Soundable。It's not。

And we're going to set it back to。So the idea is if you get like crazy。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_545.png)

And it breakout kind of sounds。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_547.png)

🎼はいでしジ。But the more we get。🎼Hir a bit should be。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_549.png)

Yeah， it's not working。Oh。No， yeah， we already use it。Yeah， we should also set this guy。Okay。Yeah。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_551.png)

我要。I think the collision was。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_553.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_554.png)

W should also be like。Do optimize builds。This kind of stuff。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_556.png)

Especially because。Heaven。Profile or game yet。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_558.png)

I kind of likes。あ。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_560.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_561.png)

O。And we are going， like。Overboard with that。Like。Next sound play is less。Then the array counts。Of。

It sounds minus1。Veryrry。Surely do you like。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_563.png)

Itra comic， they come to be a bit of bit too。🎼I really like this each time。🎼啊。Got a comment。なら。

I this is awesome already。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_565.png)

And just to check out。What we're doing。Let's print the oneande。Just's because it's nice to know。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_567.png)

いや。I think that was awesome。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_569.png)

Yeah， okay。Awesome， now let's try playing the brick sounds。 You and do like， brick sounds。😊。

And these ones I can do like grand。And I'm going also want to remove。At least。

Let's see how many bricks sounds we have five bricks。Yeah。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_571.png)

啊。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_573.png)

Header was no pointer。Can not call brick。Oh yeah， we don't have。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_575.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_576.png)

Yeah， if that wasn't extremely awesome。I don't know what is。 That was really cool。

 Let's try them both at the same time。 That's， I'm not sure if one's going to be too much for the other one。

 Let's just remove the music。😊。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_578.png)

For now， let's see。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_580.png)

🎼What game are making， we are making a breakout kind of game so。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_582.png)

🎼Let's start with level zero。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_584.png)

Well， just small comment。 We failed at making these work。Because let's say the game。

 they also zero those them。Well， that's not zero of the music， Let's keep the music playing。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_586.png)

So we' start out with a breakout game。🎼Yeah。🎼Maybe a bit too loud。🎼じゃ。But。

started to making more interesting stuff like breakout spacing pages。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_588.png)

🎼ああ。Okay， so that's the kind of game we're making。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_590.png)

Dude， that was， that was， I almost， I almost reached that。That force field there， Okay。

 so in the levels when we do like play sound for the bricks。I do like brick。Just call that。So。Sound。

Thats target volume。It goes half and the light。We should have like a set volume function。Yeah。

 let's do like it。Sat volume。Because then it' will set both the target and the。

And we can also do that on the play。Sound。This guy？Do set。不。特别的 audio you。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_592.png)

Okay。Another school of thanks and the thing is。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_594.png)

We are building this game from scratch， so started out with a blank file and no libraries whatsoever。

And if you come here to the YouTube page， which is YouTubebe。 on/dZ Dan。

 you can watch the whole process， everything was live streamed。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_596.png)

And this episode 13。And we are， we are， I don't know， I'd say halfway done thinking game。

 maybe a little bit more even。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_598.png)

And you can also download the source code in HIO for each day。

 you can download the game and the source code for free， dzd。h。o。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_600.png)

Yeah。😊，I think we're getting to cool places。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_602.png)

I see how this sounds。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_604.png)

Still too much。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_606.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_607.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_608.png)

Well， I think I'm setting the wrong finger sound。Yeah， I am saying the wrong thing。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_610.png)

Okay， this guy should be decide。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_612.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_613.png)

可以。I am liking that。Quite a lot， actually。Let's see you have a ton more sounds。

 but I think I'm going to add the difficult one now。Could permission managed to add this one？

Then'll be good to go， I think。Just just to test， I'm going to turn the plain sounds maximum。

 let's say to three。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_615.png)

And let's see if we don't crash and we don't capture the music。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_617.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_618.png)

See this is perfect， but if we don't hear the blocks， which is what the expected。Okay， now。嗯。

The tricky sound that we want to add now is the play movement sound we want。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_620.png)

They played to make sounds when because we added like animation for like squash and stretching and。

🎼これルベラバ。Follow through as well。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_622.png)

You' want to do that with a sound We try doing that quickly。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_624.png)

Previously， and that was tricky， we even't got it tour 100%。But today we have to make it work。

 so that's work to make it work。Let's see we have， let's remove the music。Let's go back to the game。

 see， that's why I don't like screen files I always get them wrong。Okay。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_626.png)

I'm also going to set。The man music。This is zero， so we don't hear any news。

And we should make a player movement out。 We already sketched that， so we added this thing。

 so we got guys are going to hear the sine wave。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_628.png)

Okay， that's a sine wave the idea is that soundal wave is going to change volume and pitch whenever the player moves。

That's going to be。A great effect， I added that effect on the previous game。

But I don't know if you guys will be able to hear that and try that。I'm trying to show you that。🎼。

That has a kind of sound。🎼。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_630.png)

Yeah， that's what we're trying to do but。And this is a pretty big butt， it's complicated because。

Palm， the other game was controlled the keyboard， so we had an acceleration that was pretty smooth。

For this game， since we use their mouse， it's all over the place。In one frame， the Delta is like。

50 and the other one is like negative 10。And if you play around with that too much in terms of the pitch and the volume。

We may have weird the results， so it' was going to have to take it easy。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_632.png)

Let's do like the player。Yeah， this point， let's do the player audio。 So we have player movement。

Sound here。Let's try， First of all， Let's try changing。The volume。 So we're gonna do。

And这个 target volume。And just to show with the problem that we had previously， we can't set， well。

 we wanted to set that to the。The player target D。礼皮。I said that to the absolute have。

Let's say times a small number， that's what we wanted to do。We can't do that。就你。Can do that directly。

Well， which term does an evaluable function？We can't do that。Because this guy's all over the place。

 so I'm going to print F32 we kind of started doing that previously。

 but let's take it slowly in this time I think。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_634.png)

7。Okay。Because of the target volume， that sounds perfect already。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_636.png)

I mean， I think I'm going to speed up a little bit of dessert。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_638.png)

我了解。Like we have the DT。Times 3。 Well， can do that later。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_640.png)

But this is perfect。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_642.png)

Well， let's do that。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_644.png)

Here in the audio。Instead of just hard code3， I'm going to do like sound。I know fading。Speed。1。

And whenever I start。Set。C。Speed to three。But this guy。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_646.png)

When I set the。Ba。S， let's say， two twice as。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_648.png)

And I should also at beginning。Set the set volume。This guy to zero。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_650.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_651.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_652.png)

That's great。 But I think this guy's a bit too much。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_654.png)

I it there。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_656.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_657.png)

Yeah， kind of like that。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_659.png)

Let's make up。So the volume is perfect。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_661.png)

But let's also change the pitch。 We could hard code the pitch。WeWe call that bit multiplier think。

Big hard code that page something like。ってい。Or fly too light。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_663.png)

Yeah。嗯。🎼，He's already a lot better。But if you guys。Listen to that carefully。Well。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_665.png)

You guys don't see problems， right？Because our pitch。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_667.png)

あ。We just hacked that pretty much quickly。Just to get something going on。And。Yeah。

 we don't actually blame the guys， so。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_669.png)

I see if you're trying to play like this sound。And I'd say we played this one。

Now we want to play like this one。So off like getting this guy。

 which we can pretty easily get the lub。We get either this or this。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_671.png)

And then maybe you can get like this one again。 So it's kind of problematic。

 We have to do like a proper。Blamding of of guys here。So instead of doing the sample like this。

Let's do it like。It's still one out of time， so。That's first， just get the sample。

But let's also we did the same thing， where did we do that with our rectangles。

 when calculate the fraction part， yeah， we did the same thing。

Which is going to be the sound position。Minus。The sample。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_673.png)

This now should be how much。W it like， oh， I closed the paint。No I did well， yeah。

 so it should be like how much we couldn't go because we were clam。Of the previous guy。

Let's let's say this guy's sample 10， this guys sample 11。And we were， like，10。5。

Yeah have the next guy， so you have to blend this guy。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_675.png)

This guy with the next one。你先。So we're going to get two samples。Say left。Let's sample  one。

 and let's sample 2。At simple one， it's going to be this guy。Left simple two is going to be this guy。

Plus， the channel count thing my。M个 one。In a case it's a stereo or mono plus one。

So it's like ifs two sound two channels， we're going to skip one， then add one， if it's one。

 we're going to skip nothing， then add one。So these are the two samples。

The final sample guy is just going to be alert between these guys。Theer between the left sample one。

With a f as a value and less sample。K。😊，And。I think they'll be all we need。We have to make sure。

 though。Havere we rap。Like technically。If the sample is like the very last sample。

We should get the first one。Yeah， I think I'm going to do that， Let's call that。Next。今年后。But。

Next sample。Clear。Then sound。Sounds so。Sample count。て个。ok。😊，Yeah， that was correct。

Now I'm going to ignore her。The right channel for now。Just we going to focus on making work。

 I'm going to turn the volume way down for you guys as well as from you just because。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_677.png)

You never know。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_679.png)

That sounded perfect， I think。Let's try doing that for the right channel。The right channel。

 this one's going to be。This guy。Right。I've said， yeah。And then this one is going to be。ASample。Plus。

2。Outve it by the channel account。Same thing。Oh， it' also， yeah。

 we are also playing by the sound volume。We can just multiply this guy by the sound volume。

It's like one last thing to do。Yan。And then。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_681.png)

Then well， we're back to normal thing， let's see。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_683.png)

Okay， I kind of like that I think the volume's a bit too much。し？Let's do 35。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_685.png)

But now let's start changing the page based on this guy as well。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_687.png)

And。I'll comic this sound the one for now just can。And we should actually set it to。

So you can focus specifically on the pitch。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_689.png)

Now let's play around with that， so the basic idea is the same thing。Same thing。

But since we're not blending this guy who just said it， it may sound a bit weird。

SoI'm going to turn my volume a bit down in the your as well。Just， so we see what's going on。

And actually， the bitch。It should start like 0。5 plus this guy。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_691.png)

And it shouldn't go too high， I think。And we should really cap these guys anyway ways。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_693.png)

That was really unpleasant。Start out way too basic。And it ended up way too。我要。I don't know。

Maybe that was just wrong。Yeah， let's comment this guy。And let's see the result of this guy。

 Let's see I。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_695.png)

got。This should be like 0。5。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_697.png)

Yeah， well it's just。Moving a little bit over5， and we' got a very weird sound out of that。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_699.png)

Let me try to hear that but I'm turning guys even on a little bit down。That。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_701.png)

Yeah， this is pretty wrong， I think。Even though we're doing the same thing。Oh， that that's 0。5。

 plus's write do one plus。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_703.png)

えなら。Playerable that sound。开奇。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_705.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_706.png)

嗯。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_708.png)

I getting a weird sound in move。Maybe our alerts not 100%。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_710.png)

Yeah。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_712.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_713.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_714.png)

Yeah， you know， I think the problem well let's just take a print screen out of that。

Maybe the problem is because we are all over the place or the lives 100%。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_716.png)

Yeah， I see this thing right here。That could probably cause weird behaviors like not 1。0。

 I don't know where。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_718.png)

So what I think I'm going to do。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_720.png)

Isn't going to create the same thing like of a。Like moving towards kind of thing so。Yeah。一。Let' see。

😊，I want to， I want this guy to be。Move toward。Let's see。Blay movement sound。This guy。

 and let's move like。就努的。Lalaying sound to have 32。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_722.png)

Multipliier。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_724.png)

It is better， but the lup is wrong， pretty sure the lup is wrong。Butら。Yeah， that was way better。

Let let me just check。Oh， we're not using the next sample。This should be like。Plus one。And then。

 yeah。You know， let me try to buggy that。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_726.png)

Let's go to audio dot see。 Let's see。So we want to play。Oh yeah， now we should turn off be optimized。

Slack。Okay， let's。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_728.png)

Sample is zero， fraction is zero。So。Next sample is two that looks correct。Yeah， but this is not。

This is just the next thing。No， this is correct。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_730.png)

Thats correct。But let's play around the sound。To we got weird behavior， let's see。Seposition。

Is this guy， so I want to blend from 2197。With 2199。And the ven amount is going to be pretty small。

Yeah。So this is the first one， this is the second one。And the result is this guy， that looks perfect。

嗯。😊，I don't know。And they wouldnt do the。But it's pretty wrong， the bitch changing。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_732.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_733.png)

We have a very thin sound。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_735.png)

Blaine alongside the other one。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_737.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_738.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_739.png)

If I remove the nerveb。嚟。That go away。No， that doesn't。That's weird。嗯。I'm starting to think。This is是。

这谢是。Left sample one。Fray。That's simple two。This guy times the volume。Then we do like the。

Left and right stuff。嗯。Yeah， we。Okay， this is。This is the problem。

We were offsetting by the channel count。And now we are not。So I'm going to do this。

An integer like this。But I have to do with this after the frerac。Yeah。Okay。Nice one。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_741.png)

Okay， let's see。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_743.png)

Perfect。Now。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_745.png)

Let's do a little bit more。This guy。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_747.png)

If you do it， its got little faster， really。4。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_749.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_750.png)

Maybe even。Maybe you can start。A bit basesier。一个嚟。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_752.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_753.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_754.png)

There's a small problem。If move for a short period， really fast。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_756.png)

I don't get as high a volume。Because this guy is just based on the time。

We're going to do something like。Plus。That's called this。桌子。Target。I don't know times this guy。

So you also move faster if we are and working faster。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_758.png)

But no， there's a difference。Yeah。Well。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_760.png)

Yeah。This is the basic idea of it。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_762.png)

much去。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_764.png)

This sounds not perfect yet。But。Maybe this guy can be a little。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_766.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_767.png)

你别人。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_769.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_770.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_771.png)

Yeah。Nice， it going like way too much now。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_773.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_774.png)

すげ 그리고。Maybe even。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_776.png)

Now it's starting to get some。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_778.png)

Oh。Perfect， now it's not 100% yet。Like if we move slowly， it is。But if we move fast？



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_780.png)

I've got a bit of a。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_782.png)

15， so we are decrementing， decrementing， decrementing， decrementing。Then we move all the way to 5。

12。Go up。Up， down and up and up。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_784.png)

And not not and。downown。Yeah。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_786.png)

Maybe I'm going to make this guy like。A lot slower and again I'm going to clamp this guy as well。

We're going to clamp for 0。7。Let's try 10。嗯。Conversion from float to integer。Oh， clamp that。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_788.png)

Okay。ううん。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_790.png)

Tends too much I think。Let's get this guyd。8ight。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_792.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_793.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_794.png)

Yeah， it's definitely way better。But I don't think it's 100% yet， let's try doing that。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_796.png)

That's you just that。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_798.png)

Let's do a move towards pretty slow。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_800.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_801.png)

Oh。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_803.png)

Any think。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_805.png)

Yeah。When we change this guy。Not getting the most clean sound ever。But maybe。

 maybe the way we're doing， we just won't get the best sound。So。Speed multiplly。

We're changing the position。A position is in samples。Yeah。Let's see how it sounds together。With the？

发样。Because we're pretty close， I think。And council。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_807.png)

行。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_809.png)

This is exactly what we want。But it sounds not clear。I mean。If we do like 01， let's see if that。

Would you like points？近い？

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_811.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_812.png)

Still're not working。 Let's go back。The non lub version。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_814.png)

Yes。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_816.png)

It's way worse。Let me just check out if this is still correct。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_818.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_819.png)

Let's see if the position is this guy， the sample。The guy。And the fraction is this。Okay。

 but the sample is not discussed actually twice。21。6。22。The next sample。21， 6， 24。Correct。And yeah。

 again I'm going to get the samples。Minus 21， 44。That's a huge jump。I don't know if I like that。

And then the right one。I'm assuming it will be 2121，620。3。Yeah。And then。25， okay。Yeah。

 and I's see these values。M- 2143。And 2471， either we got a huge jump or either that's wrong。Because。

I don't know。I don't know if I like those values。Let's see， like。Poin at this guy。I see。

 like eight of them。嗯。I think this is correct， though。Yeah。This is correct。And the loveb。

 should really。These should be pretty close。嗯。This is wrong。Okay， oh no。

 it's not wrong because we're multiified by the volume， which is pretty small， I suppose。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_821.png)

嗯。😊，That's weird。 Let's try doing that without the volume。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_823.png)

Let's see。Let's see how wrong is that。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_825.png)

Back to it。うう。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_827.png)

It's still wrong， but it's not as wrong。えすは。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_829.png)

I know it's almost awesome。We were running for that artifact。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_831.png)

Let's just try just for the fun of it， Let's try playing。Look at everything back on。Yeah。

 let's remove this guy。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_833.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_834.png)

It's going to be really cool， man。Turn the volume up for you guys。🎼うい。う。う。い。う。Dude。

 that's really cool。What do guys think？It sounds awesome。🎼I mean。We can still hear。The artifact。

But if you can't take that， it won't be like the end of the game。Still worth adding that in。

I think I'm going to leave that how it is now。Add a couple more sound effects。

And then maybe next time you can fix that。Or not， I'm going to play that with different。

Like with speakers anything like that。🎼Just to see if it sounds。 okay or not。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_836.png)

うんうん。嗯。🎼No。And in the menu you can hear that pretty clear， the gameplay you can't。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_838.png)

So。😊，And we're going to put like a huge to do like。Yeah。Let's do。Fix。呃。Player movement。Misy glitch。

But I'm going to keep it like that， let's do a couple more sound effects。Let's see。 We have。

Go here and break out。We have a couple cool ones。Have the force field？



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_840.png)

It's pretty easy to add， I's add that。So we have the player movement sound。Thats that the player。

Force to do like forest food sound。And边 here just downloaded。Force。没有。Okay， can let's do a player。啊。

十？Force。Fielel sound。It play sound。Uload it。Forest food sound。本是能。

But I'm also going to set the volume。To 0。嗯。Poiner。And I'm also going to load the first field。

Forourse。Andな。What is that。Okay， now。In the invincibility， I may just set that。Let's see。

 Do we have the alpha。Yeah。If the offer is less than one。Yeah， I think I'm。

 I think I may just do like。Set volume。Of a force field sound。To the invincibility output。Thank you。

 probably。And I'm also going to remove that other print。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_842.png)

还机。😊。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_844.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_845.png)

🎼白色。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_847.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_848.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_849.png)

Yeah， I don't know why the outfit isn't one。The office。Less。Its more than zero。I remove that。Oh。

 but only if the invincibility tea。It's not greater than zero。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_851.png)

Let me try。🎼来い。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_853.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_854.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_855.png)

🎼W。5，42。🎼嗯。🎼嗯。Okay， the visibilityibility T is negative。In the alpha， well。Yeah。

 I suppose I suggest clamp。Yeah。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_857.png)

I should just clamp it。Good what。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_859.png)

Okay。😊，嗯。🎼嗯。That's very good。You know what？

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_861.png)

I surely do this calmly there the sound and implementation。And I'm getting tired。

So I think I'm going to call that a day now， we've been doing this for like three hours and 20 minutes。

And next time around。We implement all the sound effects， fix the clear noise glitch。

 and possibly doing like the UI start doing the UI stuff。

Pretty prettytty sure you're going to do that。Okay。

 so I'm going to call that a day for today if we did a line of stuff with fixed bugs。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_863.png)

We improve the sound system a lot。We added the menu， which looks awesome， I think。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_865.png)

Res implemented the safe system。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_867.png)

I almost forgot about the safe system， we implemented the safe system to job， yeah。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_869.png)

I think we did today was a great stream。Sound effects do make a lot of things。Yeah。It's really cool。

And those bushes。Sounds really awesome， I mean， if you do get a bit of noise。

 I don't think it's such a problem because I don't know arcade games had noisey sounds anyway。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_871.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_872.png)

う。🎼う。But I definitely think we should take that， Okay， so if you want to watch it gets you miss like。

Some of their live streams， you can watch all of them on YouTube in effect。I have created。

 I have added together the best moments of a。The first two。

 like you can watch the first one highlights and the second highlights as well。

In case you don't understand for like。Two hours and watch the whole thing。

 but it can also like speed it up。And。Yeah， and you get to like the best moments。

 these videos are full of content。 These highlights。 But you can watch the whole stream as well。

 So by watching the whole stream， you'll see the whole process， line code， every decision I took。

 every thing the chat commented and we tried out。 and some of the gameplay things we experimented。

 it didn't like。😊，As well as some of the major successes and major failures that we had along the way。

 so pretty cool。 and you can also download the game。😊。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_874.png)

When each try， you can download every game and the source code。

 every episode and its source code here， and when you click download now。

 you can you're welcome to give me a tip if you want。

 but you can just click no thanks and take me to the download and then you can download it for free。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_876.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_877.png)

谁啊。So thank you guys for watching， I had a lot of fun today we did a lot and this this part of the game where we started。

Getting there a little more。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_879.png)

U interesting looking like adding a menu， adding music， and it's a very simple menu still。

 but just by adding things like that and adding music and sound effects。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_881.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_882.png)

And safe games。You know， it really starts to look like we have a we start looking to see the end of the game and I'm really excited to finish this project。

 I hope you are too。 and so if you are， be sure to follow me on all the normal platforms and next time you can do and maybe a little more progress together。

😊，So thanks for watching and I'll see you next time。



![](img/80ebbaad2eb9948dc69a50a6f8cfb116_884.png)