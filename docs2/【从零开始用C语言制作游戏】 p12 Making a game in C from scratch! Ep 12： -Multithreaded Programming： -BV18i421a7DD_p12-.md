# 【从零开始用C语言制作游戏】 p12 Making a game in C from scratch! Ep 12： -Multithreaded Programming： -BV18i421a7DD_p12-

Hello everybody welcome to this new live stream where we are creating a game in from scratch if you have been following along the series。

 you saw that yesterday we finished our last episode which was yesterday we finished our audio system actually we started building it from scratch the last stream and we got to about 9% of working so this is where what we ended up with。

😊。

![](img/6f18f54518e4455428d5825da1c39f49_1.png)

🎼美味しい？🎼Yeah。🎼The。🎼The。🎼，So we managed we managed to implement music and different audios and we added a lot of cool features let me show you guys。



![](img/6f18f54518e4455428d5825da1c39f49_3.png)

![](img/6f18f54518e4455428d5825da1c39f49_4.png)

Last time around。We did the audio system。And we can do all sorts of crs that we can change like the pan。

 the volume， the if looping or not， spin multiplier。And then we did all that last stream， however。

 there were a couple of problems that hopefully we can solve today pretty quickly。

And when we do finish those problems or at least have a better understanding of them。

 we're going to implement a multithreaded system in our game， a job system。

 so we can do like the audiomothreaded and then the rendering multi threadreaded。

 and then when we load OGG files， we're going to do that asynchronously asynchlyously as well， okay。

So。😊。

![](img/6f18f54518e4455428d5825da1c39f49_6.png)

We the well just for actually our program， let me just tell you that you guys can go to my YouTube channel。

 which is YouTube。com s d Z Dan and watch everything we did from the game ever since the first episode。

Here they we with a blank file and nothing all the way going through the all the things we implemented and last time was the audit system and today we're going to do both threading and few couple things and you can download the game and the source code on HO just come here to my Ho just day。

h。Io and just click here the game we can download the game and the source for every episode for free。



![](img/6f18f54518e4455428d5825da1c39f49_8.png)

![](img/6f18f54518e4455428d5825da1c39f49_9.png)

Okay， now few problems that we had last time。Does it place sound？

We tried implementing this sound wave sound， the sine wave sound。



![](img/6f18f54518e4455428d5825da1c39f49_11.png)

And if you guys pay close attention。Let me turn it a little bit the volume a little bit up for you guys。

You can hear a the looping problem and we were all nuts by the end of the stream like oh。

 why is this looping problem， what can we do and we had a hard time figuring that out and it turned out。

And the problem is the audio file。😡，This sine wave file is not actually looping correctly。上个哎。

We've got another sine wave file， I'm going to drop that。And replace that on the data folder。

And now if we take a listen。That's perfect。这都对。So this problem wasn't actually our problem。



![](img/6f18f54518e4455428d5825da1c39f49_13.png)

It's kind of our attention problem right we should I should had a better sine wave so we fixed the sine wave now another things that I noted here we should do in the audio before implement the sound effects。

😊，Is a。We had a hard time getting the audio to change volume based on the player DP。

Because since we used the mouse it was all over the place and we tried a lot different stuff。

 but I had an idea which is save an array of the last D and get the average that was smooth out all the mouse imperfeions and I think that's going to be a cool thing we can probably do that quickly today and we should also make a free list。

Which I might I。Disney。Right now， we just get the 32 sounds and we。

You forget to more than 32 at or just going to assert。

And I'm going to bring like quick free list just to make sure that we can do that properly， okay？Now。

 let's try to do the average thing， so we have like the player。Movemed sound。That's。

Let's save a player。😊，And a last D piece。It's going to be an array of eight floats I'm going do like。

Player last D P。Okay。😊，No。Whenever we do like the target。When we finish this guy。

We're going to save him as the as the。The new DPO now the player。Or I just forgot the variable name。

たら。第一。Well。I suppose it was a bad name because it just forgot what it was。Cl less okay。The player。

Played last。Be peace at the player。The player plastic team next。Plus， plus。

It's going to be equal to the player。Target。PP dot x。

And then we're going to see like if the player last D next。

I greater or equal than the erase count of the player。Lsty piece。

I's going to set that player SD next。20。Okay， now we should be able to get the average。

Of this array value guy， so like four and I。0。I less than a ratecount。Play your last。P plus plus。

I still like。Aage equals 0， and Im going to sum。These guys like the player。This guy。And then。

 the average。Going to。Divide that by their account。Okay。

 and now we should be able to just set the player。Movements sound at volume。To the average。Yeah。

 it's probably make it。啊。Well， I'm thinking about making that the。The absolute value。

Or maybe just the。This guy should be just the after I do the average， not sure。

Plus to the upload here。Times for all us do like。Small guy， and then we can do like a clamp。

It's like what we were trying to do last time。Okay， now let's printimp this guy。P。嗯。发样。



![](img/6f18f54518e4455428d5825da1c39f49_15.png)

Okay， let's try。

![](img/6f18f54518e4455428d5825da1c39f49_17.png)

几我 don。あ？Well。

![](img/6f18f54518e4455428d5825da1c39f49_19.png)

よし。I'm going to turn your volume down。Just so I don't give you guys a heart attack。



![](img/6f18f54518e4455428d5825da1c39f49_21.png)

And let's try to see。

![](img/6f18f54518e4455428d5825da1c39f49_23.png)

Okay， that wasn't。Too bad。

![](img/6f18f54518e4455428d5825da1c39f49_25.png)

But well， that was kind of bad， but。Think we are on our way。It's less than one。

I don't know if you guys cant hear that。That sounds pretty well， pretty good if you go。



![](img/6f18f54518e4455428d5825da1c39f49_27.png)

で go。To more than one。

![](img/6f18f54518e4455428d5825da1c39f49_29.png)

That's really bad。

![](img/6f18f54518e4455428d5825da1c39f49_31.png)

![](img/6f18f54518e4455428d5825da1c39f49_32.png)

I don't know。 It's so weird。 I think I'm gonna， I'm not going to spend too much time today on this。

バラ。Or we could do like a target volume。

![](img/6f18f54518e4455428d5825da1c39f49_34.png)

System。I think I had that system， would you start of just setting the volume and service at the target volume？

Then the volume interpolates to that。Let's tried。Let me show the volume， so。Yeah。

 let's just quickly edit that。保用。快啲作用。Okay， and then before we do。Everything thing？The sample guys。

 let's just go like。Sound。Thar to flying。Is less than the sound。Trrgge volume。无异议。Would you like。

Which is pretty much what we did， but now it's going to be a little bit more generic。😊。

If we are greater then， we subtract。And then we。Yeah， we should plan， but I think they'll be enough。

t。Then， let's pass the。あ。

![](img/6f18f54518e4455428d5825da1c39f49_36.png)

O。😊，Let's see。Yeah， this is way better。 So we start out with the target zero and the volume。Yeah。

 with the volume one and target zero。Yeah。

![](img/6f18f54518e4455428d5825da1c39f49_38.png)

This is exactly what we wanted， Maybe now we don't even need this average system because we are smoothing this guy。

So。I't just tried doing this。

![](img/6f18f54518e4455428d5825da1c39f49_40.png)

Ex like this， let's try doing。The player。Target D。

![](img/6f18f54518e4455428d5825da1c39f49_42.png)

Yeah， you know what。This may be it。Let me just start out。Player movement sound。Let's just set the。

Let's just said the target volume。0。And the。And the volume to zero。And the。あリオスしたん。

IGoing to set them both to one as the mut。

![](img/6f18f54518e4455428d5825da1c39f49_44.png)

你索。RightOkay， let's see。

![](img/6f18f54518e4455428d5825da1c39f49_46.png)

![](img/6f18f54518e4455428d5825da1c39f49_47.png)

Yeah， this one， I think should be a little bit quicker this DT。Would you like times。And。

And I sure really plan。

![](img/6f18f54518e4455428d5825da1c39f49_49.png)

![](img/6f18f54518e4455428d5825da1c39f49_50.png)

![](img/6f18f54518e4455428d5825da1c39f49_51.png)

![](img/6f18f54518e4455428d5825da1c39f49_52.png)

![](img/6f18f54518e4455428d5825da1c39f49_53.png)

Okay， I think this is start。

![](img/6f18f54518e4455428d5825da1c39f49_55.png)

Okay， well。

![](img/6f18f54518e4455428d5825da1c39f49_57.png)

