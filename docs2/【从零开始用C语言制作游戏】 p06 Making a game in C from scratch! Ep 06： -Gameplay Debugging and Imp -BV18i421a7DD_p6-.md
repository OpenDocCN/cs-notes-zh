# 【从零开始用C语言制作游戏】 p06 Making a game in C from scratch! Ep 06： -Gameplay Debugging and Imp -BV18i421a7DD_p6-

Hello everybody， welcome to my new live stream where creating an entire game in C from scratch。

If you don't know what kind of game youre creating。

 you can go to the HIO page and click on the first link。



![](img/fb0e7f46d547648aaa046497e55447ae_1.png)

Here you can download the game executable and the source code from the previous episodes。

And we've been doing it from scratch， so we started out with no lines of code， no libraries。

 no nothing。

![](img/fb0e7f46d547648aaa046497e55447ae_3.png)

And in the YouTube page you can see all the episodes so far。

 so we have five episodes started out with nothing just a platform just starting calling platform layer。

 things from Windows and together as a window to get as the renderer to get the input。

 then we added a little bit of a gameplay， the collision system。

 then starting to refining and that's what we've been doing the past few streams。

 we've been adding more gameplay stuff。

![](img/fb0e7f46d547648aaa046497e55447ae_5.png)

So if you see the game that we are creating。We started out as this breakout clone。Right？And then。

 we added a。Some mechanics， some initial mechanics like R ups that you can。

You can pick up in certain blocks。四。😊，Yeah， I like that。

And we also added this crazy mechanic that we have like special kinds of。😊，啊。

Balls and blocks that each one can all interactteract。We do other kinds of blocks。

And that's a variation on that on the system。And now， last stream。

 we started building the original idea of the game， which was to make it like a。😊。

To start implementing the old arcade games。In the breakout。I know gameplay scenario， let's say。

So yeah， you can do like you play pong in the breakout scenario。And then。

Then we also did space invaders。系。Okay， yeah。That was pretty cool。

implementedple like a system to get the neighbors。You can sometimes destroy more than one guy， see。

But。We've added so much stuff in terms of gameplay and crazy ideas。In the fast few streams。

That we have accumulated a few bugs。Right， as well as a。I don't know。

 like a lack of robustness I should say。 So that's what we're going to do today。

 We're going to solve all the bugs。 see if you go to the。Well， if you see the power down。

 which we also implemented， there are a few of them that actually don't do anything。

Because we couldn't figure out the mouse stuff in the first try。

We're going to fix that today and then。And there was strong block here， so that did something。So。

We also have to finish a couple of the power ups like the comments power up that's not 100% yet。

 and so let's fix the one that throws three balls。Yeah。

 so that's what we're going to do today if we go the to the source code that you can download HIO。



![](img/fb0e7f46d547648aaa046497e55447ae_7.png)

We made a couple of notes for where we left off。Last time。

So we wanted to add like printed number so we could do like score。

 that's that's one thing I think we should start with just so we can get a little bit more of a。

A sense in terms of gameplay。But here are the bugs they want to do。

The commentss stop in the middle of the run。And the weird three bond behavior。actually。

 it even noted when that happened， so we can rewwatch that。And the power downs can finish them。Yeah。

😊，I think that's what we're going to do。Start doing the print numbers。In the render。

 we have draw rack。Draback。What you want to do is a drawn number。It's going to be very。

 very primitive now because if you guys remember we've been doing from scratch in terms of the render and stuff。

And we are going to have bitmps， but not yet， I don't think we should stop working on this game play stuff just to have bitmps。

 we eventually are going to do that when you do the engine improvement pass。

We're going to add audio ready， for its and appss。Yeah， pretty can I do。And but for now。

 all I want to do like is a draw number thing。 So we're going to add make is going be like， yeah。

14年9。Number to draw。And then I can pass like the size。And the color and a pe。So。

I already did that in the other gate， like if you watch。

 if you see and let me just hold this up the crazy。



![](img/fb0e7f46d547648aaa046497e55447ae_9.png)

The crazy png。Which was the 200 plan game on theIO。



![](img/fb0e7f46d547648aaa046497e55447ae_11.png)

If you go。You see that game。You see we got text。As well as。As well as numbers。



![](img/fb0e7f46d547648aaa046497e55447ae_13.png)

🎼But we didn't actually did anything for real， so I mean。

 we didn't implement a font or bit match or anything like that。

That was just a hack to get the the render going and we're going to start with this hack。

 then we're going to have the fund later on， so the hack is we're going to go through each digit in the number and print it。

Since that's just like a， I know。Stupid work means not hard at all。

But we do have to get the draw each rack in the certain position for the zero for the one for the two。

 I'm going to straight up copy that the from the。From the Radeer from the crazy pond。

 so we have like a number， yeah。See， that's the kind of work we were supposed to do like we're going to go through digit here。

And then if it's zero， we're going to draw these rags。If it's， yeah。

 I have to do that for each possible digit。So I'm going to copy this code here。

And if you guys have any questions about the code， I can。I can help answer that software Re。

But it's really， really easy， I mean， we got that number， right？We have the number。

 so go through the first digit， which is the mod 10 right and then we also we have to do the first digit even if it's zero。

So we go through each digit and just draw based on what we are supposed to draw。Right。

 but our draw rack is called draw Act， not draw。Center size。Yeah。O。😊，Now， I suppose we can test。

What do you have。自己为持啊。Number。Yeah。Let's do0，0。The this。The number。Let's make it like。です。

The size let's do 5。And the color let's do。

![](img/fb0e7f46d547648aaa046497e55447ae_15.png)

Yeah。See， that's it， that's what we want it for now。



![](img/fb0e7f46d547648aaa046497e55447ae_17.png)

Now we're going to add this number up in the。The left hand corner。

And then we're going to add this score。This， this is what we want to do。

So we're going to do it this score， and then we're going to add。P much copy of this guy。

Im going to offset that。I1。Do have a score。

![](img/fb0e7f46d547648aaa046497e55447ae_19.png)

Square。Yeah。Should be 0。

![](img/fb0e7f46d547648aaa046497e55447ae_21.png)

Well， It know what if that is。嗯。

![](img/fb0e7f46d547648aaa046497e55447ae_23.png)

Student plus 10。

![](img/fb0e7f46d547648aaa046497e55447ae_25.png)

Yeah。Okay， it's a little bit big。Is do like to。5。And that's also a really like white。



![](img/fb0e7f46d547648aaa046497e55447ae_27.png)

Okay。That's kind of decent。Enough。

![](img/fb0e7f46d547648aaa046497e55447ae_29.png)

Yeah， I'm going to move that a little bit more to the right。Hs to like 15。



![](img/fb0e7f46d547648aaa046497e55447ae_31.png)

Yeah， that looks okay。 So each block we destroy going to just add this square so。



![](img/fb0e7f46d547648aaa046497e55447ae_33.png)

The strip block， like the destroyed。Actually， test for wind condition。

I'm going to do that in the test phone condition because when we destroy neighbors。

We also do this so。Test following condition。We increase， oh， we already had the blocks destroyed。

 to increase the blocks， destroy and increase the score。



![](img/fb0e7f46d547648aaa046497e55447ae_35.png)

So for now， all we're going to do is to increment。

![](img/fb0e7f46d547648aaa046497e55447ae_37.png)

So it's yeah。屎。哪先。Too interesting now what I am going to do here is going to go actually multiply。

 which is the idea we discussed last time。

![](img/fb0e7f46d547648aaa046497e55447ae_39.png)

We're going to plus equal life。So the idea is。I don't know what it's called Play your life。



![](img/fb0e7f46d547648aaa046497e55447ae_41.png)

Yeah， so the idea is in the beginning where we have a lot of life， each blocks worth three points。

 see？But if you like have only two lives， they're going to be worth two points。You have one。

So the idea is if you want to get a lot of points。You should just， you should really。

Where I'll basically do that in one run， which is cool， I think we could also add things later like。

Square multiplier based on。

![](img/fb0e7f46d547648aaa046497e55447ae_43.png)

No， yeah。Doing that。I think I'm going to do that。So， it's core。Going to do like。

Last time we destroyed a block。嗯。Yeah。Time， we。Let's see。Yes， last time。Bck。

And we also need now in the platform layer， we have the DT， right， every passing。

We're going to pass the current time。That's just going to add up because now we're going to save when we destroyed the last block。

They're going to see how much time passed based on that and maybe at the score。Current time。

Do you start off as zero？And for each frame， I'm going to add。Yeah， the current time。Plus equal。要来飞机。

首先你。Okay。Now what we can do here is every time we implementement the score。We said the last。Time。

 block destroyed current time。Maybe this should be a global variable think I'm going to do that。

At least for now， then we can clean this stuff and go like game state stuff and have a global pointer。

But， yeah。Well， those arent the only。嗰个冇 very仔先。事啊。Which is well。It just not。毎たい。A don need的。はい。Yeah。

😊，Current time now。It's going to start off at zero， so I'm going to test。Plus， the current time。

Let's say minus the last time。啊。Current time。Minus。The last。So let's say if it was like。

Once set well。Yeah。😊，They'll be like。For every second。Actually。

 this wrong should be like one over this guy。So the idea is if like we destroyed the last block。

At time five， now it time six。Right this is one。So yeah。

 I would have to do the opposite one over this guy。Oneだ？Over this guy。Now。If this is one。

1 over one1 K， this half is going to be two yeah。One second sounds like a decent number。

So if you do like a crazy， you're going to add a lot of scrum multi。

 maybe this' is going to be too much for just。Were goes together， let's just think about first time。

First time it's going to be like 10 minus zero， one over 10， yeah， okay。



![](img/fb0e7f46d547648aaa046497e55447ae_45.png)

This is going to work， but I think that's going to be really too much if forget like。What？😮。

What number did we pass minus a giant number？

![](img/fb0e7f46d547648aaa046497e55447ae_47.png)

So yeah， as suppose it didn't work in the。

![](img/fb0e7f46d547648aaa046497e55447ae_49.png)

T wind condition。

![](img/fb0e7f46d547648aaa046497e55447ae_51.png)

不次。Why didn't that break？Deestk four we。

![](img/fb0e7f46d547648aaa046497e55447ae_53.png)

Yeah。ItMore sense。

![](img/fb0e7f46d547648aaa046497e55447ae_55.png)

What？I didn't re break。Yeah， well， now we grow right。Test for wind condition。

I put a brief point in the blood the。Oh， I think we are optimized。Yeah。

Let me just check if I forgot to。To revert。Yeah， I did。Because when I post an HIO， I pass the。

 let me just show you guys the di。

![](img/fb0e7f46d547648aaa046497e55447ae_57.png)

I passed the minus02 flag， so there's an optimized build on each higho so the guys can play and I forgot to revert。

 but I suppose that was the only change I did。

![](img/fb0e7f46d547648aaa046497e55447ae_59.png)

![](img/fb0e7f46d547648aaa046497e55447ae_60.png)

不事。Yeah。The game what be added now。

![](img/fb0e7f46d547648aaa046497e55447ae_62.png)

Yeah而去。Yeah， sorry about that。嗯。Suppose not a computer。Okay， blocks destroyed。Current time is zero。

Now， that's weird。Current time plus post last yeah， so this is going to be crazy， but。Yeah。

 it's not supposed to be zero。嗯。Okay， so I put a data break point in to see。Yeah。

 I suppose there was going to be a debugy session。But I did think it was going to start debugging that。

哦我呀。Current time data break point。Nows see who's messing with this variable。

There should only be this guy。Really， and I want to break here yet。就是 yeah行。Yeah。Oh， lesss。

And no this is correct， yeah， it's because it's jump into the next statement。I'm going to。That see。

Yeah， this is zero， but the next time we go， yeah， let's just skip these。好きです。Assert。

You can just go to the end。Yeah， let's see。Current time。

I suppose we have something called current time and just overriding。



![](img/fb0e7f46d547648aaa046497e55447ae_64.png)

Current time。No， don't。Oh， we do。Yeah。Current time。That， that was， yeah。 so this guy was changing。

Dkerine。Maybe I disable that warning， I like that warning， which is like。



![](img/fb0e7f46d547648aaa046497e55447ae_66.png)

Oh， I don't think actually we have a warning for it。啊。We were writing a global variable。

Only for parameters。Okay。Okay， so this time around we should just add three， yeah， we did。Okay。

 now let's see the result。F， yeah， because we lost some life。And I just move for。

110 feet that was a lot。H90的。Yeah， but I mean I'm not， yeah， it's supposed to be a lot。

 but maybe not。That much 202。That can just make me invincible here I。Try to get a lot of points。

We should have tested at that time， there weve got it。The ball like glow。Going like crazy。

Or maybe we should just print， yeah， now that we do have a sort of a way to print to the screen。

More or less， we are going to do like a formal print later on。But well， not yet。



![](img/fb0e7f46d547648aaa046497e55447ae_68.png)

Yeah， I know what I'm going to do。I'm going to like this to like the time。Bonus。Just so we can test。

You're going to also draw。time。

![](img/fb0e7f46d547648aaa046497e55447ae_70.png)

So it should be zero from most of the time。But then you get like a lot。 Yeah， Okay， let's see，0。

Yeah啊。See， there was like a 64 once。So that's definitely a lot， we should you like to that by。10。

 maybe。Yeah。Well， maybe not by 10。Maybe by four， at least。嗯。

but it's kind of the fun of the game right so you want to really have a lot of points for that。See。

Yeah， but not 45， that's for sure。Maybe I'll divide by least five， yeah。



![](img/fb0e7f46d547648aaa046497e55447ae_72.png)

Yeah， let's try by my file。嗯。タイム？そうです。So instead of donating one over with this guy， I'm going to do。

5。

![](img/fb0e7f46d547648aaa046497e55447ae_74.png)

![](img/fb0e7f46d547648aaa046497e55447ae_75.png)

Let's see， not wrong， so it's 0。2。

![](img/fb0e7f46d547648aaa046497e55447ae_77.png)

Okay。其程就来。Very healthy。Should be like a fun project after well， not really。

 I was thinking about making like an AI play the game， like AI got you there， that's pretty cool。

And AI played the game， but I don't know。Okay， now we are talking， one， zero。

 maybe five was too much。Yeah， that was cool though， yeah one， now she got zero， yeah。Oh。

 weve got 23。Or maybe instead of doing the time should be like the amount of log that you killed without touching。

 you think。

