# 【从零开始用C语言制作游戏】 p03 Making a game in C from scratch! Ep 03： -Gameplay Programming, Begi -BV18i421a7DD_p3-

Hello everybody， let's do some programming shalli， so this is the third stream in the series where we're building a complete gaming and see from scratch。

😊，And if you watch the previous episodes here on YouTube。



![](img/d64d01b71ce34c065794ea9c9a82a965_1.png)

You can see that we did first the platform layer and a little bit of software render。And yesterday。

 we started doing some gameplay programming and our collision and we had a lot of problems with the collision for some time。

 but in the end we managed to do a collision system kind of going and review this code。

In the beginning of today's stream， just to get us started。



![](img/d64d01b71ce34c065794ea9c9a82a965_3.png)

But if you do want to follow along， you can go to the HIO page for the game， dz。hdio。

And you can download it the source code。

![](img/d64d01b71ce34c065794ea9c9a82a965_5.png)

For free， just click download now， you're welcome to give me a little tip if you want。

 but if it's just say take me to the downloads， you can download the source code and follow along or if you want to watch all the episodes。

 it's on YouTube， YouTubebe。com/dan zan。

![](img/d64d01b71ce34c065794ea9c9a82a965_7.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_8.png)

And you can。Get to the point where we're at now， okay。Before we get started， I'm just going to。

 this is the directory of the game that we've been building。

 I'm just going to copy the project as far codeder for code is the editor that I'm using。



![](img/d64d01b71ce34c065794ea9c9a82a965_10.png)

This is just a simple file， let me show you here。This specifies what kind of files to include in the project。

This way， if I do load project。It automatically gets all the files。

 so we might have to keep opening them one at a time。ok。So if you go to the game。

 I'm going to re compile just to show you what we have。



![](img/d64d01b71ce34c065794ea9c9a82a965_12.png)

This would be ended up with yesterday。We are starting to look like a real breakout game， right？Yeah。

 okay， this is kind of cool what we want to do today is want to improve the gameplay quite a lot actually。

呃。Mostly the gameplay， but also the game feel， I mean， I think they're going to go hand in hand。

And I don't think we have to do any engine modification。 I think we have all。

We need for this time around。Yeah。See， but we are going to play around a lot of the variables like that。

How ball reacts to our paal collision， we're going to do the。Increase the ball of speeding y as well。

 and maybe put a。Smaller ceiling to the max beat the ball。But it had starting to come together。

 I think。Pretty cool and you also have to do like a loose condition because right now if I let the ball fall through nothing happens and if I win。

 nothing happens as well Okay， so that's the point where we are at now just gonna quick review what we did at the end of last stream was we managed。



![](img/d64d01b71ce34c065794ea9c9a82a965_14.png)

To here we inside the blocks， the block loop for every block that's alive。

We've finished this code successfully and this code， if I'm just going to draw for a second。



![](img/d64d01b71ce34c065794ea9c9a82a965_16.png)

Just to show you what it does。We basically figured out a way。To make sure the。

Make sure we know which axes we collided from， so for instance。If we。

 if the ball hits from this side。What we do is we have a desired ball P。

 which is inside here right and we test for x and for y， for instance。

 let's test for let's say the ball y axises。You're going to see we're going to do a like an inverted lub。

 so this is the target position。Where the。

![](img/d64d01b71ce34c065794ea9c9a82a965_18.png)

See， the target position involves the。The block Py， is's exactly what we're doing this point。

And then we do the inverted lup and find out the T， so this point。

 where does it stand compared to this being the A and this being the C， which is the final point。

 right？

![](img/d64d01b71ce34c065794ea9c9a82a965_20.png)

Yeah。This。If it's greater than one means that it's after this point。We collided。If it's less than。

T one m more than zero， it's inside this point， which is okay。 and if it's negative。

 it's outsidesized so we don't even carry。Okay， so that's the basic idea if you want to review this。

And see how the whole process of us getting to this point， you can watch yesterday's stream。



![](img/d64d01b71ce34c065794ea9c9a82a965_22.png)

Okay， now we're going to do a lot of small gameplay changes。



![](img/d64d01b71ce34c065794ea9c9a82a965_24.png)

Like one thing I want to experiment right off the bat is to do like the original breakout game instead of doing。



![](img/d64d01b71ce34c065794ea9c9a82a965_26.png)

Based on my。

![](img/d64d01b71ce34c065794ea9c9a82a965_28.png)

スピード？The new ball speed， so this the calculations we do wevert the ball DPY。

 which means the velocity now it's going up。And for the X。

 all we do is we add our x velocity with some of limit here。

But the so the idea is if we are 100% still， not's going to change even if we even if we hit the paedal the ball with the corner of the paedal now。

 if you do like a super fast move， see that's what happens the ball。



![](img/d64d01b71ce34c065794ea9c9a82a965_30.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_31.png)

Not sure how it's going to be the best feel for that， but I'm going to do like the original game。

And the ball D PX is going to be actually the difference in positions of the ball and ourselves， so。



![](img/d64d01b71ce34c065794ea9c9a82a965_33.png)

The bus here。And we are here， we should go like this， and we're only going to test this in X。



![](img/d64d01b71ce34c065794ea9c9a82a965_35.png)

So we're going to do the， yeah， the ball。皮。😊，Dot x minus the R P， which is the player P dot x。



![](img/d64d01b71ce34c065794ea9c9a82a965_37.png)

let's see。 How does that look。Yeah， so this is kind of the idea we want。

I think it's can like a way stronger。few， and this is a little bit easier than the one that takes the。

The velocity to account， I think we can do a little bit of both， to be honest。

 I think it's going to be cool。 But for now， let's just。😊。



![](img/d64d01b71ce34c065794ea9c9a82a965_39.png)

Let's just multi to play that， let's say they can， let's see the result。



![](img/d64d01b71ce34c065794ea9c9a82a965_41.png)

Okay。ok。 this is cool。Yeah， see there's a lot of easier to control at this point。

Maybe10 wasn't there too much less。

![](img/d64d01b71ce34c065794ea9c9a82a965_43.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_44.png)

Okay。Yes。😊，Nice。诶。是。

![](img/d64d01b71ce34c065794ea9c9a82a965_46.png)

And okay。Let's keep that way for now， let's do a little bit of work on the blocks。Now。

 what I'm going to do with the blocks。Is instead of just。Adding this normal offset here。

Which is the block half size times 2。I'm going to do the block half size times let's say 2。1。

 so we can get a little bit of a space between the blocks。Like in the original game。

 and I think it's going to feel a little bit better。



![](img/d64d01b71ce34c065794ea9c9a82a965_48.png)

See， there you have it。

![](img/d64d01b71ce34c065794ea9c9a82a965_50.png)

No， no， that's pretty cool， I think， and maybe the color。We only changed based on the Y position。

 and let's do like we have。Let's do 255 divided by non wide， so we get 100% black。

In the beginning and 100% why it's in the last row。



![](img/d64d01b71ce34c065794ea9c9a82a965_52.png)

Let's see。ok。Now that's kind of ugly， right， but that's the start。😊，Okay， pretty cool。



![](img/d64d01b71ce34c065794ea9c9a82a965_54.png)

Yes， now a couple things I want to do。 I'm going to do one more block in each side like。



![](img/d64d01b71ce34c065794ea9c9a82a965_56.png)

This。So we feel the whole row。Now that's pretty cool。

And I'm not sure if we should do like a vertical play screen like the original game， though。啊。

I don't think that's going to be as interesting what we can do is like the first time the ball goes through。

 it doesn't collide in the blocks。

![](img/d64d01b71ce34c065794ea9c9a82a965_58.png)

That。You know that could be fun。诶。Like， first ball。我唔来。Okay。

 and then when I hit the play with the ball， I'm going to say that first。Eals。False。

And I'm only going to test the collision。With the blocks。Like if。It's not the first volume。Okay。

 actually， I can't do this in here。Because I'm drawing it here。So I'm going to have to do like this。



![](img/d64d01b71ce34c065794ea9c9a82a965_60.png)

え気待ち。Okay， so the first time doesn't collide and then collide。



![](img/d64d01b71ce34c065794ea9c9a82a965_62.png)

Okay， now now it's pretty cool， I think it's starting to look like a real game， right？😊。

Let's do some things in the beginning， we're going to do x equals to zero。

 so it starts in the middle of the screen。

![](img/d64d01b71ce34c065794ea9c9a82a965_64.png)

And I think that's good， maybe we should do like an initial velocity。Right。Okay。Yeah。

 now it's pretty cool， now it's a little bit hard。

![](img/d64d01b71ce34c065794ea9c9a82a965_66.png)

行。ok。Now it's getting cooler。

![](img/d64d01b71ce34c065794ea9c9a82a965_68.png)

And cooler， the colors are really ugly。I think we should fix that in a moment。



![](img/d64d01b71ce34c065794ea9c9a82a965_70.png)

But。Let's see。's just see if you can get that ball that's the problem of making a game at this point that all you want to do is play the game。

 right。

![](img/d64d01b71ce34c065794ea9c9a82a965_72.png)

I'm going to add a random randomness to the ball starting position， maybe。



![](img/d64d01b71ce34c065794ea9c9a82a965_74.png)

Actually， I think I'm going to do that later， okay。Yeah， I think we got it。是。



![](img/d64d01b71ce34c065794ea9c9a82a965_76.png)

Yeah， this is pretty cool thing。A couple things I'm going to do is I'm also going to add to each block。

There's a life mode， not light。 There's a。B speed。Multipliier。So we're going to add。

Both be multiplied here。And so the idea for the new viewers here。

 all we're going to do is to clonelog。breakreakout。To get the idea of the game。

 but then we're going to start adding cool gameplay changes and that's the point we're going to do a lot of cool stuff with breaker I hope。

So that's the ball speed multiplier and it's going to start out as one。Okay， here。And。

I'm going to do that the block boss be multiplier。I's going to be Y plus one。Actually。

 I'm going to do one。Yeah， one plus's do why。呃。Divided by numberway。

So the last block is going to be two the speed multiplifierier。ok。😊，Okay， that looks good。

So when we collide？With a with a ball here， we can also clean up this code later for now。

 let's just do it like it is now Okay， I'm going to do if。The block。Balls， the black。

Baallll speed multiplier。 If that is greater than the current ball speed multiplier。😊。

Then the boss screen multiplier is going to be。The blog。我 was people。Okay。😊，And then we can also do。

is。Minus power。That looks good。Yhy人 change。

![](img/d64d01b71ce34c065794ea9c9a82a965_78.png)

Okay， let's see。So this should be like the same speed， yeah， kind of looks like it。And the， the。

The brighter the block。You know， the more speed we're going to get， let's see。

It's kind of a drag increase， let's see if we feel it。With the other blocks。啊。Okay， yeah。

 now I can definitely feel speed up。It's not entirely correct。Yeah， actually， I don't feel it。Well。

 it's not correct。

![](img/d64d01b71ce34c065794ea9c9a82a965_80.png)