I think this is going to be the correct idea， but this is still pretty much problematic。

So I'm not going to worry about that now。Going to go back to the old system。And then I just。

just like comment this guy。When we implement sound effects like。Make。The。Volume have a target。

volumeum对。诶。I'm just going to wreck that。I I'll be able to understand so the free list。

 I think I'm going to be able to do the free list pretty quickly。And the free list is。This guy。

 so the problem is， if you only have， let's say， let's say you only have like one sound at a time。喂。

And then we try to play two sounds we're going to assert。



![](img/6f18f54518e4455428d5825da1c39f49_59.png)

And the problem is not that we assert。 The problem is， in this case， we should， we should。

We're just overriding the first sound。

![](img/6f18f54518e4455428d5825da1c39f49_61.png)

But I think the best thing is actually， if the first sound is not plain is。

We shouldn't actually play another sound I think I'm going to do that。So I'm going to add like。

Playing sound next， free。And I'm going to do the。First， three。So we're going to do like a free list。

When we try。When we try to get a new sound。First thing， we're going to do。

It' trying to get from the first screen。Let's call that first speed。

And if we do have a first with sound。The first free sound going to be the result。Next， free。可。😊。

Pretty easily。In case we didn't get a free sound， then in this case。

 we were going to increment this guy。Okay， and they're going to get a no sound。But。Like。If this guy。

Is a。B than this guy。They're get a no sound。If it's not。Vna。Yeah。

 I think we're just going to do that because this shouldn't actually trigger。 I mean。

 if you do trigger this， we should just increase this sky， so this is for our development。So。Yeah。

 we treated this guy。But if we have like。2 set well。I it like this every time。

Like every time you press a button button up。Let's play a sound。



![](img/6f18f54518e4455428d5825da1c39f49_63.png)

And let's not。So。Okay。

![](img/6f18f54518e4455428d5825da1c39f49_65.png)

Have two。 the next plane sound。Should be。Should be one。



![](img/6f18f54518e4455428d5825da1c39f49_67.png)

I don't know why I would cr it then。気ち。Next pen sound too。0。不要。Next plane sounds 0。 Now。

 Next plane sounds was one。And now。

![](img/6f18f54518e4455428d5825da1c39f49_69.png)

I bring sound this one。Okay， so I suppose this like is down。



![](img/6f18f54518e4455428d5825da1c39f49_71.png)

Okay， so。

![](img/6f18f54518e4455428d5825da1c39f49_73.png)

This。😊，Thing we crash because we're not adding to the free list， so this is correct behavior。啊。Yeah。

 now let's add different list。 So instead of just setting this guy to not active。

 I'm going to like stop。行。Then the stop sound。W takes the plain sound。Im to set the sound。False。

 and I'm going to set the sound of。Sound next， free， going to be the first。Free sound。

 And first free sound。It's going to be。

![](img/6f18f54518e4455428d5825da1c39f49_75.png)

![](img/6f18f54518e4455428d5825da1c39f49_76.png)

And if you do two。We assert。But if we。

![](img/6f18f54518e4455428d5825da1c39f49_78.png)

Please stop the。

![](img/6f18f54518e4455428d5825da1c39f49_80.png)

We you just probably gott replace them years。

![](img/6f18f54518e4455428d5825da1c39f49_82.png)

Oh no， yeah， well。We struggling with this picture。So we're not going to play the sound。Well。

 but then we return to a new valid sound。This is going to be problematic。Now。

 let's just do it like this。So if we are greater or equal than the array max。

 we're going to loop around， and then we can assert。For our development。



![](img/6f18f54518e4455428d5825da1c39f49_84.png)

![](img/6f18f54518e4455428d5825da1c39f49_85.png)

哇。Surehortly did like a warning for headphone users。

 but I don't think it was that loud but that was pretty loud。说 zero。Get the no playing sound。

I don't know what happened。

![](img/6f18f54518e4455428d5825da1c39f49_87.png)

Let's put a break point。Like here。Okay， so we should now get the music at this point。Yeah。

You change the sound。嗯。Yeah。

![](img/6f18f54518e4455428d5825da1c39f49_89.png)

Well， I'm not entirely sure。What happened？え？This is not actually correct。I'm just going to return。

And not play the sound because if like we are playing the sound。

 I'm going to return into pointer and a search。So this shouldn't actually happen。But the problem is。

In this case。Like if you have a pointer to the sound。To the playing sound。

 and then we change that pointer to another sound and then change the volume and and like that。

 that's going to be really incorrect behavior so we can just crash。



![](img/6f18f54518e4455428d5825da1c39f49_91.png)

![](img/6f18f54518e4455428d5825da1c39f49_92.png)

But now if we don't assume suit。

![](img/6f18f54518e4455428d5825da1c39f49_94.png)

not just you're just going to not play the sound， fancy。



![](img/6f18f54518e4455428d5825da1c39f49_96.png)

But if we do expect a pointer this may fail， not sure this is the best call though。



![](img/6f18f54518e4455428d5825da1c39f49_98.png)

But for now， we're going to do like 32 sounds and we shouldn't actually ever。



![](img/6f18f54518e4455428d5825da1c39f49_100.png)

Oh， the problem is when we were adding sounds， so this behavior wasn't entirely incorrect。Well。

 it was because of the。In but。Sweird， adding。Okay， I， I'm starting to think， yeah， our。

 this guy's wrong。 Our mixer is wrong。Yeah。Were probably， yeah。The problem is we are。We are。

 I don't know， overflowing this guy。Because we're adding。Right。Yeah。I think I'm just going to。

Cp the idea was going。It's going to be bad。But not as bad as what we just saw。嗯Let's see， so。

This guy。It's going to be。A clamp。Of I don't know， men。S 16。This guy。Add it to the left side。

Next sample。And this。Ex。Okay， I think this is gonna fix that problem。Right。Sample。Haveath a max。

A third two to int。I do like。よ。32。Okay， and then in the utilities。sign the men。As。あ。Thanks。Do like。

Clamp。To many actual parameters。Left sound sample。Times this guy。Plus， the right science center。No。

 I suppose we were correct。Yeah。It claimp too many parameters。That's in three parameters。Yeah。Well。

Yeah， you know what？没有。嗯。Let's do， like，Sample。To red。Oh yeah， we are， I have too much。

This is what you should then do。Okay。

![](img/6f18f54518e4455428d5825da1c39f49_102.png)

That's。

![](img/6f18f54518e4455428d5825da1c39f49_104.png)

![](img/6f18f54518e4455428d5825da1c39f49_105.png)

![](img/6f18f54518e4455428d5825da1c39f49_106.png)

嗯。A good clamp at this point。And just do these guys as floating points。I think I'm going to do that。

Yeah。Plant that。And then， we cannot。We can be sure when we overflow that buffer。

We should do we could also do like a dynamic。Size like instead of clamping。

 we just turn the volume down for everything。That could be interesting。But yeah， well， that sample。

same thing we were doing。And。This guy。I have to make that a floating point。Okay， truncation。

This we shouldn't actually。From N to F32。Me this guy。Or this guy。



![](img/6f18f54518e4455428d5825da1c39f49_108.png)

![](img/6f18f54518e4455428d5825da1c39f49_109.png)

Well。Still not。Working。Let they print this guy。And。



![](img/6f18f54518e4455428d5825da1c39f49_111.png)

我要。Not sure how it is how that print is going be。是。



![](img/6f18f54518e4455428d5825da1c39f49_113.png)

Yeah， anyway， the volume。Is a lot louder than it should be？Like。If you just multiply that。

 this like the global。

![](img/6f18f54518e4455428d5825da1c39f49_115.png)

If do everything like by half。

![](img/6f18f54518e4455428d5825da1c39f49_117.png)

Yeah， we can do two， but we shouldn't be able to do three。



![](img/6f18f54518e4455428d5825da1c39f49_119.png)

Yeah。Let's do， like an assert。left sample is greater than the。And the left sample is less。Well。Now。

I think that's correct。

![](img/6f18f54518e4455428d5825da1c39f49_121.png)

![](img/6f18f54518e4455428d5825da1c39f49_122.png)

that's weird。

![](img/6f18f54518e4455428d5825da1c39f49_124.png)

I well also I suppose that's not the problem。嗯。

![](img/6f18f54518e4455428d5825da1c39f49_126.png)

![](img/6f18f54518e4455428d5825da1c39f49_127.png)

![](img/6f18f54518e4455428d5825da1c39f49_128.png)