![](img/fb0e7f46d547648aaa046497e55447ae_79.png)

I think they'll be better so we're going to do like。诶 touch。Bon and， instead of a time bonus。

 let's see。Touchless。まです。Yeah， so we increased that by the。Touchless bonus， that's a bad need。

Then we increment that afterwards。And every time we hit the ball。So player， condition with ball。

We set the touchless bonus to zero and then we can do like。Yeah。

 so this last ball thing here is's kind of a waste of time， but we have to do the。



![](img/fb0e7f46d547648aaa046497e55447ae_81.png)

Touch those one。And I think that's more interesting。Because're going to be incremental more。

 more based on and you're going to see the results， right， It's not going to be like。Oh。

 I got like a 50 out of nowhere。And then we should add like this number here just to。気？嗯。

It maybe actually should be like one times。This score， I mean， what times the life？Right。W。

 that was a failure。哎呀。Let's see。I didn't see anything， maybe that was too fast。



![](img/fb0e7f46d547648aaa046497e55447ae_83.png)

Oh， actually， we are printinging the wrong thing here。Yeah， the time bonus thing。

What are you creating the time bonus？Such things are time volunteer。

So we're supposed to print that touchless on。

![](img/fb0e7f46d547648aaa046497e55447ae_85.png)

Okay。Yeah， so the score is supposed to increment。Yeah。Whenever we do like more than one guy。

 see three。Let's see if I can get that going again。Yeah， three again。Yeah。That was cool。 Yeah，17。1，2。

3，4。Yeah。Okay， I think that was。It's nice。If you guys have any questions。

 be sure to drop them on the chat。And I'll try to answer it。Let's just try to get that one more time。

I think that was the nice。Choice。On doing the。Yeah，3。嗯。Okay，3。ok。Okay， so this score is done。

 let's say。

![](img/fb0e7f46d547648aaa046497e55447ae_87.png)

If you're in the score and now these two bugs here， I'm going to do the power downs before。

To bold leverage， but， yeah。Okay， so the score was a success。If we didn't forget any our down。

 we did actually。Because I don't know if you guys remember。I the Delta。TheMouse。Yeah。

 here's the thing we started to use the mouse delta。

Because we needed that to do like both power downs。

 both inverted controls power down and the slow movement power down。



![](img/fb0e7f46d547648aaa046497e55447ae_89.png)

But would did like a quick thing or received saved the old guy and that was a problem。

And if we inverted the controls and we were like。Near the end of the screen here。If we are inverted。

 we're going right， correct， so you can imagine us going right at this point。

And we want so about here we should be like in the middle of the screen and we want to go more。

 but we couldn't because we were at the end。 So the problem was， well。

 how are we going to prevent the mouse from reaching one side。

So I talked to the people over at a handmade network about that and they're getting a couple of suggestions。

 the idea that I threw around at at them。

![](img/fb0e7f46d547648aaa046497e55447ae_91.png)

Was that maybe maybe I couldn't。

![](img/fb0e7f46d547648aaa046497e55447ae_93.png)

Maybe I should stick the mouse in the middle of the screen。



![](img/fb0e7f46d547648aaa046497e55447ae_95.png)

Like this， and in each frame I get the delta， which is what I want。And I reset the mouse position。



![](img/fb0e7f46d547648aaa046497e55447ae_97.png)

Right。So the other and they also said that I could use like raw input。

 that is what most advanced games do， I think it's going to be pretty quickly for us to stick the mouse position in the center。



![](img/fb0e7f46d547648aaa046497e55447ae_99.png)

So let's do that。I'm going to do this for testing here in the beginning， so it' set。Very sir。Pa。

So if you guys remember we used getters a pause。To take that to get the mouse position。

 we're going to set it and just take x to y so we set it to 00。

 I suppose the mouse is going to be like here， we're going to play the game。



![](img/fb0e7f46d547648aaa046497e55447ae_101.png)

![](img/fb0e7f46d547648aaa046497e55447ae_102.png)

Yeah， it is。

![](img/fb0e7f46d547648aaa046497e55447ae_104.png)

Now we want to set it to the middle of the screen。😡，we should be able to get the screen size。



![](img/fb0e7f46d547648aaa046497e55447ae_106.png)

I don't remember exactly what the call is。Like an SDDN get， oh， yeah。

 that's get desktop that's what I needed。

![](img/fb0e7f46d547648aaa046497e55447ae_108.png)

![](img/fb0e7f46d547648aaa046497e55447ae_109.png)

Get desktop window。 Okay， so。I you like。Andle to a window。Desktop。



![](img/fb0e7f46d547648aaa046497e55447ae_111.png)

Miow equals。

![](img/fb0e7f46d547648aaa046497e55447ae_113.png)

Get that no。So now that we have desktop window， we can get the get window。Size。I suppose。



![](img/fb0e7f46d547648aaa046497e55447ae_115.png)

I think that's it。し。Get in those size。てや。

![](img/fb0e7f46d547648aaa046497e55447ae_117.png)

Getwin direct。Okay。Yeah， then we have to pass， correct。Yeah。Okay。

 now what we are going to do like screen。X， we can do like a V2 I。Screen size。Yeah。😊。

And then we can do like screen size that x going to equal correct。Right。

We already did that if you guys remember in the very first stream。Screen size of line equals。By。

Firsts going to check， I always forget the bottom one， it's bottom line is top。Okay。

 now I'm going to set the cursor and screen size。Dot X and screen size。It's going to open。

The window a bit more here， getting kind of hot。

![](img/fb0e7f46d547648aaa046497e55447ae_119.png)

Okay。Let's see what we have now yeah。

![](img/fb0e7f46d547648aaa046497e55447ae_121.png)

Actually， when I played the game， the mouse did go to the very end。



![](img/fb0e7f46d547648aaa046497e55447ae_123.png)

But I kind of got that wrong， It's supposed to be like half screen size or a centered screen， yeah。

And then screen size centers。That's what we wanted now it's going to be like this guy。D Ied by2。



![](img/fb0e7f46d547648aaa046497e55447ae_125.png)

C。Okay， so we are exactly in the center of the screen that was pretty cool。

 we want to do that every frame this this guy here。😊。



![](img/fb0e7f46d547648aaa046497e55447ae_127.png)

![](img/fb0e7f46d547648aaa046497e55447ae_128.png)

But since we're not going able to close the game。

![](img/fb0e7f46d547648aaa046497e55447ae_130.png)

And I don't know what's going to happen because maybe even if we all tab。



![](img/fb0e7f46d547648aaa046497e55447ae_132.png)

It's going to be stuck anyways， so just as a contingent plan we're going to add all that four for the game。



![](img/fb0e7f46d547648aaa046497e55447ae_134.png)

In the peak message loop here。We process these buttons， I'm going to do like if Vk code。Equals to VK。

And I believe。Rning equals false。We could just return。

 we're going to break the look in case we want to do like some shutdown stuff， but I don't think。

So this dising at four， I have to see if the alt is down and don't remember how we do that in SDN。



![](img/fb0e7f46d547648aaa046497e55447ae_136.png)

Ops down。Get key down。 let's see al。A non system key is a key to when the al is not press indicates whether。

Ks extended stitch as the height。

![](img/fb0e7f46d547648aaa046497e55447ae_138.png)

I think I'm going to copy that since we already copied a thing from the crazy P game。

Let's just see the out。啊。C，f 4。What just it for。Oh， okay， this is the alt， okay。

Should have commented that， as suppose to9 32 crazy long yet。 So this is the。All down。



![](img/fb0e7f46d547648aaa046497e55447ae_140.png)

I suppose that was correct in the documentation。The context code values are0。嗯。😊。

For a key down message。

![](img/fb0e7f46d547648aaa046497e55447ae_142.png)

Oh， this is the AlPm。Yeah， well， I'm not sure I'm going to have to break to break down and see。

 but the idea is if these two are down， consider running into false。



![](img/fb0e7f46d547648aaa046497e55447ae_144.png)

Let's see if we， actually。Yeah，4 does nothing。

![](img/fb0e7f46d547648aaa046497e55447ae_146.png)

Ill have foreclos。So I suppose that argumentation is just wrong about that。



![](img/fb0e7f46d547648aaa046497e55447ae_148.png)

![](img/fb0e7f46d547648aaa046497e55447ae_149.png)

Yeah。😊，Not going to think too much about this guy as long as does it worth for this version。



![](img/fb0e7f46d547648aaa046497e55447ae_151.png)

Okay， so all the four closes the game， right？

![](img/fb0e7f46d547648aaa046497e55447ae_153.png)

So let's try， let's try doing that。 So we're going to。

Get the cursor here and we are doing the gap cursor position。

We should just get the Delta and after we get the Delta。You set it back。です？Right。

 so in platform common。We're going to， yeah， we already have the mouse APp。

 you're going to delete the mouse P。And amount DT is going to be。This guy。😊，And I think you can just。

Separate this guy into life。Mouse。P。So we only want the DT for now。So， mouse P。

I'm going to go back where I think I comment that。Yeah， this is what we wanted to do。

Why is the player why？我s。Yeah， I'm going to keep that。Comted。And this guy's going to be。はいです。

If we are not inverted。O。The mouse P。Oh， we need the mouse， the O there。嗯。😊。

We need the mouse people I think。I think I'm just going to save that as a mouse pointer thing like this。

Then， just。I yeah， maybe。I'd see here。I'm not going to flip。Yeah， and I am going to flip yeah。

 I'm going to keep pretty much like this。 So the mouse pointer。I。I did this and said。Yeah。

 can I pointer。And this guy。I set them set the mouse pointer， but I actually should do the。

Let's see the new mouse pointer。Get we transform its。喂hy。And then the mouseuszi B is going to be。

The new mouse pointer。Minus。The mouse pointer。Yeah， this guy。

And then we set the current position at the center of the screen， and then we set。The mouse pointer。

 and we have to， this is going to be like only if we are the focus window。

 we have to do that for robustness， right？But if we， if we are the mouse pointer。

Let's see mouse pointer。Equals no。

![](img/fb0e7f46d547648aaa046497e55447ae_155.png)

O。Now。Not sure how good this is going to work， so we are in the middle of the screen， right？



![](img/fb0e7f46d547648aaa046497e55447ae_157.png)

And I can't move， can I see that， I'm writing the okay。



![](img/fb0e7f46d547648aaa046497e55447ae_159.png)

Let me try moving my head。Just so you guys can see。



![](img/fb0e7f46d547648aaa046497e55447ae_161.png)

What do we have。See the mouse there？Now this is perfect。This is， yeah， this is pretty perfect except。



![](img/fb0e7f46d547648aaa046497e55447ae_163.png)

Let me put it back。

![](img/fb0e7f46d547648aaa046497e55447ae_165.png)

Except。I don't know where we are。I don't know， yeah。嗯。Let's see， I'm going to put a break point here。



![](img/fb0e7f46d547648aaa046497e55447ae_167.png)

In a simulate game。Actually。Okay。So。Oh， I think if you are all at four it does it already。Yeah。

 I'm not sure I have to test that but。Let see。😊，The mouse Dp。Oh， because okay， yeah， the first time。



![](img/fb0e7f46d547648aaa046497e55447ae_169.png)

Yeah， first time this guy should get zero。嗯。Current mouse。

We don't need to get the mouse pointer first。All we need is to。Zero that。Yeah。

Because we are setting its position to the center of the screen the first time around。



![](img/fb0e7f46d547648aaa046497e55447ae_171.png)

Okay。Yeah， oh， and just just as a note。

![](img/fb0e7f46d547648aaa046497e55447ae_173.png)

This guy。This guy actually be the very last thing before the。



![](img/fb0e7f46d547648aaa046497e55447ae_175.png)

Let's see。This should be zero， I think。Pro was not zero。Let's just play and see what happens。



![](img/fb0e7f46d547648aaa046497e55447ae_177.png)

Yeah， see the Al4 doesn't work or the Alt doesn't work。



![](img/fb0e7f46d547648aaa046497e55447ae_179.png)

So we have to change that。

![](img/fb0e7f46d547648aaa046497e55447ae_181.png)

So the thing is we have this window message。You're a。嗯。Yeah， like WM activate。App。This is called。

Set when the window belonging to a different application is about to be activated。

So this is when we are not。Activated。Correct。Or we whether the window we like， okay。

 so we got both true or false。

![](img/fb0e7f46d547648aaa046497e55447ae_183.png)

So yeah， the W PRm of the we， okay， so we have to treat this message。Which is WM Act8。So， if。

The message。Dots doluoram。

![](img/fb0e7f46d547648aaa046497e55447ae_185.png)

Is on。If it's true， the window is being activated， well， which window is it our window？



![](img/fb0e7f46d547648aaa046497e55447ae_187.png)

Let's set a lock mouse to false。Ho。啊。Mice the true。

And another thing we want to do here we want to zero the input。

This is a robustness thing that if the guy like does auto for all tab。

In the middle of another key press。It actually。Then when we do the other key up。

 I think I'm going to show you guys this， oh， but we're not using key presses， so yeah。

We're going to try to explain it thing is。

![](img/fb0e7f46d547648aaa046497e55447ae_189.png)

If we have。Let's say we were controlling this guy left， right？We are we pressed down。

 let's say the left key。Are the right teams I'm drawing right， yeah。If we press down the right key。

 and then here we all tab。And here we're not controlling the app and here we release it。

 when we go back to our app， our app still thinks that this guy is down。



![](img/fb0e7f46d547648aaa046497e55447ae_191.png)

Because we didn't actually。Got the key of message。 So one thing I do just for this robustness thing。

 I just zero input when we lose the activation。Kind of makes sense， I think。

So let's see if the lock mouse think it's going to work， let me just close this guy。

So these are the global variables。And'm going to do like， this is also global， but yeah。Lock mouse。

Tm to be true by default。And then here。I can do like。It's locked now。Message dot。Oh yeah。

 we got W per。感兴趣。Input。嗯。😊，あああ。Do we pass that as a parameter？We do。

I think this is going to be global。But let's call these guys like。啊。我等点。Yeah。

So these are the global for the games。This isn。So ct are， yeah。That that。



![](img/fb0e7f46d547648aaa046497e55447ae_193.png)

Okay。It and a nice sun down here。Okay， so oh， sorry。



![](img/fb0e7f46d547648aaa046497e55447ae_195.png)