Because。呃。I'm multiplying it more than once。先。😊，What I should do， actually， is to have a。Block based。

A ball base speed。Ba speed， okay， and the base speed。Let's see where I said is 50。ok。😊，So。

 block ball。Fte。And of all based。エス？Okay， and whenever I collide。

 I'm going to add the boss spin multiplier。And then I'm going to set it。To the base speed。Right。

To the base， all speed。Times。The we more to play。Oh。す？Okay。

 and I have to check how they actually so if。This guy。Is。Positive， I'm going to do that。Okay。😊，Yes。

 and its it's negative。I do。

![](img/d64d01b71ce34c065794ea9c9a82a965_82.png)

let's if it works on y， if it does， we're going to work on the X。



![](img/d64d01b71ce34c065794ea9c9a82a965_84.png)

Okay， yeah， this is pretty cool。We should also have a printing routine。

Just to make debugy easier in cases like this。But。Yeah， I should probably， let' get a break point。



![](img/d64d01b71ce34c065794ea9c9a82a965_86.png)

At this point。We don't have a game here。F of simulation， then add game。So I'm going to break。

We want to break up this point。So we can check out all the values， Okay。

 let's see if I don't die before I did dive， okay， we should probably call like an invisibility mode。

😊。

![](img/d64d01b71ce34c065794ea9c9a82a965_88.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_89.png)

Yeah， I think're going to do that。

![](img/d64d01b71ce34c065794ea9c9a82a965_91.png)

Just so it's easier for us to test。You're going to add。Its the ball。The ball hits。 maybe you like if。

So this is the invinscibility。If the ball minus the have size is less than arena。Mines are in size。

 going to remove the ball。

![](img/d64d01b71ce34c065794ea9c9a82a965_93.png)

To disposition and change its direction。 So now we should have E。



![](img/d64d01b71ce34c065794ea9c9a82a965_95.png)

呃。Okay， that was not correct。

![](img/d64d01b71ce34c065794ea9c9a82a965_97.png)

It's going to be minor。

![](img/d64d01b71ce34c065794ea9c9a82a965_99.png)

That soundss okay。ok。Oh， but we're not setting the in the show。Ball should collide thing， okay？

Now the speed multiplier is one and the boss speed is one that is correct。So the ball Dp 50。

Then I should do set it to 50。M-50 times one。 Okay， that's correct，50。Looks good now。

 next time around。Already。Yeah， I think because the frame took a long time， probably kept the max Dt。

 the DT， because we're debugging， so it takes like seconds。To each frame。

 so yeah the ball moves a lot。Let's see if it's still won the block。

 we're going to ignore that break point for now。Okay， then I'm going to add it again。 Let's see。



![](img/d64d01b71ce34c065794ea9c9a82a965_101.png)

Now it collided， let's see， with the second block。So the spin multiplier is still one。

 so this is not correct。

![](img/d64d01b71ce34c065794ea9c9a82a965_103.png)

Okay， so this is not correct。Here， we're doing one plus。Y minus number y is it an int？W， yes。

 we should probably do a float。Yes。I may to solve the problem and I'm also going to cap the friendly rate really quickly。

The T is going to be the。Me of， let's say，01， which is going to be our next in frame rate and the actual left。

I don't think we have a name， though。We do。

![](img/d64d01b71ce34c065794ea9c9a82a965_105.png)

I don't remember making it。So， that's， that's see。See the difference in speed。Okay。

 I think now I can feel the increasing speed。Yes， definitely。

I think it's going to be a bit too hard at 2x。Yeah， let's see。

 we're going to add the breakpoint again。Let's see this break point。So we are colliding。With tea。

With you know， the last third ball， so we expect like 1。7。Or something？

Let's see the model speed yeah， it's 1。666，66675。So our ball multiplier。Okay。

 it's going to be a little bit bigger。Yes， okay。 that looks good。 We are in good shape。

 so we can now play around with that to make it faster。 So maybe two is not as fast as we want。 Okay。

 it's pretty fast。😊，Yeah， it's pretty fast， okay。Wow， so in the X。😮，Pos。What？😮，What was that。

that was good for a few reasons。The first reason is our collision is pretty solid。

 so that was a successful last week we managed to fix all that。



![](img/d64d01b71ce34c065794ea9c9a82a965_107.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_108.png)

But we shouldn't actually。Should actually review this article。

Maybe we should not do anything in terms of well。And I think we should， yeah， the ball X。

 maybe we're going to do the same thing。I'm not sure。I think we're going to add the wide speed。Even。

😊，If we collectllide it next。Because the thing is the black God destroyed is going to be fast white because's for the player。

Why is more difficult？Yeah， so。Let's get this part here。They on to remove。This guy。

 and I'm just going to change the extract。But for the wide direction。I'm going to。Yeah。

 I think you're going to do the same thing。I' going to get the ball speed multiplier and set the new ball speed multiplier。

But I'm not going to change， yes， I don't have to test this。

All I have to do is to set to the base speed times the speed multiplier okay。That looks good。



![](img/d64d01b71ce34c065794ea9c9a82a965_110.png)

So let's see if we can get like an opening there。Okay， now it's getting pretty cool。 Yeah。

 I think I'm going to add a little bit of side race momentum too for the game。

Just to get it a little bit more interesting。Yeah， yeah， I think that was pretty。

 pretty nice the X condition。ok。ok。Let's see。 Let's see one more。是。Okay。Yes， now it's real breakout。

Yeah， pretty cool。Yeah。See， that's the thing I just want to play the game I don't want to make it more just kidding。

 let's do more stuff now。

![](img/d64d01b71ce34c065794ea9c9a82a965_112.png)

I'm going experiment with adding a little bit of our。😊，Of our satelliteways movement。

 I'm going to clamp that a lot like 10。So the basic idea of that is we're going to get our。



![](img/d64d01b71ce34c065794ea9c9a82a965_114.png)

So if we do this。It's going to be see way stronger。Yeah。you can also like。Do the other。

We around yeah。But you can also just use the normal breakout thing。Yeah。Maybe maybe。



![](img/d64d01b71ce34c065794ea9c9a82a965_116.png)

Maybe I'm not going to cap as much。

![](img/d64d01b71ce34c065794ea9c9a82a965_118.png)

But， I'm going to。大掉。I see。

![](img/d64d01b71ce34c065794ea9c9a82a965_120.png)

So if you are pretty still。Shouldn't be much of a when you go。Really fast。Yeah。Okay。

I'm happy with that。After today's trips， wow， that was pretty cool， right？Okay， wow， that's nice。

Not sure that was correct， though。Did you guys see that， it hit like this and went back up， yeah。

 see。嗯。Okay， that was correct。That was not correct。I think。



![](img/d64d01b71ce34c065794ea9c9a82a965_122.png)

Okay， so I'm kind of enjoying the movement for now。Let's just do a quick review here。

Offfer to do what we're doing in X。If we collide with the X guy。We change the desired X， okay。

 that looks good。We change the X direction of the ball。That is correct。

I get that boss pin multiplier。And we set the why。Yeah， see， this is the problem。We can't set it。

Yeah， I think I're going to do the same thing。But the other way around。 So if we are going up。

 we're still going to go up， we're going down。 I'm going to go down。 That was the problem。



![](img/d64d01b71ce34c065794ea9c9a82a965_124.png)

Okay， so let's see what you have now。Okay， this is pretty cool。

Maybe I should add even more of our speed thing because since we are doing theO。

The older the where you hit the panelal dictates where the ball goes。停。😊。

The play is not going to move as fast， so if he does move fast。

I think we want to make it like go really crazy。I think it's going to be good。Like this。 Like see。

Should be a little bit faster。 No， maybe it's fast enough。 I think Yeah， maybe it's fast enough。

 We don't want to get it out of control completely。

Just wanted to be a little bit of a chaotic attainance。Okay。Yeah。Looking good， guys。

Did the box load down？

![](img/d64d01b71ce34c065794ea9c9a82a965_126.png)

I think that was just impression， let's see if the ball slowed down。Yes， no， no， it's 1。8。And。

Then it's still company funny， okay， it didn't slow down。

Okay now we should probably add wind and loose conditions。It's coming along really nicely。Yeah。

Maybe we could do like a little bit of a faster bowl。



![](img/d64d01b71ce34c065794ea9c9a82a965_128.png)

At the end。So the boss pin multiplly is going to be。This guy times， I don't know， too。



![](img/d64d01b71ce34c065794ea9c9a82a965_130.png)

It'll be y times 2。

![](img/d64d01b71ce34c065794ea9c9a82a965_132.png)

Let's see。And it's going to be too crazy。So it starts off pretty slowly。赢呢。

And then it start building up， it's pretty fast already， yeah， maybe two is too much。前次。No。

 I don't know， I kind of like that。是啊。Yeah， I already lost， okay， maybe too is too much， let's do 1。

5。😊。

![](img/d64d01b71ce34c065794ea9c9a82a965_134.png)

嗯。If you guys have any questions， be sure to drop them in the chat I'm going to try to answer them as guests as I can。



![](img/d64d01b71ce34c065794ea9c9a82a965_136.png)

Yeah， now we're talking。See it starts off pretty slowly， let's try to get the。About to the side。

 we pretty much have old breakout here。That was like。That was like not a lot of work honestly。

And we did from scratch， so if we watched the earlier streams。

 we started with a blank file and we didn't use any libraries and used the Windows right because the game is running on the Windows I don't think you guys can see the whole thing yeah。

But apart from that。That was pretty much it。Now we can work a little bit on the game field aspect。

 I maybe 1。5 is still too much。Well， I don't think so I think it's good yeah。

So if want to get the ball， we have to deflect like this， right， we have to also use our speed。Okay。

 yes， like is， okay。So that's the rewarding part of breakout right， managing to do that。Okay， yeah。

 maybe 1。5 is due to much less to 1。2。

![](img/d64d01b71ce34c065794ea9c9a82a965_138.png)

Okay， what do we want to do now？

![](img/d64d01b71ce34c065794ea9c9a82a965_140.png)

Maybe we want to change the colors， oh I'm going to do the game over condition so I'm going to remove the invincibility sheet。



![](img/d64d01b71ce34c065794ea9c9a82a965_142.png)

And。I think I'm just going to do it like this。

![](img/d64d01b71ce34c065794ea9c9a82a965_144.png)

If we collide with the bottom part and I'm not even going to do the bottom part。

 I'm going to let this drop。All the way to zero。

![](img/d64d01b71ce34c065794ea9c9a82a965_146.png)

So if the ball， DPY minus this is less than zero， I'm sorry。



![](img/d64d01b71ce34c065794ea9c9a82a965_148.png)

Not 0。

![](img/d64d01b71ce34c065794ea9c9a82a965_150.png)

Yeah， we are not entirely sure。

![](img/d64d01b71ce34c065794ea9c9a82a965_152.png)

Where is that， so here's the whole screen。I like to get rid of this。This border here。

And I've about evolved through a little bit。But the thing is。



![](img/d64d01b71ce34c065794ea9c9a82a965_154.png)

