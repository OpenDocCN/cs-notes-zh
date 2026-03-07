# 【从零开始用C语言制作游戏】 p17 Making a game in C from scratch! Ep 17： -Gameplay Improvements： Ani -BV18i421a7DD_p17-

Hello everyone， welcome to this new live stream where I'm creating an entire game in from scratch。

 if you have been following along， you saw the game progress all the way from nothing。

To where we are now and we are we have been creating a lot of cool stuff in the game last episode we optimized the renderer was a crazy episode was like four and a half hours or something。

 Yeah， four hours and 22 minutes。😊，We managed to get the game running in 4K from 16 minutes length per frame all the way to 16。

Milliseconds per frame actually got a little bit lower than that。

That was a cool challenge now we are safe to go back to gameplay programming and maybe expand the levels a bit and improve the overall field of the game。

Okay， now if you go here to the HIO page and I have some cooludos for you in a second。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_2.png)

You can download the game and the source code for free， just click here。

And then you can download every day， a very different episode of the live stream。

 you can download that separately sorry from the first day。



![](img/d4175b7c7da94dffbf39910f5457f6a6_4.png)

And then when you click download now， you're going to give me a tip and I got to say I have received a couple of a very generous tips。

So I thank you for that。AndBut if you just take no thanks， you can just download the game。

 but if you want to help me out， you can also help by sharing the videos。



![](img/d4175b7c7da94dffbf39910f5457f6a6_6.png)

I YouTubetu channel， which is listening me to the news。



![](img/d4175b7c7da94dffbf39910f5457f6a6_8.png)

That I have created， I have started actually making a tutorial series because this series is more like an openform kind of a series。

 where I hope you guys do learn in the process， it's not very structured。

 which is good because you learned things like improvising and refactor and experimenting with a code and going back certain decisions。

But in the other hand， having a more structured。Tutial is nicer for beginners。

 so that's the target of this tutorial series and I've already created the first one and that's pretty cool I think。



![](img/d4175b7c7da94dffbf39910f5457f6a6_10.png)

I added it without little bit of animationation going on let see。Yeah。

 I see some drawings that I tried to do。And if you are interested in a more introductory step step by step approach and a quicker because it's going to be pretty quick compared to this series。

 you can watch。This series in share with friends who everyone wants to start programming games。Okay。

 and I also changed the art for the channel think that that's pretty cool there's nothing now it'。



![](img/d4175b7c7da94dffbf39910f5457f6a6_12.png)

My other commercial game， okay？So these are the news and。



![](img/d4175b7c7da94dffbf39910f5457f6a6_14.png)

I'm really excited to where this will lead us。 Okay， now let's go ahead and if I'm not mistaken。

 I'm going to crash。

![](img/d4175b7c7da94dffbf39910f5457f6a6_16.png)

And I do crash that's because I deleted some of the old art assets。 no， at the end of last stream。

 I was， I don't know what happened to me， I was a little bit crazy。😊。



![](img/d4175b7c7da94dffbf39910f5457f6a6_18.png)

And I really wanted to get that 16 meiseconds per frame。

 so I I did everything I could and in the end I ended up。😊。

Having the logo split into having just the little part the of the bitmap。

 the actual bitmap and the other things just。Just doing by hand。Let's see if it goes to the menu。

Because of your logo。Yeah， I see how we removed the logo。That was like a hand drawn logo。

 so to speak。So yeah， that was that was like crazy， I don't know if。Though the best call or not。

But I wanted to get that。Performance man， and we did。 So that was a victory。

 let's just remove now the loading of the logo because we are not。😊。

We're not going to use that logo anymore， just the half logo。



![](img/d4175b7c7da94dffbf39910f5457f6a6_20.png)

Let's see where we are。Okay。Nice。So that's the point where we are now， even if you go to full screen。

 yeah， seen we're running at 12。I mean， the second for frame。It's really。

 really cool and we're only at two， we're running at two milliseconds per frame at this size。



![](img/d4175b7c7da94dffbf39910f5457f6a6_22.png)

And running at 12 at 4K so I don't know， we are at a great point。



![](img/d4175b7c7da94dffbf39910f5457f6a6_24.png)

So it's time now that me get my note because I played the game a little bit off stream so we can。住在。

We should not do， we should not start the gameplay。Final pass， I should say。

Which is our to improve the levels， to like better levels， improve the field。That's been pretty cool。

And maybe do like more levels that would be cool like Tes lab。

 I think that's going to be the first one I want to do。In the new batch of ideas。

 I'm not sure I'm going to do all of them though， these they're just like batches of ideas。

And that's it， and then you can do like the final polish pass， which will include the engine。

Now today， we're going to start doing like some things like make the amounts P based on the yield position。

 this like some。Some general improvements and are also going to improve the play movement。

We just what are we discussed？Last time around。And we know the collision is not 100%。

 so I noticed a couple collision problems and I'm pretty sure I wonder wedo the collision。

But maybe you're going to do the level the four just so we can do no。Just so we can。

Got some more visual stuff going on today because we did a lot of engine pass。

 so let's start doing something late but。Yeah， this is important and that's also due to like the better levels。

It's not too hard， but going to start an R path to making the levels better。 Okay。

 now first thing that I should note is that if I out1。



![](img/d4175b7c7da94dffbf39910f5457f6a6_26.png)

Like if I open， I don't know， it's not bad。7。😊，The player gets all crazy。And。I want to fix that。



![](img/d4175b7c7da94dffbf39910f5457f6a6_28.png)

And the problem is that here in the Windows spectrum layer， when we set the center screen。

See the center screen is the position we're going to use to lock the mouse。Okay， and。Yeah。

 and then mouse input。See， where do we set。The center screen， Lets see。

I'm not sure where we set center screen。Oh， it's here。 Okay， so every time I change the size， Okay。

 that's not really necessary， but oh it's under the screen。 Yeah it's right。 Okay。

 so it is necessary。 So this working fine The problem is here when you calculate the Dp。

We use the center screen as our target position， which would be okay。



![](img/d4175b7c7da94dffbf39910f5457f6a6_30.png)

I mean， it is okay when we are centered。But when I all tap out of the game。

 I'm no longer sticking the mouse， see？Now the mouse is free because。

 the players want to play the game。And I should really also。不是一。Yeah。



![](img/d4175b7c7da94dffbf39910f5457f6a6_32.png)

Yeah， she maybe be not set that to zero。Set。Csor to zero。Let's see。 That's size。The activate app。

Yeah， I should only set the cursor to zero。Whenever I unlock the amounts， oh lock the amount。

So if I own tab other game， I should really。

![](img/d4175b7c7da94dffbf39910f5457f6a6_34.png)

See the开。

![](img/d4175b7c7da94dffbf39910f5457f6a6_36.png)

嗯。Of some fireworks going on here。I don't know what's going on。Yeah， guys。

 you probably hear the fireworks as well， yeah。H天。S curtisister。Yeah。

 but we can take a look at that later。In this have cursor to zero thing。嗯。Let we change this to。5。

Yeah yeah， we。Get it crazy。嗯。😊，I don't remember entirely how we did the cursor thing I still like wait cur oh。

 that's the audio， set the cursor position set it to zero， we only set that to zero we don't。Yeah。😊。

I'm going to pull like a note and see。Here。Let's say， well， we can do that。

 so I'm going to stop the cursor， I'm going to。Yeah， what you like。Csor。And right here。

 I'm going to make an H cursor。Bad cursor。You the IDC arrow， would you like the default cursor。

 they all have to do here is like do a handle。To a cursor。Call that1 32 cursor。

And they don't think it was that。Okay以。I should have recorded those fireworks because we are using fireworks sound。

And。

![](img/d4175b7c7da94dffbf39910f5457f6a6_38.png)

That's pretty cool。 Lo cursor A， let's see。😊。

![](img/d4175b7c7da94dffbf39910f5457f6a6_40.png)

Book cursor MSDN， you guys saw that a lot。

![](img/d4175b7c7da94dffbf39910f5457f6a6_42.png)

Going through the documentation and make sure that things work the instance， so let's take the age。



![](img/d4175b7c7da94dffbf39910f5457f6a6_44.png)

Yes。Okay， let's see if that works。

![](img/d4175b7c7da94dffbf39910f5457f6a6_46.png)

Okay， that works。Yeah， we already see the mouses there。Oh。I know。I don't know， it's not 100%。



![](img/d4175b7c7da94dffbf39910f5457f6a6_48.png)

嗯。

![](img/d4175b7c7da94dffbf39910f5457f6a6_50.png)

It's funny because when we move that。

![](img/d4175b7c7da94dffbf39910f5457f6a6_52.png)

for some reason， the node pe or you have to test that more thoroughly。



![](img/d4175b7c7da94dffbf39910f5457f6a6_54.png)

I'm going to a。Test。Thirdly。have your right to early， I'm not sure。Okay。

 so if you're supposed to unlock the mouse， we do that。Yeah， and this looks correct。Mouse。Yeah。

 and this is what you actually want to do instead of just doing the tin mouse。

I'm just going to do like the old mouse P。Okay， and after we do that。

 we can set like the old mouse B。Old mouse， B。Chair。We can set that to the。So the mouse pointer。有。1。

You must be， okay。They are going to create。Let' see。Create the P2 I。好。Musekey。

And we should probably initialize that。拿其实。The mouse。Maybe the center of the screen and see yeah。



![](img/d4175b7c7da94dffbf39910f5457f6a6_56.png)

Well， it's really problematic。

![](img/d4175b7c7da94dffbf39910f5457f6a6_58.png)

Oh， must be。And said that。I think we should set that afterwards。



![](img/d4175b7c7da94dffbf39910f5457f6a6_60.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_61.png)

Yeah。Let me just for。I mean， not。Qu imagine it。Fine。Hi， cursor。

Every set the cursor to zero from like。H Chris。Yeah， we already did this load cursor thing。Oh。

 we have this show cursor。Maybe that's what was missing there。

We set the cursor and then we show it that was I don remember who it was。

 that was somebody's step on the stream。

![](img/d4175b7c7da94dffbf39910f5457f6a6_63.png)

Have short。

![](img/d4175b7c7da94dffbf39910f5457f6a6_65.png)

Okay， so let's just see if we fixed that problem。

![](img/d4175b7c7da94dffbf39910f5457f6a6_67.png)

I don't know。Second cursor， but it's still， okay， so now we should hide the cursor。

 we should not hide cur。

![](img/d4175b7c7da94dffbf39910f5457f6a6_69.png)

C。

![](img/d4175b7c7da94dffbf39910f5457f6a6_71.png)

Okay。

![](img/d4175b7c7da94dffbf39910f5457f6a6_73.png)

So let's review the code。The first position should be wrong。It mean that every position is wrong。

 now the new mouse P is this guy and the DP is going to be exceptionalal with the old guy。

Then we set。Oh， okay。Yeah， this is the problem。If we lock。We should set。Just set this guy。

To the winter Tuesday。Which is what we were doing。And。



![](img/d4175b7c7da94dffbf39910f5457f6a6_75.png)

And in case you're not locked。And we should Okay， so the first edition was problematic but now it's 100% now if I go back shouldn't go crazy and it doesn't go crazy。

見る。I go back tea。

![](img/d4175b7c7da94dffbf39910f5457f6a6_77.png)

Right。Just kind of think the first position。呃。Well， I can just。嗯。

Yeah I'm thinking about what's the best way to initialize that because in the center screen。

 you probably have a valid center screen Yeah， so I'm going to create like yield mouse I going initialize that。

😊。

![](img/d4175b7c7da94dffbf39910f5457f6a6_79.png)

The center screen。Yeah， that should be good to go and you can probably assert。



![](img/d4175b7c7da94dffbf39910f5457f6a6_81.png)

This point。That it's got a added value。Yeah。Okay， so if we fix that。

 let's go back to hiding the cursor。

![](img/d4175b7c7da94dffbf39910f5457f6a6_83.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_84.png)

So now we don't go all crazy when we out tap out of the game。



![](img/d4175b7c7da94dffbf39910f5457f6a6_86.png)

No。Yeah， we still should should make sure that when we all tap register because like if I opt tap。

 see now I can see the mouse。If I do like visualual Studio， I can still see the mouse。But if I do。

 let's write for codeer， I can see the mouse。Oh， because the screen is still visible。Yeah。😊，Yeah。

 were not sure。Not sure I'm going to do that case， but that was a。

That was a victory for now so okay and now we got a small problem。

 we have to redo the player tag because if we have a slow frame rate。

 it doesn't run exactly the same so check out the menu。



![](img/d4175b7c7da94dffbf39910f5457f6a6_88.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_89.png)

お。How we get super thin and the audio gets you high pitched as well if we go。

 if we try to build a non optimized deal， let's see how bad。



![](img/d4175b7c7da94dffbf39910f5457f6a6_91.png)

C。😊，It's not as high pitched。That's because the size is still frame rate dependent。



![](img/d4175b7c7da94dffbf39910f5457f6a6_93.png)

At this point。Which。You thought about different things to do like make the player have a size that have a D。

 which is a velocity for the size。A derivative。Sees the player scale at low frame rate， so yeah。

 that's the base。Plan and the way we assumed we were going to fix this by doing the player size。But。

Not entirely sure。That's the best way， because the thing is the audio doesn't use the player size。

I you like player movement sound。Yeah， it doesn't， it use a target Dp。So this is wrong。

This really should be the target DP。Yeah， okay， so this is one problem。Play movement sound。

You probably had the same problem with the ball。

![](img/d4175b7c7da94dffbf39910f5457f6a6_95.png)

Let me try to explain what the problem is。We have。The speed。

 the player speed or target speed or whatever。That is in units per second。



![](img/d4175b7c7da94dffbf39910f5457f6a6_97.png)

Okay。We are't selling the target volume。To the ins per second， time is a very small value。

Is the ZP in units per second or units per frame？嗯。Okay， let's see where it's being set。S to 0。Yeah。

 I think that's the problem。 I think it's not in the correct scale。

Thiss going to break the gameplay significantly， but I've got a break through eggs to make an om。

 isn't that the same？呃。Okay。Yeah， let's see， this is where we calculate it。The target Tp。

It's the desire to pee。

![](img/d4175b7c7da94dffbf39910f5457f6a6_99.png)

Minus desired。 Yeah， see。We did that， I don't know you in the second day。That's not actually correct。

Well， or is it？嗯。The DP。The DB should be framed dependent。



![](img/d4175b7c7da94dffbf39910f5457f6a6_101.png)

And。Because。

![](img/d4175b7c7da94dffbf39910f5457f6a6_103.png)

see。We have a desire。 this is like the。

![](img/d4175b7c7da94dffbf39910f5457f6a6_105.png)

The new P and the old P。Great， let's print。が。They're target。You don't have plenty too。

Let's make a print。5 feet to eye。啊。Okay。😊，And we also have to add。Too many parameters， yeah。

 we don't take。Ding zeros。We don't take the number of big。Value2 already used。Okay。

 let's see the value and I think the problem is this D should not be here。



![](img/d4175b7c7da94dffbf39910f5457f6a6_107.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_108.png)