That was wrong。So we start， I should just， I think I'm going to move myself。啊。



![](img/fb0e7f46d547648aaa046497e55447ae_197.png)

Allder for。I have OPS S in it。Okay， think I'm going to move myself up here just so guys can see。

The mouse what's going on， so we start the game and it's not locked。



![](img/fb0e7f46d547648aaa046497e55447ae_199.png)

But when I tapped。

![](img/fb0e7f46d547648aaa046497e55447ae_201.png)

It's locked， so we're doing it the other way around。So I suppose。



![](img/fb0e7f46d547648aaa046497e55447ae_203.png)

When this says。That is true if the window is being activated， I suppose it's。



![](img/fb0e7f46d547648aaa046497e55447ae_205.png)

Arow window， right？

![](img/fb0e7f46d547648aaa046497e55447ae_207.png)

This is kind of stupid， but I mean， we can are kind of stupid。

Because it kind of makes sense if the wind just be activated what this guys talking about。



![](img/fb0e7f46d547648aaa046497e55447ae_209.png)

A different。Applicationcation。So。

![](img/fb0e7f46d547648aaa046497e55447ae_211.png)

But it doesn't matter， really。Okay， so we're not locked。And now we are locked。

 we didn't change anything think did you compile。

![](img/fb0e7f46d547648aaa046497e55447ae_213.png)

Oh crap。 So we yeah， we want to stop。 Oh， but I closed。Okay， you have to open that again， oh my God。

Yeah。I thought， I just。I didn't do remember our best audit for。



![](img/fb0e7f46d547648aaa046497e55447ae_215.png)

Okay， so opening any Vi studio again。

![](img/fb0e7f46d547648aaa046497e55447ae_217.png)

ok。I think I swapped them did I not I did it。

![](img/fb0e7f46d547648aaa046497e55447ae_219.png)

I have to go through that。Clled bananaan。Yeah， now you're stuck and Ire not like， yeah。Let's see I I。

 yeah， okay。Yeah， it wasn't that hard， oh， but we do get a crazy yeah， at this point。



![](img/fb0e7f46d547648aaa046497e55447ae_221.png)

At this point， we should also zero。This guy。I'mSo， let's see which guy。This guy。

 Sand a mouse pointer。Oh， so it's also just going to for all these guys as a look one。

But we have to zero ham up here。Because， let's say。是这。pointin。



![](img/fb0e7f46d547648aaa046497e55447ae_223.png)

I'd say if if we auto out tab and then move our guy here， when I auto type back。

 this delta tag is going to be picked up。putut my finger in the camera。

 this delta is going to be picked up by our delta and it shouldn't be really。



![](img/fb0e7f46d547648aaa046497e55447ae_225.png)

Okay， I think this is good。But we still don't see our guy， right？Let's see why we don't see our guy。



![](img/fb0e7f46d547648aaa046497e55447ae_227.png)

I'm going to put a break point。Here in the simulate game。可能。Yeah。So this guy should be zero。

And it's still not zero， well let's see what we have in a few frames over。G'， yeah， now it's zero。

So the problem is the first frame。I'm going to go through the first frame just to see what's going on。

Here。Yeah。So， let's see。We first center the mouse。Oh， it shouldn't be zero。

 it should't be the standard。

![](img/fb0e7f46d547648aaa046497e55447ae_229.png)

Yeah， that was kind of stupid。 So a center， let's see。Yeah， it should be whatre setting the。

Same the mouse pointer two。So we're getting the offset from like the。Zero position to the century。

Yeah。So。Okay， is those correct and we are activating the app in the beginning。Oh。

 but we don't have say。Yeah， again， I'm just going to throw that as a global for now。At least。

 and I think we' forever。Because I should really like doing this。

So the game doesn't create things like a bullet and mouse， yeah， I think we're going to do this。

This is a little bit of a cleaner way of doing this。ロボ thing。Yeah。嗯。Okay。Process button。32 inputs。ok。

😊，This guy， knew mouse pointer in my。O。So I suppose the documentation was correct。

If we're not locked， oh no， yeah， lock mouse。Never mind。Lock mouse。

 we32 lock mouse in the late can be。

![](img/fb0e7f46d547648aaa046497e55447ae_231.png)

this guy。

![](img/fb0e7f46d547648aaa046497e55447ae_233.png)

Okay， now let's see the problem。The simulate game。The mouse Dp is still pretty big。

 well let's go again。And step through the first code here。First guy like。Oh actually should really。

 I should really like。So the mouse new mouse position is center， I think。Yeah。😊，Yeah。

 the new mouse position， okay。The center screened。The only 32 miles is zero。



![](img/fb0e7f46d547648aaa046497e55447ae_235.png)

So I suppose it， oh， yeah。Yes。😊，Because the first time this is zero。

So after we set the center screen for the first time。



![](img/fb0e7f46d547648aaa046497e55447ae_237.png)

We are going to set it。Okay， so we didn't fix that problem and we did that on the call deck。



![](img/fb0e7f46d547648aaa046497e55447ae_239.png)

Okay。Starting to get something。

![](img/fb0e7f46d547648aaa046497e55447ae_241.png)

But of course， we are stuck just like a mouse， which。



![](img/fb0e7f46d547648aaa046497e55447ae_243.png)

Probably X。It's probably pointing to this as a problem。So get the new mouse position。

We can we we get the the deelta to the。We in 32 month oh， we shouldn't really change this guy。



![](img/fb0e7f46d547648aaa046497e55447ae_245.png)

This should always be the center。

![](img/fb0e7f46d547648aaa046497e55447ae_247.png)

Guess not。We set it back to the center。The next time。It's to test。Against the center as well。

You know what， I shouldn't really have this guy。I should just remove the new。Guy here。

And this guy should really be the same screen。Yeah。

We're going to lock it to the centernder screen in this guy。It's going to be。The center screen。 Oh。

 it's already a。Me too， I suppose。Be right。Sent your screen， you're only 32 on the screen。Okay。

 center screen。Yeah。Okay， now the mouse pointer guide。I'm going to delete。So yeah。

 it's pretty much going to be stuck at the center position。No need to do that anymore。



![](img/fb0e7f46d547648aaa046497e55447ae_249.png)

Okay， now it's going to the other side， but the idea is correct， I think so。



![](img/fb0e7f46d547648aaa046497e55447ae_251.png)

In the beginning， we just。Get the center and set the mouth to the center。

So the first time around the issue should be zero because we just add it to the center， right？

So it gets。Oh， we're getting， yeah， we're getting like screen to client。

I don't think now we want to do that。 we want like the absolute screen see of the mouse， okay。



![](img/fb0e7f46d547648aaa046497e55447ae_253.png)

![](img/fb0e7f46d547648aaa046497e55447ae_254.png)

HaBut。You guys couldn't see that， but it's inverted。



![](img/fb0e7f46d547648aaa046497e55447ae_256.png)

Probably because I'm studying it wrong， so I'm the new， yeah， the new minus the old。



![](img/fb0e7f46d547648aaa046497e55447ae_258.png)

Yes。是别。

![](img/fb0e7f46d547648aaa046497e55447ae_260.png)

Okay， now， this is pretty cool。Yeah。 see those points are racking up。Now this is awesome， I think。

Yeah， now we can leave the screen， I don't have to fix that。When we do our game。Feel pass。Yeah， nice。

Yeah， okay。Yeah， now I can't close it with a mouse。



![](img/fb0e7f46d547648aaa046497e55447ae_262.png)

It's okay。She should also make ask escape。Detro the game。I'm going to turn the light off。

Oh because it's getting kind of dark in here， Okay， now you guys can see the whole thing。So yeah。

 I think it's good for now also going to second mouse。



![](img/fb0e7f46d547648aaa046497e55447ae_264.png)

I'm going that that in the to be app or。We're going to set the cursor。To zero because now it's stuck。

 so we might as well just not show it。

![](img/fb0e7f46d547648aaa046497e55447ae_266.png)

So while it didn't do anything。

![](img/fb0e7f46d547648aaa046497e55447ae_268.png)

嗯。Maybe I to do that on the mouse group。啊。

![](img/fb0e7f46d547648aaa046497e55447ae_270.png)

です。Let's see。Now， still showing。

![](img/fb0e7f46d547648aaa046497e55447ae_272.png)

Set cursor。

![](img/fb0e7f46d547648aaa046497e55447ae_274.png)

Let， let's see the MSDN。这し。Set cursor。If there is no previous cursor， hand it to a cursor。

Or load by load cursor if the strmer is no， the cursor is removed。



![](img/fb0e7f46d547648aaa046497e55447ae_276.png)

Yeah， so I don't know why。The cur wasn't on move。Let's do you like this。



![](img/fb0e7f46d547648aaa046497e55447ae_278.png)

嗯。😊，Well， it's not getting removed。

![](img/fb0e7f46d547648aaa046497e55447ae_280.png)

![](img/fb0e7f46d547648aaa046497e55447ae_281.png)

Yeah， but we can worry about that。That cares。

![](img/fb0e7f46d547648aaa046497e55447ae_283.png)

Okay， now。Okay， it's kind of looking good。 Now we now we can do。



![](img/fb0e7f46d547648aaa046497e55447ae_285.png)

I'm going to add the ask key， escape key。TK code。Just because it's kind of intuitive。

 too close the game with escape。But we can do like a manual later on。 So if the Vk code is VK。



![](img/fb0e7f46d547648aaa046497e55447ae_287.png)

Yeah。😊，Because now we can' we can go to the A axis and close that， okay。



![](img/fb0e7f46d547648aaa046497e55447ae_289.png)

Now we have all the structure ready to do the。The two power downs。 So the power downs。

 let's say power。We have。Insta kill， which is already done， I just going to like。We lose a life。

Strong blocks is done。It can turn back this assertion。

Inverted controls is done and then I'm going to do this slow player， let's do slow player first。

A slow player。Controls。Okay。Slow player。To reset that。Yeah， in the simulate game。

They're doing like this。And then we do， like， if。Slow player is greater than 0。Do like a remote bus。

好吃。S2 one， in this case。It'll be， I don't know， half。So it's going to be like， oh， this is an no。

 it's not， I thought I was an in。Speed multiplier times。Whatever this guy turned out to be。

Sp multi times。这 guy。Okay。Yeah， this is the。ど？

![](img/fb0e7f46d547648aaa046497e55447ae_291.png)

O。Oh。

![](img/fb0e7f46d547648aaa046497e55447ae_293.png)

Ass well to test that。I should make。When we create the blocks？They actually， you know。They actually。

Are everyone's going to give these power low play。

![](img/fb0e7f46d547648aaa046497e55447ae_295.png)

Okay。

![](img/fb0e7f46d547648aaa046497e55447ae_297.png)

Let's see if we are slow。We're not。Ex suppose。Oh， but It think we're collliding with that too。



![](img/fb0e7f46d547648aaa046497e55447ae_299.png)

Okay， we are， but actually we are wrong。Wow， it's low player。Yeah。We should just keep this guy。

This guy should be kept。And this guys be multipl。Makes sense。Yeah。😊，The this guy。Mus。



![](img/fb0e7f46d547648aaa046497e55447ae_301.png)

O。Now， let's see。If we par slow， I don't。Appeared to be slow。What。😮，What was that。



![](img/fb0e7f46d547648aaa046497e55447ae_303.png)

You have to review that code as well。I may just go to the video and see what exactly happened。

That was weird。O。😊，Speed multiplier。Times。Whatever this guy turned out to be。This looks correct。

If the slow player team。

![](img/fb0e7f46d547648aaa046497e55447ae_305.png)

我呀。Don't know。

![](img/fb0e7f46d547648aaa046497e55447ae_307.png)

Do know what's the problem？Okay， now I think it worked， but I was too shocked looking at that bug。

 yeah， it worked， oh this is pretty cool， I think。Even 0。1 just low。Wow， fast the normal speed。

It's like super fast。Yeah。哈。😊，We should have a timer， so things like that don't happen， right？



![](img/fb0e7f46d547648aaa046497e55447ae_309.png)

Yeah， so in the game。Few paths。 Let's call it that or is the small few paths。Let show timers。Because。

That wasn't fun。0。1。感谢。0。05， yeah that's what we did， that was a bit。



![](img/fb0e7f46d547648aaa046497e55447ae_311.png)

Okay， now this is nice。K。Okay。I think that was correct。What I assumed happened。

Was there we hit the side？Of a guy。And we try to hit the side of one gun。See。

 not sure that's correct， though， because if we hit。



![](img/fb0e7f46d547648aaa046497e55447ae_313.png)

Andm going have to play around with that so let me just。Review didn't forgot。 yeah。

 we finished all the powers。Although I think we had another idea for power in vertical controls。

Did that low player blocks， the randomom ispled more blocks when kill blocks that change rivalry。

I remember that was another idea for a par down。Yeah。あの？嗯。So yeah， that was weird。

 let's test the Dp dot wise， let's see where we change that。Update。Walls。

What is the do ball block condition。 Yeah， so if we do the X collision。

 we also reset in reverse ball。

![](img/fb0e7f46d547648aaa046497e55447ae_315.png)

DB。Let's try not doing that and see how it looks。 I don't remember how the original breakout is。



![](img/fb0e7f46d547648aaa046497e55447ae_317.png)

![](img/fb0e7f46d547648aaa046497e55447ae_318.png)

Let me just see。No of that we tested it。第。The slow。Player。N。

Let's just make sure that we got all the power。We've got other powers implemented。😡。

Slow plaing vertical controls， strong blocks tend to kill。



![](img/fb0e7f46d547648aaa046497e55447ae_320.png)

That looks about right。Okay， so what I want to try。That was a big fail。Yes， see。

 I think that's the expected behavior。Anyways。Yeah。Yeah， okay。I think that's correct。

And I have to play around with that for a while。I think that they'll make it a bit easier to。

To climb， which is good I suppose。Because now we can just pretty much do like this。一行。Yeah like this。

Okay， it's not any easier， I suppose。Yeah。那倒 was是。Let's see。 That's record。There。O。嗯。Yeah。

 I think that's better。

![](img/fb0e7f46d547648aaa046497e55447ae_322.png)

So we don't reverse， let's see reset and reverse ball P。Yeah。We don't do that。We hit the X。

 which makes sense， right？I don't remember exactly why we did that in the first place in the X。