If we you have like a super wide screen， that's what we did in the first day。

 we have a like pixel independent random， if have a super wide screen。This is like the normal side。

 long live sea， indeed。C is the most fun programming language should have as of now。

 I think it's great。Okay， so。If you have a super wide screen， that's the result。

 if you have a super tall screen， let's say is 16 by 10 thing see。This is a little bit thicker。

So I think we're going into hard code change our。Draw arena， we do like clear screen and draw。



![](img/d64d01b71ce34c065794ea9c9a82a965_156.png)

Function down here。Let me show you guys here。Where we draw the arena？Enterd。

 but I don't think we're going to draw this bottom thing here。Yeah。



![](img/d64d01b71ce34c065794ea9c9a82a965_158.png)

I don't think we're going to do that。Go to have the feel that the arena is going to end like this。



![](img/d64d01b71ce34c065794ea9c9a82a965_160.png)

So。Yeah， let's do this in the rendering。I clear。s you're not going to draw the bottom guy。

Which I think is this one， zero。Now it's this one。

![](img/d64d01b71ce34c065794ea9c9a82a965_162.png)

Oh， now it's black， Okay， so I guess we do have to draw。



![](img/d64d01b71ce34c065794ea9c9a82a965_164.png)

But we have to draw with the react color。

![](img/d64d01b71ce34c065794ea9c9a82a965_166.png)

Okay， see， now it's more interesting because we have like the feeling that we are。

 we have an abyss down there。 that that was a pretty small change。

 and that was pretty cool thing in terms of。😊，Pressure。

 maybe we can do like a little thicker board on top later on and do like the score and things like that。

But。Yeah， okay， that was pretty cool。So now we have to do is if we do hit that bottom thing and we can let that pass for a bit。

 it's not like it's not just needs to be a perfect。



![](img/d64d01b71ce34c065794ea9c9a82a965_168.png)

呃。I think I think I just。The and的。Here， if we collide。That's do like。口对。Not game over。

 We're going to， you know， lose a life that for now it's gonna be a you game over。 Hey， Marcus。

 hi again， suggest make the brick line a real world。 Each row upset set a brick from the previous。

It row offset。

![](img/d64d01b71ce34c065794ea9c9a82a965_170.png)

A brick from the previous， so not sure it means make the bricks like a real wall。Each row offset。

 so this guy。Half a break from the previous。Oh， you mean not have the little， the little space。

 We added that now。 We could， could just remove it。 I don't know how you， how you feel about that。

 Let me show you， We just added a 2。1 offset instead of a。



![](img/d64d01b71ce34c065794ea9c9a82a965_172.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_173.png)

The en upset， that's what you mean， I think it does look pretty cool。Yeah。

 maybe you're going to stick with that for a time thanks for the suggestion。

 yeah now we start changing the world。Yeah， I think that is pretty cool。

Though I'm not sure why we are not centered now。Yeah。Okay。I think that's way better， thanks， Marcus。

呃。Yeah， I'm going to have to fix the centering thing， I don't think we are centering now。Dude。

 it's already starting to get fun。And we didn't do much。 I mean。

 each break is over two instead of fun。 Oh， so you mean like up。



![](img/d64d01b71ce34c065794ea9c9a82a965_175.png)

Adding hose， this is the half size so I have to multiply by two so if you want to be two that are for one。

 it's going to be like four because it's the half size。



![](img/d64d01b71ce34c065794ea9c9a82a965_177.png)

You mean like this？I mean， sure we could add like a level where。Yeah， it's cool。Visually。

 but it's weird。I mean， each brick is over two bricks instead of going， oh。

 it's in terms of row only。

![](img/d64d01b71ce34c065794ea9c9a82a965_179.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_180.png)

So we should do like this。Okay， not sure that's it， but that's pretty interesting too。



![](img/d64d01b71ce34c065794ea9c9a82a965_182.png)

No， look at real a wall image。Okay， now I see what you mean。



![](img/d64d01b71ce34c065794ea9c9a82a965_184.png)

You mean to offset every other role。And look like。Like this。Is that what you mean？

I'm secretly converting C plus plus to C at work。 Yes， that's a nice thing to do。

 just little know that and know。 Yeah， the thing about C++ and C is。😊。

If you use like a lot of C plus plusness， like modern C+ plus stuff。

It's going to be very different from C， but you can use like C++ in just a little bit of the features。

😊。

![](img/d64d01b71ce34c065794ea9c9a82a965_186.png)

Let's do that Mark I'm not sure about the map because I did like a couple of the ideas we experimented。

 maybe can we can add like to new here。Inplay ideas ideas。And like bricks。With large。

Spaces between them。Because we are going to do a lot of levels in this game。

 we're going to first start cloning breakout as we are doing now。

 but we're going to work on the field a little bit more and once it's nice。

 we're going to create crazy levels with crazy rules。

 that's the idea to really experiment into the game time。 Okay， so let's do Marx's idea。😊。



![](img/d64d01b71ce34c065794ea9c9a82a965_188.png)

So now this is the connected bricks， right？Yeah， we have to change the offset。

 I think it's because it's in float。

![](img/d64d01b71ce34c065794ea9c9a82a965_190.png)

Let me just。The X offset。I have size times。嗯ん。Let's do。



![](img/d64d01b71ce34c065794ea9c9a82a965_192.png)

Let's just see if we fix the standard thing。

![](img/d64d01b71ce34c065794ea9c9a82a965_194.png)

No， we didn't。 Oh， maybe I think it's because there's a。Yeah， there was an infinite number of blocks。



![](img/d64d01b71ce34c065794ea9c9a82a965_196.png)

No， still， it's still weird。

![](img/d64d01b71ce34c065794ea9c9a82a965_198.png)

We offset by half。A block。X offset。Like half size time well。

Not going to worry too much about that that's implement Mar's idea so if the role。Is even。

So if y modulus 2。We are going to do this else。We are going to do。This。Have brick size。不要开衫。Plus。

 illegal for okay。

![](img/d64d01b71ce34c065794ea9c9a82a965_200.png)

Thats。Okay， now that's pretty cool， right， let's start seeing。😊，Dude。

 if you get the ball inside one of these holes， it's going to be craziness。

That's a pretty cool pattern right here。D， that's， that's awesome。😊，Like see。

 it's like we're actually carving a hole， yeah。Yeah， it does look nice。😊，I'm going to cap。



![](img/d64d01b71ce34c065794ea9c9a82a965_202.png)

The first and the less。Few bricks。 So visually， it looks even。Like these guys。So let's do that。

 It's in the size， right， Oh， the block size。

![](img/d64d01b71ce34c065794ea9c9a82a965_204.png)

Is a constant for now。 So I'm going to remove the block side yeah， the block half size from here。

 I'm going to place it here。 So each block add its own half size。Okay。

 so we're going to set each block half size to this。嗯。The X offset。Maybe yeah。

 the X offset row can have to do that slowly。Let's do like no offset for now。Good， I'm not sure。

I'm going to do that and you have to presupose this foreign two， I suppose。嗯。Block， block have size。

来。Size？I think we'll be able to do that。Without。Yes， we are going to be able block have size。

 lock have size。That's just like block， half size， we can change the block。是吧。Well。

 it should really remove the law。Name from the block variable because we already sidestruct。Okay。来。

All have。

![](img/d64d01b71ce34c065794ea9c9a82a965_206.png)

I suppose you're correct now， let's just see if nothing changed。 Yeah。

 the offset is up now we're starting at00。Maybe we can hardcoat that for now。



![](img/d64d01b71ce34c065794ea9c9a82a965_208.png)

Yeah， let let's do a little bit of a hard coding The this guy's going to be minus11 and this one is going to be the number in x。

Times the half size will be for。Okay， I think it's going to be mind。



![](img/d64d01b71ce34c065794ea9c9a82a965_210.png)

Oh and the y is plus。

![](img/d64d01b71ce34c065794ea9c9a82a965_212.png)

No，' sure we got it all wrong。Oh， because we are subtracting to the offset， okay？



![](img/d64d01b71ce34c065794ea9c9a82a965_214.png)

Okay， so let's see now。

![](img/d64d01b71ce34c065794ea9c9a82a965_216.png)

Yeah， now we're a little bit better。So we can do like 12 here。

 And now we can start doing that thing if we are in the。The first or later row， so if x is 0 or x。呃。

Us no x minus1。We are going to。Do half a block。

![](img/d64d01b71ce34c065794ea9c9a82a965_218.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_219.png)

ok。That was kind of correct。But we also have to move that by half block。嗯。Okay。No， I don't think。

 so I think this I'm going to hard code it like。Or for now。And2。Do you like hard codeed。Size。

Or we could just let that。

![](img/d64d01b71ce34c065794ea9c9a82a965_221.png)

No， that's okay， Mark it's not deraing dude。 You're just having fun。 That's the fun part of the game。

 You know， we， we want to owe that。 That's pretty weird。😊。

We want to experiment what is nice in terms of。Ideas， you know， we。

 we don't want to do like a straight clone。 We want to start out with a clone so we can understand what。

 what it does。 Good， like the so paal ball position thing that we implemented in the beginning of stream today。

That was nice。But。But we do want to experiment crazy ideas this dude。

 you're going to see we're going to do so much derail in terms of game design that's the fun part Yeah。

 but it's still still awkward。😊。

![](img/d64d01b71ce34c065794ea9c9a82a965_223.png)

Im going。😊，If you do know what should be the correct math for that， see this is so weird。嗯。Okay。

 I got it wrong。 Yeah， this is 2。0 and this is。4。

![](img/d64d01b71ce34c065794ea9c9a82a965_225.png)

See， hard coding is not a very。大。What's going on？

![](img/d64d01b71ce34c065794ea9c9a82a965_227.png)

Every other role in Xs。I felt accommodate that mean why。Oh。



![](img/d64d01b71ce34c065794ea9c9a82a965_229.png)

Yeah， I got it wrong， this。So I'm supposed to do， okay。



![](img/d64d01b71ce34c065794ea9c9a82a965_231.png)

Yeah， I'm going to do a little bit。I like eight kids of 12。



![](img/d64d01b71ce34c065794ea9c9a82a965_233.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_234.png)

Okay， so that was the point we were at。 Maybe we can do a little bit less like。



![](img/d64d01b71ce34c065794ea9c9a82a965_236.png)

Or just gives us a little bit of room。To do some damage there， Okay， now。



![](img/d64d01b71ce34c065794ea9c9a82a965_238.png)

If we are in the。

![](img/d64d01b71ce34c065794ea9c9a82a965_240.png)

The corners， I'm gonna do a square block。Okay， this is correct。This。

 I don't think this is correct oh。

![](img/d64d01b71ce34c065794ea9c9a82a965_242.png)

Because it's offset， right？

![](img/d64d01b71ce34c065794ea9c9a82a965_244.png)

So all I have to do this is move。To to write of that a bit。These guys。I should have made them larger。



![](img/d64d01b71ce34c065794ea9c9a82a965_246.png)

Yeah。So in this case。We're going to see， okay， if we。A this。 going do this else。They're going to do。