![](img/6f18f54518e4455428d5825da1c39f49_129.png)

I think I may just delegate that problem for later as well。

Just because I want to get motor threading working today。

 and then we can do like another audio stream where we implement sound effects， implement music。

 and fix these problems。But。don't know。The problem is， let's do， like。



![](img/6f18f54518e4455428d5825da1c39f49_131.png)

![](img/6f18f54518e4455428d5825da1c39f49_132.png)

Weird。来 sample。And less than the max。

![](img/6f18f54518e4455428d5825da1c39f49_134.png)

Shouldt be doing something really stupid。

![](img/6f18f54518e4455428d5825da1c39f49_136.png)

A I home排。

![](img/6f18f54518e4455428d5825da1c39f49_138.png)

![](img/6f18f54518e4455428d5825da1c39f49_139.png)

![](img/6f18f54518e4455428d5825da1c39f49_140.png)

啊。If the last sample is greater than。This guy。Well， yeah， assert。

 make sure the left sample is greater than the men。Times the small number。And it's less than the max。

10 is small number。 Maybe the men and the mags are wrong。



![](img/6f18f54518e4455428d5825da1c39f49_142.png)

Yeah， so。行。😊，Ill that a different source。一。Les sample is 350 the men。Wellow。



![](img/6f18f54518e4455428d5825da1c39f49_144.png)

嗯。Okay， so。ですけどね。

![](img/6f18f54518e4455428d5825da1c39f49_146.png)

没关系。She do have the problem and now let's。The man。Yeah， this is。



![](img/6f18f54518e4455428d5825da1c39f49_148.png)

It's wrong。呵。Well。

![](img/6f18f54518e4455428d5825da1c39f49_150.png)

Wellow， that was a stupid typo。

![](img/6f18f54518e4455428d5825da1c39f49_152.png)

Yeah， well。Oh， well， heaven sometimes。

![](img/6f18f54518e4455428d5825da1c39f49_154.png)

Perfect， thanks， Marcus， in fact， just brought a lot of good luck because we had a weird bug that we were chasing for like。

 I don't know 15 minutes， well，10 minutes。

![](img/6f18f54518e4455428d5825da1c39f49_156.png)

![](img/6f18f54518e4455428d5825da1c39f49_157.png)

And then we just figured it out。So。You brought good luck。无异议。

Now we I suppose we are done with our free list kind of thing。But if we， if we have like。



![](img/6f18f54518e4455428d5825da1c39f49_159.png)

3 sounds Max。

![](img/6f18f54518e4455428d5825da1c39f49_161.png)

Yeah， we assert。But we should be able to continue。That's trying taking out these two。



![](img/6f18f54518e4455428d5825da1c39f49_163.png)

![](img/6f18f54518e4455428d5825da1c39f49_164.png)

I does not play that sound。The and let's see if it be problematic to possibly return zero。

At this point。I don't think。 I don't think it will。

Because the important side effects we're going to pause in the beginning。

And these guys are just going to be like one offs。Or maybe everything we change like the volume thing like that。

We do that through calls。Yeah， that may be a good choice。Then make sure the point is not low。Well。

 yeah， who knows。But。I suppose we are done for the id system as of now。 and in fact。No what。

Let's try to implement this guy again。Just because。

Just because we fixed a pretty significant problem with the sound system。

And that actually made that actually help。These are sort little sound。We did the move towards， right。

 So sound volume is the move towards。Move towards。So I have the sound volume。

Then move that towards the target volume。With a speed of Dt times three。



![](img/6f18f54518e4455428d5825da1c39f49_166.png)

Threader seems like a dark matter to me， well， hopefully。You'll be able to follow along。

 but they are pretty crazy。 They're not as crazy in the beginning。



![](img/6f18f54518e4455428d5825da1c39f49_168.png)

![](img/6f18f54518e4455428d5825da1c39f49_169.png)

The beginning is pretty okay， but once you。Do， you know。Craazier stuff。

With that then starts to be coming really pretty crazy Yeah I kind of agree with you。

 but hopefully in the beginning you'll be able to get what we'll do that'll be pretty easy we're just fixing a couple。



![](img/6f18f54518e4455428d5825da1c39f49_171.png)

![](img/6f18f54518e4455428d5825da1c39f49_172.png)

Upfront we had。Target。老0。Let's set this guy to one as the default。



![](img/6f18f54518e4455428d5825da1c39f49_174.png)

![](img/6f18f54518e4455428d5825da1c39f49_175.png)

Now let's go back to the player movement sound。可以。Sound and then do like what your movement。

Sounds going to be equal to。Let's play the。Sound sign。Set it to Luke。Now。

You should be able to do now。Yeah。Is set。Well， here。I do that the。Player。诶。Player。Move and sound。

The target volume。It's going to be。s that clam path。0 and 3。Of the player。Target低皮。ThatX。Times。

And then we'll actually go into print。F3。F 32。Yeah， well。R does a lot of tas。

These are jobs are going to support interoperable jobs。嗯。Not at first。

But I'm going to do like a job queuee system， so I'm going to have like a couple of different cues。

And。

![](img/6f18f54518e4455428d5825da1c39f49_177.png)

Yeah， and the queuees， I shouldn be able to organize like priority cues。Yeah。

 so they're not going to be interruptible， at least for this game， maybe。

 but the priority keep is going to。Make them know less or more important。

 so you can assign like one thread。To work on like a lot of stuff。

 which is not non high priority and then like the render one， we can do the more high priority stuff。

That's going to work。

![](img/6f18f54518e4455428d5825da1c39f49_179.png)

Yeah， well， this is still going to still going to need to think about that。



![](img/6f18f54518e4455428d5825da1c39f49_181.png)

Because。

![](img/6f18f54518e4455428d5825da1c39f49_183.png)

For some reason， when we move slowly。Just。Ass。To the thing， or if we move fast。



![](img/6f18f54518e4455428d5825da1c39f49_185.png)

Oh， it's because the target DT gets clamped。Yeah， well， let's not worry about that。

 worry about that later。let's let's take out the turnf once again we implemented that like three times a day。

 then we're going to do Fred， people seems to be excited let's do Fred。

Because that's what we're here for today。The other thing was just clean up the old system。

 all the old system system that we did last time。

![](img/6f18f54518e4455428d5825da1c39f49_187.png)

Okay， so now we're back to just having the music。

![](img/6f18f54518e4455428d5825da1c39f49_189.png)

And let's do a case why we don't lock the mouse。That's not locked in my house。



![](img/6f18f54518e4455428d5825da1c39f49_191.png)

And the player piece is going to be all over the place。But hopefully。



![](img/6f18f54518e4455428d5825da1c39f49_193.png)

See。😊，We'll be able to village the id system。I'm going to get my。Well。

 let me just put two guys so that you guys can hear。🎼So。

See now we're not updating the game anymore because were like we got the window。

 so we are pretty much stuck。Our game loop that's not a problem。

 but the sound is problematic so we shouldn， we should be able just to continue playing the sound。

🎼Normally， so this is the main benefit or not the grab wheel think the independence of the sound system is the the big benefit of what we're going to do in terms of multi thread today。



![](img/6f18f54518e4455428d5825da1c39f49_195.png)

The idea is not very complicated， but it probably will get complicated。

 so I also had my notes like I I did last time。In case they lost， things like that。啊。

But the basic idea is。We have this call， let's open the documentation。



![](img/6f18f54518e4455428d5825da1c39f49_197.png)

Have this。Create。Thread， call to Windows。

![](img/6f18f54518e4455428d5825da1c39f49_199.png)

And this call。We're going to sell a lot of stuff and then we're going to pass。A。

A point to a function， which is the function that this thread is going to run。ok。😊，And well。

 that's the basic idea of it， right， so when we do this。We're going to launch a thread。

 And this thread， if I go to like。I don't know details， performance。Yeah， see。

 so I have like 250 process running on this computer for some reason。And。They have like 3000 threads。

So what we could do is just every time we need to do something asyn name。

 we just launch a thread like most people do。But we want to avoid having calls to windows。

 So that's why we're going to do our job system。 So we have like a fixed number of threads。

And then we can like organize。That。Based on our needs。And yeah， so the beginning。

 we' just going to launch a lot of threads just so you so we know。



![](img/6f18f54518e4455428d5825da1c39f49_201.png)

Just so we know。Well the beast that we are going up against。Any about what can I do， I think。I think。

