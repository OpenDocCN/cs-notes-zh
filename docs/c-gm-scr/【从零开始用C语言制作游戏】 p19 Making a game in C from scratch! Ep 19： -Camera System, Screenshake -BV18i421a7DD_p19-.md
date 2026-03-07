# 【从零开始用C语言制作游戏】 p19 Making a game in C from scratch! Ep 19： -Camera System, Screenshake -BV18i421a7DD_p19-

Hello， everyone and welcome to this new live stream where created an entire game in C from scratch。

 the game is you know getting complete， to be honest。😊。

We have come a long way from the first line of code that we wrote all the way to where we are now。

 in fact， let me just check out the lines of code。We have written so far。miss事。

Because I think we did。We did write quite a few， actually。A couple thousand maybe。Well。

 it was taking a long time， so I don know what。Okay， get work。呃。Yeah， okay， there you go， so。

This is not our our code， this is the library use for an image， so this is actually our code。

3000 lines， 3。2，000 lines of actual code。Plus like nine， if you had blank lies in the comments。

Probably， like。4 and a half thousand。It would be less。4500。

 4300 lines of code as pretty decent to write everything on stream。

And currently on the image library， we have almost 10000 lines。 You can watch the whole thing。

 every line of code that we wrote on my YouTube channel。 if you go to use dot com s Dan z Dan。

 you can watch from the very first episode。all the way to where we are now， we are。

 this is episode 19， so there were 18 episodes up to this point。



![](img/7d44c52568183ee28453dce79ee0ef2b_1.png)

And you can also download the game for free on HIO and the source code as well。

And someone asked me to add a license to the game。And I wanted to make that as permissive as possible。

 so it's dual license into the public domain and like you're granted a right to do whatever you wanted。

就。There you go， can download and do whatever you want with it。And when you click download now。

 you are welcome to give me a tip if you want to， but then you can just click no thanks and then you can download each episode's source code all the way from the first episode all the way to where we are now and where are we you may ask。

 well， let's see。

![](img/7d44c52568183ee28453dce79ee0ef2b_3.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_4.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_5.png)

Let me play the game here。

![](img/7d44c52568183ee28453dce79ee0ef2b_7.png)

Do you hate yourself what the resing you're using C Do I love myself， that's the reason using C？

See is。A very fun language， to be honest， very simple one。

 not many things to consider whenre reading compared to C++ and we are doing from scratch。

🎼And we are very， very perform， we wrote the software render。🎼You see from scratch。And the。

It iss running like at 4K。

![](img/7d44c52568183ee28453dce79ee0ef2b_9.png)

Well， I should probably feel that。Optimized build， right？So when I'm building an optimized build。

 which's what we should do。

![](img/7d44c52568183ee28453dce79ee0ef2b_11.png)

It's running at a 60 framech per second lock。So we're running way faster than that at 4K。



![](img/7d44c52568183ee28453dce79ee0ef2b_13.png)

So。Yeah， and it's also awesome to learn things like that。



![](img/7d44c52568183ee28453dce79ee0ef2b_15.png)

Okay， so this is the game I have so far it's a breakout game。

 it's called break Arrcade Games Out it's a pretty bad name I think many of you guys have any name suggestions？

I like the sound Thanksgiving's been moving yeah。It was pretty hard， you know we。

But we did manage to get a pretty decent sound mixer that we can change the pitch of the sound as well as the volume pretty easily now as well as make it a stereo。

 which is pretty cool so it starts out as a normal breakup。い。🎼So this is the first level。

 which is just break count。then have breakout with power ups。

This was the very first idea that people gave on stream。M Cl Ar。Okay， I got strong blocks。

 so now blocks are infinical and it's。🎼So then。We made what the game was actually about。

 which making old games like breakout so this is Pung。🎼Playing as if it were breakout。🎼简样子笔。🎼ううん。

And I think this is pretty helpful。🎼Ill keep strong log in there。And then you have Tetriris。

 which is the one that we did last time。あ。🎼这好。すごい？🎼今年了。I had another idea for this game mode。

Which is to make like the women it' a pretty quaint hit yeah， and if I mentioned the shot yet。

 this guy， now they're going to start。The new challenges like this guy can drop like R downs。

🎼So I have to avoid those。🎼The sameme time as trying to get them。Yeah， there you go。

In I have about two blocks of plants。🎼Okay。🎼ま。🎼何厳中です。And I have rotating blocks， all crap。Yeah。

 its maybe a little bit too hard， I think。Uh， but I have another idea for the typeless one。

 which to make several smaller pieces that you only have to hit once。I may add that。

 Im not sure I'm going to add that。Before。🎼Probably in the very end。

After you destroy the rotate piecesis。So that's one of the to do things cea。

Maybe also change the speed a little minute。Is it at this point？Scrprinting possible。I't know。

 I have to do some balances again and the Space invade one， which is really cool thing。Yeah。

This one's the best。3 life。So that's the point where we are now。

 the plan just to make you guys aware of the to do thing。



![](img/7d44c52568183ee28453dce79ee0ef2b_17.png)

Oh， yeah。 that's the idea for indicators makes a smaller shape that use the neighbor system。

 So you only't have to hit them once。 So I'm going to。I want to know that on the game。

I'm going to note that as another idea。We did the ts one。你啊。

Tetris makes smaller shapes that ecosystem so。10。try one。



![](img/7d44c52568183ee28453dce79ee0ef2b_19.png)

Okay。Now the plan is today we should redo the collision because there are a few weird cases。



![](img/7d44c52568183ee28453dce79ee0ef2b_21.png)

That theia is not 100%。And we definitely want to fix that。

 I mean it's kind of hard to reproduce that's the biggest biggest problem。hard to reproduce that bug。

But we are going to take us special care on the collision today。And hopefully by the animal have。



![](img/7d44c52568183ee28453dce79ee0ef2b_23.png)

A more robust system。It would also improve the field a little bit like screen shake， menu， stuff。

 transition， that could be cool。Which was the size of the player role condition so in case its like。

This one。Increase our size， I'm moving my mouse to the left so I should also move him to the left。



![](img/7d44c52568183ee28453dce79ee0ef2b_25.png)

The the square。Do I have a sound。And then maybe we can increase the test。

 maybe we're going to leave this for the next stream。

 its maybe going to be too much so at this point when we finish this guy， we will be left。

Maybe with more gameplay exploration， not sure， though， because we did a lot of gameplay today。

 not today， I mean， already， and I don't want this to be a super long stream。

 We're going to spend hours and hours of gameplay because you guys got the idea， right。

 He could go all crazy on all sorts of weird game modes。😊。



![](img/7d44c52568183ee28453dce79ee0ef2b_27.png)

And get more out of the game。Its probably what I should do。

 but since I'm only programming this game on a stream。

 I' not sure this would be the best call to spend like hours and hours and hours playing around the gameplay。

So I think I'm going just to finish these five levels。Iprove them。

And then we could do the polish pass， which is make like the full screen launch prettier， well。

 let see。

![](img/7d44c52568183ee28453dce79ee0ef2b_29.png)

Yeah， on the nondevelop build。More optimizations， maybe not sure if I we're going to need're running pretty closely make an async audit so we can get the。

The data size down right now， our data folder is like 50 is like a 25 megabytes。

 the music alone is 14， the sound effects。Are like 11。

 so if we make like an OGG vus reader or a use one， we're probably going to use a library for that。

We can。We can get that data further way down the size。Save and equipped。I'm not sure though。

 if you're going to need that because we are already saving every time we need to。

N the cooker to cook the assets that will go along with the OGG reader。

That could be pretty pretty nice and that's a cool thing to change that'll be a nice challenge。

The acid cooker like acid cooker。Nake returned the player's mouth， yeah， and some smaller things。

Yeah。And the game and test is at lower terms。 Yeah， and after we do this。We should be able to。

To launch the game。And。I going'll share it with you guys because。

I think I'm pretty sure that I'm going to release this game on this team as well。

So that'll be a cool thing to do， I can't implement the steam API on a live stream。Unfortunately。

 but I can。Show my API distraction layer I suppose， so I'm going to do that。And then we can release。

Yeah， that'll be it。Online subsystem。And then release。



![](img/7d44c52568183ee28453dce79ee0ef2b_31.png)

And we're going to leave these guys for like next games。Okay， these other ideas that we had。

So that's the plan， so let's start now we're going to break the game pretty pretty badly today with a collision。

 but I think it'll be worth it because that's one thing one important thing。

That I should say is that when we start start the collision day two。

 as you can see even the name of the video is like。

Gameplay epic collision failure and epic collision success。 Well， as you can see now from the future。

 it wasn't such an epic success because we are having to review the collision system。😊。



![](img/7d44c52568183ee28453dce79ee0ef2b_33.png)

But the thing is， when we first wrote the collision system。

We weren't 100% aware about where to fit it perfectly。So we didn't want to spend like a lot of time。

Perfect it as of now， since we are getting， know the polishing done。

 getting the gain down to its release state。

![](img/7d44c52568183ee28453dce79ee0ef2b_35.png)

We can focus a little bit more on making the grocery perfect。

 so now we can go back with a way better， I don't know， condition， I should say。

To go ahead and review the gl system。 Okay， so we ended up using a sweep。

 We just like we have the ball position and the desired ball position。😊，And we have like blocks。

And we can test。Whether or not the ball collided with like this guy and if it did。

 we can move the ball back to where it should be like。At this point。And then destroy the block。

And then change the ball direction。So that's the basic thing， we are doing this。Now the problem is。

There are some tricky situations like if you have like three blocks like this。

It'll be cool for you guys to see that the problems aren strange dating。



![](img/7d44c52568183ee28453dce79ee0ef2b_37.png)

But last stream。Last stream you could really see goes probably a couple times。

Even it was like a almost looked like a ball went through or one block。

Whi has to do with the way we are， which I looked the Con before。

 which has to do with the way we are。The way we are processing the collision， right。

 so that's one of the biggest things that we have to change today。はい？



![](img/7d44c52568183ee28453dce79ee0ef2b_39.png)

Okay。😊，The idea is， let's say we have the ball。O。😊。

And let's say we have a desired pe based on the ball deepp， so the ball wants to go here。ok。😊。

So the the main thing starting out， just like I said now， the thing is， the ball is the main thing。

 It's not the block。 So right now， our collision， let's say， collision。😊。



![](img/7d44c52568183ee28453dce79ee0ef2b_41.png)

Our pollution is being made， see。On the blocks。And then we iterate through all the balls。



![](img/7d44c52568183ee28453dce79ee0ef2b_43.png)

I're going to do the other way around，m going to do for each ball I'm going to throw the blocks。

And just。Note on performance。We are running like in 4K， let's say， something like this， right？

No it's 20386。3 I know。The size of a 4K display， but it's over 8 million pixels。



![](img/7d44c52568183ee28453dce79ee0ef2b_45.png)

So we are running a few。To things like our arranger。And it's not like trivialle things。

 we're also doing like draw。That was。Our fault， rhetoric？😊，In our well。

 we are drawing with suff accuracy， some things。We're enjoying Bnap。

 so we're doing like texture fetching。And。And sampling for every pixel of the  eight million ones。

 where not everyone have。Textures。And we're also doing like， I'll delete this guy。啊。

This was one of the ideas that we could make that password。And we were doing like the rotated guys。

 every frame as well。So we don't really care about performance in this point。A。For this thing。

 because we're iterating like through， I don't know， 300 blocks。



![](img/7d44c52568183ee28453dce79ee0ef2b_47.png)

A couplele times for each ball。 so going back so for each ball。

 let's go through the blocks and see if they collide if some of them， if like one collide。

I'm going to calculate in no position。And this one's going to be the old position now， see。

 I'll make this one。Yeah， then I can destroy this block。



![](img/7d44c52568183ee28453dce79ee0ef2b_49.png)

And then I'm going to read through all the blocks again， like we implemented that last time。



![](img/7d44c52568183ee28453dce79ee0ef2b_51.png)