Yeah， it's kind of hard。

![](img/d4175b7c7da94dffbf39910f5457f6a6_110.png)

To analyzeize numbers。 We could。 We could say like。Player targetp。X， not zero。



![](img/d4175b7c7da94dffbf39910f5457f6a6_112.png)

And make help that。

![](img/d4175b7c7da94dffbf39910f5457f6a6_114.png)

Then it gets to first。

![](img/d4175b7c7da94dffbf39910f5457f6a6_116.png)

I'd say it's。

![](img/d4175b7c7da94dffbf39910f5457f6a6_118.png)

对是。this is how much we removed in a frame。

![](img/d4175b7c7da94dffbf39910f5457f6a6_120.png)

Yeah。😊。

![](img/d4175b7c7da94dffbf39910f5457f6a6_122.png)

So this is wrong now。So the DB should be how much removed。In one frame。Units。啊。

See this where I'm not entirely sure what we want， I's just fine doing that。



![](img/d4175b7c7da94dffbf39910f5457f6a6_124.png)

Turn the volume down because I'm show you what's going to happen to the pitch sound。



![](img/d4175b7c7da94dffbf39910f5457f6a6_126.png)

think got like super solid。

![](img/d4175b7c7da94dffbf39910f5457f6a6_128.png)

Because of that there's small number that we're using for the target well。Just yeah。

But' it's hard to say to see if we're going to get consistent results just by looking at this thing。

So what I am going to try to do is I'm going to change the。The spring parameter。

Let's go to the spring。What， what happened。Theification。That was pretty weird。So let's use the DP。

Play your usual role。你P。There is desired to P。What's the target？DP。Yeah。😊。

So you're going to have to multiply that。By a large number。I'm sure how large。



![](img/d4175b7c7da94dffbf39910f5457f6a6_130.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_131.png)

O。That was。That be too large。

![](img/d4175b7c7da94dffbf39910f5457f6a6_133.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_134.png)

Okay， let's， let's just see。

![](img/d4175b7c7da94dffbf39910f5457f6a6_136.png)

If we go back to the optimized build。If we have consistent results。Festible。



![](img/d4175b7c7da94dffbf39910f5457f6a6_138.png)

I don't think we do。No， we don't。Now we're just scratch on the unopimized， now it's the opposite。



![](img/d4175b7c7da94dffbf39910f5457f6a6_140.png)

Yeah， we may have to take a look at that code carefully， this polish pass。

You have to be a little bit of a patience you to avoid。To。O。Yeah， I'm going to show。

 I'm going to do like step by step again。Just going to make sure that this guy's correct let me just。

True。Great。Yeah。The player target DP。Is how much he moved like。



![](img/d4175b7c7da94dffbf39910f5457f6a6_142.png)

If you want to move， if you want to target pieceB like 100。That00 is in US per second。



![](img/d4175b7c7da94dffbf39910f5457f6a6_144.png)

Right I think this was great。And our calculations are wrong。So let's， let's draw。

 go back to drawing our。

![](img/d4175b7c7da94dffbf39910f5457f6a6_146.png)

Our solid player， they use the target P。As the position。Okay。



![](img/d4175b7c7da94dffbf39910f5457f6a6_148.png)

So this is like the， the most solid guy。 And the problem was getting this guy to move to， to look。



![](img/d4175b7c7da94dffbf39910f5457f6a6_150.png)

Yeah。

![](img/d4175b7c7da94dffbf39910f5457f6a6_152.png)

Yeah， this is perfect。Now。We're going to go back。And start。

Messing around with the player sides with the spring that we created。



![](img/d4175b7c7da94dffbf39910f5457f6a6_154.png)

切。So it looks pretty solid standard。

![](img/d4175b7c7da94dffbf39910f5457f6a6_156.png)

It does have a little bit delay， but that looks。

![](img/d4175b7c7da94dffbf39910f5457f6a6_158.png)

But if I removed this guy。Yeah， the problem is the size calculation。

Let's start fixing the audio first。

![](img/d4175b7c7da94dffbf39910f5457f6a6_160.png)

Because that looks a little bit easier。So now set the player movement sound。Here。

There's the bigger target DP。See， because we divided by the delta time。

 we have to multiply that to the DT。That makes sense。写第批。第样。



![](img/d4175b7c7da94dffbf39910f5457f6a6_162.png)

So we should have consistent sound now。

![](img/d4175b7c7da94dffbf39910f5457f6a6_164.png)

It's really high diched。But let's just see it's consistent。 If it is， then we can just。



![](img/d4175b7c7da94dffbf39910f5457f6a6_166.png)

T that out。

![](img/d4175b7c7da94dffbf39910f5457f6a6_168.png)

Yeah， it is okay， so that's the problem we were using the DT broker we're not multiplying that but the DT。

 so we want that to be less。Yeah二。

![](img/d4175b7c7da94dffbf39910f5457f6a6_170.png)

Lower pitch， let me put audio for you guys。

![](img/d4175b7c7da94dffbf39910f5457f6a6_172.png)

Directly and not go through my system。

![](img/d4175b7c7da94dffbf39910f5457f6a6_174.png)

You know what， I think I had one。

![](img/d4175b7c7da94dffbf39910f5457f6a6_176.png)

Too much zero。

![](img/d4175b7c7da94dffbf39910f5457f6a6_178.png)

I'm not sure。Let's just play around with the。

![](img/d4175b7c7da94dffbf39910f5457f6a6_180.png)

WithThe charge falling。

![](img/d4175b7c7da94dffbf39910f5457f6a6_182.png)

Let's just make。I you。

![](img/d4175b7c7da94dffbf39910f5457f6a6_184.png)

I think that's a nice started volume。Now for that target pitch。



![](img/d4175b7c7da94dffbf39910f5457f6a6_186.png)

I think that was too high pitched。感 see。

![](img/d4175b7c7da94dffbf39910f5457f6a6_188.png)

Yeah。😊，So it was high pitch because we multiplied that by a large number。Oh， what。😮。

Let's play that by the DT？我还粉。

![](img/d4175b7c7da94dffbf39910f5457f6a6_190.png)

Well。That makes a lot of sense， right？Okay， now I think we're going to make a little bit higher pitch now。

We have a consistent value。

![](img/d4175b7c7da94dffbf39910f5457f6a6_192.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_193.png)

Okay， that looks good。啊。Let's try that now with the unoptimized build。



![](img/d4175b7c7da94dffbf39910f5457f6a6_195.png)

That's if you have a similar result。

![](img/d4175b7c7da94dffbf39910f5457f6a6_197.png)

Perfect， perfect， so yeah， that that was the problem。

 so let's just do the same thing for the visual guy。😊。



![](img/d4175b7c7da94dffbf39910f5457f6a6_199.png)

So whenever there's the player target。If you so yeah， this was correct。

 we were getting the units per second。And but we were using it wrong。 We were using it without。



![](img/d4175b7c7da94dffbf39910f5457f6a6_201.png)

Ting that back when we set the target volume because we're doing this every frame。

 so we need to convert that back to units per frame， not per second。Okay， nice。Nice， nice。

Let's see where we you was the player， is the player target DP？So whenever you use that。

 so here's where we calculated， perfect。嗯。Place sound variation if you collide with ball。

 see if this would probably also consider the DT。Or not， let's say if we go out of the ball。

 we see our but no， this is perfect， this is perfect。Let's see about this the ball。Yeah。

 this is also perfect because we're setting the DP to the DP。

So they are in the same unit now this is probably where the problem is， Yeah。

 sees the same same thing we did down there。And they still don't have the。Yeah。Multipplication。

 so what by that by the Dt。Now we have this guy in the Unsburg frame。Just went， oh， wait a minute。

We are multi that by the DT。

![](img/d4175b7c7da94dffbf39910f5457f6a6_203.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_204.png)

可以。

![](img/d4175b7c7da94dffbf39910f5457f6a6_206.png)

Let's see the optimize。I don't know。Let me try running that first。Thinkme about the full screen。て？

Is that I do take more time， I think。🎼Well。Changing my mouse。🎼は。



![](img/d4175b7c7da94dffbf39910f5457f6a6_208.png)

This is weird， so let's try to understand this is a little bit more we have us p。A visual DDP。Which。

It's a desired P minus the visual P。So。Times the D P。So I think this。We're considering that as a DP。

So we should probably divide this whole thing。By the GT。I think。But I'm just going to offset that。

Let's say， by a larger number。Let'd say 02， So let's move back。

Because this is the DP and this is the DDP okay， yeah， because now we're multiplying that again。

 we're multiplying that by the Dt squared， so we had to divide by the DT here。

That was one problem and the Dp。这是DP。Yeah。DP is just whatever this is， multiplying by the DTC。

 this is why we need to that。And then the visual P， the P plus the Dt times the Dt。

 the Dp times the Dt。EDP times， yeah。Now， this is for the play visuals。

Not sure how that's going to change。 Oh， this is going to make it。

This is going to make the player follow that blue square consistently in terms of different frame rates okay and now the player half size。

Let's see， let's see the the player base have size X。Plus， so we're adding in offset for。

 which this would being the DP scaleale。Yeah。嗯。Which is one times yeah。



![](img/d4175b7c7da94dffbf39910f5457f6a6_210.png)

Maybe this is correct now。来次。

![](img/d4175b7c7da94dffbf39910f5457f6a6_212.png)

几。So we crashed， why did we crash？Yeah， our position was too much， we have to fix that。Yeah。

 I'm going to fix this，' going to set the hot level。To be。To have a range， because I know。

Shouldn't crash。So we could be from zero all the way to the L count， right？来不。It's gonna be clamp。0。

And the L。你边呢。Well， not the account，0 and。Out count -1。



![](img/d4175b7c7da94dffbf39910f5457f6a6_214.png)

可。😊，Now we should have a crazy position， but you should crash。



![](img/d4175b7c7da94dffbf39910f5457f6a6_216.png)

Well， so we fix the crash， it's good。But well。500。The GT。

 we're running at two milliseconds per frame。So， if we multiply。The DT， let' see。Should be this？Oh。

 it's won over this guy。Yeah， let me just remove this 500。

I'm not sure it should be like one divided by frequency。



![](img/d4175b7c7da94dffbf39910f5457f6a6_218.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_219.png)

嗯。If if we remove。Well。Let's set this guy to be the DP directly。



![](img/d4175b7c7da94dffbf39910f5457f6a6_221.png)

Yeah。We're going to turn our volume down because some weird soundit effects are going on。



![](img/d4175b7c7da94dffbf39910f5457f6a6_223.png)

嗯。St呃。This guys， how much you moved。Last frame。Maybe the multipliers are wrong。



![](img/d4175b7c7da94dffbf39910f5457f6a6_225.png)

你就是。This guy can't see。 maybe it's going be 0。

![](img/d4175b7c7da94dffbf39910f5457f6a6_227.png)

Okay。Okay， now we can see that was a， I wasn't expecting that。



![](img/d4175b7c7da94dffbf39910f5457f6a6_229.png)

Just for crazy fun。Let's just make this guy， the player。Have size wide。



![](img/d4175b7c7da94dffbf39910f5457f6a6_231.png)

This is for no particular reason other than our advise。I this see。Looks like a dance， okay？



![](img/d4175b7c7da94dffbf39910f5457f6a6_233.png)

Now the thing is， we should have consistent。

![](img/d4175b7c7da94dffbf39910f5457f6a6_235.png)

Movement like this across frame rates。

![](img/d4175b7c7da94dffbf39910f5457f6a6_237.png)

Scale wise because the position we just you know we order to so。Let's try removing this guy。



![](img/d4175b7c7da94dffbf39910f5457f6a6_239.png)

It was pretty consistent。

![](img/d4175b7c7da94dffbf39910f5457f6a6_241.png)

So I think the size is correct because the size is pretty much like what we did there。

 we multiplied that。

![](img/d4175b7c7da94dffbf39910f5457f6a6_243.png)

By the DT。Like this。Now， this guy is wrong。The spring。Soは。Hey。Hey no， it's nice to see you here。

 manam。Everything is great around here， what about with you？Nice to see you， man。诶 ok。

Let's fix the spring thing， we want to change the so the basic thing we should do。

 we shouldn't like one。We could set a visual P。To be the player。Trgget B。



![](img/d4175b7c7da94dffbf39910f5457f6a6_245.png)

So this way， you should have like a non stretchy guy。



![](img/d4175b7c7da94dffbf39910f5457f6a6_247.png)

Okay。Actually， I think we do stretch， but we don't have it delay。



![](img/d4175b7c7da94dffbf39910f5457f6a6_249.png)

那是。Everything's great to hear nice to hear that， man。Okay， so this。Is the。



![](img/d4175b7c7da94dffbf39910f5457f6a6_251.png)

Dsect player position。We want to add a spring effect。



![](img/d4175b7c7da94dffbf39910f5457f6a6_253.png)

Which means that。啊。We want to get somewhere。Like。You guys saw the final result that we wanted right。

 but it's not consistent across train rates that was the problem so let's say if the player is that the target position is here。

 we want the actual position to do something like this。



![](img/d4175b7c7da94dffbf39910f5457f6a6_255.png)

ok。That's what we did with the spring effect， and this is the basic equation。



![](img/d4175b7c7da94dffbf39910f5457f6a6_257.png)

This is the target？Position。😊，Let's try to change you that's a desired be。



![](img/d4175b7c7da94dffbf39910f5457f6a6_259.png)

Let's see if there's any difference。

![](img/d4175b7c7da94dffbf39910f5457f6a6_261.png)

No， it's maybe be one frame of a lag， okay。This is a target position。Oh， and this was the GDPP。

This is the target position。继续。And this is our position。ok。And this is the target velocity。

 and this is our velocity。 I think this is okay。 I think this is correct。 This is a spring。😊。

Equation， pretty much。If you remove this part of the coefficients。

 we should just have like an infinite spring。But I'm going to remove this one multiplying here。

And the player DP。I's going to multiply that and this looks correct。

Let's go back without the velocity coefficient。

![](img/d4175b7c7da94dffbf39910f5457f6a6_263.png)

Let's see。This speak Portuguese？Yeah， so Brazil， man。🎼すみませ ベルとメイン。Okay。

 so the interesting thing that happened here。That I wasn't really expecting to stop ever。

We are resilient。Awesome。

![](img/d4175b7c7da94dffbf39910f5457f6a6_265.png)

You know， the new video that I posted on my YouTube channel。呃。

Wwhich was the tutorial because this isn't like an actual tutorial， this is just a live stream。

 but I do expect you guys learn me by following along。

 but I post like a step by step tutorial and this one I posted subtitles in Portuguese。



![](img/d4175b7c7da94dffbf39910f5457f6a6_267.png)

So you canda or that see。We can the to Portuguese。And hopefully I did do a couple of jokes like Eli Simon。

嗯。Things like that。So his nuts。

![](img/d4175b7c7da94dffbf39910f5457f6a6_269.png)

For making a game from scratching and see， dude， the progress， see the progress。

 we've been doing this like 40 hours， which was 16 streams。



![](img/d4175b7c7da94dffbf39910f5457f6a6_271.png)