I suppose it makes sense， but。嗯，O。So these two bug down here might be when the collision happens on X see。



![](img/fb0e7f46d547648aaa046497e55447ae_324.png)

I think we kind of solved that just by not doing the thing we were doing so。Let's play around。

 we should also make them random。不。Thats a nice climate， see。



![](img/fb0e7f46d547648aaa046497e55447ae_326.png)

Dude， that's awesome， oh， and we here， So I suppose you forgot something par account。



![](img/fb0e7f46d547648aaa046497e55447ae_328.png)

W shouldn't the part count？Part accounts like the last。 Hi， what did I miss。

 We started doing a lot of cleanup。

![](img/fb0e7f46d547648aaa046497e55447ae_330.png)

And overall improvements on the gameplay。So we did a score system if you see in the top left corner now we count scores so were drawing numbers our render now support drawing numbers it's still a pretty hacky thing。

 we don't have bitmps yet we're going to do that in the engine pass but at least we can draw the score and we played around a little bit of a score and now。

We also changed the mouse movement completely。If if you see in the right hand corner of the screen。

 see the mouse。Neer like the breakpoints in Vijo Studio。

 that's where the mouse is so we are sticking it to the center of the screen we sticking it it's kind of fun sticking it to the man。

We are sticking it to the center of the screen。And we're only getting the delta。

 and that allows us to do what we couldn't do when we were trying to get the absolute mouse position。

Which was the correct inverse， a power down and the slow power down， which is pretty cool now。

 I think。So yeah， what we are just trying to do is just running down these bugs and notice this。

 so that's what we're going to do。

![](img/fb0e7f46d547648aaa046497e55447ae_332.png)

We're finishing these guys。Which is more like a gameplay cleanup pass cleanups in terms of。Bugs and。

Things that were kind of left unfinished。We're going to do that。

And thatll be the end of the initial gameplay。And then you can do this clay cleanup。

 which is not going to be too much because I think it's pretty well structured。At least for now。

 I an O seat。And then we can do the fuel pass， I think we'll do the fuel pass next time。Good。

 I love the the pseudo thought。 Yeah， I do。 You should see that。 Let me show you the code that we。

 we didn't write that by hand because already did that like 10 times already。

 And that's really boring。 So we just copied that from the other project。😊，But super basic to it。

 we just for each digit， we just draw the number of racks that we want to draw， so that's it。

That's really stupid。But it works really nicely， I think we're going to draw that at the end。

Prr file。Works nicely for now。Then when you do like proper font Bimap rendering。

 you can like make a font。And turn that to a bitm。And then draw that， Okay。

 I just want to do the wall。AGuy here。Instead of doing this kind of crazy stuff。

 I'm going to do if we are in the。Let's see in the first three guys， So if we are。Less than three。

Or should I say less than are equal to2？I'm going to possibly add。A power block。Block， par block。

It's going to be oh， actually， yeah， this is gonna be the random choice。

 We did random last time It's pretty easy。 Let's say random choice out of6。那是。

And we're going to do a random， we shouldn do it like a random。Power block， I think。

 like random and power up and we to power down first7 segment display。And just styfo this course。

 yeah， we could do like a pixel font。

![](img/fb0e7f46d547648aaa046497e55447ae_334.png)

But maybe it can be like a little bit more stylish。Instead of doing like one like this。

We can do like a one like this， which is also cool。I don't know。

 maybe we could just keep that as a relic。😊。

![](img/fb0e7f46d547648aaa046497e55447ae_336.png)

Of our hacks in the development。I'm going to do a random power up。Yeah， I think that's gonna be cool。

 And we we are in the last two guys。 So if we are。Greater to our equal。

Greateaer than are equal to six。Grandham tries six。And its do to a random car down。

And XPM parser or something like that should be simple to add。Yeah。😊，Maybe， which I wanted to do。

 like。Cooler think of the but。Not sure。 I just want to finish this game because I had a lot of ideas about other games as well。

 but I do want to finish before I started another one。 the first thing for bitn and text mode。 Yeah。

 exactly， but we did at the beginning of it's not parsed by any means， but。😊。

We interpreted this guy as a， I don't know， a level thing like a level editor， I suppose。

 a tilemap editor， Yeah， tilem so。Do that。We could expand that and do like for blocks and that I think would be enough。

Cool thing to do in the editor in terms of parsing for this guy this time around。But yeah。

 I mean making games make you have more different for games， which makes you want to do more games。

 so it's kind of a positive feedback loop in this sense， yeah， I do have the random key。

In range this guy。 So I'm going to do a random。Power up。Let's see if we have any more like random。

Its。See， this is a random part down。Yeah。Po random。H right down， see this is semantic compression。

 man， this is what Casey means by semantic compression。This is awesome。Seeve did all of them。

 so in the power up， let's see this guy。I think it is。I may actually just do。

let's do a full function， I was think about doing a man。Random int。randomandom。Power up。Reture。

Random end and range。This guy。Yeah， one two part of that。Then we can do like that。And。Random。

Which is this one？Okay。She starting to run out of water， had a pretty salty lunch。

 som probably going to drink a lot of water this stream。Random power down must turn value。

Of coursese。ます。

![](img/fb0e7f46d547648aaa046497e55447ae_338.png)

オッケー？Now let's go back to this guy。And see。The our randomness。Improves the experience， well。

Maybe that was a bit too rare。Yeah。That was certainly too rare maybe we can do like twice as much。Oh。

 but now it works and that was pretty cool， Oha， yes。That's what we wanted as a commentt。Okay。

 that was pretty cool。 And look at that score， man。 Oh， inverted controls。😊。



![](img/fb0e7f46d547648aaa046497e55447ae_340.png)

Okay。Okay， that was pretty cool。You know what？In our。

Engine improvements are also going to do file IO。For ice core。And level saving。

I'd say saving the level。Taving unlocked levels。And I， of course。

So we probably want to add a manual at this point。Probably。So menu。

Mainine is not really a major improvement。But heck。



![](img/fb0e7f46d547648aaa046497e55447ae_342.png)

Think you guys got the idea。So I think we're starting to have a cool game。



![](img/fb0e7f46d547648aaa046497e55447ae_344.png)

Okay， so this is the least cool game。 Maybe there there are too many blocks。



![](img/fb0e7f46d547648aaa046497e55447ae_346.png)

Honestly。I'm going to remove like a one row of them。In a。Yeah， I'm going do。Maybe we need two rows。

 oh， not in the exit。

![](img/fb0e7f46d547648aaa046497e55447ae_348.png)

![](img/fb0e7f46d547648aaa046497e55447ae_349.png)

Yeah。

![](img/fb0e7f46d547648aaa046497e55447ae_351.png)

not sure。Maybe if I like decrease a couple of things here， increase the size。Let's do like 6，5，3。

 I think it's gonna be too much。Thats yeah， way too much。Let's add like 10%。



![](img/fb0e7f46d547648aaa046497e55447ae_353.png)

It's easy to make a math by。Okay， okay， I like that。 I liked the act。😊，So we've got fewer blocks。

Which means's going to be easier。Which is good I suppose the first level， we don't want to。

We don't want the player to quit I have this problem with my with my big commercial game Okay。

 so we don't want that as well we don't want the player to quit before he gets the cool part of the game。

 but we can't just put the cool part right off of bat like this。

Because it familiar enough with things like power ups， at least。As well as the game itself， right？

Oh man。Look at that。Dude， that's going to be super overpowered the comment guy。Dude。That was awesome。



![](img/fb0e7f46d547648aaa046497e55447ae_355.png)

Oh， we should see， yeah， we should test the other but， okay now。



![](img/fb0e7f46d547648aaa046497e55447ae_357.png)

This is pretty cool Now all I have to do now I'll make the block a little bit bigger。



![](img/fb0e7f46d547648aaa046497e55447ae_359.png)

Maybe I should remove like one extra roll and make it a bit bit。



![](img/fb0e7f46d547648aaa046497e55447ae_361.png)

scribe。

![](img/fb0e7f46d547648aaa046497e55447ae_363.png)

Okay， let's try moving。

![](img/fb0e7f46d547648aaa046497e55447ae_365.png)

Okay， this looks， pretty cool， I think。Kind of like that。

We should also cap these guys at the very end just to make it more interesting。

Oh we also increase grant of choice。

![](img/fb0e7f46d547648aaa046497e55447ae_367.png)

In the wall。 Yeah， let's make it。4。One in four maybe is a bit too much， 25。Now we， these bugs， Okay。

 we finished the comment， I think。Certainly looks good now， let me just add like。比要不拉。Right。

We're going to do the con so black。Power block。

![](img/fb0e7f46d547648aaa046497e55447ae_369.png)

And we go to comment。Good to see a lot of comments just so we can test every possibility。

 So the first thing we're going to do is test。 Yeah， good。 that was nice。😊，See。

 that's a perfect comment。Let's test that again。But this time let's do like a diagonal comet like this。

Cool。Co。See， we have to be careful with comments though。😊，Yeah。

 let's see a very vertical comment and a fer。Okay， let's just try once。To get like a very。Yes。Yeah。

 I think it's pretty cool。

![](img/fb0e7f46d547648aaa046497e55447ae_371.png)

So I liked the comments。Let's stress the table shot。Which was a little bit problematic。The bug real。

 yeah。

![](img/fb0e7f46d547648aaa046497e55447ae_373.png)

To foria。Let's let's test the triple shot。Oh， not sure this is good， though， the first position。

It's right in the beginning of two blocks， so we may want a different。So now it's working。

Another thing I want to do with the triple shot。That was a failure。Is I want to， I want to。

 I think I also， I always want to have this pattern see because that was really confusing。

SoIf you have a triple shot。Not sure， I was thinking about in a triple shot scenario。

 the normal ball always go in the center position。But I don't know， yeah。

 I see because it's kind of confusing if you have a lot of balls。But it's not too bad， I suppose。

I mean， you do have to pay attention， which is good， right？And you can also yeah。

 like if I'm trying to， if I'm trying to like open that that guy right there。

 and if I get a triple shot。I can still be able to do that。Yeah。

And I think the Jual shots are board key。Yeah， what I want to try is like a two shot。

just make me I want to try triple shot。That I gets to the why。Gooduy， yeah。嗯。

I'm just looking out for a you。Behaviors， I think the whole problem was inverting the why。

In the expavation， which we fixed the beginning of。This stream。看 that was。Oh。

 we didn't destroy that blow。No， we did。No， I suppose it's working。 Yeah， the problem was。That guy。

O可以。

![](img/fb0e7f46d547648aaa046497e55447ae_375.png)

Very cool， so we finished that。Now it's the kind of tricky thing I think is the more mathy thing of today we we've。

 you know， solving problems pretty nasty I like this kind of a stream， I mean。

 not stream because I've been doing this for just like a week。

I like this kind of a work where we have a lot of problems and we go like one by one fixing them because I think。

It feels really productive。Right。Yeah， because we did a lot without， without， you know。Without。

 you know， a lot of time， I suppose yeah。So create blacklock or remove that guy。

 so now let's try to fix the two ball level So right now the two ball level is all crazy。



![](img/fb0e7f46d547648aaa046497e55447ae_377.png)

It's， I mean， yeah， this guy pretty slowly now it's guy gets fast and this guy's slow and then it's hard to control like see I want to move this guy the other way the idea is cool and before before I say it's too hard for the player or it makes no sense whatever。



![](img/fb0e7f46d547648aaa046497e55447ae_379.png)

I want to try a bit more。Hello， Marfia， it's nice to see you back。呃。

We're doing some gameplay cleanup。And I think the games getting a lot better。

 We added a score system。 You can see that in the。😊。



![](img/fb0e7f46d547648aaa046497e55447ae_381.png)

In the left corner of the screen， we finished all the。Power downs。We finished those。

 we fixed the ball movement when it collled with X。

 and that fixed the power ups that were problematic。I'm great。 How are you。啊。Had a lovely Saturday。

And of finishing it。Programing games， dude， what a bet。 How can I do it like a better。

And this your Saturday。Then to do gamess， okay， but we want to finish this guy。

And this guy is kind of problematic。 So the idea that I had。



![](img/fb0e7f46d547648aaa046497e55447ae_383.png)

Mypresent good university course is finished。 Oh， this is great ma'am。 When I was at university。

 I couldn't wait for them to finish and。😊，The time off the vacation。

 I suppose they had the vacations of like a month or so was enough to get anyone to go back。

But that was just for a period， I didn't actually finish university I quit。

In the middle to finish my game。I think there was a fair trade， though。So， yeah。

I didn't actually do a lot， anyways。But I did meet a lot of people there and that's I think what university is best at。

 you know networking and getting to know the professors and the colleagues。

 people interested in know getting together and making games in advance learning。So in this sense。

 that was pretty cool， but in sense of the actual subject。

 it wasn't very it was kind of a practical university， so yeah。

'm not sure I learned a lot just by doing myself， I was already doing the game before I went to university in Yo's Hunt。

 I was already doing that so。I still have to learn for exams。

 but at least no more running to university here。Well。

 I did like to go to university physically because I went on foot。

And I was kind of chubby before university and in Bel zone， there was the city where I live。

In Bel Zhi， everything's like uphill。 So I went like for half an hour uphill to the university。

 So I I really got to a better shape just by going to university every day。

 So I had that pro of going to university。 What did I study。 I did a course called digital games。

 which is basically learned how to make games game development and stuff， which is pretty cool。

 It's very new here in Brazil。😊，But so the problem with this being new is that it's hard for the faculty to get professor professors with a lot of experience because there aren't a lot of people with experience here in Bel Z I mean。

 they are in Sano Paulo and maybe like。Potile egg， which is also a big。Technological city in Brazil。

 but aboutzo there aren't that many so it was hard for the university to get a lot of professors。

 so they kind of pulled professors from computer science from other areas that they don't know much about games so that suffered a bit but。

I really like to just sit down and do， so that's why I wasn't like 100% for a university。

But it was fun that I met a lot of people， a lot of cool professors， a lot of cool friends as well。

 so I think it was worth at least for the time that I spent there， which was two years I suppose。

Yeah。😊，So the idea for the two ball level now is that each ball tagged with the flag will recalculate its speed based on the position。

It is the position it is。The moment it changes its DPY to be down so that it will always take X seconds to go to the player。

 So the idea is。

![](img/fb0e7f46d547648aaa046497e55447ae_385.png)