But this's the thing。ok。😊，And。Yes。😊，Yes， exactly， so this is the collision point。

And this not like we should advance。Based on that collision。



![](img/7d44c52568183ee28453dce79ee0ef2b_53.png)

Okay。😊，So。Let's do a few things， we simulate the block for the level。

This may change like the position。So I'm going to change this。Before we do the ball。Update。

So first thing you're going to like update。The blood position。Okay， then the balls。

 and then right here I can do the。包。来可一性。Okay。😊，And。

Probably think the first thing you should do is the simulate level。It's just。Go to the level。

Let's see what we do here。 Yeah， we update the position。Yeah， so we simulate level。

 you update the blocks， and the balls。And do the player collision of the ball and the player collision well。

Where're the player？Probably have to be the player first。Yeah， we arguing doing the play first。

 the play we were doing， yeah。Up here， it's not dependent on the game mode， game， yeah。

 the game mode。Okay， so。After we do the ball block collision。

We can start doing the rendering because everything is done as suppose everything simulation like。

 so we're going to go through other blocks again。We collided now。Think about this now。Oh。

 so we are doing that again。Oh no， this is like， oh， yeah， okay， so this is in the actual collision。

Yeah， this condition that you gonna change。给。So this is what we're going to work on now and they then have the first field。

Rinery。And then we draw the blocks。Blocks and they have updated power blocks probably we also updated power blocks。

Well， it doesn't even matter。嗯。Yeah。And then we ran the particles and the balls and the walls and the hut。

Okay， this looks okay， so now we remove the collision。



![](img/7d44c52568183ee28453dce79ee0ef2b_55.png)

So now we should have no whatsoever。With the blocks。We don't。

And the challenges to air collision back。🎼In a way that it's way more robust。



![](img/7d44c52568183ee28453dce79ee0ef2b_57.png)

对。Pretty cool。Let me just pull this up here so we can。For reference， so for every ball。

I'm going to go through every block， oh if it's not the first block movement， right， how to do that。

So I'm going to go through every block。And see if there's life in the block。Okay。😊，And yeah。

 we do have this do ball block collision and let me show you what this is。We take a ball in a black。

And then we do the sweep。Based on the ball desired P and the ball P。Okay， so these are the。

These are our main variables， right？And the DP。And they have signs， okay， yeah。

So we've got a collision point。Yeah。Okay， and then return true if I collide it。

If I actually destroy the block honestly。Yeah。If I describe the block。Well。

This shouldn't be if I destroy the block。Just collided。So even we've provided with a strong block。

We should return to your like。At this point。Can I false。



![](img/7d44c52568183ee28453dce79ee0ef2b_59.png)

But I'm not sure we should return。Also。Because for instance， if we return。When we。Yeah。

 this means that we're going to change。Just one side， I suppose。



![](img/7d44c52568183ee28453dce79ee0ef2b_61.png)

Yeah， I can return， I'm actually going to do like here。Result was false。

Because if you should collectllide the ball。In two directions。

 which probably changed both directions。That's one of the problems the collision is one of the reasons the collision is feeling a little bit。

Unpredictable， which is like。Totally not the way should feel， right。Okay。Okay， now forever。

For every ball。I'm already checking if it's active， right？Yes。😊，几。😊。

And then I'm going to do the collision。Okay， and if we collid it。T all the blocks again。

 and then we have to update the ball properly here。So we're going to review， yeah， the desired P。

 we're also going to change the P。But the idea is you go back through all the blocks， right。

 blocks equal blocks minus1 and we break。Well don't need to break but。I break anyways。No。

 this is wrong， man， that's really stupid。We are breaking out of the loop， oh。

 because this is like the ball loop， okay， so yeah。AtThis point we don't need to break。

 our need to do is to set。The ball back to the first ball。

 And then we can do all the tests again because now you may have passed through this ball。

 but now we want to check it again because the position has changed。 Okay， so this is a new basic。



![](img/7d44c52568183ee28453dce79ee0ef2b_63.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_64.png)

For that。But a bo block collision。But now let's review what happens when we collide， okay。

 so when we do collide， increase the ball size， we set the Dp to the lup。On the。Theyre DPY。Okay。

 so this is the new， this is disposition， right？No， the， this is the P。Yeah， from the， from the P。



![](img/7d44c52568183ee28453dce79ee0ef2b_66.png)

To the D P， to the desired P， we have the。We have the collision point， which is TY。



![](img/7d44c52568183ee28453dce79ee0ef2b_68.png)

At this point， we collided surely also set that on the x for some reason I'm not setting that on the x。

 the target X。I that correct？不要。Before we go around and mess with this thing。



![](img/7d44c52568183ee28453dce79ee0ef2b_70.png)

We should have basic condition back so then we could go ahead and make that a little bit more robust。



![](img/7d44c52568183ee28453dce79ee0ef2b_72.png)

Yeah， we do have。This is pretty much what we had。

![](img/7d44c52568183ee28453dce79ee0ef2b_74.png)

You much what to be had at the audit， okay， but we can do。



![](img/7d44c52568183ee28453dce79ee0ef2b_76.png)

A got a job， so this is the thing that we wanted to do we want to put the ball here。And then。

 continue the collision。Testing like from other frames。



![](img/7d44c52568183ee28453dce79ee0ef2b_78.png)

This new position， so we have to calculate that。

![](img/7d44c52568183ee28453dce79ee0ef2b_80.png)

So。You can also do like more robust things。You know， this may be the problem， I'm thinking。

 I think this is a problem。Yeah。You know what， we're going to change the collision a little bit more。

Let's say we have two blocks like this。And the ball is going， well。

 since we are updating the blockss like bottom up，'s like the ball here。

 so the blog is here and it's a super fast ball it wants to get here。Yeah。😊，Yes， exactly。

 in this case， I think it's going to work in this case。We were going to simulate this block。

Youre going人 say，ok， oh， co， so。We should move the ball here。

And if we do what we said we're going to do。We're going to move that up。

 so it's going to collide with this block， so it's going to move down。So when you finish the frame。

We would have moved， we would have ended up here moving down， having to these two blocks。

It's really weird。In the correct simulation， we should end up like here。

Or maybe you feel faster than up like here， right， because we we crcheted off and move up， all right？



![](img/7d44c52568183ee28453dce79ee0ef2b_82.png)

And it's right just one block。So we can't just test， we can't just set。

We can't just set our that yeah。We can't go here， we can't just set。The new position here。

Because all this means that wecollled with this block， they just need that we collided。



![](img/7d44c52568183ee28453dce79ee0ef2b_84.png)

Because it doesn't mean that this is the first block we highlighted。オッケ？



![](img/7d44c52568183ee28453dce79ee0ef2b_86.png)

So。嗯。I like the ball baseball here when you set the pee to the ball peep。We're going to do this here。

The very end of the update call， thing。ButInstead of just setting that to the desired P。

We should probably do alert， right， probably do like this alert here。

The ball pe is going to be where it started。Well。If we didn't collide， it should be one。收入。



![](img/7d44c52568183ee28453dce79ee0ef2b_88.png)

This should be one if we didn't collide。But if you collide it。

 should be whatever the value that we collide with。



![](img/7d44c52568183ee28453dce79ee0ef2b_90.png)

I'm going to call this， like。Man tea。 So it's the smallest tea， right。

And we're going to start with a mean tea。

![](img/7d44c52568183ee28453dce79ee0ef2b_92.png)

20啊。So the smallest collision is like the end of where we want to go。 Okay， it's the first step。



![](img/7d44c52568183ee28453dce79ee0ef2b_94.png)

Now， then we're going to check the ball collision passing the ball the block and T。

I pass a block right maybe I should inline this again。Yeah， I think I'm going line this。Well， no。

 not yet。Let's pass now the or we do have the ball。So' I'm going to save like。I shall I do yeah。

Block， like block， hit block。Okayケ？😊，And they we're going to pass it。Okay。So， now。

What we do is whenever we try to collide， we receive。Should be a pointer right， A pointer menee。

The man tea。Actually， this is to be appointed to appointment because we want to change the pointer。

And the hit blood。K。Now。We calculate the difference between the desired P and the ball P and calculationtic point。

In this case。We just like whether or not we should test with the upsider or do based on the DP。

And then we get。The Twi。So if the Ty is greater than zero and less than the min。7。😊，嗯。Yep。

Then instead of doing this。Well， yeah， stop doing this。if zero this whole thing out。

Start doing this I'm going to set the min。T， the TY。Oh， Ash。Okay， this is wrong， actually。

 this is just test。This is to test the exposition。Because the exposition here have to see if we are in the range。

 right， so this is the test， so we do have to do this。So。Yeah。So yeah， this is the extraroppo。

 So now we increase the ball size， we set the desired P speed multiplier if we need to。😊，Yeah。

So at this point。We're going to set them in tea and set。The hit block。To the block。Actually。

 we should have a mean Y and mean X。

![](img/7d44c52568183ee28453dce79ee0ef2b_96.png)

Because like here I're in the X。

![](img/7d44c52568183ee28453dce79ee0ef2b_98.png)

Yeah， and we also change our mean wide， yeah。Me mean X T mean T X。M t外。Okay， I like this。

 I like this。😊，In T x and N T Y， and this is going to be the target x。

 where I can call that Tx then way didn call x。T X。Okay。The Tx and this set the hip block。



![](img/7d44c52568183ee28453dce79ee0ef2b_100.png)

To the block。And let's see。We call out of the block。



![](img/7d44c52568183ee28453dce79ee0ef2b_102.png)

And maybe now we are safe to return。Yeah。😊，I think this is correct。You're going to get false。Yeah。

 I'm trying the results too。Now， same thing hearing about an if zero that out。If this guy。

 then I'm want to do the same thing。Okay。😊，It's going to be pretty good， I think。Now。

 we have to take the mint。X。And all the mean T， I。And mean Tx。Same thing here。Andto X。年纪管。Okay。😊。

And this should be the mean TY。And this should be the men。Yeah。MT X。Then we call that。Okay。Okay。

 nice。Let's see NNtyY undeclared identifier。Mee， okay。So。Oh。So actually， this is wrong。This， yeah。

 I wish， yeah， I don't know what I was thinking， and we only need one。Which is the mintee。



![](img/7d44c52568183ee28453dce79ee0ef2b_104.png)

Yeah， because we're actually going to lur with that that are're I going to。



![](img/7d44c52568183ee28453dce79ee0ef2b_106.png)

Get that value individually。Yeah。Yeah， because the de T， yeah，'s not this is actually right。

This is actually the target。Or maybe I we'm going to call that at y， Yeah， which is like。

What's the value of y in the point where we are at see， So now we're not going to set that to the y。

 we're going to set that to the Tx， now we'm going to set the X we're going to set here to the y。Yep。

😊，Yeah， I think this is what we want in the first place。Okay。😊。

Now we have to pass the correct things here。Yeah。Okay， can I convert V3 to V2？So yeah。

 the love's going to be a whole thing， oh， it's going to be way better， I think。

We have a little bit tube。 I don't。Matrix， random。B就 eye。Thank you。Okay， so learn to be2。

Go to return。This guy。And then we can。Okay。Okay， if you guys have any questions。

 be sure to drop them on the chat and I'll try to answer it。Okay。😊，I's see。 we compiled。

But I do want to， well， we haven't finished right the call yet， Okay， so well。We at the minee。

Did this guy it？That they hit black okay。啊。Yeah， this is what we want to change if we collided。

With a block。Actually。No， this is wrong。This is wrong now we're not going to do anything if we collide it。

Yeah， this is going to be perfect。I going to do anything if you're collided。Okay。而。Because actually。

 we do know if we collide it， right， which is if we have a。哎呀。E valid。Okay， and the thing is。

 when we finish loop。Here。嗯ん。😊，You can just set absolutely。The case。Where we don't try col， okay now。