And we have a lot of stuff already。

![](img/d4175b7c7da94dffbf39910f5457f6a6_273.png)

Check it out， man。But I try to un speakak English yeah， because。

Most of people don't speak Portuguese around me。

![](img/d4175b7c7da94dffbf39910f5457f6a6_275.png)

On the screen， let me go back to where we were。So I can show the progress of making a game from scratch and see。



![](img/d4175b7c7da94dffbf39910f5457f6a6_277.png)

So we did breakout， we can't even ignore like this blue thing。好僧。We did break out with power ups。

Well， if you can get a power out。Yeah， there you have it and bitmap support。Yeah。Okay。

And that's what we're going to improve today， the other game modes like breakakout Po。Ohあましかった。

And break out spacing invades。And what I do this is I can even do a game just in an angel。Well。

 but that's the process right， I mean the more you do， the better going to be come at it。And。

And the amount of time that you invest。It's like really proportionportal to to the results that you get and I'm super。



![](img/d4175b7c7da94dffbf39910f5457f6a6_279.png)

Sure about that。It's pretty evident。If you do want to learn things like actually check out this video and in the person in the series。

 I just post the first one， we'm going to post the other ones in the following weeks。



![](img/d4175b7c7da94dffbf39910f5457f6a6_281.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_282.png)

I didn't do any the best time in it， yeah。But once you get started。

 the hardest things is getting started。Once to do， get started。



![](img/d4175b7c7da94dffbf39910f5457f6a6_284.png)

It becomes like a routine， like a habit。🎼And then。It's all my fault yet， but I don't know。

 mean it's not like。

![](img/d4175b7c7da94dffbf39910f5457f6a6_286.png)

Most people have hard times starting。I mean， I had a hard time studying。

 but what wants to do get started。

![](img/d4175b7c7da94dffbf39910f5457f6a6_288.png)

It becomes like a positive feedback loop likeking a game， right。

 because you see the better stuff that you're doing even you want to do even better stuff。🎼し。



![](img/d4175b7c7da94dffbf39910f5457f6a6_290.png)

I think。I think we are consistent。Well。You don't have to review that code。跟是。Yeah。

 let's see the size wasn't changing。

![](img/d4175b7c7da94dffbf39910f5457f6a6_292.png)

🎼美し。Now the audio。It's not they consistent。

![](img/d4175b7c7da94dffbf39910f5457f6a6_294.png)

Yeah。That's weird。 Are we using the visual DP in the audio for some reason？

We're sure use the visual DP anywhere should we。Well， the player。lay。比如说DP。Yeah， we are not。

What about， the GDPP that's delete there？Re more fun。是。

He's doing the he madeade way way more difficult to engineering general where for， yeah， dude。

 it is more fun because。I know the fun about doing things from scratch and understanding them and being able to do。

 well， speaking about understanding them， we should really understand what's going on。



![](img/d4175b7c7da94dffbf39910f5457f6a6_296.png)

Yeah。😊，Because somewhere we are not frame rate independent。But I don't know， man， sometimes。

Let's try going like full screen。Okay， so。Now we're super wrong just by going full screen。When next。

嗯。😊，So I see now it's hard for you guys to see， well。Let see if I can change the display to。



![](img/d4175b7c7da94dffbf39910f5457f6a6_298.png)

Yeah。Check out the full screen game。See how we don't have like。We don't have the sound。

Nor the big distortion。

![](img/d4175b7c7da94dffbf39910f5457f6a6_300.png)

That's because we' were at well Frank， if we do the small one。We do have so。

We apparently haven't changed anything。To be honest。Whi。Not sure why。

 why use CA C++ C++ has a lot more features and most of them really make the code more complicated and harder to read in order to compile。



![](img/d4175b7c7da94dffbf39910f5457f6a6_302.png)

In this series I'm using C++ because this meant to be more educational in terms of okay。

 you're going to learn how to make game the C++ is the industry， yeah， C+ is a nightmare yeah。😊。



![](img/d4175b7c7da94dffbf39910f5457f6a6_304.png)

But come on see is way more fun， way more streamlined and has everything you need， I mean。

 there will be one or two features。That would be cooler if they were in sea。But well。

 I'm not going to die because of it。So。Yeah， maybe I'm going to have to test the full screen thing。

Just make sure that。That's consistent。Okay， so maybe I'm going to go full screen on you guys。

But then I'm going to have a hard time reading chat。S was a God to me， dude。

Be careful your Gods what you worship right， see's pose is crazy man。Come on， it's not elegant。

 it's not an elegant God。Yeah。😊，Okay。呃。Yeah， let's go back to our audio。The player movement sound。嗯。

We are taking the absolute of the targetP time the TP。



![](img/d4175b7c7da94dffbf39910f5457f6a6_306.png)

So yeah， we have units per second。Correct， because we have units per frame。

And then we divided it depth by the DP， which is。How many seconds per frame we have。

 So we divided that we multiplly by this guy。

![](img/d4175b7c7da94dffbf39910f5457f6a6_308.png)

Yeah， units per second， so we have units per second。Here they're going to and we're multiplying that。



![](img/d4175b7c7da94dffbf39910f5457f6a6_310.png)

By the seconds per framein。

![](img/d4175b7c7da94dffbf39910f5457f6a6_312.png)

So it leaves us with the units per frame。And the target volume。It's going to be。

How many we change in that frame？This is good or bad。你干去。Just like zship first。嗯。有谁。I don't know。

I am not entirely sure。

![](img/d4175b7c7da94dffbf39910f5457f6a6_314.png)

Because we did that and probably we didn't see anything changed on this episode。



![](img/d4175b7c7da94dffbf39910f5457f6a6_316.png)

We see the difference。So we do hear a little bit of sound。



![](img/d4175b7c7da94dffbf39910f5457f6a6_318.png)

And here we hear a lot of sound in fact take this guy away。And they add a couple more guys like this。

That's if it's different。

![](img/d4175b7c7da94dffbf39910f5457f6a6_320.png)

The other。Okay。

![](img/d4175b7c7da94dffbf39910f5457f6a6_322.png)

So I can pretty much say confidently that this proved to be a better result。I sure， it's 100%。

Perfect。😊，But it is a bad result。

![](img/d4175b7c7da94dffbf39910f5457f6a6_324.png)

Yeah， this may just be。

![](img/d4175b7c7da94dffbf39910f5457f6a6_326.png)

Oh， and now we got them mouse。Yeah， see at like one the time per frame。We are super jelly。Oh。

 but we are pretty jelly here as well。At six。

![](img/d4175b7c7da94dffbf39910f5457f6a6_328.png)

Yeah， see okay， so that's evident so like this， well you guys can't see anything right？



![](img/d4175b7c7da94dffbf39910f5457f6a6_330.png)

Let。

![](img/d4175b7c7da94dffbf39910f5457f6a6_332.png)

Me show you guys again， okay。

![](img/d4175b7c7da94dffbf39910f5457f6a6_334.png)

So。Check out this movement。Try to do the same。

![](img/d4175b7c7da94dffbf39910f5457f6a6_336.png)

Yeah。So。We are still firmly dependent。

![](img/d4175b7c7da94dffbf39910f5457f6a6_338.png)

So the target， yeah。Maybe this。This operation is wrong because let's go to the ideal。

 the target volume。Its like a， it's just a to， yeah， I mean。We don't use that as a DP or not。



![](img/d4175b7c7da94dffbf39910f5457f6a6_340.png)

In the target。已经。

![](img/d4175b7c7da94dffbf39910f5457f6a6_342.png)

Units per frame here。The target。Volume。I don't know。Should just be the。Yes。

This is this is like really complicated。Because we are like in a couple levels deep in terms of。



![](img/d4175b7c7da94dffbf39910f5457f6a6_344.png)

啊。Interaction。Time indirect， if I could say that。Like。😊，Yeah， this是的。This is the problem。

We have the DP， which is how much the plane moved from one frame to the other， okay， that's the DP。



![](img/d4175b7c7da94dffbf39910f5457f6a6_346.png)

嗯。It's actually that。

![](img/d4175b7c7da94dffbf39910f5457f6a6_348.png)

D拜 by。

![](img/d4175b7c7da94dffbf39910f5457f6a6_350.png)

DT。You know what？Maybe I should just consider this guy。And call that death。

So the diff is how much you moved in one frame。ok。😊，Okay。



![](img/d4175b7c7da94dffbf39910f5457f6a6_352.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_353.png)

Can we change that for the。For the sound， but let's try to hear the sound。



![](img/d4175b7c7da94dffbf39910f5457f6a6_355.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_356.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_357.png)

Okay， I think。I think we are perfect now， let me show you guys the full screen again。



![](img/d4175b7c7da94dffbf39910f5457f6a6_359.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_360.png)

🎼行。

![](img/d4175b7c7da94dffbf39910f5457f6a6_362.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_363.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_364.png)

Okay so yeah。No， it's still not 100%。Still not 100%。



![](img/d4175b7c7da94dffbf39910f5457f6a6_366.png)

嗯。This guy we are dividing by the DT， and then here we just multiply that back into the DT。



![](img/d4175b7c7da94dffbf39910f5457f6a6_368.png)

But this guy is in。Unions per frame。So units per frame。If you multiply that by the frames per second。



![](img/d4175b7c7da94dffbf39910f5457f6a6_370.png)

It is like divide by the second square frame。Got the NP second。

 so I'm going to try doing the division here。

![](img/d4175b7c7da94dffbf39910f5457f6a6_372.png)

Which is the same thing so I could probably just do as the other guy。



![](img/d4175b7c7da94dffbf39910f5457f6a6_374.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_375.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_376.png)

I think there'll be no escape， honestly。I'm kind of a thinking about giving up doing this。At least。

嗯呃。Go back towards the change because we didn't change from well。So at the end of the day。

I think this guy should use just a diff。

![](img/d4175b7c7da94dffbf39910f5457f6a6_378.png)

Because you're updating that every frame。

![](img/d4175b7c7da94dffbf39910f5457f6a6_380.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_381.png)

Yeah， but that's。I don't know， it's not good at all if we divide that by the D team。



![](img/d4175b7c7da94dffbf39910f5457f6a6_383.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_384.png)

🎼我。

![](img/d4175b7c7da94dffbf39910f5457f6a6_386.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_387.png)

I think the other problem actually may be。This move towards here。Because we are moving。Yeah。Yeah。

 I think how okay。I think I got somewhere。This move towards is trying to get to this goal。

At this speed， which considers the DT。Plus the target。So this is just wrong。

ItShould be something like this。And let see。Move towards。Okay， and then in the audio。Move towards。

 Let's see。 we use then。Fading speed。AtF speed。And that's just a constant。Yeah。

 the deep T should look like both of these guys。

![](img/d4175b7c7da94dffbf39910f5457f6a6_389.png)

那起 think。Okay。I think we achieve success。Let's see full screen。



![](img/d4175b7c7da94dffbf39910f5457f6a6_391.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_392.png)

Okay， we did it， we did it。

![](img/d4175b7c7da94dffbf39910f5457f6a6_394.png)

We fix the problem so the problem was to move towards I then just remind you guys how the move towards worked so you guys can it's a very useful function the move towards see it takes the the where is it now the target and how much should move right so let's say we are at X and then we want to go to y at the speed of 10。



![](img/d4175b7c7da94dffbf39910f5457f6a6_396.png)

And then we just add 10 to x。And then if you go like pass why， we go with ticket one。

That's to move towards。And the speed which we were moving was wrong， it was like this the DT times 5。

 which is a correct constant because this should be in frame time， not in seconds。

 but then I add the target guide， and I shouldn't really add the target without modify the DT at the DT。

Is really the。The base here because the target is now frame rate。Independ。

 see how multi fired up at the D T here。Nice。The tariff volume， I should probably just。

I probably to use the same thing， which is the player。Guy here Time this guy。



![](img/d4175b7c7da94dffbf39910f5457f6a6_398.png)

But it's less noticeable than the pitch， see。

![](img/d4175b7c7da94dffbf39910f5457f6a6_400.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_401.png)

Okay， so this is not correct。The target。I'm multiplying by the DT there。

 so I shouldnt multiply it here。

![](img/d4175b7c7da94dffbf39910f5457f6a6_403.png)

Yeah行。II'm not sure what's test this。🎼Yeah？

![](img/d4175b7c7da94dffbf39910f5457f6a6_405.png)

う。

![](img/d4175b7c7da94dffbf39910f5457f6a6_407.png)

This is correct。But。Not surely upset。

![](img/d4175b7c7da94dffbf39910f5457f6a6_409.png)

嗯。

![](img/d4175b7c7da94dffbf39910f5457f6a6_411.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_412.png)

Oh so okay， the volume is wrong。The volume is really wrong。收。

Let's see this guy should be able to multiply that by deeply。

So not they real confused because if I'm already multiping it by the Dt here。

I shouldn't have to multiply that again by the DT， so it shouldn't be something like this。啊。

But again， that's how it was。

![](img/d4175b7c7da94dffbf39910f5457f6a6_414.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_415.png)

No， I can't hear anything。

![](img/d4175b7c7da94dffbf39910f5457f6a6_417.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_418.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_419.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_420.png)

Yeah， I think the volume is the only problem。 Oh， the volume is problematic because it's also going through a。

😊。

![](img/d4175b7c7da94dffbf39910f5457f6a6_422.png)

It's also going through a。It's also going through a move towards there， so if I set the。

Player movement， sound。

![](img/d4175b7c7da94dffbf39910f5457f6a6_424.png)

Fadty speed to something smaller。嗯。Try something weird。



![](img/d4175b7c7da94dffbf39910f5457f6a6_426.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_427.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_428.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_429.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_430.png)

Yeah， I'm pretty sure the problem is the volume now。Seeteve。

 because there are so many things operating at the same time， it's really。

 really hard to isolate just one of them。But let's try so the volume。这第一。



![](img/d4175b7c7da94dffbf39910f5457f6a6_432.png)

That's just here the pitch。Oh。

![](img/d4175b7c7da94dffbf39910f5457f6a6_434.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_435.png)

So， it's not。

![](img/d4175b7c7da94dffbf39910f5457f6a6_437.png)

Correct， let's go back to the workforce。

![](img/d4175b7c7da94dffbf39910f5457f6a6_439.png)

And I think it's。

![](img/d4175b7c7da94dffbf39910f5457f6a6_441.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_442.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_443.png)

Okay， it's not 100% the edge。But I'm pretty confident that it's more correct。



![](img/d4175b7c7da94dffbf39910f5457f6a6_445.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_446.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_447.png)

Yeah， and at the end of the day， it's not about making the perfect game。

 it's about improving the game every time。Oh， the volume was wrong。



![](img/d4175b7c7da94dffbf39910f5457f6a6_449.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_450.png)

But this is like really wrong， so let's check this out。We want to go to this guy。

 which is how much he's moving。Times the DT。So it's the amount per frame that hits moving？

I don't think the target should include the GT。

![](img/d4175b7c7da94dffbf39910f5457f6a6_452.png)

I don't think it should。

![](img/d4175b7c7da94dffbf39910f5457f6a6_454.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_455.png)