Well。Can I do a print hint down here。Let me see if I can do that before I run the game。I can。 Okay。

 that's nice。 So I'm going to。😊，Create a thread。 And I'm not。

 I'm not even going to free the thread at this point， because this is like。



![](img/6f18f54518e4455428d5825da1c39f49_203.png)

Stimer thing and when we create a thread， we should encompass a lot of things like security attributes and stack size。

 I don't care about any of that。

![](img/6f18f54518e4455428d5825da1c39f49_205.png)

For this guy。Okay， but what we do care about is the procedure， which is at this guy。So。

I'm going to create， like， a。I specified， yeah， I think in the documentation says how it's going to be it's going to be like do you word winning a guy for。



![](img/6f18f54518e4455428d5825da1c39f49_207.png)

![](img/6f18f54518e4455428d5825da1c39f49_208.png)

This is the thread that。They want us to do and it like a void star data。ok。😊，Yeah。

 then we're going to pass the thread product。

![](img/6f18f54518e4455428d5825da1c39f49_210.png)

And a parameter。

![](img/6f18f54518e4455428d5825da1c39f49_212.png)

That's fast had an O 10。 They you want to print 10。 Well， let's do like。Let's do 10 loops。

 and do 10 threads， and then we're going to see how that looks。

 and then we're going to clean this up。That's pretty much what we've been doing so it works。

So it works for how we want to do。 And the way we're going to do the API just so we be cleared like when we are rendering and things like that。

 we can do like。啊，OS。run a think。Yeah that's like a function。

That's the way we're going to do the API， whichs going to be pretty sweet。I think。



![](img/6f18f54518e4455428d5825da1c39f49_214.png)

So we're going to pass the eye， so that's the parameter。The creation flags。啊。Like here。啊。

Create suspended。 Now， we don't need to create suspended。 and a pointer to receive threat。 Yeah。

 we don't need a identifyifier。

![](img/6f18f54518e4455428d5825da1c39f49_216.png)

可 now。You can't cast into。Thread problems return of value。Okay。

 now let's see if we crash or do something bad we shouldn't do not。Now， if you do print int。

We should be able to print a lot of ints。18chRecently， so I'm going to cast that to a y pointer。Data。

 then I'm going to dereference that point。

![](img/6f18f54518e4455428d5825da1c39f49_218.png)

It know。Okay， nice。I'm going to turn the desktop audio for you guys down like absolutely that guys don't hear anything。



![](img/6f18f54518e4455428d5825da1c39f49_220.png)

So。That was pretty cool， I me just。

![](img/6f18f54518e4455428d5825da1c39f49_222.png)

We got。Some values like you' got two， two， four， five， eight， and a lot of ten。



![](img/6f18f54518e4455428d5825da1c39f49_224.png)

I supposedly they were already a secret so we could do like a lot of threadds。



![](img/6f18f54518e4455428d5825da1c39f49_226.png)

![](img/6f18f54518e4455428d5825da1c39f49_227.png)

I know。 What's gonna happen， yeah。嗯。Well。I suppose I didn't want that to happen。



![](img/6f18f54518e4455428d5825da1c39f49_229.png)

But well。你s got that。And this is a little bit problematic in terms of passing arguments。

 and that's the thing when doing multi threadread。We have to be very conscious about how we pass things around。

We are passing a pointer to an end。And this ant gets changed on this main thread。

That means that when this guy gets to read him。First of all。

 he could be out of scope and second of all， the value changed and that's what we saw。



![](img/6f18f54518e4455428d5825da1c39f49_231.png)

We saw the value changed。

![](img/6f18f54518e4455428d5825da1c39f49_233.png)

So the way I'm going to do is that I'm going to try to copy the whole int。

Chad conversion from int to voice our greater size。Maybe you' like it as 64 at the problem， yeah。

So now instead of passing the pointer to the int， I am copy the int。So。Pretty much you can do that。嗯。

Point of tru。I think I'm just going to ignore that Ronnie。To be honest。I do like build。



![](img/6f18f54518e4455428d5825da1c39f49_235.png)

ok。😊，Okay， now it's pretty cool， let's see what we got terms of result。We got zero，2， four， three，5。

 six，7，9。And 8。It' weird， didn't get a once， so got one， two， three， four， five， six。



![](img/6f18f54518e4455428d5825da1c39f49_237.png)

Yeah， so I didn't get a one for some reason。啊。

![](img/6f18f54518e4455428d5825da1c39f49_239.png)

还掉。Okay。Yeah， maybe got stuck and just lose。 We lost the first guy， which we did。 So yeah。

 now we have all the the guys。 so we can see that they ran out of order in a sink。 Hey Ju see， yeah。

 we're doing a game and see man。 and they out pretty cool， I think。😊。

We're doing like threading stuff today。呃ok。So this is the basic idea。 So see Marcus。

 the basic idea is not very complicated， I mean。

![](img/6f18f54518e4455428d5825da1c39f49_241.png)

We have to be conscious about what we pass and what we read and what we write。

 so that's the main thing。Like this， but the idea is we create a thread and we pass a threat procedure。

 okay？However， in our case， we are not going to whenever we want。Create a thread。

And as for the operating system to do that， we don't want to create like  a thousand0 threads。

 or I'm not going to create  a thousand0 but。We should do the thread managing ourselves。

 so we have to create a job system and the idea of this job system。Nice， I will watch while I go too。

 thanks。Okay， so the idea of this job system。Is to。 we have a queue of things we want to do。

And we have a number of threads associated with thatQ。And okay。

And then we say like I did in the odd example， like， oh。

Add this entry to this queue in whichever thread is available， is's going to try to do that job。

That's the basic idea。So I'm going to like if zero this guy out for per a second and I didn't if zero things enough so I end up。

Rewriting a lot of our test codes for now， I'm just going to zero that so we can keep testing that。

And that's start doing like track progress with like tests。



![](img/6f18f54518e4455428d5825da1c39f49_243.png)

Go back and seat。Yeah。

![](img/6f18f54518e4455428d5825da1c39f49_245.png)

O。😊，ok。没有。嗯。Let's create our。Multi threadreading section here in our Windows file。Okay。😊，Okay。

 now the call that we actually want the game to do is OS like。Do。Work a sink。

And then we should be able to pass。诶。AQ。W you're going to right up now and a prop。Okay。

 so this is the main call。However， we also need stuff like。啊。

I create Q and that's what we're going to start to。First of all， we are going to create。

Couple cus you want to create like an audio one， which is like。这是第一。

The audio doesn't even need to be acute。But I think we may just use that。Okay。

 so the idea is to make the same thing we're doing now with this thing， but in the game。

 so without calling。Window  stuff， right， So that's the goal。 that's the short term goal。 Okay。

 now let's do a win 32。Create。9。可。😊，And。Yeah。And here， we're going to create。The thread， Just thread。

And we're going to say how many threads you want for this skill like， remember。

Then you can calculate the number of threads in the person's computer and then do all sort stuff。

Number of threads。Okay。啊。The thread。That we want to。

The procedure that we want this to actual run is going to be the same for all threads。

I can just copy this guy。And it's going to be like。1 32。

The data that we're going to pass is the queue。😡，And in this case。We can pass the pointer。

 So I'm going to receive。The S call that we32。Call that O S。Yeah啊。

So we're going to pass the queue and we're going to do the wing 32。Thread f。Okay。

 so here if we do like OS block here。We can do like。O。😊，Now， that's great。EOS got Q。I still like。

Different。Okay， so now we're just creating。And。😊，And。And calling data。

 so this is the basic idea but I're going to need a couple more things here。This guy。

 we are going to do an infinite loop， but I'm not going to seem like we're going to wait。

 but the infinite loop is check。There's a job to do。ok。😊，So， like。Like， I don't know。 when 32。You。

Next。All right， job。Okay。So if we should do the next Q job。这 job。Wow， did job。Okay， and else。

 here we're going to sleep。Okay。😊，And。Well， let me think for a bit because the way we want to sleep。

Let's see。 how is that vim。 No， that's four codeer。



![](img/6f18f54518e4455428d5825da1c39f49_247.png)

For codeer is a。Let me show you guys is a free。Coding， text editor， and well。And barco in China。啊。

And it's a pretty good one。You can get it for free or you can pay like 12 bucks and get the customizable version。

 but I just use in the demo version。 It's a really cool software because。😊。



![](img/6f18f54518e4455428d5825da1c39f49_249.png)

It has all sorts of crazy， you know automatic white spacing and that's like virtual white space so。