Let me see if I hit with the wall。I said the desire to P。 I should also change the P。Yeah， so。Yeah。

 I going have to review this also， but this is the best idea。If we finish and we hit a block。

Now I can do this。In case， if we hit a block。What are we going to do first of all？

We are going to destroy the block at this point。So yeah， yeah。

 we're going to do actually this whole thing。Like。😊，Okay， nice， let increase the ball size。And well。

 this is what we have to rethink。We're going to change the pulse speed multiplier。

And we're going to check。If the ball has a strong blocks。Then this case is the hip block。

It test it has a life。愿咪。Let's try the block。

![](img/7d44c52568183ee28453dce79ee0ef2b_108.png)

Okay。😊，Now。We're going to set the P P。

![](img/7d44c52568183ee28453dce79ee0ef2b_110.png)

Which is the no starting point。Yeah。The P is going to be the result of the。ok。



![](img/7d44c52568183ee28453dce79ee0ef2b_112.png)

Yeah。

![](img/7d44c52568183ee28453dce79ee0ef2b_114.png)

And then。诶 p。And this would be the mean。T alert。Feature。ok。And well， we have to know the direction。

 though。Because here。We copied。Yeah， I'll this guy。In this case， let's see what we do。

 We increase the ball size， change the spin multiplier。You the。And yeah。

You I have to test the comment。So， I'm going to。You like。😊，col诶 condition。I分。Re fly。To the bed name。

Yeah， so if。Collion happens with why。Else， this is what we're going to do。 change the bowl。EPX。

 so if we hit the X， all I'm going to do is change。The X， if we have a Y。

 we're going to test this whole thing。Ball DPY。Change the comment and reverse the ball， DPI。

 or else you're going to do nothing。2sses ball okay。I think this is like we the block life。

 it's going to be a way better thing。Then we can probably， yeah。

You could probably in line here as well。Let step for the time。Okay， so at this point。

 we can set the ball。

![](img/7d44c52568183ee28453dce79ee0ef2b_116.png)

P。吃的留肝。Just here。

![](img/7d44c52568183ee28453dce79ee0ef2b_118.png)

Okay， and then we can。Do this again。Yeah， we can move the ball again。呃。

And then she should probably have to test the whole thing。Let's see play with ball。

Because it could hit a wall。And yeah， at the end， the are it's not really light and updates sound。

So this we don't want to do twice。But， you know， this， I think I'm gonna。

 I'm gonna make this thing down。 I do the ball。The Raer ball。Because this is more like static thing。

 not gameplay related。So it gets like the notice values are when we get a block。

This is what we'll do。Okay， yeah， this looks a little bad。

 So I think we' going have to run the this whole loop。Lets I of changing the DT。

I'm also going to change。I'm going to do like something like。V DT。开四。W。mount。目咁嘛。

So we started out as zero。Movingve it amount and then the Dt。

 so I're going to multi that by one minus the ball moving amount。K。😊，Oh， you know what？

Go me drop this guy in here。I'm gonna to do like a while。W move amount is less than one。

' going to run this whole thing。This is going to be pretty good， I think。呃。So。

So start updating the ball and we want to move one。From zero to one。

 so while we still haven't moved to one， we're going to set the desired peak。

To be the he1 minus whatever， right， how much we have left in our movements。Okay。

 then we do the player bulk collision with player with the wall with the other wall。

We check the end of the arena。We the yeah， and the block collision now。In this case。

 we're going to set the P to this new guy and we updated whatever you need， I think we can do like。

so you change the ball， the block。Thanks。😊，We change the ball size。 you change the ball speed。

 which's going to be pretty cool。We change the collision depending on whether or not it happened with Y。

 which I'm going to have to know down here。So do collision player， let's see。

Coll lesion happened with why。And I happened with why。特别先。Happ with y equals  three。If it happens。

Okay， so no need to do this。I think we are going to go to a good shape now。Its the hip block。啊。Okay。

 update sound。She said we don't update sound。If we collectllide。With the top arena。And the ball。

It's not active。Oh， because。Yeah。Well， good。It should be toldwed。the boss's not active？Any more？

It's not even going to run this guy。 So this is going to be pretty cool。Yeah。Okay， I like that。

We do have to be careful， though， because it's going to break a lot of things。



![](img/7d44c52568183ee28453dce79ee0ef2b_120.png)

But this's going to be a pretty robust collision system， I think。

 that we can utilize on other games and this knowledge also。



![](img/7d44c52568183ee28453dce79ee0ef2b_122.png)

And let me put that comment here just。Okay， and now I set the bulk P which is the new starting position。

Seend the new starting position to the ball pe Minty， okay。继谢。It didn't happen with why did we be？ok。

😊，And then we should run through this while and check again。I like。I like this。Let me。

 let me put it deep up。Breakpoint。Whenever we hit a block hole。



![](img/7d44c52568183ee28453dce79ee0ef2b_124.png)

Game line 437。

![](img/7d44c52568183ee28453dce79ee0ef2b_126.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_127.png)

So， yeah。嗯。Got a problem with a sound， and guess was that sound？It's weird。

And see which sound are we trying to play or probably。To debug mode。Again。7。

Return your volume down because that was a very unpleasant noise。Yeah。Okay， so sound。

It is a lose life。Sound。That's weird。That's for a great point in the play sound。Sorry。

 I would play all the initial sounds。There are a ton of initial sounds。Okay。You're supposed to play。

The start game sound looks good。To lose life， who's trying to lose a life？Lose life。

Ball reached the end of the arena。So probably this calculation is wrong。Move amount is zero。

 so it's going to be Dt。Times1 minus0。啊。Yeah。Why didT out。So， the ball p。0。

45 are about desired pay is 0 minus 50。응。I don't know this is it right I I assume the ball was supposed to be going down。

 What' the ball Dp。It's-50。So。Yeah。Okay。Trying to move the ball。Which is the first ball， right。

 D 2 d，0，0， yeah2 d0。DT is 0。016 bubble to  zero， so if this guy should be the end this is correct。

Our ball D P is-50。Yeah， this correct're supposed to be going down。This is 40， okay， positive 40。

So we're just a little bit down。Looks， this looks's pretty correct now。

don't collide it with anything， very you care。Or the end of the arena。差里。Yeah。

And it's the first level event， Okay， so this looks correct。Let me remove that break point。

 but let me just put these variables。

![](img/7d44c52568183ee28453dce79ee0ef2b_129.png)

Inside if。These ones。Because we only care about that it's the first law。

 and then we do the collision。Yeah， yeah。 this is more common。



![](img/7d44c52568183ee28453dce79ee0ef2b_131.png)

Robust。Colllation look just。

![](img/7d44c52568183ee28453dce79ee0ef2b_133.png)

For your information。Yeah。Well， anyways， I'm going to a breakpoint also in the Oops today。



![](img/7d44c52568183ee28453dce79ee0ef2b_135.png)

Close something。In the lose life， where is that？Yeah。



![](img/7d44c52568183ee28453dce79ee0ef2b_137.png)

B desired P is minus50。 Okay， let's see what's going on。Ball moving them out。 He oh。Okay。看。Yeah。😊，嗯。

This is very wrong。We're not setting the movement around。So， yeah。

If we didn't do the first ball movement， I I said the movement。Movement amount。Was he called again？

Ball moved out。Well。Okay， so。小个包。I go on so we just forgot。Or I just forgot。Okay so。And in this case。

 where we doing min。We can pretty much just set the movement。And the mint tea is gonna be the most。

 we can stop operating on the mint tea。And start operating on the movement amount。

I think they'll be better， so that's called an ball movement left。完了。

And while it's greater than zero。Oh，来。I still have movement。And then instead of passing the N T。

 you're going to pass。The波。Movement left。Yeah， I really like it。😊，开 ball。Moment？嘅。好。Yeah能理解啊。

If you didn't collide。With anything。We' probably said that。Let's see if we to colliding with a block。

The movement。Should be 0。 Yeah， because this means we did the full moment。哦。我能。Left。Okay。

 make our bats， everyone。

![](img/7d44c52568183ee28453dce79ee0ef2b_139.png)

Let's see if we get something。So I'm still going to break。



![](img/7d44c52568183ee28453dce79ee0ef2b_141.png)

Now let's break on these two cases。Okay。So we didn't。Crash。

 which is a progress but we didn't move the ball either。



![](img/7d44c52568183ee28453dce79ee0ef2b_143.png)

We are probably going through this case。Just there's no ball for movement。

So we just set the ball movement to movement left to zero and the ball P。To the goal。Desire to pay。

Right。Let's do all again。 Let's see。I will use boxs again。Just in the render ball。

And we updated your sound。Yeah， this is wrong， we should really be an out the P。冇。

Somell multiplier with ball P。And you know what？I think now the ball did well， we use it here。

 but we could have eliminated that also。哦。Yeah。老DPDP。Trail， D P， trail， flags。DP。He。

So that wasn't very consistent， but that's correct， come sound。Draw ball。O。

We changed the movement to operate from one to zero and we forgot to。



![](img/7d44c52568183ee28453dce79ee0ef2b_145.png)

Let's see， I am starting to get confident that this work。Now， this is very problematic。

That is analyzed and let's assume。To know what we want， then we can。Ive now。In fact。

We might actually， we should probably collide with two blocks and then。

I think this going to return just this block because yeah， I should return this block。Yeah。

 because let's see， let's imagine this line。This one we collide when we are here and this one we collide when we are。

Is that correct。No， I think we're were colliding with them at the same time。

You're probably expected to get like a random block， which is not。Which will be this one。

We probably hit them both， I suppose， colliding with them both。I'm not sure， yeah， I was X。

 so the most correct thing that we want here to destroy them both， but let's see just what happens。

So're glidded with a block。Oh， we already computed that。嗯。



![](img/7d44c52568183ee28453dce79ee0ef2b_147.png)

So you know what， I'm going to make。Temporary break point。啊。Inside here。Just so we can。



![](img/7d44c52568183ee28453dce79ee0ef2b_149.png)

See the collision before。It actually finishes so we can see the two locations。But now。

Just one question hat。Anyways。So。The collision happened with y is true and the hip block。

 the block and the movement。That is minus 18， this is wrong。Should be between one and zero。0 yeah。

买了这一起。M T， yeah， this wrong Should be， should be the T Y， okay。



![](img/7d44c52568183ee28453dce79ee0ef2b_151.png)

Okay。So we're testing the TY and the Tx just to see if it's in the X range。

 but the collision actually， in this case is happening with a Y。

And in this case happening with the x， okay， so that was just a small attack。



![](img/7d44c52568183ee28453dce79ee0ef2b_153.png)

Let's go back to the buggy。

![](img/7d44c52568183ee28453dce79ee0ef2b_155.png)

Okay， now I probably。I don't know， probably just， yeah， just one cl。Women left now we have 0。18。

 which just looks perfect It block collision happen with wise true。几。😊。

So now we're going to keep moving。Well， we collided with two of them， I suppose。

So I guess it did collide with the other one。Yeah， well。Yeah， I'm not going to complain， I。

And you know what？

![](img/7d44c52568183ee28453dce79ee0ef2b_157.png)

I should probably set the collision happened with white to true and here should probably reset that。

Because if there's an escalation that happened before the white collision lesion。

 they should take precedence。

![](img/7d44c52568183ee28453dce79ee0ef2b_159.png)

Okay， now we should probably just have one collision， and we do have more than one。

Let's see if we have three and we do have have oh， oh， because now everyone's going to be true。あ so。

Not a problem now。The bubble of the left is 0。85， so we got a collision right in the beginning of death train movement right because we are critical at this point already。

 okay？So what we want to do。well， let's see if we're going to destroy the block， then we will。

 so we destroy the block。We increase the ball size。And we're probably going to make it faster。

And did the collection happen with what， Yeah， so are we going up， Yeah， do we have a comment note。

So you're just going to reset and reverse the ball P。Procesed Bob and D， PL， whatever。Okay。

 now this is the Tru part。 So we started out。With minus- 18。In X， I'm gonna gonna help。-18 point。