So I think you have。Let we exit the full screen。Size see。It's wrong。 Hy cursor， side cursor is 0。啊。

I don't know， the sectors is really finicky。Okay， I think now we are a lot more correct。



![](img/d4175b7c7da94dffbf39910f5457f6a6_457.png)

な。

![](img/d4175b7c7da94dffbf39910f5457f6a6_459.png)

And now。I'm going to remove this guy from the D P。Oh my god， he tackled so many things。



![](img/d4175b7c7da94dffbf39910f5457f6a6_461.png)

Okay。

![](img/d4175b7c7da94dffbf39910f5457f6a6_463.png)

🎼う。No， this was correct。This was correct。

![](img/d4175b7c7da94dffbf39910f5457f6a6_465.png)

Like。Okay， now I'm going to be。The most precise。

![](img/d4175b7c7da94dffbf39910f5457f6a6_467.png)

Mathematically。But I think we proved that a lot。

![](img/d4175b7c7da94dffbf39910f5457f6a6_469.png)

Now， I'm just going to make sure。That the size。

![](img/d4175b7c7da94dffbf39910f5457f6a6_471.png)

Is okay。

![](img/d4175b7c7da94dffbf39910f5457f6a6_473.png)

🎼I think it is。So let me just go back to the unoptimized build and let's play around it。



![](img/d4175b7c7da94dffbf39910f5457f6a6_475.png)

Okay。I like that。I really like that。

![](img/d4175b7c7da94dffbf39910f5457f6a6_477.png)

Well， I don't like that。Check out what's going on。

![](img/d4175b7c7da94dffbf39910f5457f6a6_479.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_480.png)

I'm going to set a break point。That's that a break point。

Whenever we set the full screens of the togg。Full screen。Never we said that to full screen。



![](img/d4175b7c7da94dffbf39910f5457f6a6_482.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_483.png)

Well， been brave for some reason。Oh it's the other one this one。行。ok。Now。

 whenever you change the size to full screen。Im also going to put it like a break point。

You'ing the size。Let's just keep going and also。Going to put a break point。嗯。Indyア게。

Now we should give a to update。Let's see what's the mouse Tp。Well， it does look too unreasonable。



![](img/d4175b7c7da94dffbf39910f5457f6a6_485.png)

I think the problem。Maybe when we change， like。This guy？We should reset the old mouse。

 so the old mouse。Like this。So we'm gonna put you mouth， in this。P your old mouse here。

And we're going to set the old mouse。And we change the size as well。



![](img/d4175b7c7da94dffbf39910f5457f6a6_487.png)

Yeah。😊，I think that's a problem， see。オッケー。Now it does work。



![](img/d4175b7c7da94dffbf39910f5457f6a6_489.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_490.png)

Oh it doesn't market。嗯。😊，So let's go back。To simulating the game， updating the game， let's see。

The mouse。Why is it？Unreasonable like that。

![](img/d4175b7c7da94dffbf39910f5457f6a6_492.png)

But we did render。Yeah， oh， I suppose it was kind of correct。No， I suppose it's correct。But。

This is where it gets out of hand。 So the mouse DP worlds 26 units。Whi is a lot。And then okay。

 we set the collision and let's see the spring。Yeah， this guy is going move。Quite a lot。Minus 38。

I know， this guy。Which should be positive。800 time。I' know。



![](img/d4175b7c7da94dffbf39910f5457f6a6_494.png)

If I make this brain。存だ。Well， Bur and not going to run a bathroom rate anyways。



![](img/d4175b7c7da94dffbf39910f5457f6a6_496.png)

Maybe you shouldn't spend too much time on that。Let's just understand a little bit more about it。



![](img/d4175b7c7da94dffbf39910f5457f6a6_498.png)

企。Let's just ignore this guy。And let's see how that looks。Yeah。

I suppose it was correct the way we assumed that。This whole thing。Had to be defined by the DT。

But then should really multiply that by something else， but let's just check out。Yeah。

 see how we get。

![](img/d4175b7c7da94dffbf39910f5457f6a6_500.png)

Very small values。

![](img/d4175b7c7da94dffbf39910f5457f6a6_502.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_503.png)

嗯。So lets say let's multiply that by a very model。

![](img/d4175b7c7da94dffbf39910f5457f6a6_505.png)

放弃。

![](img/d4175b7c7da94dffbf39910f5457f6a6_507.png)

I think this guy can be a little bit larger， oh， I'm just a。I was just。Deightiding。This guy。



![](img/d4175b7c7da94dffbf39910f5457f6a6_509.png)

And not the whole thing。🎼い？Let's cross our figures。Okay， so we are a little bit in this low motion。

I think that's because we are running really badly。Oh， you guys can see。To go back。No。

 we are really fast， so。Maybe I shouldn't divide by the DT。

What happens if I don't define by the teacher？🎼I was super不 stole。



![](img/d4175b7c7da94dffbf39910f5457f6a6_511.png)

But we are consistent。I suppose。There wasn't a problem there。I suppose I just had to limit， yeah。

I we just have to limit this guy。Because since we are running at a very low frame rate。

Aren't we Are't we。Liiting the frame rate。We were supposed to。Last BT。



![](img/d4175b7c7da94dffbf39910f5457f6a6_513.png)

So this is。More of what we expect。 Oh， but we were limiting。



![](img/d4175b7c7da94dffbf39910f5457f6a6_515.png)

To tan。

![](img/d4175b7c7da94dffbf39910f5457f6a6_517.png)

Well， this is very wrong now。I don't think you guys can be anything right？Because of the size。Yeah。

 let me go back。No， I think we're going to keep at the point where we were like this。At this point。

Yeah， at this point。And I'm just going to limit this guy。

And let me just print it to see what values we have。



![](img/d4175b7c7da94dffbf39910f5457f6a6_519.png)

You know， I have pretty big fat is like 200， I think。400， 800。And we have like huge values。

Like would those that？

![](img/d4175b7c7da94dffbf39910f5457f6a6_521.png)

Couldn't even print the number。

![](img/d4175b7c7da94dffbf39910f5457f6a6_523.png)

So I'm going to do is limit。はい、そう。Going to clamp that。At C2 of 10，000。Okay。啊。



![](img/d4175b7c7da94dffbf39910f5457f6a6_525.png)

あ。

![](img/d4175b7c7da94dffbf39910f5457f6a6_527.png)

Let's limit that to 1000。

![](img/d4175b7c7da94dffbf39910f5457f6a6_529.png)

🎼Nice。The looks better。

![](img/d4175b7c7da94dffbf39910f5457f6a6_531.png)

I don't know。This is really bad。Let's try just taking a little more time into that。

 then maybe we're going to go back， we're going to go to the level design。Afterwards。

If I limit this guy to 100。

![](img/d4175b7c7da94dffbf39910f5457f6a6_533.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_534.png)

🎼Yeah。I that the target P。It doesn't make any sense。



![](img/d4175b7c7da94dffbf39910f5457f6a6_536.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_537.png)

哦。

![](img/d4175b7c7da94dffbf39910f5457f6a6_539.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_540.png)

Okay， so the problem is the target。地皮。Okay。So this guy is a desire to minus the fu。

Which is how much you moves last frame， So this is the target position。Yeah。

And this is less frame historic position。No， yeah。Wait a minute。Oh， no， this is the why， okay。

Maybe this guy should be multiplied by the D divided by the DT。Yeah。😊，好奇。

So here multiply that by the DT squared。This guy is in。Units per frame。So if I define this guy。I个DT。

Should be used for second。

![](img/d4175b7c7da94dffbf39910f5457f6a6_542.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_543.png)

But， we are supposed to be the。You're supposed to be oh this scan of random。



![](img/d4175b7c7da94dffbf39910f5457f6a6_545.png)

Okay。So we don't go nuts， but we do have。🎼Different。🎼Results， we are faster。



![](img/d4175b7c7da94dffbf39910f5457f6a6_547.png)

We are faster， this lower we are。So if the DT is greater， we are faster。

So this really shouldn't be necessary， I know。

![](img/d4175b7c7da94dffbf39910f5457f6a6_549.png)

Do we have like a Dt multiplier， I think we do like target。



![](img/d4175b7c7da94dffbf39910f5457f6a6_551.png)

啊，这DT。安こ。Let me set the Dt multiplier down a lot， so when you press up。The DT multipllyiering。

It's going to be。

![](img/d4175b7c7da94dffbf39910f5457f6a6_553.png)

So we're going to take the against the motion to see。



![](img/d4175b7c7da94dffbf39910f5457f6a6_555.png)

我要。1。

![](img/d4175b7c7da94dffbf39910f5457f6a6_557.png)

For some reason， it's like really。Let's see if I go full screen。It doesn't appear that here。

Going back to our。It doesnn't really changing the size at all。



![](img/d4175b7c7da94dffbf39910f5457f6a6_559.png)

Maybe it's just because we were super slow。

![](img/d4175b7c7da94dffbf39910f5457f6a6_561.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_562.png)

Yeah。😊。

![](img/d4175b7c7da94dffbf39910f5457f6a6_564.png)

This is really weird， really weird。Let see we don't see。Okay。🎼Let's see that。



![](img/d4175b7c7da94dffbf39910f5457f6a6_566.png)

Okay。Prom is。When we move a great amount of。Let's go back to this screen。

When we move a great amount of length。At this point。We go way overboard。ok。😊，And the visual D。

Doesn't get updated to that so maybe。This should be the target Dp。



![](img/d4175b7c7da94dffbf39910f5457f6a6_568.png)

我要。I sure不's see。

![](img/d4175b7c7da94dffbf39910f5457f6a6_570.png)

That doesn't have。This guy is when we are super high。

 this guy becomes super high and we go like really strongly on that direction so I'm。

Pretty confident。This guy。Should be。Multiplily it by the DT。呃。Yeah， because this guy is even units。

B frame。If you want to baby per second， we multipi by the frames per second， which is the。



![](img/d4175b7c7da94dffbf39910f5457f6a6_572.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_573.png)

Okay， I think this is correct now。But we should really play off。



![](img/d4175b7c7da94dffbf39910f5457f6a6_575.png)

う。That's itけ。🎼It's funny， because the。🎼好けえよ。Also to the alone time。

Maybe all our assumptions now are correct， I suppose。



![](img/d4175b7c7da94dffbf39910f5457f6a6_577.png)

That this guy。

![](img/d4175b7c7da94dffbf39910f5457f6a6_579.png)

Is the DP。嗯ん。😊，Is our assumption？

![](img/d4175b7c7da94dffbf39910f5457f6a6_581.png)

No， that's not。Forget about that， you never heard that from me。



![](img/d4175b7c7da94dffbf39910f5457f6a6_583.png)

Our assumption。🎼Its just same。

![](img/d4175b7c7da94dffbf39910f5457f6a6_585.png)

That。的。This guy， which is not frame dependent。

![](img/d4175b7c7da94dffbf39910f5457f6a6_587.png)

And this guy， which is not from a dependent。You guys can't see right， keep forgetting that。次。

So this is the fast result。And there's no screen by slow motion。



![](img/d4175b7c7da94dffbf39910f5457f6a6_589.png)

Okay。

![](img/d4175b7c7da94dffbf39910f5457f6a6_591.png)

So that。I know。 I think I'm just going to leave。Where we were， and we did have some for progress。

We didn't， it wasn't。100% in。Just see where we are。

 We're going to compile and optimize mode because I don't know making sure that the movement system works when we are like。

Running at 10。A 20 frames per second？那我 wasn't2 we were we were。



![](img/d4175b7c7da94dffbf39910f5457f6a6_593.png)

Yeah， it was 20 years， thanks guess。Rerain。

![](img/d4175b7c7da94dffbf39910f5457f6a6_595.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_596.png)

Yeah， it looks， pretty good at 12。So we probably have two。We probably sleep now。

We should probably sleep now。And while not physically sleep， just sleep the frame。

So we have a consistent prime rate。And now we can play around with the values a little bit more。

Like a review。3 scales at。Super low frame rates。But we didn't prove that。 So let's do。

Let's go back to the game college。东し。

![](img/d4175b7c7da94dffbf39910f5457f6a6_598.png)

Okay。So let's just make sure we have。Somewhere， let's go back to the spring settings。



![](img/d4175b7c7da94dffbf39910f5457f6a6_600.png)

嗯。We are super。

![](img/d4175b7c7da94dffbf39910f5457f6a6_602.png)

我是不 springing。

![](img/d4175b7c7da94dffbf39910f5457f6a6_604.png)

啊。😮。

![](img/d4175b7c7da94dffbf39910f5457f6a6_606.png)

嗯。

![](img/d4175b7c7da94dffbf39910f5457f6a6_608.png)

Im guess it's going to control Z a lot。Just because I don't know what we were playing around with this guy。

Yeah， we played around this condition。Oh， we had a clamp problem。Yeah。

 let's just keep the clamp at 10，000。

![](img/d4175b7c7da94dffbf39910f5457f6a6_610.png)

O。

![](img/d4175b7c7da94dffbf39910f5457f6a6_612.png)

Nice。

![](img/d4175b7c7da94dffbf39910f5457f6a6_614.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_615.png)

So we are a little bit different。But they're not 100% different。E programming in C， dude。

 the C is awesome。そそうそう。啊。Oh man， that's awesome。 What do you mean。I don't do see。Well。

 you should do C sometimes really clears your mind if you know what I mean。



![](img/d4175b7c7da94dffbf39910f5457f6a6_617.png)

Well， kind of forgot what I was doing。Can have me remove the the draw。



![](img/d4175b7c7da94dffbf39910f5457f6a6_619.png)

Let fix so like this。

![](img/d4175b7c7da94dffbf39910f5457f6a6_621.png)

It's too confusing。

![](img/d4175b7c7da94dffbf39910f5457f6a6_623.png)

Don't you think simple pluss more confusing？

![](img/d4175b7c7da94dffbf39910f5457f6a6_625.png)

I'm pretty confident I think C++ is way more confusing to see。Maybe if you compare that with。

Higher level languages。

![](img/d4175b7c7da94dffbf39910f5457f6a6_627.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_628.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_629.png)

Thing grow in a good place Now let's try locking the frame it's going to be pretty simple。

 I have the。It was supposed that confusing。I know， man。I'm not going to hold that against you。

We can just sleep。For some time。

![](img/d4175b7c7da94dffbf39910f5457f6a6_631.png)

And well。

![](img/d4175b7c7da94dffbf39910f5457f6a6_633.png)

But how much time is the question， right， because we want to have a target frame rate？



![](img/d4175b7c7da94dffbf39910f5457f6a6_635.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_636.png)

We want to have a toilet framemate and want to sleep。For like our target。Minus our left D T。黑手。Sleep。

It's going to be equal to this。This is how much milliseconds， right？If you like， if。Sleep。

It's greaterer than a lot， let's see。We should sleep to sleep。And now I should do a2 T。Okay呃 lastT。

Inpartial from using H files， H files are also present in C。

 but were using in a compilation as a unity build， so just one compilation unit。

Which means that we don't really need。Age filing。This is in seconds， so we're going to multiply that。

