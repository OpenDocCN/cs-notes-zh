# 【从零开始用C语言制作游戏】 p16 Making a game in C from scratch! Ep 16： -Optimizing the Game (5x fa -BV18i421a7DD_p16-

Helloello everybody， welcome to this new live stream in a series where we are creating an entire game in C from scratch。

 if you have been following along， this saw the game progress all the way from nothing。😊。

To where we have now， and let me show you at what point we are at the game。



![](img/d2b281400e0d90c00f492f0adbc6943a_1.png)

So last time you created a school name main menu with all sorts of animations and things like that。

And you can go ahead and play。The level， the first level was just breakout flow。

Because that was like the start off idea for the game？う。And then we added。🎼えや。

Breakout with powers and parads， which was a。The starting point of。Yeah， see。 I got this。

 and last time。We added that UI to the player。W来。Where he can。

See what power ups and car downs it has。In theecting him at the moment。诶。

Pretty cool and we also added breakout pond。Which was like。The base idea for the game was like。

 what if all ourcade games had to be like breakout？🎼Yeah。So， these are like。

Some arcade games that we implemented just to have a。

A more fuel for the game and what we wanted to build。🎼北こ。And then we the breakout spa invadeters。

Okay， and the past was streams we added a lot of fl。It's more of like sound effect。怎么看 mean。

Individual things that built up to making the game a lot better， like sound effects。あしい。

The menu of the interface and all sorts of crazy stuff。However， we have a control problem。

If you see on the top right corner of the screen， you see the frame frame rate counter。

 which is like in the milliseconds per frame so we're going like。For milliseconds per frame。

 Its pretty fast。However， in the menu， we are going a lot lower， we're going 11 trains per second。

Oh and the force field effect not turning off， nice to see that bug。

And that problem affects our player visual and sound。



![](img/d2b281400e0d90c00f492f0adbc6943a_3.png)

🎼So。we're going to start optimizing that today， so today is going to be a hardcore coding stream where we should optimize understand code but and also view a profiler。



![](img/d2b281400e0d90c00f492f0adbc6943a_5.png)

Okay， so let's just fix these small problems。 I've also， I also had a couple of problems that I。

Realized when I played the game， I had a collision problem。And I think I have some idea。

Of what is happening。And that's also add。TheFors。Force field。It's just takes the force of it out。

 not turning it off so force。诶，晓。Sound。Yeah， whenever we start the menu。Let see。Which is here。Change。

G mode whenever we go to the menu， we should zero the first few attempt。

That's it fixed and we had another collision problem and that was even more evident in low frame rates。

 so I think I'm going to turn off the optimization flags。And I'm also going to let's say。

 I'm also going to increase。

![](img/d2b281400e0d90c00f492f0adbc6943a_7.png)

The game window just so it runs slower。Yeah。😊。

![](img/d2b281400e0d90c00f492f0adbc6943a_9.png)

Ha to do that in game。Because we have all sorts of problems we should fix in terms of light performance so if you go to like a larger window。

See now we' wearing like seven frames per second。Our seven milliseconds。

W's a lot better than seven frames per second。See that that looks。Not， correct。

I make that run even slower。

![](img/d2b281400e0d90c00f492f0adbc6943a_11.png)

Yeah， see in the main menu， we run so slow。That crash the game。that's because of the plate of pe。



![](img/d2b281400e0d90c00f492f0adbc6943a_13.png)

And just so that doesn't happen last time you had AE。We had a clamp here， that's for that clamp back。

Well， let's make it like。Dig enough， so we don't。Worry about that in normal circumstances。



![](img/d2b281400e0d90c00f492f0adbc6943a_15.png)

I see。🎼Is see。

![](img/d2b281400e0d90c00f492f0adbc6943a_17.png)

I know have to。Let's not worry about that。 We have to improve first let's improve the performance。

 Then we can go back and 6 bucks。 Okay， but the collision problem。

 I think was something else because we had the notion of a ball collision P。

 which were we were using So let's say we had two blocks。



![](img/d2b281400e0d90c00f492f0adbc6943a_19.png)

念灯包。Did something like。です。So it had a targeted position， which was this guy。

The position went through this guy， so this guy would be eliminated。

 but since the dark position would also collide with this guy， we would still destroy this guy。

 So that was a problem by using the collision thing。And now， in this case。We destroy this guy。

 and then we test with this position。 That sounds good， right， However， there is a problem。

Let's let's say the server stands like this， so we want to go like this。

But then we collide and we go like this。So this guy got gas destroyed。

And this guy is going to test against the imposition， correct？Kind of correct， because。

What happens is if we have already run through this block， the collision run。

We are not going to run through that again。Because， I mean， order into the blocks。

And it gets to a point where we already tried this block and then we tried this one。

 and then this one changed the ball position。So we updated opposition。

Destroy this block and then just keep going to the next block what I think we should do。



![](img/d2b281400e0d90c00f492f0adbc6943a_21.png)

And I'm not sure how bad will be in terms of performance。 I mean。

 clearly not worse than the rendering， which we're going have to take a look at today。

But much so if you go like to blog。Let's see。Wall movements， Raha。When do we do， like the。The black。

Yeah， we do seem late black per left。Yes， if we do collide with the block。We break through this loop。

 which is for every ball， but we should also try every block again， So I'm going to。Reset this guy。

And comments like。If we collideed。Test。All the blocks。Other blocks。So later on。

 if you want to optimize that。We could do a。

![](img/d2b281400e0d90c00f492f0adbc6943a_23.png)

A spatial partition shouldn't be too hard because。It's it's pretty easy to divide them in different blockss。



![](img/d2b281400e0d90c00f492f0adbc6943a_25.png)

Make them run like。啊。So we have rear meeting。

![](img/d2b281400e0d90c00f492f0adbc6943a_27.png)

Said oh yeah。Technically should be disconnect guy。Yeah。

 but it shouldn't be too hard if you want to optimize that to kind of only try to do the collision with you。



![](img/d2b281400e0d90c00f492f0adbc6943a_29.png)

Laled there are actually close to you。几数。

![](img/d2b281400e0d90c00f492f0adbc6943a_31.png)

Pretty sure we failed。Pretty sure failed that I should really be record while I am recording， but。

Maybe I should take a look at that video， I'm going to stop and start recording。Okay。

Now let's just see going open to Premiere。Just so it's easy for us to see the video。

 I'm going to see what happened at the very end of that recording in order don want to spend too much time with collision。



![](img/d2b281400e0d90c00f492f0adbc6943a_33.png)

Today。😊，Because today's like optimization date， but we're not going to do like the full optimization so we're just going to start。

Just start the path。To optimize by just。Wrtiding a profiler to understand our code better。

And things like that。Okay， let me just turn these man。Smaller。And then， I'm going to。来 see。

I'm pretty nice， right。Yeah， let's see。軽承？So if I can turn the volume down。嗯。

What happened to this screen？Oh yeah， this is actually the。IHave to reduce that size。可以。OK电览器。哇。

 let's嚟。Here， it's okay。Yeah。Let's see what happened。So， we hit this block。See， that's what I think。

I think we should have fixed that by just doing that， so I'm running again through all the blocks。



![](img/d2b281400e0d90c00f492f0adbc6943a_35.png)

With a new position。As the test position simulate well。嗯，而 see level。Simulate。Lock for level。Yeah。

 this's not entirely correct， we should yeah， we can't do that。嗯嗯嗯。Let's do like。First best。

This is really a hack。Okay， but then we do。For every ball。Do b black。Yeah。

 then we use the ball desire to be。That's the one that we update。Correct。3楼。

This looks pretty correct to me， I think let's start debugging that pretty quickly I'm going to put a break point。



![](img/d2b281400e0d90c00f492f0adbc6943a_37.png)

Let's see I don't have the levels where I'll just close the game。If we put a break point， let's see。

Here we have the game。And whenever we change。It's a brief。Okay， so we updated the block P。

Blolock shouldn be， it's not valid。And the ball we changed。Yeah， the ball。

 so now it's not first passing anymore。Then we reset the block。Didn't the break work？Oh， that okay。

 so this dramatic。We shouldn't draw the block， in this case。



![](img/d2b281400e0d90c00f492f0adbc6943a_39.png)

But I don't think we did。This looks like the particle。



![](img/d2b281400e0d90c00f492f0adbc6943a_41.png)

嗯。Let's just see what we have so the block。Okay， now it's a valid block again。It's。Yeah。



![](img/d2b281400e0d90c00f492f0adbc6943a_43.png)

Oh。But this is wrong。

![](img/d2b281400e0d90c00f492f0adbc6943a_45.png)

Yeah。😊，The first pass should not resimulate the blocks。

So maybe you should have like simulated flag that we said that falses every frame。

I know this is kind of hacking。Maybe we can split that into two parts， first simulation part。

And then the。Coalition part。Collission and rendering。But then we should that。未必啊。

I don't know if I like that。 Now we're running for the block like three times and possibly four。

This guy。

![](img/d2b281400e0d90c00f492f0adbc6943a_47.png)

Let's see what we have。

![](img/d2b281400e0d90c00f492f0adbc6943a_49.png)

Just。

![](img/d2b281400e0d90c00f492f0adbc6943a_51.png)

So， we set the block。Yeah， this is a little bit more correct。



![](img/d2b281400e0d90c00f492f0adbc6943a_53.png)

Yeah， that that looked pretty。P perfect。Not sure how bad we are though。

 at a performance because of that。あ。

![](img/d2b281400e0d90c00f492f0adbc6943a_55.png)

And looks， looks。It's pretty cool。 But let's just check。Performance now。



![](img/d2b281400e0d90c00f492f0adbc6943a_57.png)

3。And form me the second for frame。I'm prettyty sure we were。And something like that。

 yeah because you don't haven't that many blocks， Okay， so yeah。那's。Let's keep it like this for now。

Okay so supposed。We fixed that and let's just play like。



![](img/d2b281400e0d90c00f492f0adbc6943a_59.png)

对不是 the game。That's planned in the space invade is just rather the collision。

It's really more evident for this。是。Yeah， I think it looks。



![](img/d2b281400e0d90c00f492f0adbc6943a_61.png)

Looks pretty perfect to me。Turn your volume back up。



![](img/d2b281400e0d90c00f492f0adbc6943a_63.png)

mMy avoidant as well？Okay， so let's。

![](img/d2b281400e0d90c00f492f0adbc6943a_65.png)

That's people like this for now And there's also a problem that when I finished the spa invades。

 I could I didn't actually save。😊，And was a pretty that was a bmmer。You at the levels。Like test。啊。

For wind condition。Victory， see。We should save。If it's。Both of these cases。Okay， so this is， this is。

If the current level is greater than or equal21。Then I unlock the next one。Yeah， then I should say。

But then。Okay。And then if maybe update high score， then save。7。😊，The score。

It's greater than the saves high score。I don't know if guy of looks correct。Then the result is true。

And we changed the highest score to the score。

![](img/d2b281400e0d90c00f492f0adbc6943a_67.png)

嗯。😊。

![](img/d2b281400e0d90c00f492f0adbc6943a_69.png)

Maybe I'm going to have to test that again。

![](img/d2b281400e0d90c00f492f0adbc6943a_71.png)

Well， that's just for the。See basically of it。Likeking invaders。



![](img/d2b281400e0d90c00f492f0adbc6943a_73.png)

不要。Yeah， we do have a button right to win the game， so we have zero。



![](img/d2b281400e0d90c00f492f0adbc6943a_75.png)

🎼Now， if we win should be 14， see。

![](img/d2b281400e0d90c00f492f0adbc6943a_77.png)

I don't know what's going on level， let's say at line 3 for T。Al that's put a great point。



![](img/d2b281400e0d90c00f492f0adbc6943a_79.png)

A test when condition。

![](img/d2b281400e0d90c00f492f0adbc6943a_81.png)

Yeah。Okay， so I just pressed。Fin the game。And then the block destroyed。Is the number of blocks？

So you're supposed to finish the level， not state。Yeah， so it changed， oh。

 because you changed the game mode before。嗯。So at this point， current level。Its invaders。

 but the score is 0。

![](img/d2b281400e0d90c00f492f0adbc6943a_83.png)

啊。You could like， go back。年ニ。

![](img/d2b281400e0d90c00f492f0adbc6943a_85.png)

Okay。That break went for now and let's see。Okay。

![](img/d2b281400e0d90c00f492f0adbc6943a_87.png)

Okay， now fixed that。

![](img/d2b281400e0d90c00f492f0adbc6943a_89.png)

Now I' lets make the game full screen and that's going to run pretty badly， I think。

Let's go back to our optimized mode。

![](img/d2b281400e0d90c00f492f0adbc6943a_91.png)

Just we can feel a little bit better about ourselves。



![](img/d2b281400e0d90c00f492f0adbc6943a_93.png)

Okay。So we were running like at one， maybe two milliseconds per frame， which is pretty cool。

And we don't need to run faster than that。But we do need to run faster than。



![](img/d2b281400e0d90c00f492f0adbc6943a_95.png)

Well， well， yeah， let's make a full screen so we can have a proper benchmark。And on the full screen。

 I'm just going to copy that from the other game because that's not very much interesting。

And the other game used like Raymond Chs， how I switch a window between a normal and full screen。啊。

Tutial or a reference guide I suppose。So， no need to like。I need to worry too much about that。系。

And the basic idea。Is that we change the window styles and set its position。And so all it flags。

And we say we do we have window flags。Yeah。So if we go back to the。

To the the non Fo to the read mode。I do have to。 I'm going to set like the flags。

To what they are now， so window。Flas。So never I create a window。These two flags， so。The flags。Okay。

And a window position。Yeah I got see the position。Which is a wreck， I suppose。No。What do you want？

We go placement， okay？一器。Cyntax error。Does it not know it a window？哦都可。です。Okay。

Now should we just go let see and we are。Let's make a。Toargo， we have like F one。To。

To make that full screen， let's make a F 11。ToToggle。To toggle the full screen mode。

So we're gonna do。Hello。Targggo full screen。And I can test that， let's see。

You can make the game close screen。To a few arguments， what whats it take？The window。

I don't know if we have the window here。

![](img/d2b281400e0d90c00f492f0adbc6943a_97.png)

第る。や。Let's see you can get the window where comfortable。And we can't and as you guys can see。

 our frame rate drops dramatically， well， we can't see that， but right now it's 66。



![](img/d2b281400e0d90c00f492f0adbc6943a_99.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_100.png)

Milliseconds per frame。But if you go to the game。

![](img/d2b281400e0d90c00f492f0adbc6943a_102.png)

It's raw， I of bad。It's 12 per frame。So， I'm surprised。But， it plays horribly。Which。

 I'm not sure why。🎼At least， the collision worked。Nice。So if at some points。Yeah， see。

 So when we drop frames not， not drop frame， let's say。



![](img/d2b281400e0d90c00f492f0adbc6943a_104.png)

Id say when I go， when I go to like。Frame rates lower than acceptable， which is like 60 probably。



![](img/d2b281400e0d90c00f492f0adbc6943a_106.png)

Our position goes crazy and we have to review that。But yeah， we are going to re that Sweden。

Let you do things。🎼But okay， so we've got full screen working and maybe going to make the full screen the default for。

啊。For non development builds。一次。So we create a window。Let's see if。Not development。That's toggle。

The full screen。So it shouldn't change anything。But if I make the non development gu。



![](img/d2b281400e0d90c00f492f0adbc6943a_108.png)

It should be filteraltering。And it is。See how he does in。Yeah， it starts， starts off with a。



![](img/d2b281400e0d90c00f492f0adbc6943a_110.png)

White square。That's kind of bad。 So maybe what I'm going to do。

 that's kind of a a little bit of a hack。But I'm going to set。going to。



![](img/d2b281400e0d90c00f492f0adbc6943a_112.png)

Copipy the memory should be black。Yeah， so we get a black screen， I don't know it's still。



![](img/d2b281400e0d90c00f492f0adbc6943a_114.png)

Still not nice， but so let's not do that。 Let's just。



![](img/d2b281400e0d90c00f492f0adbc6943a_116.png)

Comment on the engine。The engine polish bass。Let see。Full screen。Predary。Okay， hi I'm George。

 got from Greece， I try may go and have to return to say good luck and， thanks man。Thanks。

 cool to see people from all over the world watching the stream。

 I hope you are learning a couple things。

![](img/d2b281400e0d90c00f492f0adbc6943a_118.png)

Thanks， man， very nice have you to say， oh， we can watch the whole thing on YouTube later on。

Which is Utah Com Dan today， Dan。You can watch the whole series and watch the recordings from the very first line of code all the way to where we are now and hopefully to the game's launch。



![](img/d2b281400e0d90c00f492f0adbc6943a_120.png)

And then on H Io， its dj。h。o can also download the game in the source code for free if you want to play around with that and maybe learn a little bit more。



![](img/d2b281400e0d90c00f492f0adbc6943a_122.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_123.png)

Yeah， I forgot to say that in the beginning of today's stream。



![](img/d2b281400e0d90c00f492f0adbc6943a_125.png)

Okay， so we did the full screen and now we have like a benchmark for our speed。



![](img/d2b281400e0d90c00f492f0adbc6943a_127.png)

Let's go back to the。

![](img/d2b281400e0d90c00f492f0adbc6943a_129.png)

So the development build。And so this is the optimized build and we are running。



![](img/d2b281400e0d90c00f492f0adbc6943a_131.png)

🎼As full screen。At 65 meiseconds per frame， which is really， really bad， so we are going to optimize。



![](img/d2b281400e0d90c00f492f0adbc6943a_133.png)

But in order to properly optimize， and that's like the first thing when you optimize。

 you should actually know what your code is actually doing。

How long is it taken to do with the things that you wanted to do？

So then you can make the decision like what to optimize。

And how should we like the optimization target？Because if you just start doing like random stuff。

 you're going to waste a lot of time and you're going to spend lot a long time optimizing something that has not actually caused the problem。

We do have a pretty strong idea of the causal problem。Based on the experience we did last time。

 which。Which is draw transparent road they react， so if you take those guys out， let's see。



![](img/d2b281400e0d90c00f492f0adbc6943a_135.png)

We go to 14 frames per milliseconds per frame。

![](img/d2b281400e0d90c00f492f0adbc6943a_137.png)

Wehi're just。Pretty acceptable， it's not great。

![](img/d2b281400e0d90c00f492f0adbc6943a_139.png)

But just as another experiment， I'm also going to remove。



![](img/d2b281400e0d90c00f492f0adbc6943a_141.png)

The logo。Let's see how long does that take？

![](img/d2b281400e0d90c00f492f0adbc6943a_143.png)

Yeah there we go all the way to five。And this is perfect。F should be a nice target。

 I mean in our current conditions。But we should actually aim for like a 16 frames per second。



![](img/d2b281400e0d90c00f492f0adbc6943a_145.png)

Because this heart Kate。Just to understand what we are up against。You are running。Is it correct。

 I think that's correct。Well， let me just check。

![](img/d2b281400e0d90c00f492f0adbc6943a_147.png)

But the 4K resolution is because I don't know if I know that by heart， well'll close that exam 4K。