YeahI think。I'm going to write these numbers here。Just so， you know， like this is the ball peak。

And this is the desired P。 This is inside。This is inside the cube the block。So we are going up。

 right， So X is getting greater。ok。Now。We should set。That' to 。85。Yeah。So this。Is the new？V p。

 I it should be between。19。2 and。This looks great， I think。

And now the ball movement left we to have movement。They said we should probably move the ball again。

 so that's what we're going to do now。We do have movement left？

So now the desired P should be the bulb P and the ballal Dp changed， right。

 so now we should be going down。Which is correct。And the ballal easy times the movement left。

This is wrong。This is wrong。Yeah， if removed。Yeah， this is right。If we the move。

What we're testing here， I think what we're testing is correct。Which is。

We're testing how much we're having me draw that edge to make it a little bit easier。



![](img/7d44c52568183ee28453dce79ee0ef2b_161.png)

And you have the ball and the。The block kind of ball here。Let's say。

 well let's make that little more evident， okay。If removed moved up to 85。

Our movement left is just1 minus 85， so yeah。

![](img/7d44c52568183ee28453dce79ee0ef2b_163.png)

So if we did collide in this case。The movement left。It's gonna be。关。好。



![](img/7d44c52568183ee28453dce79ee0ef2b_165.png)

okay。O。Let's。Try that again。So。We've collided with a block。We， do whatever we need to do。

 change the file position。Okay， now the bow movement left 0。44 it。

What this actually means that we moved， this should be the min T so。



![](img/7d44c52568183ee28453dce79ee0ef2b_167.png)

I'm going to rename this guy to meet tea。We started out as one。 so the mint tea。

Should be the bubble left， correct， should start out as one。



![](img/7d44c52568183ee28453dce79ee0ef2b_169.png)

Why is that no dry？So we start out as mintee is one。M tea。And the movement left。

They are both one at this point。Now we collide here。Yeah， this is perfect。Gide here， so the mintty。

It's going to be on no point。8，5。

![](img/7d44c52568183ee28453dce79ee0ef2b_171.png)

The movement left to be 1 minus eight times， so yeah。Chd。This。😊，Yeah。

 whenever we do the ball movement。Left， we do now。聆轻。And that's it。 So this gonna be the min tea。

But the movement laps， one minus。

![](img/7d44c52568183ee28453dce79ee0ef2b_173.png)

O， okay， now that's。Perfect。😊，See I me put the break one out here。Okay now the mintee is 0。55。

Which means they're removed。We managed to move up to 0。55。Yeah， we have like the ball。Yeah about P。

Move up a little bit。Now this guys reach 45 and it is， that's the movement left that we have。

They're going to move that this amount。The desire to be。So now we're now going down。Again。

So our why is。It's less than the way it iss， the desired point。Okay。

 and then we tried to do all collisions again。And then we were going to have to do them all。

 I suppose， but now shouldn shouldn't collide with anyone。And it doesn't。So in this case。

 we set the ball movement left to zero， so we moved the whole thing。And just we said， okay。

I really like it。 Let's， let's see if it works。😊。

![](img/7d44c52568183ee28453dce79ee0ef2b_175.png)

We debugged， apparently understood the problem。

![](img/7d44c52568183ee28453dce79ee0ef2b_177.png)

Its going to be really cool see。Okay。Okay， this looks perfect。

We probably have to fix that case where we collide with two blocks。Yeah， see probably， I don't know。

Z feels a a lot more predictable。哎呀。

![](img/7d44c52568183ee28453dce79ee0ef2b_179.png)

Okay。So it's not working。In that case。

![](img/7d44c52568183ee28453dce79ee0ef2b_181.png)

嗯。I'm going to see my notes， but I did take some notes。Possible reference assert that Dp。

Space on the final P。Yeah， the DP。Spial。The ball P， the beginning of the sweep。

 should be updated when the ball desired P changes。That's oh， we're not doing that for everyone。

So let's do this， this was the wall collision thing。



![](img/7d44c52568183ee28453dce79ee0ef2b_183.png)

In this case， C， we update the ball。Desired P。This is wrong。We should really。嗯。me think。

If you go out over the wallroom and do the same thing， you want to change the ball。P。

Then we calculate the desired to P。But not。I don't know。 I don't know。 but let。

 let's see the other red flag， so。

![](img/7d44c52568183ee28453dce79ee0ef2b_185.png)

Setting the other axes where inclusion hits， we change this whole thing。

Now we're saying the whole thing， so just in both directions for two。

The idea behind this desk in both directions。Because。Here in the collision。

 we just see whether or not they're going up or down。So no need to test both direction。

Poion only when inside。This is interesting， should we collide？When we are right on the edge。

 and I suppose it should be。Suppose this is less than or equal to this guy as well。

Return false when any collision。Avoid double。Okay， so we assumed we would need to return false to return。

 I suppose， in this case。To avoid double， but we didn't get double collision。Yeah。

 it wasn't the problem， the problem was like no collision。



![](img/7d44c52568183ee28453dce79ee0ef2b_187.png)

So， let's。Now I started。Yes， he。

![](img/7d44c52568183ee28453dce79ee0ef2b_189.png)

I think the problem was to per frame。

![](img/7d44c52568183ee28453dce79ee0ef2b_191.png)

Yeah， so this。s correct。Well， it doesn't even matter。It doesn't even matter， by I suppose。Coect。

 and you have to do the wall thing。But let's fix this Egypt problem， which is。The hip block。嗯。

I think the problem was。When we are already inside the block。The suite wouldn't work。Yeah。

 when we are see。Because if we sweep from that， well。You know what， I'm going to do a crazy thing。H。

But。When we respond to blocks。Let's spa huge blocks。



![](img/7d44c52568183ee28453dce79ee0ef2b_193.png)

Just so we have like a a collision happening。

![](img/7d44c52568183ee28453dce79ee0ef2b_195.png)

Well that wasn't that huge， was it？W'ch the size？Oh this is the science。



![](img/7d44c52568183ee28453dce79ee0ef2b_197.png)

That was a spacecing。

![](img/7d44c52568183ee28453dce79ee0ef2b_199.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_200.png)

Well， let's make the blocks even bigger。

![](img/7d44c52568183ee28453dce79ee0ef2b_202.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_203.png)

Yeah， but we want the blocks to actually collide the players。



![](img/7d44c52568183ee28453dce79ee0ef2b_205.png)

テティ？See， this is the problem。We changed。A collision。Well。

 we're not sure because this is not a block cols。

![](img/7d44c52568183ee28453dce79ee0ef2b_207.png)

But the idea is the same if you are sweeping from inside the block。We should destroy it。



![](img/7d44c52568183ee28453dce79ee0ef2b_209.png)

Yeah。😊，So we have to make sure that this works。

![](img/7d44c52568183ee28453dce79ee0ef2b_211.png)

And then probably have to make。

![](img/7d44c52568183ee28453dce79ee0ef2b_213.png)

No， I think that's the only problem。Swefting from inside of blocks。Okay， so when we do。that。

When we do the bulb。Block collision。We going to do the ball block collision。



![](img/7d44c52568183ee28453dce79ee0ef2b_215.png)

Here， the sweep。This is weird。Because I believe the sheep should。



![](img/7d44c52568183ee28453dce79ee0ef2b_217.png)

Oh the sweeps getting the limit。You know what， if we tested both sweeps and didn't collide。And。

 this is another thing we could have done。看。Okay， so。I see doing things。

After you've done them for the first time in one project。Makes it really more clear。TheAdvans。

 so the idea is。If we are colliding。They get like the ball in the block。

 I don't know what what does ABB versus ABB take。We take a P1。 So ball desired P。Half size or bowl。

Have size。Block P and block。sizeize。If we are colliding。The ball is already。side the block。

I'm going to do that but see this is where I think we should probably collapse the loops。But。

If we do the block collision。If you're collided with this block。So I'm going to do like。

 I am going to do。If you're col with this block。Oh if you didn't collect， it's black。And we did。

The AVB testing failed， which means that we are inside a block。I'm going to just fail the collision。

I'm going to set the min。钱。To0。Which means that we don't move at all。Right。

And then we said the collision happened and why it would be。And we can probably up。Yeah。

 because if you're inside a block， doesn't matter which block， you collect who inside it anyway。

Actually， if this is zero， yeah， we're going to try， yeah。

 this is perfect Now you have the mint teacher to zero， which means that we are we got stuck。😊。

On this iteration。And we also have to change what the collision happening why， I'm going to set that。



![](img/7d44c52568183ee28453dce79ee0ef2b_219.png)

It's kind of a heck， but it's a heck that we could have done that before。

It probably saved does a lot of headache， but it wouldn't be as robust as it iss going to be now。

 but the idea is。It it is a heck， right， but if you're。If our。With the length of our y。



![](img/7d44c52568183ee28453dce79ee0ef2b_221.png)

I think I could do like。Like sweet。Yes。I'm going to do like the length squared。

The length squared of our ball。Des Ied to pee with a ball pee。反那就。Okay。



![](img/7d44c52568183ee28453dce79ee0ef2b_223.png)

This will be the sweep path， the collision will happen with the Y if our sweep。Well， no。

 not the length。The thing is， if， if it。

![](img/7d44c52568183ee28453dce79ee0ef2b_225.png)

Go能 just do the mind。I meant that I think the sweet path is a substitute too。So in the collision。

 what happen with the why？If the absolute。Of the sweet pad。The sweep path， why。

It's greater than the absolute sweet path X。

![](img/7d44c52568183ee28453dce79ee0ef2b_227.png)

可。😊，Yeah， in this case， itll mean see in this case I'll do the Y It's not 100% just like。

Maybe even be。Really that solution。

![](img/7d44c52568183ee28453dce79ee0ef2b_229.png)

Yeah， you know what？I order to change。Change it at all。So I'm going to say like collision。我是包。Update。

Aes。Sat that to minus1。春新的。Yeah。fall。Data aes be  -1。0， for1 out。For x1 y。That also。AAbout。Is that。

嗯嗯。对来。In this case， it's y so one。No。This is is X。X would be 0。And this。ho you want。Nice。

 and in this case。ですね。Okay。Illegal for type po， yeah， so you wanted to。

now whether or not it applies to returned。2。I think I think I'm going to。 Yeah， I'm not going to。

On that to I understand， I'm not going to delete the code。Turn true问 this。好死。Okay。

 you can't convert F 32 to B32。Which one。I think the ball have size， maybe。不确。Yeah， so。

If we hit a block， we're going to assert。The ball。Update aes is not -1。Well， this is wrong， yeah。

 because that's。That's the thing we are changing here， right？Allll update x is minus1。

Hit black's going be。Yeahや yeah yeah yeah yeah yeah。Okay， so。If the ball。Update access is。0。

Let's do one。We do the five。Else， if it's zero， you do the x， and if it's not， we don't do anything。



![](img/7d44c52568183ee28453dce79ee0ef2b_231.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_232.png)

感' you。Okay。

![](img/7d44c52568183ee28453dce79ee0ef2b_234.png)

This is exactly what we wanted。 Now all we have to do is make sure。There we have。

A functional collision system。Right， I mean， that's just what we want in the first place。



![](img/7d44c52568183ee28453dce79ee0ef2b_236.png)

哼，唔起。Okay， nice。 I like。I like it。 I like it。 I like it。Okay， until I get the。

W shouldt break out the yeah。Fick perfect。Even that one， I think that was the correct one。

 it was too fast for me too。Completely understand。But， I think。っち。我 that只么。Okay， so now I can say。

 I mean， we have to test more right， but in theory， the theory。Behind our collision system。

 it's now very robust。I see that。Because it's doing like sweeps and it's doing like， well。

 we still have to fix the wobble thing， right？I' going to takes the lot fee now。



![](img/7d44c52568183ee28453dce79ee0ef2b_238.png)

That fixke the whole thing。The old thing is the thing that。新的。