By 1000。

![](img/d4175b7c7da94dffbf39910f5457f6a6_638.png)

And， we should be。And we should be in frames。

![](img/d4175b7c7da94dffbf39910f5457f6a6_640.png)

Okay， now we are at fruit 16 frames。

![](img/d4175b7c7da94dffbf39910f5457f6a6_642.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_643.png)

Oh。嗯。Is that correct， though？可以。Are you using the paid version no。

 this is the free version of far coder。I don't really like spending a lot of time configuring tools and stuff。

 and this version is very good， so it's good enough for me at least。But down the line， I do want to。

 I don't know study how to customize that because there are a few things I want to do。

 like not too much， though I really like the way it's set up。But this just for the record。

This is versionion。F。0。28。The latest versions changed the couple of things I didn't like。

So I kept at a 28， so the whole visual thing that highlights where you are and the parentheses and the races and things like that。

I just think turned to a salad for fruit salad， I don't like that。

 So the first thing I have to do when I download the the when I pay for the customizable version is to go back to this version and I don't know there are some shortcuts that I don't know what happened like。

Control shift key。To close panels doesn't work anymore， not sure if it changed。

 I couldn't find to what， and I suppose you are really to use the supposed to use the customizable version in the latest version so I just kept at 28 yeah。



![](img/d4175b7c7da94dffbf39910f5457f6a6_645.png)

Yeah， well， let's see our print。 Let's see。Yeah， so we measuring wrong， we're getting 14 and zero。

 we're getting like we're flipping every other frame。



![](img/d4175b7c7da94dffbf39910f5457f6a6_647.png)

Because the counter， let's the ending profiler flip。That's okay20 here。I might try it someday。

 but I like sublime very much。Yeah， I mean， editors。

 editors should be just what you're really comfortable with。啊。So unless you're unhappy。

 and in this case you should really force a change。

 but I don't think people should force a change unless they。

Really I don't like because they pretty much do the same thing if you're fast。In your editor。I mean。

It's perfect， that's the point， that's the point just to program fast。

We set the DT and then we do the last counter here。Okay， so we surely measure that。

We should really get the performance counter。For the last counter， again， absolutely。还有。



![](img/d4175b7c7da94dffbf39910f5457f6a6_649.png)

🎼Yeah。

![](img/d4175b7c7da94dffbf39910f5457f6a6_651.png)

啊。But actually， I think we should do this whole thing。



![](img/d4175b7c7da94dffbf39910f5457f6a6_653.png)

For some reason I got a negative number first， Oh yeah， because the first。



![](img/d4175b7c7da94dffbf39910f5457f6a6_655.png)

First one takes some time， that's okay。Current time。And I add the current time down here。

 Last date is gonna to be the second elase from the last counter。And I be from the。Okay。

Let me think about that today I'm very good at thinking。Okay。We calculate the DT。Let's do the。 Yeah。

 doesn't matter， okay。And then we see how much we should sleep and then we probably sleep。Then。

After he's left。We have to set the last counter again， so last counter。Pair performance counter。

And the current time。This should really be。This should be the T T。Before。Sleep？Okay。😊。

And then we get the last counter， and then we do the 4DT。Okay。Second e lapse with last counter and。

We don't need， we don't need this guy anymore。Cronment culture。Yeah。Well， actually。Lastty tea。

 How much。From the last counter。 Yeah， okay。

![](img/d4175b7c7da94dffbf39910f5457f6a6_657.png)

So I think we are sleeping the correct amount， yeah， 14。🎼15。9。



![](img/d4175b7c7da94dffbf39910f5457f6a6_659.png)

🎼4，10。So。I suppose now that we have a precise frame rate。C。😊，And we's going to make a small ran here。

We should really try to have consistent frame rates。Because we spent like， I don't know。

 40 minutes a day trying to make our animation work。We have inconsistent frame rate。

And that's just a huge headache。

![](img/d4175b7c7da94dffbf39910f5457f6a6_661.png)

If we can。🎼Like we have now， lock our frame rate。🎼And， and we can lock， because。

If you're running at a 4K， I mean， you could probably test on other pieces and stuff。

 but we were running at 4K。And we are actually sleeping three to four milliseconds per frame。

If we are doing this。We can pretty much assure that our game will run at this frame rate。



![](img/d4175b7c7da94dffbf39910f5457f6a6_663.png)

But here's the thing， if the guy has a super high frame rate display。

And theirs local computer is going to be really problematic。I mean。な？If he has like a。

 I don't know if there like 200。120 Hertz 4K display。

But if he does have that and he plugs in a very slow video card。

 our animation is going to be really crazy。I'm not sure we could lock。Well。

We could since we're not actually sync to the virtual blank。



![](img/d4175b7c7da94dffbf39910f5457f6a6_665.png)

🎼It could give the game like a 60 FDS like right now。😊，But I'm just going to write a comment。



![](img/d4175b7c7da94dffbf39910f5457f6a6_667.png)

For the target。B and like。Get user。嗯。Why are you using farcos that of them？

That's a load to the question， dude， you yout know the load to question fallacy。

 you're implying that them is better than forcoders。I'm just about to start playing more。

 a tax editor or I'm just kidding。I don't know， man， I like it way， way。

 way better if things way easier to use。And I haven't spent too much time with him。

 but I guess that's the point of the editor， right。

 you don't want to spend too much time on the editor。All you want to do is like。

Get some go like get user。Refresh， rate， That's pretty easy。Things we can do that later on。

So I suppose now we can safely say。Me， safely is a hard bird。We can say。That。Later given it。道。

But now that we are allowed to have existing frames per second and we sleep properly。

We can forcode is very easy to customize too exactly。

Fort codeer has a it's pretty much open to do whatever you want is to do。So I'm not doing。

 much customizations or I like customizations that all already。But， yeah。

If you are into getting exactly how you want， forcoder can be turned to whatever you want literally。

Yeah。

![](img/d4175b7c7da94dffbf39910f5457f6a6_669.png)

Okay。So finally。Finally we got to a betterpointt， I think I'm going to have to change the value little。

 but now that we are。

![](img/d4175b7c7da94dffbf39910f5457f6a6_671.png)

Locked artistic 60 frames per second and we were not paying and we didn't get。

Full frame rate independence in terms of animations。So in the spring。

 I'm going to play around with the values just so we have what we want。

So now I don't think I'm going to clamp this guy off。



![](img/d4175b7c7da94dffbf39910f5457f6a6_673.png)

And let me try to move this guy a little bit so。Have。Don't know Vm。

 but I am from Iax and this is a nightmare。Yeah。

![](img/d4175b7c7da94dffbf39910f5457f6a6_675.png)

Yeah， I mean， editors， man。They're supposed to just make your hard life really easier。

 they would be like。Hard to learn how to use it for the first time and things like that。DT0。



![](img/d4175b7c7da94dffbf39910f5457f6a6_677.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_678.png)

let' see。Let me turn on this guy again。So we know how much we have with lag。



![](img/d4175b7c7da94dffbf39910f5457f6a6_680.png)

是。

![](img/d4175b7c7da94dffbf39910f5457f6a6_682.png)

Okay， the legss pretty good， so I think we can go back。2，30。有改。



![](img/d4175b7c7da94dffbf39910f5457f6a6_684.png)

Okay， that's see。

![](img/d4175b7c7da94dffbf39910f5457f6a6_686.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_687.png)

What。😮。

![](img/d4175b7c7da94dffbf39910f5457f6a6_689.png)

Find Case， this guy。

![](img/d4175b7c7da94dffbf39910f5457f6a6_691.png)

I surely make it more。

![](img/d4175b7c7da94dffbf39910f5457f6a6_693.png)

Yeah。

![](img/d4175b7c7da94dffbf39910f5457f6a6_695.png)

Maybe 30 was just too much， I don't know。

![](img/d4175b7c7da94dffbf39910f5457f6a6_697.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_698.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_699.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_700.png)

I'm going to make that a little bit snaper， maybe I'm just going to go back to those numbers you see。



![](img/d4175b7c7da94dffbf39910f5457f6a6_702.png)

Oh， this is too snapy。

![](img/d4175b7c7da94dffbf39910f5457f6a6_704.png)

Next very like。See。

![](img/d4175b7c7da94dffbf39910f5457f6a6_706.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_707.png)

A bit better。Let's try 30 now。

![](img/d4175b7c7da94dffbf39910f5457f6a6_709.png)

AhI' know， man， it's hard to get those values， right？



![](img/d4175b7c7da94dffbf39910f5457f6a6_711.png)

They were right when we were only at two meiseites per frame。



![](img/d4175b7c7da94dffbf39910f5457f6a6_713.png)

Like let's try removing this value just we have just one to play around with。



![](img/d4175b7c7da94dffbf39910f5457f6a6_715.png)

Coting for a codeder Comping Vi Studio， yeah。

![](img/d4175b7c7da94dffbf39910f5457f6a6_717.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_718.png)

Well， we are actually compiling here。We are technically compiling in codeder with Viual Studio。

But I'm running on the Vi studio。I could set a run shortcut in forcut that's pretty easy。



![](img/d4175b7c7da94dffbf39910f5457f6a6_720.png)

But since it's nice， I have de buggging information。I just know。I just do that anyways on a。



![](img/d4175b7c7da94dffbf39910f5457f6a6_722.png)

Onut to you。Okay， so this is nice， let me remove the clamp。



![](img/d4175b7c7da94dffbf39910f5457f6a6_724.png)

Let's see。 How do we look。And this is a little bit better， but maybe like 15。Yeah。

 we're doing like half。

![](img/d4175b7c7da94dffbf39910f5457f6a6_726.png)

I don't know。 I don't know。 I don't like these numbers。



![](img/d4175b7c7da94dffbf39910f5457f6a6_728.png)

Okay。I like this one better。응。We implement some good Tri values in game。Not for this game。啊。I mean。

That was kind of a nice idea。But， honestly。When I， when I do like a full game。

 because this's not supposed to be a game engine just to be like just this quick game。啊。

But if I were to do like a full game engine at this point。I would certainly try the。

The game is a separate file thing， to game a separate code。

So so I could just recompile the game inside the game。We know C++， yes， they do know C++。

I'm not the most modern super close guy。ButI do know some of it tonight。When you go to like crazy。

Copy， move， semantics， whatever。I'm not 100% if I to live with it。But I don't know， man。

 it's just too confusing and since I don't do u。I don't work PC++。And this just for a fun。

 I'm not going to use that if I were to use a C++ game， I would like very much like a scene。Project。

 but with a couple more featureses。Yeah。Like， not crazy。



![](img/d4175b7c7da94dffbf39910f5457f6a6_730.png)

All great stuff。

![](img/d4175b7c7da94dffbf39910f5457f6a6_732.png)

In order what I think you're going to try just to get that movement a little bit tighter。

I'm going to try， get the moving， going to be like 100% squared like。



![](img/d4175b7c7da94dffbf39910f5457f6a6_734.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_735.png)

Like if I move this guy to one and this guy to zero。



![](img/d4175b7c7da94dffbf39910f5457f6a6_737.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_738.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_739.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_740.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_741.png)

It didn't compile。

![](img/d4175b7c7da94dffbf39910f5457f6a6_743.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_744.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_745.png)

I' me try cranking these numbers really high。

![](img/d4175b7c7da94dffbf39910f5457f6a6_747.png)

Just okay like really tight controls。

![](img/d4175b7c7da94dffbf39910f5457f6a6_749.png)

然呢。Yes。

![](img/d4175b7c7da94dffbf39910f5457f6a6_751.png)

Not like this。And I'm pretty sure these guys are the problem。



![](img/d4175b7c7da94dffbf39910f5457f6a6_753.png)

Oh， man。See， because。We were going way too much to that direction， way too much。

This is how much we want to move。Yeah。Yeah。

![](img/d4175b7c7da94dffbf39910f5457f6a6_755.png)

Not cool this thing。

![](img/d4175b7c7da94dffbf39910f5457f6a6_757.png)

🎼Okay。So what I want to do。

![](img/d4175b7c7da94dffbf39910f5457f6a6_759.png)

Is that make this guy move faster？可走。s。But also， this guy should be。で well。



![](img/d4175b7c7da94dffbf39910f5457f6a6_761.png)

The problem is for it takes a long time to run and just stop running the program。



![](img/d4175b7c7da94dffbf39910f5457f6a6_763.png)

🎼オッケー。🎼This is this is the。

![](img/d4175b7c7da94dffbf39910f5457f6a6_765.png)

Ohow that's weird， let me turn on all right。Center guy again。



![](img/d4175b7c7da94dffbf39910f5457f6a6_767.png)

Why are we not spacing bes？🎼Why would I break out？

![](img/d4175b7c7da94dffbf39910f5457f6a6_769.png)

Maybe I'm using the wrong position， I should be using the target P。Yeah， probably。 I's see， high。来不。

Yeah。😊，HP。

![](img/d4175b7c7da94dffbf39910f5457f6a6_771.png)

First。Okay， perfect。But now this guy is supposed to be a little bit of let's go back to the spring。



![](img/d4175b7c7da94dffbf39910f5457f6a6_773.png)

I know， find tuning controls like this。Can take a long time， but this is like a nice lesson。

 We should have locked the frame rate。

![](img/d4175b7c7da94dffbf39910f5457f6a6_775.png)

Way earlier。Okay， I think I like this guy。发呀。

![](img/d4175b7c7da94dffbf39910f5457f6a6_777.png)

And。And the particles paw。Which is the let's say trail。Yes。The amount of fartics is fun。Yeah。

Based on the ball Dp。USBT。Let's try playing around with that。



![](img/d4175b7c7da94dffbf39910f5457f6a6_779.png)

Actually， it's like we get less fewer particles。

![](img/d4175b7c7da94dffbf39910f5457f6a6_781.png)

嗯。里边是 justse个GT。And get a constant amount of particles。Well， it's supposed to be the opposite right。

 so it's going to be like one divided by this BT。

![](img/d4175b7c7da94dffbf39910f5457f6a6_783.png)

🎼So干。

![](img/d4175b7c7da94dffbf39910f5457f6a6_785.png)

So， this like。嗯。See。

![](img/d4175b7c7da94dffbf39910f5457f6a6_787.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_788.png)

Print。I can print the speed tea。And we need the trailponwner to。嗯。The true honor。We increment that。嗯。

Let's see Sp。

![](img/d4175b7c7da94dffbf39910f5457f6a6_790.png)

Let's see。

![](img/d4175b7c7da94dffbf39910f5457f6a6_792.png)

好。That 0。So， maybe we should do like。

![](img/d4175b7c7da94dffbf39910f5457f6a6_794.png)

还是。

![](img/d4175b7c7da94dffbf39910f5457f6a6_796.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_797.png)

It's mapped into range normalized， so it's zero。It's from zero and one。ItFrom zero and one。

So if I just multiply that by。By a small number。

![](img/d4175b7c7da94dffbf39910f5457f6a6_799.png)

We've had a lot of partners。

![](img/d4175b7c7da94dffbf39910f5457f6a6_801.png)

Okay， but the problem is the faster it is， the fewer part because we have。

 so we have to do the other way around so one divided by speed。