Here here's the player and okay， let's say I hit the ball in a block here。It'll take。

 let's say one second。Lets take one second for the ball to go from here to here。

But let's say we hit the ball oh yeah， we hit the ball and then it hits here。

It will also take one second。To reach down here， so it will change its speed。So yeah。

 so it'd all just take fixed amount seconds y， because in the beginning。

 we can now spawn a ball that goes like this and a ball that goes like this。

And they will always offset。Between balls， so the player has to worry about the blue ball。

 then the orange ball， then the blue ball， then the orange ball。



![](img/fb0e7f46d547648aaa046497e55447ae_387.png)

I think they'll be a good solution。That's just right。

 So the first thing I'm going to play around is the flag。Right now， let's say flag。Yeah。

 we have the ball adjusted speed based on zero and one。

 let's take that out that was a really ugly hand。Let's do bow。fixedixed speed。See。

 that's way cleaner。 And we also get to fix that hack that we put in， see。😊，So I do do heavy things。

 but I do clean them up later on， so I think I can do keep doing heavy。So ball Ri A and ball。

Fixed speed。 What was that that we called。6。6。Okay。😊，Okay。Okay。Process ballwin D。

 if we are supposed to just be okay， if we are。Supposed to be。A fixed。Speak ball。Calculate。Se。对。第一批。

Sounds good so no need to do twice。Oh man， it's nice to just throw some code。

For for you to understand more of the program。And then when you do have more ideas。

 then you to go back and clean that up， that's always better， I really like it， okay。But this guy。

Should be fixed speak。And yeah， we also， yeah， there we are， calculate speed adjustment。So。

If we are going down， calculate the speed adjustment and this is what we're going to change。

Change this。Yeah。Okay， we can't do that。It are crazy。签几天。Let's put a comment。Or like employment。

Too few artem。 we don't need balls anymore。Doing。It's just。And。I't want to worry about that now。O。

Same thing。Pixed ball。speed？Well， fixed speed。Pretty cool。 Change this。I wasn't changed this。

 oh it wasn he that it's okay。Now。嗯。What we want to do is to see the distance to the player。

 so distance。2 players。Which is ball。TP， okay， so this， this is the player。 And we have like。Time。

To player， that's hard code that to one， Let's do two。And just as a note。

 when you're adding the music。Were going to make sure that the music matches this guy。In this case。

Because we do like the back， if we do like the main beat and the back beat。

 each one's going to be a ball， so you're going to like two two by and for every two you hit one ball and pi the other ball that was kind of stupid。

 but I think you guys got that point。I like doing like music。



![](img/fb0e7f46d547648aaa046497e55447ae_389.png)

Connected gameplay to see the。

![](img/fb0e7f46d547648aaa046497e55447ae_391.png)

The two handed pound game。That was pretty much like getting music together and I did a system where I pretty much did that。



![](img/fb0e7f46d547648aaa046497e55447ae_393.png)

You know， since three。Since we hadt get the game so much time now。

 let's see I had like the music BPM here。And yeah， I calculated the ball speed based on music DPM。

This is like。I subtract 60 to get seconds and four。To get the。Together cho notes。

And we reach the play field。啊。The amount I music。 But the problem in that case that didn't work 100%。

 and I didn't worry too much about it is that。In that game mode where the pedals get closer， hey， TV？

In that case where the pddles get closer。You change obviously right the speed。

 and I didn't want to think too much about that， it's kind of hacky。

But it was enough to get the feedback， but now I think in this case， when the speed is fixed。

 we can really get the music connected。I think that's going to be really cool and that really adds the game field kind of thing。

 so this is the player。Okay。And time to player， So I want to know the speed to get the player so it's going to be the distance。

Let's say if it's 10 units， yeah。If I divide that by the time。Let me just think。

I'm going to get five units per second， yeah that's correct。So。And then I'm going to divide that。

By the ball。That base speed， yeah base speed。And then I'm going to get the speed multiplied。

 so return this guy， I suppose that's it。Goon to go。Missing semicolon。Before ball。Yeah。Yeah。

 we didn't invite， thanks， Johnny， nice catch， man。呃。



![](img/fb0e7f46d547648aaa046497e55447ae_395.png)

Yeah， let's see calculate Peter。And just。Okay。Okay， now。Our base speed is 050 units。

Our distance to player is 84。 Does that make sense？Yeah， that makes sense。Now。This first divide here。

 this is dude， this is like really confusing this window。I just want to like the watch window。

The first divide is 42。It means that I need to move 42 units per second。To reach it in two seconds。

We are at 50 units per second。So if I divide this guy。Again。We got 0。84， so we need to get so lower。

In order to reach that sex and that looks pretty correct， I think。Yeah。Let's just see what happens。



![](img/fb0e7f46d547648aaa046497e55447ae_397.png)

Okay， this game。Let's see。So it's pretty slow， takes two seconds。This guy and this guy。

 iss pretty fast， it's pretty fast。Okay， it's not 100%。



![](img/fb0e7f46d547648aaa046497e55447ae_399.png)

Actually have to change the initial guide。Fixed speed， so can overs shoot。Speed。Yeah， in the stadium。

 the ball one。D p。Going to set the balls key。包括怎么样？B0。Just so you get a niceher， but one's going up。

 the other one's going down。

![](img/fb0e7f46d547648aaa046497e55447ae_401.png)

嗯。Okay， okay。So。At this point， obviously， they are already going to cross the center。

But that's the easy thing， right？And let's see if they take two seconds like one， two。one。2， yeah。

I think that's great。1。Yeah。But that's not 100% correct。What？😮，Did have that problem。

 I think we had that problem。嗯ん。

![](img/fb0e7f46d547648aaa046497e55447ae_403.png)

So if we die。Let's add that to the list。 So if we die。To low level。可以。To the house。Yeah。

 that's kind of super pleasant。

![](img/fb0e7f46d547648aaa046497e55447ae_405.png)

You have to do that。Okay， now if I drop the blue ball here。It should really be the same， right？



![](img/fb0e7f46d547648aaa046497e55447ae_407.png)

嗯。Yeah， it's not correct， let's go through this one more time just to make sure this is correct。Oh。

 first of all， let's see where we call it calculate speed adjustments。Whenever we process ball。

 when DP down。望？When D P down， we do that when we collide。With a block。You know why。Okay。

And with a wall， that looks correct。Let's go back， calculate。Yeah。

I don't need to comment that it's pretty evident if we are supposed to be should speed calculate speed adjustment。

Oh。Okay， that's the problem， we are multiplying that by the DP。Yeah。

 and I think we have to multiply that by the base speed。Like this。So if we are greater than zero。不是第。

F speak。

![](img/fb0e7f46d547648aaa046497e55447ae_409.png)

Yeah， because it was multi not sure， though。

![](img/fb0e7f46d547648aaa046497e55447ae_411.png)

啊，来 see。And you know what， just to be 100% correct， this shouldn't be。



![](img/fb0e7f46d547648aaa046497e55447ae_413.png)

Minus player P should be like。Plus， player to half size。



![](img/fb0e7f46d547648aaa046497e55447ae_415.png)

Just so we hit like both。Like。

![](img/fb0e7f46d547648aaa046497e55447ae_417.png)

Yeah。Just trying to get this correct the start。So instead of zero， this is going to be。Yeah。

 I suppose that's not important for now， but I want to make sure that in this case。



![](img/fb0e7f46d547648aaa046497e55447ae_419.png)

We hit the ball and the wall at the same time。So in this scenario。I don't think we gots low enough。

 see。We should be pretty clear， like。Should be。Orange first。 and then blue。嗯。

But we are getting slower。Whi is good， I suppose。Oh。No。

 I' not sure I' going to go step into the calculate。Speed here， so let's see oh we do that no。

 we don't do that。Let's see。So I'm calculating。Let's see， for the orange wall。Yeah。

 it's supposed to be the same thing at time to player  two， distance to player 82。

So we should have returned。

![](img/fb0e7f46d547648aaa046497e55447ae_421.png)

I'm going to call that result。Just so you can't have more easily see。The result。



![](img/fb0e7f46d547648aaa046497e55447ae_423.png)

A result。O。

![](img/fb0e7f46d547648aaa046497e55447ae_425.png)

Let's see。

![](img/fb0e7f46d547648aaa046497e55447ae_427.png)

Oh， the great point。电铺。

![](img/fb0e7f46d547648aaa046497e55447ae_429.png)

Let's that。Run in again。Okay， so the orange ball distance to player 82， the result is 0。82。Times 50。

Sounds right。Now。That's going to suck， I think。

![](img/fb0e7f46d547648aaa046497e55447ae_431.png)

你可以。嗯。You know what？嗯。I think I'm going to limit the mouseDp。Like。😊，One unit。Just。Yeah。

 I want to limit anyways。

![](img/fb0e7f46d547648aaa046497e55447ae_433.png)

But we're going to limit the player in the edge。So。

Just because we're doing like back and forth in the visual studio thing， okay。So in this case。

 82 looks good。Let's put that didn't help much。Okay， let's see the blue ball。82， yeah， okay。D啊。



![](img/fb0e7f46d547648aaa046497e55447ae_435.png)

Okay。Now let's try to do things more interestingly。

The orange ball should still be 82 and now the blue ball。Oh， this is going to be painted the bug。

That's just offset。This。Okay。Yeah， now I suppose we are the blue ball， let's see。Yes。

 here are the blueball。So the result is 0。37。Well， this looks correct。So if I multiply 50。

this by the result， as do。I painted the Dbug。Yeah。Result。Let's see 18 units for a second。

That looks pretty correct。Let's just believe。See。That's just no one let's just speed up。ができてで。Yeah。

 so in this first。电。😊，Apparently they are perfect， oh， they're not， they're moving down a bit。似。

He has appreciated him moving down。Yeses。Well， so they do have to start exactly in the middle。Well。

 yeah， they're moving up and down， so it's a little bit crazy。



![](img/fb0e7f46d547648aaa046497e55447ae_437.png)

Anyway， let's do it the right way。So what I want is the player five plus the player half side5。

 this is the start point。啊， minus。22是来时店。Sp to the arena。Have size。Why mine is this guy。Right。

 divided by two， let's do like。Okay， so this， I suppose， is the， let's say， middle point。喂。Middle 。5。

Player。H有。

![](img/fb0e7f46d547648aaa046497e55447ae_439.png)

Now let's see， well， that was wrong。

![](img/fb0e7f46d547648aaa046497e55447ae_441.png)

They're in a half size y。Which is not here。Minus。Player。Well， let me see exactly what this is。



![](img/fb0e7f46d547648aaa046497e55447ae_443.png)

5，62。嗯。Turned out to be 41。Yeah， that's not correct。Half size is 45， but player Y is minus 40。Oh。

 the verI is already negative， oh， but minus 40 minus 38。Oh yeah， okay that's weird。

 so that's the result。

![](img/fb0e7f46d547648aaa046497e55447ae_445.png)

Yes， there really should be plus。

![](img/fb0e7f46d547648aaa046497e55447ae_447.png)

来's起。😊。

![](img/fb0e7f46d547648aaa046497e55447ae_449.png)

Okay。That's cool。Okay， Ro， that was gone， I thought it worked。It did。For a little bit。

 maybe I have to take into account the involved。Size no， I don't think I don't。



![](img/fb0e7f46d547648aaa046497e55447ae_451.png)

嗯。😊。

![](img/fb0e7f46d547648aaa046497e55447ae_453.png)

Yeah。

![](img/fb0e7f46d547648aaa046497e55447ae_455.png)

Oh the first one definitely worked and the second one。

 I think were as well and third one definitely didn't。嗯。Yes， this is certainly wrong。



![](img/fb0e7f46d547648aaa046497e55447ae_457.png)

That they have the same speed， Well， they are supposed to because you know what。

 I think now that's a good point。To add a print messger to our engine really quickly。

Very bad one at first， but just so we can really like print their speed， things like that。

So I'm going to do。In a breakout code。I'm going to do a lot。操你卡手。加 see。And I'm going to have。For now。

 all I'm going to print is integerers。Just to make this safer life of message。

 I'm going to have like 64 in us a 32 integers。And let's do print and。ItTake an int。And have like。

Message。Okay， print in， it's called that number。哎。Turno white。 We could also take a color。But yeah。

 not your color。So this guy is going to be a strict。Message。P now it's going to be int。

It's called that value for value。And then a color。We should also add like a life。Or。

 not so worry about life for now。This is message。I have 32 messages and the current message。

And when we print， we're going to be like a message。Is messages。Plus， current。Message plus plus。

If current message is greater or equal than a array count。Messages。Current message is zero。

 so with a circular buffer， and we're going to do message。Well。E equal number。Message color。

Equals color。m going to do。Render。It'sCa that。是吧。Messages。

4 int I equals 0 int I less than rate count。Messages。I plus plus。关是只有message。

Message equals messages plus I。If message， well。We don't have。嗯。哎，是吧。Whatever。

 that's not print everything for now。Message， draw numbered。Message。Well。Right。Size。The draw number。

嗯。No the position is going to be， let's call it P。So P equals。Let's say minus arena half size X。

And minus arena。Half satisfied right。 So we're going to do like。A moldold V2 for arena half size。

And minus。O。So we have position and for every guy we need to like。Increase that。The size is2。2。5。

 so let's increase that by03。And they can also do like。2。5。And the call is the message color。



![](img/fb0e7f46d547648aaa046497e55447ae_459.png)

Okay， let's see if we got a bunch of say， oh， we have to include that all that on this。



![](img/fb0e7f46d547648aaa046497e55447ae_461.png)

Getting ahead of myself here。呃。Let's do that in the Windows platform layer。

South Raery now I'm going to include console。c。In the game。We are going to。是吧。Messages。

And you know what this going to be。For development only。Else。You create like a few macros。

Just what we call the compiler。 So draw。Messages。Okay。😊，And。Frint。Yeah。ok。

Arena have size on the find identifier， I think I about artcode that。I feeling like minus。-40 minus。

in- 16 minus 40。

![](img/fb0e7f46d547648aaa046497e55447ae_463.png)

な。

![](img/fb0e7f46d547648aaa046497e55447ae_465.png)

Okay， got a bunch of zero。Okay， well。He's kind of ugly。

But we just want to have we're going to improve on that a lot。But for now。

We're going to test Martha's idea and check if they do have the same speed。