![](img/d64d01b71ce34c065794ea9c9a82a965_248.png)

Twice as as because of a block， or we can do more blocks。



![](img/d64d01b71ce34c065794ea9c9a82a965_250.png)

诶。No， I think I got it wrong。

![](img/d64d01b71ce34c065794ea9c9a82a965_252.png)

Let's just keep the black size。Okay， this is correct， how I have to do is move them a little bit。

This。

![](img/d64d01b71ce34c065794ea9c9a82a965_254.png)

Okay， so I'm going to do， yeah， in the beginning of the X。Do this。



![](img/d64d01b71ce34c065794ea9c9a82a965_256.png)

Yes， in now open。干少。In the beginning of the X， we're going to do this。Yes， and in the end。Of the X。

For every other road。Actually， this is not correct either。



![](img/d64d01b71ce34c065794ea9c9a82a965_258.png)

Because if you move them by half size， some of them is going to be a big hole， some of them amount。

 you know what I think I'm going to do， I think I'm going to stick with the first idea。And not。

Do this。 I mean， we can just， we can just make them。The size be the same size。



![](img/d64d01b71ce34c065794ea9c9a82a965_260.png)

I think we're going to do that for now。It's gonna be enough。 And then we can add。呃。To the ideas。

 more crazy stuff。

![](img/d64d01b71ce34c065794ea9c9a82a965_262.png)

Yeah， I think I'm going to do that。 Okay， so for the ideas， bricks with large spaces between them。

Bricks。Looking like a wall。But offset it。Bye。By half a brick。



![](img/d64d01b71ce34c065794ea9c9a82a965_264.png)

So right now， we're upsetting。 I have a brick， but we're not doing a。



![](img/d64d01b71ce34c065794ea9c9a82a965_266.png)

Good looking well， I suppose， maybe we could also。Go back and add the small size rate change。



![](img/d64d01b71ce34c065794ea9c9a82a965_268.png)

Okay， that's pretty cool， right。😊，Yeah。And you guys will be able to play with that as well。

 because at the end of this stream， I'm going to post the source code。For more craziness later。

 each row could be offset randomly。Yes， you know what what I want to do in a medium term。

 I'm not sure it's I'm going to do like a graphical editor or like a text editor。

 but I want to be able to specify certain brick patterns like I want to do okay。

 I'm going to place like a wall like this， a wall like this in a wall like this。

I definitely want to do that。That's， that's in the。



![](img/d64d01b71ce34c065794ea9c9a82a965_270.png)

That's in the plans for hitting play craziness， but we do we are going to add a few few craziness out actually。

 so what we're going to do is we're going to note。You know。Bandom offset for each role。

And we're going to start playing around。We're going to do the loose condition， right， let's do that。

But I， yeah。MaybeMaybe I'm going to keep the wall like this。So game over， if we do collide。

 I don't think we're going to collide with the arena， per se。

 maybe we can do like what is the arena size？The arena size。Is 45 here， so if we do like minus 50。

If you do with minus 50。Let's just set。Start doing。Okay， and the start game。Should we restart really。

 but that's going turn of。嗯。Start。And if I said initialize to false。

Most of this still going to be sorted out。

![](img/d64d01b71ce34c065794ea9c9a82a965_272.png)

The other things is the。The start by zero thing that we support， okay。Yeah。

 we do have to resetsell a couple of variables。 Oh， nice， even parsing an image and making brick。

 Yes， exactly。 I think that's gonna to be pretty cool。

 Maybe we could draw those bricks like like a Photoshop or thing like oh。

 it's weird that this block did next。😊，嗯。Yeah， see， these guys should should have been deleted。



![](img/d64d01b71ce34c065794ea9c9a82a965_274.png)

Okay， but that's pretty cool。Okay， let's do some offsett。So， I'm going to set。呃。

That could be a fun experiment like。呃。MyA improvements level editor。And if you slice to false。

 I'm going to set。The first ball movement to true。I'm going to set yeah。

 I think that's only what I need to do。Yeah。

![](img/d64d01b71ce34c065794ea9c9a82a965_276.png)

7。Okay。Okay， that's pretty cool。So we do have a game over it。And we do have a start game。ok ， let's。

I'm just going to play for a little bit just too。To get the feel of it。

 I think it's pretty cool in terms of。Game few。 Yeah， see the collision is not 100%。

 I'm going to have to reset the deep。 So the collision is not 100%。



![](img/d64d01b71ce34c065794ea9c9a82a965_278.png)

L底P的X。And the bulb P。 x also equally。Let's see what else。Today。Yes。



![](img/d64d01b71ce34c065794ea9c9a82a965_280.png)

Yeah， that's about it。

![](img/d64d01b71ce34c065794ea9c9a82a965_282.png)

嗯。Yeah， I'm not sure what's going on with the col， maybe we added a bug or maybe we discovered a book。

Let's just try to do it slowly。知。Is nice。Okay， looking good。Maybe it was the second time around？

That this boat happens。Or maybe only if we do like some crazyaz stuff。

That's straight do some crazy stuff。Now， this everything looks right。Yeah， everything looked pretty。

 pretty awesome。Okay， now let's see if this is problematic or not。



![](img/d64d01b71ce34c065794ea9c9a82a965_284.png)

Okay， I， I think I see the problem。 No， life equals one。I thought I wasn't doing like plus， plus。

You in the life。Okay。嗯。Okay， I have to reset said next but that's the problem。Next block。

Is the blog that we start with？I'm not sure that's the problem。

 but that's a problem I do have to reset the block and later it'm going to be li in completete。Reset。

The blocks here。

![](img/d64d01b71ce34c065794ea9c9a82a965_286.png)

Because if we have like a1 more blocks than the other one， you do have to clear that， okay？

So I think that's definitely a improvement well， what happened？



![](img/d64d01b71ce34c065794ea9c9a82a965_288.png)

Do we not offset the ex position？

![](img/d64d01b71ce34c065794ea9c9a82a965_290.png)

audi p x。Involve Px。Start game。We should probably， yeah， I think we are already。

 we change the position of everything here and then we collide。With everything again。See here。

So what you can do is do this at the end here。After the whole collision thing。

 it's a bit weird because we're doing here collision and renderry with the blocks just so we can put them once。

So。We should probably do collision first and then check this。Otherwise it's going to be pretty weird。

 I think。You could also do that in the fer and F drive。Yeah， we're going to do one frame of lag。

 but it's game overdue， I think that's what I'm going to do so I'm going to do block P。



![](img/d64d01b71ce34c065794ea9c9a82a965_292.png)

Yeah， I think that's correct。Yeah， because we were set the position and then we going to do we were doing all kinds of crazy calculations after。

 oh， that's pretty cool， yeah。Dude， it's really fun now and we didn't even do anything in terms of game feel。

 like making it look nice and feel nice。

![](img/d64d01b71ce34c065794ea9c9a82a965_294.png)

Okay， perfect。Now， at this point。

![](img/d64d01b71ce34c065794ea9c9a82a965_296.png)

We have a breakout game。

![](img/d64d01b71ce34c065794ea9c9a82a965_298.png)

Correct， it's a simple breakout game。And we do have one。

 but what we want to do now we want to do a like。APpiI。

 let's call it that so we can experiment with crazy gameplay stuff。

Like most suggest a couple things in terms of block layout and that's awesome。

 that's what we're going to do。But we also want to do。More than just luck up。

 we also want to do rules changes。 That's pretty cool， right？Yes。

 so for now we're just going to do the block layout thing。

 we're going to do a enough for the game mode， let's call it that。



![](img/d64d01b71ce34c065794ea9c9a82a965_300.png)

Tack F game。Going to do。You do game mode。Breakout。As do。然么。Okay， you're going to do a game mode。呃我。

你 mode。诶。That's called that。Construction。Wt you do that every other role。

Some of the created and this one's going to be。Sped。And then I'm going to tease you guys。

With what they're going to do after we do these few game modes。Okay。

That's all I'm going to say for now I didn't say anything and just typed。

 that's what I'm going to type for now。Then I can have some fun so this I'm going to receive a。

Game mode。Game mode。And then I'm going to do re switchitch on the game mode。So in case we are doing。

Gs we're doing normal。Okay， and I'm going to do a invalid default case。

 I don't think we have a search。Probably doing a third like default。Assert。0。Let's see。

 I missing for。Start game。Yeah， so we're going to do like the currency。Or you can just reset the out。

And do that。If you lose it until reset。Okay， yeah there's no assert， let's do a assert。On the一的意思。

Go to do a。A very simple assert that's just going to crash the game。Sert。Condition。If。Condition。呃。

Yeah， I'm going to write。To a no pointer。That's always fun， right？Alse nothing。

And we're also going to like if development。Else。Else。手机对吧。And now in our build。

 we're going to say that this is the development。to。Okay， minus D develop。

Unexpected and the file ended if。Okay。Equals。嗯。Our search is not。Correct。Zero， yes。

 cast as a point to an int going to get into then instead to zero the answer going crash。Okay。

And here。This is the visualization。We are going to do that on the start。Pretty much this whole thing。

Here I like to start game。The first game， okay？And then I don't have to do like niize normal。

First ball movement。And I'm also going to。Reset the blocks。



![](img/d64d01b71ce34c065794ea9c9a82a965_302.png)

那哎。I'm going to leave you like that for now。 Let's see if everything is， as we expect。 Okay。

 so we're having the normal game mode。

![](img/d64d01b71ce34c065794ea9c9a82a965_304.png)

We should also change the colors。But they we're going to do like a more beauty pass。

And then it resets nicely， okay。

![](img/d64d01b71ce34c065794ea9c9a82a965_306.png)

Okay。So that's the normal game mode。What we are going to do now is start playing around with more game modes。

呃。I'm going to do a lot of copy and pasting code。Which I not sure is the best。For now。

Maybe we could do like。like this could be out here。ok。😊，Yeah。

 and maybe we could override that and all you have to do is change the block position。And I think。

I'm thinking about no， not yet， that's not the editor yet， I'm going to do later。Okay， so the normal。

 the wall construction spaced。Let's do the case。J宝。Oh， let's just see if how our search is working。



![](img/d64d01b71ce34c065794ea9c9a82a965_308.png)

We're going to start game what？

![](img/d64d01b71ce34c065794ea9c9a82a965_310.png)

Let's see crash。No， we don't crash， we just have nothing。S0。Oh。It's the other way around。

 if this is not true， yeah。

![](img/d64d01b71ce34c065794ea9c9a82a965_312.png)

Okay， now crash。

![](img/d64d01b71ce34c065794ea9c9a82a965_314.png)

And also I like to do like a。Eal default case。That all does is exactly this。

So I think it's easier to take just like we've got a default here。Do you like family。Okay， nice。

And okay， now I'm going to do that。Case。Jm， well。And the wall is going to be what we have。

And this one's going to be the normal breakout mode。Which is just setting the black half size。To。嗯。

Yeah， black。Have size。就是天真 be really really cool。Okay。If no。And then here I'm going to start。