![](img/d2b281400e0d90c00f492f0adbc6943a_149.png)

Yes。See，4K resolution is 3。3，8，40。21，60 should be840 times。So in that case。

 in our full screen mode right right now， we are doing。The basel film， at least。8 million times。

 at least， I say at least。

![](img/d2b281400e0d90c00f492f0adbc6943a_151.png)

Because we do have some overdraw，Like we draw the background， then all of this guy。

 were drawing on top of the background again。So these guys we draw like twice。

And these guys also and these guys， but no， they're pretty also。The biggest problem。🎼Is the。

You feel right。So。

![](img/d2b281400e0d90c00f492f0adbc6943a_153.png)

Yeah。That's nice to know， so if we should do at least。



![](img/d2b281400e0d90c00f492f0adbc6943a_155.png)

Looking around like 10 million times。

![](img/d2b281400e0d90c00f492f0adbc6943a_157.png)

We should should have a pretty fast culture the that's what we are up against， we are up against。

10 million things。P friend。And that's just to note that games must be really fast because there are a lot of pixels in the screen。

 but computers are fast so we can afford to do all sorts of crazy stuff 10 million times per frame。

 that's kind of bit of a same thing to say So let's understand our code a little bit better。

 So let's build a profiler。 So the idea for that profiler is I want to know what's taking。😊。



![](img/d2b281400e0d90c00f492f0adbc6943a_159.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_160.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_161.png)

That that 11。Iid for FWC now？So I'm going to create a profiler dot C file。Right。

 and then we can start。Being around。Ands do like this。Your filer。要起。ok。

I created that on the wrong for。We really leave that later on。So， break out。Hold。Your fire dance。

 okay。Okay， what do we want the profile to do， You want the profiler。



![](img/d2b281400e0d90c00f492f0adbc6943a_163.png)

Let me show you guys what I wanted to do。I want something like this。

Let's say we have the total milliseconds per frame right here。And maybe you could do something like。

Input。How long it takes？Like the game， how long it takes？And the。And let's say the flip。

Because the rendering is being done by the game， so we can't separate these two like openGL。

And how many takes per flip， and then we can do like。The audio。And the audio sleep。

So these are the main ones。But then we also want to do like a smaller thing on the game。

Like how much we take？On each rendering thing， so draw our rack it' do like。Draw。

 how long it takes on the draw， the draw bitmap。The drew our road tailed racked。Yeah。

 those are the big ones， right？

![](img/d2b281400e0d90c00f492f0adbc6943a_165.png)

Let's see what else we have。In the renderer。Can draw react and fix those？Correct。Direct。

Draw arena racks， okay。

![](img/d2b281400e0d90c00f492f0adbc6943a_167.png)

Clear arena screen， so we could probably do light。Arena。

Which certainly two of them combined or we have drawn numbers as well。And we have drop text。As well。

Yeah， and then draw transparent rectangles， drop it map。Draw the subpixel one。And they draw text。

 so I'm going to do yeah。Draw sub pixel。Draw text， which's going to include number。



![](img/d2b281400e0d90c00f492f0adbc6943a_169.png)

I think that's。Oh， the Dt tax just calls。Theyre direct， so that's not going to be very。Yeah。

 so does the draw sub pixel so I can't remove this guy。And this guy。Direct。

Because we should only do like。Certainly do guide that create this， so the clear screen。

 I don't think we use the clear screen。What we do on the menu。So。

The dry arena going to include the the。And include the。The clear screen。 So draw in pixels。

 draw in pixels transparent。Those are the dry so dry transparent rotateated one and drop maps。

 I suppose。

![](img/d2b281400e0d90c00f492f0adbc6943a_171.png)

Hello to PG。 Okay， yeah， so this is about correct。So the draw Act。

 drop the map rotate it in the arena， that's what we want to do。So let's start doing our professor。

 so let's do it in them。

![](img/d2b281400e0d90c00f492f0adbc6943a_173.png)

I still like type depth。Fly。Profeeller。M。Your profiling。I do input。That's your game。ice you。

So things are the ones we're going to do first， then we can do the audio we're going do the draw ones。

 okay？So what we want to do。Here。We want to like begin and end the profiling for these guys。

So whenever we start。Like here， the input， if you like begin。Pro filing。You we give proing input。

And then。1。We am。Profin。For final inputs and enemy start， we begin the game。And at this point。

We end the game。And。Here we end of it。Okay。😊，But since this is going to have。

Since this is going to appear in some performance sensitive thing， I'm going to do its own。

It's on a if depth， like you have development。And I'm going to do its own thing。啊。哎。

Because this is probably going to take a while。 So don to try to inline。

You can pro going take a profining item。I was a bad name。じじる。For filing， okay。

 now in the build dot bat， we're going to do our pro filing。出来。Okay。Hey， Clne， how are you doing。

 man， I'm doing great？Today we're going to do some optimizations。

 so we're going to build the profiler for the game so we can know。😊。

What time you're spending each of the most important things， so this is like how we want it to load。

Like in the corner of the screen， we wanted to have information on how long take on a on the game and the flip。

On the audio， on the lead part of the audio， and for each draw。And then maybe you can do like。

You can do a like here。No。Rangering。Game， which is like the game minus these guys。

So hopefully by doing this， we'll be able to have a nice understanding of the project。

 so we will go do the optimization， the proper one， which we may do today， I think。We are going to。

We're going to do that on what's actually taking the time， right？

Doing good just woke up Oh nice to your prize better Yeah F is awesome and it's a nice thing to write as well。

 it's pretty fun。😊，So can we do the profile income。So we're going to do a str。

Let's do like profiling data。And let's say it has like， let's say。A headcount。And then we have。Time。

And then here we can do like againin profiler。Or like， yeah。Yeah， at very end。We can go and go filer。

 so we're going to draw with one frame of the label， that's okay I think。So whenever we。

We I had a lot of fun writing mind。 Yeah， it's pretty cool。

 I did a simple one on the the other pong game that I lets on the child。



![](img/d2b281400e0d90c00f492f0adbc6943a_175.png)

Let me sure for people who haven't seen it。Sa for this game， I did a pretty simple profiler。

 That was pretty cool。😊。

![](img/d2b281400e0d90c00f492f0adbc6943a_177.png)

I think I was going to be a pretty more。I also wrote a memory tracer to trace all the allocation thoset us yeah that's awesome I usually do like allocation is very。

😊，Cautsciously。So I don't like。Do a lot of malls and stuff。

 usually but I haven't done like a huge game on C yet， the huge game I did。

 I used an engine so they have their own tools for that。



![](img/d2b281400e0d90c00f492f0adbc6943a_179.png)

So I haven't had to write the memory tracer， but that's going to be a pretty interesting challenge as well。

 I think。The Fr， all we're going to do is like to zero our prop data。

 so we're going to have an array of profil。你咧。And I'm going to do we have zero range？Profiling。

And in the。Oh， the thing is。嗯。😊，We actually should like render the profiler。

You should render that before the flip pens because。Yeah。

 so the numbers are going to be a little bit weird， but I think that'll be okay。

We in terms of like some of them are going to be updated， some of them won't。

So we're probably going to need mic。Ol the data。嗯。Yeah， so let's call that back profiling data。

And I'm going to do the writing writing data。So whenever we begin。The profiler， we are going to0。

Dere finding。The writing for data。Okay， yeah。Okay， so we're going to zero the profiling data。

And we're going to actually， before we do that， we're going to copy the whole thing。To the old one。

Yeah， doesn it finished perfect。Right， it was mainly for finding edge memory leak since basically all my locations are one time locations as well it's nice to print this tech trace as well it's kind of fun to write be able to nice to be able to write Yeah I mean you probably learned a lot doing that right and that's always valuable。

😊，And if it was fun right， that's also valuable， but the learning process for writing。

Things to understanding more of the code。That also， that always pays off， I mean， that's really cool。

So for every guy I'm going to copy from the。When I set the old。Oh cross。Good拜。Microfil data。

I to the writing。We're fighting data so save what we wrote last frame and then we to write things again。

Okay， that's the begin。So I guess I don't need the names。Yeah。

Totally I have built ins in normal my programs from that， it kind of crash Yeah。

 like if you practice it that's really cool and the thing is just like when I wrote like that small profile for the other game。

😊，My understanding kind of incremental a lot。 So in this game。

 I want to do like not only a profile as well， because I learned how to do that pretty easily in terms of like a simple one。

 right， simpleim one。 But also， I'm going to， I'm going to expand on that。

 So this one gonna is gonna have a lot more info。😊，Then the other ones。

 because we want to be able to optimize that a little bit more thoroughly。Begin Pror。Yeah。😊。

You should also define these。And the render one。But I thought。

I thought I had turned on but oh turned on the provided。给。So when we render the profiler。

All I'm going to do now is going to run through like。Kind of thinking how I want to do that because。

I probably want to like drop text as well。That's see where we are printing our frames per second。

 is it on the game let's see？Yeah， we are printing that here。

 so we want to bring somewhere that's do like P。Eals this guy。But I'll ask you a little bit。

It like 40 maybe。 So that's where stocks are going to draw。Text。

I'm going to draw what was the first one， the input。Input will be。That let's do P。Let's do2， maybe。

And then I's do red。Well。Next's do like。A light kind of。Okay。😊。



![](img/d2b281400e0d90c00f492f0adbc6943a_181.png)

Now let's see if you get something。🎼We don't。

![](img/d2b281400e0d90c00f492f0adbc6943a_183.png)

嗯。

![](img/d2b281400e0d90c00f492f0adbc6943a_185.png)

而行。😊。

![](img/d2b281400e0d90c00f492f0adbc6943a_187.png)

Is this code even running？

![](img/d2b281400e0d90c00f492f0adbc6943a_189.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_190.png)

啊。What I think I'm setting to of finding。Our profound。Thats super prefer。



![](img/d2b281400e0d90c00f492f0adbc6943a_192.png)

Now I should run。No， it's not run， okay。Dude， what's going on？是。😊，Let's see。



![](img/d2b281400e0d90c00f492f0adbc6943a_194.png)

If profiler。In course one。Oh， now we're doing。Youre 32 pointer Yeah because we take a lot of colorsers。

 so we're going to do like color。Because this。This one I'm going to take up。Pointer to the color。

 and one color。And I remember that there's an actual， another argument， let's say。T。

 but I don't remember which charge is that align。Go to do text。A line right。

 that's due to right just for the。So it's this guy， the P， the size， the color one， oh。

 there's another zero lyrics， also。First color。Yeah， maybe we should have like two draw taxes。嗯。Yes。

Oh， and profiling you should have the。And profiling end。这反理。Enrnder profiler。Okay。



![](img/d2b281400e0d90c00f492f0adbc6943a_196.png)

To a few arguments， would I take？Okay， now it should work。And a crash at was no pointer。

You were trying to write。N P， oh， because we should be all caps。



![](img/d2b281400e0d90c00f492f0adbc6943a_198.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_199.png)

We only have uppers， well， we could probably。Do that。



![](img/d2b281400e0d90c00f492f0adbc6943a_201.png)

嗯ん。What a giant font。

![](img/d2b281400e0d90c00f492f0adbc6943a_203.png)

But that's what we wanted to see。

![](img/d2b281400e0d90c00f492f0adbc6943a_205.png)

Well呀。But the tiny font。

![](img/d2b281400e0d90c00f492f0adbc6943a_207.png)

Maybe I didn't do it。Okay。

![](img/d2b281400e0d90c00f492f0adbc6943a_209.png)

It's kind of taking some time to compile， okay， so this。🎼This is okay， I suppose。



![](img/d2b281400e0d90c00f492f0adbc6943a_211.png)

So maybe it's a little too di still。

![](img/d2b281400e0d90c00f492f0adbc6943a_213.png)

If you can go a little bit。

![](img/d2b281400e0d90c00f492f0adbc6943a_215.png)

Oh， now it's pretty much unbeatable。

![](img/d2b281400e0d90c00f492f0adbc6943a_217.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_218.png)

Okay。So I'm going to like draw。Draft 32。And let's do the。Back。Pro finding data。

Can we do the profiling。Input。Dot timer。Okay。😊，Then let's draw。And then we' under the P。

 which you going to offset size。 let's do the same size。And the color iss just the color。

 And P is P is going be P dot y。Minus equals。Well。B到 X。What equals like2。double to float。



![](img/d2b281400e0d90c00f492f0adbc6943a_220.png)

K。

![](img/d2b281400e0d90c00f492f0adbc6943a_222.png)

Yeah， it worked， but then we should probably offset everyone in life。Should be0， just by the way。

I'm not sure what numbers that are supposed to be。

![](img/d2b281400e0d90c00f492f0adbc6943a_224.png)

Let can put a break point。

![](img/d2b281400e0d90c00f492f0adbc6943a_226.png)

Well， we are supposed to。Oh， yeah。 you should also。Turn off the optimize render。



![](img/d2b281400e0d90c00f492f0adbc6943a_228.png)

Dptize a code。And now it's render pror not profiling。O。Now， the timer is zero。The P。

Everything looks reasonable。Maybe this guy is too small for the。



![](img/d2b281400e0d90c00f492f0adbc6943a_230.png)

For the text， which is weird because we have like two different。Scals。



![](img/d2b281400e0d90c00f492f0adbc6943a_232.png)

One for text and one for numbers。So that's not good。



![](img/d2b281400e0d90c00f492f0adbc6943a_234.png)

Yeah， see。

![](img/d2b281400e0d90c00f492f0adbc6943a_236.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_237.png)

🎼Okay， but they。Why should also be offset items？I think I'm just going to add B2。Goon to add6。And。

Bye。

![](img/d2b281400e0d90c00f492f0adbc6943a_239.png)

爱然乐亲。

![](img/d2b281400e0d90c00f492f0adbc6943a_241.png)

Yeah，85 was way too much， but the 6 did look correct。



![](img/d2b281400e0d90c00f492f0adbc6943a_243.png)

And。Okay。

![](img/d2b281400e0d90c00f492f0adbc6943a_245.png)

Okay， perfect， that's what we want now we want that for every guy。

And I think we're going to just do a macro light。是啊。Oh。あ下。And take a name。And the。

How many hours develop until now we have？Something like 40 hours。Or哎 yeah。No， actually。

 I think it's like 48 hours， Yeah， 48 hours。 I remember I saw that this morning， 48 hours。

 you can watch the whole thing on YouTube。

![](img/d2b281400e0d90c00f492f0adbc6943a_247.png)

From the very first line of code， and we were doing everything ourselves。



![](img/d2b281400e0d90c00f492f0adbc6943a_249.png)

And。Yeah， hopefully you're going to have a pretty cooler father today。



![](img/d2b281400e0d90c00f492f0adbc6943a_251.png)

And that we can I use to make our game run better。Okay， nice。 So I'm gonna draw。Pro finding guy。行。

Put。Pretty good for a week of work。 Yeah， dude， that's awesome a week like of if I was。

 if I were doing this like full time would be pretty much a week。

 even a little bit less because I don't know what we can indeed game developers like 60 hours。

 I suppose。😊，Something like that a good week and we've done a lot and I could have copied a lot of the code like I've already wrote you in the per 540 game they could have copied that。

 but I want to write on stream so you guys can see the whole learning process and my mistakes as well。

😊，So that's like a week of word from scratch， I think pretty good too。Pro finally input。给。😊。

And this is going to be the index。And this is going to be all the P。And this is going to be the name。

你。Well。😮，What do you mean。I the I ident。Maybe you should do like。Wow， this is wrong。Yeah。

 it's supposed to be something like this， right？I don't remember。I suppose， I suppose。But that's it。

一次。😊，We got a lot of problems， so。Oh， okay， no this。So let's do with the other ones。不就。

The game and the flipped。So。Let's do four letters input game。Game。



![](img/d2b281400e0d90c00f492f0adbc6943a_253.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_254.png)

Let's just add that。埋边开始。

![](img/d2b281400e0d90c00f492f0adbc6943a_256.png)

Now let's do three。Okay， nice， now let's fill those numbers， shall we begin profilr？I'm gonna do。

Well， I surely like set。嗯。Like a begin timer。Yeah。So I'm going to set。The writing profiler data。

Right writing pror data。Dods begin timer。Yeah。It's going to be。

I'm just going to cheat and call Windows Fun from here， I suppose。Or maybe yeah， no。

 I'm not going to do that。 I'm going to。Like we have the time。Get seconds elaed。Let's do， like。

 in line。You 64。OS， get。Current。Let's get。Reformance calendar。And that's。Tur。Trying to counter down。

Then we're going to do the OS get per。Connor， and we have to forward the clarity。I found common。

But this is only freeR。I you't remember what we call it that filer。不海的这。Okay， begin timer。

Do not doubt。At the item position。ok。😊，So we get the timer。That's the only thing gonna need do。

 When we finish， let's。Like no timer。Or we could probably call the other one。W was the other one。

32 gets seconds。Lasted。Maybe you can take a U 64。Call that OS gets deed。你安。And。So you're going do。

TheTimer。And it should also increase。Count。ok。😊，And the timer。诶。Yeah， time should be O S。

Second the last。It second to left。And they're going to pass。Our begin time。

And we should in we multiply that by a thousand because we're going to do everything in milliseconds。

Okay， so that。That's all I think， so Do Quadpart。You'll need to do that now for the last counter。

And this should be a。 They take less。Conor do plot part。And then we do OS second to lap。

 that's counterner do。ok。I don't know。 Maybe we are good to go。



![](img/d2b281400e0d90c00f492f0adbc6943a_258.png)

Let's see what we have。This looks perfect。This looks really， really perfect。🎼So the game。If I pause。

🎼Well。

![](img/d2b281400e0d90c00f492f0adbc6943a_260.png)

F power should。 I should also not。Ranger the profile， so if。If32 paused。And yeah。

 the profile is considered right now。Maybe we should do like， I'm not sure。

Maybe probably should not because Sid。So we sure not paused。



![](img/d2b281400e0d90c00f492f0adbc6943a_262.png)

Re引あや。

![](img/d2b281400e0d90c00f492f0adbc6943a_264.png)

Yeah but that was pretty correct， so if I pause let's see our frame takes 23， can you guys read that？



![](img/d2b281400e0d90c00f492f0adbc6943a_266.png)

I think you can make it a bit too。 Yeah， let's change the color of the。This guy？😊。

Let's put down the profiler suppose。On the floor。Let's draw this guy， and that's make him red。

So this is the first and the DT is not realistic。Just like。



![](img/d2b281400e0d90c00f492f0adbc6943a_268.png)

Okay。🎼Yeah， red is too strong。So our frame took 22。7 milliseconds。The input took like 0。

07 milliseconds， the game took like a huge part of it， which is what we expected and the flip took 0。

7 milliseconds。Which？🎼We had to take that hit because of it。

Wos does not optimize for making me anymore， like for the past 20 years。Okay。

So that's perfect now we should be able to， let's let's try doing the audio one。



![](img/d2b281400e0d90c00f492f0adbc6943a_270.png)

Since we have。Like different threats for stuff。 we should really， we shouldn't really have。Big well。