![](img/d4175b7c7da94dffbf39910f5457f6a6_803.png)

And we've got a lot of more this， I do even more。

![](img/d4175b7c7da94dffbf39910f5457f6a6_805.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_806.png)

Let's do a lot of particles。

![](img/d4175b7c7da94dffbf39910f5457f6a6_808.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_809.png)

Why don't have in， that's for the break point。5， 73， let's do like five。



![](img/d4175b7c7da94dffbf39910f5457f6a6_811.png)

Great以。The game。Where's the game game？是。

![](img/d4175b7c7da94dffbf39910f5457f6a6_813.png)

Our speed is 0。That's no good。AndI'm going to make it the deepbu build again。



![](img/d4175b7c7da94dffbf39910f5457f6a6_815.png)

That's why we didn't use the。This guy。The ball D P， the length。The end of 50。

I don't know why this guy' is zero。We see the length squared。Slpe this huge number。Oh it's。



![](img/d4175b7c7da94dffbf39910f5457f6a6_817.png)

Okay， so it can be zero， so zero is the normal speed。So I'm going to do like。I know one。Plus。

On speed。Of2 of one， it's going to have twice as many particles。啊行嗯。So this is。

This is zero nationally1， one divided by one。Times is a very small number， well let's do something。

1 plus 0， if we are。Ligger， we should be like two or something like that。In this case。

 be one divided by two。Time to the small number。 So would should have than。 Yeah。

 this sort about right。

![](img/d4175b7c7da94dffbf39910f5457f6a6_819.png)

不行。

![](img/d4175b7c7da94dffbf39910f5457f6a6_821.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_822.png)

Yeah， I think this is kind of reasonable。

![](img/d4175b7c7da94dffbf39910f5457f6a6_824.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_825.png)

。It's less than 0。

![](img/d4175b7c7da94dffbf39910f5457f6a6_827.png)

I mean。This is a very small。Number。The trade respond should be like。事。It's like negative one or so。

Turn out to be 0。1。Speed is 0。哇。What。This thing is one。What。😮，Times this very small number。Is one。



![](img/d4175b7c7da94dffbf39910f5457f6a6_829.png)

Oh my God， I type， I don't think I have ever done this typo before。That was a stupidty， man。

It be like this thing。

![](img/d4175b7c7da94dffbf39910f5457f6a6_831.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_832.png)

Wow。Yan。

![](img/d4175b7c7da94dffbf39910f5457f6a6_834.png)

Okay。Let's。Wow， that was really stupid。

![](img/d4175b7c7da94dffbf39910f5457f6a6_836.png)

So should have like very few particles。I should one party books。I do。



![](img/d4175b7c7da94dffbf39910f5457f6a6_838.png)

嗯。Yeah， but I feel like this should be really small anyways。



![](img/d4175b7c7da94dffbf39910f5457f6a6_840.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_841.png)

Like。

![](img/d4175b7c7da94dffbf39910f5457f6a6_843.png)

是。

![](img/d4175b7c7da94dffbf39910f5457f6a6_845.png)

Just for display purposes。

![](img/d4175b7c7da94dffbf39910f5457f6a6_847.png)

Se this number。int1。Then go to 0。6， go to 0。8， 。9。

![](img/d4175b7c7da94dffbf39910f5457f6a6_849.png)

Okay， this is about right， maybe we should do like point times four。



![](img/d4175b7c7da94dffbf39910f5457f6a6_851.png)

。in1。🎼You5。And now we do have a limit。I don't think I like that。う。Because。

We are responding maximum one per frame。And it since we are framemates like。60 frame per second。

We can see the trail like frame or frame。

![](img/d4175b7c7da94dffbf39910f5457f6a6_853.png)

What I think I'm going to do。I spun a particle。And the size x。Its actually。Plus， the speed。



![](img/d4175b7c7da94dffbf39910f5457f6a6_855.png)

TX。

![](img/d4175b7c7da94dffbf39910f5457f6a6_857.png)

し。Yeah， see what happened now the particle。

![](img/d4175b7c7da94dffbf39910f5457f6a6_859.png)

It comes like taller or wider， I suppose， cancel。泡你啤酒。So it feels the home app， oh that was it。

 that was it， yeah。Okay， that was like the best solution from today because today's been a crazy day。

Crazy the senses that。Not much stuff in actually。Happening as we expected。

 but I think by the end of the day。We're going to turn out okay。

 so we managed to have lock stream read。Yeah， this was。



![](img/d4175b7c7da94dffbf39910f5457f6a6_861.png)

I like this， it's pretty good。Okay。So let's remove the print。



![](img/d4175b7c7da94dffbf39910f5457f6a6_863.png)

And I think we are good to go。Now。

![](img/d4175b7c7da94dffbf39910f5457f6a6_865.png)

And me also remove this guy。Let's now improve the levels。



![](img/d4175b7c7da94dffbf39910f5457f6a6_867.png)

First of all， the Pg level。

![](img/d4175b7c7da94dffbf39910f5457f6a6_869.png)

The breakouts， nice distance， I think the other one。The wall level。

I should really make Y I that a little bit。That's at by 。8。



![](img/d4175b7c7da94dffbf39910f5457f6a6_871.png)

To make it a little bit easier to get the ball back should be the other way let's try zero。

To get a ball。Like up， yeah， this looks a。It's going to increase the speed of the game。

It more interesting。

![](img/d4175b7c7da94dffbf39910f5457f6a6_873.png)

Okay， I like that。This one's alreadying and the po sitting， the pong game。Let's see why offset。

 let's see which one's the Y offset。I guess it's this guy。We're doing -32。 Let's try -12。

 That's getting weigh。

![](img/d4175b7c7da94dffbf39910f5457f6a6_875.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_876.png)

🎼Yeah。This would be like the extreme but。啊。回去。😊，Get him like。A lovedown。嗯。



![](img/d4175b7c7da94dffbf39910f5457f6a6_878.png)

Maybe like。28？

![](img/d4175b7c7da94dffbf39910f5457f6a6_880.png)

一。

![](img/d4175b7c7da94dffbf39910f5457f6a6_882.png)

And also， in the simulate level， let's see。The pondg level。decrease his tele us。



![](img/d4175b7c7da94dffbf39910f5457f6a6_884.png)

Now this is frightening。Probably try to get of his twitchy movement。Dude， now this is awesome。

Now it's pretty much impossible to get it all behind him。Y， I managed to get that。🎼お气。



![](img/d4175b7c7da94dffbf39910f5457f6a6_886.png)

I can turn out the profiler。Because we don't need that anymore。



![](img/d4175b7c7da94dffbf39910f5457f6a6_888.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_889.png)

I kind of liked that。It it have been a bit too much。



![](img/d4175b7c7da94dffbf39910f5457f6a6_891.png)

But I kind of like。Yeah。To get the Paul re from here。Nice哦。🎼Okay。Okay。I think P is now way。

 way more interesting。Yeah。Yeah， now I have to be really careful now。

Because that area had just turned into a death trap。Okay， thats strong box。Nice。



![](img/d4175b7c7da94dffbf39910f5457f6a6_893.png)

It's kind of funny in terms of progression because it kind of feels like he's getting away from me after I try a lot of blocks because actually he's trying to get the center on the ball。

 but the center is empty。

![](img/d4175b7c7da94dffbf39910f5457f6a6_895.png)

So that was enough to make fun way more interesting。 in no， I don't think I need anything else。

 I was thinking about。Well， independent block movements could be interesting。

But it could make like the p influence the ball speed， don't need to do this， man。



![](img/d4175b7c7da94dffbf39910f5457f6a6_897.png)

The idea for the punk independent block movement， well。It's supposed to be really subtle。

It's like each block。Has a tiny bit in the leg。I want to get reach up。



![](img/d4175b7c7da94dffbf39910f5457f6a6_899.png)

Read of this preachy movement。So I'm going to say if the ball。P is greater than the enemy P。32 guy。

I truly do like I'm only going to accelerate。If the distance is greater than something so。DDp。

Looks awesome， thanks， man。You know， if you want to watch the whole process of creating the game from the very first line of code from scratch。

 you can go to the YouTube channel。

![](img/d4175b7c7da94dffbf39910f5457f6a6_901.png)

Which is YouTube。 on slashdm Zd。

![](img/d4175b7c7da94dffbf39910f5457f6a6_903.png)

And then you can download and you can watch from the very first episode and see how we got there from nothing。

 And I just posted。

![](img/d4175b7c7da94dffbf39910f5457f6a6_905.png)

You see on my Twitter。I' see Twitter。靠。

![](img/d4175b7c7da94dffbf39910f5457f6a6_907.png)

On my Twitter， I just posted a。I couldn' name to。I'm not sure about that。Yeah。

 just this is the progress of the game so you can see how it was like from the very first episode all the way through last episode。

So the improvements we got and then we added like bitmap and then particle systems。Yeah。

 and then audio。

![](img/d4175b7c7da94dffbf39910f5457f6a6_909.png)

Yeah， man， and you can download the game for free on H IO， which is Dan Zd。h。io。



![](img/d4175b7c7da94dffbf39910f5457f6a6_911.png)

And yeah， just click download here， you can just go to the download and need to pay but you are welcome to give me a tip。

 then you can download the game and the source code for free， you can download the whole source code。



![](img/d4175b7c7da94dffbf39910f5457f6a6_913.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_914.png)

And I'll do whatever we want with it。

![](img/d4175b7c7da94dffbf39910f5457f6a6_916.png)

Okay。😊，The Po independent block movement。

![](img/d4175b7c7da94dffbf39910f5457f6a6_918.png)

Oh yeah， I was going to fifth sky。 So if the ball。If the distance so length squared。啊。Well。

We actually just need to subtract these guys。Subtract these guys。Days I'll check it out， no problem。

 man。

![](img/d4175b7c7da94dffbf39910f5457f6a6_920.png)

Let me link you to the YouTube channel that you can。Can go from every other guy from there。



![](img/d4175b7c7da94dffbf39910f5457f6a6_922.png)

If I subtract these guys， I'm to get the absolute of this。And let's see。

Let's say if it's sc it then Chaanttan is going to be too much but。I guess during three。Print。

This guy。😊。

![](img/d4175b7c7da94dffbf39910f5457f6a6_924.png)

Let's see the value。Here we have。

![](img/d4175b7c7da94dffbf39910f5457f6a6_926.png)

I have zero。🎼Have 17。No wasn't entirely bad。Oh crap， I got slow， slow movement looks pretty cool。



![](img/d4175b7c7da94dffbf39910f5457f6a6_928.png)

Yeah， I think I'm just going to make like less than six。



![](img/d4175b7c7da94dffbf39910f5457f6a6_930.png)

Let's try playing。You see high feels？

![](img/d4175b7c7da94dffbf39910f5457f6a6_932.png)

And I you also remove the print。Because it's really distracting， having all those numbers。



![](img/d4175b7c7da94dffbf39910f5457f6a6_934.png)

Yeah， look at that。I think this is going to the H page now， oh， he's trying to get away。Oh。

 it's going to be hard。Okay， got him。我来就十二哥than thanks。😊，Have a nice game。

I don't know which game is in today。哎，你在里面聊。

![](img/d4175b7c7da94dffbf39910f5457f6a6_936.png)

Man， I really liked the pung， the pong was kind of the worst game mode now is pretty much one of the best。

That's awesome， awesome。Now。Let's do。

![](img/d4175b7c7da94dffbf39910f5457f6a6_938.png)

The space invaders getting faster as time moves， I think they'll be the only thing we need because space invades are pretty cool as of now。

Gallla best what that fuck okay。So have a nice one， man。I probably know these people。

On the beauty side screaming， if it's a go or not。

![](img/d4175b7c7da94dffbf39910f5457f6a6_940.png)

Really， really cool， man。 I also want to add the few stuff maybe today like。This thing。

Then I going leave collision for the next time for tomorrow probably because this is going to be hard and we always spend a long time today trying to get the consistency。



![](img/d4175b7c7da94dffbf39910f5457f6a6_942.png)

Oops， press that wrong button there。Try to get the consistency。



![](img/d4175b7c7da94dffbf39910f5457f6a6_944.png)

Oh， ash should probably go back。To the optimized build。Because。We are not 100%。

When we are not optimized？Minus02。あ。Ignoring minus over2。



![](img/d4175b7c7da94dffbf39910f5457f6a6_946.png)

Oh， I type zero2， okay。Awesome， really， really cool， so。😊。



![](img/d4175b7c7da94dffbf39910f5457f6a6_948.png)

Let's go to the space invaders space。That's invaders， yeah。And they move。But this movements target。

Yeah。Movement。Target， oh， we are already decreasing。 and we already did that。Okay。



![](img/d4175b7c7da94dffbf39910f5457f6a6_950.png)

嗯。😊，T that about it， see。

![](img/d4175b7c7da94dffbf39910f5457f6a6_952.png)

Oh yeah， I remember when we did that and it got super fast by the end。

 you're going to be fine tuned it。Yeah， finally， come。Love of the visual effects。

 it's amazing what you can do some。That was one of the goals。W it goes on this project？

So get way better gainfield if you go to my HIO page。

You can see the progression of my games from scratch because when I used to use engines。

 it was really easier to do this sort stuff of like， I mean， easier in terms of the perception。

You could probably just add a particle system and attach that to the ball。

And then it would already look okay， at least， okay？But now when you do that and seed。

We need a special eye for that and that's really， really valuable I think。

 even if I go and do another project with an engine。Having that eye， which I'm not going to lose。

It's going to really help you even in those scenarios now。

 so you can see on the HIO page the progression。Which was like the very first game I did there in sea。

Did I uploaded。Felt really bad because I didn't have like cool movement and things like that and the other one felt a little bit better。

And this one， man I went all in in terms of visual effects， I mean， an animation two I mean。

 this looks pretty cool the spring thing。Whenever we hit。Whenever we hit the walls。

 also the audio is pretty cool， I think it really adds to the experience。Yeah， particles， oh man。

 missed the ball。And I actually tried it。Another thing that we could do that we could increase the speed for every guy we hit on the space invades。

Not sure that's going to be super hard， though。I think I'm going to do that。



![](img/d4175b7c7da94dffbf39910f5457f6a6_954.png)

I'm going to do that。 maybe a bit。Too much。But what the heck？诶啊。Let's see we have the block。

The stride block blocks the stride。Blocks destroyed。Block destroyed。嗯 test flow condition。

I'm going to say like level。你知来。Level scored changed。Yeah。So。

And then we'm going to go switch on the current level。And in case it's in level。In a video。

 what is it called Oh， that was a pretty bad name having the。Ting the number， yeah。

That was a very bad idea I。Okay。Now it's going to be really hard， I think。That will score changed。

So maybe I'm just going to decrease that a bit。And also decrease the sky bit。Let's按 let's。Evaderers。

It would be level states。期在。Movement target。

![](img/d4175b7c7da94dffbf39910f5457f6a6_956.png)

こち。

![](img/d4175b7c7da94dffbf39910f5457f6a6_958.png)

爱起。Yeah， I think it's going to be possible because we just try a lot of blocks。