Keyboard， I don't have like a robot that tells me things I don't know how to set it up。

 maybe I'll do it later。 This keyboard is a D keyboard for。And I really love it。So yeah。

 I'm not sure the switch， though， I think it's blue， but I'm not 100% sure。

And think's a great keyboard they don't sell here in Brazil。

 so I had to ask a friend of mine that went to the United States to bring it back from me。

So I was like， yeah， you know what， I it might have been brown and pretty sure's brown。

 You are correct。 nice， nice years。 Yeah， Yeah， it is brown。😊。

I a I also have had work a razor stealth with green switches。But this one's way better， I think。

Three more robust。Okay。Illegal for structure have size of X。Zero already used。We need to do that。

And then I'm going to start。

![](img/d64d01b71ce34c065794ea9c9a82a965_316.png)

How about when you hit buck， sometimes it gives you power ups？



![](img/d64d01b71ce34c065794ea9c9a82a965_318.png)

And have to hit the bulk。That you had， oh， hit the powerds， that's a cool idea。So。Boxes， my blocks。

Gives。Power ups。That you have to hit。的包。起来。You could also like。Or。Are collided。

That's pretty quiet idea too because。

![](img/d64d01b71ce34c065794ea9c9a82a965_320.png)

You have to hit the ball。And the powered up， so this is the first， oh， now it's nicely standard。

So I suppose that the math was right。😡，The problem。Was our offset mega okay。

 so this is like the first game mode。Have to clear this out？

We have to do like win a wind condition too right， and then when you do and also have to do like cheat coats when you clear this guy out。

 we'll be able to move to the other one。Okay， that just。Yeah。

Maybe I'm going to do a little bit more spacing。

![](img/d64d01b71ce34c065794ea9c9a82a965_322.png)

Like。t2， I think。In the hearing。Oh， we didn't add spacecing here。



![](img/d64d01b71ce34c065794ea9c9a82a965_324.png)

。2。2。Yeah， that sounds a little bit better， but I have one guy too many。



![](img/d64d01b71ce34c065794ea9c9a82a965_326.png)

What could I do？

![](img/d64d01b71ce34c065794ea9c9a82a965_328.png)

Oh9。

![](img/d64d01b71ce34c065794ea9c9a82a965_330.png)

Yeah， see now it's a wrong offset， Oh， because we have to consider this offset， oh okay。



![](img/d64d01b71ce34c065794ea9c9a82a965_332.png)

Okay， so the x offset is going to be the number of x。Times， this guy。Times4。Oh。

 four is the block size， yeah。Do you like hard coded black sound。Or we can do this。Very here。Blood X。

It goes4， okay， that's better。Block exercise， and this is the block。Bck。Okay。Noun X redefinition。

I can do that。一就为いいや。Costant。And we also have to move that outside this file for now because it're going to have tons of game modes。

But for now， it's okay， missing。The constant。But I didnt cost。搞一口。Dude， that's a weird error message。



![](img/d64d01b71ce34c065794ea9c9a82a965_334.png)

She says expression bad。

![](img/d64d01b71ce34c065794ea9c9a82a965_336.png)

Not constant。 Okay， now it's entirely wrong。 Oh， we have to do half， half the size。Let's do a 1。1。



![](img/d64d01b71ce34c065794ea9c9a82a965_338.png)

Which is half of 2。2， which is the size。Okay， I think we are correct。 now， if we do a。



![](img/d64d01b71ce34c065794ea9c9a82a965_340.png)

even number of guys。

![](img/d64d01b71ce34c065794ea9c9a82a965_342.png)

Is that going to be centered， no？

![](img/d64d01b71ce34c065794ea9c9a82a965_344.png)

We're almost correct。We are did too much。As you have。嗯。So let me try to understand that。



![](img/d64d01b71ce34c065794ea9c9a82a965_346.png)

I'm doing like just the size of the wall。

![](img/d64d01b71ce34c065794ea9c9a82a965_348.png)

Then I'm offsetting。I have that size。ok。Oh， this is the block half size。Thanks。sizeize。

So we have to multiply that by buying nothing。

![](img/d64d01b71ce34c065794ea9c9a82a965_350.png)

Because we want to move half。

![](img/d64d01b71ce34c065794ea9c9a82a965_352.png)

ok。Okay， I think we are going somewhere。

![](img/d64d01b71ce34c065794ea9c9a82a965_354.png)

9。I'd see that's not the very the most fun part of the game， no， we're not getting anywhere。



![](img/d64d01b71ce34c065794ea9c9a82a965_356.png)

The offset is going to be the number as of load。Times。The half size。嗯。Yeah。😊。

I'm going to draw that out because I don't think this is right。



![](img/d64d01b71ce34c065794ea9c9a82a965_358.png)

呃。Let's say we have like three blocks and each one has one。We want to move for 1。5， let's say。

 minus 1。5。How do we know that？It's the number of blockss。



![](img/d64d01b71ce34c065794ea9c9a82a965_360.png)

Number of blocks。Times。The size divided by two。That's what we are doing。Here。And the position。

Is x times。This guy minus the offset。

![](img/d64d01b71ce34c065794ea9c9a82a965_362.png)

so this was supposed to work。

![](img/d64d01b71ce34c065794ea9c9a82a965_364.png)

But apparently， we are one guy。

![](img/d64d01b71ce34c065794ea9c9a82a965_366.png)

Maybe the first one。嗯。That's just hard coded， like。



![](img/d64d01b71ce34c065794ea9c9a82a965_368.png)

Plus。On is this year。Just to see the result。Yeah， now it's standarded。

Now let's try to do a even number of guys I'm not sure why I have to think about that Yeah。

 now it's working Why do it have it offset by the block hash size？



![](img/d64d01b71ce34c065794ea9c9a82a965_370.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_371.png)

Let's say we have three guys， and each one has two。So the half size， let's say， the half size too。

So we want to offset。Let's say half sizes are 6。Dided by three。Which is2。



![](img/d64d01b71ce34c065794ea9c9a82a965_373.png)

Yeah。😊，It is wrong。Plus half size Yeah， I suppose I just got got it wrong with the first time。



![](img/d64d01b71ce34c065794ea9c9a82a965_375.png)

Oh， now it's nice， okay。

![](img/d64d01b71ce34c065794ea9c9a82a965_377.png)

Now， we can definitely add a little bit of a。Of a difference here。



![](img/d64d01b71ce34c065794ea9c9a82a965_379.png)

And then。Add half of that here because they have some。Okay， nice， I'm going to do like 190 blocks。



![](img/d64d01b71ce34c065794ea9c9a82a965_381.png)

Maybe22 is a it too much？

![](img/d64d01b71ce34c065794ea9c9a82a965_383.png)

No， I don't know， I like that。Okay， what do you guys think。About what we have so far。



![](img/d64d01b71ce34c065794ea9c9a82a965_385.png)

嗯。I'm gonna do a， a。

![](img/d64d01b71ce34c065794ea9c9a82a965_387.png)

I think we have。We have like our left and right movements。Yeah， we have left， right up and down。

 What I'm going to do is if we press right。Prob do you like if。If development here。

 I have to clean this up later but。And that's okay。If you press。But on the left。

 that's what we did the first streams。 The first stream， actually， going to start game。诶。

I take current。Game mode， minus。What。😮，Other idea， the ball could be round and collide as a certain side of a box。



![](img/d64d01b71ce34c065794ea9c9a82a965_389.png)

But how would that change gameplay， though？Because it's a circle against a。Circle against a wall。

 It's going to reflect the same way。I think I may be wrong， though。Oh， because yeah。

 we have we will have blogs like this。I think。And in this case， it would be different。

 but I don't want the square one to collide like this。That's just not interesting。

 So I think all the balls are going to collide as a circle。Eventually。Yeah， we're doing it， yeah。

 we are collect as a circle because we are removing the box size and doing it as a point。

So we're doing the collision testing， the rectangle， the square。

But the reflection is just that zip was a subtle， but some collisions are different， for example。

 against the corners of yeah。But I think the circle is more interesting than the square。

Like for all cases。 So this case， if we hit like this。We want to work as a service thing。And in fact。

 when we do like a game field pass， we probably are going to do like a。

Rotated a rectangle based on the ball direction。I think that's going to be the final ball。

 a rotated rectangle。I think it's more interesting visually than a circle。嗯。Yeah。

 maybe we could do that later on， but that's the pain I think we're going to do a rotator rectangle。



![](img/d64d01b71ce34c065794ea9c9a82a965_391.png)

But。udeWe're going to do so much big stuff in terms of gameplay changes。That。



![](img/d64d01b71ce34c065794ea9c9a82a965_393.png)

That's why I'm admit， I don't want to be stuck in too much like， oh。

 small differences in block stuff。

![](img/d64d01b71ce34c065794ea9c9a82a965_395.png)

Because we're going to do crazy stuff in terms of gameplay ruless that that's gonna to be fun。

 I think you guys thought a little bit of a hint。 current game mode -1。 And if you do right。

 we're going to do。😊，Game play mode plus one current game mode。So I'm going to add a game mode。

G mode。Equals0。I think I'm going to do like。よし。Current gain already equals 0。

And then I'm going to do current game mode here。嗯。If game mode is greater or equal to。Eote count。

G mode equal equals 0。Else， if。Game mode， I don't think I'm going to test less than zero。Yeah。

 whatever。 yeah yeah， because we're doing -1 M。 So if it's less than  zero， game mode equals。

Count minus one and the count' is going to be always the last guy。Okay以。

And then I'm going to set current email mode。9点。Current game mode。Okay， I need to do this。



![](img/d64d01b71ce34c065794ea9c9a82a965_397.png)

Now if I press right， I change the game mode if I press left。I pressed left when I was zero。



![](img/d64d01b71ce34c065794ea9c9a82a965_399.png)

Oh， because I don't have these game modes， okay， so for now count is just these guys。



![](img/d64d01b71ce34c065794ea9c9a82a965_401.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_402.png)

F is correct。Okay， so we're playing this game mode， change to this one， go back。Oh。

 so see that was the problem I mentioned earlier。We use more blocks in one game mode than the other。

 and we're not clearing those。So they just start out as they。Yeah。😊，They're just there。

Let's see if what happens when I try to collide， I think it're just going to collide as normal。



![](img/d64d01b71ce34c065794ea9c9a82a965_404.png)

So we have to clear， see this incomplete reset the blocks。

We are going to reset the blocks and going yeah it's going to go through all available blocks and set their lives。

Toose0 their lives。To0， yeah。Here。走啦。Likefe。Equals0。They're not a life now。



![](img/d64d01b71ce34c065794ea9c9a82a965_406.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_407.png)

Are you game them by trade， yes。If you watch the first stream。

 I showed you a little bit of my history。

![](img/d64d01b71ce34c065794ea9c9a82a965_409.png)

But I worked with games for advertisements for some time until I decided to do a actual big commercial game。



![](img/d64d01b71ce34c065794ea9c9a82a965_411.png)

So that's the game I released， I released for the PC and the PS4。In 2017。