Not sure what's going to happen let's just do like audio。

Let's just see how long we're taking to do the audio。Since the audience once thread。

 we probably have to do like。Things more carefully but。I don't know it's just just to have some idea。

 so as' do like。Update audio， yeah。So we're going to begin the profile for the audio。And then here。

 before we sleep。I'm going to end。F。

![](img/d2b281400e0d90c00f492f0adbc6943a_272.png)

爱奇。😊，He， it does work。

![](img/d2b281400e0d90c00f492f0adbc6943a_274.png)

Interestingly。哦。He does。I would say each of is pretty much the same one as the F。😊。



![](img/d2b281400e0d90c00f492f0adbc6943a_276.png)

Okay， so he does work， yeah。So it took like 0。3 milliseconds to baby audio。This is actually， yeah。

 this is the whole audio， it's not just our game， but it's also the。Library part， that's perfect。

全机励五啊。

![](img/d2b281400e0d90c00f492f0adbc6943a_278.png)

A10 of a millisecond， if we include the sleep。When don't do like audio just sleep？

Just so we know how long it's taking for it。audio thing。Yeah。

 but that's we're not going to optimize the audio that runs pretty well。



![](img/d2b281400e0d90c00f492f0adbc6943a_280.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_281.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_282.png)

🎼Yeah， so we sleep for a long time。

![](img/d2b281400e0d90c00f492f0adbc6943a_284.png)

It's okay， I suppose， so the audio slip。嗯。Let me do these guys。In seconds。

 just so I can see how much was for the audio mark。



![](img/d2b281400e0d90c00f492f0adbc6943a_286.png)

It's sleeping for a long time。

![](img/d2b281400e0d90c00f492f0adbc6943a_288.png)

Oh， because we were in several。Yeah。😊，H not sure， though。Let me， also draw。Draw int。

I can draw the hit count。And let's do like a little bit more to the side。78。是吧。Number。Your number。

好 let's see。We take。The number。一P。The size， the color and the number of living。



![](img/d2b281400e0d90c00f492f0adbc6943a_290.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_291.png)

So all of them are one ever doing like the audio a few times。Per frame。The number still weirded。

 I think。

![](img/d2b281400e0d90c00f492f0adbc6943a_293.png)

Ares living that much， I don't think we are。And maybe we should divide。This guy by the head count。



![](img/d2b281400e0d90c00f492f0adbc6943a_295.png)

Just you get like。

![](img/d2b281400e0d90c00f492f0adbc6943a_297.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_298.png)

What numberumber do you try to write？Mine is a huge number or that I put that on the no。



![](img/d2b281400e0d90c00f492f0adbc6943a_300.png)

TheTimer divided by the hit count。Maybe it's  zero。That's do like us safe。Dfin。So yeah。

 I should get like one。So let's do that。In line。Three two save， divide one， you're going to take A。

 you're going to take B。If。B， well， yeah， be。0。第。This one。turnA10。Okay， now let's see if you crash。

So this is pretty cool。It's pretty nice。We should probably tell that， I don't know。嗯。I hit。

Then right here we do like。Theal the grass choose to make。The hit be just。

If we don't want to worry about that， that's。Hit your definition。Yeah。



![](img/d2b281400e0d90c00f492f0adbc6943a_302.png)

Okay， so we're taking it the full time Yeah， let's just take a quick look。

 I don't want to mess with the audio now。

![](img/d2b281400e0d90c00f492f0adbc6943a_304.png)

So。Yeah， I think this is wrong。But I don't know why we didn't。The left times。

 how much times in seconds repairs， No， that's correct。And we're sleeping that much。



![](img/d2b281400e0d90c00f492f0adbc6943a_306.png)

🎼LetSee how much we， 15 meiseconds。

![](img/d2b281400e0d90c00f492f0adbc6943a_308.png)

Well I know。Now I'm going to worry about the other。Okay。

 so we got the first part of our profiler working。

![](img/d2b281400e0d90c00f492f0adbc6943a_310.png)

🎼Which is like。The base gate out。🎼Now， what I want to do is to sub divide the game into the rendering things。

 so pretty much going to be the same thing so that。



![](img/d2b281400e0d90c00f492f0adbc6943a_312.png)

I'm going to do like draw rack。When do draw which which one was it。Draw bitmap。When就抓。Rotate it。

Which is also transparent。I going to draw第。Let's call that back。Okay。

Now all I're going to do is in the software rendering， let's add these guys to like。To our draw。

 So draw。Rect in pixels transparent。Let's see who's calling that you're direct。O是吧。

Calculates access to world， access to world。Dawx， so begin。Pro finallying。Profiling。Right right。企。😊。

Then when we finish， we're going to。And for time。Unfined。I don't like that。ButWell， we can do。

It's C and C++ it got four the clearing stuff。For some reason。We don't have the items。哦。😮，you like。

Maybe I'm going to do the other way around。I'm just going to place。

We'll throw ar before the software rendering。And then we're going to do the drop text， drive 32。

 things like that go to。Text。And forward declare those guys in here， so。Drug taxes do the drive。32。

I going to draw number。K and text。A line， right， it's。好。Yeah， it's just changing。Okay。

 you happy now compiler。Let's see how long we're taking on the direct。Or not drawing that。

Let's also change the color。For the audio guide to be a little bit different。

Maybe a little bit lighter。And these guys that make like a darker blue。And， let's do like。

This is the right。

![](img/d2b281400e0d90c00f492f0adbc6943a_314.png)

Let's see。😊。

![](img/d2b281400e0d90c00f492f0adbc6943a_316.png)

And let's just add a few more of those spas。

![](img/d2b281400e0d90c00f492f0adbc6943a_318.png)

Just a smart thing， let's see。

![](img/d2b281400e0d90c00f492f0adbc6943a_320.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_321.png)

我要。Say problem head before， right？

![](img/d2b281400e0d90c00f492f0adbc6943a_323.png)

是啊。

![](img/d2b281400e0d90c00f492f0adbc6943a_325.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_326.png)

Because we were doing like a lot of times。So。Let's do like the other way around。

 let's do the draw number first。You go to 6， then this guy8。Because it's marked predictable。

Then we can probably let's do them both， let's do like the。Safe divide by the hit。

And let's just do the raw one。ok。And I do like。Just like direct。



![](img/d2b281400e0d90c00f492f0adbc6943a_328.png)

Well， it's going to take some time too。

![](img/d2b281400e0d90c00f492f0adbc6943a_330.png)

Okay， this is better， but now this is pretty confusing。Where's， where's the P。

 Lets started at like 70。 And then we draw first one。 Let's move like。12 this guy。You move like。Well。

 no these are。12。16。Then I do。8天。

![](img/d2b281400e0d90c00f492f0adbc6943a_332.png)

Just to kind of do。

![](img/d2b281400e0d90c00f492f0adbc6943a_334.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_335.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_336.png)

Okay。Okay， we are getting somewhere six。Then let's do 12。



![](img/d2b281400e0d90c00f492f0adbc6943a_338.png)

24。

![](img/d2b281400e0d90c00f492f0adbc6943a_340.png)

Almost。This guy's perfect。These guys should be a little more。So， let's do。That smoking。

Would't managed to use the H5 E。

![](img/d2b281400e0d90c00f492f0adbc6943a_342.png)

Probably。But seems it's like just two functions。A files are really pain the but man。

 I really don't like them， so if I can avoid them I would much rather try to avoid them。



![](img/d2b281400e0d90c00f492f0adbc6943a_344.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_345.png)

If I can't， then I can't right， but this case just two functions I'm going to do it H file。I know。

I really don't like them because it makes everything you had you were like twice。I mean。

 not everything but every function， every function dec and stuff。😊，Let's do the draw guide。



![](img/d2b281400e0d90c00f492f0adbc6943a_347.png)

So I really don't like it。Okay， this is better。🎼So。Let's see， we are calling 2000 Res。

 that makes sense because we're drawing a lot of small text。And that's taking 0。7 milliseconds。

 which is like a very small number per rec。

![](img/d2b281400e0d90c00f492f0adbc6943a_349.png)

Which is。Nice。I've just seen the game。It's kind of hard to see the audio， but we don't really care。嗯。

🎼The input there we got five。202 per frame and this is different。Yeah。

 because this is something everything， okay？5。2 per frame and we have like 500 racks。Yeah。

 kind of makes sense， 500。6ix00， I suppose we're taking 0。6 minutes， so our draw rack is perfect。

 I suppose， compared to like our rendering time。Let's now。Do the other ones。 like to do。D draw。

That's it， that's like to draw。This map。And that's do the door rotate it。结数。We have like both。あ。

So draw I yeah。the clear screen， I'm going to count that。As the background。Ground。😮，For funding drug。

Okay。😊，And here we're going to do the end background， but we're also going to do this guy。爱始。

Calculate access world， draw act。Draw arena rack。That's background。Clear arena cream。

 that's also background。Draw number。Not going to consider that because all that that does is called direct。

 so we are already considering that。Same thing for drive3 two， yeah。

 this one is the elephant in the room， I think。So we draw the rotate wreck。Yeah。Then we finish。And。

And。bit maps here we draw bit maps。I think that was a pretty cool path we did。It's not。

 it's not like。Huge or perfect or cant like see all sorts of crazy stuff。

 but I think that's perfect for what we need。DX， so pixel story all it does is calls the draw X。

B so transparent。I don't think we are accounting that。Rrrect and big s。Yeah。

 I don't know where I'm gonna to add these guys。Let me just ignore that for now。

 I and put another category， so we're going to draw。Got subre， which is for a sub。Fixel， correct。

And I're going to do。Refining。Fly dress so。Oh， but it also calls a draw because yeah。

 the transparent ones are just the very border so'。Yeah， just like one row of pieces。The text。K。

Get alignment。Now we are only tested in the draw part。I don't think we care。

I think we did everything。So correct。Dit map。Rotated。And background。Let's see， guys。

 Let's see in the menu。

![](img/d2b281400e0d90c00f492f0adbc6943a_351.png)

See， this is perfect。Yeah。🎼This is perfect for fighting exhaust we are drawing like。😊，2300 wrecks。

 but it hardly to take any time at all。The total game time is 21 seconds， yeah。

 we should also add the rendering time。

![](img/d2b281400e0d90c00f492f0adbc6943a_353.png)

And then， let's do， like。嗯。I'm going to draw。I don't know。G。Minus。B。

I think we again since we are right aligned。I think we can do that。Again。He， okay。

 I change the color once again。Make that a little bit talker。To2。呃，财务。Okay， so the hit。

I need to do that。Let's just do this。 So it's going to be。The providing game。Timer。

So its going be timer minus equals。Everyone's time， so we're going to do every braining that。

What's I do。Draw background。Big man。Rotated interact。我天。we had show the timer and then don'll need。对。

不须到手。

![](img/d2b281400e0d90c00f492f0adbc6943a_355.png)

Yeah， so this is what we expect， right？Pretty much all our time spend raining。Perfect。🎼Now。

This is the elephant in the room right Binap is also a problem。

But it's not that much so we're calling that twice and we're taking like seven milliseconds per that's a lot。

 a lot。These are for these two guys here。Our bi is just the logo four milliseconds， it's also a lot。

R X pretty。Okay， background calling that once。And we're doing that。Like 1。9 milliseconds。It's also。

Are we optimize， I don't think we are optimizing。They're not。Well。😮，Supp suppose that's good news。

So we are taking 11 milliseconds now， 0。07 on the input。I think that's a bit too much， maybe。啊。

Comparing to what we have， this is nothing right。Our game takes 10 milliseconds。🎼Okay， and the flip。

 00。6。Theirect very short period of time， 0。1， the bitmap takes one a second。

 okay now that's more reasonable。Okay， our background takes 0。14 that's perfect， I think。

 because it's pretty much just straight off trying。Yeah， this is nice。I rotated statistics for。

 so if you can you can have that， we go from 11。🎼To like 5。Meiseconds。If you have that， oh。

 if we wanted to do like a fulloc。Which we may want to do。

 we can do it like really quicker than that。Let's just start small。Okay， so that's the basic thing。

Let's see the game。

![](img/d2b281400e0d90c00f492f0adbc6943a_357.png)

Show me the game。I don't know if you guys can read that， it's kind of a。

 the colors were really bad let me just zoom in so you guys can see。I don't know where Zoom I went。

 I was here。So yeah， the game's taking 1。5。From which 0。18 is the game， so this is more reasonable。

 0。6。

![](img/d2b281400e0d90c00f492f0adbc6943a_359.png)

Is openGL， but I mean 1。5 we don't want to change any of that so our rotate， yeah。

 we only do like these particles as rotator rectangles。



![](img/d2b281400e0d90c00f492f0adbc6943a_361.png)

And they're taking like a very short amount of time because the problem was。

We're doing a lot of pixels on the main， so if we optimize that we're to it so we've got 71 rotate racks。

 two backgrounds， takes a very short amount of time。🎼That's perfect I mean。

 this is pretty cool our rot rectangles can get out of hand。

 let's see if I can get like a crazy yeah。😊，We seeing the other level this type right here。

If I can get like the comment。Then呢。We got a lot more particles。

Yeah I'm kind of trying to pay attention with multiple things， so I'm just failing out to find。哦。

阿神阿神。Oh well， that's an awesome afterward。Why did we have any comments， ma'am， Let's see。

 I want to see some comments。Dude， that's really bad not。原来你居还在着。反。来 see。

So this some more chaotic scenario， games taking five milliseconds， four of which is the rotator act。

No。Yeah， because we're on that 200 times。So if we managed to optimize that。

We are going to be good to go the bitmap we have like one， two， three， four， five bitmaps。

Stakking just 0。01 milliseconds per call for this perfect so the big thing you want to play around with is the rotate rec。

So that's what we want to optimize。In fact， before we we try to optimize that。

I'm going to try playing a little bit on full screen。🎼Well， maybe just a menu。

 that's a nice benchmark mark。Yeah。

![](img/d2b281400e0d90c00f492f0adbc6943a_363.png)

Certainly so the menu on full screen， let me show you guys。this guy。Yeah。



![](img/d2b281400e0d90c00f492f0adbc6943a_365.png)

Yeah， you can see。We're taking 0。66 milliseconds， which is like huge。 We， We want to make that 16。

 That's our goal。See our goal。For whatever you want to do is。Make the menu on full screen 4K。

 this is 4K resolution， which is we measured， it's like 8 million pixels。

We want to run that at 16 milliseconds on this PC， which is pretty good but it's not like the best and then we're doing like CPU only。

They are okay， and let's just make sure what we're doing。 Okay， so our bitmap is taking a long time。

 we can probably cut that because if we're doing like 16， we can't spend half the time on theap。

So we want to optimize these two guyss。Possibly this guy is wrong。 I don't。 I don't know this guy。

you just see。Just like one point， I'm not sure。This is the clear screen。



![](img/d2b281400e0d90c00f492f0adbc6943a_367.png)

Yeah， if we were to optimize that， okay， so let's see optimization options。

 we're going to discuss that。So we have to optimize this guy for sure。In this case。

 it takes 25 milliseconds。Huge， but it does have to calculate like millions of times。Yeah。

And the bitns probably so these two are the big guys， we could probably do this。

 so what are the tools？That we can use to optimize right， because this like。

 this is real optimization because when I release the other game。

I me show you guys in case you don't remember。If you haven't seen actually it's called Elios hunt。

 it's on the steam。 I release that for steam and PS4， I use the real engine。

 So when you're doing this kind of game where you're using an engine and somebody programmed that for you。

 you have no idea how it works anything like that when you're just scripting and you can do a lot like sort crazy particles and animation when you're doing this kind of game when you use an engine。

Casually。When going to say optimizing？You probably means you mean using less of the engine。

 so optimizing and our asset would be to make it has like fewer shaders， less polygons。

 things like that optimizing the level would be to have fewer actors or game objects on the level。

So that's the sort of optimization that we have when we use an A。But in this case。

We should do like a hard card optimization。The problem is our code， not how we use it。

 We have to run through all those pixels。 We have to。So the problem is how we're doing this well。

 maybe how we're doing this， which is what we're going to see today， but there are other tools。

 so the first thing we should do。

![](img/d2b281400e0d90c00f492f0adbc6943a_369.png)

It's like， analyze。Analyze。Understand。Prepare。These three guys。

So we have to analyze what're doing what they're doing exactly。

Prepare them for later optimizations and well I don think I can read that it's pretty badly written。

And。And I don't know what。Understand， yeah， and understand them。Right and that's the first call。

 so they have like all sorts of function calls， let's see。And the rotated banks。See what we call。

The doth product recall sub the， we're going to do this。 We're going to expand this function。

 the lub color， see if we think this can to be sped up。We're going to expand that。

To make sure that to understand the whole thing。

![](img/d2b281400e0d90c00f492f0adbc6943a_371.png)

You said instead of just being like function calls， it's going to be straight line code。

We're gonna first this guy， then this guy， and then maybe this guy。That's first step， analyze。

 understand， prepare the other step we can do is we can do wide operations on them。

So this is like one of the ways that GPUs work with like millions of pixels pretty quickly。

Is because。Our normal erar， which is 64 bits in this PC。

We usually do like one operation of the attack， so we put it like a floating point and then we multiply that on a floating point and that's one operation。

SMD， which stands for single input multiple data。A single input， like a multiply。

Can be done with multiple data， like four vectors。How it does that well instead of having a 64 bit。

Guy， we put a vector here and not in here float here， not in here。

 they have a wide factor and in this right one we can put like four floating points。4。

Floing points and GPUs have even wider ones that you can pull like 16 floating point valuess for floating point variables。

So if we do this properly， we can get up to four times speed just by doing this and we can probably optimize by just analyzing seeing that we're doing stupid things。

 not sure how much we can take out of this， probably probably a little bit， let's say at least。

Is you can do like 50%。Gams。Can we just like to 515 and then we' can do reduce the result 25%。

Because we can do like four upgrade at a time。So right off the bat， I mean， not this is hard。

 but we could do， that's a possibility we could do like 51。Divided by two， divided by four。

So you can't get this guy all the way to six。And if you do that， we're going to be six plus eight。

Plus， let's say one。Plus。Yeah， whatever， like 3。Plus one or something like that。

 we can get that back to 20 just by doing these guys。We could probably do that in the bitmax as well。

 So if do like 8。Divided by4。Divided by two， you can get that to one。

 that'll be a huge game just by doing this， there's another weapon that we have in our optimization weapons。

Which is a motor thread。And we already discussed that。

 in fact we implemented a job system in our range， so it's not that hard for us to implement our rendering in Mo rally。

Depending on the way we do， because let's say the guy has four。Cose on his CPU。

But today people have like eight and six， let's say four。But we are what。

 one goes through the audio and one and one goes through the。For the other systems。

 like we're going to do like async audio loading。So if we multithread this guy。

 we can pretty much get to two so back to 50% of the result。I mean， this is like。inus yeah。

 so we are discounting right， so getting faster recorded and you can get that down to 50%。

Another 50%。Probably more。But if you divide that on like two parts of the screen。

 I we do like this guy， this guy。That should be almost 50% because there's the borders so it's not exactly。

 but that's the basic idea this also not exactly this。But it's just a big idea。Okay， so in theory。