When you do like simulate ball。Update calls。So we got the DP desired。PY。ああ。Yeah， well。

Let's print and。好。DP。And let's do， like。Oh。哇。Really， ugly agree。It just small one。

We're going to print that。Which is a rifle。A color。Okay。😊，Else， rival B color。

And then we do like all。Kunth convertt。Okay， this is the why they don't have to like。

Let's multiply that by。I know 100。对。It's not like accurate。This is just a way to visualize。

That more cleanly and then we're going to improve all that we're going to do a what we talked about last stream about doing like a print f。

 I would take floats and things like that。

![](img/fb0e7f46d547648aaa046497e55447ae_467.png)

![](img/fb0e7f46d547648aaa046497e55447ae_468.png)

Okay， youve added a number， was that negative？Yeah， I probably have to take the absolute。Do we have。

You have A BS app。Absolutely。In float。

![](img/fb0e7f46d547648aaa046497e55447ae_470.png)

Yeah， we do。 Okay， let's see。Okay。The speed is 50， it's good。Oh okay， yeah， let's just see the thing。

 speed is 50。And if you hit like the other ball， oh， I think that's the problem。

So that's a gameplay thing， not a cool thing， yeah。The further the ball is。

 the more multiplier it has， so it gets fast。Yeah， I think that's the problem or but we didn't hit the any ball。

 okay， you never mind， that is a problem but not D problem。So。诶。I'm not sure。



![](img/fb0e7f46d547648aaa046497e55447ae_472.png)

喂。Well， let me just。

![](img/fb0e7f46d547648aaa046497e55447ae_474.png)

S see。I'm not sure why one of them。I don't know why they fit flgged。Oh， because when we hit。

The player。It changes back。Not sure how I feel about that。主思 c。4。8。1 C+ presenting trend to use。

Not sure what you mean， dream VAP dotcom。Compiling C with MSV。

You know what should have been easy just is there just to print their velocity？

Instead of trying to do that。Council thing。But we are going to need that later on，嗯。So yeah。

 let's just keep going for a bit。

![](img/fb0e7f46d547648aaa046497e55447ae_476.png)

Yeah， you know what？Let's just see when we sat that to the base speed。

And maybe we won' to do that if we are a fixed people。So， okay。い， this guy。Rese and reverse。嗯。

See plus pleasure and not like。Yeah。I don't like。Much of it。嗯。Yeah， this is the problem I。好嘢。

I don't want to reset that。Okay， so if。Let's see， I'm not sure this going of be a good solution if the ball。

Is a ball of fixed speed。We just。Set the ball DPY。To-1。

Let me just see if there's any problem by doing that。We are also。Yeah。

I don't think there's a problem。I think I miss golf flag like every time I tad it。



![](img/fb0e7f46d547648aaa046497e55447ae_478.png)

Okay， let's if this game plays busted。Now， this looks pretty good。O。Now。Okay。This is not like。

Perfect。But I don't think it's like entirely bad。Right。Let's play around with this。Yeah。

 but it's really hard， it's really slow。This is like clean。嗯。

I think it really to drop that game most for now。What are you trying to do again， Well， we have this。

Game mode。Or this mechanic， I should say， but we have two balls。Where have to hit， you know。

Each one has to hit like。The one of the same color， so yeah。Well， you can see。

What it's about pretty much， right？

![](img/fb0e7f46d547648aaa046497e55447ae_480.png)

So we have we have to do away， this is all wrong。 we have to do away。

 so we don't have two balls hitting the player。

![](img/fb0e7f46d547648aaa046497e55447ae_482.png)

At the same time， we want always to be like one ball and one ball then one ball ball。

 we got a lot of problems like they they kick that， you know， they oh， we also have the problem of。

Yeah。So loans are short， see how are you supposed to fix that？Yeah， I think I'm just yeah。

 and the thing just to finish the answer。We were trying to figure out a way to have like two balls。

While being oh， that was pretty cool， I like the ball hit each other。

We were trying to find a way to make it reasonable for there to be two balls。In the play area。

Without being overwhelming to the player。See but。This is just。Weird。



![](img/fb0e7f46d547648aaa046497e55447ae_484.png)

So for now。I'm going to。Not sure I' going to delete that game mode， but I'm certainly going into。

I'm going to do the few paths before the clean up。 I'm going to comment that out， at least for now。

 so。We have like the arena。stadium。Stadium and the chest going to comment that out for now。嗯。

K know what I'm going to do like this after the count so it doesn't count。They don't count。

Illegal escapes is the art。So now we have bi game。Doude that participant was so bad。

That was like a really random thing。Let's now finish it。呃。Timer。At least a little bit。

When we set the print， we set the message。Timer。Let's do two seconds。Let's take out the color。

And then。If the message。Timer。Is。mar than zero。We do that。Let me do the message。

Timer minus equals Dt。Have to get the。Okay， then we draw。The message。I do them all。Just you like。

It's still white。Color。No need to pass call。What we need is a timer。So print end。Okay。Okay。

 this looks reasonable。 but now stuff printing like this， let's print。I don't know。 We have like。

What input do we have？Have left right， that's do like。那就 if。Frast。Butotton up。We printt。Take1。

Some reason。

![](img/fb0e7f46d547648aaa046497e55447ae_486.png)

Okay。

![](img/fb0e7f46d547648aaa046497e55447ae_488.png)

1010。Okay。😊。

![](img/fb0e7f46d547648aaa046497e55447ae_490.png)

Its kind of words。But we are printing all of them。Which is bad。If the message is greater than oh。

What did I do if it's。F's less than are equal to zero continue。



![](img/fb0e7f46d547648aaa046497e55447ae_492.png)

This type they didn't do anything。Okay， so we we got nothing， which is good now press up right。



![](img/fb0e7f46d547648aaa046497e55447ae_494.png)

Okay， pretty cool。 Now， let's do a。Let's do like a static。0。看。



![](img/fb0e7f46d547648aaa046497e55447ae_496.png)

![](img/fb0e7f46d547648aaa046497e55447ae_497.png)

技少。I think I'm just going to print the other way around， I'm going to start it。

Like 40 and do like minus three。

![](img/fb0e7f46d547648aaa046497e55447ae_499.png)

Okay， this is pretty cool。

![](img/fb0e7f46d547648aaa046497e55447ae_501.png)

Can now have a proper system printer。

![](img/fb0e7f46d547648aaa046497e55447ae_503.png)

Put that a little bit more on the side。买的。

![](img/fb0e7f46d547648aaa046497e55447ae_505.png)

嗯。Minus。Well， let's see what hearing have sites。诶。facts。Yeah，9。



![](img/fb0e7f46d547648aaa046497e55447ae_507.png)

Okay， so we have the print system。

![](img/fb0e7f46d547648aaa046497e55447ae_509.png)

But a very simple one， you're going to improve on that as time goes by。

 but now we can print stuff and that'll make it so much easier to debug。

And just to test things because I don't think we have ever done that。

Let's try compiling a non development build。Well， actually it works。Or maybe it doesn't。It works。

 okay。Nice， so we we take our asserts。Let's see if we do take out a search。Se 0。Perfect。

 now if you go back。

![](img/fb0e7f46d547648aaa046497e55447ae_511.png)

build。We should crash right off the。

![](img/fb0e7f46d547648aaa046497e55447ae_513.png)

We do。Nice。That was a familyary move。Yeah， we took out。The two ball level。So like maybe reconsider。2。

B levelss。I don't know， I think it's going to detract from the base game。A lot， so yeah。Hazards。

 block random spa。L of changes right every。We only to do that。If we decide to do that。

Just considered， I would leave the two ball left just considered it。 Yeah， but like。

Two balls without worrying too much about the speed。Because that's just frustrating。

 I mean you can spend like five minutes go like a perfect run and then for some random reason。

 you hit a ball。And then the speed changes right， or gets a little bit closer to you。

 and then them both hit you in different directions and it's just like impossible。It know。

 that's not a challenge to that。That just if you ready， right？I know if I were to lead that。

I will fix it， so for now let's not do it， but maybe you can go back and do this reconsided then。

Had a。Yes。And this thing is easier to do like hazards a block， we can do that， I think。

 a block that random response more blocks when killed。Spons more balls when killed。

Because we know this speed。Yeah。Yeah， I'm going to keep that as also it a too ball that okay。



![](img/fb0e7f46d547648aaa046497e55447ae_515.png)

So。We are almost done with our gameplay stuff we want to do。



![](img/fb0e7f46d547648aaa046497e55447ae_517.png)

And you know what， I think you're going to fix the wall。Going to make them a。Line up perfectly。

 so what I need is。

![](img/fb0e7f46d547648aaa046497e55447ae_519.png)

When we add a wall。Like this。Okay， if。We for every other role。If we are。X 0。Let's do block half size。

X half size。Like。Let's make it half。And in the other case， if x。It's Nax。卖错。



![](img/fb0e7f46d547648aaa046497e55447ae_521.png)

See， sometimes you shouldn't you shouldn't know chase。

 I don't allow that really or shouldn't chase like a challenge。



![](img/fb0e7f46d547648aaa046497e55447ae_523.png)

What did I do I shouldn' shouldn't？Should I have done this， I should made up like a block。

Havelf size okay， yeah sometimes no when we tried doing that。And there's been not a lot of time。

 but sometimes just hitting our head against that， and if it's not super important for the thing you're doing at the moment。

I just say ignore it and then come back like the mouse thing we did。

 we fixed the mouse today date pretty easily。

![](img/fb0e7f46d547648aaa046497e55447ae_525.png)

![](img/fb0e7f46d547648aaa046497e55447ae_526.png)

You know， I did ask the guys that he made network， right？But。

Sometimes not just worth spending a lot of time in something。

 maybe just want to clear your head and do something else because there are a lot of stuff to do。

 right？Okay， so。I think this is better。The left ones are correct。



![](img/fb0e7f46d547648aaa046497e55447ae_528.png)

But the right ones， I don't think they are。The left ones are these ones， so if x equals non x minus1。

That's a good break point here。

![](img/fb0e7f46d547648aaa046497e55447ae_530.png)

Because I don't know if 54，8， because I don't know if that's been triggered。Sorry that。気。Okay。

4 becomes。Two， okay， so it is be treated。Case of x equals 19。



![](img/fb0e7f46d547648aaa046497e55447ae_532.png)

I just don't。See it， I suppose。Let's make it like block。Relative。あ。Let's do this just。I you happy。

But。啊。And do like。Yeah。

![](img/fb0e7f46d547648aaa046497e55447ae_534.png)

![](img/fb0e7f46d547648aaa046497e55447ae_535.png)

Yeah， see I don't see them。Oh like。Let's make it times five。



![](img/fb0e7f46d547648aaa046497e55447ae_537.png)

I don't know。Where they are。Blocks。

![](img/fb0e7f46d547648aaa046497e55447ae_539.png)

I don't know， man。Let's just review quickly this one looks good okay， so if we are。In even roles。

 right。We should zero out the first guy。I's just remove this。



![](img/fb0e7f46d547648aaa046497e55447ae_541.png)

Let's just see。Well， let's go back and see everything， so this is the original problem。

 not problem like condition。

![](img/fb0e7f46d547648aaa046497e55447ae_543.png)

C。😊，What do you want to do？Is fix those left most blocks， so it looks like a perfect wall。



![](img/fb0e7f46d547648aaa046497e55447ae_545.png)

给。😊，The first thing is to check out these。

![](img/fb0e7f46d547648aaa046497e55447ae_547.png)

That looks pretty good to me， so we also want to move them。



![](img/fb0e7f46d547648aaa046497e55447ae_549.png)

Yeah， I think I'm going to do that， I'm not sure。Oh， okay， no， let's add like an now X。

I don't know what I was doing。X offset。X offset。Plus， equals。



![](img/fb0e7f46d547648aaa046497e55447ae_551.png)

Okay， now let's see what that。

![](img/fb0e7f46d547648aaa046497e55447ae_553.png)

Oh， that that was wrong， wasn't it？We didn't even use the X。 Oh， we do have an Excel。

 dude this is be a warning or not。 Oh yeah。We should really do like。

Warning is theirs and all warnings。Yeah。😊，哇，一次。Non standardard。Nameless Okay， this I don't care。

 So I'm going do like a。Let's do。 Let's see how。I do。I just set warning student earlier。

 I'm going to do that。And then I do warnings。です。Just want to check out the。Just want to see the。

Syntax for these guys。 So I' going to ignore。4201。Its minus W D， yeah。And this name here。

 I'm going to。Se that the wire strip。A non constant aggregate initializer。Should that be a problem？

I don't think so。I don't see why that should be a problem。Random function prototype converting to F。

I don't know why that should be a problem。Okay， it's not defined as a pre processingces macro， Well。

 that wasn't my problem was it。啊。Replacing zero for。Yeah。

 I think that's not a problem either so please。Oh， maybe I have to fix all of windowses。No okay。

Un namedd tag4 bys petting after Data member Binap E。你看。😊，Padding does happen， so 48。Yeah。

 name I should do and stuff， yeah that's go。Equal conversion from bo。Fraasft 32。Day speed is a goal。

It is。这解。Conversion from in to U8。Yeah， this I just cast。Dividing that light。Oh， that's boring， man。

 taking all those hours。De， okay， so this is what we wanted this warning I was complaining about the warnings earlier because I hadn't turned them as errorss。

 so Axon said。Hi， it's pre your local declaration。So。Should we call that。啊。X。啊塞。Yeah。So， plus。Or这。

这 same thing。You wait here。You wait here。Cant convert from int。32。Local variable。On version from32。

Oh， there the clamp。Let's do a clamp path。啊。Yeah。Cl。Let's do internal F32 clamp。

You better didn't add that comper flag。It's been in the long term， I should have added that before。

 I suppose， so these problems didn't pile up。😊，But。Yeah， let's see if we got a lot of errors。

 let's see。😊，Now we don't。We are almost done。 I thought I honestly thought that was going to be like。

All of them as competitors。But yeah， this's going to be good man this kind of。

These kind of bugs like。Oh， you're overriding a global variable those are annoying。

 so I might as well just。Lets have that as a warning as an error suppose。嗯。

Coversion from double to F 32。Here， I suppose。Yeah， this warning stupid， I mean。

 it's not 100% stupid， but since we have to take these parameters。I might as well not use them。

 right？Was down？Yeah， I'm also going to take that parameter。That weren't anyway， so 4189。