It was a long time of like three and a half years of development。And a lot of work。呃。

But the short story is， I realized that I didn't actually know programming very well and pretty much。

I thought it would have separate non game rate No I do have a nonga related job I was indie at this point professionally。

 but then I had an opportunity to have an investment on my startup which is not related to games so that's what I do in my day job and I've been doing games for as a hobby for like one year now。



![](img/d64d01b71ce34c065794ea9c9a82a965_413.png)

So that's why I'm doing like crazy stuff doing our own engine， you know。

 not worrying about the commercial aspect， you know。

 cloning breakout and having some fun with the gameplay because I don't have like commercial addition with this game and these kinds of games I'm doing now。

 maybe one day I'm going to go back and do like in the as a fulltime job again。

 that'll be pretty cool。

![](img/d64d01b71ce34c065794ea9c9a82a965_415.png)

Yeah， I could talk about my startup is actually in Portuguese because I live in Brazil。

It's called Ca Staus， means I want an internship。

![](img/d64d01b71ce34c065794ea9c9a82a965_417.png)

So we connect companies to people who want。Innerships。So the students race are here。

With their curriculum and stuff， and then we kind of find correct the right energy for them。

And that's pretty cool。But it's only in Portuguese because you only work in Brazil。

 actually you only work in this town， so yeah。

![](img/d64d01b71ce34c065794ea9c9a82a965_419.png)

And it's pretty cool， yeah， we've been doing that for one year exactly pretty much。And。Who knows。

 hopefully you go， you know。

![](img/d64d01b71ce34c065794ea9c9a82a965_421.png)

It'll be really successful。It's a nice opportunity to make games as a hobby because you don't have to worry about all this business stuff and not that I don't enjoy thinking about that。

 but in terms of games， I think it does far a little bit of fun because it would start thinking about。

 oh， maybe I'm going to do like micro transactions。Because it's going to give me more money。

 but they're going to make the game worse， so it's always tough these decisions so when I don't have to make them because I do them as a hobby it's all the battery。

What text tag do you use for that， are we're using node GS？For the backend server。

 And we're pretty much doing that。Only that。And we have like Amazon AWS as our service。So yeah。

Not fun programming jascript。 That's why I'd like to see here， because I。

 I really like the low level stuff。 But hey， that was the what the startup needed。

 That's what we did。😊，呃。And maybe she should like we do like a robustness pass in the startup。

 that'll be cool。Okay， now let's see if you can get that。Okay。So we changed game mode and if we fail。

 I think it's going to reset， yeah， it did reset。See。

 but now you can change game modes and now this structure。We can do all sorts of crazy stuff now。



![](img/d64d01b71ce34c065794ea9c9a82a965_423.png)

We're going to do a little bit of crazy stuff， but they we're going to do a whole bunch of crazy stuff。



![](img/d64d01b71ce34c065794ea9c9a82a965_425.png)

Hopefully that's cool right， So first of all all I'm going to do is I'm going to do the current game mode when I when I lose we're going do like a。

😊，Mnu screen， things like that later on I'm going to do we have the wall。

 we have we're going to do the construction。And the based。And then we can maybe start the guy。

Just for fun。And then we can do like a polished pass on these guys。

And then we can change the color and do all sorts of crazy stuff I don't want to do too much before we make a more interesting API to organize that because like if you you change the color。

 it's going to be yeah， I don't know。Okay， so we're doing the。The。The construction。

 the construction is going to be。Pretty much the same as the normal one。But we're going to have。

 we're going to offset by。By twice the。Like twice the why？

We're going to have every other role field and maybe we can do like fewer roles。0。



![](img/d64d01b71ce34c065794ea9c9a82a965_427.png)

The construction。

![](img/d64d01b71ce34c065794ea9c9a82a965_429.png)

O。I think that's going to be cool， yeah， I see。😊，I think that's interesting enough to stand it in its own level。

Or not， I don't know， it's just an idea。This is pretty easy， so。然。



![](img/d64d01b71ce34c065794ea9c9a82a965_431.png)

Just because I said it was easy I lost immediately after。😊，And I can do a little bit more。



![](img/d64d01b71ce34c065794ea9c9a82a965_433.png)

On the X guys。关。

![](img/d64d01b71ce34c065794ea9c9a82a965_435.png)

Okay， this is pretty cool， I think。Maybe you can do like。



![](img/d64d01b71ce34c065794ea9c9a82a965_437.png)

Mores。Like seven。And he started them。The lowerr like。



![](img/d64d01b71ce34c065794ea9c9a82a965_439.png)

Oh it likes to you？

![](img/d64d01b71ce34c065794ea9c9a82a965_441.png)

Yeah， I think I'm going to do。

![](img/d64d01b71ce34c065794ea9c9a82a965_443.png)

哎我。Yes okay。Think that'll be enough， then can play the game and see， okay， that's pretty cool。

 I think。

![](img/d64d01b71ce34c065794ea9c9a82a965_445.png)

Right。And I should maybe add。Some guys in the middle， that could be cool。Yeah。

I think I'm going to do that。

![](img/d64d01b71ce34c065794ea9c9a82a965_447.png)

Yeah。No， you know what， I'm just going to do the。The past。Yeah。Yeah。😊。

Because I want to do the really crazy guys later on taste。The spaced are it's going to be。

Is guy Jameses， that's it。Thanks too。And here I'm going to do times four。

Then I can do fewer blocks like new1。10 by six。

![](img/d64d01b71ce34c065794ea9c9a82a965_449.png)

Yeah。That see。Okay。I think that'll be cool， yeah。They a bit more unpredictable。Yeah。Okay。

 that can be a cool level。And then we can do the power up level。I'm thinking how。How。

I should do game， the game win， the level win。codeode now。

But I'm thinking about how I'm going to structure。对啊。Again get the difference is， oh。

 this is not right， it's still。

![](img/d64d01b71ce34c065794ea9c9a82a965_451.png)

Dude。I should probably organize this code before I go any further。To doing more。

Thing like create block and then it automatically enters。嗯。I think I'm going to do that。

 We're going to do like。Internal void。The black。Gre， black， black。Like， luck。Okay。😊，And。The number。

Anex。The number in Y。For now， all I'll do is just copy this code and create。Like black。

I'm going to 19。っぱいな。ok， lets see。Noumb。

![](img/d64d01b71ce34c065794ea9c9a82a965_453.png)

嗯。Okay。See， this apparently is correct now we are going to get this spacing as a parameter spacing。



![](img/d64d01b71ce34c065794ea9c9a82a965_455.png)

And it could be zero。 So it's going to be。小啲。Time is facing。And this is going to be times two。Times。

Spaceacy times too。Is that correct。Now it's going to be two plus，2 plus。Spaccing times two。Yes。😊。

2 plus spa。Thanks，2。Okay。Dgregate somewhere。And they go in direction。In two Q arguments。

 the spacecing is gonna be 01。

![](img/d64d01b71ce34c065794ea9c9a82a965_457.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_458.png)

嗯。😊，So the X offset was not correct。Yeah， it's not times the spacing， it's times one per spacing。



![](img/d64d01b71ce34c065794ea9c9a82a965_460.png)

Suggeestsing for a block type of block that one try to revive someone who that name is wow。

That could be cool。A block that when destroyed。Reiveed some of its neighbors。Yeah。

And that could be a cool idea to experiment that maybe be a little bit too chaotic。

 but definitely going to do that that's pretty much on the same vein as the block that gives power ups。



![](img/d64d01b71ce34c065794ea9c9a82a965_462.png)

So I'm going to do a block。Ls。Randomly。Revive their neighbors。When。Yeah。

 we're going to do a lot of gameplay stuff in this game。

 that's going be the the main ball code development， which is the point right。

 you want to develop the game， not the engine， the engines does just the。

Just a waiting for you to understand your limitations are not and improve upon that so bricks with a large space between them we did that bricks looking like a normal wall else have a brick。

 that's what we are doing。

![](img/d64d01b71ce34c065794ea9c9a82a965_464.png)

I mean， we have done that。It's this one， but we have to fix these guys。Right。



![](img/d64d01b71ce34c065794ea9c9a82a965_466.png)

Yeah。😊，Okay。

![](img/d64d01b71ce34c065794ea9c9a82a965_468.png)

So let's continue in this work， So I think we got it working right， yes。

 this is exactly what we wanted。

![](img/d64d01b71ce34c065794ea9c9a82a965_470.png)

We should now work a little bit more on the offset。So the offset。X offset is the， yeah。

 I'm going to work on that one more time。

![](img/d64d01b71ce34c065794ea9c9a82a965_472.png)

Because now it's going to be the final one。

![](img/d64d01b71ce34c065794ea9c9a82a965_474.png)

That's going to be a cool cool game mode。啊。不拿。尤其的。Pace the ti。

Oh I don't know if that's the best description going to draw。Going to do like this。

Let's do with Mike。嗯。です。嗯。Yeah。😊，Okay。And that's the plate down there。That's going to be a cool one。

 I think。Soci to say people have fun instead of debugging highly crypttic skills yeah that's the point man'。

 if you see the very first stream I said very clear that the main point there are three main points is to learn。

To help you guys learn and to have fun right so we want we don't want to do like complicated stuff it's been like。

Always going to be clean code and organize stuff for a big team and stuff， no man。

 I this isnt going to have fun to make a game。Yeah， that's why we're using C C is like ways simple。

 we don't have we can just take a quick look and understand the problem。

 so that's going to be a pretty cool game what I think。But I want to do too much。

 I don't want to do too much。Breakout related game mode because that's going to be the fun part。

 this part right here， I don't know if you guys understood what I meant。

But this is going to be the cool thing， I don't think we're going to be able to do that today maybe。

 maybe I'm just going to finish this great black black thing。呃。



![](img/d64d01b71ce34c065794ea9c9a82a965_476.png)

Okay， so the idea is I want to standard these guys。So I may even pass a position right。

 so if I pass position， I want to center the guys is based upon this position。

I want to add each block size and each block size。

![](img/d64d01b71ce34c065794ea9c9a82a965_478.png)

It's going to be the block。🤢，The block half size。Yeah， each block sizes this， right？

Block half size times  two plus spacing times  two， so this is the block half size。

This is the blockhouse size。So I'm going to add all the block have sizes。All of them should be。See。

 that's the thing I don't understand if p pass zero， it's going to start at the zero position。



![](img/d64d01b71ce34c065794ea9c9a82a965_480.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_481.png)

Perfect， I want to end at the zero position。So what I should do is like two half block time times two。

Plus two times spacing。So this shouldly。The endposition。



![](img/d64d01b71ce34c065794ea9c9a82a965_483.png)

If I am not entirely mistaken。Yeah， that's not it， that's one block off。



![](img/d64d01b71ce34c065794ea9c9a82a965_485.png)

guess should like。

![](img/d64d01b71ce34c065794ea9c9a82a965_487.png)

That looks about right。

![](img/d64d01b71ce34c065794ea9c9a82a965_489.png)

So all I have to do is half of this whole thing。

![](img/d64d01b71ce34c065794ea9c9a82a965_491.png)