We should be able to let let's add like 8。32 to 51。This guy， so 60。So you want to get 60 down。Yeah。😊。

We can get 60 down two just by analyzing probably this's not like exactly。

 but we can probably get some gains there， some gains， not not two。

 probably then we can do like four and then two again。

So if we do like the full things that we can do at this point。

 this is pretty hard not saying that this is easy， we can get this guy down to three， so we add six。

We can get our game， this is like the most complex scene we have the main menu because they have a giant bitmap。

 have two big rotator rectangles if we manage to optimize。Our code to get the menu back to 10。

The target is 16。So you can get like 16， so you can get like a margin of error pretty substantially here。

😊，If you manage to optimize that up to 10。Running as 4K。So we are running at least eight。

 maybe 10 million pixels。😡，In nine milliseconds。I'd say we cant give ourselves a pair in the bag because they'll be a huge mission competition。

 okay？So our goal is to get 66。Down to 16。These are our tools that we're going to。

That are we going to play around with。This is the expected things we can get out of these tools。Okay。

😊，And but what we really want， our target is 16。OkayK that's the plan。

 we're probably going to spend today and probably the next stream as well optimizing these guys。

 maybe so they were always all we're going to do is the analyze part。Analyization， the analyze。第。

Yeah啲。We're going analyze。Probably today date and then I'm going to prepare and then do some stuff like this。

爱呢。And then we can think about Cdy and multi threadreading next time， probably。Okay。

 so that's the goal and we've probably saved that print screen。So just we can compare。



![](img/d2b281400e0d90c00f492f0adbc6943a_373.png)

I think I'm going to save that later on。 Okay， so that's the goal。

 Let's now start looking at this function， which are each our biggest culprit。



![](img/d2b281400e0d90c00f492f0adbc6943a_375.png)

Okay， so we have the begin profiler and。Yeah， so。Again， if we， if we do this。

And we go to full screen。

![](img/d2b281400e0d90c00f492f0adbc6943a_377.png)

And we see how much。

![](img/d2b281400e0d90c00f492f0adbc6943a_379.png)

Takes it。Okay， how much staking？

![](img/d2b281400e0d90c00f492f0adbc6943a_381.png)

It's taking a 25 per run。 Okay， let's see how that compare there。 pretty much said，25。Now。

We have two parts in this code， the first part is let let's call that that preamble。

 which is like transforming the vertex and we also have a speed and cleanup things here and we do a lot of stupid stuff here like to calculate the new rotator rack positions and the axiss。

We probably clean that a lot and this this is just the first part， this first part。

 if we analyze that and understand that and prepare for it， we can get like a lot going on。

And the other part。Yeah。😊，Okay， and the other part is actually the pixels。Okay， so this is the this。

The thing we run like millions of times per frame。

![](img/d2b281400e0d90c00f492f0adbc6943a_383.png)

So let's see if we like completely reduce that to zero， which is impossible， let's see。

 but if we optimize that bit， let's see how much we can reduce，s probably not that much。

Not in this scene at least， because we have just two rotator racks in the other one so that we have hundreds。

 we could probably benefit by optimizing this， which we are going to do。

 but let's just see at this point。

![](img/d2b281400e0d90c00f492f0adbc6943a_385.png)

I' see how optimize to my， yeah， didn't change。

![](img/d2b281400e0d90c00f492f0adbc6943a_387.png)

Didn't change anything， let me show you guys。Youre a 25 per run。Now we're still at 25。

 so we didn't change anything at all。So this guy， we don't have to worry about that。

So we don't have to worry about this guys for now， our big problem is this。

 so how are we going to optimize this code， first of all？First of all。

 we are going to unpack these operations。in fact， before we unpack。

There are some stupid stuff we are doing here。So let's understand the sort stuff we're doing。

We get pixelel， X I， cover that to float。And see if that't。And then we do three。

Different origin transformations on them。So you transform them。yeah， so see。

 once you stop to try to optimize the code， you see a lot of simple stuff were doing。



![](img/d2b281400e0d90c00f492f0adbc6943a_389.png)

That's say we have。We have this wrecked。

![](img/d2b281400e0d90c00f492f0adbc6943a_391.png)

And we have like this peak。What we are doing is we're calculating the right position to this guy。

 to this guy， to this guy and to this guy。That's pretty stupid。

All we need to do is to do like one guy， which is the origin， I suppose。



![](img/d2b281400e0d90c00f492f0adbc6943a_393.png)

So。Just make sure we don't break anything。In the menu。I'm going to draw another rotate guy。

 Let's call that。Test I don't know， sorry we're going to do like。T plus equals D T。

Then I'm going to rotate by the test。然后跟刘拼。The very end。And then let's do like a smaller guy。

This just so we can watch。The transformations are all 20，0。And let's do like。

Just so we can see that we're not doing， and let's also test the alpha。



![](img/d2b281400e0d90c00f492f0adbc6943a_395.png)

Because we can see that our code modifications doesn't change the behavior。

We don't want to change the behavior of the cult， just the performance of it。



![](img/d2b281400e0d90c00f492f0adbc6943a_397.png)

あ。

![](img/d2b281400e0d90c00f492f0adbc6943a_399.png)

Okay， so this is what we want to keep right， let's try taking this three sub sub operations to talking them into one and the dot product see。

 see this is going to be really cool just the first part， just the first optimization part。



![](img/d2b281400e0d90c00f492f0adbc6943a_401.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_402.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_403.png)

This guy。We're getting， like， the。We're getting。It's position relative to all these guys to calculate that。

Let's do a relative to like one guy。Only I saved this guy。Okay。Then willll dot product that。

With this guy and the other guy。ok。😊，And just by doing this， and we know that。It's the same thing。

 right in terms of like。Its style perpendicular。Because it's correct。So if you do these two， guys。

We can go， we can do it like。

![](img/d2b281400e0d90c00f492f0adbc6943a_405.png)

Z and one。 so instead of testing。You stop doing four tests， if it's greater than， oh。

 we're going to do four， or is that doing like four different ones？



![](img/d2b281400e0d90c00f492f0adbc6943a_407.png)

Like the dot product for each of these guys。 fantastic experience and0。😊。

We're gonna do like for two guys in test， it's greater than 0 and smaller than1。

 Sam thing for this guy。 So we're gonna do like。😊。

![](img/d2b281400e0d90c00f492f0adbc6943a_409.png)

Once up two dot products， they don't fantastic test here。

That's the plan that's just for the cleanup part， the first part， the understanding and analyzing。

 then can probably optimize that even further， so let's just。I'm going to call that relative。PixO P。

And let me just。That would be also cool to compare。I'm also， I'm going to keep this path like。Else。

But okay， so we're going to do also because we're going to part on a great pad example。

 So we have the P pixel relative P。Okay， and we're going to subtract that with the first point。

So that's the basis for our rotation。Okay， and then we're going to do two projections。

 the first one is going to be the first taxi， let's see， which is the first taxis。It's 0。1 minus0。

Okay， and we're also going to do。X is 3。And I'm going to rename that。To access。

We're also going to put the HC here。Can I rename these guys。This only two xs one and two。

And they both have the origin at pixelixel zero， which is the one that we're going to subtract。

 so the first projection is going to be the dot。Of the pixel。Reelative B。With the first taxis。

And the other one with the second axes， do I need to do that？

And if the first projection is greater than zero and。Smaller than one。



![](img/d2b281400e0d90c00f492f0adbc6943a_411.png)

So if you are inside this range right here。

![](img/d2b281400e0d90c00f492f0adbc6943a_413.png)

We should draw the pixel。Okay， and if the other projection。greater than 0 and less or than equal。

Less than r equal to1。Then we can draw。Thatてそ。First of all， let's see if it broke something。

And we did。是。O。Let's run the code and let's see what we broke。



![](img/d2b281400e0d90c00f492f0adbc6943a_415.png)

We're gonna let it run for three times。 So we're going take the guy whose point is 0， yeah。



![](img/d2b281400e0d90c00f492f0adbc6943a_417.png)

Oh， we're optimized so we have to take off the optimization flags that can probably debugged。



![](img/d2b281400e0d90c00f492f0adbc6943a_419.png)

Okay， now that's。Think about our optimizations。So one， two， three， so on the third guy is zero。

Can we do the racks and the axes？Yeah， well we can probably optimize that too。Yeah， certainly。

 certainly。 we do like。Eight matrix and multiplications。Okay， okay， okay， now let's see。Our， R P。

 are。Yes。😊，Oh， this is in Texas。No， this is not in pixels。Yeah， yeah， I'm sorry， this ist case。



![](img/d2b281400e0d90c00f492f0adbc6943a_421.png)

Okay， so and the center is like left， the bottom left。Okay， so we have these points like 600。300。66。

300。Okay， now the xs you're calculating R。One， which is this guy。Minus。啊。0。So why should be zero。

 so we have like zero。I know 60， and the other one is three。Minus this guy。And we have。Yeah。

 I think this should be like。This guy minus three。

![](img/d2b281400e0d90c00f492f0adbc6943a_423.png)

Because the X should point up，Ubsurize it， right， but should points like。Straight up， yeah。

Let's just see if we changed it visually。And I removed the point。记。Go still don' don't have anything。

不ち。

![](img/d2b281400e0d90c00f492f0adbc6943a_425.png)

In effect fact。Just for the first test that we're doing。I'm going to pass zero for the location。

 so that's going to be easier to divide。I mean， it's probably infected this guy here， yeah。

 so you can do it。

![](img/d2b281400e0d90c00f492f0adbc6943a_427.png)

Okay。So the angle is zero。And actually the break point， then I to for the break point。

So the first axis。Is 68 to0。 The second axisxes is。



![](img/d2b281400e0d90c00f492f0adbc6943a_429.png)

Oh， so I suppose it was correct。

![](img/d2b281400e0d90c00f492f0adbc6943a_431.png)

Yeah， actually I should have read the value itself of like guessing。68，0。0ero68， perfect。Now。嗯。

Let's see the first point。Is 5。97。In three or6， should we include that。

 let's see the minimum balance。I think we should。And the pig are relative。It's minus 0。9。

 so I suppose we shouldn't。You know what？Let's run the first pass first。

Just so we can get like the correct pixel position and things。



![](img/d2b281400e0d90c00f492f0adbc6943a_433.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_434.png)

Yeah， also。ok。Now， the pixel P is the same value， okay？Calculate the relatives， objectionions。

And we don't draw it。That's kind of a bumer。Let's see which ones， which one we do draw。

Not the second one。That's a buner because。Let's see which one we do draw。bri啊。X 1。



![](img/d2b281400e0d90c00f492f0adbc6943a_436.png)

And why1， so。And来 cheat。Maybe we can do that。For everyone。



![](img/d2b281400e0d90c00f492f0adbc6943a_438.png)

Maybe。I can think about that as well。Okay so now it'。Let's see if you manage to print this guy。

 and we do。So。If we now go back to our optimize， well， our not full optimize， but our。

Hopefully quicker pass。It should also fill so we have a benchmark for that。

 so the values are the same。A great relative。 The relative is a very small neck and a。Like0。6。

 this is， this looks pretty promising。 Now， when we dot that to the axisxes， we should have。

A value between0 and one， I'm pretty sure。I have three。You have 37。Oh， okay， I think because。

This actually is not normalized。

![](img/d2b281400e0d90c00f492f0adbc6943a_440.png)

I'm pretty sure that's the problem。Because we're doing same thing as we did in the UV。

Let's see where we did the UP。Yeah， mapping to normal。That's what we're doing pretty much。

Like we have the pixel。And then we're mapping the X。Enter the minimum and the maximum。

That's what we want to do。Inffect were just。We might just increase our speed。

 but this kind of comes with the understanding， we might just increase our speed just by doing days。

So math。Inter rangege normalized。Yeah， that's what I want to do。啊去。So。Now， we have the X。And the max。

 yeah， we have the range。It's called that x range x。Which is。Max bound。Minus。Menbound。

You't have the range wide。Maybe we're going to do those are vectors。

 but let's do one thing at a time。So。We have the pixel and it have the min and the max and the range。

 So we're going to do the v which let's say it's x minus the min。Bound X。ok。Divided by the range。

Divided by the。Thanks。And we don't need to clamp that because we're going to test。Down here。So。

 let's do like。Let's call that you for the lack of a better word。Same thing as the U。Okay。

 and we're gonna。Let me do with these guys。Okay。😊，Now。This should give us the year we want。

 Let's see what exactly we're Oh， is this correct。 Yeah， let's see what we're doing。

 I think we're doing exactly the same thing。But in a more complicated way。With the dot product。

Because that's easier to understand when we first hack the code， but right now when we're optimizing。

 it's doing like way more than we should do。So the min minus the bound。

 that's what we're doing like this， oh， shouldn't be the bound， actually。No， not the bound。Not about。

 It should actually be the。Rect， what is it called？Rect the P。Correct。JustP。

YouJust tried to open the window because it's kind of hot in here。す。

Yeah it's really hard here in Brazil does a doV2 use no， it doesn't use cosine but。还必须要有。Good point。

It does this。But even though it's not using cosine， this is a lot more than we need。

This is what we're doing。And we're going to like change。What we need。Yeah，'s let's do the same thing。

This part of a like opening。Expanding the function。So can get we can do everything in line。

 so don't need to function call， that's both for understanding and compile your help， really。

Even though it's marked as in line you never know， So the picture relative P yeah。

 so this is the picture relative P。X， correct， and the range。



![](img/d2b281400e0d90c00f492f0adbc6943a_442.png)

It's going to be。The length of the axis。

![](img/d2b281400e0d90c00f492f0adbc6943a_444.png)

So' going to precalculate that。So the range axes one。So this is also not correct。

I should really do them both， like the relatively B。Because they can't do it X separately。I think。

Well， I could。So。Yeah， so all I should do is divide by the range， I think。

 at this point and the range。Is the。

![](img/d2b281400e0d90c00f492f0adbc6943a_446.png)

This notThis like the bounding box， so the min and the max， so this the triangle。

 this the min and the max， right？Man max， man and Max what we want to do is to get this size because we want like zero to be here and want to be here。



![](img/d2b281400e0d90c00f492f0adbc6943a_448.png)

So this is actually going to be the length V2。Of the axisx one。And this is the length2 of the axis。

Okay， so。Lme。But like all that range one， range X is one。



![](img/d2b281400e0d90c00f492f0adbc6943a_450.png)

Okay。😊，So。

![](img/d2b281400e0d90c00f492f0adbc6943a_452.png)

This thing is going to work properly。 So we get like the size。 and then we see。です。

In the dot product part， which was what we were doing。We were doing like。

A dot x times b dot x plus B dot y A do right times B dot y。

Let's just see the value of our P of our EU， let's see。From int。And 32。Lth he two on5。

 Don't I have a length， or I only have length is squared。do。Square root F。Of these rights。

And they'll be the length too。Un square。是可。I thought we had a met， oh， yeah， we're doing like。买这样个人。

Sine F， cosine F。是。Okay。

![](img/d2b281400e0d90c00f492f0adbc6943a_454.png)

对 it。Now， let's see the value for this guy， we may lost。

So for each point you calculate if the point is inside rot rectangle exactly and by point you mean pixel and that's right so for each pixel because that's a shorterer render。

 this is what the GPU does if we use like openGL but this are not using openGL we have to do this ourselves so for every pixel and we're running like in 4K8 million pixels per second like and for each pixel。

 I have to know whether it's inside the rectangle or not。



![](img/d2b281400e0d90c00f492f0adbc6943a_456.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_457.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_458.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_459.png)

And this is the what is it called？The axis theorem， something next separation axis theorem。

Which basically we have like two axes。We can optimize this guy too is' like a lot of cr。

 but this guy we're getting we're getting good at his So for if it works right so for each pixel。

We have to know whether or not it's lays inside the rectangle， so we got each axis。

For the guy or because this thetum can do like just two。

And then we dot that with a projection with the relative P。 Then I get to 0， if you are like。



![](img/d2b281400e0d90c00f492f0adbc6943a_461.png)

Here。😊，And one， if we are here and everything in between， so if it's greater than one。

 we are outside if it's less than zero we are outside， and we're only testing this bouning box。

Re's like this right。

![](img/d2b281400e0d90c00f492f0adbc6943a_463.png)

Roing test this mailing box， so we optimized that inclusion as well。



![](img/d2b281400e0d90c00f492f0adbc6943a_465.png)

Okay， let's see now the values we have like the first second third。I pixel P。Same thing as before。

Who are going to subtract。This guy。By the men。And then divide by6 states so we get。

So this is what we expected to see this the correct value。

And I think that's pretty much what we have while we to do the correct dot product。Oh yeah。

 the correct， I mean， the normalized dot product。That's what we will get because the initial tests。



![](img/d2b281400e0d90c00f492f0adbc6943a_467.png)

We weren't normalizing like we are now， we were normalized because we're dividing by the range。

 right？And we only need to normalize these guys。Because before we were testing。

 let me see where before before we were testing just the beginning， so zero。 so all we cared about。



![](img/d2b281400e0d90c00f492f0adbc6943a_469.png)

Was if it's greater than zero for this guy， this guy， this guy and this guy。Okay。

 so if it's like this is 30， so if it's relative to like pixel and not the size， that's okay。

 but right now we're going to do like， well， we can also test。



![](img/d2b281400e0d90c00f492f0adbc6943a_471.png)

And I think therell be even a better optimization instead of dividing by the length。

We just test if it's less than。The， the length itself， so。The range act is one。And the range axis to。

 I think that'll be a because then we avoid to do the square root。We avoid doing the square root。

Here。等下找什么？All we do is a small subtraction。And we don't even need this guy and you can call set of view。

 were going to call that projection zero。For now， but。Wow。That that's funny。A scanline algorithm。

 Yeah， it is pretty much a scanline algorithm for simple shapes。

 we are going like like a scan line really， so yeah。



![](img/d2b281400e0d90c00f492f0adbc6943a_473.png)

Prety much。Okay，1，2，3。 Let's see。嗯。Our U is a very small number， well。

Not that small and a projection is bigger， I suppose that's okay。



![](img/d2b281400e0d90c00f492f0adbc6943a_475.png)

Okay， I think I am ready。To make another visual test。So I'm going to call that price zero。And。

Let's call that part one。We can just be one and two since we have like。One in two axes。

And this guy's going to be the。Oh， so this is wrong。

This has to be the full minus like we were doing the pixel relative。G。😊，Oh， okay。

 so I'm confused this will only work because we're not。Rotated。For rotateating。

 we need to do this whole thing， so we need to get subtraction because。Yeah。

Now that's keeping their steam。This is the same thing。



![](img/d2b281400e0d90c00f492f0adbc6943a_477.png)

Okay。😊，Now， the dot product。

![](img/d2b281400e0d90c00f492f0adbc6943a_479.png)

It's going to map into these and， yeah， so we do have to do the job product。



![](img/d2b281400e0d90c00f492f0adbc6943a_481.png)