![](img/7d44c52568183ee28453dce79ee0ef2b_240.png)

Here， whenever you coll out to these guys。I probably don't have to worry about the player。

In the ceiling。Because it's not going to hit a block and a player in the same frame。

Nor the ceiling and。Well， the silly。It could happen， you know what， that's played of time。

Let's try to get the ball behind。more。牛。It's crazy， I really like the pun level， I really do。



![](img/7d44c52568183ee28453dce79ee0ef2b_242.png)

Yeah， see， so we may hit the ceiling and。The other guys， so we have to check out these three guys。

 right， the ceiling， yeah。These three guys。And actually， in these cases。

 I can pretty much just set the above movement left to zero。Which is not 100% accurate。

Let it work now。Maybe you can change that later on but。Oh。If we hit。The end of the arena。

We're not going to move anymore。If first one movement or。One moment left。less。Okay， so in this case。

 we're going to ignore the block。And this， which is the player and the bo perfect。Now in these cases。

We do have to know how much we moved。I mean， we we could also just set that to zero。

This would probably means that we have probably less movement。On the frame， we hit the。The walls。



![](img/7d44c52568183ee28453dce79ee0ef2b_244.png)

But I don't really think that'll be a problem。Yeah， see that was a no boy at all。

 and that vision was awesome。Yeah， I don't。I don't really notice that at all。



![](img/7d44c52568183ee28453dce79ee0ef2b_246.png)

So I think I'm going to leave it like this。And。Yeah its smart has hack so we can go back and improve because that's the thing we don't want to make the perfect decision system。

At all， what we do want to do is a better system than we have。Last stream。And that's life， man。

Just make 1% better every day， that'll be 100% better after 100 days。😊。

Let me test a little bit more back and pretty confident。



![](img/7d44c52568183ee28453dce79ee0ef2b_248.png)

Our collision is。Perfect now。And just because I had a word perfect。Have a horrible work problem。Yeah。

See， I think decades the ball was already signed。Because it took a while for them。

that was pretty cool。But visually， that was fine。And。In terms of correctness， it was 100%。

 so I'm not going to complain。切。Yeah， that was。That was pretty well done， too。

And' probably going to have to watch some of these in slow motion。

Or I could play the game is slow motion， but it'll be kind of boring。

So I think I'm just going to play that a bit。And then I'm going to record testcallation。Yeah， see。

Not。Let me understand what happens there。Just make sure。That was a bit weird。



![](img/7d44c52568183ee28453dce79ee0ef2b_250.png)

That was a pretty， pretty nice one though。I'm going to stop and start the recording。Okay。

 just so we can analyze the very end。Oh that thing， let me go to the recordings。



![](img/7d44c52568183ee28453dce79ee0ef2b_252.png)

Okay。Is see。welcomeで。new来週？In terms of correctness。Yeah that was。That was。You know what。

 I don't know if it already happened or not。Yeah，You know what， I think I'm going to open。

The future resolve。

![](img/7d44c52568183ee28453dce79ee0ef2b_254.png)

And drop the video in。Just so we can。Analyze it frame by frame。So yeah， let's do this。

My computers having a really hard time doing all of these。Thanks。20。48。Yeah。Oh， well。Okay。

 so you open the entire project just so we can。

![](img/7d44c52568183ee28453dce79ee0ef2b_256.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_257.png)

See， edit。

![](img/7d44c52568183ee28453dce79ee0ef2b_259.png)

Yeah。Oh， this is really slow。

![](img/7d44c52568183ee28453dce79ee0ef2b_261.png)

Okay， now let's import the video here。哦。Okay， there it is。And let's go to the very end。

I'mNot sure I make that full screen。So。It's nice to see that in reverse， the particles look awesome。

Piano， this is。This is where we're moving A see。Yeah， so that was a bit weird， let's zoom。And。屁。

How do I。Move this guy。Let's see， so。We destroyed the three of them。And I went down。

I suppose you were right。I suppose。Yeah， it's hard to tell what happened。But。In this case。

 we would hit the precise corner。We've could have hit like this one first。

 or let's say this one and this one， this one， so we go up。To the left。And down。So。Yeah， I think。

That'll。That'll be it。Was that the weird one， was that a more weird one？to watch some。てきと。

That boring。Yeah， I think that was the view one。No， I think those was are more weird。A weird one。

Yeah。😊，Let's see， Yeah， see， same thing。But I think we are wrong because in this case。

 it's evident that we hit this guy first。Then should have hit this guy。

I think our piece not considering the half size。Yeah， see。

 we should have hit this guy and then this guy， we should not have hit。See。

 we should have this and this and then gone up。But we hit like the three of them。

And hit this guy then went down and then he' liked a lot of them。

Bpartpartal systems looks really cool。I think。So yeah， let's， let's review our P， our Ps。

You know what。顶不能住。Yeah， let's do this。

![](img/7d44c52568183ee28453dce79ee0ef2b_263.png)

I'm going to do like。A he to。Oold。老 piece。P倍 16。Then we do A2 old ball。F size 16。等会 do来。投到。可以。😊。

And whenever we hit。A block。Yeah， whenever we hit a block。嗯。是。

And we're not going to get in this case， I'm going to print。And whenever I going hit a block。

 I'm going to like do like the。Od。包。P。At。Next cold ball。Because course。啊。I really want to save。

 I really want to save this ball piece。So this is like the collision point。Okay。

 and then the same thing for the half size and I'm going to do it next。

F the ball plus plug if the next ball is greater than the race size。Your bo皮。The next quality。

Thanks all the all。Okay。😊，And this would be the half side。And have size actually floats。Okay。😊，Now。

 let's in the。Their movement here。Here I'm going to go through we do clean the screen， I。

Going do like four。D欧宝。T。那你说。rotate take erect。Okay。I'm going to draw at the old。包PIT。やて。2。Hd ball。

Half size。And then， I'm going do。0 for the angle。Let's do dream。And then ask you。拿。Hi。

 glad you finally got you live， what are you doing。

 we are doing a huge change in the collision system。😊，Because the first time。First time， it's not V3。

The first time you wrote the collisionleg system， which was' in the second day。

We actually didn't know exactly how to structure it and it was a crazy thing， right？But。

We learned a lot。Through making the game， And that's one of the huge advantages of。

Like one of the huge things， I suppose， which is the more it make the game the better you are at making not only games。

 but big game so。There were a couple of problems with the collision， and now we're doing a big。

A change in the cruise system。So， just。And。We changed we already did a lot of code stuff today。

 like just changing the same things stuff。一啊啊。What's the problem？The colored。

You two in different You two pointer， Oh it is a pointer。So。We are almost done。

 were just going to fix one colgen problem that we still have。

Which probably has to do the wayre cating the P for the ball。



![](img/7d44c52568183ee28453dce79ee0ef2b_265.png)

The the no P， like the idea of the call is that now when we do like big motions。

We managed to get the ball to this point。I think itll be correct， though。

And then we in the same frame， we continue doing the collision。

 so we may hit like these two guys in one frame frame。 it's about pretty fast。

 So that's going to be really， really cool and it's really better。😊。



![](img/7d44c52568183ee28453dce79ee0ef2b_267.png)

As of now， but it's still not 100%。Color。What's the problem， Oh， man。

These are messages to be a little bit more helpful。Pameter  four。Float to float to float pointer。

 is this also a pointer。啊。Experent。Yeah。ですか。So take the size， the angle， the color。啊，I don't know我台。

Just a normal color。Can't convert from the V pointer oh。



![](img/7d44c52568183ee28453dce79ee0ef2b_269.png)

So that was weird， I saw the pointer I thought the color was going to take a pointer because that's what we did。



![](img/7d44c52568183ee28453dce79ee0ef2b_271.png)

In another function。Now whenever we hit a ball， we should stick there， can we do our little shadow。



![](img/7d44c52568183ee28453dce79ee0ef2b_273.png)

And I think。Well， you know what I think this is wrong。嗯。See how we are inside the ball。

 this other ball here。We should really be， like。

![](img/7d44c52568183ee28453dce79ee0ef2b_275.png)

Sure to be like this。So， in the level。Let's， let's change。 see the ball。 Yeah， do bulk test。



![](img/7d44c52568183ee28453dce79ee0ef2b_277.png)

In this case， the problem was the ball Y， correct， yeah。



![](img/7d44c52568183ee28453dce79ee0ef2b_279.png)

You know what we could play now in super slow motion。Okay， Is do that。

Let's do that because I think now we'll be able to。啊。😮。



![](img/7d44c52568183ee28453dce79ee0ef2b_281.png)

We should be able to see。If the ball is changing rapidly， when we collide。And it's going to be。有第二。

Okay， but it's nice， though。Okay， let's see。Yeah， I guys I's seen a couple less videos it's included。

 yeah， it is。一？🎼Oh， it was still hard to see， man。

![](img/7d44c52568183ee28453dce79ee0ef2b_283.png)

好 things we're gonna。Articicles， you're going to remove the particle system。

Riner particles not going to remove the render， but not going to。I'Not going to draw particles。

UnReachable code。 Yeah， thanks compiler， Larry。Very useful of you to say this。



![](img/7d44c52568183ee28453dce79ee0ef2b_285.png)

Bgy。Yeah， yeah， I do it is， it is， it wasn't completely buggy， but it is， it was a little bit buggy。

And that was just a little bit buggy now。It's even last bugggy， as I was saying。

 all you have to do is get is get that like。A little bit better every stream。

But now since we are taking the time to improve that。You should be hot better。爱奇。Okay。

 this looked correct and I'm going to do one more just again。Yeah， think I think that is wrong。

 I'm going to start the recording。

![](img/7d44c52568183ee28453dce79ee0ef2b_287.png)

And I'm going to drop the video again on the Vinci Re so it can go frame by frame。



![](img/7d44c52568183ee28453dce79ee0ef2b_289.png)

And analyze it。是。因啊。Yeah。I don't know， man， how to， how to move， how to move this guy， I'm not sure。

Oh， because the ball grows。嗯。So RRP is perfect， except。The bug grows， so。This causes weird problems。

So I think I'm going to move the ball。The direction is grew， yeah。あら。啊。Let's see the other one。Yeah。

 that was even worse。The center kind of looks correct， I think。But the increase in size。Doesn't。



![](img/7d44c52568183ee28453dce79ee0ef2b_291.png)

So， yeah。Let's let's go to the collision。Have we collided。Yeah， yeah。Okay， we increase the size。

Increaseing ball size。Let me just play a little bit with the decreased ball size， well。

 not the decreased， but the non increased ball size。



![](img/7d44c52568183ee28453dce79ee0ef2b_293.png)

Just so we can make sure that we don't。W we are better， it's going to be hard to get that bug 100%。

Dude， now the games super fast because you played that in super slow motion。

Just a quick note while I play the collision a little bit。

Doing deepbug visual addresses like the ones we just did that was pretty quickly。

 that was pretty fast。It's awesome。Because it took us almost no time。

And it helped us like 1 thousand%， so that's always good， always good。



![](img/7d44c52568183ee28453dce79ee0ef2b_295.png)

What's that？P sound。Variation。Ws the next one sound what？The next thing sound is minus a huge number。

Why。

![](img/7d44c52568183ee28453dce79ee0ef2b_297.png)

So we found a bug in our audio system now。Okay， next。Bs。



![](img/7d44c52568183ee28453dce79ee0ef2b_299.png)

Sound。If it's is that that to aitable sound count。30。Is oh， that's not。0。lastday 아이。DRA count。Okay。

 same thing here。Let's do the next。蚊香。Oh， that's it。That was a weird， but。

 but I think we are perfect in the collision， but we do want to change the ball size， so we can't。



![](img/7d44c52568183ee28453dce79ee0ef2b_301.png)

Just。Comment this out。 so you have to make the cold work in this situation。

 What I want to do is I want to move the ball。啊。The amount it increased， right。

Maybe the increase ball size。啊， whatever。So' going to say like。Hold size， it's going to be bold。