I'm going to test this game a lot off screen。If anyone。好的。And if anyone wants have ideas。Tms of。

This fuel path that we're doing now。Feel free to。Tll me there。哎呦。It's not getting out of hand。Yet。

Which may be a sign that we should still make it。Oh， but。No， yeah， it is correct。



![](img/d4175b7c7da94dffbf39910f5457f6a6_960.png)

I felt like the frame rate dropped。No that even if you don't have the profiler of reing， let's see。

地铁。Even if you don't have the profiler。I'm going to draw the DT。Yes。Profilr。

Maybe a bonus that makes a ball a lot bigger and something， well， the ball does get bigger。



![](img/d4175b7c7da94dffbf39910f5457f6a6_962.png)

The more guys are destroyed。So if I get a commentt， let's see if I can get a comment。

So I got a yeah Mr。 comments。I got a comment。The ball got a lot bigger， maybe we can increase that。



![](img/d4175b7c7da94dffbf39910f5457f6a6_964.png)

Let's try making that a little bit bigger， we played around with that。About。Have size C。Size see。

Youal 75。 Let's see。We decrease the ball。 where is that？Riner balls。Oh， it should be like here。

 so let's see。Size。あ that。No fall alert， Oh， it wasn't a fall alert。Oh， man。

Is there anything on my part that I should do？Or are that just like Twitch doing？

Okay increase ball speed， yeah， let's do a little bit more。



![](img/d4175b7c7da94dffbf39910f5457f6a6_966.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_967.png)

Twitch， yeah， okay。Yeah， see now it's more evident。If you're going to keep like that。

 what do you think， man？ADM244， what do you think going evolve this big？

I think we're going to keep it like this that's cool yeah， I think that's better。

And it's funny how mother it gets when it gets to us。



![](img/d4175b7c7da94dffbf39910f5457f6a6_969.png)

Oh， that was awesome。Yeah， I really liked it， really liked it， thanks for your suggestion man。

So now I'm going to add some animations with it power up and power down。I think that can be cool。

So we have like the power， it's called a power block， I suppose。Yeah， for every power block。

 it's not inactive。We just。Make a move downwards。And let's see， that's animated。

I think I want to do like yeah。Aation like this。So I'm going to add to the levels let's see if you've got a block。

Power block。Let's add a。MMT。I'm into the p block， andT。Plus equals the Dt。

You have the power block Academy T。It's greater than one。She also do like。And am in the direction。

Yeah。Then whenever we on the pickup， let's see。U。Spawn。It'spon power block。Let me set。

The anum direction to。true。Let's see and。呃。And add direction。They want to do the MT。Okay。

 and then like， if。Car block and。Ed， I'm going to sleep because it's kind of like good night。 Thanks。

 man。 Thanks for dropping by。 Thanks for your suggestions。 Have a nice， Have a nice night。😊。

What is it called enemy add direction that's a pretty bad name If we're supposed to add direction。

 I do this。Else。Gona do。で。So we're going to add here， we're going to subtract。And it's。

Les than are equal to zero。And this， if it's greater to all you growth。We then are equal to one。

If that's the case， we're going to switch the direction。谁先。😊，Okay。

 but now this is the important part。嗯。Let's just try， do we have the half size？No， we don't。

Is it hard coded， check out？Yeah， it's hard call the power block have size。嗯。😊，So that's。

 for some reason。The control。Coma shortcut we change this panel， stop working。So kind of sucks。

See the power block。系。30。Not sure where is it declared？It's in the game。Bye。Yeah。Well， not really。

That's searching the whole project for power block。F size。It's in the levels。

 but I couldn't find for some reason。So every power block now has its size。太上。Oh my God。

 so many hours。は。I whenever never respond。Power block。I'm also going to set， oh。

 I forgot what was the default。Value。To， yeah， it was being set。So。I'm going to set the half。

Size to2。Now have brought have a。million other problems。Animimate direction， on a member。

Let's call that。P block， c， yeah。DoCa there。don't need to do this guy anymore。

And when I received power of law。Size going change for power。B。Okay。Okay。



![](img/d4175b7c7da94dffbf39910f5457f6a6_971.png)

🎼We shouldn't have any difference。Well， I can't see a car line。Do nice around sounder。



![](img/d4175b7c7da94dffbf39910f5457f6a6_973.png)

Not surround but like stereo， what text error you used before for color by the way。

 I started using Emax。When I was learning。But I use that for a very short amount of time。

 Then right off the bat， I switched for code。 I had been coding。For a long time， man， I mean。

 I started for real when my game released when my big commercial game。



![](img/d4175b7c7da94dffbf39910f5457f6a6_975.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_976.png)

Which was it's making two a years now。So in my game iss called Elizaus Hunt。Can I release that game？

I spent three and a half years developing it when I finally released that on August 2017 so almost two years。

Then I started learning program for Rio in C+ and C and stuff。Then I started using ImX。

 but just for like a couple of months， then I learned about fourcodeder and then I switched。

So I'd say that， that was my main editor， really。Pretty cool。Pretty cool。



![](img/d4175b7c7da94dffbf39910f5457f6a6_978.png)

Okay呃。Let's see now。

![](img/d4175b7c7da94dffbf39910f5457f6a6_980.png)

Now I should be able to play around with this right， so I'm not sure。

 not sure how I'm going to do this。Going to do like。嗯。Here。You're going to set。Power blow啊。

Power block。Fs。 x and2。Increase。不然还是。三m跟你。And we're going to increase one minus the Num1 minus。

AnmT because I want that to be to start slowly and then。Go really， really big。

 We're going to do one minus。 It's going to start out as one。 and then it goes all the way to 0， so。

So I' I actually just。Let to increase this guy time for Dt。 Not sure if that's a good number。

 and I have to execute a man with that。 and then here the same thing， but。



![](img/d4175b7c7da94dffbf39910f5457f6a6_982.png)

来次。I don't know， man， not sure if thiss going to look good or not， I's see。And looking forward。

So power block。阿 see。

![](img/d4175b7c7da94dffbf39910f5457f6a6_984.png)

Okay， that was cool， but that was way too slow。Let's do like。And。

I kind of liked the size that it got。7。Anim speed multiplier。Maybe're going do life。

And certain Note plus plus it's not good， but it gets the job then and I'm not comfortable with it。

 try for for a bit free version， but close it since it has to learn how to use it a lot of time。

 Do you really think it takes oh， because you don't， you're not used to like。😊。

To the control space scheme， I suppose。You're used to the shift movement like this， right？

Self control space。move yeah， that's the big difference， man。Yeah， for a coder。

 the the newest version， which is u。30 I suppose 4。0。30。It has a mode that。Thatta does this。

sure lot messages。Yeah， in fact。No哎。Yeah， it's going to have to go to the latest version。

And it works like this so we can set that to work like， but I don't know， man。

I really liked this system。Once I got used to it it really took some you got used to it。

 but EmX took a way longer time to get used to that。



![](img/d4175b7c7da94dffbf39910f5457f6a6_986.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_987.png)

So I suppose when I moved to Forcoder， I was like really comfortable。So yeah， that's a bummer。

That may be a good investment。Maybe should you like some research。To see if it's worth。

If that scheme is really faster or not？ok。That was like super cool， but that was cool。Okay。

 now this is gonna be。

![](img/d4175b7c7da94dffbf39910f5457f6a6_989.png)

Yeah。😊，Yeah， kind of like that。But I think I'm going to make it like 0。3。

And then maybe you're going to move that a little bit。And if you do some research。



![](img/d4175b7c7da94dffbf39910f5457f6a6_991.png)

Thing that may be worth。It's like， yeah， we're really close。



![](img/d4175b7c7da94dffbf39910f5457f6a6_993.png)

I mean。Yeah， I don't know if' a doctor or I to put a cap of face。But we are close。

We just finished doing this。And I want to add like more another level， like thetes level。

 we do have to do some collision work， I think I'm not sure I do have to do some more plane now that the frame rate is locked。



![](img/d4175b7c7da94dffbf39910f5457f6a6_995.png)

I shouldn't really have to worry about that too much， I think。

But I am going to play a little bit more has Cap face a lot no idea why。Well， it is a nice face。

 I have to have to admit。😊，So the collision was acting weird in some rare circumstances。

So we do have to review that， probably next time T T。



![](img/d4175b7c7da94dffbf39910f5457f6a6_997.png)

So we certainly have to review the colleg。Actually， with theation， and I'm going to add a trus level。

We locked the frame rate， that was pretty cool。And then we're going to do more gameplay， let's say。

We are doing moneyplay， so more fuel stuff。Like skin shape。

Make menu start like this is going to be cool。In transitionition for the。



![](img/d4175b7c7da94dffbf39910f5457f6a6_999.png)

The transition for the menu to the game。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1001.png)

🎼で？That's gonna be a challenge because I haven't done anything like that with no engine。

 Usually an engine just style over spawn like a different widget like in unreal real then you can annovaimate inside the widget。

 things like that。 But now I have to do by hey clone man。

 I'm just about to to finish the stream So we' arrive a little bit late。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1003.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1004.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1005.png)

But we did do a lot of improvements now our frame rate is locked。So our movement is consistent。

And the pump level is way quicker， I think。🎼いつ？I just think。If I manage you get the ball behind it。

后面。Get away from there。🎼How light？They movement。Yeah， see that's。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1007.png)

呃。This is going to be review the size when yeah， this also has to be worked。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1009.png)

When we when I get up against the side， I added this size multiplier， which is going to feel really。

 really nice， I think。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1011.png)

I do have to change the position。Yeah。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1013.png)

You know what I'm going to do？

![](img/d4175b7c7da94dffbf39910f5457f6a6_1015.png)

I't know。Lookinging great yeah， I think those were pretty cool additions Oh we also added a small animation。

😊，I think I have to see that。To the winers， the ball size。

 thearrow man was about to see that an animation to the car up when it's coming down now it gets bigger and smaller。

つ。For some reason， I don't Yeah， see。That's pretty cool。Just试试。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1017.png)

Oh， did you see that？When we try to fetch from outside the screen boundaries。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1019.png)

哈。Our Biap renderer is wrong。That's interesting。Yeah。

 I'm going to just put a comment because I don't really think we care about that。But like。Our U V。

Ftch。Is。Wrong。Wrong， when。A bitmat。Goes outside。Those partially。Outside the area。Yes。😊。

Not considering。Yes， it is software render rendered everything， man， everything was well。

 there is one exception。Which is the PNng reader， We didn't write the Png reader。

 but everything beside the Png reader was written by ourselves。 and you can check out here on the。😊。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1021.png)

YouTubbe channel， it was on day one that we did see we did platform layer and software engineering programming。

 of course we did increment it later on like we did。Let's see we did rectangle。 Yeah。

 we did rectangles on。Day nine and bi maps on day 10。60th， dude， 60th B， 4K。4K man， that was。

 that was last stream。 last stream was all about optimizing。

 It was running at 60 milliseconds per frame， which is like。

 let's see how much of that is pretty slow， let's see。😊，It's oh my god， it's like 60。Is that right。

100 divided by system。16。6 fairs per second。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1023.png)

Yeah。What you got so far。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1025.png)

So yeah， we got at 61s played that 4K， so that past stream the streamre 16 was all about optimizing yeah。

And we got the biggest problem was the rotator rectangles。In the bitms。

 and we optimize that and we could also do a lot more。But I'm not going to worry too much about it。

 like I said， like you said， it's supposed the ship time by now。So this is what we have， man。

But you never know that you're using Excel。Yeah。哎。See the collision is permit， yeah。😊。

The information is pretty cool。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1027.png)

You know what thing I'm going to do？Can make a 3D game。Well。Do you mean from scratch？

I haven't done that， I've done 3D games using engines before。

Because I do know a little bit about Molly and animating and text， anything like that but。

It would be a lot of work to write 3D， I mean， depends on the 3D game right。

 but I do intend to do that， but not yet， so I do have to be way more familiar with that。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1029.png)

I'm going to add a small sound。Small sound whenever we。For the。For the power blocks。

I just may add also I'm going to change the player movement sound。You're a little more high pitched。

So I'm going to increase the guy， let's say to 9。2。And the power block， let's see， power。B。

 I'm also going to add a plain sound。I'm playing sound to that。Let's say call that sound。O。

K make a 3D single player RPG。By myself for me。I don't know， man。

 let me show you the game that I had made。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1031.png)

So this is the game I've made， it wasn't by myself though I did have a few friends helping me out。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1033.png)

It is 3D。But I didn't do that。From scratch， though， I used the rearranging。

And that's not an RPG its a top down shooter and a pather。I think arere now， pretty nicely you think。

So yeah， I have done that， but it takes a long time， I spent three and a half years making this game。

So if you want to make a 3D single play RPG。You are in for some。For some years of development。

Even if you do have a team， so that's why I'm doing since just a hobby for now。

 I'm doing like simplified games。Okay， now never respond the power blocks。Let's see。 Power blocks。

Think different。Nice advice。啊。s in the level， let's see when I spa the power block。

I'm going to accept。The sound。Target volume。Two one， maybe it wasn't a be too much。

But when I collect the power block。Just like power。I do like player。Coalition。

We do that on the power blocks。See yeah， if you collided with a player。

IfYou're colliding with the player， I'm going to set。The sounds to zero the target volume。Let's see。

 do we have a if it reached the end of the screen or we just ignore that？I think we just ignore that。

嗯，Our。Connected。Yeah， we do just ignore that。So that's weird。So what I'm going to do。Here。

In the very end of this guy， I'm going to be like if。Power block P。

t y is less than I don't know how much。Mus40。Let's try it。-30。If we manage that。

 we're going to set that。To inactive。Okay。Now I have to initialize the sounds。So。

Let's initialize the sounds。 Oh I should also， yeah， yeah， let's let's do this， let's do this。

All kind of。Where do we have our par blocks？I black。So for every power block。How many do we have？16。

 okay， that's enough。If I had like a lot， Imburnd probably increased。

Our audio playing capacity or 64 already。So initialized。Whenever we are initialized， I'm going to。

Is that the power block sound？To play sound。Oh， we have to do that。After we load the sounds。

Well sounds， it's called this。Power block sounds。And to play sound。 is's going to be this sign。

Sunshine。And I'm going set loop。I'm gonna set。你。I don't know。 Let's see。 what is it called fading。

Speed to two。And I think， oh in the source， yeah， this is what they're going to make pretty cool。

 I'm going to make these guys。Stereo， so said source X。

I don't know if you guys remember when we did this system。That was really cool。

 we're going to set that to the power block key dynamics。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1035.png)

So let's see， and things are going to wait too loud。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1037.png)

H。Yeah。😊，嗯。I'm going to set the sound。老你。Office sound。7实几个。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1039.png)

Yeah。And one it' be way too loud， but let's see。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1041.png)

Okay。Apparently。We don't have a sound。Play sound。Let's debug that。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1043.png)

Because。That should been pretty easy to do。Let's do game 2 45。Of the game 245。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1045.png)

Okay。Okay， the sound is valid。The sound is valid。I know it looks perfect。