Okay， then I think might be。In a good shape。

![](img/d64d01b71ce34c065794ea9c9a82a965_493.png)

嗯。

![](img/d64d01b71ce34c065794ea9c9a82a965_495.png)

还没行。

![](img/d64d01b71ce34c065794ea9c9a82a965_497.png)

No we're not ne maybe this guy doesn't get yeah， this is pretty much trying error。

 I'm sorry I'm failinging completely at doing this。



![](img/d64d01b71ce34c065794ea9c9a82a965_499.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_500.png)

Yeah。

![](img/d64d01b71ce34c065794ea9c9a82a965_502.png)

Okay， this is correct。 Now I'm going to try to use that for the other guys。

 And that's I think the problem。 I'm going to do that for the spaced because that's mostly the easiest one。

 I'm going to do a block。哎呀。A start block block。I don't remember what we called it。

Create black block， yeah。Create black black。And I'm going to do。Space is going to be one。

And I'm going to do。Sa 10。Like6。

![](img/d64d01b71ce34c065794ea9c9a82a965_504.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_505.png)

四。This is wrong， maybe because of this guy， maybe this guy we should also。Offset by the spacing。

 I suppose。T basin。

![](img/d64d01b71ce34c065794ea9c9a82a965_507.png)

And。

![](img/d64d01b71ce34c065794ea9c9a82a965_509.png)

That's the whole block。And if you have half of that。Go to start。

Oh because we don't start at this point， Oh okay， I think I understand the problem。

 we don't start at this point， we okay。

![](img/d64d01b71ce34c065794ea9c9a82a965_511.png)

This position is the center position。Correct。So。Center position。

I do have to subtract half the block size from that。Let's suppose the spacing is zero。

So all I'm doing here is moving minus the offset， yeah。That's why I'm having this guy。

Here in the offset。Because this guy needs the center。Okay。Sounds about right。 So the half size。

Times one time spacing。Oh， I'm sorry， one plus the spacing。



![](img/d64d01b71ce34c065794ea9c9a82a965_513.png)

I think we are getting somewhere。

![](img/d64d01b71ce34c065794ea9c9a82a965_515.png)

Okay， this looks perfect。Let's see， and this looks perfect。Okay， we finally got it。



![](img/d64d01b71ce34c065794ea9c9a82a965_517.png)

I think I'm going to drop these guys a little bit on。



![](img/d64d01b71ce34c065794ea9c9a82a965_519.png)

Why。yeah that was cool， finally。

![](img/d64d01b71ce34c065794ea9c9a82a965_521.png)

Okay。That looks cool。So。You know what I'm also going to do instead of doing the。CW default。

For the position， I'm going to set。The window position maybe to 0。

0 because sometimes the window goes a little bit。too low for the guys to see。



![](img/d64d01b71ce34c065794ea9c9a82a965_523.png)

Now you guys are going to be able to see the position all the time and we're going to do like full screen mode later on so。

It's not really that important。ok。This one we going to fix this one later on。

That was Mar's suggestion。This one's pretty cool。Yeah。Yeah， see， that's pretty cool。This one。Yeah。

 this one。Ha to some crazy stuff later on， because it's like you're doing like the。See。

 you're doing like the fun part。Of the other game modes， but like all the time。Yeah， okay see。

This one。It's kind of like the other one。Spaced， yeah。There's like pinball， actually。Because of it。

 you know， it kicks all around。Like almost randomly。Yeah， see。I think that's getting somewhere， guys。

Okay， these are the four game modes we have for now。



![](img/d64d01b71ce34c065794ea9c9a82a965_525.png)

Okay， we're going to do the wind condition and then we're going to start doing the more crazy game old like。

 oh， I'm just going to do， I'm sorry， I'm going to do these guys。啊。As the this guy as well， so。

Let me see what else I need and we need to change this guy。Which。Maybe for these guys。

 I'm going to hardcode them。I'm going to， yeah， because they're like a little bit more specific。

Going to keep them。

![](img/d64d01b71ce34c065794ea9c9a82a965_527.png)

This way。I probably do the offset correctly。

![](img/d64d01b71ce34c065794ea9c9a82a965_529.png)

Just because we kind of learned a little bit more about that。The offset。The offset should be black。

Have size dot X。At this guy。At quite size anymore。Same thing that X。Plus。ok。And then the offset。

It's like hard coded here， you can pretty much copy from this offset。Yeah。哎， that's。Dude。

 I want to get， I want to finish this quickly so we can do like some crazy game modes before lunch we' going to have to leave you know。

And some time。Okay， so I'm going to do the same thing as the block X。Yeah， black acts have size。

Black X have size。Spaccing。How much the spacing， there's no spacing。In the wall， because it's a wall。

Sppacing declared in fire。Okay。Here。Semicoon。

![](img/d64d01b71ce34c065794ea9c9a82a965_531.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_532.png)

嗯。

![](img/d64d01b71ce34c065794ea9c9a82a965_534.png)

I think this guy's going to meet， I'm going to need to offset by two。



![](img/d64d01b71ce34c065794ea9c9a82a965_536.png)

And when we do like the closed wall。

![](img/d64d01b71ce34c065794ea9c9a82a965_538.png)

I'm sorry， by none。When we do the closed， we're going to have to decide on that。



![](img/d64d01b71ce34c065794ea9c9a82a965_540.png)

Yeah， I'm going to do like。

![](img/d64d01b71ce34c065794ea9c9a82a965_542.png)

。in5。

![](img/d64d01b71ce34c065794ea9c9a82a965_544.png)

Okay。It's okay for now。And this one， this one is nice。



![](img/d64d01b71ce34c065794ea9c9a82a965_546.png)

I think I can add one more。In the space guy。

![](img/d64d01b71ce34c065794ea9c9a82a965_548.png)

です。Okay， not nice， yeah。Okay， so the plan is。

![](img/d64d01b71ce34c065794ea9c9a82a965_550.png)

We're doing the gameplay stuff， right？We're doing the gameplay initial expectation we're going to do。

呃。More。Right now we're going to do the wind condition right wind condition。

Then we're going to do more complicated game modes and we're going to do a small。C用。Pass。

It's going to be colored。Squashhy and stretchy。Things like that。

 And then we're going to do the engine。Improvements， not sure we're going to do Bimap at this point。

 but we're going to do particles， so that's fun。And。And then we're going to do more gameplay stuff。

Okay， that sounds about right。 Let's do the wind condition。 I'm just gonna keep a counter of。

Or we do have， we have the next block。The next block is actually the number of blocks。

 I'm going to do the number of blocks。And then I'm also going to do the blocks。This is right。Okay。

 the number of blocks。I'm sorry， I had it。Here， the number of blocks is。

Zero and rec create however many blocks we want。And the。ABs destroyed。Is0。哎。😊，Now。

 whenever see next block can be。Noumb blocks。Okay， and。Whenever we destroy a block， I'm going to do。

Test for。我给你看得行。Okay， that's easy enough。I're going to do internal and we're going to do is split that in different files。

When it gets a little bit more complicated， maybe when we do complicated game modes。嗯。😊，Initial void。

Turnal void amies， okay， test following condition。If。Oh， we could also add the number of blocks out。

 number of blocks that destroyed。Plus， plus， if。Number of blocks destroyed is a number of blocks。

We want。 So we're going to。Change game modes。Start game mode， start game。Passing。Current。

TheO plus one， so we'd have to do that after。This ourrcing。Okay， that looks good， I think。



![](img/d64d01b71ce34c065794ea9c9a82a965_552.png)

Things going to be cut hard for us too。To win， maybe're going to take a while。

Kn what I'm going to do。I'm going to do like a cheat。



![](img/d64d01b71ce34c065794ea9c9a82a965_554.png)

Where I'm going to。You're going to do up for invincibility。So。启功。Invinible， it was not invincible。

Okay。😊，少人。Intenible。Pos house。And we're also going to speed up the game。Like。Press down。

 I going to speed it up a lot。So you're going to do like DT。Multipier equals like 10。

We might break the game at this point？But you know， it's just。Just to be quick about testing。

And here you're going to do DT。Times equals Dt multiplier。And a DT multiplier。

It's going to start out C， Yes， we are doing C。 exactly。 C is the most fun language we have so far。

 So let's do that。😊，That's the point。The team multi supplier。

 then we're going to do more energy free press。Let's do we through release down。If released。But down。

Will you reset and multiply one。

![](img/d64d01b71ce34c065794ea9c9a82a965_556.png)

Let's see if this works。 Now we should lose okay， we should lose。 now Immissible。



![](img/d64d01b71ce34c065794ea9c9a82a965_558.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_559.png)

Yeah， but I do have to kick the ball， right？Else。包。P那DP。Dot by。マ。Okay。

 I should probably also change something visually。来。😊，If in principleible。m goinging to draw It know。

We're going to change the player。Color to white。

![](img/d64d01b71ce34c065794ea9c9a82a965_561.png)

I don't know。Okay， now if I if I。Okay。诶。Not as to win this game。Yes。Okay。

It's glad to see everything working pretty much perfectly at this speed。

We should also print to this screen。Okay。That was interesting。Okay。

 let's see if you're going to win or not。We did win。



![](img/d64d01b71ce34c065794ea9c9a82a965_563.png)

Okay， guys see。That it was pretty cool， but we didn't reset the ball position。Oh。

 because we have to do that down here。We can't change can't restart here。So what I'm going to do the。

The start game is going to be the。嗯。Okay， instead off doing the start game here。Here。

 I'm going to do the。This is a bit of a hack。 We're gonna to do a。Start game。And。开始。Advance。げゲ。Yeah。

😊，诶。And down here， game over， or I'm going to change the task the advanced game mode。

Then we're going to start。Okay。You know， we do have we are going to do some cleanup later on。

But for now。I think this is good。D team multiplier。嗯。Where maybe here。嗯。Yeah。

Advance game of equal spell。And when we do start game， you're going to set the advanced game mode。



![](img/d64d01b71ce34c065794ea9c9a82a965_565.png)

Okay。Now let's test that。

![](img/d64d01b71ce34c065794ea9c9a82a965_567.png)

Dude， we could do like some crazy， slow motion stuff like。

I almost thought I really lost about that for a second。Maybe we did。Wow， we went all the way around。

 okay。Let's now win this game。Command。Okay。Okay。Okay。All right， isn't that what we wanted？

And I were not in this anymore。

![](img/d64d01b71ce34c065794ea9c9a82a965_569.png)

呵呵。😊，Maybe what amm going to do for this build。I think。I'm going to。The game over be start。

The first level， maybe。What do you guys think should be？Shouldn't make the player have to win all。



![](img/d64d01b71ce34c065794ea9c9a82a965_571.png)

I't know all the levels。At once or maybe one at a time。



![](img/d64d01b71ce34c065794ea9c9a82a965_573.png)

Yeah， I know what I think I'm going to do。What at a time。

I'm not that evil of a game designer anymore。Okay， we are in good shape。We did the wind condition。