I don't have to worry about that at all， and I think that's pretty。Pretty nice， Yeah。

 I really like that so。Like we can do all sorts of crazy stuff。And it's crazy fast too。

I would like that。Okay， so the win 32。啊。To next。Do job to take the O job。

We're going to check if there's a job。Yeah。Go to check if there's a job。And the return， like。

Shouldt sleep， So at this point， we should sleep。ではい。ok。😊，And this lead thing。

 we're not actually going to sleep， we're going to wait for the spho to call us back I of Linux， oh。

 it works on Linux too farcodeder。

![](img/6f18f54518e4455428d5825da1c39f49_251.png)

Has the next version？

![](img/6f18f54518e4455428d5825da1c39f49_253.png)

So。I try it out， I really delight it。Although we are programming four Windows because this is a game and most people play games on Windows anyways。

Soオッケー。So the thing is this sleep thing we're going to do here， it's not going to be an actual sleep。

 we're going to wait for the semapho to call us back， which is pretty much the same thing as a sleep。

 but it's like a threaded sleep。So right here we need to create the seore。喂。And yeah， great。Before。



![](img/6f18f54518e4455428d5825da1c39f49_255.png)

For。Yes let's check out this call。Yeah。So there's a cool example in case you want to know like。

的 example。Well， I don't see the example。I think the example is without the EX guy。Yeah。

 using a sepho， so if you want to know more about sephos and writing and things like that。

It's similar to what we're doing， yeah， we're going to use the weight for multiple objects。

So we can pretty much take a look at this guy。But we're going to pretty much write。

That basic idea to get our Q going on。 So create semima4 E X。

 So we're gonna to need to create a semi of4 So this thread can wait for it at this point。

 And I'm going to save that on the Q。 So the Q。

![](img/6f18f54518e4455428d5825da1c39f49_257.png)

三。My4。So， I'm going to create。Real stuff here。 So we have a seapho。Handled。Okay。😊。

And I don't like the win API compared to the next one， yeah。

 well I dont know I don't know anyone who likes the win API。Stuff， to be honest。

 so I'm not going to hold that against you。Thiss like platform。He then depart。

And we do like a platform。

![](img/6f18f54518e4455428d5825da1c39f49_259.png)

Okay， so the Smapho attributes。

![](img/6f18f54518e4455428d5825da1c39f49_261.png)

No need no， don't need to care about security attributes。



![](img/6f18f54518e4455428d5825da1c39f49_263.png)

Initial count。The life must be greater or 0。

![](img/6f18f54518e4455428d5825da1c39f49_265.png)

Is there like the number of。Threads are going to create。



![](img/6f18f54518e4455428d5825da1c39f49_267.png)

What the samepho。

![](img/6f18f54518e4455428d5825da1c39f49_269.png)

Yeah， well， I I think we're going to just pass zero。 and the maximum count is the number of threads。

 If I am' not very much mistaken。

![](img/6f18f54518e4455428d5825da1c39f49_271.png)

And let's see what else we got。Max the name。

![](img/6f18f54518e4455428d5825da1c39f49_273.png)

关。I don't think。Yeah， I care。7。And the flags it's reserved， and must be zero。

 That's the best kind of。

![](img/6f18f54518e4455428d5825da1c39f49_275.png)

Thanks。Desired access， yeah， for the desired access。Who need like the whole axis。



![](img/6f18f54518e4455428d5825da1c39f49_277.png)

Semaphore all axis。 That's what we need， okay。So。Yeah。Yeah， okay， so let's say。We created a sepho。

 so when I'm here， we we go to sleep， what we are going to do is that call that we just take a look after' going to wait。

For a single object， he X。And let's take a look at that specific。



![](img/6f18f54518e4455428d5825da1c39f49_279.png)

Yeah， so see， this is just basically a weight until the object is in a difference。

States of the object that are going to pass is the metaphor for。



![](img/6f18f54518e4455428d5825da1c39f49_281.png)

So this the queue。

![](img/6f18f54518e4455428d5825da1c39f49_283.png)

Semaphore。And the milliseconds that we're going to wait。



![](img/6f18f54518e4455428d5825da1c39f49_285.png)

That's a great life。Until they wake us up so let's do like。



![](img/6f18f54518e4455428d5825da1c39f49_287.png)

And alertable。If this experiment is true， the thread is in the waiting state the function returns to the system。

嗯。Slled by fire legs。

![](img/6f18f54518e4455428d5825da1c39f49_289.png)

哎要回给你。Okay， so we're getting somewhere， so now this is our the do actual the do job kind of thing。

So what we should be careful is the thing that we took a look when we first did our test。

 our thread and test。Here。Is that if multiple people are trying to access the same data。

 we're going to have a problem。So since we have a queue。Here。

 we have to be careful to make sure that。We are reading and writing the correct stuff to the queue for that we're going to need the atomic operations。

 I'm going to take a look at that now。The base idea for the atomic operation。

Is we have stuff like interlock。Exchange。We're going to compare to that's that's what we're going to make。

 So that's thing that we're going to compare to。The one that we think it's the correct one。

 as well as the one want to put in there。 So if anyone changed。

Values in between like us preparing our stuff， this is not going to work。 So this is the basic idea。

Okay， so。I should have， like。They are next entry。3 read。Hand like and in tree count。一年。And actually。

 the entry count just going to be an array。This guy， I'm going to do like U 32。

 I' mark that as volatile。哇。茶よ。Because is it play for the compile to take a look at people probably going to keep reading and writing that a seems？

So。Next， anchor to read。And we're also going to need astruct。Fday。OS job。Yeah。And we have a data。

 which it's whatever the game wants us to do。Right。😊，That's a。The main thing。And。Maybe that's it。

Let's go step by step。We have the next entry to read， and that's called that the original。Next。Okay。

And now， the next one。That's the one who want to set to this guy。Next entry。

We want that to be the original that we just read。Plus one。

But we're going to wrap same thing we did like last time in the time that we're going to wrap based on the array count for the Q entries。

So let's create an name tree。I like doing that on the。This。呃。Oh， that was weird。Okay， so OS jobs。

That' the entries， let's do I a know。I say 32 jobs。Maybe we're going to increase that。

If you need more。Yeah， I don't really care too much about that。Okay， so。

This is the value that we think is inside of here because for all we know。

 the value changed by this time。 you know， we don't know are apps that are not games popular on HIO。

Well， usually it's apps related to games in some way。So。Well。

 four code is there probably because people write games in it。But yeah。

 tax editors and programming stuff， but there are a lot of non games on HIO。Yeah。

 it's pretty cool I like that， but because each child makes it really easy to distribute stuff。

They're awesome。Yeah， okay， so a volatile。 Yeah， so so this guy is the one that we want to put in there for the next one。

So now you're going to do that。Interlock compare change thing。In in fact。呃。Yeah， okay。

Because in my notes here， I'm just going to tell you guys I have what I should test if the original is not equal to the next entry。

Because if it's not equal to the next century。It means that someone already messed up。

Our we're gonna we're going to step of this later on， but let's just continue what we're going。

 So we're going to do the interlock。Compare。Exchange。Okay， in this call。



![](img/6f18f54518e4455428d5825da1c39f49_291.png)

Let's see if I can get the documentation for。I made an easy lamp for HI， That's awesome， dude。

Is it like the library is on each。So。This is the theme， we want to change this value。

The output value， yeah。We'm going to put this value inside this guy。Only if this guy。



![](img/6f18f54518e4455428d5825da1c39f49_293.png)

Is't there。So if nobody changed accidentally， well not accidentally， like in between these guys。

We should be able to just keep going and then returns。



![](img/6f18f54518e4455428d5825da1c39f49_295.png)

But the original guy so we can test these guys。

![](img/6f18f54518e4455428d5825da1c39f49_297.png)

So yeah， that's what I'm going。嗯。Original value， Let's call that original。Let's call that。

Internal light。Okay， so we are going to pass a pointer to the queue next。Entry to read。

And we want to put the new entry there。How a new entry to read。APpiI of each other。

 I can do anything you want。Oh， that's cool， man。I didn't actually know that was a thing。

And never used it too much， but do are nice。That's called API。

 you can do anything you can do it just click on the web。关P APII哈。That's nice。

I may take a look at that later。do we have a link for that？はい。For well。Yeah。

 it should be new ancienty trees。Okay， so I'm going to put this value in only if the original value is in there。

O。😊，That makes sense。Now， if the value that we just read。Interlocked。嗯。😊，To lack to value。