Let's look at the power blocks。ItsCar less。Here。嗯。Yeah， it looks like they have。If that it's sound。

 let's just keep going there。🎼新で。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1047.png)

Okay。Do we zero the par block？And the sound is zero。Spawn power block。P blocks plus next power block。

And。Oh， I think we do， I think we do。Either levels。Power blocks。Yeah， we do zero。

I'm not going to zero the power block。Well， but instead of no of not searing。

We're going to call like reset。Power blocks。Okay。Yeah。Okay。Cannot play alone。Or some role played。

I don't know what you mean， man。I don't know what you're talking about。

Im really sure you know what you're talking about， I have not friends。妈呀。

Maybe you should make some friends， just go to game development。Meetings。

A lot of people there wants to make friends and like， go to a game jam， those are always fun。

Reset power blocks。 you can also make。Greatade friends online。

Informed like people with shared interests。But usually don't approach them talking on me stuff。Yeah。

😊，That's usually not the best way。What I am going to do is just going set the par block。

State too inactive with that。I remember。Le。Pyineactive。Kind。Is that it。And I'm also going to。

Se the point。对吧。Sound。I am introverted and I don't like talking， but this just practice。

I'm also super hyper introvert。And look at me streaming to like nine people and talking in English。

 which is not my first language， just get used to it when I was releasing my game。

I had to go to all sorts of events to present that。And I had to stand for like 12 hours a day。

And just talk to people。And I don't like talking to people。But I had to learn how to do it。

 and then you kind of see some interesting things。You learn some things about that。

 so this forced me。To be more open to talking。So now that I enjoy it now， but I'm less against it。

 I suppose， so it's just practices like programming， you just have to do a lot。Do that a lot。Text。

 I embarrassed you see my grandmothermars spell， also just practice， man， read some books in English。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1049.png)

I read the whole song of B and Fire series in English like three times。

And I don't know where we improved a lot of my English and just making these live streams。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1051.png)

I can really be more confident expressing my thoughts in English as well， but it is pretty hard。

 though。It is hard。Let me see if I can now reset。而克ly。🎼I'm more of an ancient。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1053.png)

Okay。So few problems。As a guy， it's good to hear。呃。Set the volume to1 was too much。

It is like point one。And。Yeah， that sounds。Sorry about that， I'm going to decrease your guys's sound。

A little bit。呃。And I should probably make like the volume based on your distance to it。

 but I'm just going to set it really down just so。Just hear that a little bit。ok。

Now what I am going to do。Oh， I have like a couple things。Like how's justw。

Hopefully not it wast your house， sorry about that if that was the case。呃。

I'm also going to increase the speed multiplier。ALi bit to make that。I don't know。

And then I'm gonna see， let's see the power block。I see。Inactive。Okay， in this case。

 I'm going to set the volume。这0啊。I can do like。Target button to zero。Sound no problem。

 those high pitch sounds where you can never know where it comes from， sounds like me and I yall。あ。呃。

Okay。So but 30 is lets me see where I change the bulb because this 30 is not correct。

I could play ball， let's see。Re the ns minus 50。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1055.png)

Yeah。Let's， I'm also going to go to the。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1057.png)

Create block， block。And also going to make like every block。哦。Power up。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1059.png)

Just are part down， just we can hear that。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1061.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1062.png)

🎼你。Okay， I'm not sure I like that。嗯。Let's see。Yes。跟他。Turn like。Fitty speed to its Steve。Let's make。是。

Let's make that a little less。I don't know， high pitched， a bit lower pitched。

And whenever we spa the block。That's set that target volume mic way down。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1064.png)

Should be just like a detail to tell the truth。I sound like。Okay。Yeah， that's a very precise thing。

🎼ネ気でもす。That was too low， maybe。I don't know if you guys could hear that idea。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1066.png)

Yeah， I didn't。And minus 50。Minus 50 is also not enough。Cha 60。は01。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1068.png)

It like 。05。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1070.png)

And I think there'll be enough。I suppose。Okay。Yeah。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1072.png)

Okay， you know what？I didn't like that， I go hear it， but I have sensitive heat， yeah。

I did not like that。Because。Well， you know what。Maybe I should like for every active。Fire block。

This volume gets lower。I don't know。 I don't know。 I don't know。

Like if we have a lot of power blockss， we shouldn't really。Play a bunch of sounds。

What do you guys think？I don't know， I don't like that， maybe I'm going to just take it out。

I just going to take it out。I think you're doing great。Yeah， but these power blocks sound， man。

I think what I am supposed to do is have like if more power blocks spawning with sound。

The one guys look， oh， so maybe。Yeah， maybe I can do that。Yeah so。Yeah， okay， so。

You're a nice comment moivate me， but theres something you can improve carefully。 Yeah， but I't know。

 I think it got to a nice point there I think then like update。😊，Power。Power blocks。うんLet's see。

For fuel rendering。Or is it sit here？Cpate power。Los。Okay。Now this is really bad。

 I think I'm just going to。Make that a little more。Senssible to read。Yeah， sometimes。

You do have to spend some time making our cold preder or whatever that means。Okay。Okay。Now。

We will run through all the power blocks。And then we count or maybe， yeah。Yeah。

What about having the pitch increase as goes up and decrease？看。😊，Nice， niceice one， man。

I am going to do that。Awesome， awesome， awesome call， really。So the pitch。The pitch。

Will be dependent on where it responds。I'm going to set like the power block。Sound。

A speeded multiplier。I could pretty much just add that to the P。喂。But I'd say this is like zero。

And its like，-60。So I'm going to add 60 to that。So this should be zero and this would be a lot。

I should really do the other way around。I don't have to think about that， but I like your idea。

Sees what I was doing here。For the power blocks， let's see。 Okay， so I'm going to have like。A Friday。

I could do like here。A。Power block count。And I'm just going to。And this is not like the best ever。啊。

Okay， discount。 And then。I said。P block， sound。Target volume。To be。That's a point。15。Divded by。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1074.png)

The active far block。Now this would be way better。I think turn out guys， yeah。嗯。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1076.png)

I think I removed the idea。I'm going to go back。Oh turn the game to the rough notes in the level。

Block， block。And we'm going to make。Block， power block。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1078.png)

Be the power。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1080.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1081.png)

ok。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1083.png)

Okay， I liked that。So now。Let's do the pitch thing。啊。Here in the game。

Every frame' going to decrease the pitch sorry， increase the pitch， the pitch。

So let's increase that by the Dt， so let's just hear how that sounds now。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1085.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1086.png)

Keyboard， I don't have a robot， but my keyboard is the DAS keyboard。Four。

I really like it desk keyboardboard for yeah。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1088.png)

Okay， when I change game mode， I should reset the power guys。没 menu有。Like this menu。Cha。

Change game mode。Okay。😊，want to reset， oh， I do have reset power。Oh， it's different。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1090.png)

Reet power blocks。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1092.png)

Red switchitch， no， it is。I'm not sure。I appreciate it's brown， yeah， it's brown brown switch。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1094.png)

うん。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1096.png)

That is great， I really liked it， however， we do have to change the initial sound。😊。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1098.png)

Because I think you guys understood the problem， but if you have a block coming from down here or it down here。

 let's say it starts as a as a I don't know， 0。15 that we were doing， right？

And then it gets all the way to， I don't know， 0。05。But if this guy starts out here at 0。15。

It's going to get all the way you try to know。Nextative。Whatever。

 oh it's actually increasing so this is going to go I don't know to 10。

5 and this may actually go to 12。5 because it was more for more for a longer period of time。

 it was increasing the pitch。😊，I sensed a lot of handmade heroes instrument that's the idea， man。

 the idea was to make a handmade hero that we could ship。In a very short amount of time。

 so like I said， we are almost done。I suspect maybe five live streams， I suppose。Well。

 maybe a little bit more， I was count on 25 live streams。But we may do a little bit less。

 I don't know， it's nice to spend some time like maybe because not as interesting。

 but we do have to make that those things a little bit stronger， like more robust。

Now let's think about an equation for that。We have the arena height， right？have the arena。

Arena have size。Why。So if we start at the half size y。Let's draw that。Because you know。

I'd say this is like 50。And this is like minus 50。We want this。To be。X， right？

We want this to be x plus the time that it takes。So。MaybeMaybe we can do a alert。Yeah。😊，First of all。

 I'm going to map my position into this range。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1100.png)

And normalize， okay， mapping strange， normalize。Which is going to be the minus theory are're going to have size y。

And they're going to have size right？And I'm going to do that with a PI。

 so this is going to return zero if we are here and one if we are here。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1102.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1103.png)

But we want the other way around。We run like one and zero。This is going to be like one night。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1105.png)

I mean， far quarter see the askIboard Oh， oh yeah， man。I mean。

 I learned to program with Casey pretty much， he was my almost personal tutor。

 he was in person because he doesn't know me。But I consider him like my teacher， really。Yeah， I mean。

 I didn't know how to program before， but that was for real。

I actually bought the deskboard because she says he liked it。

But then I watched in the latest stream that he said he liked the basketballboard three and not the four。

 but I really liked the four， so whatever。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1107.png)

So that was pretty cool。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1109.png)

Yeah， although he uses C+ plus for handmade heroro， this is C， so there you have it。Yeah。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1111.png)

Okay， I think this is a little bit better， but we may have to change。This to something like wastemo。

Traffic or key is better than us， okay？I am going to keep that in mind。

It was pretty funny because they don't sell doS keyboards in Brazil。

So when a friend of mine went to the US， I asked her to bring this keyboardboard for me。

And she did and that's awesome， I do have a razor stealth。At work。And it's pretty good。

But the deskboard's way better。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1113.png)

Those are more expensive soy gas makes sense。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1115.png)

So let me try playing around with the space invader and let's see， how does that sound？他姆。

I think I like it。日人。I felt President New， keep our layout out。Yeah。

 the keyboard we use is actually called a BNT2。Which I don't know if any other country uses it。バラ。

It really sucks for programming。Because of like the semi colonlon position。And the oh。

 that was awesome， that soundless， yeah， see。So I really like。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1117.png)

The way it's sounding。So yeah， we use a BNT2。But I use just the English keyboard and whenever I need Brazilian stuff。

 I just change that back to the NBA2 and I can pretty much use except for the interrogation mark。

 we don't have that because Brazilians have one extra key in the keyboard。

Comparing that to the American keyboard， so I can't type interrogation if I use the Brazilian keyboard with the American physical one。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1119.png)

So， yeah。I think they'll be it man， I implemented most of the stuff that guys suggested and there were great suggestions to be honest。

 I really like I do have to here with headset on to be honest。😊。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1121.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1122.png)

Let me turn your guys's volume a little bit up。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1124.png)

So you asking can tell me what you think。うん。努力暖。魅意。Yeah。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1126.png)

See， I really like the way it's sounding except minus60 is too much。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1128.png)

I try minus 55。Let's try playing。🎼胖来。Oh， that was crazy。🎼嗯。一。う。Oh。

 I got this little anti vertical control ones， oh my god。Okay。So the farm mouse exits the screen。嗯。

🎼F miles exits the screens。🎼你。Yeah。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1130.png)

We don't have a mouse and dey， a window。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1132.png)

Just quickly searched that。I want this to be a short live stream， but come on。

It's three and a half hours already。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1134.png)

Mouse leave。 let's see code for W mouse enter。If this website can load any day of the week。

The message was。Doesn't exist。Community that what we want to achieve。Oh。Mouse over it。For the period。

I'd see catch changed， I's see what that means。Sent to window that is losing the mouse capture。Well。

 you want。What happened。I haven。I handle to the window， gaining the mask。Okayay mouse button。

Mouse activate。When the cursor is in an active window then press the amount button。

 the parent window。When mouse move。 Yeah， but this is called like。It's called like a lot。

I wantt want to set the curse well。系啊。Moles leave。Sleves。嗯。Why don't they have a mouse in？

That's really weird。Button， button， hit test， mouse wheel， mouse move， yeah。

I'm not sure what we should do， but I mean， maybe we don't care about it that much because the game's supposed to be full screen anyways。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1136.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1137.png)

But I don't know， I'm not too happy about that。See， this is the kind of stuff。

 man that we have to do to ship the game， but it's not meant to be the most robust game ever。

But I think there'll be enough for today。Okay， so let me tell you guys a little bit because some of you guys didn't see the news。

 I have started on my YouTube channel， which is YouTube。comd Z dam。

 a tutorial series where I'm going to teach you how to program gain C++。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1139.png)

And this is meant for beginners， so if you don't know a lot about programming， just the basics。

 this is perfect for you， you're going to go in depth and're going to create a graphical game。

It's going to be p， I'm pretty sure。Then I already released the first tutorial。

 we're going to give the introduction about our game structured and how our games programmed and things like that。

 And I added it。 it was a lot of hard work， but I think it looked。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1141.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1142.png)

Pretty， pretty nice， I think。It was like small animations。Are you doing GL or SL， No。

 this is also going to be software render， just like the game are doing out。

 the thing is when you're teaching someone。A beginner program or how to program you don't want to make that person uses a lot of libraries because they think program is to use using libraries so that's the problem I had when I learn programming as probably most people have because they think okay。

 so in order to program I have to use all these libraries and you don't and don't need to use them you probably want to use them in more complex programs。

But I don't think in a learning program， this is going to be really quick。

 it's going to be like eight videos or something。8 videos with seven minutes each。So yeah。

 you definitely don't want to。Hed that person you know thinking about libraries all the time because when you do think about libraries。

 you're not going to study programming， you're going to study how to program that library。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1144.png)

And it're going to be。Thinking about all the random things that it wants you to do so yeah。

 but maybe later on when I get to do 3D games， hopefully。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1146.png)

Maybe tutorials as well， then we're probably going to use GL directly， open GL directly， probably。

Yeah， but for now software Henryry， which is a lot more fun and a lot more。A lot more， I don't know。

 instructive， that's the word instructive。To learn okay， now if you want to follow along the series。

 you can subscribe to my YouTube channel where I post every episode， so for the very first one。

 where we started with game with a blank file and no game。

And we slowly started making the game better you know I just going to show this video while I talk。

 which is like the progress so we started out with this game and then slowly we started making the game playing today we had some awesome improvements。

And it is looking pretty nicely， I think。There are a few things we want to change。

Especially the collision I thing the collision thing is going to be a little bit more。

 I think that's the last。😊，igBig piece of problems that we have to solve， I think。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1148.png)

啊。But today， and now the game looks like this。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1150.png)

。Sounds like explosives。He had the idea what to sell like fireworks。And I think you不较想。

Especially when you get the。去不下。起。Did you hear that？命。打死你。Really cool。



![](img/d4175b7c7da94dffbf39910f5457f6a6_1152.png)

Really cool， so。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1154.png)

And you can download the game for free on HIo， which is dd。h。o。

 and you can download source code and play around， make your own games， increment this game。

 make more levels things like that。Yes I do think it's getting it's getting really cool thing it's slowly slowly getting there Okay。

 so thank you all for watching and I hope you enjoyed probably learn a thing or two and hopefully I'll see you guys next time I'll see you then thanks。

😊。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1156.png)