But， yeah。But it is better I suppose。Prize1。Pze two， x is1， x' is two。

And band would test against these guys。Okay， so we are coming a long way we you don't need this guy。

 don't need this guy。F 32。Yeah， well。Yeah， let's do that in。And this guys effort。O。

And this is like the pixel。Right。

![](img/d2b281400e0d90c00f492f0adbc6943a_483.png)

Let's see the photoss we have。P哦 sorry。ですか。Xixel p。Pture relative。Projection。3。And guyss 37。It is。

We do paint， I'm not sure we are correct， though。

![](img/d2b281400e0d90c00f492f0adbc6943a_485.png)

Let's see how that looks。

![](img/d2b281400e0d90c00f492f0adbc6943a_487.png)

HmI don't know if guys probably can't see that。But we do have something。Can you see like here？

We have like one pixel。

![](img/d2b281400e0d90c00f492f0adbc6943a_489.png)

And it's going like crazy up。Okay。Yeah， see what they're having。🎼ほん。



![](img/d2b281400e0d90c00f492f0adbc6943a_491.png)

Okay。😊，嗯。That's so we are correct， I'm at this point we're pretty sure we're correct。



![](img/d2b281400e0d90c00f492f0adbc6943a_493.png)

Well， yeah， but I don't like the result again from the topt product。Get got like 30 something。

 we should get pretty close to zero。Because let's see， our pixel。It's this guy in our Maxim mint。啊。

Yeah， the axes。嗯。

![](img/d2b281400e0d90c00f492f0adbc6943a_495.png)

Yeah， let's open the dot product up。Because we're supposed to do that anyway。So。Laxxi。So this guy。

What we're going to do is the pixel。PP。Hey。X。D with the axises。So see， we already have like。Okay， so。

Okay。Let's a。

![](img/d2b281400e0d90c00f492f0adbc6943a_497.png)

Now we have the same thing， but it's in line， that's if you have the same result。



![](img/d2b281400e0d90c00f492f0adbc6943a_499.png)

We do have the same result。Okay， now the range。

![](img/d2b281400e0d90c00f492f0adbc6943a_501.png)

Let's just make sure it is what we expect， so let's run through debugger one more time。关。2， three。

 our range is 68， and this guy is also 68。 so this is perfect。Okay。Our picture is a guy。

 our picture are relative。Is 0。04 and 0。05。What we expect from the projection？😡。



![](img/d2b281400e0d90c00f492f0adbc6943a_503.png)

It's like。If you do a first pass over Y， you can calculate all the pixels that inside erect just two operations。

She start doing wise。If you do a first pass over why？I suppose you mean white pixels， right？

You can calculate all the pixels that are inside the。We this two operations。

But that'll be only in one axis。I suppose。If you see further understand what you mean， let's see。

For each line。Yeah， but if you do。A first passover y for each line， then we're doing x times y。

 right？And if yeah， for this line， you go through all the pixels and see。



![](img/d2b281400e0d90c00f492f0adbc6943a_505.png)

Oh， I suppose you mean。I don't know， I don't know exactly because at this point， for instance。



![](img/d2b281400e0d90c00f492f0adbc6943a_507.png)

We do have to calculate。This axisx， which can calculate only the min X。Yeah。

 but we're already doing that， we're already doing that mean and X of mean Y。

So these are the pixels that we ran， all these guys。



![](img/d2b281400e0d90c00f492f0adbc6943a_509.png)

And we just do this guy， this thing per pixel。

![](img/d2b281400e0d90c00f492f0adbc6943a_511.png)

So I don't think we can calculate less pixels。Because I didn like for every line。

 you have to check every pixel right， so but maybe the suggestion that you're doing。



![](img/d2b281400e0d90c00f492f0adbc6943a_513.png)

And said， Re， maybe you can optimize this calculation， just do one。



![](img/d2b281400e0d90c00f492f0adbc6943a_515.png)

Dot product。That could be a good optimization。啊。But I don't think you can because for each guy。

 you have to know like the two axes like this guy。And this guy as well。

You can use the line equation to calculate only the borders。Okay， so you mean like draw。

 first of all， draw the lines。嗯。😊，You have like a。A link for something。

It implements that because I'm not familiar with the line equation。

Like a rotated one because we do have axes we cha lines， right？

And the way I would run through these guys， just the way I'm running like run through the hole。

Rectangle of them right， and' see whether we should paint them or not。I suppose。啊。

Maybe there is a more。A simpler thing。

![](img/d2b281400e0d90c00f492f0adbc6943a_517.png)

To go straight to these guys。That could be a nice call。Line equation。Ex time。Okay。

So this is the equation。That V Z。那个。Ourl suggests you can get find A D for each of the lines。Yeah。

 so I suppose this is like per pixel right， x and y， well y is the resulting line。



![](img/d2b281400e0d90c00f492f0adbc6943a_519.png)

Then we are supposed to draw。I'm still not 100% sure what you mean， I mean this。

Let's say this our a pixel grid right， and we have like this line， let's say this line。

We need to know an X and and Y for every pixelel that we need to draw， let's say these guys。Right。

That's the thing。

![](img/d2b281400e0d90c00f492f0adbc6943a_521.png)

The way I'm doing now are trying to do， I mean， we did like this。And they run pretty pretty nicely。

 I mean， it worked right， but we have to optimize that。The way we were doing。

 we were doing like for every accident we did a do product per pixel。



![](img/d2b281400e0d90c00f492f0adbc6943a_523.png)

So that's what we did。And that's what we're trying to optimize。



![](img/d2b281400e0d90c00f492f0adbc6943a_525.png)

O。😊，啊。I'm not sure， though。Yeah， he said A and B。For each of the lines。

So let's say we have four billion lines。 So we're going to have four ys， but for every x。

 every x means every。Point X。Okay， I think， I think I know what mean， like for every。Yeah， okay。

 I think I know what for every X。Like for every， like this guy， this guy and this guy。

There should probably only have one。

![](img/d2b281400e0d90c00f492f0adbc6943a_527.png)

嗯。And for every x we can calculate where where the Y that I should paint right according to this equation。

 I'm not sure this is 100% though because like in this case we should paint these two guys。

So in this row。You should think two guys， who can invert the equation。X equals okay。

So we find the X and Y for every。

![](img/d2b281400e0d90c00f492f0adbc6943a_529.png)

Yeah， but if we run the equation for x and the y。You're going to end up doing all the pixels， see。

Yeah， you can import the equation。Hes the link data he provided。

Or not link you just type that on the chat okay， yeah。

 so we can find the x and y for every X and for every y。

 so we're going to be able to find these this guy for this X and this guy for this y。



![](img/d2b281400e0d90c00f492f0adbc6943a_531.png)

I suppose。Even if that's true， what you can do。But you can turn。You can run on for why。

But that would only give us a line and would it not run only for Y。Okay， yeah， so for every why。



![](img/d2b281400e0d90c00f492f0adbc6943a_533.png)

We're finding out。The X。And why？

![](img/d2b281400e0d90c00f492f0adbc6943a_535.png)

Okay， but the point is that's only going to give us the lines， it not。

If that only gives us the lines。We're still going to have to fill them and by filling them。

 we're going to have to test every pixel against the line。Right。Well。

 I suppose that if you have like the beginning and the end line。We could feel the whole role。Yeah。

 I suppose that's what you mean。 Yeah， if we manage to see the first guy and the last guy， yes， okay。

😊，Okay， now I understand a little bit better。Okay， so。So we find a role of pixels。

And then we see the minimum and the maximum of the collision in that row。

And this is the equations data。你自。Ourrael gave us。And if you do that to have the mini thematic。

 we going， okay， let's try commanding that。

![](img/d2b281400e0d90c00f492f0adbc6943a_537.png)

That's for implementing that。That's going to be really awesome if we managed to do that because。Yeah。

 I mean that's going to run way faster。Okay， so that's run for everyone。And we have like the men。

Bound lie and a max bound lie。And you help me out here， man， in case I know something stupid。

 okay so yeah， for everyone。

![](img/d2b281400e0d90c00f492f0adbc6943a_539.png)

We are going to have to see。

![](img/d2b281400e0d90c00f492f0adbc6943a_541.png)

The men。Nimax， so let's do like again。Inex。M max X。O。😊，And so we're going to find the x， right。

 so the x。Thiss supposed to be A， right。啊先。That's supposed to be A。So we're going to。I take。

Like minus B， iss gonna be Y minus B。为 minus B。先呃礼拜拜。O so。

But is that b minus y or y minus b I think it's going to be y minus b？Yeah， okay， so yeah。Okay。

 so we're going do this to find the minimum x。 So the minimum x is going to be less hardco that to be the first axis because we don't know because since this is a rotator rectangle。

 we don't know which of the axes that we want to actually do。 Well。

 maybe we can do like for every four。

![](img/d2b281400e0d90c00f492f0adbc6943a_543.png)

And see， yeah， I could do it like for every four。

![](img/d2b281400e0d90c00f492f0adbc6943a_545.png)

And see where it interact， Okay， so this is like a line。Sth collision night， pretty cool。

This is like。Let's look for the first one。So we're probably going to need all of the access。Okay。

 so the A it's going to be the aes。One dot。X and the B x is2。Dot way x is 1。t way， correct？Y and X。O。

😊，And that's called that。X1。Excellent。Okay。Now， we find out。



![](img/d2b281400e0d90c00f492f0adbc6943a_547.png)

For every line。And you have to get the min。Let's see。 it shouldn't be for every land thoughat。

Should be only four。

![](img/d2b281400e0d90c00f492f0adbc6943a_549.png)

2 of the exit。 but which two， I'm not sure。So this supposed to be like one and。To that。0，1。

I think this is wrong， I think I'm going to need。I I'm going to need new aes。So I'm going to do。

Ting'mre gonna do like foreign X gonna be。UFrom one to 0。Then from 3 to 0。Then from three to two。

Then， from 3。And from。To and from longitude。Okay we're going to do axs one and two are parallel。Yeah。

So I'm not sure which ax to get， honestly。I'm not sure which taxi is to get。

Let's just strike one and two。And。And this actually should be just。エチ？We're going to do like。

X equals x1。就。Should we do like。No， I'm not doing close。So here we just。Prora。Yeah， I also have to。

です。Can do pixelel。This is just to see if we manage to get somewhat word。

 then we think about more about these cats and these kind。喂。😊。



![](img/d2b281400e0d90c00f492f0adbc6943a_551.png)

Okay， lets。If you've got something。

![](img/d2b281400e0d90c00f492f0adbc6943a_553.png)

I think we actuallyly use the wrong exit。It game， let's try access。



![](img/d2b281400e0d90c00f492f0adbc6943a_555.png)

嗯。Okay， so we just crash。If you use X is3。Let's see what's the value of x。



![](img/d2b281400e0d90c00f492f0adbc6943a_557.png)

Oh， okay， that。Oh， okay。 so actually， that was a typo should be X。



![](img/d2b281400e0d90c00f492f0adbc6943a_559.png)

2 dot Y。はい子。

![](img/d2b281400e0d90c00f492f0adbc6943a_561.png)

Well， that's same result。

![](img/d2b281400e0d90c00f492f0adbc6943a_563.png)

Oh， because I guess。To the why I suppose it's zero。 So let's try。Three and four here。



![](img/d2b281400e0d90c00f492f0adbc6943a_565.png)

嗯。Dfinding by is zero。So先。

![](img/d2b281400e0d90c00f492f0adbc6943a_567.png)

I suppose it's one and four。I'm going to have to take a look at the aes。



![](img/d2b281400e0d90c00f492f0adbc6943a_569.png)

Oh， no， yeah， I guess we're correct。How， I can just see。你能干呢。But a break point let's。

Three point here see。1，2，3。I see the X is one。It the one that goes from x。

I suppose we have to offset that by the minimum x。You have to check the inclination of eachJX to verify and consider if it's turning an next max yeah。

But that's hardco that for the first time。Like。Have to check the inclination。嗯。

Because right now we're doing a square， this time it's just a square。So the x is like 068。Right。

And then minus-68。0。I suppose this is the wrong result， right？



![](img/d2b281400e0d90c00f492f0adbc6943a_571.png)

That's not。In this。Arithm， I suppose。The line should be like， this line should be cover testing。

 testing this guy。So this guy， yeah， it is minus680。So it's like。This。Do you have any code reference。

 man？

![](img/d2b281400e0d90c00f492f0adbc6943a_573.png)

Because。I don't know。I'm still not 100% sure how to get that working。



![](img/d2b281400e0d90c00f492f0adbc6943a_575.png)

I think I got the idea， I got the idea right， I need to get the minimum and the maximum X， right？

But for all we know， it could be any a and like to say I'd have to check the in of each axis to verify file。

 okay？But once we do know the axes。I suppose we have to。We have to project that axisx， right。

 have to do the dot product。

![](img/d2b281400e0d90c00f492f0adbc6943a_577.png)

Yeah， I think that's what we need to do like。

![](img/d2b281400e0d90c00f492f0adbc6943a_579.png)

We we used to do the dot product。那 see。😊，Let's see if we have like these guys in this like minus 68。

And this is like 60。Right。That's what we had。Now。For every pixel。Yeah， okay。嗯。



![](img/d2b281400e0d90c00f492f0adbc6943a_581.png)

Well， technically。If you don't care about。The rotation。Yeah。

 but that was what we were doing like way before， like just， yeah。

 just straight up setting the no next， right？

![](img/d2b281400e0d90c00f492f0adbc6943a_583.png)

But yeah， okay， but to get the min and the max， according to this new thing。



![](img/d2b281400e0d90c00f492f0adbc6943a_585.png)

嗯。But I think this is the other way around， right， let's see we got four and minus4。



![](img/d2b281400e0d90c00f492f0adbc6943a_587.png)

If you want to hard code the correct results， this should be one and two。



![](img/d2b281400e0d90c00f492f0adbc6943a_589.png)

Yeah。And， I think。But I may offset that by the。Why is it minus though。Yeah。

 it's offset by the mean bound X，m not sure it's the1% correct。I just want to see the correct result。



![](img/d2b281400e0d90c00f492f0adbc6943a_591.png)

爱奇。

![](img/d2b281400e0d90c00f492f0adbc6943a_593.png)

🎼啊。

![](img/d2b281400e0d90c00f492f0adbc6943a_595.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_596.png)

Okay。That's certainly not correct。

![](img/d2b281400e0d90c00f492f0adbc6943a_598.png)

Cause the aes。Wech should actually instead of subjecting by the axes。

I think I'm just going to do by the points。Right。Because the minimum x。

I think I should work out this equation just to make sure that I understand the equation。

Let's see we have like。50100。And 60，60 is the point， they have these guys。So， it's X。Mus y y zeros。

 is's going to be y。At'80。Divided by the x。You fight it by this guy？I actually just get the 50。

 right？How do I know it's 50？

![](img/d2b281400e0d90c00f492f0adbc6943a_600.png)

你拜你 by a。Yeah， but。啊。Did you said that A was like。The axes。唔知。If I end B for each of the lines。

 so a equals。啊。Okay， so I were doing like everything around。 So got a。Which is。This guy， why。

Dived by this guy at X。This for each of the x'es， right， so this is divided by a。

 I'm going to call that a1 for first axis。And then we have。The be。

What if x is zero if the rectangle is centered？I suppose that that has to be hard coded， right。

 T zero condition。Yeah， I suppose thats。Like。Yeah， I want have to hardcode this rope。

 but that's okay。 Let's just try to keep going and the be's gonna be exposed the other way around。

So it's going to be minus B。喂。Is that it？That help me out， man， that was that was your idea。うん。B2。

 right by a2。A1点。

![](img/d2b281400e0d90c00f492f0adbc6943a_602.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_603.png)

Okay， now we've got nothing。

![](img/d2b281400e0d90c00f492f0adbc6943a_605.png)

Let's debu that。3。A0 minus infinite。Yeah， because we were divided by zero so。

That says for x equals y， where is。X equals0 S y， these a constant。



![](img/d2b281400e0d90c00f492f0adbc6943a_607.png)

Okay。So that's so B says for x equals zero。

![](img/d2b281400e0d90c00f492f0adbc6943a_609.png)

Wheres why？

![](img/d2b281400e0d90c00f492f0adbc6943a_611.png)

That the。Okay， I suppose I yeah。I suppose that makes a little bit more sense。That's the men。About。

Right。So， yeah， because as you can see， I'm not much of a math guy。

 So weret have to do all our sort of。😊。

![](img/d2b281400e0d90c00f492f0adbc6943a_613.png)

Mad stuff， I do get a little bit lost。 That's why I do trust the code a little bit more。

So the B is a constant that says for I may actually study。L line equation。Opstream。

 maybe next time then I can improve the line equationator thing if we were to do this route。So。Okay。

 so we got Aes。Got to be。Says for x equals0， where's y。Am I entirely sure this is correct。

 This is mean X me。For x equals0。

![](img/d2b281400e0d90c00f492f0adbc6943a_615.png)

I don't know man。I know if you have some link where I can read on that。

I think we're going to read on that in next stream， yeah， sorry， no that's okay， man。

 so it's too it's also valid to go through these exploration things。



![](img/d2b281400e0d90c00f492f0adbc6943a_617.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_618.png)

I mean， I do， I did learn a lot about other possibilities。

 like this idea of running through each line。Each y and moving like the two bounds。

That can be like the quickest solution， I think are pretty correct。But the thing is。

 I'm not math savvy enough。To implement that right off the bat。

 right like right now on a live stream。But I am going to read on that。And maybe next time。

We'll be able to change the algorithm to run exactly like this。



![](img/d2b281400e0d90c00f492f0adbc6943a_620.png)

We just like。We calculate。We' not prepared that for next time。

This is going to be the x the equal minus。Y minus B times a。So this is where。Yeah。

 I think that'll be a good plan。Where a。A is。The axes。Y divided by the x is x。And B。Is that。

lead tells。Were outline。He is like。4 x equals 0。I'm trying to find the article where I can read about yeah。

 if you do find it， that' would be great help， but I think that's enough for me to start looking for examples。

I suppose that wasn't a very confident voice。😊，So we have to calculate B， A and the B in this case。



![](img/d2b281400e0d90c00f492f0adbc6943a_622.png)

For I understood the idea。 and I think that's a great idea， like。If we manage to do this。嗯。Yeah。

 we have to know like for air。That's what you mean by skinline。

 This is pretty much exactly skinline right， so we go from each one and we see where we should collide。

Yeah。😊，So if I managed to understand。The math behind finding these mini Max。



![](img/d2b281400e0d90c00f492f0adbc6943a_624.png)

It's very pretty easy to implement， usually these math kind of stuff is a little bit harder to understand them to implement。



![](img/d2b281400e0d90c00f492f0adbc6943a_626.png)

So that's， I think， the problem that I faced today。But thanks a lot， man， for for having me。

It's always nice to understand more algorithms and I'm not even a CSS person that much so。

Not a math person， not a CS person， just a game dad。



![](img/d2b281400e0d90c00f492f0adbc6943a_628.png)

So I think we're going to leave that for next time we're going to comment that like。



![](img/d2b281400e0d90c00f492f0adbc6943a_630.png)