And we're done， okay。Thatice。But what we want to change is the。X board set， right game。



![](img/fb0e7f46d547648aaa046497e55447ae_555.png)

Ex orderer offset， okay。Let's see how our guy looks。Now。H。Isn't that nice？Dude， that's awesome。

That's really cool。But honestly。I'm not going to do that yet because I want to see。

 I think I go to that for the same role。

![](img/fb0e7f46d547648aaa046497e55447ae_557.png)

Yeah， no， the other world so。This is。Correct in theory。Same thing here。

But I'm going to do if x is equal to this guy。Right。

I make it smaller and then this one's going to be like mine hand。Then I also have to。At the。我这。



![](img/fb0e7f46d547648aaa046497e55447ae_559.png)

Yes。Okay。See， I'm not sure why that isn't working。

![](img/fb0e7f46d547648aaa046497e55447ae_561.png)

You see that。

![](img/fb0e7f46d547648aaa046497e55447ae_563.png)

It ended up in the middle or good， at least now we know where it is。嗯。

That was weird plus what offset where offset starts off at zero。

And then we do like it minus half the block size。

![](img/fb0e7f46d547648aaa046497e55447ae_565.png)

Which should be pretty small。 Let's just see。If we don't do that。



![](img/fb0e7f46d547648aaa046497e55447ae_567.png)

![](img/fb0e7f46d547648aaa046497e55447ae_568.png)

嗯。哦。Yeah， so this guy should be times two。Because we are adding about half the block size here。

But in this case， the last guy the half block size。Yeah。I'm going to do it。This case。

 I'm going know this guy。あです。Else。Yeah， the problem was since we are offsetting them by， oh。

 we're also doing here。 Oh， but this is the first one。 So it should be zero。 Yeah。

 since we are offsetting。We're moving him to the site by this guy。We can't。

We can't we can also do that before。Yeah， I think I'm going to do that， okay， so first of all。

 I move them to the correct position。Yeah， that's going to be cleaner。Then I set the block half size。

And。The block relative P dot X， I offset that。ないですか。Okay。😊，Now this same thing， but I add this guy。

Oh， it's gonna do。 Yes way clean。Okay， looks good。

![](img/fb0e7f46d547648aaa046497e55447ae_570.png)

That' see。Okay。

![](img/fb0e7f46d547648aaa046497e55447ae_572.png)

Not 100%。I should say。

![](img/fb0e7f46d547648aaa046497e55447ae_574.png)

Let's see， probably maybe we got that。Is this right so what？



![](img/fb0e7f46d547648aaa046497e55447ae_576.png)

Okay， yeah， because we're not oh。Okay， so if we are this guy。We have。To do this。



![](img/fb0e7f46d547648aaa046497e55447ae_578.png)

Let's see。

![](img/fb0e7f46d547648aaa046497e55447ae_580.png)

Let's not do。Okay， I want to see like the normal wall， and then we can start playing around with it。



![](img/fb0e7f46d547648aaa046497e55447ae_582.png)

啊。

![](img/fb0e7f46d547648aaa046497e55447ae_584.png)

Okay， I suppose this is correct， they start offset by one guy。Yeah， this is correct。Nice。

Doude the comment is awesome now。是。It's like crazy。Oh， trap， I float。



![](img/fb0e7f46d547648aaa046497e55447ae_586.png)

嗯。自たちたち。う。Okay， now all I have to do now is in the first row。呃。In the first row。



![](img/fb0e7f46d547648aaa046497e55447ae_588.png)

To do this。

![](img/fb0e7f46d547648aaa046497e55447ae_590.png)

No， wait。回来。😊，Oh， it wasn't the else。So it wasn't changing the last one。

 so the last one's probably wrong。

![](img/fb0e7f46d547648aaa046497e55447ae_592.png)

If I do it like。Yeah， you know what？This correct， that didn't make sense， this is correct。

But now I can add that to the block half size。Okay， now。Now I'm going to make。



![](img/fb0e7f46d547648aaa046497e55447ae_594.png)

This guy， smaller。And remove that。

![](img/fb0e7f46d547648aaa046497e55447ae_596.png)

嗯。😊，Can not。那就。First。Dude。We we have too many yet。好， not sure。Maybe do have a little bit too。

Are not of cool guys。

![](img/fb0e7f46d547648aaa046497e55447ae_598.png)

Okay， you should block the player for next in this one， yeah， I'm going to do that。

 but I wanted to do that as an animation thing so this is the screen and this is a player。



![](img/fb0e7f46d547648aaa046497e55447ae_600.png)

If the player moves a lot like this， I want， I want it to be like。Like this， you know， like。

Like squashed against the screen。I this normal player。



![](img/fb0e7f46d547648aaa046497e55447ae_602.png)

Just to do the visual interest， so we are going to do that。



![](img/fb0e7f46d547648aaa046497e55447ae_604.png)

When we do this question stretching， which is the next task。



![](img/fb0e7f46d547648aaa046497e55447ae_606.png)

Yeah， it's going to be really really cool man， I love doing like animation things because they you know they changed the game completely。

 but I want to make sure the games fun before we do that because that can be really misleading and we talked about that way before actually we did this thing。

We have played。A couple of different breakout games。And。Including that from that lecture。

 I believe it was Dan that gave me the link that lecture with all the crazy breakout things going on。

 it's called a Ju or Lucit。So they do like over the top Juness。And we want to do that， well。

That much， but I want you to do something like that。

 but before we do that we want to make sure the gameplay is nice and fu so that's why we're doing this initial gameplay before I start doing cool stuff with that。

Okay， and the showtimers thing is going to be like RPG things I think this is going to be cool。Okay。

 so。

![](img/fb0e7f46d547648aaa046497e55447ae_608.png)

呃。Actually， I just forgot what we' were doing， oh we are we finishing the wall thing。

 I've taken a long of time to this right， but things don't。



![](img/fb0e7f46d547648aaa046497e55447ae_610.png)

![](img/fb0e7f46d547648aaa046497e55447ae_611.png)

So yeah， these guys are a bit weird， let's just make sure。Let's just make sure it makes sense。

Like this。Were going to remove。All of these modplifiers。



![](img/fb0e7f46d547648aaa046497e55447ae_613.png)

Yeah。

![](img/fb0e7f46d547648aaa046497e55447ae_615.png)

Okay， so this is a normal wall。And then I'm going to do like the first block is going to be smaller at see。



![](img/fb0e7f46d547648aaa046497e55447ae_617.png)

Okay， then I'm going to move that by half to the right。



![](img/fb0e7f46d547648aaa046497e55447ae_619.png)

![](img/fb0e7f46d547648aaa046497e55447ae_620.png)

Yeah， by adding text button。So this looks correct。 Now the other one， let's make that block smaller。



![](img/fb0e7f46d547648aaa046497e55447ae_622.png)

![](img/fb0e7f46d547648aaa046497e55447ae_623.png)

W are the other blocks。Oh， that was it。

![](img/fb0e7f46d547648aaa046497e55447ae_625.png)

The position is already correct。Nice。Nice， that was easy。Let's do like this。Okay， now let's add。



![](img/fb0e7f46d547648aaa046497e55447ae_627.png)

Two more blocks or one more black。

![](img/fb0e7f46d547648aaa046497e55447ae_629.png)

Yeah， two or too much lets do。抓。

![](img/fb0e7f46d547648aaa046497e55447ae_631.png)

Yeah， maybe I have to make it a little bit bigger because maybe we can stick that ball there and then it's going to be。

Well， maybe if you manage to the ball there， we deserve。We deserve that of crazy thing that。Dude。

 this is so cool。So now I think the gameplay is interesting， really。

Like first we have normal breakout then got。Break out on steroids， which is。呃。This guy。Okay。

 yeah he did that。Yeah。This is pretty cool after that。Yeah， I have to avoid all of these guyss。Okay。

 yeah。Okay， pretty cool now then have Palm。Pong's awesome， I think。At least in terms of。Ts of idea。

 right？And it's not really that hard because once they start dropping like crazy， I mean。

 the power downs。All I have to do is like。Calling to the out way now what we should do。

I think we're going to do that now is add a time reward for the blogs as well for the。For the， well。

 it also fix the collision， yeah I'm going to do that first。

So fix the collision and then add a core multiplier， let's say for the first。好一次。

The longer you take the less points you you make， I don't know now that kind of seems to punch Yeah。

 let's just fix the collision and then after pond， which is pretty cool。We got spa invaders。

 this one and think also great。 dinner can do more later on can do Tes。

 I want to do like donkey Kong and then maybe Super Mario and then you guys can have more ideas like what old games would feel good in this breakout。

😊，Crazy idea， thing。That could be pretty interesting。ok。😊，Yeah， I think。We are getting somewhere。

Okay。Pretty cool。Now let's just fix the p collision。Let's see if we do like this。Yeah。

 see how the collectionians are Do those。 It was awesome when you managed to get the ball behind him。

SoDe。 Yeah， so we already got more points for that， so。I suppose。Okay， yeah。

 then we revertted the controls。哼可以。Yeah， that fixeds the collision。



![](img/fb0e7f46d547648aaa046497e55447ae_633.png)

I think it's doing that in pound。Simulate level。So if the desired P。

It' greaterquaer than the arena half size P minus。Well。

 they should be correct unless we are computing the enemy have size x wrong。

 which we might as well be doing， might as well in the sense that maybe we are those。嗯。Yeah。

 let's put a breakpoint here just check out the values6， eight。



![](img/fb0e7f46d547648aaa046497e55447ae_635.png)

681。是。Yeah， let's see the first time we play like this。嗯。You haveer in a size。

The plum cap size is 16。4。As if that makes sense， the desired p is0。



![](img/fb0e7f46d547648aaa046497e55447ae_637.png)

So Pong enemy。Half size。So it's eight。Oh， because we changed that。 See。

 that's where hard code is stuff dude。 That's not hard code。 that。 Let's do like numb X。And numb。

Hard coding。Pretty much点 you。Scred that later on。It wasn't that hard of a bug to fix。Noumb X。



![](img/fb0e7f46d547648aaa046497e55447ae_639.png)

Well， the space is hard coded。I don't think I'm going to change that。Thats pretty nice I。Let's see。

Dude， this is pretty cool。Let's try again colliding。Well。T should just be。就し。

Do knowledge hard test the collision。

![](img/fb0e7f46d547648aaa046497e55447ae_641.png)

Just going to add strong blocks。That's your like strong blocks。 Let's add that to like。



![](img/fb0e7f46d547648aaa046497e55447ae_643.png)

Just so we can test。

![](img/fb0e7f46d547648aaa046497e55447ae_645.png)

は。Dude， okay。And I do like this do it slowly。Slowly， slowly， oh crap。It's not so slow。C。Oh。

 maybe it already collided。嗯。

![](img/fb0e7f46d547648aaa046497e55447ae_647.png)

Yeah。So it's wrong。It's wrong。Now it's。Yeah。So。Yes。And have size， and number。Oh。

Half size the number x。Times two for the satinella it's 1。5， do it again。



![](img/fb0e7f46d547648aaa046497e55447ae_649.png)

All of this hard coding stuff。Because we changed that。



![](img/fb0e7f46d547648aaa046497e55447ae_651.png)

To make them look more like this， which I think was a great call because I think it's pretty much perfect。

Okay， so it's not quite but close。

![](img/fb0e7f46d547648aaa046497e55447ae_653.png)

It's nice to ricoochet off the wall。So it's one point。F， which is the size。Plus 0。5。

 which is the spacing。 I suppose I should remove 0。05 because spacing only happens in one side。



![](img/fb0e7f46d547648aaa046497e55447ae_655.png)

This is not like 10%。I'm not 100% sure at this point。Let's see。I think that was wrong， actually。Oh。

 no。

![](img/fb0e7f46d547648aaa046497e55447ae_657.png)

诶。Let's just keep hacking it until you find out the value and then can understand that。



![](img/fb0e7f46d547648aaa046497e55447ae_659.png)

Just because it's kind of confusing at this point。第五题。Okay， so this is turned not。



![](img/fb0e7f46d547648aaa046497e55447ae_661.png)

Correct。1 or five。Let's just check out。The parameters。For。Or create。L like。So。I'm Al for today。

 wish you good stream， thank you Moreus， was nice to see you here， man。Number X12。

Number one doesn't matter's spacing。Maybe you shouldt remove the spacing just make sure。Okay。

 X offset 0， Y offset doesn't matter。Block half size。It should be 1。5 this。

Based on speed multiply doesn't matter， right or it doesn't matter。Yeah。

 we're going to remove rivalry， I think。It's a cool idea and concept。

 but that's not what the games about。Yeah， let's remove。



![](img/fb0e7f46d547648aaa046497e55447ae_663.png)

Let's remove the spacing。

![](img/fb0e7f46d547648aaa046497e55447ae_665.png)

Just to see if you get the correct result， we should have a better way of testing this。

But head around。Well， it's not， it's not。It's not a bad thing to have him with no space in it。Yeah。

 see。 this is perfect。

![](img/fb0e7f46d547648aaa046497e55447ae_667.png)

But the problem is the space。Let's go back。To create。哇。对吧。And see the spacing。

Is used in the X offset。Which is the number， yeah， maybe that was the problem。

AndThen here is the two。哦。Yeah， the number X。Oh， we we didn't multiply by two because yeah， okay。

Yeah， I thought that was the problem， but if you do this， it's like one whole guy。

Park and it it's the same thing as doing this。Yeah。So this is what we're focusing。Wud。But problem。

 I think the problem is the offset， maybe。

![](img/fb0e7f46d547648aaa046497e55447ae_669.png)

And I'll try remove the offset later。Well， we can't really it。Let's just see actually oh。

 but it's pretty， pretty standard so that's not the problem。



![](img/fb0e7f46d547648aaa046497e55447ae_671.png)

Do want move the tro blocks？

![](img/fb0e7f46d547648aaa046497e55447ae_673.png)

No， we didn't。Why wasn't the box strong？唔' see。Okay， now there's wrong。次。嗯。

That was really wrong for some reason。

![](img/fb0e7f46d547648aaa046497e55447ae_675.png)

Oh， because we died， that's why lot of women strong。



![](img/fb0e7f46d547648aaa046497e55447ae_677.png)