F size。They have the old and the new size。Yeah， we changed the ball movement。Whatever。

 and then we're going to set the ball P。点过的。Set that I'm going to add that to the ball P。Plus。



![](img/7d44c52568183ee28453dce79ee0ef2b_303.png)

What do we want， We want to move that。The free collided。col why。



![](img/7d44c52568183ee28453dce79ee0ef2b_305.png)

I'm going to move that twice the ball p in white， so I'm going to make like here。Size offset。

Size offset。Okay。And if the ball pe。If the ball Dp。Well， first of all。Let's do this。

Before we update the axis。Because then it cannot。Yeah。Size offset set yeah。

If we hit on the Y axisxes。If we are going up。If the Y axises is positive。We have to move it down。

So size offset。Do's why。It's kind of equal to the。包。H size。Minus the old size。Thanks to。

I think that's correct。Okay， now if we are not。冇片啊。I'm going to do the same thing。

 but it's going to be the so the new have size。Should be larger and then minus subid。Okay。

 now same thing for the X。We're going to change the X。But before I change。

 I'm going to test if it's greater than zero， so if we are going。If you are going to the right。

It means that we are increasing。Yes， this is wrong。 if you are increasing the y。

Tres zero are going up。Sure。 yeah， that's right。Okay， now same thing for the X in this case。嗯。

I don't know。 I don't know。 I don't know。 I think this word ball have size。Oh， correct。

 ball arrow have size。

![](img/7d44c52568183ee28453dce79ee0ef2b_307.png)

Okay。

![](img/7d44c52568183ee28453dce79ee0ef2b_309.png)

Let's see if the guys things's going to work。阿起。Okay， I think， I think that's a lot better， yeah。

Yeah， beautiful was awesome。

![](img/7d44c52568183ee28453dce79ee0ef2b_311.png)

Yeah， so when we got。

![](img/7d44c52568183ee28453dce79ee0ef2b_313.png)

The inside guy。We got a wrong collision， so that's zero because we were inside。

 so suppose that's the last case， right？That we should work on。And let me just。そです。

And I'm going to just。It's for the sake of。Make it easier。Going to。Okay。

 because if we ever want that back， which we are going to need it， I suppose。嗯。Okay。

 so the last problem is when we are inside。The block。

 I think we're going to do the thing that we were going to do and we didn't do。

Which was to see whether or not it was up or down based on the。On the difference。Get a street path。

Yeah， I even started doing the code。If。Yeah， there's not 100% precise。But I think。That'll work。

Because this is supposed to be liing fast cases。So I don't know。

 I think this may just work so the I'm going to update the axis is the y axis。

 the y axis is one right so y。You have turnern area operations in sea。I think we do， we do。

So I'm going to do like， if the ball。TY， sorry， if the sweep。De p委。

I'm going to take the absolute of that。If this guy is greater。Thenhan the X。Fish do one。P。

 I never fit you。Missing， Sam I going before。Yeah。Okay， now we can assure。Aert。

S also a pretty good name， we can assert。That the well， I'm going to put it down here。这 you like。



![](img/7d44c52568183ee28453dce79ee0ef2b_315.png)

Be valid。K。😊。

![](img/7d44c52568183ee28453dce79ee0ef2b_317.png)

Now let's play around invis。We are going to have to play with the collision a lot just to make sure。

And it's working。Yeah， see， that was perfect。 We got a zero dude that was。

 that was really lucky on us。 I got another zero， so I got a zero， which means that we got， okay。

 so we crashed。😊，Yeah， our audio is problematic。 Well a good thing we put that as certain and let's see our playing sound was 64。

😊。

![](img/7d44c52568183ee28453dce79ee0ef2b_319.png)

Oh， because we are not testing。This is wrong we testing。



![](img/7d44c52568183ee28453dce79ee0ef2b_321.png)

嗯。Here。Yeah， this is like inverted。Our。一次。We could probably make more sounds now。

I don't know if 128s too many sounds。

![](img/7d44c52568183ee28453dce79ee0ef2b_323.png)

But just for the。Second， that's test with 30 like。

![](img/7d44c52568183ee28453dce79ee0ef2b_325.png)

设施。16 is。

![](img/7d44c52568183ee28453dce79ee0ef2b_327.png)

是哪个？Because we have to have at least the number of。



![](img/7d44c52568183ee28453dce79ee0ef2b_329.png)

Its in the beginning。Yeah， so。Yeah so this is problematic I mean we are supposed to test that later。

 but I don't know。So we're going to test that to get a free list， if we have sounds on the free list。

 we're going to get from the free list， if we don't have the free list。I'm going to insert。

Going to assert this guy。And then I can pretty safely get from him。And we're going to increment it。

And then if it's greater， than the。The array count。And so that to the immutable sound count。

I can assert this to make sure。Righter。

![](img/7d44c52568183ee28453dce79ee0ef2b_331.png)

Yeah， that should fix it。That's play another game mode let's see how the collision stands out， maybe。

Maybe with the comments， it's going to be a little bit crazy。啊some。

Got 10 of zeros and it looks perfect。饿。Okay， I got a ton of it。Our downs there。Dude。

 I think we can call it victory， see how they just scraped the blocks， that was pretty cool。

I think we call a victory for the collision or today。啊死。Really awesome。 our， I wish is really。

 really cool now， Oh， crap， I was I was stuck between TNT。😊。



![](img/7d44c52568183ee28453dce79ee0ef2b_333.png)

Okay。😊，So， I think。I can call that a victory for today， what do you guys think？That was great。

That was great。I reallyally， really liked it。Now me just remove that print。

And let's clean up this guy。 I don't need。 I don't think we're gonna need this guy anymore。 If we do。

 we can write that again。 That wasn't too hard。 gonna remove this guy。 Now it's old code。

see if there's any it zeros here， let's see the levels。We do now this on the old。

 so now we are way cleaner here， way cleaner。Same thing here。喂听。

And let's see probably going remove this guy just。So， it's easier to read。So narccl is way better。

 way better。And maybe I'm going to un this。And just for a quick test。I'm going to change the。

I'm not going to sleep。Just so we know if our frame aid is good， oh。

 we should also go back to the non optimizeized field。



![](img/7d44c52568183ee28453dce79ee0ef2b_335.png)

こち。

![](img/7d44c52568183ee28453dce79ee0ef2b_337.png)

To the opposite。啊，冇见。Then link。

![](img/7d44c52568183ee28453dce79ee0ef2b_339.png)

Okay， so we got one and two milliseconds per frame， now we're at one， and we collide。

We have a little bit of a hit。When we， when we。We get a ton of them。

Because you have to calculate everything twice per frame。But we are great。いい？Dude。Doude those crazy。

That was。Completely crazy。Dude。I should probably finish this game。Just so I can enjoy。

That high score。That was a huge feature。Yeah也。I'm gonna have to click then post that on Twitter or something。

😊，Because sometimes I do have some crazy plays。And since you are playing at a higher frame rate。

 the trail looks way better。Maybe we're going to do the lup for the trail。I don't know。

May not be 100%， though。Because we do have to lu between the old position and into the position。

But the opposition may change。So。It's also to test the collision against like these smaller cases。た。

Other crap， okay， you still have some lines left。啊。啊是没电了。う。Yeah， these final blockss are。

I don't know how it was in the older breakout， like the really old one。

If you really had to be super accurate at very end， but they had bigger blocks。

But that's kind of the price we pay if we want to do like crazy stuff with a breakout。g水。

I'll take that。By the way， game looks and feels awesome。

 it shows what we can do even without fancy engines Yeah， that's the thing man it is。

And by understanding。What makes these subtle things make the game really pop？

Like discussion stretch to the audio， we still have to work on the values a little bit I think。う。

But then when we do make use of a game engine， which has a lot more tools， right？

We're going to be able to create such a better game than just create like random particles in unreal Rio or something yeah。

 the particles look great in unreal Rio， but if you don't know how they can enhance the gameplay exactly。

You're not going to reap the boss benefits only。Making a game with no engine。Really。

 really helps you to understand the priorities in making like， oh my God， it's been hard。

Like like the animations or the particles and like making the walls move like that was a great call。

 I really liked it。Let's see， oh my god， it's going to be hard。嗯。

And we are going to add screen Sha now。It's nice of you。 Oh， it's nice of you too。 let's see。

Oh my god。Maybe I'm going to fail with one black na。Okay， succeed， huge high score， victory。Okay。

Open the window here。

![](img/7d44c52568183ee28453dce79ee0ef2b_341.png)

Awesome。😊，So， I say， we should now。Be super happy because of our collision victory today。

And now we should work on the mar fuel stuff， the screen shake。Oh， with the level transition。

The level transition。Maybe maybe you should do like the asset pack， maybe you should do like。呃 see。

Maybe we should do like the OGG reader and the asset cooker first。Yes。こシ。Yeah， so that's the plan。

 but that's for next time I think today we can still pretty much do let's see what time it is。

 yeah still little bit too， we can do at least the screen shape。It's going to be not too hard。

 it's going to be pretty fun， but I do need to take。

Like a two minute break so I can get more water and go to the bathroom。

So let's take a two minute break。And I suggest you also got some water。

Because now we're going to improve the game field， it's going to be really cool。

And then probably do the level transition That's going be really nice because I haven't done that。😊。

With no way in the before。Okay， kind of confess， right， like a cool animation before the game starts。

Okay， let's do that together next time， so maybe guys can help me two minutes。Okay， I'm back。

Now let's improve the game field， that's going to be really cool， screen shake。

I think that's not gonna be too hard。But I didn't know famous that words。

 I said that like three times in the series and all time every time I said that。

 I spent like hours doing it。The problem known our screen shape。Here we have a ton。Of different。

All different draw calls。So we have like this draw。Draw erect in pixels。主要。Reect transparent。

 then we go direct。And let's say we do the calculates effort multiplier， but we don't have a。

Camera and notion of a camera。So I suppose that's the first thing you're going to have to add。

It's going to be quite easy to test， though。So。Yeah。I'm going to do like a V2 camped。And。

Vtu can leak。And whenever we initialize the game。ming to set the campe。2， let's say 0。The can D P 0。

 I mean， they should all， They should。 They should be0 already， okay。Okay。

Now I think I'm going to go through each one and change that。Yeah。嗯。

So the drawing pixels don't care about this。The pixels。Did be to world。Its going cool because oh。

 okay。Yeah。😊，Where's our skill。Let's call that the camscar。Yes， so now it's hard code。

 That's okay now。Because it's called Cam'sscape。で。Here。So many scale。Yeah。

 this we haven't improved still。Because。If you can improve that， I'm going to write note。

Are the optimization optimizations。You do like。X。Then。Yeah， I think I'm going to do that， preamble。

 preamble， is that how we write that？Of the draw。Rotated， wreck。Scall。LetJust keep going。That's it。

Okay， now let's go one by one and subtracting the camera P。 Okay， yeah。

 we have subtract this like the camera， I say， the camera P is one。

 You want the guy to to be at minus-1。

![](img/7d44c52568183ee28453dce79ee0ef2b_343.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_344.png)

So if we move the camera right， we want them to move left。That's pretty easy。Now let's see。

 so this the first one draw。I'm going to。T equals sub E2。P。😊，Kam。But this is going to be like。

I'm going to have to do this like every。Every time。



![](img/7d44c52568183ee28453dce79ee0ef2b_346.png)

Im then we call draw and now draw re。星星。Oh， but we have a couple other values。We have the P。

But we have the well let's just test。If I direct。

![](img/7d44c52568183ee28453dce79ee0ef2b_348.png)

Is offset correctly， so should be zero。But。She probably set like the can。P dot X to one。

Everything should be right lot once you're。

![](img/7d44c52568183ee28453dce79ee0ef2b_350.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_351.png)

O。Pretty cool and Tim was also。

![](img/7d44c52568183ee28453dce79ee0ef2b_353.png)

Not that much。Nice， now those are the。Direct。Which the text？哦。