Now I think you're going to come at solutions。

![](img/d2b281400e0d90c00f492f0adbc6943a_632.png)

So maybe we're going to optimize to doing like this， okay？But for now。Let's see。系啊。A and B insert。

Okay， let's go back to the slow version。Just make sure it's working。And it's not working。あ。😮。

What happened。I think I have an extra。No， I don't know what happened。Oh。那O。



![](img/d2b281400e0d90c00f492f0adbc6943a_634.png)

I suppose。Yeah， ok。Let's see if this low version works。



![](img/d2b281400e0d90c00f492f0adbc6943a_636.png)

Yeah， for slow version books。Let's try doing the。The normal one。Well， it's going to be。都起。one。Yeah。

know， zero and zero。Okay， so the idea is just to compress what we were doing like stupidly into a smarter thing。

 and I think we are getting somewhere， but still not 100%。



![](img/d2b281400e0d90c00f492f0adbc6943a_638.png)

It's like zero% in terms of vivo。Viual result。But sometimes we do have to take a step back。Okay。

So the P，'m sorry let me do one more and a。They lost which you keep us。1，2，3。Oh， what happened？😮。

Or not。Oh yeah， it's supposed to be like this。1，2，3。Now let's see， our pixel is this guy。

Our relative pixelel is this guy。 So we have， as we say here， the knife and the cheese in our hands。

All I have to do is this is perfect， this is the relative P。All I have to do is to know。

The dot the dot product， yeah， between these guys， I think the problem is a normalization problem。

 one of the vector should be normalized and isn't。So。We have。Let's see what we have。We have this fee。

嗯。Okay， and we have these axis right now。The a that we're doing have like。0。We have this axis。

And this axis。All you need to do is to。She got the。

The dot product to see where we map onto this axis。This is perfect， I think， but for some reason。

We're getting weird numbers， we got three and 37。So I okay， so this guy is。Zero， okay。

 so this is something thing that matters so we are going。Okay， so this should be zero。

 this should be 0 dot 04 times this。Which is 3。That does not look correct。At all。0 dot 0，4。Okay。

Let's assume this is correct。But the line is a bit weird because。This guy， they're relative。

It's like 。05。And were going， like，0。05 times this。Okay。Yeah。😊，I think I know the problem。

 This guys supposed to be normalized。By this guy。

![](img/d2b281400e0d90c00f492f0adbc6943a_640.png)

Yeah。😊，And by normalizing me。0。

![](img/d2b281400e0d90c00f492f0adbc6943a_642.png)

Yeah。

![](img/d2b281400e0d90c00f492f0adbc6943a_644.png)

Let me just check。Let me go back to the dots product version。Okay。嗯。X is one and x is 2。Sscribe。

But this is their fix。Oh， you know what， that was what we were doing。We were subtracting。These guys。

1，2。Yeah， you know what， let's do like one step at a time， I think。

I try to get way too ahead of myself。Start up doing like one， two。Let's do like this。

And let's remove。The third relative vaccine， reaches is by three。And then we can do。We can do like。

 all these axes。But。There's something set up。3。Sts doing10，01。



![](img/d2b281400e0d90c00f492f0adbc6943a_646.png)

Which is this guy？They I'm going to do 0，3。And one， three。



![](img/d2b281400e0d90c00f492f0adbc6943a_648.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_649.png)

And let me just see if I didn't break。I might have broken。



![](img/d2b281400e0d90c00f492f0adbc6943a_651.png)

Think。や的。Yeah， I did break， I did break。So。6 is 3。Okay。嗯。

Now we only get two of them and let's see these dot products， let's see。



![](img/d2b281400e0d90c00f492f0adbc6943a_653.png)

1，2，3。Okay， then we've got the pixel relatives to the tube。Two other points。And dot products。



![](img/d2b281400e0d90c00f492f0adbc6943a_655.png)

Yeah， let me analyze the numbers of one more time。

![](img/d2b281400e0d90c00f492f0adbc6943a_657.png)

Okay。So we're going to find the relative to the zeroth point。The second point。Third point， et cetera。

The dot products。Get all positive， right。But we do the first with one and three。



![](img/d2b281400e0d90c00f492f0adbc6943a_659.png)

Oh yeah， we did that wrong， so one in three。ok。And then we do 0，1。Which is this guy。 and then 0，3。

To this guy， what I should do is zero， one and2， three。See，0-3。Yeah。😊。



![](img/d2b281400e0d90c00f492f0adbc6943a_661.png)

So。We have zero，1，2，3。First axisxes is。01， so we go like from zero to one。

 then to go from one to zero。That's kind of stupid。Then we go from zero to three。zeroYeah。

 so this is what we want to avoid。This back and forth。



![](img/d2b281400e0d90c00f492f0adbc6943a_663.png)

Yeah， so that's the only thing we want to avoid and that'll because avoid like I hope my stuff so。

I want to avoid this guy and this guy。Let me just see again if I am running correctly。At this point。

See。

![](img/d2b281400e0d90c00f492f0adbc6943a_665.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_666.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_667.png)

We are not what happened？Yeah。Okay， let me just go back to what was working。其 so。

So this is perfect behavior now。What I want to do is to eliminate， let's do one step of time。

 let's eliminate。This guy， the projection two。Projection two is doing the same relative point。

 which is this guy。

![](img/d2b281400e0d90c00f492f0adbc6943a_669.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_670.png)

By now it's doing that。

![](img/d2b281400e0d90c00f492f0adbc6943a_672.png)

With the other axes。Like this taxes。

![](img/d2b281400e0d90c00f492f0adbc6943a_674.png)

Thats right。Instead of doing this。All I， I am going to do。If the test projection0 size。



![](img/d2b281400e0d90c00f492f0adbc6943a_676.png)

Let's see production size。For the working， they still like one。それ以ラ。They are three。4000。37。And 4000。

I don't understand why it's maybe if I divide 4000。By 68， let's do like。4000。食时 ok。Okay。Okay。

 this is rare to check if I point inside the shape pretty quickly about I don' understand why it works。

 okay， I just thought like okay， thanks for the reference man， I am going to state that。

I'm going to save that here in my browser。And I'm going to check it out offstream and hopefully you can improve that later on。

 that'll be cool， but I think now we are to a nice point。The projection。Here。

This P guy could be normalized。Could be divided by the maximum size。



![](img/d2b281400e0d90c00f492f0adbc6943a_678.png)

To get the result。 So if I remove。This guy。Okay。😊，And we're going to test it this guy。

It's going to be a lot of math at first， I。But this work if this guy is greater than them。The axises。

五玩。Whenlay， okay。That's great that。王磊。Okay， but this is not correct。 This is actually。

 this guy's divided by。The X is one length， Okay， let's see。



![](img/d2b281400e0d90c00f492f0adbc6943a_680.png)

If we mentioned got that working， then we can optimize that optimization。If that makes sense， okay。

 so we got to working。The projection  zero is3， if we do this。Okay。Let's see how that looks。



![](img/d2b281400e0d90c00f492f0adbc6943a_682.png)

Okay， it's not quite great。

![](img/d2b281400e0d90c00f492f0adbc6943a_684.png)

Not quite right。嗯。Because the projection 0。

![](img/d2b281400e0d90c00f492f0adbc6943a_686.png)

Let's。Let's again， see the data because that was like 4000 something。嗯。Oh。What happened？

Did I get the wrong， Yeah， I got the wrong back？Oh， Alex。23。Okay， the projection 0 is 3。Okay。

3 should be greater than 0。 And this three。

![](img/d2b281400e0d90c00f492f0adbc6943a_688.png)

See， this is where I don't understand。I have this point， which is like this guy。

Maybe I should normalize。

![](img/d2b281400e0d90c00f492f0adbc6943a_690.png)

Oh， yes。Oh yes， I think I got a problem， I should normalize the axes。Okay。Okay。

 I think I got the problem。The axes should be normalized。Should we create them and normalized。

I think even have normalized yet。Amal eyes， okay， they're going to do。Or let's do like the first guy。

It'Go going to be x is one and x is2。And I can do like。Dix up to ur。With a normalized axis and。

And lesss than the X point length。And they've got the punch one。

To be less or equal to the axis is to。Okay， we don't have normal eyes。Kur， what's that。Oh。

 Microsoft Matt。Okay。Let's quickly do normalize。So Is do anymore more。On the lines take effect。

We're going to return。The vector。Divided by its length， right？

So I don't think we have let's do like a Mo too。And I'm going to multiply the vector by one divided by the length。

Okay。😊，Aes。黄你。あ。起来。

![](img/d2b281400e0d90c00f492f0adbc6943a_692.png)

Okay， okay， let's see what they have。1，2，3， see。Yeah， this looks。Oh， it was the same。How come。

Oh oh no， this is correct， but now you should be able to test this。Against these guys。But。



![](img/d2b281400e0d90c00f492f0adbc6943a_694.png)

still have only one pixel。Come on， man。 I thought that was going to work。



![](img/d2b281400e0d90c00f492f0adbc6943a_696.png)

🎼Yeah。

![](img/d2b281400e0d90c00f492f0adbc6943a_698.png)

There's only like one pixelile moving in a slow way， not a weird way。You did a dot product。

With the pixel relative。That's just one guy。Yes。

![](img/d2b281400e0d90c00f492f0adbc6943a_700.png)

Just so we know， if we have something。So we have a line and that's wrong， I think。And the thing is。

 we have a line。That's rotating around the centered point。



![](img/d2b281400e0d90c00f492f0adbc6943a_702.png)

Probably， this is wrong。Like， let's see。 Our axes are。This guy mines this guy。Normalized。



![](img/d2b281400e0d90c00f492f0adbc6943a_704.png)

Here is a tough product。Okay， let's。You know what， Let me remove。You guys。Just so we could like one。

One guy， only。And we can of see like the first one。Dixel is 598。

3 or7 and the projection looks perfect。Next one。Well， I didn't like next frame。Okay， next one。

The pixel moves one and the projection is one。 See， this is what I expected。



![](img/d2b281400e0d90c00f492f0adbc6943a_706.png)

Oh， the X length to be calculated before。 Okay， that was a stupid mistake because okay， okay。

 now our normalized plane is not， it's not completely forfeited。😊。



![](img/d2b281400e0d90c00f492f0adbc6943a_708.png)

X is1。OkaySo first of all， I have to calculate X's one。Okay。😊，Get to normalize it。

I already had the axis1， why not？I do have this guy can be like really optimized a lot。

 but let's do one step at a time because I get really excited exit one。Normalli of Xs one。And。

Acc is to。On back is too。I want to see it。Oh okay， we started off okay。

But we are skewing instead of rotating。🎼Let's see if we're going to go back to rectangle or if we're going to compress ourselves down to zero。



![](img/d2b281400e0d90c00f492f0adbc6943a_710.png)

Oh， yeah， okay， I suppose this is an X and Y mismatch I'm thinking。So。Okay， oh， okay。

 now because I comment out this code。

![](img/d2b281400e0d90c00f492f0adbc6943a_712.png)

See， let's see， let's see， let's see。 Okay， oh my God， we are running so much faster， I think。



![](img/d2b281400e0d90c00f492f0adbc6943a_714.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_715.png)

Okay， finally。Finally， finally， we've managed。To change， okay。Yeah that。That was nice。

 It took a long time， but we managed to， and that was the like small understanding thing we can we can do a better job。

 but。We first managed to change from three subs and four dot products。

To one sub and four and and two do， so we already compress like half of the math involved so remember that our target。

You see， our target was half。I think we already got that just by the first step。

And we can even do like a better job。And this thing， but just for the fun of it。

Let's now build an optimized build。And that's test。However well we are running a full screen。



![](img/d2b281400e0d90c00f492f0adbc6943a_717.png)

开起。😊，Full screen。And I print screen， move at sea。

![](img/d2b281400e0d90c00f492f0adbc6943a_719.png)

We were running at 25 milliseconds。 Oh， know what to be fair。 I have to remove。The other wreck。

This guy。

![](img/d2b281400e0d90c00f492f0adbc6943a_721.png)

Okay， so let's make it like full screen， take a print。



![](img/d2b281400e0d90c00f492f0adbc6943a_723.png)

I already saw the result I saw。With a hint of my eye。



![](img/d2b281400e0d90c00f492f0adbc6943a_725.png)

Dude。We already。Good went。2。14 milliseconds for frame。So we went to 25。I wait 1 for tea。

So we managed to have or lets do like 14。So we did like a 44%。Increase。Already。

And now we're running at 44 milliseconds per frame。That's almost acceptable， playable。

 but we're going to go to 16。Miseconds。And okay。And if you're managed to implement that other optimization。

That。V0 male， I think is V0 male is not V0 male。Sugges it。Maybe we can。

Make even like one two doctor products per row， maybe four per row。

But that would be a huge optimization。Okay。Let's do just a little bit more of optimizations。Because。

😊，When you are going to do like Cimdy or yeah， Cdy in this guy。

We should really spread out all the functions。So of'm doing like V2， I'm going， I'm going to do like。

Alf 32。For everyone。These guys， so I'm going to do the dot product。In F32。

 because if we syn theize that。We' going to run at one， takes ahead of time。

So we're going to stack like X，x，x and y，Y，Y。Yeah， they have that。Okay， so let's。Let's do the。

The do product like this。Where a is this guy。And the is this guy。Okay。😊，ItSa thing。

 but now it's actually。Se a is one El projection。1， let's do like  one and2。

Like we did do it back and forth。Time。Okay。Its so real， whatever。



![](img/d2b281400e0d90c00f492f0adbc6943a_727.png)

I see if you still have the running。

![](img/d2b281400e0d90c00f492f0adbc6943a_729.png)

We do。Okay。And。That's a bit more clearer。 Now let's do this guy as two。F 32 guys。

 I'm going to do like。This guy。That x， which is just the X pixel。Minus。It's guy dotX。

And same thing for the why。Okay。😊，And in this case， I're going to do this guy。X。

And this can be precompd， this guy。二の下。Can't。I'm sorry， it's supposed to be like this。



![](img/d2b281400e0d90c00f492f0adbc6943a_731.png)

Okay。At me。

![](img/d2b281400e0d90c00f492f0adbc6943a_733.png)

Dude， we already got another big performance boost。Just对 see。

And you can remove that when we say in line to the compiler。It doesn't care。Like。

The duck right was in line， the subv was in line。But this is like suppose's more clear for the compiler。



![](img/d2b281400e0d90c00f492f0adbc6943a_735.png)

And yeah， dude， let's see。

![](img/d2b281400e0d90c00f492f0adbc6943a_737.png)

Dude， dude， dude， dude， check， check this out， check this out。Oh， I forgot to print now I think。



![](img/d2b281400e0d90c00f492f0adbc6943a_739.png)

I don't even have words to describe。So we already dropped。66%。Next to 22。Milliseconds per frame。

You know what？Yeah。No， that that's it， man。That's it we dropped， we can go further， I think。

We're going to go further， let's see if I have time， I have to have to leave in some time。

 but I do have a little bit more time。We were 25 now we were four。P rotated rectangle。Yeah。

That's also， dude， that's so， so， so， so much better。 Let's see quickly。😊。

On the software render thing， let's see what we do in the bitmap。

 I don't think Bitmap has a huge preamble no， pretty small。 just oh， no this。Yes。Pretty small。

But here we do the mapping things range normalized。Yeah， I do the alpha thing。 This is a bit crazy。

Im I learn the color。You could probably have a non luped version of the colory how much a skin gain we have。

If I don't blur the color and just set the color。

![](img/d2b281400e0d90c00f492f0adbc6943a_741.png)

安。

![](img/d2b281400e0d90c00f492f0adbc6943a_743.png)

So we were a four。Meiseconds。うん。😊，So， yeah。We dropped substantially。 Yeah， we dropped like。

Almost 25%， so our alertp is problematic。You know what I'm going to do？Which is gonna be。

It's going to be kind of bad because we're going to split the code。But I'm going to speed the cold。

And then later I'm going to probably reunite the code， but I'm going to do like a draw。

Rotated wrecked。That's not transparent。嗯。😊，That's mostly for the mans and stuff。So， yeah。Alpha。

 let's see。And for this guy， I'm going to start cleaning。He that。This。

Because this is like way better this now we could simply that， but's pretty， pretty straightforward。

I think。Yes。It's super easy， actually。嗯。啊。We can probably work on this guy like a lot。

 but for this other guy。

![](img/d2b281400e0d90c00f492f0adbc6943a_745.png)

We're going to work on that later。Let's see how much of a speed boost we have。 Well。

 you do have to call the other guys， right， so in the menu。



![](img/d2b281400e0d90c00f492f0adbc6943a_747.png)

I'm going to do a。I for our rotated rack。Too many。 Yeah， we don't need。 Oh， oh no。



![](img/d2b281400e0d90c00f492f0adbc6943a_749.png)

Yeah， youですか。さ。We did have a alpha。

![](img/d2b281400e0d90c00f492f0adbc6943a_751.png)

Okay， now a little bit of speed boost。Not too much， though。I don't know why。Yeah。Let's do。

 like the transparent。Let's just see who uses this。Meter particles。

 particles going to have to compute the only particles now。

So this is better now let's go back to the game。Alaxy。😊，Maybe floating print collar， maybe simply。

 maybe a sink。What you're going to do is。Like， optimize。那一个。Inline， expand， expand。This map。Entrance。

Parent rotated。Big so。Cause。Optimize， transparent to interacts。Ser direct。Preamble。

 I'm not sure that's how you write preamble。 That's the And I think we're gonna do that。

We did a profiler I think we're going to do that today， these two guys。



![](img/d2b281400e0d90c00f492f0adbc6943a_753.png)

Maybe next time I'm going to think about these guys。Okay， let's just see how well we are running。



![](img/d2b281400e0d90c00f492f0adbc6943a_755.png)

Yeah， we were wearing about two cranes per second。2 meiseconds per frame。2。7， yeah。

 it's pretty much the same result。ok。😊，So。😊，Just a reminder。

 we were running at 66 now were running at 20 and we didn't do pretty much any I mean。

 we spent a lot of time， a long time understanding the code。

 and that's the most important thing that that we have to do when we are optimizing。

 we shouldn't really really understand。

![](img/d2b281400e0d90c00f492f0adbc6943a_757.png)

What do you do， I'm going to do these two guys。So I expect an improvement on the bitmap energy thetic rectangles。

 pixel calls。But I'm going to take one like maybe a two minute break。Let's see。 Yeah。

 I'm gonna take a two minute break。 Again I'm gonna try to do those pretty quickly。 But It know。

 I do have to go in a while， so。2 minute。Great。😊，And I'm excited。

Yeah would be so cool if we managed to get。To get a。



![](img/d2b281400e0d90c00f492f0adbc6943a_759.png)

The menu to 16 frames per second。It's like 19， 20， 19 right now。And let's analyze that。So we cant。

So we can see whether or not we can do it this like。Or about 20 frames per。

20 milliseconds per frame and keep saying the wrong thing。呃。So the game。

Sticking 16 and we are spending four on the flip。Okay， so。Have to optimize this 16。Okay。And the 16。