If they're interlocked value。Is。The original value， because that's what it returns。

 it returns like the not the changed one， returns the original one， yeah。

So if this guy is the original value。It means that we've got to do the work。O， so we。Get to do。Okay。

So in order to do the work， that's going to be， pretty simple。We're just going to call。Oh yeah， well。

 we need also the call back here。So this call back。Let's do a attack death。Let's call that O S。

Job call back。And I don't think it's going to return to anything。

 I don't think it's just going to be like。喂。And the callback is going to have a queue。Thanks， man。

 for the link。So， yeah。We have a queue and we have the data。Job will ask you。 Do already have it。

I'll call back。嗯。Name type definition。嗯。What is the problem again？I always。

I always forget about this。This type there。For function pointers。So attack that void。This guy， well。

 this looks correct。To me， in terms of the syntax。Name type definition in parenthesesis。

It's not definition just using。It's a new link compile off to my C plus plus。 That's awesome。

 I think we could use a new language。😊，Like jump blows JI。That could be cool。

 maybe I just misspelled this guy， I don't know。Name type definition， in。

I have no idea what that's supposed to mean。Like， let's copyied this guy。You' like F。Okay。

So let's dev void OS。Job， callback。Okay， now let's take void。Pointer。Daタ？ok。

And we want a O job entry queue， a job queue。But we're not defined yet。We need to pass that as。Sure。

Hopefully I'm not going to get started there for like。Years。I just see， yeah。

 so at this point it works， so I think I'm just going to preecclar this guy。And do you like。

And then I's try to with that。Still nothing。I can reuse sea code， so I learned a bit of sea。

Do another stuff， yeah。Well， C is still very much used， not just for like embedded systems。But to do。

 like， the real。Really fast code like for gaming engines， they do like little bit C for that as well。

Come on， guys。I don't want to get stuck in this guy forever。 I don't know what the problem is。

 I may just cheat。And look at the other game。诶。Yeah， he struck this guy。Let's try doing this guy。

Because I'm doing the define here， which I was supposed to do later but。Oh， is the name and then？No。

 it's white in the name。O S drugQ。Oh the semi， no， it's not the semi column。

So it is this guy that has a problem somewhere。嗯。Cs King， yeah。呃。I have no idea what the problem is。

I could really use some better error messages at this point。Like。

Thelaration of Kew Heights Global Decation。Why does this thing this a global decor？Okay。

I have no idea。What the problem is。That this guy's complaining。Well。

 let's do like something I used to do when I use other people's tool and that's just。



![](img/6f18f54518e4455428d5825da1c39f49_299.png)

![](img/6f18f54518e4455428d5825da1c39f49_300.png)

The fact F iss in the wrong place。What means。He's just laying around here。As a global guy。Now。

 let's best stick this guys out。We're actually for the tech。

I can't put the type F after the job queue， which probably that's what you mean。 It works， right。

 But I can't do that because I need to use this guy here。 I have a pointer to the。OS job callback。

I need that pointer here。Well， maybe I can do it like。Yeah。Okay， so I suppose。I suppose， yeah。

 that's better。Oh， well。Thanks for a tip puzzled。I was puzzled and I would probably gu be like there for a while for for your help so thanks。

 thanks a lot。Okay。So let's keep going volatile long difference in volatile U 32。

I suppose this is also volatile time。有接点啦。Well it take long。S the U 32。 Well。

 but which one is this this guy？Yeah。Next entry to read。Unclared。New。O。Okay。

 we're getting there slowly so now we get to do the work， let's do the work。We have the queue， right。

And well， we wna call it cow the， the the callback。With this data。And this cute。可以。😊，Yeah。😊，Yeah。

 that's about it。So啊。Let's just make a point of the entry of the QO OS。Job， well， that's a bad name。

It's called that country。This is just going to be the。The you。A。Correct。Yeah。Plus， the next entry。

To read。哦。然后带上来。Thank you。😊，Entries。啊。Plus the index， which is the inter value， okay？

Now if you do entry。好 back。😊，Like this。Let's see how do you look。k机。Unced identifier。No。Yeah。

 the data is actually the。吹。O。😊，Term does not evaluate to a function taking 258 arguments。Well。

 I hope not。Better。ok。That's， that's certainly weird。Yeah。Entry callback。Which is。This guy。O， oh。

 it's not astruct。So。I don't know if I solved the problem。The type death。

Because that' I can't say short to here， I know。I don't know what I did there。It is a， it is a。

Let's check out。妈呀。My cheat here， my cheat code。And。下次。YeahThe callback。I define that。First。好买。

Can I find that here。C。😊，Puzzled if you could help me get less puzzled。Because。😊，I don't know。

 This guy has to be first。I don't know， man， this guy has to be first。

So the type F in the wrong place， I don't know。Where else I could put the guy can't put at him after this guy。

And since I have like a 32 jobs here， this guy has to come for this guy。So， I think I'm gonna。

It of a order dependent problem here。Ststruct O S DQ。 I don't。 I don't。 I really don't see why。

This guy's not working。Because。I'm just saying， okay， I'm going to use the pointer to disrupt。

 not even thestruct， the pointer to disrupt。Nmetime definition parentheesis。



![](img/6f18f54518e4455428d5825da1c39f49_302.png)

That's go her。This guy， but this has like nothing to do。That's what I'm doing。



![](img/6f18f54518e4455428d5825da1c39f49_304.png)

They玩。Dude。That's the warning。That's what I guess for using warning as errors。Come on。Okay。嗯。Yeah。

 well， I know I feel a little bit bad。amount of time。 but that's let's keep going。Okay， so。

Now we should do the queue， and I'm also going to save the completed index because we might want to check if we completed the jobs that we want to do or not。

But I think I'm going to just do that as a comment for now。Completed jobs。

So they are fantastic if we are done or not。ok。😊，So。Should sleep。In this case， I shouldn't sleep。

Because I did some work and in this case I should sleep。That way were wrong。ok。Yeah。好吧。Okay。

 so I should sleep and should。So。This is done now all we need to do now， well。

 let's see if this is done。We do and then we wait for a single object， well。

 I think that's a product she seeing yeah。And then we do the next work。Yeah， that looks correct。Now。

 we need the actual call。That we're going to use like OS the work I。That's the last thing we need。

Let's put that。Everything else。Okay， so this is what the game is gonna do。

 And we already have a queue， is O。Job queue。And we already have a PRc， which is a OS job callback。

And should pass the data， probably。O now。You're going to all you have to do is just to add a new guy there。

And。And we have to be careful because this is like as work。

So pretty much have to do the same thing we did for。 So we're going to have a new next。Entry。😊，Oh。

 because we have like an entry to read。You also do it an entry to write。

Because now we're going to write angels， so same thing。谢听不见。😊，The volatile。Next entry to right。

这 to be theQ。Next entry。Two right plus one。With a modo， with the array count。有ね。可。😊。

And and this is the point where we assert。You see that the next anchorker right。Is a。

ItsSmalll than the later we are reading， correct。Like， if you， if you're writing to the。To this guy。

We shouldn't be reading the out。小Q。Thanks。😊，有异。And this should be fair。

 It should fair when we have a。Sa。没。A small。Okay。嗯。Now有。We should now have the correct next entry to。

 right。Now， let's。Write an entry， right， so we have a job。你确定。

And it's going to be something thing like Q。Make sure you plus the queue。Next， Andrew to write。

This is the job that we want to。To fix， then we're going to set the callback。The callback。

m set the data。Okay， and I'm going to place the right barrier。I believe that's how。但是。Thererier。

So this kind of is a flush to all the threads。So， yeah， okay， so。Q。Neck noon。To read。All back。

I call that pra。 also call that call bank。ok。😊，Now we should have set the correct guy at this point。

And now I'm going to do is set the next entry to right， since you just put the right barrier。

 we can do it that pretty。To the new。

![](img/6f18f54518e4455428d5825da1c39f49_306.png)

Next entry to write。Okay。😊，And now if go back to our Sepho guy。We need to release it。Exactly。Yeah。



![](img/6f18f54518e4455428d5825da1c39f49_308.png)

Because we。For the queue。Symapho， we added one more guy。系。Okay。

So I don't know if this should work or not。I'm going to have to debug that pretty carefully。

But hopefully。

![](img/6f18f54518e4455428d5825da1c39f49_310.png)

This has the same effect， so let's go back to our first system。



![](img/6f18f54518e4455428d5825da1c39f49_312.png)

And let's try to do this guy。Here's in our immune system。First of all， I'm going to create。Q。