But we have so much stuff that's hard coded。Yeah。The player P is going to suffer because that's not。

嗯。We're going to have to think about that。

![](img/7d44c52568183ee28453dce79ee0ef2b_355.png)

ButOkay， so。Draw arena X。The and leftmost。It's going to be the same thing， right？

I have to subtract all。Ftmost。等 then。Subtract the accountopy。Dot X。Same thing for the right most。

And that's it。Have size， wide。That's namelight。Honestly。



![](img/7d44c52568183ee28453dce79ee0ef2b_357.png)

Let's see。开次。

![](img/7d44c52568183ee28453dce79ee0ef2b_359.png)

ok。

![](img/7d44c52568183ee28453dce79ee0ef2b_361.png)

Yeah。

![](img/7d44c52568183ee28453dce79ee0ef2b_363.png)

That by5。

![](img/7d44c52568183ee28453dce79ee0ef2b_365.png)

Yeah， so the arena is not。

![](img/7d44c52568183ee28453dce79ee0ef2b_367.png)

Hundred%。D erects。So we do like the X， Y is the P， Y。Oh， we don't， we shouldn have set。These guys。



![](img/7d44c52568183ee28453dce79ee0ef2b_369.png)

就是笔。Yeah， now I think。あ。ForSome reason， we are not dry。



![](img/7d44c52568183ee28453dce79ee0ef2b_371.png)

The left most correctly。The top one looks correct。Just this one。嗯。Havelf size y。啊。



![](img/7d44c52568183ee28453dce79ee0ef2b_373.png)

I don't know。I know it was supposed。

![](img/7d44c52568183ee28453dce79ee0ef2b_375.png)

Oh， it's correct， but。Yeah， I think， oh， since we haven't structured the game。Word like that。

The player pe。It's going to be a little bit powerful it。The player P and the。

And the hard code collisions。Yeah。So first of all， we have to fix those。



![](img/7d44c52568183ee28453dce79ee0ef2b_377.png)

Yeah。

![](img/7d44c52568183ee28453dce79ee0ef2b_379.png)

But that's weird。I mean， the player P should be correct。I don't know。You're going all the way。

过 the way。To this guy， but oh， okay。

![](img/7d44c52568183ee28453dce79ee0ef2b_381.png)

Okay， that was kind of stupid w because of。We haven't done in everyone yet， I mean。

 this guy's probably wrong。But。But the player is not the problem yet。Okay， so that's。So draw number。

 we don't need to do that because we call it draw。Drf 32 calls drawn number。

Draw transparent data react can have to do this the P。ok。I think this part， I can't。This part。

 we optimize。And this part was the par better we could optimize further。Okay。

 let's see what else we have。You are rotated wrecked。ちとい。Bitmap。Dropet map， same。Draw rack subpixel。

 which was the one that we thought that was at stake and attacks。

 I think it's just going to call draw Act。

![](img/7d44c52568183ee28453dce79ee0ef2b_383.png)

Okay。Let's see now。

![](img/7d44c52568183ee28453dce79ee0ef2b_385.png)

Now we don't even see the player。correct。

![](img/7d44c52568183ee28453dce79ee0ef2b_387.png)

系。

![](img/7d44c52568183ee28453dce79ee0ef2b_389.png)

Right。Yeah， everything is working except。Kin of look at those。Partsで。Everything is working。

Accept the。

![](img/7d44c52568183ee28453dce79ee0ef2b_391.png)

The clear。Arena。

![](img/7d44c52568183ee28453dce79ee0ef2b_393.png)

Yeah see。😊。

![](img/7d44c52568183ee28453dce79ee0ef2b_395.png)

啊。Oh， we didn't comp it do this。

![](img/7d44c52568183ee28453dce79ee0ef2b_397.png)

If you're going to take a long time to finish the game， Okay， now it's okay， now we're perfect。

 now we have a camera。

![](img/7d44c52568183ee28453dce79ee0ef2b_399.png)

Now that we do have a camera， we should be able to add screen shake， which is what we want to do。

Maybe you're going to do just screenshake today and then next time we'mre going to do these guys。

Maybe。Yeah， because we've been streaming for like two and a half hours already。

And the collision of thing， man， the collision thing is hard， things are to on your head。ok。Now。

 let's do the camera thing like can P。Right in the beginning of the loop。T pig，Let's say update。

And the way we're going to update the camera。Well， we could just do like the basic thing or the KP equals everyV2。

just add。E two of campe。And then a multiplication of like him。离by。And D key。

This is like the very basic thing we did a couple of times already， so if we set。

So if you said like here in the beginning。I can do in the very end here。If we set it like the chm。D滴。

To be。1， and the can lie to be， I don't know。Negative。



![](img/7d44c52568183ee28453dce79ee0ef2b_401.png)

Bye， should type a chemical。And we do have。And it's kind of funny to see how the player moves super slowly。

But the out rectangle doesn't。Because the player has subt of accuracy and the other one doesn't。Yeah。

 we see the difference there。That's awesome。It's almost。

Almost makes me want to add a motor to around with the camera。



![](img/7d44c52568183ee28453dce79ee0ef2b_403.png)

No I note that maybe。Donkey K， maybe sure that I like at one point I went to go super Mario。

But then I drop that， but maybe I'm going to do that。Pretty cool now。I don't want to do this。

What do I want to do， Do you guys have any idea what I want to do。嗯。😊。

Any ideas of how we're going to do the camera， the camera will be a spring。

 just like the rest of our springs。Right， so same thing we're gonna have。A DP here。 And these。あGDP。

Is gonna be。其出啲。Some offset。I'm going to copy the values from the player。

 but then we can play around with that。Of the desired， which is 0， so。0。And。The current。P， so can。谁？

Okay， so that's。That's the first factor。Then we're going to add。The factor to0 d speed。

So you're going to add these two guys。And this one's going to be safety and multiplication。Of V20。

屌调咯。And the CA DP。Oh。This is wrong。This is a multiplication。Off the subtraction on these guys。Yeah。😊。

Yeah， now we're talking now now same thing it's multiplication of subtraction， this guy at camera DP。

 and that's like 20， which is the factor that we did for the other guy。

And then you can finish the multi， finish the ad。机。😊。

And now here we're going to add this guy to this guy。And they're also going to add。The DDP， so。

So we this guy to the。天。嗯。😊，And at this point， you're also going to add。TheDDP。Times the。D。

 T squared。Time is 0。5。We just like the formula。Of the that's that's why it's called EPI almost set in Portuguese police。

 That's why。😊，That's why the D。It's called DP because it's the derivative。

That's still a word I have to say a lot more derivative。They derivative。

So that's the formula to get into this guy to the P from the DDP。

 so we have to multiply that by the square of the factor which is DTU to time and half。So yeah。

 we're gonna。We'm multiplying this guy。I'm going to add this guy to this guy again。The correct， add。



![](img/7d44c52568183ee28453dce79ee0ef2b_405.png)

Now we should still have a stable camera。

![](img/7d44c52568183ee28453dce79ee0ef2b_407.png)

But now let's do a little bit of a okay now every time you press up。

Let's add a bit of a camera movement。 Let's set。Let's see what we do with the walls。

For the bow wall collision。I suppose we just add， right？Oh do wall hit effect。Yeah。You love。No。嗯。

Where do we change Oh yeah， we just set it to 30。So I think we're just going to set。Tm。P。

 just test D P， sorry。To， let's say。10 minus 10。Just for fun。Just for fun， that's at F32 England。



![](img/7d44c52568183ee28453dce79ee0ef2b_409.png)

Yeah。

![](img/7d44c52568183ee28453dce79ee0ef2b_411.png)

So every time we press up， we expect to see like a slap on the camera。That's really cool。😊。

I don't think we are going back to our zero position。



![](img/7d44c52568183ee28453dce79ee0ef2b_413.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_414.png)

That was really cool， though。Especially when I pressed that a lot like this。



![](img/7d44c52568183ee28453dce79ee0ef2b_416.png)

嗯。

![](img/7d44c52568183ee28453dce79ee0ef2b_418.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_419.png)

else。Oh， we're trying to roll back。But they're having a hard time。Dude， screen shake is always fun。

 always。😊，I mean。It's not the best call for the game， but it's fun nonetheless， at least。



![](img/7d44c52568183ee28453dce79ee0ef2b_421.png)

For us to fair around it。You know。Oh， because we're not updatinging the cam， yeah， the cam。DeepP。

 we're not updating that。K if， you just going to be the a me2 yes this thing here。

They start of multiplying that by the square。We don't multiply。What。



![](img/7d44c52568183ee28453dce79ee0ef2b_423.png)

Okay， that was a weird compiler bug。切。Okay。Now， they're talking。Now we are talking， dude。

 that was awesome， yeah。Look at that screen shape。Let's。That's pretend we already programmed it。Dude。

 they you're gonna be so much better， like so much， so， so， so much better。

 like a million times better when we had the screen shake， I mean。

 how come we haven't done that before？😊。

![](img/7d44c52568183ee28453dce79ee0ef2b_425.png)

But everything， everything is time， right， everything is time， so player， ball， col。😊，Player。

Pre collisionulation with ball。Recolide。Oh， probably， probably gonna make a functional that。

 Let's do like Sha creamre。Maybe ice cream shape。Shake screenre is more fun。Bd screen shake tomorrow。

moer之间。Okay， and I'm thinking about whether or not we should add the screen shake or just set it。

Maybe fruit is going to be way too chaotic。It's not the best place to put in the labels。

 but I'm going to put them there anyway because that's where we put our utility stuff。So yeah。

 let's do like。Inline， add。Im for。Spcreen shapeake。S factor。And let's sha 100。Okay。

 and let's try just setting。Yeah。😊，As to the。And screen shape。



![](img/7d44c52568183ee28453dce79ee0ef2b_427.png)

100 same thing we had before。But let's just set this way I press。



![](img/7d44c52568183ee28453dce79ee0ef2b_429.png)

A lot， just by setting。Which is pretty quiet I think。And let me try。Let me try adding， so add you to。

That see's I createdでげ。

![](img/7d44c52568183ee28453dce79ee0ef2b_431.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_432.png)

Yeah， I like saying。Okay。😊，Now we should be good to go now。

 that's all let's just add these add screen Sha calls whenever you want to add screen Sha。

So player collision with ball， player collision with ball， we are and added a speech check。Okay。

Let's do a ball collision with the walls。Maybe we can do like a little bit less。Okay。😊，Fage dinner。

 Oh， I should also add a noise if we。Yeah， let's also add screen shape in this case。

 when we lose a life we can add。冇。After all， we lost life， right？你识。啊。Thementation。Yeah， so this。

This if。So then I add like 1，50， You lose a life。And if we don't， I'm going to add like 75。

 I'm also going to add a sound because I think theres a sound is so play。Random。Some with variation。

Let's see。 The sound is gonna be。Salary direct。Redirect sound。The variation。嗯。Just like。3。

And I don't think that there are lot forms。Well， could be the bulk。Let's go back to I screenhe。

 so can I convert F32？老皮。ok。啊。Now。Ball block collision。嗯嗯。When we hit a block。Add speechche。And。

And never a0 in this case。

![](img/7d44c52568183ee28453dce79ee0ef2b_434.png)

来起来起来起来起。What。Why not screen shake？

![](img/7d44c52568183ee28453dce79ee0ef2b_436.png)

Why no screen shakeake？啊。Did I mess something up here， yeah。I did。This doesn't even make sense。



![](img/7d44c52568183ee28453dce79ee0ef2b_438.png)

Yeah。オッケーオッケーオッケー。オッケー。Yeah， okay。イエ。I don't think I'm going to add in the player collision。



![](img/7d44c52568183ee28453dce79ee0ef2b_440.png)

Because the player collision is the good thing。

![](img/7d44c52568183ee28453dce79ee0ef2b_442.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_443.png)

Maybe just a tiny bit。Yeah。When we got a comment？It's going to be super all over the place。Yeah。