It spent pretty much everything on the render。Everything's illator。



![](img/d2b281400e0d90c00f492f0adbc6943a_761.png)

So we have 13 plus 15， yeah。I think we free optimizetimize the dip mapap。We will be good to go。

But we could also。Yeah， less see a bit than that now。That is the bitmap now， dude。Dude， so cool。

 Really cool now。let's understand what we're doing in the loop of the bitmap。So the bitmap is not。是。

The bitmap。It's not rotated。But we do have to calculate the Us。So I'm going to expand。

The math is a normalizedized thing。See嗯。Yes。两得起。The V， let's do another V。And the range。

Can you calculated like this like range。Range。What did I do。Bangrange， why。It's going to be why。1。

Minus y 0。Then when I do the range X could be x 1 minus x 0。So this would be the range wide。

Theve is why。Minus min。Do we need to clamp？Free sure we do。I mean。

 I think we shouldn't ever make that's just a c。Yeah。😊，Let's assert。The。😊，Is less than 0。

 or it's greater than or equal to 0。Andvy。Is less than greater or equal to one。Okay， so we changed。

All these guys to like this guy。I do the same thing for you。Oh， tyypo， think I got that。

So y minus min and a min is actually。So x minus x1。強要。You does the you thing。And as a search you。

Okay。😊，Okay。And so this is pretty， pretty good。We do have a number right yeah we do， it's 8。

7 a milliseconds per frame。Um。The lup。Let's open up the。Let me do int。Pixel X。It's going to be cast。

Of this guy。Where you。You is the T。So this is新。A。Is0。看。Yeah。And this is in that breath。So。

Another great optimization just。😊，By expanding the function。Dude， this is awesome。

You times did that with。That was correct。And the same thing for the pixel Y。这BV。

Times a bit more height。Okay。I think you can reach  16 milliseconds per frame， I think we can。Okay。

Lv is removed。Colored。Is a。Yeah， I would have to do the out on this guy， so the color。

Is the Binap Excels？Yeah， this is like the we can recalculate this。Call that strideide。

 What is it called。Bch。刚来。It's got that's right， I think。And let's see pixel Y is used anywhere else。

Is not。So I think we're just going to enlighten this guy。Well， yeah。Do we need to that。

 so we don't need to do this enough。32。I don need to cast this well， but。Not sure。

Whether or not we should do this in F32。I should just say the algorithm I propose is faster without Cdy。

But we CM theR version could be optimize much further。嗯， okay。That is a nice point。Because。

The code is really easy。To make wine isn't Cindy。I mean。The draw rotated。Is that， yeah。This code。

 I mean， it super easy。 We have like seamless subtraction， seamless subtraction。Seeimply multiply。

 multiply， add。That's it。That's basically and then we do like a mask。So yeah。

 if and the idea is if we need to sym theize， we can get like four times。

 well not exactly four times， it pretty much four times faster。Then where we are now。

So we can get this down to like。Ha。Half a millisecond。Dude， but I don't think you're going to need。

 honestly because。We're going to be super fast just by doing these。First optimization。

 but we could also do that in parallel， that was the other plan。

 we could do that can to thread that because we already have the system。

 the job system to do that in parallel， and we could also get like two x from that。

So it can get other way to like 0。25。Meilliseconds， dude， computers are fast。Okay。Let's see。

 Annastride beat this guy。Conversion from。And the range or the range。そ。Yeah， the range has to be。

This guy drew 32。Okay， and this guy conversion。For I that they're two to int。

Which is the V at V F F 32。This is wrong， is it not？V time is withthap with time thisap height。

 that's the。Yeah， I suppose it is correct。So let's do everything like this specific that's all that dilemma。

O。😊，呃。Okay， pointer add。C inter。 Yeah， okay， so。Actually， the result will be an end。

But I do have to do the math in float。Okay。Now。So the color will be the pixel plus Sky。

 then we get it below that。The alpha， so I'm going to get， this is kind of。This is。We can get。

This guy。Out。来。Can you like the alpha multiplier？Times 255。

And then it's the color that I match the alpha shift。And I'm multiplying it by the alpha， Okay。

 we did remove one guy and this lub， we are probably going to change that to floating point。But。Yeah。

嗯。But since we are not， let's just doing like。Ofer。Lerp， like。Color， alert。Alpha。

You then I have to also get the naked color。I'm going to do a like collar。Equals。This guy。And then。

We should do like。R。He callss this guy。We are probably going to break something in the way， G and B。

Okay。Okay， and let's see。Oh， we are doing therping F32， though。What is color。

 the color is the pixel color？Okay， so in order to optimize that。We would have to make。

Our frame buffer inflowat， which I don't think we're going to do。

So I don't think we can escape doing this。Yeah。Yes。Let's do another lub。See， like。These guys。

And the T is the T。No。Where is the T， the tea is the alpha？I just hope some。Ts the alpha。

 alpha times。BR。I this guy times AR， so this is one of mines the output。Yeah。

 I don't think we can optimize this in any way。1 minus the alpha。Times AR。Yeah。1一。😊，一。To理。建笔。Okay。

And now the final color will be the shifts。And a pixel。It's going to be well， another blur color。

Oh no， if there's this guy already。It's just another make color， right。Yeah， I still like。Color the。

Okay a。And they。Actually， it's the other way around。This is a。Okay， so color。He。😊。

So we had the alpha。Then me extract the individual guys from here and from here。Like the pixel。

Then we will。Yeah， we blend them together。变成啲二分。3。Yeah， okay。This looks。About right to me。



![](img/d2b281400e0d90c00f492f0adbc6943a_763.png)

So we were running at 8。7。First of all， let's see if you have。🎼So。



![](img/d2b281400e0d90c00f492f0adbc6943a_765.png)

Our result is not correct。That looked like a stride problem to me。Oh man， we did so much stuff。

 I should have taken that slowly。嗯。现在47点727。Let me just remove the alpha。

And let's just set the color directly here。

![](img/d2b281400e0d90c00f492f0adbc6943a_767.png)

I see。😊。

![](img/d2b281400e0d90c00f492f0adbc6943a_769.png)

Okay。This guy。Make that。O。Okay， the problem was the stride。

We were doing the multiply in the wrong pantar way。They were doing height。Cast after everything。

 we should have done that before。

![](img/d2b281400e0d90c00f492f0adbc6943a_771.png)

Okay， I been that for renderer he back to normal， let's see。



![](img/d2b281400e0d90c00f492f0adbc6943a_773.png)

I didn't see how fast we were rendering。So you guys will see with me for the first time， let's see。

We got about。1。5。2 and得六 two。Miseconds。Okay， it wasn't too bad。啊。Yeah， so this is pretty。 Well。

 you know what， if I remove the assert。AndAnd the profiler， that would be cheating。



![](img/d2b281400e0d90c00f492f0adbc6943a_775.png)

Let's just see just for fun。

![](img/d2b281400e0d90c00f492f0adbc6943a_777.png)

Let's keep the profile。对。

![](img/d2b281400e0d90c00f492f0adbc6943a_779.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_780.png)

Yeah， well you have the same result， the assert didn't doing anything。

I thought I would have gotten more。I thought， yeah， in fact， that was。That result。

I thought we we would have gotten more by just collapsing， we did remove a couple of things。

 let's see if we can precalculate anything the the range we did。Let's remove this a。Color。

We could pre add the pixels to the stride and do that。And how that like。Soce， pixels。

It's going to be this guy plus the stripes， so spa。Exそ。Let's see what else。 Yeah， this has no escape。

Well。Yeah， that pixel。Color。Where do we declare a color？Yeah， this is like stupid。We call that。Soce。

It map color。O。Yeah， alpha times。Yeah， see， this is where pre multiplied alpha comes into play。

We could do pre multiply alpha。That would optimize this part。But。Yeah。Okay。



![](img/d2b281400e0d90c00f492f0adbc6943a_782.png)

Yeah， a bit better。Yeah， I got to 18， sometimes 17 sometimes 20。Oh， this is a better number we got 6。

7。You a smaller one， but we've got a larger bank。Yeah。14。So we got to 14。

 but the Windows takes three。Yeah， I suppose that's all we can do for now。Now。

 we can also fix the preamble， let's just see how much the preamble takes for the Gitmap。



![](img/d2b281400e0d90c00f492f0adbc6943a_784.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_785.png)

Because that looks。

![](img/d2b281400e0d90c00f492f0adbc6943a_787.png)

So we were at。6。7 approximately。

![](img/d2b281400e0d90c00f492f0adbc6943a_789.png)

Yeah， I always， yeah， takes like nothing at all which to like 6。7。



![](img/d2b281400e0d90c00f492f0adbc6943a_791.png)

So。So we still that six。 seven。We are at。5，5。46。In the draw， rotated。



![](img/d2b281400e0d90c00f492f0adbc6943a_793.png)

Correct， but if we remove the preample things。This is a lot more。

 so I suppose we could get it better。

![](img/d2b281400e0d90c00f492f0adbc6943a_795.png)

You get a better performance。Yeah， no。

![](img/d2b281400e0d90c00f492f0adbc6943a_797.png)

Nothing changed， really。Well， this may actually be different in the gameplay。

Because we have a lot more particles。

![](img/d2b281400e0d90c00f492f0adbc6943a_799.png)

I' seeing the gameplay。

![](img/d2b281400e0d90c00f492f0adbc6943a_801.png)

🎼嗯。🎼す。Yeah， it's kind of hard。So but it's pretty fast。Let's make that full screen。



![](img/d2b281400e0d90c00f492f0adbc6943a_803.png)

🎼Yeah， so even the full screen， I'm going to take a screenshot let me see like a crazy particle。



![](img/d2b281400e0d90c00f492f0adbc6943a_805.png)

I just do like space invades that can get it crazy。Okay， let's got comments real。See， we are like。



![](img/d2b281400e0d90c00f492f0adbc6943a_807.png)

The bitnap is pretty slow， yeah， so we are very slow because of the bitnap that was a nice catch。

 so we were doing all sorts of crazy stuff。Oh， we weren't doing it。That many crazy stuff。

This guy's pretty quickly。Yeah， we take a  zero。0。So yeah， for a guy。

So I think we got to a good point and they rotate back。The Bimap is still pretty bad。

I think that's what we should optimize next。Yeah， we're taking like eight in here。And a foreign here。

Probably because of the fourth field， which is like a huge bitm。



![](img/d2b281400e0d90c00f492f0adbc6943a_809.png)

Yeah。😊，So we are getting there。 so let me update what you do。You know what I。

I'll come here to the profiler because we ought to do this anyway and take like D DT。Well。

 I'm going to keep the Dt here， but I'm also going for the D team the game。Like。



![](img/d2b281400e0d90c00f492f0adbc6943a_811.png)

Just so we can test like。

![](img/d2b281400e0d90c00f492f0adbc6943a_813.png)

Yeah， we're like 17 up to 20。Meiseconds per frame。

![](img/d2b281400e0d90c00f492f0adbc6943a_815.png)

And if I do like no development no profiler。🎼We are 19 up to 20， okay， but we are 17。



![](img/d2b281400e0d90c00f492f0adbc6943a_817.png)

And you stay at 17 a lot longer。

![](img/d2b281400e0d90c00f492f0adbc6943a_819.png)

And in the game。🎼あ the game。

![](img/d2b281400e0d90c00f492f0adbc6943a_821.png)

We were like six。Get up to 10。But now we're gonna go crazy， right。 Yeah， now we're like 20。



![](img/d2b281400e0d90c00f492f0adbc6943a_823.png)

S。So we do have to take a look at the bit map。

![](img/d2b281400e0d90c00f492f0adbc6943a_825.png)

That's for sure，This guy out。Let's go back to the profiler and get this guy back in。So。Dude。

 but that was a lot of progress。Expen a bit not transparent， okay， we did that。Oh。

 we didn't do that transparent。Transparent。Then the render。嗯。Insparent rotated racks。This is。

This is what we were doing。And alert color， so I'm going to copy that from the bitm thing you did。

It shouldn't change that much。来。Here， here。嗯。Color alertp with alpha。你呢。

I guess the bi map fully seemed the yeah。I guess the Bimap rule needs somebody。



![](img/d2b281400e0d90c00f492f0adbc6943a_827.png)

That's for sure。Well。Let's see， what was the last number？Yeah， but I think there's no escaping that。

 but that's going to be fun to learn more about that。



![](img/d2b281400e0d90c00f492f0adbc6943a_829.png)

Well， I kind of lost the frame， but that's just。Expand these guys。So we have the pixel source。

And a color is just a color。 Oh， so we can， we can recalculate this guy since its just a。

Solid fill going be this is going to improve a lot of funds， it's going to be cool。

So it's the color RGB， this the pixelix RGB。And I'm gonna。Lerp。These guys around。

And I can also pre multiply this guy， So I'm going to do like。Like a source R。

It's going to be like this。Soce。A， you at this。They're the same thing for。The green blue。Yeah。

 because doing that this guy is the pixel。And we can't pre multiply that。Okay。😊，Go one minus alpha。

 Well， we can't。 we can't see how much is。 So I'm gonna。 Yeah， it's gonna be like in alpha。And oh。

 this should be floats。Right。So， guys， yeah。Often times。This guy I going to do the G and B。金币や。

So and this just be the alpha times AR。In alpha。And alpha。

And this is going to do outside of the loop。B color， yeah， also have to do this。Nice， its going be。

 it's going to be way better。I think so we extract the pixel color。We love that。And then， we。

Combine that then particular。

![](img/d2b281400e0d90c00f492f0adbc6943a_831.png)

But it's kind of hard to measure。

![](img/d2b281400e0d90c00f492f0adbc6943a_833.png)

🎼In the game。We are wrong， though。Oh， and the ball。



![](img/d2b281400e0d90c00f492f0adbc6943a_835.png)

The ball can be a non。Ro the高 wrote one。What did we get the alpha was wrong。Yeah。



![](img/d2b281400e0d90c00f492f0adbc6943a_837.png)

I think they were not rotated。

![](img/d2b281400e0d90c00f492f0adbc6943a_839.png)

🎼That guys has nothing to do with rotation， it was just size。



![](img/d2b281400e0d90c00f492f0adbc6943a_841.png)

The side was wrong for some reason。Let me comment that out。Get this guide back in。



![](img/d2b281400e0d90c00f492f0adbc6943a_843.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_844.png)

Okay， so we did something pretty stupid。Let's see what we did。We get the pixel RGB。We calculate。

Which is like the inverse alpha， which is one minus alpha。Times， DixO RGB。Plus， the source， RGB。

 Okay this。

![](img/d2b281400e0d90c00f492f0adbc6943a_846.png)

けえない。I already think20 way， dude，' 20， 20 way faster。Way， way， way faster。

Like now it's even an accept or even with the huge。O。 now， I should really measure。

 measure like this， but。You're running。A lot， a lot faster I'm going to do like a full comparison after on。

 our bitmap alphaism should be clamped， I don't think it is clamped。



![](img/d2b281400e0d90c00f492f0adbc6943a_848.png)

It's just a bitmet alpha。

![](img/d2b281400e0d90c00f492f0adbc6943a_850.png)

Likeイ？This the rotate rack absolutely pretty correct to me， but if I get。I you guys can see that。See。

😊，If I get like an alpha from the。Let's see。 it's going to go away now。



![](img/d2b281400e0d90c00f492f0adbc6943a_852.png)

So the bitmap。Alpha blending didn't work so bitm。Can you bit that color？Gooditn alpha。嗯。



![](img/d2b281400e0d90c00f492f0adbc6943a_854.png)

Well， that sucked because。I thought。嗯。

![](img/d2b281400e0d90c00f492f0adbc6943a_856.png)

Oh， is that because of because of a。We have an alpha multiplier。Oh， the office calculated。Yeah。

So we clamp。

![](img/d2b281400e0d90c00f492f0adbc6943a_858.png)

And then I going divide that。By the app multiply which。Which goes all the way to I don't know。

 let me debug that。🎼Let's see。No。ちうだけ。It's kind of hard。🎼Okay。Let's stop at the draw bitmap。Routine。

🎼god really excited this。Got a lot done today。呃。へい？Now。Let see you're drawing force field。

And the multiplier is 0。7。Oh， because we have to clamp that。Yeah， I have to clamp the alpha after。



![](img/d2b281400e0d90c00f492f0adbc6943a_860.png)

This。

![](img/d2b281400e0d90c00f492f0adbc6943a_862.png)

I don't know why I stopped de buggy， I thought I didn realize the problem， but apparently I didn't。



![](img/d2b281400e0d90c00f492f0adbc6943a_864.png)

Let me just assert and assert。Alpha。Greater。W are equal than 0， probably could be greater2。

 but it's okay。And alpha。Is last day。

![](img/d2b281400e0d90c00f492f0adbc6943a_866.png)

八ち。All was that or was that a player？Yeah， we do assert。啊。Or was that just a crash？No。

 that was a break point， yeah， that was a social assertion。



![](img/d2b281400e0d90c00f492f0adbc6943a_868.png)

But that was a wrong， because we are optimized， okay， we shouldn't be optimized。



![](img/d2b281400e0d90c00f492f0adbc6943a_870.png)

If we want to debug。Let's see。😊，The alpha is 56， or is the alpha multiply4？So we got。Well。How。

 how much is。Let's see how much we passed the function。

The alpha T supposed to be there is small number， Yeah，0 plus 01。So we are divided by four。

 so bitmap color。What is this guy， 255， you're supposed to draw a full bit map。



![](img/d2b281400e0d90c00f492f0adbc6943a_872.png)

But if we divide 255 by four。看。63。Oh yeah。 Oh， this is correct。 But because this is not。

In the flow scale。But I suppose it should be in float scale。I did like 255 times this。Oh。

 because it's like 250 divided by 255。Okay， so yeah。Ted my math。

 So alpha is the the the like I don't know。Bitmap。Right right，255。看一下。Alpha a called multiply。

So we want to isolate。Like we can do like bitmap times。Dided by this guy， okay。

So that's what we needed， we needed a bitmap。Maybe it's not going to be worried that maybe we're just going to keep that division。

Well， this guy changedd the multiping alpha。Yeah， I'm just going to keep the di there。牛皮。



![](img/d2b281400e0d90c00f492f0adbc6943a_874.png)

Yeah。Oh， but。

![](img/d2b281400e0d90c00f492f0adbc6943a_876.png)

Do we got that slow just by adding the division？

![](img/d2b281400e0d90c00f492f0adbc6943a_878.png)

🎼No， you're like1。

![](img/d2b281400e0d90c00f492f0adbc6943a_880.png)

And we're like 60， Oh， we're not optimized。

![](img/d2b281400e0d90c00f492f0adbc6943a_882.png)

Let's go back。To be optimized。🎼Okay， so like 19。And know like three， that's great。

Why do we have to fix that？We are like three。

![](img/d2b281400e0d90c00f492f0adbc6943a_884.png)

3。1，3。2。Let's remove this guy。Or maybe we should， yeah， we should multiply。

And this guy'm going to multiply by。One divided by 255。Okay， that's the correct man。