And I're going to pass a OS。墙。晓。使代。IPa a point to that。I'm going to say like create like two threads。

And yeah， that's my。That's it。Now， we should be able。In terms of life。Just as like E。And and， and。

Do work a seek。Should you like， add。Job。is cute。And then I'm going to create like a print。1加2。

And I'm want going to pass a number， so that's do。And I did the same。But this time's going to be。

Platform， independent， well。So yeah， too。Ad job to Q， probably。A draft。Okay。

 and I need a pointer to the queue。And we need to create the print app。When we go ahead。

 we need to create a function of this type。So it's going to be like。唔会。Print。加。

And I have to take the same thing。This guy。 So to make it easier， that's why there's a defined guy。

 right， So I'm going to define。A job callback。Go to get a name。 And I'm going to。Good this guy。

Just so it makes it easier to。Yeah， instead up doing this guy。

 I'm just going to do DO O job callback。The print。job。Okay， everyone called print int。

And remembering that data is a parameter。Okay。😊，Do I need the queue here？

I don't think I need a queue。OO好。嗯。哇。O。So let's go back。This guy。😊，ok。

So pointium is matched for parameter three。Okay。

![](img/6f18f54518e4455428d5825da1c39f49_314.png)

I'm just going to see hope and see works well it doesn't work so。We're going have to。Didbu that。

 but we were supposed to debu that even if it were， so not going to complain too much yet。

Probably did a couple mistakes because we wrote。那边口笑。First of all， let's create a queue。So。Well。

 it's also zero that。

![](img/6f18f54518e4455428d5825da1c39f49_316.png)

嗯。Do you have the series strength？

![](img/6f18f54518e4455428d5825da1c39f49_318.png)

We do。Okay， so。OhWe zero thestruct and then we create a semapho that looks like a valid one。

Of two threads。

![](img/6f18f54518e4455428d5825da1c39f49_320.png)

And then let's create the tooth Oh also。你销售。Re呃。Let a release。 I see here。Close handle。



![](img/6f18f54518e4455428d5825da1c39f49_322.png)

Okay， because since this guy's going to be in an infinite loop。We really don't care about。ほ。

About a reference to it， Okay， so that's great one guy。Let's close。Let's create another guy。 Okay。

 so these little icons show that we change threads， so。This is the our thread。Which is good。

Now let's try to do Q for the next job。So we get the Q。It was like a valid queue。But has no entries。

Okay。So the next is zero。Well， we went back to the other guy。取消。The next zero in the new is one。See。

 that's the thing we want to check。That was the if that I was uncertain。

 we have to check if we actually should be。Doing work。Yeah。



![](img/6f18f54518e4455428d5825da1c39f49_324.png)

But。I'm just going to。Just quickly check this out here。On the say next。

WeCheck out if our entry to read， yeah。We have to check if we wrote that。行。😊，呃。Original， next。

It's different。On the queue， next。Entry to right。meansan that we wrote something here。



![](img/6f18f54518e4455428d5825da1c39f49_326.png)

Do that。 Otherwise， we should sleep。行。谢。So we're going to run this guy。

The original next is zero and the new one that we are reading that we should read this one。

 but since we haven up 10。Oh， we already， okay， we already added 10 guys。Nice。

 So now we should be able。就。And so this next entry is 0。I should be one。It is one correct。Now。

 if it is equal to the next， which is， it means that we got to change this guy。Okay。

 so we changed threads here。嗯。Okay， let's take up the reference here， okay。Oh。

 thiss going to be little hard to so the entry。Has no data， which is wrong。

But it does have the print job， so I think we've just forgot to add the data。



![](img/6f18f54518e4455428d5825da1c39f49_328.png)

When we added the entry。We did added data。

![](img/6f18f54518e4455428d5825da1c39f49_330.png)

Well， that's。Let's go back and see。The entry， oh， oh， it's zero because the first number is  zero。

 okay。So and then。Yeah， we got the first guy。They're going to call the callback。

 So this is what we're doing。 And we're calling the guy with zero。And it returns false。

That means that we should now try again to do another job。And now we should， yeah。

 so the other thread already did like 10 jobs。And we now should probably not do anything。

 so we are going to wait infinitely。I think our job system worked。



![](img/6f18f54518e4455428d5825da1c39f49_332.png)

![](img/6f18f54518e4455428d5825da1c39f49_333.png)

Let's try to see that with no break points。

![](img/6f18f54518e4455428d5825da1c39f49_335.png)

That was pretty cool。One，2， three， four， five， six，7。

 and it wasn't a more correct order because we only have two threads if we do like four threads。

 probably。

![](img/6f18f54518e4455428d5825da1c39f49_337.png)

It should be in a less correct order。 Let's， let's see。



![](img/6f18f54518e4455428d5825da1c39f49_339.png)

Yeah， yeah， okay， so that's better。I mean， better in the the sense of what we are doing right so this shows that we're doing that all threaten that so0。

2，3，4，5， six，7， eight so the one got like for a long time that's no problem because the other ones were working for it。



![](img/6f18f54518e4455428d5825da1c39f49_341.png)

![](img/6f18f54518e4455428d5825da1c39f49_342.png)

Okay， dude， that was great。Just for the fun of it。Instead of like。

 when we tried to do a lot of threats， this guy hung for a long time， hung， yeah， hanged。

He hangs for a long time。

![](img/6f18f54518e4455428d5825da1c39f49_344.png)

Let's tri to100， which we should assert。Because we don't have 100 entries， well we didn't assert。



![](img/6f18f54518e4455428d5825da1c39f49_346.png)

Oh， maybe we did them so fast。Yeah。Well。I's tried doing 1000 entries at some point。



![](img/6f18f54518e4455428d5825da1c39f49_348.png)

We should have triggered that assert。It didn't， and it looks kind of correct actually。



![](img/6f18f54518e4455428d5825da1c39f49_350.png)

嗯。So you're going to have to debu that。Later on。But for now， I think we can start using， really。

It's called that Earth right？We can start using this guy on our audio system。



![](img/6f18f54518e4455428d5825da1c39f49_352.png)

Which is going to be a nice test to see because if you guys remember。



![](img/6f18f54518e4455428d5825da1c39f49_354.png)

firere。🎼Turn the volume up here。こん。

![](img/6f18f54518e4455428d5825da1c39f49_356.png)

For some reason， if we hang like let's let's。有啊。Now that's。That's not like a mouse again。

 and let's hang。

![](img/6f18f54518e4455428d5825da1c39f49_358.png)

🎼。

![](img/6f18f54518e4455428d5825da1c39f49_360.png)

So we should be able to do this and not hang。Okay， that's that's the goal。

Of making the audio easy for now， and there are a lot of other benefits。That's like one at time。

So the audio thing that we should call in parallel is just this this guy， really the update audio。

So this guy， I'm going to pull that off a。functionction。And call that。32。Well， in fact。When I。

 when I edit the audio。啊 you。Do this。I can already， like， O S do。Add job to Q。

And you're going to create like an audio queue。I mean， it shouldn't actually be a queue。

 just a thread really， but I'm going to add like  going 32 update。Audio。

And I don I don't know if I need any data like Sp zero for now。Okay， so。In the audio。

 which should actually be。After the。The vote threading， we're going to do like OS job callback。

3 to update audio。Nice。Let's see what happens。Yeah。

 so we need to do the whole audio thing after the most thread thing。Last Dt。

 So instead of using the last Dt。I am going to set。The target Dt。

And let's say we're going to try to update the audio。This amount of time。

 and well probably get that later on。So。You没 to。Use the target E。Audio queue。

 so we do need to create a queue。For the audio， so。OS job Q。好，你。Q。And we'm going to do the。32。嗯。

create。开始。And I'm going to pass one。And。Yeah， well that's only it。 Yeah， okay。

Let's go back here and let's see what we have， so。This is a target DT。

So I'm going to do that forever。And now I should sleep here。Okay。😊，And。One frame。

And when you is a target D T。And the expected bites maybe be。DT。So it is Marcus。

One frame and play around with the safety， maybe we don't need any safety at all。Who knows？

So the amount of time you're going to sleep。It's like the elapsed。Time minus。你啊。The target。

How was the target？Okay。😊，Now let's calculate the eapseed time elapsed。Time。And let's do， like。

132 seconds。Alex。Thats passed like the last。好这。And same thing we did。

 we're going to like in the beginning， we have like。Large integer last。Conner equals to。嗯。改这方。ok。😊。