You want to play around with the Suprememe values as well。And our is awesome。Accolition is really。

 really cool I think I think。这然就不行了。Dude。Yeah， I think it's prettying tent now this screen shake。

And the spring settings， which probably play around。Okay， let's try basically。

Maybe the wall is too strong， I think。Did you hear。It's crazy。Yeah。Look at that， man。



![](img/7d44c52568183ee28453dce79ee0ef2b_445.png)

Okay， so I'm going to decrease， what did I do？あけて。So'm going to decrease。

The wall screen shape comm to 30。This one， I can leave like。And when we hit a block。Let's make like。

But， let's change the。Canm。If we。Let's say， this guy is。



![](img/7d44c52568183ee28453dce79ee0ef2b_447.png)

To decreaseecre this guy。

![](img/7d44c52568183ee28453dce79ee0ef2b_449.png)

We should have a smoother screen shape。He， I see。 that's not very intense。

This like the initial force of the spring。

![](img/7d44c52568183ee28453dce79ee0ef2b_451.png)

Like how much goes to the other side？So how much was it？



![](img/7d44c52568183ee28453dce79ee0ef2b_453.png)

Let's try and make 5000 just do。1000。

![](img/7d44c52568183ee28453dce79ee0ef2b_455.png)

And so this is very quick。And unpredictable screen shape， which I think is pretty。



![](img/7d44c52568183ee28453dce79ee0ef2b_457.png)

And if you decrease this guy， species iss going to last for longer。

 it's going to go like back and forth for more times。



![](img/7d44c52568183ee28453dce79ee0ef2b_459.png)

Yeah。Yeah， I think this is better。Great。

![](img/7d44c52568183ee28453dce79ee0ef2b_461.png)

Yeah， to lose life， lose life is awesome。一个那个。Really， even。

Put that screen shakeake on the lose life itself。

![](img/7d44c52568183ee28453dce79ee0ef2b_463.png)

Let's make that too。Because I don't know， man， we lost life。



![](img/7d44c52568183ee28453dce79ee0ef2b_465.png)

And we can also make。These guys even small。And then hit a block， maybe 50。



![](img/7d44c52568183ee28453dce79ee0ef2b_467.png)

Let's big， that's big tense。Oh， that's weird。When we lost a life。The Tes game。The play on the。

Fallspon inside the block。

![](img/7d44c52568183ee28453dce79ee0ef2b_469.png)

Okay， so got a small bug。In this case， if we are not in the first law movement。Or。Have you seen talk。

About the games absolutely， man， and when we first implemented the first small things about the game juice like animation and stuff。

I even referenced that showed that talk on stream and we talked， oh， like can become Tland。Yeah。

 that really sucks。I showed that talk on stream。

![](img/7d44c52568183ee28453dce79ee0ef2b_471.png)

And we discussed about what are the elements that we wanted to add in this game。I absolutely。

' a great talk。

![](img/7d44c52568183ee28453dce79ee0ef2b_473.png)

For anyone。we're going to know the talk。

![](img/7d44c52568183ee28453dce79ee0ef2b_475.png)

That highik quote is talking about。 It's called。Juice in our loses。No， it's not it。你就是。あ？



![](img/7d44c52568183ee28453dce79ee0ef2b_477.png)

Yeah。This talk。It's really cool man， I mean super over the top by the end， right？

But it is pretty cool， it's great actually， you should be able to know the accelerated version。😊。



![](img/7d44c52568183ee28453dce79ee0ef2b_479.png)

In order to understand what consists of the game juice， so to speak。



![](img/7d44c52568183ee28453dce79ee0ef2b_481.png)

But we should be able to tone that down for our game。Yeah， that was pretty， pretty。

 pretty solid I think。Really， really like it。Okay， that to the spacing videos。

She also probably standard the text man as a polished name。里面有。嗯。Okay， this may be it for today。



![](img/7d44c52568183ee28453dce79ee0ef2b_483.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_484.png)

This may be it。We have implemented a camera system and screenhe with success。

So I think next time I'm going to start out by doing a level transition。They're gonna do this。

 This gonna be kinda， kind of hard。

![](img/7d44c52568183ee28453dce79ee0ef2b_486.png)

Because it's kind of finicky。To get the player collision， like when we move him。

 we have all sorts of problems。Then what happens if we move really fast？



![](img/7d44c52568183ee28453dce79ee0ef2b_488.png)

あの。It's not going。Super fun， I suppose。 but it's going to be cool。

 I think we can play around with this a lot。 The level transition to the main menu in the bank。😊。

And we should also play around attention a little bit more。

 I'm going to play that off stream just to get a little bit more ideas。



![](img/7d44c52568183ee28453dce79ee0ef2b_490.png)

But I think I liked。That other ideas。Oh， actually， we didn't solve the t but。This is that part。



![](img/7d44c52568183ee28453dce79ee0ef2b_492.png)

Yeah。

![](img/7d44c52568183ee28453dce79ee0ef2b_494.png)

It has to do with the order that we are reading collision。Versus。Versus the other that weR。Checking。

 checking。Do the game over thing， right， not not the game over the year。They lose life。

So whenever we lose life。Here。😊，Lose life。Let's see what we do。Yeah， see that we are。

If we die to we set the advanced level。If we don't。We reset everything。

 we can't reset everything here， we can't。So I'm going do like。

We're going to do a variable like this is an advanced level。And this is。I don't know。

 Let's call that。 lose life。一。Great name， great name， except it's not a great name。Yeah。

 and visitors should probably not do this either。There is game over。We should just。Same thing。

 but at advance。To the current level。Yeah。い、 okay。Go to do light。

It was a life and if instecute or if you don't have life。Go to be advanced level， set the target。

 play the sounds at the volume。T level。Se the target。这个下啊。Okay。

 now we're going to say lose life at the end。And I'm gonna just in the whole thing。That at the end。

 here。Fans。Fance level。If you like if。Loose。Life at the end。你论不来。Los life。好。And we set the。

And lovelyly。We said that。Okay。

![](img/7d44c52568183ee28453dce79ee0ef2b_496.png)

I'd see if we fixed。是た。Dude bunge loud， now， oh， bunges so awesome。

I probably had a massive screen shake when Po， Yeah， I'm gonna do this。 when Po hits the level， so。



![](img/7d44c52568183ee28453dce79ee0ef2b_498.png)

The level， I still simulate level。So whenever the enemy in Kong hits the arena。Stcreen shape。

Massive one。Well， maybe。

![](img/7d44c52568183ee28453dce79ee0ef2b_500.png)

一0分。I don't know， maybe too much， we get too excited when doing screen shakes。



![](img/7d44c52568183ee28453dce79ee0ef2b_502.png)

Dude。

![](img/7d44c52568183ee28453dce79ee0ef2b_504.png)

看だ。Thatn't bit too much。But I also am going to only test this。Let's go back to like 150。

m going to test this。If you're not already inside it。Oh， like。可愛い？こ。And， well。If is。好。I。

Colliding with wall。 if it is not colliding with the wall。S兴趣。Set this guy to。Same thing down here。

And then we do like the house。我下的。

![](img/7d44c52568183ee28453dce79ee0ef2b_506.png)

不行。Let's see。2。あす。So we probably had a sound effect as well。



![](img/7d44c52568183ee28453dce79ee0ef2b_508.png)

What kind of sound effects we have for when a player hits when the enemy hits the wall， let's see。

Yeah， that wast cool。A cool。Add high idea。I great。

![](img/7d44c52568183ee28453dce79ee0ef2b_510.png)

I'm going to have a player a wall one， but I'm going to make it way base here。

Do we have the player wall？Yeah， we do play a role down。We're going add screen shake。

 and we're going。喂。Sound with variation。哎 yeah。La。Well sound。Let's see I， no， I don't。Variation。

 let's say， 0。15 F。And the source is going to be the。好。Hung enemy P doX。But， we are also。In sound。

We are also going to set the sound。Speing multiplier less decrease that。So be really base。



![](img/7d44c52568183ee28453dce79ee0ef2b_512.png)

Let's hear it， Let's hear it。I think you're nerve writing on。Me。



![](img/7d44c52568183ee28453dce79ee0ef2b_514.png)

Yeah， it's too low， also。We' like a fool。So I think I can make that even easier。I'm gonna do like。Se。

我要。For the sound。Do this sound。Try to get volume。Plus。I know let's do plus one。

Let's try and make that really absurd。

![](img/7d44c52568183ee28453dce79ee0ef2b_516.png)

あ。🎼Let's see。 Let's hear right。🎼哇。🎼Like one。🎼日用。Yeah。Do to give so much better inspiration。Oh man。

 that was crazy。后面O now now。🎼好啊Okay。🎼Me。🎼Oh one left that's finishing finishing okay there we go Oh let's see if we fix that bug。

Oh， we did。

![](img/7d44c52568183ee28453dce79ee0ef2b_518.png)

We did hit that bug by changing the order， okay， awesome， dude， today's today's awesome today。

Everything was awesome。I like whenever's awesome days。Okay， I think I'm going to leave it for now。

 oh， it's three hours， pretty much exactly。Thank you so much for watching I hope you enjoy today。

 if you want to download the source code for free， you can go to my HIO page like me yeah。😊。



![](img/7d44c52568183ee28453dce79ee0ef2b_520.png)

Which is dazdam。h。o。Okay， come here to this game and just make it download now。 you can。

 you can download every episode source code typically if you want to just on see and see the progress and watch as we build together。

😊。

![](img/7d44c52568183ee28453dce79ee0ef2b_522.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_523.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_524.png)

Just click download down andre welcome to give me a tip， but if you can just if if you just download。

 it just click no thanks。

![](img/7d44c52568183ee28453dce79ee0ef2b_526.png)

Okay。😊，And oh， Ju is also for people who didn't see it at the beginning of the stream。

 we also have a license and a license is do what you want with it。

 So it's either in the public domain or you do whatever you want with it。

So you can do whatever wanted， I don't care。

![](img/7d44c52568183ee28453dce79ee0ef2b_528.png)

呃。

![](img/7d44c52568183ee28453dce79ee0ef2b_530.png)

This is just because people asked， oh， what's the license I was like， dude， what do you mean？

This like just for fun， man for everybody to learn and have fun。

 I don't want people to have to be worrying about or do I have to put like what what is it called attribution？

No， I mean， if you want to， I'd appreciate it， also appreciate the donation， but whatever。

 do what you want to learn from it and have fun and you can also download you can also watch the whole thing from my YouTubebe channel。

 which is YouTube our/DZ Dan。

![](img/7d44c52568183ee28453dce79ee0ef2b_532.png)

And you can watch from the very first episode all the way to where we are now。



![](img/7d44c52568183ee28453dce79ee0ef2b_534.png)

And dude， the game has come along really， really nicely。

 I say that pretty much every day now because I'm really happy with the way the game is。

Is looking at feeling in it。E ceter， I really， really like it， really like it。



![](img/7d44c52568183ee28453dce79ee0ef2b_536.png)

You can also watch my tutorial series， I have begun an actual tutorial series where I teach you how to create a game in S from scratch。

Start at beginners。But I think it's pretty cool because it's kind of fast paced。



![](img/7d44c52568183ee28453dce79ee0ef2b_538.png)

Each chapter is going to be like seven minutes and so on and I there's a theory behind it。

 like the same and the platform layer， things that you see in this stream I explain on the other one。

And yeah， then I do like the beginning of the programming。

And I'm gonna to post blue starts every week， hopefully。 And let me。

 let me know what you guys think about all this， right？😊。



![](img/7d44c52568183ee28453dce79ee0ef2b_540.png)

And yeah， hopefully you joined the stream as much as I did。

 Hopefully you learned a couple things as well。 Today was great。 We did a lot of cool stuff。

 and that's it。 Thanks for watching and I'll see you next time。 Bye bye。😊。



![](img/7d44c52568183ee28453dce79ee0ef2b_542.png)