Why did that suddenly stop working？1。5， which is the size times this spacing。

 I think this guy has to be times2。

![](img/fb0e7f46d547648aaa046497e55447ae_679.png)

Anyways。Times half because it's half size。嗯。

![](img/fb0e7f46d547648aaa046497e55447ae_681.png)

Yes。That's funny。Dude， I want to fix this。Anmy half size。Oh。Oh yeah， no。

 I think we are considering the have size but， let's just re through the other code enemy。Half size。

So if it's greater than the arena half size。X minus。Ennemy。This is correct。Assuming the values。So。

Number of blocks。Yeah。Times the size of the blocks plus spacing。Times 2。啊。This。😊。

Let's review it one more time here I'm getting tired。blah， bh， yeah， those。

 this can be the kind of thing that I just said in the beginning that not in the beginning。

Some like maybe it's not worth banging our heads against this for some time。Yeah。

 the offset considers that times two， so does this guy， so if we are going to multip that by half。

It's got to be like。

![](img/fb0e7f46d547648aaa046497e55447ae_683.png)

Which is twice。嗯。

![](img/fb0e7f46d547648aaa046497e55447ae_685.png)

totallytally wrong。Let's try getting it back to zero。Anmy half size， right， number x times。

The size divided by two。

![](img/fb0e7f46d547648aaa046497e55447ae_687.png)

Yeah， sometimes you just have to de by line。

![](img/fb0e7f46d547648aaa046497e55447ae_689.png)

udeWhat do we change here， I me go back like a lot。We didn't divide by two。The enemy half size。Okay。

 dude， that was super stupid because this is already the half size。O。



![](img/fb0e7f46d547648aaa046497e55447ae_691.png)

Now we're getting。そうです。Is the number of blocks times the half size for each block gives us。



![](img/fb0e7f46d547648aaa046497e55447ae_693.png)

The half size for all the blocks that's right now， let's see how the spacing comes in。Yeah。



![](img/fb0e7f46d547648aaa046497e55447ae_695.png)

Now， space。I're going to add 0。5 of spacecing these guys。



![](img/fb0e7f46d547648aaa046497e55447ae_697.png)

I suppose I can do just that。

![](img/fb0e7f46d547648aaa046497e55447ae_699.png)

Maybe offset by the spacing for each side， like the left side and the right side， let' see。OkayOkay。

 let's see。 oh my god。Whenever I don't want to win， I win whenever I。没有。Okay。佢感急。Okay。

 I think that was perfect。为什很气。

![](img/fb0e7f46d547648aaa046497e55447ae_701.png)

是。See， oh， not Yeah， Not quite perfect， but I think I can it's because of the。



![](img/fb0e7f46d547648aaa046497e55447ae_703.png)

![](img/fb0e7f46d547648aaa046497e55447ae_704.png)

Thisho's the last guy。So one of them don't have this guy。

Which I can get really close to the screen just make maybe I should do like a slow motion。嗯。

AndI was still not correct。Still not。

![](img/fb0e7f46d547648aaa046497e55447ae_706.png)

Gett it called oh， I subtract。

![](img/fb0e7f46d547648aaa046497e55447ae_708.png)

Yeah。Have to add that。Let's see。 oh， my god。Okay， since we already in this side。

 Oh now you' are in this side。Okay。

![](img/fb0e7f46d547648aaa046497e55447ae_710.png)

Let's see。 see。Okay。

![](img/fb0e7f46d547648aaa046497e55447ae_712.png)

Yeah呀。I don't know。I just keep adding like I can keep adding random numbers， but。



![](img/fb0e7f46d547648aaa046497e55447ae_714.png)

This is like my last ride because it's like the half size times two， the spacing times two。

 but I think。It worked。That was a weird collision。AD。Almost。I almost manage to see it。

It's like not 100%。Yeah， not 100%。あ。

![](img/fb0e7f46d547648aaa046497e55447ae_716.png)

嗯。

![](img/fb0e7f46d547648aaa046497e55447ae_718.png)

Let's。Try adding like，2。Times good， I don't know why three。



![](img/fb0e7f46d547648aaa046497e55447ae_720.png)

I don't know why two would be on a decent number either， but let's try two。Yeah， maybe it's two。

Then I can just make sure the spacing is really the point。ていうかま。



![](img/fb0e7f46d547648aaa046497e55447ae_722.png)

No， it's not 100%。So if I again， if I remove the spacing。This works。Yeah。

 the problem here is the offset， so the offset is two。Oh， yes， two plus spacecing intensity。嗯。😊。

I suppose this is hard coded， like the size。Block half size。Block have oh， no， no， Okay。

 so block have size。Block have size。Times the spacing。Spaccing。

 I'm going to comment that the spacing is relative。So。Times。I should call it like。Yeah。



![](img/fb0e7f46d547648aaa046497e55447ae_724.png)

Okay， now it makes more sense。I'm going to review the game in just a while。 Let's just see。

 I think this is going to work。 Sometimes you do have to， you know。Spend some time。

Really understanding our program， yeah， I think that was perfect。Yeah。

 and then you can like comment and do more so， okay， this is perfect let's do one more time。



![](img/fb0e7f46d547648aaa046497e55447ae_726.png)

Yeah。Okay， let's remove this trunk box。呃。

![](img/fb0e7f46d547648aaa046497e55447ae_728.png)

At this point。We have a， first of all， a breakout game。Okay。Okay， not too fancy。Then。

We have a more interesting break count game。Let's see。With power ups。嚟。😊，Having more than one ball。

And。Having your ball go through the blocks。And you also have power downs。That blog right there。

Red block。I definitely don't want to get that。Depends on what it does， really。

 some of them are like things to kill but then our other。So yeah， that's really cool。

We also added scores part of the game， starting system。ok。see what else you got。

So that's the more interesting breakout version， okay？And then we added a P breakout version。死。😊。

So now we are playing。Palm inside breakout， that was one of the。Das ideas for the game。

 So this was like。The games about you playing breakout in different。Old acade games。

So that's prong dude that was pretty cool， yeah， I got the strength。So that's fun。Let's just。Yeah。

 see so we guys。It has powered down as well。Okay， yeah， nice。Okay。

 and then we have spa invade invaders。And it's pretty cool because they move like kind of fast。

And you really want to kill the first guys first。So I think I got this spirit across of space invadevaers。

Inside breakout。You know what， maybe they should shoot power downs， that was the original plan。

 but that's hard enough without them shooting power down， so I don't think I'm going to add that。

They already have like power ups。That's pretty cool。You know what。

 maybe I should change the color of the secondary balls。Yeah。



![](img/fb0e7f46d547648aaa046497e55447ae_730.png)

And we're going to do that pretty quickly。And then that's it for this stream。



![](img/fb0e7f46d547648aaa046497e55447ae_732.png)

At block life， I don't think I'm going to do with that。Here at。B life。Review two ball levels。

And I do that on the second gameplay exploration。嗯。But in LBlock life， we're going to do that later。

 create more levels， I think we created enough levels。So initial gameplay， done。Next time around。

 we're going to start doing some fuel passs， so we're going to improve the gain fuel。Like the colors。

 squashing stretching。Show timers。Maybe like shake the screen a little bit。W。Skin shakeake。What else？

Like make the walls smooth。And like。😊，Ball trail。Particle system。 Yeah， let's do that。

And then we're going to do the engine improvements， maybe you can like do rotator racks first。

For audio and thready。Then you're going to do audio threading then bitmaps and particles。

 it's going to be a more elaborate by gameplay thing menu and file IO。Saving and loading。

 saving and unlock levels and high scores， okay。They're going to do more gamely。

 if that looks like a plan。I think I'm going to do like really quickly the three。

 oh maybe I should do like。Yeah， color。You can start with that。3。Bob color。Squash and stretching。

 show timers， yeah。I think you can start with the three ball color。So that is it for this stream。



![](img/fb0e7f46d547648aaa046497e55447ae_734.png)

If you want to download the game and the source code for free for you to play around with。

 you can go on my HI page， which is dzd。h。io， you can click on this first game here。



![](img/fb0e7f46d547648aaa046497e55447ae_736.png)

And yeah， you can download each episode's executable and the source code。

So you can see from the very first episode which we didn't have much。

 we only have the like platform layer and for all the things we are adding in terms of gameplay in terms of systems。



![](img/fb0e7f46d547648aaa046497e55447ae_738.png)

Which is pretty cool。If you missed any stream， you can come to my YouTube channel。

 which is ddan YouTubetube。com/danzadan。And then you can watch every episode and see every line of code being typed into the game。

 we didn't use any libraries at least for now。Any libraries， so you understand everything。



![](img/fb0e7f46d547648aaa046497e55447ae_740.png)

And。That's it and just if you want to come here and download now you're welcome to give me a tip。

 I received a pretty nice tip last time around。

![](img/fb0e7f46d547648aaa046497e55447ae_742.png)

So thank you for whoever did that。And if you want to tip knee， you can also do this。

 but you can also just click no thanks， take to the downloads and just download here。



![](img/fb0e7f46d547648aaa046497e55447ae_744.png)

![](img/fb0e7f46d547648aaa046497e55447ae_745.png)

So that's it， I hope you have enjoyed this stream。And。Okay。I don't know what happened。

Is that a bug like？嗯。Yeah。Yeah， we can pretty easily access the screen。I'm going to fix that。Yeah啊好。

You know what， it seems。Seems like this guy is more sensitive than this guy。什么意思？Oh。

 I think I think it's just my mouse， no， it's not， it's pretty weird dude。Okay。

 so maybe we're going to start with some debugging next time。

I can just try to understand this bug because this is weird。Yeah。Definitely something wrong here。

You know what， Let's try not locking in my mouse。

![](img/fb0e7f46d547648aaa046497e55447ae_747.png)

Sorry because I just found a bug。I want to just try to understand what's wrong with maybe so just so I can like at least。

G me a hint next time around。I was about to close this screen but well。



![](img/fb0e7f46d547648aaa046497e55447ae_749.png)

Just went out of water。So so we didn't actually stop locking the mouse。



![](img/fb0e7f46d547648aaa046497e55447ae_751.png)

你人拉。

![](img/fb0e7f46d547648aaa046497e55447ae_753.png)

2。Okay， yeah， now this is not actually supposed to work。



![](img/fb0e7f46d547648aaa046497e55447ae_755.png)

Because we are getting the mouse the center position。I wasn't really feeling that。



![](img/fb0e7f46d547648aaa046497e55447ae_757.png)

Until like the very end。 but it's definitely。I don't。No。



![](img/fb0e7f46d547648aaa046497e55447ae_759.png)

You know what I'm going to do， I'm going to draw a cursory。



![](img/fb0e7f46d547648aaa046497e55447ae_761.png)

No有。I think I'm going to just make a note for next time。

 I don't think we're going to start with that。But。I don't know。



![](img/fb0e7f46d547648aaa046497e55447ae_763.png)

Let's use the print to help with out。 Let's， let's do that。 So mouse D P， let's print the mouse D P。

Let's bring the speed to my head。Pri。Speed multiplier。Times that。Yeah， let's use flow from in。

I meant， yeah。

![](img/fb0e7f46d547648aaa046497e55447ae_765.png)

Let's just see if you understand this problem。

![](img/fb0e7f46d547648aaa046497e55447ae_767.png)

So。0ero， for some reason。嗯。😊。

![](img/fb0e7f46d547648aaa046497e55447ae_769.png)

Why is this big multiplifierier is zero？

![](img/fb0e7f46d547648aaa046497e55447ae_771.png)

Oh， it's 100 really， but we don't see it。Okay， so that's just。Let's just fix that。



![](img/fb0e7f46d547648aaa046497e55447ae_773.png)

That's too like minus-89。You see the one， if it's my deadline。



![](img/fb0e7f46d547648aaa046497e55447ae_775.png)

Yeah， I can， okay。Okay， so。See， now， I don't know。 Okay， so this is not the problem。



![](img/fb0e7f46d547648aaa046497e55447ae_777.png)

Let's try seeing this guy。 should really。Oh。That's stupid， we just hack this really really quickly。

Wow， that was so stupid just so you couldn't like do a lot of crazy stuff for some reason。

But if we are supposed to do that， we should really cap that to the night of like min1 and minus1。

 max minus1。But we don't want to do that。So yeah， that was just stupid code。



![](img/fb0e7f46d547648aaa046497e55447ae_779.png)

Yeah。😊，So we werecaping that， okay。Wellow， now it feels really different， but really better。

 this is like exactly what we want。Yeah。Well now it really feels for you。Yeah。Okay。

 so well solve that bug。Just left over code。Because we kind wanted a hack not going extremely crazy。

Because we don't have like amorphous yet we don't have。A limiter for the。At position yet。

You'll see this point racking up。Let's break out。Yeah， we don't have a limiter。所。

I that's really crazy。Yeah。Okay。I's just run this level， just so we can hand in a high note。Yeah。

 and I can get like a lot of points to。あもしますね。我。But I do have one extra line。So。Yeah。

 that's got more points， more points。Okay。Okay。Yeah， I'm going to try not to mess this up。Okay。Okay。

 nice。 let's block。Let's go as slow as to be。Okay。Oh， and the points don't get reset。

I don't think this is a bad idea， but we're not going to be after the final game。But for now。

It's kind of cool。Yes。Yeah。Dudeude。That was points。Okay， I don't know all got strong box。

That's like the least of our problems， traumas。Do you。Yeah。



![](img/fb0e7f46d547648aaa046497e55447ae_781.png)

Maybe life should just just the last thing of today today， random choice。P down。

 this is the wall right yeah， that's do like a little bit more。Last week。 Okay。

 so I hope you enjoyed this live stream。 I certainly did。 We did a lot of stuff。

 The game plays way better。 We have to take the time to fix the things we create， right。

 So next time around， we're going to focus on the game feel。😊。

Then we're going to do a little bit more of a cleanup， both in the code and the structure。

 maybe going to。Maybe we're going to destroy the idea of the rivals and to want to take that back to go back and add them。

 but I don't think we're going to do that。嗯。And maybe the life system， yeah。Okay。

 I hope you enjoyed it again， check out the YouTube channel with all the episode and check out the HIO for the source code。



![](img/fb0e7f46d547648aaa046497e55447ae_783.png)

Okay， I'll see you guys next time， thanks for watching。



![](img/fb0e7f46d547648aaa046497e55447ae_785.png)