And now we're going to do more complicated game modes。

 and I think that's what we're going to left off for today we're going to start doing more complicated game modes。

And we could do like pickups。We can do it like dead neighbors。Hey I we're gonna do pong。

 I want to do pong guys that that was the whole idea of the game， right。

 the whole point of the game is to do that。So。We've got to do that quickly and then we're going to do a small fuel pass and then we're going to do engine improvements。

 audio， threading particles。Bitmap， notture。Level editor， Not sure。More gameplay exploration。

Then a polish pass， that does look like a good plan。Yeah。

 we're going to need some sort of laboratory rhetoric to express these kinds of a。

And maybe here we're going to do audio threading particles and I think I'm going to do like rotated。

Rightect。That's going to be fun and difficult and if we do that， we might as well do bitmps。So yeah。

 I think we will do this。And then we can do a like。APo pass。 You're gonna to do engine。

 We're gonna to do a profiler。We're going to do a cooker， acid cooker。Okay， yeah。Okay。

 we're starting to get， you know， Mar advancedta， so what we are going to do now。

 we want to do a GMm。That's it powers。The thing about GM powers。You know。

 we may actually do this as the GM powers。Or one of those。I don't know。But the point is。So far。

 we only make the distinction of the game mode when we start again at this point。

 but if for're normal we create this kind of block， if we space we create these kinds of blocks。

 the wall and the construction。And we need that。But now， we also need。This。

Like what happens when the ball gets destroyed？A block gets destroyed。

And we are also going to need more hooks。So what I'm not sure。The better way to do is maybe。

This whole simulate game。It's actually a simulate game mode。And we write pretty much that。

Different times for different。Guys。Not sure。Ma lead to some crazy copy and past or this guy。

Or maybe we add a hook like we have to start game mode。Right。Maybe we can do like。

Tnal void players cordor。Or block destroy， Yeah， I think that's going to be better block destroyed。

They're going to pass the block。Yeah。😊，That sounds good， actually。If the block is destroyed。Block。

It's right。For now， all I'll do is the test when condition。Like this price concentration Oh good map。

Test form condition， and then I'm going to do a switch on the current game mode。

And in case we are on the。The power up。呃给们。We are going to do spa。Power ups。

What do you guys are thinking about when you think about powers。

 what kinds of pars would be interesting on this kind of game？Invincibility is the obvious one。

But I think we can do of more balls， that'll be cool。Part up where when you hit the bolt。

 I think I'm going to do that。

![](img/d64d01b71ce34c065794ea9c9a82a965_575.png)

When if it's a ball。Different balls project。Different sides。But once they hit something。

 they get destroyed。So this way， you know they don't go back at you or maybe they get destroyed try when their DP equals。

 yeah， okay， thinking that's going to be fun。

![](img/d64d01b71ce34c065794ea9c9a82a965_577.png)

Give parads。Okay， so powers ideas。I doing inscability。We're going to do more balls。Swn of your。呃。

 talentent。That was the correct term。Yeah， I't know your。There。More balls spun off the player。呃。

If they are。呃DP。Dtly is greater than 0。They get tried。Okay。Looking good。 Looking good。呃。

And then we could also do a。A。Game mode with more balls。Hey， we do like the De guys？

They revive their dead neighbors and blocks randomly con more balls。When killed。看。

Thatll be a tough game mode。Okay， so yeah， let's do these pickups。 We already have the intensibility。

😊，嘅 mode。And what I am going to do now is a game modestruct to hold。This information， right？

So I'm going to do like Kingstruct。Type thating mode。State。呃。Is going to be a union。

Of all the different game modes we want。 So maybe I'm going to create a。A file for the game modes。

I don't know。那 yetな yet。Okay， so I'm going to create astruct。嗯。G old states。Okay。

 going great structure， which is gonna be the。呃。Game called G M。Power ups。State。

And I'm going to have a array of paras。That's say 16 startups。Pox。I'm going to restruct。Power。2月份。

And I'm going to have a part of kind。可。😊，Pow。We're going to have power up。Me间系。A power up。

It's called that triple shot。ちと？Shut。Yeah， let's do that for now。

And the power up is going to be I'm going to have a power up kind。Kind。Yes。Yeah， that's。

 that's honestly all。All we need for now， I don't know， let's see。

This is going to be the GM para up state that have paras。When I have。In invincibility time。

And we're going to have。A numberumber of。Triple shots。O。😊，And when we start the game mode。

We are going to set the current。Now， the game called state。2，0。Yeah。😊。

I'm going to do like a power up。I'm not sure I'm going to do structure that。嗯。Like。

That's do the player inibility thing。If've been invincible else drawing like this。But。Spawn powers。

 okay。Let's do a spa power up。Function。And then you can decide how you're going to what we need。So。

Spawn par。For now， let's just pawn the。Invincibility， because we already have that program。

So we're going to have like the next part up。So powered up。Per up。Equals power gains。I would state。

Dot powerups。Plus， name of state。Dot next part。Okay。I'm sorry other that。Gm。开会啊。Our ups。嗯。

I have to cast to a game always。Task screen conditionition， redefinition。Yeah。I do have。

 I think I'm going to have to no， I don't， I was going to have to predeclar that。

Block destroyed to a few arguments， this block got destroyed。It like。Okay， in fact。

 I'm not going to do the power up steam mode。I am going to just make the wall game of gives part us for now。

哦。All parts okay。Yeah。We are going to， let's see。Get the power up。Por of dot P。

 So now we know that we need a P。 It's going to equal the block P。Let's do a P。一sB。

And the power of kind。It's going to be powered up。秘めており。Okay， so we need A P。And a kind。Okay。

We should also do like an active。Yeah， or you can use that kind of like power up。Inactive。Okay。

 and then I'm going to pass the block。Okay， now the same thing we did for our blocks array。

You're going to do like， if。If we。K of lost my train of thought。Next part up close plus if。

Next part game old state。The next product。Is。Greater than。Game mode state。P ups a re count。

Greateater than or equal to。We are going to set it back to zero。

 so we're going to have a recycling system of fires。Okay， so。嗯。I may also do a post。

Like a pre rendernder。Game mode pass like pre render simulate game mode。Like this。Think they'll be。

Yeah。Let's to assimilate。电脑。So because we need to render these guys， but only if we are in the。

Wellald game mode， we could call it like well and powered up game。So， internal。W simulate。G mode。

we switch。On the game mode， on the current game mode。Okay， and if we are。On the wall game mode。

We are going to。Getive it my for。I'm going to。Go through all the powerups。喂。😊，P up。好玩了。

Itquals game mos。State。Got power ups。W powered up。Is not ski mode State dot power ups。

Plus a eight count。You should have like a。For that。Per。嗯。All up。Okay， for every power up。

 if we were supposed to enter that。We are not。We are our kind。you like not people。

 If her time is not， my God， let's do it。 Power up。Connective。It is an exit， sorry to continue。Okay。

 so now I'm going to draw the power up and then you can simulate the power up。

 So for now I'm going to do is draw like a。Are we using the yellow， I think the ball is yellow。

 right？Let's get a ball here。嗯。Trus the ball here。No， the balls not yellow， let's do。

 let's do an orange part up。Or yellow one， yeah， whatever。Okay。This is gonna to be。A。Power of do P。

We're going to do like hard color for now， we're going to do like two， two。



![](img/d64d01b71ce34c065794ea9c9a82a965_579.png)

Okay， let's see what happens。

![](img/d64d01b71ce34c065794ea9c9a82a965_581.png)

For now should happen nothing， okay， nothing happens， but if you change game mode。

W should spawn a apart up， okay， we do spawn a apart up。Dude， today's like a great day。系。😊，Yeah。

That's cool， what？Now we can do。Either scenario now it's starting to recycle paras。

Now we can either start。Oh wish， also， we are resetting or not。Not sure we are resetting though。

Oh we are because we're clearing the RH to0。So the point is。We're not sure we should hit。

It a ball or move to get it。 Maybe you should like a move for now。 But I think that's it for today。

We did like a lot of stuff to。See， because once we got the basic engine going on like we did in the past couple of streams。

You，I think that was a nice choice for the pi。

![](img/d64d01b71ce34c065794ea9c9a82a965_583.png)

呃。Like we did。That structure。Now it's really easy now all I have to do is know。

Sorry implementing stuff。In terms of ideas， not in terms of what we have to do right。

 so more complicated game mode speakups than neighbors pond。Do you like a nice？Clean up。

On the game mode system， we have to do that。And then we can do a small fuel pass， color， stretching。

 squashing and stretching。And then we are going to do the engine pass。Does that sound good， guys。

 I think it does。 So we did a lot of stuff today。 I mean， today was mostly。😊。



![](img/d64d01b71ce34c065794ea9c9a82a965_585.png)

We got to the fun part， I suppose the most fun part。

It was great to think about all these problems we did in the past couple of streams。But today。

 like pure gameplay stuff， dude just like sit down and make a game。

 what kind of game would want' make， I a know， start making a game and then you figure it out along the way。

嗯。Stroggly implement a life system to be more forgiving。So we don't have to like。Get everything。

And I'm going to post the source code。And the executable on the games's HIO page and you guys are welcome to try that out。

 you know， comment， what do you think about what we did today in terms of the ideas in terms of game feel。

 oh miss it。Inm of the feel of the game， you know， especially the。

The direction thing that we did because we're not focusing on like making it up colorful and splashy and dynamic in this sense。

What we do want to do is to have it responsive before we focus on the more， I know， flashy things。



![](img/d64d01b71ce34c065794ea9c9a82a965_587.png)

Yeah， so if you want to play around the source code and the game。



![](img/d64d01b71ce34c065794ea9c9a82a965_589.png)

All you have to do is come here in the games HIO page。 I'm going to throw that link on the。

On the chat， I was going to put that on the YouTube video and you can download see there's episode1 source code。

 episodes2 source code， and as soon as I finish this stream， I'm going to post episodes3 source code。

So you can download， you're welcome to give me a tip or not。

 it's okay and then you download source code and play around。

 it's nice if you're want to follow along and make your own games， start with the first episode。

 watch it and do the same thing because。

![](img/d64d01b71ce34c065794ea9c9a82a965_591.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_592.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_593.png)

It's very easy for us to change this game to be whatever game we want。Because all of the other stuff。

 like the math， the utilities， the Windows， software rendering。The collision system。

 we't have to touch that at all。That's the only thing we need， you know， we have a function。

 we receive a call asking us to simulate and all you have to do is simulate and call the renderrring stuff can get the input。

Pretty easy， so。And if you want to watch the previous episodes。

 you can watch that on my YouTube channel， which is YouTubebe。com/dam Zd。



![](img/d64d01b71ce34c065794ea9c9a82a965_595.png)

Couldnt watch episode 1， episode 2。 and I'm going to post episode 3。

 and I'll see you guys next time we stream。 I hope you enjoyed it。 I did。

 Certainly now we're starting to have a more concrete game。 That's always fun。 So thank a lot。😊。



![](img/d64d01b71ce34c065794ea9c9a82a965_597.png)

See you guys next time。