So we get the last time and then we set the last counter。是第。啊。And ask you this helper function。

Second to left。I。下午。Maybe you can be online line。32。Seconds， last。

A you going to receive a large integer。Any fact we can。That's what we need。So。た感。Al next。Yeah。

 well a need to work on that。A bit more， but as for the time。Turn at 32 current counter。 we have two。

Large。Did your。Co well， we're querying for the current counter twice， right？I take picture here。

Cmment to counter。NowLet's do the。Just forgot to call the call again。Counterque funds。Okay。

Syntax error。Frequency counter。Let's make that up。B for now。嗯。just make sure。

And we set the frequency counter。Before we do the audio stuff。Okay。😊，嗯。😊，是利店 so。

We could probably be a little conservative about that， maybe。Track to one。

Frequency conversion from F2。They were fastastic。 That's weird。好。啊，错的一。Okay。Okay。Frequency看。Yes。Okay。

 let's。

![](img/6f18f54518e4455428d5825da1c39f49_362.png)

Let's debugging that to make sure that it works。So the last counter。

And we do all the safety bike stuff。And then we call the update guy。And then。N to sleep。



![](img/6f18f54518e4455428d5825da1c39f49_364.png)

You know what？诶。We should really like。Do that later slowly so。Now， let's call that。Okay。😊，-1。

And this is actually going to be。对。The maximum of zero in this guy。So we don't get like to sleep。

We don't overflow the buffer and sleep like for a long time。I don't like sleeping too much。



![](img/6f18f54518e4455428d5825da1c39f49_366.png)

Let's see running the first guy。The tragedyged DT in the e time was fine。 Oh， it was oh。

 it was very small。 so we should sleep 0。

![](img/6f18f54518e4455428d5825da1c39f49_368.png)

Oh， because this is in seconds， this meiseconds。几数。So going to do it like。Thousand。呃。Times this guy。



![](img/6f18f54518e4455428d5825da1c39f49_370.png)

15， that sounds perfect。Because we were spent like just a little time doing this。

Maybe you can can use that thread for other things。

But six are not going to be super multi threaded just for the rendering， I think。

 and some reading though。I don't think Id care about that。Go going to sleep。And then。历史。

What do we have？

![](img/6f18f54518e4455428d5825da1c39f49_372.png)

So we do have audio， oh， let me unlock the mouse to last。



![](img/6f18f54518e4455428d5825da1c39f49_374.png)

🎼。

![](img/6f18f54518e4455428d5825da1c39f49_376.png)

So。Well， let me give you guys the correct audio and I'll turn this one down。



![](img/6f18f54518e4455428d5825da1c39f49_378.png)

So as you guys can hear， probably。🎼Even when I。JustPvent the game from updating。

Like grabbing the window and this can happen like in all sorts of crazs like not only the grab window。

 like if I have a super low frame rate， like I make it full screen and have a very low frame rate。



![](img/6f18f54518e4455428d5825da1c39f49_380.png)

![](img/6f18f54518e4455428d5825da1c39f49_381.png)

🎼です。🎼Or a。If I do all sort the crazy stuff with a window or if I there's a window update and it hangs。

 whatever。

![](img/6f18f54518e4455428d5825da1c39f49_383.png)

The audio doesn't care because we are running asynchronously， asynchronously。In a synchronous way。嗯。

So， I'd say。That was a huge success for today， huge one。Because we implemented， not only。

The threading。But the whole arms。The whole job system。That was great。 So Pror。😊。

Maybe a think rendering。Just now that we have the。Tools， you can do that。And then。We should also do。

But they'll being the polished fans。Maybe we'll do3。32 floating print colors later on。And yeah。

 the next thing we'm going to do is file Io。For saving unlock levels in high scores。Well。

 we did we do we also fire writing because we already have firewe so UI so we're going to do show timers。

 partsy balls， whatever menu。Okay。表。Cool， and then。We can also implement the sound effects。

And just finish up with the audio， maybe I'll do that if we're going to do the file writing。

Thiss the last thing we need for the engine。 Then I' go and do the audio， then go to the UI。

 and then we do better levels， few stuff。Nice cleanup and let's do like more levels。来bos。

And a polished bra。Which I don't， I don't。 I don't know if we're going to do that。

 thenre not going to do the。 Oh， yeah， we also。At this point。Implement sound effects。And music。

And some effects， it maybe going to do like make。I think， because now it's pretty easy for us。

 I think O G G。Readter。Because OGD takes a large to decompress， we can do that AC personally。

Doude that words its hard to say asynchronness ace。诶星。turn those asly。Or maybe asly， ascly， yeah。

You can make an async OGG reader and then play around with these guys as well。

So we have file writing next time， it's going to be a quick screen。And then we do the audio。

 it's going to be a longer run。And then we go back and then maybe we do the when we do the profiler。

Decide to make the renderry。We do the cooker， and then we do the game。 Du， we are awesome。

 Let's do some cleanup。 I don't， I don't。😊，I don't know if you're going to keep the test here。Yeah。

And let's also delete。Like。This guy was just for testing， a up to Q。And。

Discusaging in the platform independent。Part。But let's put this guy touch。And don't need to test。

Any more。P farm， common。I了。What the breakout game。Ptform services。Yeah， we also do like the O S and。

Like this。But the again can now do。Okay， now I decided to wait。Okay， so now the game can also do。

Called this threading stuff so next time'm around we're going to do we're going to save the score and save which levels the player progressed。



![](img/6f18f54518e4455428d5825da1c39f49_385.png)

So yeah， we're going to。So working on， that's hard stuff。



![](img/6f18f54518e4455428d5825da1c39f49_387.png)

And also。Just some ideas。That's the game。When we do， like。Make my first。 I can make。

The power up and down。That's say scale pilot。

![](img/6f18f54518e4455428d5825da1c39f49_389.png)

O。We are coming a long way， guys。It's great to work on these engine systems because it's hard like。

Getting， well， today wasn't that hard， but yesterday it was pretty hard to get the other working。

🎼And。AndOkay， so it's also a very iterative process， sore going to improve the audio as we go along。

 right？🎼So yeah， okay。But I once you get that to working。

Our game gets so much better and we are very confident in terms like when we come up。

Not come up with bugs when when we see bugs， right， yeah， come up with bugs。

I're going to make comfort blockss and spray that way。It's going to be way easier for us to fix them。

 right？🎼Because now we know the whole system because we wrote it on stream。



![](img/6f18f54518e4455428d5825da1c39f49_391.png)

Okay， so I hope you guys enjoyed today's multi threadra stream。 We did a pretty complete job system。

 I mean someone said， oh， do you guys can stop jobs from executing？I don't think we want to do that。

 we're going to end up having like three cus， I think， which is the audio one， the rendering one。

 which is like the priority queue， and we're going to have like a low priority one。

 which I like to load assets， thing like that。Music to decompress OGGs。

There'll be enough for our motor threadreading part of the engine。

 but we we also should do the profiling quickly because we shouldn't like optimize the render or anything like that without profiling。

 but the OGG will be pretty slow so we're going to have to make that a seamless。Okay。

 I hope you enjoyed today's stream message we did if you want to check out。



![](img/6f18f54518e4455428d5825da1c39f49_393.png)

All the live streams from the very first one， it started with a blank file。

You can go and just drink some water。You can go to my YouTube channel， which is YouTubebe。com/danzad。

And you can watch the whole thing ever since the first episode。

 we started out with a blank file and every line of code you saw。😊，Im implementing here being typed。

 we fixed all the errors that happened and all those sorts of crazy stuff。

And you can see the whole process and you can also download the game and the source code for free on Ho。

 so you can click here in the game on Ho is Dan。h。o。



![](img/6f18f54518e4455428d5825da1c39f49_395.png)

![](img/6f18f54518e4455428d5825da1c39f49_396.png)

Click download now and you're welcome to give me a tip。

 but you can also just download and you can download each day separately so。



![](img/6f18f54518e4455428d5825da1c39f49_398.png)

![](img/6f18f54518e4455428d5825da1c39f49_399.png)

You can download each day with the Executable and the source code。

 and I'm going to post todays day now。

![](img/6f18f54518e4455428d5825da1c39f49_401.png)

Okay， so I hope you enjoyed and I'll see you next time to make a more complete engine due to this fire writing and and reading to create our safe system to save our play high scores and levels and all sorts of stuff so I hope you enjoyed it as much as I did and I'll see you next time see you then。



![](img/6f18f54518e4455428d5825da1c39f49_403.png)