So it's just defined right to55， Yeah， I think that'll be right。



![](img/d2b281400e0d90c00f492f0adbc6943a_886.png)

Perfect。

![](img/d2b281400e0d90c00f492f0adbc6943a_888.png)

Perfect。Nice nice nice niceイ nice。嗯。So let's go back to the game。

 we expanded to bid that energy time rotate take pixel calls， did that。

We could optimize the rotate added preamble， I think I'm not going to do that to date。😡。



![](img/d2b281400e0d90c00f492f0adbc6943a_890.png)

I think I'll be for next time， but you know what， maybe this round of optimizations was enough for what we need。



![](img/d2b281400e0d90c00f492f0adbc6943a_892.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_893.png)

For now， at least。

![](img/d2b281400e0d90c00f492f0adbc6943a_895.png)

Let's run a full screen。Yeah， I definitely want to optimize this guy further。



![](img/d2b281400e0d90c00f492f0adbc6943a_897.png)

Just show you guys are number。Yeah。Yeah， you know what's not， I don't know。So。

We are spending five milliseconds on the rotated guys and six on the bitm。

Which means that these guys alone， well， 0。8， right， so these guys alone。I like 12。Miseconds。嗯。😊。

Let's just take a look at the bitnap one more time。So we calculate for every row。The V。

This could be optimized in a weird way because we know how many access we have， we could just offset。

The the。嗯。I don't know。let事。Yeah。

![](img/d2b281400e0d90c00f492f0adbc6943a_899.png)

I suppose we will have to senddy that bitmps。Although we could make。The good cheat。

And make the break。And the out doesnt matter for the break well。

You can make this guy only be a bit mad。是。Thatll be a crazy cheat。You know what？



![](img/d2b281400e0d90c00f492f0adbc6943a_901.png)

I think I'm going to do that。I think I'm going to do that。Just don't tell anyone。

Because if we remove。True remove the bitmap。

![](img/d2b281400e0d90c00f492f0adbc6943a_903.png)

Let's see how fast can we go？🎼Yeah， if can go like to 11。



![](img/d2b281400e0d90c00f492f0adbc6943a_905.png)

But。

![](img/d2b281400e0d90c00f492f0adbc6943a_907.png)

If I make the bitm smaller。I could probably also make that faster。



![](img/d2b281400e0d90c00f492f0adbc6943a_909.png)

And I only need to be honest。The Rcade game。 so I'm going to cheat， I am going to cheat。

 but that's okay because that's a video game， right。

 you're supposed to cheat if it's a single player。Okay。So this is what I'm going to do。

 I'm going to whenever I draw the logo， I'm going to draw text as well。

You the create biotax with then still this text。Okay。And。Go do like， great。好。

And the piece's going to be 0， 30， approximately going to have to have hardcode that a lot。

 and this guy going to have to play around with that a lot in the color。Do you like white。

Just to see where it ends up。Tline center， starting at to zero color。I was just great。Little bit。

 little bit。

![](img/d2b281400e0d90c00f492f0adbc6943a_911.png)

Bigger， a little bit higher。

![](img/d2b281400e0d90c00f492f0adbc6943a_913.png)

Okay， a little bit bigger still。你这个。

![](img/d2b281400e0d90c00f492f0adbc6943a_915.png)

Okay， that was too big。

![](img/d2b281400e0d90c00f492f0adbc6943a_917.png)

And。That was way too big。

![](img/d2b281400e0d90c00f492f0adbc6943a_919.png)

哎，行。

![](img/d2b281400e0d90c00f492f0adbc6943a_921.png)

🎼Okay， so the position is almost perfect。

![](img/d2b281400e0d90c00f492f0adbc6943a_923.png)

But it's。Today。Seeing a lot of time to compile。Okay， we are almost nice I am going to。2。



![](img/d2b281400e0d90c00f492f0adbc6943a_925.png)

🎼To move。Bit， right。And you know what， I think my are is wrong。



![](img/d2b281400e0d90c00f492f0adbc6943a_927.png)

I think the R is not supposed to have the。

![](img/d2b281400e0d90c00f492f0adbc6943a_929.png)

Yeah's supposed to be straight from the left and answer it from the right so。In the。

 let's do whenever see the R。I's supposed to have this one and not have this one。Okay。I's see。

I should also go back to drawing。I't know if it'll look that good。

I think it will I know it a bit smaller。

![](img/d2b281400e0d90c00f492f0adbc6943a_931.png)

64。And also now a little bit to the right。

![](img/d2b281400e0d90c00f492f0adbc6943a_933.png)

Okay， little bit smaller still。A bit more to the right。



![](img/d2b281400e0d90c00f492f0adbc6943a_935.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_936.png)

Okay， that was way too small。 What did I do？

![](img/d2b281400e0d90c00f492f0adbc6943a_938.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_939.png)

I suppose the size is correct now。

![](img/d2b281400e0d90c00f492f0adbc6943a_941.png)

Yeah， it just one。

![](img/d2b281400e0d90c00f492f0adbc6943a_943.png)

Yeah， I can't complain too much。About that， it'll be hard to get a better position。

And then let's do like the menu text colors。And then let's do our array count and text colors divided by two。

Plus1， I think。Too many for the re。

![](img/d2b281400e0d90c00f492f0adbc6943a_945.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_946.png)

But it's inverted。So I'm going to start。At this guy。



![](img/d2b281400e0d90c00f492f0adbc6943a_948.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_949.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_950.png)

Let me see how it looks。By itself。

![](img/d2b281400e0d90c00f492f0adbc6943a_952.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_953.png)

Yeah， I know what， Im going' have to start with this guy plus one o。



![](img/d2b281400e0d90c00f492f0adbc6943a_955.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_956.png)

Oh， actually this guy's wrong， I'm going to do the whole all of them。



![](img/d2b281400e0d90c00f492f0adbc6943a_958.png)

I'm going to start， I'll。 Let's see。

![](img/d2b281400e0d90c00f492f0adbc6943a_960.png)

Oh I think now I got。

![](img/d2b281400e0d90c00f492f0adbc6943a_962.png)

YouGo everything wrong。 now it should start at zero and it should be perfect。



![](img/d2b281400e0d90c00f492f0adbc6943a_964.png)

Okay， I think that's it， let me go back。You you're trying the bit Mac？



![](img/d2b281400e0d90c00f492f0adbc6943a_966.png)

It starts。

![](img/d2b281400e0d90c00f492f0adbc6943a_968.png)

It starts。

![](img/d2b281400e0d90c00f492f0adbc6943a_970.png)

Offset starts like light， not。Okay， so now I should be good to go， let's see。



![](img/d2b281400e0d90c00f492f0adbc6943a_972.png)

Okay， I think I'm good to go， but I didn't want to compile。



![](img/d2b281400e0d90c00f492f0adbc6943a_974.png)

Okay， perfect， but the R is pretty bad， the other R is way better。



![](img/d2b281400e0d90c00f492f0adbc6943a_976.png)

Let me。It was like this。

![](img/d2b281400e0d90c00f492f0adbc6943a_978.png)

ね。

![](img/d2b281400e0d90c00f492f0adbc6943a_980.png)

🎼Yeah， okay， nice， nice， nice， nice， nice。😊，So I'm going to go back to the text。But the colors。

 when I receive the menu colors。I am going to change these colorss。We to do menu dark。

What I'm not going to do。That normally， so I'm going to open the Photoshop logo file。This shows。That。



![](img/d2b281400e0d90c00f492f0adbc6943a_982.png)

You should know know programming really well to optimize your code but。



![](img/d2b281400e0d90c00f492f0adbc6943a_984.png)

You should also do some crazy workarounds when it's necessary， right， I don't know。 I think。

 I think that's fair。So I'm drawing bottom up， right so this should be the first color。



![](img/d2b281400e0d90c00f492f0adbc6943a_986.png)

And let's see if that's the first color。And I'm going to start。It's zero now。メニュー。明。Co dry colors。



![](img/d2b281400e0d90c00f492f0adbc6943a_988.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_989.png)

I think we are good。Let's just remove this lines back。



![](img/d2b281400e0d90c00f492f0adbc6943a_991.png)

That's only you take the dart。

![](img/d2b281400e0d90c00f492f0adbc6943a_993.png)

Okay。But the first one is actually the dark one， so I got the other way around again。

 so this the first。

![](img/d2b281400e0d90c00f492f0adbc6943a_995.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_996.png)

Let's go back to them。C。😊，This is the first。This。third。



![](img/d2b281400e0d90c00f492f0adbc6943a_998.png)

I think this is faster than last time。This the fourth。



![](img/d2b281400e0d90c00f492f0adbc6943a_1000.png)

Right， this。でて。This is the second to last。In just the last one。



![](img/d2b281400e0d90c00f492f0adbc6943a_1002.png)

Okay。Now let's see。

![](img/d2b281400e0d90c00f492f0adbc6943a_1004.png)

How that looks。Perfect again now。

![](img/d2b281400e0d90c00f492f0adbc6943a_1006.png)

Go back to doing it。 if Gu。

![](img/d2b281400e0d90c00f492f0adbc6943a_1008.png)

And I'm going to。I'm going just draw。See it's even not the most optimized guy。

 this really rises like a beginner some。So I'm going to have two versions。And I agree to the tint。

 yeah okay。This would be。First version of the logo。It's the dark one。Yeah。Yeah， now we talking， so。

So transparent PNG。And it would be like。We break out data。干逼。啊。I don't know。啊Logo。Like half logo。今儿。

And then I'll do the half little bright。I suppose I got the other way around。The bright one。Yeah。

 the bright one is the other one。No， I suppose that's right， so half。Half logo， okay。



![](img/d2b281400e0d90c00f492f0adbc6943a_1010.png)

Now let's go back to the game and let's see where we've got the logo with that logo。

 let's duplicate that。Let's make a big mat half flow or d'n a good map。那东。Light。

And let's see where you load that。Also load the hes。Half logo。And now。Whateverever we draw。

 let's also draw the half logos。来。给他 see what你 have。We have a。We didn't get the smart。

 So let's see what is it called。Or did I call it， oh my God， there's so many things opened。

Breakout data。It's half logo light and half logo。

![](img/d2b281400e0d90c00f492f0adbc6943a_1012.png)

Dark。Oh， my god。Okay， yeah， this's probably half logo。所有。Logo， let's see。 I am running。

To get this working before I have to leave。Okay， and the size is wrong。😊，Well。

 this is going to select。 So this image size。Is this guy。And the old image size。どですか。So if we were。

 let's see the ratio。You wrote this guy divide divide by this So it's the other way around， right。

 Oh， I can divide by this guy。87 divided by 620。This guy。



![](img/d2b281400e0d90c00f492f0adbc6943a_1014.png)

This is for the height times over the height。50。😊，Got 2。10。是。



![](img/d2b281400e0d90c00f492f0adbc6943a_1016.png)

Okay， now let's see。It's 11，91 divided by it。This guy。😊，Times。32， 25。



![](img/d2b281400e0d90c00f492f0adbc6943a_1018.png)

28，57。Okay。😊，And see if we have the correct size， we're also going to have to adjust the position。

Double to float， no。

![](img/d2b281400e0d90c00f492f0adbc6943a_1020.png)

That's one of the stupidest sea things。

![](img/d2b281400e0d90c00f492f0adbc6943a_1022.png)

Okay， perfect， just a little bit too high。

![](img/d2b281400e0d90c00f492f0adbc6943a_1024.png)

Well。I'd say that's perfect。Also going to have to do the rectangle and the out。



![](img/d2b281400e0d90c00f492f0adbc6943a_1026.png)

Let's just see， if I remove。The bitmap， let's see our frame read。See how optimized we can get。



![](img/d2b281400e0d90c00f492f0adbc6943a_1028.png)

Yeah， then we got to 12 and 13。 man， that's it。 I am I oh， I have to do this really quickly。

 so let's not stop to analyze it。's let's not celebrate yet。😊。



![](img/d2b281400e0d90c00f492f0adbc6943a_1030.png)

Let's do a draw， on this is going to be hard。To get right。Dirrrect。The屁。Let's do zero。Let's try 0，40。

Zero，28。And the size。That's just an0 20。10。And the colors。我对。Now， this is like really wrong。

But let's make the color different。是。And that's also removed it。For now。



![](img/d2b281400e0d90c00f492f0adbc6943a_1032.png)

Okay。

![](img/d2b281400e0d90c00f492f0adbc6943a_1034.png)

Now way too wide and way too tall。

![](img/d2b281400e0d90c00f492f0adbc6943a_1036.png)

🎼Okay。

![](img/d2b281400e0d90c00f492f0adbc6943a_1038.png)

Let with it down， let's make a little bit wider。Let's move that。2。Okay， but I can't see。是啊。

It's very just rotated direct。Okay。后面。So have size angle。Alpha mode。Rightい。Thats angle。

Offfer multiply your angle color。

![](img/d2b281400e0d90c00f492f0adbc6943a_1040.png)

So it's 2。5。

![](img/d2b281400e0d90c00f492f0adbc6943a_1042.png)

Okay， that's that now let's make it a little bit less wide。And that's due tall who's doing 3。5。



![](img/d2b281400e0d90c00f492f0adbc6943a_1044.png)

Let's move down a little bit。

![](img/d2b281400e0d90c00f492f0adbc6943a_1046.png)

Okay， almost perfect。LetSpring that a little bit up， so 21。To tall still。你会坏。オッケー？真好哦。



![](img/d2b281400e0d90c00f492f0adbc6943a_1048.png)

Okay， a little bit down。

![](img/d2b281400e0d90c00f492f0adbc6943a_1050.png)

It last wide。

![](img/d2b281400e0d90c00f492f0adbc6943a_1052.png)

ALittle bit up， a little bit less wide。

![](img/d2b281400e0d90c00f492f0adbc6943a_1054.png)

It'll bit up。

![](img/d2b281400e0d90c00f492f0adbc6943a_1056.png)

ALi bit last slide。I think that'll be good now。

![](img/d2b281400e0d90c00f492f0adbc6943a_1058.png)

Yeah， that's good， I do the outuch。The last thing we have to do。Oh， man。Out。

And I just copied of things from break， but let's make that。Myケ。首先生。

This should also just like correct。And I'm going to do like a color。Turn that light on。Okay。

Text color。Lets see what's the text color。です。So， sketch of color。One color start to seau。テ time。



![](img/d2b281400e0d90c00f492f0adbc6943a_1060.png)

Okay， has be a little bit smaller。Color。

![](img/d2b281400e0d90c00f492f0adbc6943a_1062.png)

Let's see。 Let's see。 Let's see。嗯。

![](img/d2b281400e0d90c00f492f0adbc6943a_1064.png)

Let to remove this guy for that。

![](img/d2b281400e0d90c00f492f0adbc6943a_1066.png)

Okay， the out is different， the O has to be 100%。

![](img/d2b281400e0d90c00f492f0adbc6943a_1068.png)

Squared。Okay。😊，And I was too big。

![](img/d2b281400e0d90c00f492f0adbc6943a_1070.png)

7。

![](img/d2b281400e0d90c00f492f0adbc6943a_1072.png)

Okay， it's okay if you'm going to move center that， move a little bit up。



![](img/d2b281400e0d90c00f492f0adbc6943a_1074.png)

I think thatll be a bit easier。

![](img/d2b281400e0d90c00f492f0adbc6943a_1076.png)

It' too big。Just a little bit。Is that the out I do like？



![](img/d2b281400e0d90c00f492f0adbc6943a_1078.png)

2，5。

![](img/d2b281400e0d90c00f492f0adbc6943a_1080.png)

Oh， make， I made it bigger。

![](img/d2b281400e0d90c00f492f0adbc6943a_1082.png)

What？😮，What happened？

![](img/d2b281400e0d90c00f492f0adbc6943a_1084.png)

You know what。I may just call that a day。Let's just do the same thing。But the out。

We'll be see what color it's pink right yeah。屎。And now that's removed。This guy。



![](img/d2b281400e0d90c00f492f0adbc6943a_1086.png)

This is the， the heady guy。

![](img/d2b281400e0d90c00f492f0adbc6943a_1088.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_1089.png)

Okay。Okay。😊，We managed。We've managed to get that back。To get that back no。

 to get like working at all at。

![](img/d2b281400e0d90c00f492f0adbc6943a_1091.png)

16 frames per second， so this is the story of today。This is like the thumbnail is like。



![](img/d2b281400e0d90c00f492f0adbc6943a_1093.png)

The victory that we achieved。So we started out。And yeah， we started out。

With a menu at 66 milliseconds per frame and finish at 12。4 milliseconds per frame。I don't know， man。

 I think we can just go home。Celebrate， I do have to leave that。So。

I'm going to save that for like more optimizations。And let's say that we worked on that。

And now at this point， I should probably like lock。Frame rate。Possibly。

Then we go back to the level thing， so make full screen pre。The screen lounge。



![](img/d2b281400e0d90c00f492f0adbc6943a_1095.png)

It点。So that is it part today date， everybody。

![](img/d2b281400e0d90c00f492f0adbc6943a_1097.png)

It's not like 100% standard。🎼I'm going to move that right。😊。



![](img/d2b281400e0d90c00f492f0adbc6943a_1099.png)

Oh， because I suppose yeah， no。I could just move a little bit， right？Mu， the out。

Move that right like。Okay。😊。

![](img/d2b281400e0d90c00f492f0adbc6943a_1101.png)

Okay， this wasn't the longest live stream we did yet。This was the longest one。

But I think we did so much stuff， we learned a lot， it was really a lot of fun。

 I hope you also enjoyed this。If you want to watch the whole development process from the very first pixelel all the way through everything we did。

including now which was optimizations that's like real optimization I think that was pretty cool we got that we got that running so so much better just for you guys。



![](img/d2b281400e0d90c00f492f0adbc6943a_1103.png)

So in the beginning of today， it was running at 66 milliseconds per frame， and as was running at 12。

 milliseconds per frame。We managed A， let's see。5。3 times increase in performance。

 I guess it're running five times better our menu。And the game is also running pretty nicely as well。

 now it can pretty much play at 4K。

![](img/d2b281400e0d90c00f492f0adbc6943a_1105.png)

I like。😊，Great。😊，And we can still like improve a lot。Yeah， dude， this is perfect。 This is perfect。

 So I'm gonna have to finish the stream right now really quickly， but if you want to follow along。

 you can subscribe my YouTube channel， which is YouTube dot com s Dan Z Dan。

 You can watch the whole thing from the very beginning all the way to where we are now。

 And you can also download the source code for free and play around with it on my HO。

 which is Dan Z do H do Io。😊。

![](img/d2b281400e0d90c00f492f0adbc6943a_1107.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_1108.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_1109.png)

![](img/d2b281400e0d90c00f492f0adbc6943a_1110.png)

You can download the whole thing， all the episode source code for free and the episode as well。

 you are welcome to give me a tip。

![](img/d2b281400e0d90c00f492f0adbc6943a_1112.png)

If you come here， but you can just we can know thanks and that's it， I'll see you next time。

 thanks so much。

![](img/d2b281400e0d90c00f492f0adbc6943a_1114.png)