# 【从零开始用C语言制作游戏】 p20 Making a game in C from scratch! Ep 20： -Animated Level Transitions -BV18i421a7DD_p20-

Hello everybody， welcome to this new live stream where we are creating entire game in from scratch today is live stream number 20。

That means that we've been doing a game for quite some time now。In live stream episodes time。

 if you can say so， and the game has come along pretty nicely and it's about time we start wrapping up the game so we can publish it hopefully and that'll be a good challenge。

 right？So let me show you guys what we have so far。What we have made in these 20 live streams。



![](img/ffd282b2d431f9765c707d3effca38b7_1.png)

So this is the game right now， in fact。

![](img/ffd282b2d431f9765c707d3effca38b7_3.png)

You just revert the source control because I usually。see I usually。

Rename and pack these files together so we can。So I can build a game properly for HIO。

And I just going to revert through the episode what we had。



![](img/ffd282b2d431f9765c707d3effca38b7_5.png)

And this is what we fit in， right？🎼い。So we have a breakout。We had screen shape， it's pretty cool。

 we really did the whole pro system and I think it's pretty good for a ship。😊，And yeah。

 I think there'll be enough and the screen shake。🎼T蟹谷子 awesomesome的 shityou know。Read really really。

They have super breakout power ups。Pllph， Alex。🎼And we have palm。

🎼And Bo is now pretty cool when we had a like a screenhe。😊，🎼When呢 can很你你 edge。いやいんだねレマ。Pares。

Which is the newest edition， I had some ideas about how to protect。🎼Py that to run better。

And Space eers。Which is the craziest。You know。接死。

![](img/ffd282b2d431f9765c707d3effca38b7_7.png)

Pretty cool right if you want to download the game and the source code for free。

 you can go to my HO page， which is dZ。o and download。



![](img/ffd282b2d431f9765c707d3effca38b7_9.png)

Youick the first game here and you can download the game in the source code。



![](img/ffd282b2d431f9765c707d3effca38b7_11.png)

And do whatever you want with it， that's the license， you can do whatever you want。



![](img/ffd282b2d431f9765c707d3effca38b7_13.png)

呃。And just click download now you're reference to give me a tip。

If you want to or just click no thanks and then you can download each episode source code separately。



![](img/ffd282b2d431f9765c707d3effca38b7_15.png)

Okay， and in the YouTube channel， which is user。com/d say Dan， hey man， what's up。

 nice to see you here again。He's wrapping up some introductions and then you can get started。

 it's going to be pretty cool today， I think going to wrap up the gameplay hopefully。

And on the YouTube channel， you can see every day I have live streams started from the first day all the way to where we are now。

 so 19 on YouTube， this is number 20。And I think we're going to go maybe up to 25 I'm thinking which was the original plan so we're good at stick that schedule right in a good sense and you can also watch my tutorial series about how to do the game where I explained step by step everything involved make the game right and the stream more lava let's just sit down and make game kind of thing although I do explain if you guys have any questions be sure to drop them and chat as well。

😊，Okay， so I made a few notes by playing the game。

![](img/ffd282b2d431f9765c707d3effca38b7_17.png)

Now things to change and improve in this。And there's a wrap up thing that we're going to do today。

 so yeah， we want to do more field stuff。Which is the manual transition。

And Ru has the player and then we can improve the Ttririss gameplay also。

 and a couple of ideas that to implement the tttris was to making the game over when the block hits the end。

 I'm just going to destroy the block and lose a life so we have three chances of getting the blocks to the end that'll be a little bit better I think。

And I had a pretty weird bug of the game over not zeroing this score。How about we start with that？

So as far as I remember， that's pretty easy。

![](img/ffd282b2d431f9765c707d3effca38b7_19.png)

🎼Sure be great。 So I just yeah see， I have three。And score and then。Still have three。



![](img/ffd282b2d431f9765c707d3effca38b7_21.png)

Yeah， that's certainly。Not okay。 So in the game over。Oh yeah， I think we just。Yeah， we didn't。

 so this is trauma。If we zero it here， it may work in almost all cases。Oh。

 we can probably just change that in the advanced level， I think that be okay。Yeah。Yeah。

 if we lose a life at the end of the frame。I'll start game， Shi really。Yes， start game。

 I think the one that can0 the。Yeah， that correct。

![](img/ffd282b2d431f9765c707d3effca38b7_23.png)

O。😊，I think they'll do it。

![](img/ffd282b2d431f9765c707d3effca38b7_25.png)

🎼ち。Perfect。

![](img/ffd282b2d431f9765c707d3effca38b7_27.png)

Okay， so that was a pretty quick fix。And another， I think it's another game field thing that we want to do。

 we want to make the game slightly slow motion。When we hit a block。

Last time we played around one motion to debug things and that was a pretty cool。Change， right。

 Dt multiply and we already have a Dt multiping here。So all I have to do。

Just to make like the DT multiplier。Move towards one。

Let's move towards Dt multiply and moving towards one。Let's make the rate of DT。

 We can make that faster later on。So right now there should be no change。

 but now every time we destroy a block， so just destroy。want this stride。

See you respond spawn the explosion and I'll actually just do the test。

While we conditioned be I want to increase the score。Is also see the D T multiplier。

Make that minus equal。

![](img/ffd282b2d431f9765c707d3effca38b7_29.png)

I have to play around those values， but the idea let's see。🎼いい。



![](img/ffd282b2d431f9765c707d3effca38b7_31.png)

可。Let's try。0。9。

![](img/ffd282b2d431f9765c707d3effca38b7_33.png)

Let's just actually said that。

![](img/ffd282b2d431f9765c707d3effca38b7_35.png)

Oh yeah。🎼欧耶欧耶。

![](img/ffd282b2d431f9765c707d3effca38b7_37.png)

My god。What happened。Oh， we didn't actually compile。Oh， so we started out like bids， right？



![](img/ffd282b2d431f9765c707d3effca38b7_39.png)

Yeah because we decreased， so we got negative。🎼。So this is kind of the idea， but。



![](img/ffd282b2d431f9765c707d3effca38b7_41.png)

This should probably be a lot faster， Mike。Time thing。 should you're a really small thing。



![](img/ffd282b2d431f9765c707d3effca38b7_43.png)

う。Yeah。い？

![](img/ffd282b2d431f9765c707d3effca38b7_45.png)

You know what I think we're going to do like we're going to get the max。Of 0。1。 And this guy， minus。

one。And I actually I'm going to make this guys slower again。

So we are going to decrease every frame up to 0。1， every frame， now I mean every block destroyed。呃。

So we probably chain things together， so in the normal case， we shouldn't even this yeah。



![](img/ffd282b2d431f9765c707d3effca38b7_47.png)

And even three。How isn't that？🎼哦， to第 other个 side。う。If they can do like some more crazy math。

 let's see the comments。Let's see how it come works。オッケーで。That was interesting。



![](img/ffd282b2d431f9765c707d3effca38b7_49.png)

Not sure。I think到。Let me' going to make that a little bit。The match like 0。15， however。

 I am going to decrease the DT multiplier。By something like。I don' know，5040% of the 18 multiplier。



![](img/ffd282b2d431f9765c707d3effca38b7_51.png)

🎼安しい。So I want to feel that a bit。すい。🎼maybe before it was too much。Are you with that？うん？



![](img/ffd282b2d431f9765c707d3effca38b7_53.png)

But let's just check out the comment。

![](img/ffd282b2d431f9765c707d3effca38b7_55.png)

Oh。うん。Maybe you're showing change that。不 got他扛我。

![](img/ffd282b2d431f9765c707d3effca38b7_57.png)

Yeah afford is way too much。Maybe you can do like point one。But only if， let's see。

Only if you a touch this bonus， so only touch this bonus later。



![](img/ffd282b2d431f9765c707d3effca38b7_59.png)

![](img/ffd282b2d431f9765c707d3effca38b7_60.png)

So now one block should do nothing。Let me print this guy。



![](img/ffd282b2d431f9765c707d3effca38b7_62.png)

Just so we can't make sure that it's correct。晚安。🎼也血。Don't change that。🎼nice come。



![](img/ffd282b2d431f9765c707d3effca38b7_64.png)

啊。Well， it's greater than mono early test。It's greater than 0。



![](img/ffd282b2d431f9765c707d3effca38b7_66.png)

🎼オッケー？

![](img/ffd282b2d431f9765c707d3effca38b7_68.png)

🎼n这呀。And。

![](img/ffd282b2d431f9765c707d3effca38b7_70.png)

know this。🎼う。何？Yeah。いいい。So you could probably add a side effect to that as well。Yeah， that。



![](img/ffd282b2d431f9765c707d3effca38b7_72.png)

Okayケ。The sound effect。Should be maybe the whistle。Yeah， let's just try doing the whistle。

So I'm gonna I set see。We're going to do a like。D a slow。毛胸毛胸。Sound。Let's set that volume。

To be the D1 minus the DT multiplying。Okay， and then we should play sound。ち。

Go to do the slow motion sound， because play sound。Let's try the whistle。

But let's try to make that a little bit easier。Not sure， not sure。 let's just test things out so。

We are going to add another plain sound。There be this slow motion。It so sound。Does that ball sound？



![](img/ffd282b2d431f9765c707d3effca38b7_74.png)

不谢。😊，🎼绿意。It were kind of hard to get。

![](img/ffd282b2d431f9765c707d3effca38b7_76.png)

Yeah， let's。Let's make a button。To change that。

![](img/ffd282b2d431f9765c707d3effca38b7_78.png)

![](img/ffd282b2d431f9765c707d3effca38b7_79.png)

![](img/ffd282b2d431f9765c707d3effca38b7_80.png)

![](img/ffd282b2d431f9765c707d3effca38b7_81.png)

一。😊，Decrease even more the speed much。

![](img/ffd282b2d431f9765c707d3effca38b7_83.png)

🎼う。

![](img/ffd282b2d431f9765c707d3effca38b7_85.png)

嗯。Well， I't know。

![](img/ffd282b2d431f9765c707d3effca38b7_87.png)

🎼It feels a bit laggy when he didn't like。Yeah， are making we are making so it's gets a little bit slower。

🎼When you hit the black， it's supposed to be really subtle。



![](img/ffd282b2d431f9765c707d3effca38b7_89.png)

Not supposed to be two noticeable。Just to have a little bit of a field thing。Let's try making。Like。

volumeolume twice as much， but if it turns out that it's a bad idea， we can take that out， though。

呃Let's see。

![](img/ffd282b2d431f9765c707d3effca38b7_91.png)

🎼But I was also， I was also forced。before let's see。Yeah。Oh。Yeah， you know what， I think all right。

 I think we should really make this like if the torr is bone， as that say。😊。



![](img/ffd282b2d431f9765c707d3effca38b7_93.png)

Is that an of three？Then we decrease the Dt by like 0。2。Then you can do that。Other cases？



![](img/ffd282b2d431f9765c707d3effca38b7_95.png)

Whi'ch like when we get like crazy bonuses。

![](img/ffd282b2d431f9765c707d3effca38b7_97.png)

In this case， we sure really to get any change。🎼可。I got you all back。🎼有man。奥美。何？Yeah。🎼Yeah。

 you know what在 not韩业不嫌 happy。With this either。Finally， kind of like， yeah， awesome man。

I try to do them at like different。来。Well， at weekdays， I can only do them。At night。

I sometimes into Sunday morning。Okay， that was pretty cool。い。That's not portion。I to play with。Re。

🎼Yeah。I can try to get a content Yeah， so that was pretty cool。I mean， I don't know。

 maybe you guys can play and tell me what you guys think。About this little motion。

It may just be a bad idea。Yeah。I''m not such a big fan out。With be niche。

We be between the person is travel to the bottom。干？

What do you mean you that because this slow motion really？那我还那么装，我们还。

I haven't gotten the three to the three ball party yet。

 but it does only pump the balls towards the blocks when it exhibit pure collididing。🎼Yeah。

 you know what？In the very first gameplay stream， which was like second stream。

 we try and played around with multiple balls for the player and we even did like some weird things to the speed of the ball to make sure that it's always possible to two。

🎼To play with them。But that was really， really crazy so in the other in the mode that we got more balls。

 which is when you get the power up more the triple shot。They don't harm you at all。 So yes see。

They're going to go up and they can kick off ball that you have to add combos。I'm going to remove。

Yeah， see， they can't move the not crazy stuff， but they can't go back to you so you can be safe to and you have one ball to worry you about。

Yeah， they like Commonal residents。

![](img/ffd282b2d431f9765c707d3effca38b7_99.png)

There was a。Yeah， when we tried having multiple balls， and tried that a couple of times。



![](img/ffd282b2d431f9765c707d3effca38b7_101.png)

You guys for the program， yeah， that'll be cool， that'll be cool I mean we we we add it by hand。

So that they get destroyed， so we have a flag like get destroyed when Y is negative。But。

In terms of the game design， that wasn't interesting to have。

Three balls going each one in a different place at the same time， so yeah。

 that was kind of weird so I am going to remove this guy I did not like I did not like this guy。

So I can move the sound。Do like slow motion sound。So that was a little bit a bumper。그。咩啊。

I'm going to try just one more thing。Yeah， I can remove the sound， no problem。

But I'm going to remove just one more， I'm going to try this one more thing。

And everywhere hit a ball。I'm going to now do this。Let's say。 I'm gonna set。Okay， let's。

Lets do it like。Slide -4。And then the DT multiplier。We set it back to one every frame。

 So weve got one frame of lag of like。Feel thing， so。



![](img/ffd282b2d431f9765c707d3effca38b7_103.png)

This is like the last try to make this interesting。い。🎼You。Yeah。你理由。嗯。It's really subtle。

I don't think they're going to keep it though。🎼I don't think that people。 I'm gonna let again。うほら。うん。



![](img/ffd282b2d431f9765c707d3effca38b7_105.png)

Yeah， I'm going to do this。So forget about us。你下子的自题。So no more slow motion。When a bug is a block。

 he feeds the bug， is there the scorere that's supposed to increase when you destroy a block？Oh。

 there's another one。

![](img/ffd282b2d431f9765c707d3effca38b7_107.png)

Is the score supposed to be hit when we describe block， is it not。



![](img/ffd282b2d431f9765c707d3effca38b7_109.png)

How it's not。Oh， I may have deleted more things than I should， yeah， I did。

I do even more think that I should have。Thanks for catching this guys。



![](img/ffd282b2d431f9765c707d3effca38b7_111.png)

It will be way harder to catch that later on。Nice part， thanks。🎼There you go there you go。Yeah。

 it feels a little bit better。You havent are responsive。



![](img/ffd282b2d431f9765c707d3effca38b7_113.png)

Okay， so the Texas level， instead of like losing the whole life， losing the whole thing。

I'm going just lose one guy。And we're also going to this try。When do we call this try？Yeah。

 we decrease the life。And call the black destroyed。Oh， I do have to call a bvo。I'm gonna say that。

First of all。And。Side。Yeah。So。I'm going to set the life to 0。Just because now we don't need care。

This is just black。So whenever we do the simulate。Block for level。Yeah。

 see now they can't get us right。

![](img/ffd282b2d431f9765c707d3effca38b7_115.png)

Okay， this looks okay， I think。🎼Let' see。Geting。It's not a key if it's easier， first place。

 first point。Easier。🎼Second point， if I only use one line， lose one。じ？

🎼It's also going to be easier because the ball will reset。W just。Good suppose。Well。

 that felt a little bit slower。🎼就是。🎼い。And I see so the blood reached there。

I think this is as far as I got the time is going， but I'm going to do this。Yeah。



![](img/ffd282b2d431f9765c707d3effca38b7_117.png)

Let's a bit better I think。The other idea for theteers level。Was to make。The well。

 this should be like engine。The other idea was to make like smaller shapes。

 that use the mapor system。

![](img/ffd282b2d431f9765c707d3effca38b7_119.png)

So data you only have to destroy one block。🎼ぜ。That may be a bad idea。Maybe you're like， we alternate。

 we alternate。🎼Okay， every other shape， you destroy it。

By having like big blocks or like small blocks and just straight small blocks。See。

 right now we could have。We have like smaller shit。Although this idea is pretty cool too， yeah。

Now we should be able to have small issues。🎼And maybe the smaller shapes will be the rotating ones。

shapes。Re。🎼哦。

![](img/ffd282b2d431f9765c707d3effca38b7_121.png)

Ptty cool， pretty cool， I think let's try making that we have like the create shapes as farm shape。

Swn touch shape。And we should also take a size。Let me take a quick look on the neighbor system because I don't really remember。

How that works calculate all neighbors。Yeah， suppose just called that。This is stupid， okay。We get。

 okay， so we iterate through the blocks like。Squared， right？And I'd say if we are close to a block。

We。Yeah。We had a neighbor， if it's valid。So I think you want to hard code this。Go to do like。

 size and。Neighbors。Okay， now let's see where we put around the size。Have the lane size。

The lane size it should probably also be a variable， like。Something like this。B do like。Number。

Thanks。And is that the only plane， yeah。Now， this is the number of lanes。Now， this is the color。

My mistake。When we， when do we get like the random。Rain。Win， in way。Or your hardco the random lane。

I suppose that's okay for now。ok。So。下一次。we。C offset。Block have size。 Okay， so this is the size。

 So the default is for and neighbors is false， so。For false。Fs。And for。

Let let's do the neighbor system。And the neighbor system is going to consist like if。If we want see。

We have a number ofns of four neighbors。You're going to have to increase that。

Our block so farm is like one， two， three， four well。Our blocks is for。So I'm going to， yeah。

I'llGet next of Apple blocks。I'm going to save。Let's see。Gets next。Oh， because we recycle blocks。

 yeah， okay， so I'm going to have kind of hard code。Neighbors。Okay。你个允时。See啊。Let's call that。

Block neighbors。Neighbor blocks。Okay， so block neighbors。And whenever we and we have like the。Next。

要不就 have来。No， that's July like。Next。Right。Neighors。Okay， so whenever we got a new block。

 we're going to set the block neighbors。To the block。By the next block。Plus， plus。That's a c。

Next block is less in。啊。It's less than the array count。For the block papers。Okay。Now， the thing is。

 in the very end if。If we should be neighbors。I'm going to run through all the blocks。Neighbors。

Well else should really be like the。Block neighbors， remember the block neighbors。Bye。哦。知。Yeah。

This is what we want to do。For every。Well。You can do the same thing， right？Yeah。

 for every next block we have。If it's ourselves。This will continue。If it's not ourselves， we can set。

The lock。Neighbors， I。Neighbors。嗯。有没有口代。Index。喂。Eal to the。Broad neighborhood Jake。

Because Jay is going to skip one possibly。And。

![](img/ffd282b2d431f9765c707d3effca38b7_123.png)

Okay， so we should have the same behavior。Let's just make sure everything works then we can test out the neighbor system。

🎼。Solid。🎼はバは。🎼用な。

![](img/ffd282b2d431f9765c707d3effca38b7_125.png)

オッケ。So。Let's now test the neighbors so。When we spawn t sheet。That's seven between neighbors。

So we should only， if we destroy just one guy， we should be able to。



![](img/ffd282b2d431f9765c707d3effca38b7_127.png)

Well， you have to destroy them。🎼ああやしく。

![](img/ffd282b2d431f9765c707d3effca38b7_129.png)

And I'd be fun to make， oh， I was thinking you could draw a number on each block with a number of neighbors。

Then we got a mines sweeper flashback， h I like that idea。



![](img/ffd282b2d431f9765c707d3effca38b7_131.png)

![](img/ffd282b2d431f9765c707d3effca38b7_132.png)

呵呵。😊，The space invaders。Has the NA system as well。Maybe that could be its own level。



![](img/ffd282b2d431f9765c707d3effca38b7_134.png)

同。I'm going to note that。Ass a nice idea to add。We have a lot of ideas。Yeah， let's see。Mines。すい。对。外部。

Shows the number。好了。と。The giant destruct block。I great， by the way。



![](img/ffd282b2d431f9765c707d3effca38b7_136.png)

Instruct a ball。Yeah。😊，Just got pretty crazy right we added that we added that the very beginningkina。

 but it was a very small size edition。Yes， he put it， yeah。The， the couple， the less dreams。

We commanded a gate tour a lot， so we we made got a huge ball。Yes。



![](img/ffd282b2d431f9765c707d3effca38b7_138.png)

那。嗯。呃。Okay， so let's now play around with the size， let's see if we can change the size。

So spatetriris shape。Let's try making that at one。Very small shape。



![](img/ffd282b2d431f9765c707d3effca38b7_140.png)

🎼お man。

![](img/ffd282b2d431f9765c707d3effca38b7_142.png)

That's awesome。

![](img/ffd282b2d431f9765c707d3effca38b7_144.png)

That's awesome。Let me try it。🎼Theyけ。It is going to be hard to get it though maybe once too small。

In the beginning， it's easier to get it because you know where it is。And there you go。

🎼Looks more realistic， but they are kind of small。Can even make like the big Tas shapes？

They do that was a great combo。

![](img/ffd282b2d431f9765c707d3effca38b7_146.png)

The big touches shapes。They can spawn。Either power downs。Orre little dash shapes。I don't know。

Let's try getting that a small attention。

![](img/ffd282b2d431f9765c707d3effca38b7_148.png)

Yeah， 1。5 is okay。And we've got a huge set of shape with our downs。So a three blocks shake here。



![](img/ffd282b2d431f9765c707d3effca38b7_150.png)

I probably destroy the first blog right at the bat right now we have two shapes。



![](img/ffd282b2d431f9765c707d3effca38b7_152.png)

These two， which probably add a couple more shapes， though， let's see t。So we got。Yeah。

 these ones are okay， this one could be cooled at three。



![](img/ffd282b2d431f9765c707d3effca38b7_154.png)

Let's add that。

![](img/ffd282b2d431f9765c707d3effca38b7_156.png)

![](img/ffd282b2d431f9765c707d3effca38b7_157.png)

嗯。I have this one， which is this one rotated a tall one， not sure I'm to add a tall one though。



![](img/ffd282b2d431f9765c707d3effca38b7_159.png)

Because that can be really hard to get。

![](img/ffd282b2d431f9765c707d3effca38b7_161.png)

This one is also cool。Well要。I know， I think when I had a top one。That's abit one。

And let's make the short。And set。we have to add like。You have to add like an extra line for everyone。

Just because that's how the system works。And I have flag shapes。That's going to be one， two， three。

 four， five yeah。

![](img/ffd282b2d431f9765c707d3effca38b7_163.png)

So， okay， so we start out with one shape， then start， then we add a big shape with a power down。



![](img/ffd282b2d431f9765c707d3effca38b7_165.png)

Then let's add to the two shapes， whats do like。し？嗯。嗯。So。After the level， if we have spawned。嗯。

We have Sp four shapes。Where are the rotating shapes？嗯没。Oh， I don't think well。

I don't remember for every block。Over the specific shape I。Do you remember when we change the road？

听的清。来不。That's weird。I don't remember。Onlyy 19 when you start forgetting what you role day too。Yeah。

 you' have told me right。That's a good sign， though， right？

These there are games getting finished maybe have a lot of stuff done that's a good sign that's。

Readally bump， but but in fact。I did， I didn't wrote that on day two， I wrote that on day。



![](img/ffd282b2d431f9765c707d3effca38b7_167.png)

The day before the last day， so pretty sure that was。That was 18， so this is 20， yeah。

 so last it was two stream pass， which was like this week I don't remember。



![](img/ffd282b2d431f9765c707d3effca38b7_169.png)

I think we did this specific thing， shape thing。Shape I。But that's just a sign。

And this is actually a bad system。So yeah。Now we just set the shapes。



![](img/ffd282b2d431f9765c707d3effca38b7_171.png)

I don't know， I don't know。Let's just play for a little bit more and see the change we are and so we started out with a small shape。



![](img/ffd282b2d431f9765c707d3effca38b7_173.png)

You' got a big shape， see just right that one。Then。Then let's make like the two shape。



![](img/ffd282b2d431f9765c707d3effca38b7_175.png)

In those smaller shapes。So I'm going to remove this guy。And let's do like the post level。

Sponwn shapes。So we've heard destroyed destroyed all the blocks， and we have two shapes， yeah。小。

But we should also make， like， a。Swn。I don't know emit。あ。Continuously。Sponse small shape。

That's a great name， is it not？嗯。I just half joking， to be honest。Okay。

 so continuously small small partnerships and when we simulate。And we should know。Well。

 maybe you like sponsorships。Then we can do it like a。Sma smaller shapes tea。

I prefer one letter variables for maximum degree。😊，One level one letter variables。😊，Yeah。

 I don't think you have enough letters in the alphaphabetdo。So， simulate level。For。Tatris。If。

Con Texas shape。I was one smaller shape。Then we're going to increase the small shape T。

And if the small shapes， T is greater than。I know that's neglect have。We decrease that I have。

And then， we。Swn attaches shape。We're going to do one shape。啊。We try do the post。No， yeah。

 we are in the post level already。You are in the simulate， yeah。

So we're going to see we're going to spot the shape oh if it's。Minus1， we got a random。

So we have to take them look at that。And that's make up neighbors。

Now there should be no wind conditional。But we're going to fix that later。Pwn trus shape。y。

This is where we get in nu lanes minus1。Well， but we are not really changing yeah。

 the number of lanes。Here， the number of lanes is going to be， well， let's just keep changing that。

It's gonna be。The size。Plus one， then we got five。But the smaller the size， the more lanes we want。

 So we want like one over this size。Which should give。I'd say。One of4 what。104 if you give a 0。25。

If you multiply that。来。好行。By 20。You got five。But let's see how that looks for like point。うち？1 size。

1 over point。504。5。Times for。13， 13 lanes。I guess that's okay。Convert to float to end。Yeah。

 I think we can do， can we do that yeah。あ justか。O。😊。



![](img/ffd282b2d431f9765c707d3effca38b7_177.png)

And let's see what you broke。

![](img/ffd282b2d431f9765c707d3effca38b7_179.png)

🎼So we broke the initial position。I suppose。Oh， because it's small。嗯ん。

So it's fun times the first shape。It's not linked to anymore。Should be how many lengths we got。

 we have 13 lanes。36 or something。

![](img/ffd282b2d431f9765c707d3effca38b7_181.png)

Or maybe you just get random of length。

![](img/ffd282b2d431f9765c707d3effca38b7_183.png)

So we crashed。Shape spawn。

![](img/ffd282b2d431f9765c707d3effca38b7_185.png)

Oh， okay， so now I have to increase the number。Testing。Because now we can have a lot of enemies。



![](img/ffd282b2d431f9765c707d3effca38b7_187.png)

But I don't know what we freak。🎼1 more than8。🎼表面。🎼This is going to be a pretty cool game out。Oh。

 they are rotating。🎼Yeah。Oh， man。This is crazy。This is great， yeah。😊，Yeah， I really liked it。😊。



![](img/ffd282b2d431f9765c707d3effca38b7_189.png)

I really liked it。I呃。Maybe we should ride off the bat。It's too much。 Yeah， definitely too much。

 but I liked where we are going， I suppose so a couple things I think I don't want to sponsor to to guys。

😊，At that point。Here， so at this point， I'm just going to spawn the small shapes。Okay。And then。

We could probably recycle this like。P let see for。Texas shape。Yeah， we increase the shapes sp。Yeah。

I'm starting to see。Well， now let's just keep going， so。Shakes。On。

So whenever we get like to a decent number of shape shapes， spun。

 we're going to turn off the small shapes。And we're going to do like two rotating blocks just for。

Just change the pace。So。I assume， in the post。Slate level。Let see if you get like 20 shapes。

If we are greater to 20。Can we spawn to per frame， now I don't think we can spawn to per frame。Well。

Yeah， I think you' have to do like greater than 20。Then I'm going to do Tes。あって。Texas。

So let's make like tets， spawns， small shapes。False。It's also reset T。2，0。

But I don't remember the rotating thing。

![](img/ffd282b2d431f9765c707d3effca38b7_191.png)

They're going to be small rotating shapes， I don't want them to be small rotating shapes yet。

 oh which also decrease the year。

![](img/ffd282b2d431f9765c707d3effca38b7_193.png)

Ire get。あしし。Te。ItStill like one second。Oh， if it's greater than zero point。This is wrong， so。

I think one will be okay， so Texas。Spaong， small shapes， target。Dan。

 we've got the target and we respond a smaller shape。At this point， we stopped small shapes。



![](img/ffd282b2d431f9765c707d3effca38b7_195.png)

Yeah， let's see。 let's see。

![](img/ffd282b2d431f9765c707d3effca38b7_197.png)

何？Not big shape。R downs。Oh， then it started to the small shapes。Oh， yeah。

 we are setting that at some point。好 man。うは。🎼八ち？🎼呵。Oh。Yeah， I celebrate。Okay。

 now you got small shapes。Sose they're really liking that。Oh no。 Thanks for。



![](img/ffd282b2d431f9765c707d3effca38b7_199.png)

看。So because we didn't。Spawn the small shape at that moment。We finished。嗯。

He'm going to do like a wind。Here。And then whenever I do like test to wind condition， see。抖。

Condition。Levels。Scocorre changed。And。When to return。Not win， I suppose， so。So when is false。

 we return true。So now we shouldn't win， have to add debug feature to bounce ball in the right direction。

What do you mean like？

![](img/ffd282b2d431f9765c707d3effca38b7_201.png)

🎼I'm not sure I know what you means that。What's the right direction in the both to follow the bricks？

あに。看。Oh， I think that's what mean that could be useful。啊。Yeah。

But we also had to predict the ball movement at that point。🎼玉音盆。Ma。

 I guess anything will be better than the meat plane。Okay。



![](img/ffd282b2d431f9765c707d3effca38b7_203.png)

哦。Okay， now it's a little bit too hard。

![](img/ffd282b2d431f9765c707d3effca38b7_205.png)

I think we still have too many。Guys， do we say like。How many。We say to turn that to false。20。



![](img/ffd282b2d431f9765c707d3effca38b7_207.png)

Stripe 10。

![](img/ffd282b2d431f9765c707d3effca38b7_209.png)

Yeah， not to spend time in st blocks。We could have a destroyed block but。



![](img/ffd282b2d431f9765c707d3effca38b7_211.png)

That I think will be easy to implement。Yeah， let's do the destroy block。So。If I press down。

I'm gonna let's see。哇。Where do I iterate through the box。 Yeah， I'm going go through。Each block。

 then I'm going to destroy。Block this dry here。嗯。即。😊，Nice call， man。What is it。Cold。The dry block。

Block the Detroit。Not blocks。To few arms。Ba。Well block。冇。Maybe destroy right neighbors。



![](img/ffd282b2d431f9765c707d3effca38b7_213.png)

Yeah， so nice call， thanks， and that was pretty easy。笑了。Justs tried it oh， but this is like。



![](img/ffd282b2d431f9765c707d3effca38b7_215.png)

Shes not these down to be pressed。

![](img/ffd282b2d431f9765c707d3effca38b7_217.png)

Because they're' going to destroy them every frame and that's not good。



![](img/ffd282b2d431f9765c707d3effca38b7_219.png)

对。😊，Yeah， I'm going to actually take a look at the rotating thing because I don't。3。



![](img/ffd282b2d431f9765c707d3effca38b7_221.png)

Oh， I still have this low motion。Yeah， so that was a nice time saver。Let's see， Ro。

We have the rotate I and the rotate T from the Texas state。

We just increment that when it' greater than two， we try to rotate the blocks。That have life。

And that a specific shape。Spirtter。4。I'm not sure what that's supposed to means shape ID greater than four。

And see what else， So it's got to be the shape idea。

Yeah that's the only time we play with the rotation。But the shape idea。

 I thought it was just the actual shape。Shapes， spa。So it's not， it's not the。

So the ID is actually the shape。She。Yeah。Okay， now it makes more sense。Now， if it's greater then。

 let's say at。10， right？Can we stop spawning them to yeah。So if it's greater than 10。

Then can start rotate。And we're going to stop spawning them。And we're going to spawn out two shapes。

 this is a pretty bad system， by the way， because this should be dependent on the shape。Yeah。

 I'm not going to mess with that。So yeah， correspond to guys。And we're going to make it so。

The big guys will spa small guys now。So they rotate and they spawn small guys。Yeah， I think they'll。

 and then we can just start spot small guys that Sho。So。感 see。😊，Sponwn Texas shape。

Whenever we do the power block thing instead of just setting it to the first shape。Well， no。

 that's not what I want to do。嗯。How do I know if the entire shape is destroyed， we don't know that。

Oh， we don't need to know that。Yeah， it's going to be kind of ugly， but if I。Do you like。Square。

Level score changed。Yeah。If we。El if the level state。Do t。Go shape bondwn greater than。10。And。

We don't have the block info， so it's squ cheap。And we don't have the block here either。Yeah。

 this is kind of ugly， but I'm going to pass the block down to everyone。

Just so we can hard code this。To know， like。Then， we。It's called on this motion。So。Song t shape。1。1。

1，2，1，5 and two。Block， yeah， this guy has to receive。Illegal forstruct。So。看。Oh， well。



![](img/ffd282b2d431f9765c707d3effca38b7_223.png)

是。Yeah， so it is a ugly hand。🎼何がしてです。Okay we've got a lot more shapes， I suppose。



![](img/ffd282b2d431f9765c707d3effca38b7_225.png)

Let me do an unopimed field so we can take a look at that。



![](img/ffd282b2d431f9765c707d3effca38b7_227.png)

Maybe we have to redo this system。🎼んなつ。Yeah。So respond 33， is it wrong though？

How many shapes respond？Oh， okay， so this is like for every frame。We're responding to shapes。

 so this is drawn。

![](img/ffd282b2d431f9765c707d3effca38b7_229.png)

So。We should probably now that I think of it。I like a level progression。Yeah。😊。

This should actually be the more。Same approach。But I'm not going to change the whole thing。Yeah。

 I see this this is pretty good， but it's nice that we got this point。



![](img/ffd282b2d431f9765c707d3effca38b7_231.png)

Oh mean， they got pretty fast too。Hello。

![](img/ffd282b2d431f9765c707d3effca38b7_233.png)

Oh。对。Except。Let's see。 this one。I'm not sure they spawn small guys， though。I don't think they did。

 When we spun the shapeless do like does be multiplier。Let's do a maximum of。



![](img/ffd282b2d431f9765c707d3effca38b7_235.png)

愿意。🎼We surely not spawn， like。

![](img/ffd282b2d431f9765c707d3effca38b7_237.png)

I'm going to respond these two guys。These guys。Actually， when the shapes are destroyed。

When I spawn more than two shapes， I can set that to false。Then I have to destroy all the shapes。

Yeah， so。What is it called post。Levels。Here。So， if we。It's sprwnung more than tan shapes。got呢。

R should be more like more than12 shapes。If I did one more than 10 shapes。Shapees spawn。啊。

that's greater than 10。Well。And do like。E go to life。Then， I'm going to。Fwn two shapes。



![](img/ffd282b2d431f9765c707d3effca38b7_239.png)

O。8。Yeah， this is way better。Oh， but its not be rotating yet。Sound was no pointer。Which sound？

Rdirectect sound。I was not no pointer。If sound。But。Sound， sound。Was' no one。

Is this like a thready problem？嗰。It is not an all pointer。What。😮，That's so weird。

We use the sound sound here before， right？Yes， see we asserted that it wasn't a no pointer and if it was。

 we continued。And I was complain that I was a no pointer。うす。I don't like this bug。

I don't like this bug at all。If we try to set。あし。Oh， I'm not sure it's spawn those。Dude。

 thanks for that suggestion of adding the cheat。That was a huge time save。

INot sure why it's not spawning the small ones， though。I suppose they are fun。



![](img/ffd282b2d431f9765c707d3effca38b7_241.png)

This is， oh， this is when we completed the episode so we can't be here。This is wrong。 This is wrong。

Should be。Unlike level。Level score changed。So the score changed。If。Shapespeare than 12。

And it's a big shape and small small shapes。Well， now we don't have。



![](img/ffd282b2d431f9765c707d3effca38b7_243.png)

Oh。Yeah， I suppose we were testing site visit。样子上。看。Yeah， but it's funny in the wrong place。

It's going to be pretty quick and they can even swallow a bit faster。



![](img/ffd282b2d431f9765c707d3effca38b7_245.png)

I should really add the postponwn level shapes， so I'm going to。Oh man。

 this is turning to a very ugly level in terms of like。In terms of the structure。But。Yeah。

 but I don't want to clean this up too much。It's just this level。

So I'm going to instead of just point the shape。I'm going to set。The levels。Take tanks。

Pos levels spa small shapes。As plus going have the course levels。Shape same thing。

The smaller shapes now。Then， we do this。Okay。shapes。But actually， one of the setup transition。

 So you know what'sm going to do is， I'm going to do the way it was。And。Of。

And I'm going to pass the block position。Black pink。I may add a point to a V2。And let's see。

 whenever we set the。き？I going do if。This is like。Hard。Cold。If we do have a hard codeed pe。

Hes gonna to equal today that。Okay。Okay。Now， if we do have a hard code P， we should probably also。

Now what instead set of hard code and a P，m going to hard code a block。Fong ts， yeah。

 it's going to be good。Parent block。And the only difference is。We have a parent block we set。The第。

To the parent blocks。So that's one thing。And the other thing is that we should make the speed。

A little bit faster。 So do set the speed detectors。Yes。一次。Specifically， we don't satisfy。



![](img/ffd282b2d431f9765c707d3effca38b7_247.png)

我有。Notuch， let's see。他です。They were to finish that。Then we can do like the final pass。

 which is going to be crazy。Then I'm going to do a crazy pass man that that pass was crazy。This。

 the last ones you'll need really crazy。哦。Yeah， the last ones rotating， so the rotation swungwan off。

Oh， did we啊？So that position was really weird。Z they like small。Fanah snacks。I suppose。

It's really fun， though。So yeah， as suppose it is。And because I got the position of the ball。

It goes like really crazy。Like the shadow， I suppose。So we are too off。No， we just want。

Where did that spa。So I suppose they one in the right place Oh。

 but the position for the rotation is wrong so this is。



![](img/ffd282b2d431f9765c707d3effca38b7_249.png)

The P， oh， it's not the P that should be， yeah。あ。It's not the P， the P is correct。The black peas。

 the black relative pea。嗯。😊，Yeah， I suppose。The block P。When we rotate。What position do we change。

Change the block relatively， so yeah。I going to change the rather than the block P is going to be this。

But if we do have。If you do have a valid。Parent block， it's not going to be there。If you do have。

 it's going to be。Black P。2 be。Theros of block P。Plus， the parallel， yeah。



![](img/ffd282b2d431f9765c707d3effca38b7_251.png)

This looks correct。Okay， okay， man。 we're getting there。It's almost really almost done。And actually。

 the fireworks sounds when I press the button。They're also pretty cool。

And it does have a nice filter。So they are spawnes a crazy condition。

🎼Now I'd let me just pause since we got here。And let's just make sure。

Let's just see how many blogs respond。

![](img/ffd282b2d431f9765c707d3effca38b7_253.png)

Let's see。 the level。State。Tris。Respond， and' say，21。So if we， yeah。

 so I think this will be the final one， So if we。Yes。Yeah。嗯。😊，Okay， so 21， so if we。Mged to。

Destroy 21 shapes。So。This will be in the。When。那不点。If free men should destroy 21 shapes。

its greater than。Are equal to 21。Well， here we can pretty much this test。So if it's greater than 21。

 it fits equal to 21。We should now do one last crazy response。ok。😊。

And we're going to set when to true。So that was stated up。Tuches。W to true。 So now we can win。

And we're going to spawn several small shapes。I say， we' to get to 40 shapes right the end。

Let's try that。Sert。Des ships bond。嗯。Yeah， another hack。This is not the best place either。

We got to the last shape。If you got to the last shape。S suppose minus one， right？

Then we are going to stops point， so we're going to set。Tes。光。Small shapes。Yes。Okay。

 and I think we should be good to go accept the rotation thing。Should you like one myself。

 it's greater than。

![](img/ffd282b2d431f9765c707d3effca38b7_255.png)

Okay。

![](img/ffd282b2d431f9765c707d3effca38b7_257.png)

And which probablybi also add。Power ups in the last few months because it's going to be crazy。

 so we're supposed to be okay。It's supposed to be a nice crazy。

Then we can do like one final balancing。Yeah， but the position is to run。That did not solve。Oh。

 but there we go。Expling the crazy number of types of species。



![](img/ffd282b2d431f9765c707d3effca38b7_259.png)

Okay。😊，哼。😊，They were too early。Oh， because you have。So instead of just hard codingding， that's 21。

I'm going I say that if。The level score changed。And。The win， what is that？Level progress。Fit's 2。

Then we can start spawning these guys。Then we're going to set that to two。

When we start spawning the big two vessel when we do this。十分就已系好。Progress。



![](img/ffd282b2d431f9765c707d3effca38b7_261.png)

谢些。

![](img/ffd282b2d431f9765c707d3effca38b7_263.png)

Yeah， and we should probably also add， let's say， the power。Locking。Yeah， here。

If we are in the wind condition， so if。Caes。我。You're going to spawn a power up。 so it's going to go。

All the way from 0。It the power of glass。

![](img/ffd282b2d431f9765c707d3effca38b7_265.png)

Now， let's play。And see， this should be good to go I think。So these should get part downs。Yeah。

I want to achieve there， but。显实。I guess it didn't work。而且。Re respond。



![](img/ffd282b2d431f9765c707d3effca38b7_267.png)

Yeah。😊。

![](img/ffd282b2d431f9765c707d3effca38b7_269.png)

'Not sure， though。Not sure， so。

![](img/ffd282b2d431f9765c707d3effca38b7_271.png)

I see， whenever。This guy didn't actually run。hake， yeah， we can't hard call the Shakes fall to 11。

We have to do the level progression， so the level progression。This one。

Let's just make sure we when we set a lot progression。When we got more than 10。



![](img/ffd282b2d431f9765c707d3effca38b7_273.png)

![](img/ffd282b2d431f9765c707d3effca38b7_274.png)

Yeah， because we cant make sure it's one because now we have different。Oh no。没有。爱老吃笔。

🎼Should be actually， no。

![](img/ffd282b2d431f9765c707d3effca38b7_276.png)

It's weird， why am I winning？

![](img/ffd282b2d431f9765c707d3effca38b7_278.png)

![](img/ffd282b2d431f9765c707d3effca38b7_279.png)

Let me put a breakpoint levels 537。Let's go to levels。5ive，37。



![](img/ffd282b2d431f9765c707d3effca38b7_281.png)

Ws falls。

![](img/ffd282b2d431f9765c707d3effca38b7_283.png)

We didt even go through that？Oh。We've probably gone through one of these guys。是不是是。Car。

That doesn't make sense。

![](img/ffd282b2d431f9765c707d3effca38b7_285.png)

Test for wind condition and for the break point。Let me put a great point。Here。



![](img/ffd282b2d431f9765c707d3effca38b7_287.png)

Oh， in fact， I think I didn't feel break my just press at ten out of control of tens。



![](img/ffd282b2d431f9765c707d3effca38b7_289.png)

This is so weird。

![](img/ffd282b2d431f9765c707d3effca38b7_291.png)

How are we advancing？It put a break point。

![](img/ffd282b2d431f9765c707d3effca38b7_293.png)

さきな。Oh， wait a minute。That very point didn't work。

![](img/ffd282b2d431f9765c707d3effca38b7_295.png)

Start game。

![](img/ffd282b2d431f9765c707d3effca38b7_297.png)

いや呀。Okay。

![](img/ffd282b2d431f9765c707d3effca38b7_299.png)

Why is when one？So。When it was true when the progression was true when we were supposed to spawn。

Small shapes。Well we could really act by doing this， but this is not supposed to be true anyway。冷来风。

Progression。Yeah。😊，So。The problem was just the order of the code。 We were saying the progression to2。

 and， but we weren't exploiting them yet， and they were saying the win before that， so。



![](img/ffd282b2d431f9765c707d3effca38b7_301.png)

Yeah。Now， yeah， so this what happens when we don't have a superstructured thing， but to be honest。

 it's kind of impossible to have a superstructured game from the Ge go。

Because we didn't know how the Tetriris game was supposed to look like。

So now we were supposed we are actually in the better shape to restructure the level code。

 we're not going to do this because。🎼We're supposed to finish this game pretty quickly right。

 there not supposed to be a huge project。You guys should be able to follow that from the beginning to the end pretty reasonably。

It looks pretty， pretty good man。😊，Whether like the four block one explode。Yeah， perfect。

Let's see response tomorrow guys。How many shapes is gone 41。Okay。



![](img/ffd282b2d431f9765c707d3effca38b7_303.png)

If the progression is true。 yeah， we have to。This is， this is weird。

ThisThis is the first progression， right？Yeah。Level of progression。



![](img/ffd282b2d431f9765c707d3effca38b7_305.png)

Okay。Okay， no， that was your wrong。So got two， we got one guy。

Now we should have the small ones and we do have the small ones。And they're rotate。Yeah。

 I got way too many。You you't got the big the two big ones。And they might be。



![](img/ffd282b2d431f9765c707d3effca38b7_307.png)

Oh， we got the two big ones， but that was way down the line。

The two big ones govern the progression is what。So let's see。Yeah。

 I wasn't really supposed to stick the tattoos for this long。

 but since it's going to become a pretty good one， do that。This one I said that two。So。

Should only be2。Let's see small blockss。Oh shapes Sp to。 Yeah。 No this is correct。And it's。

That's been a data break point whenever we change the level progression。



![](img/ffd282b2d431f9765c707d3effca38b7_309.png)

Yeahや，我知。So this is not sure。Yeah， I think。LetMaybe be wrong。Level score changed。

And we spawn two shapes and there's like one block room yeah， okay。Okay。

Now we are on level progression1。W means they want to destroy all blocks。Ssform to。Let's just see。

Let's just see when we stop spawning small guys。When the leverage ratio is zero。In everything。

 so that's probably the post simulate level。

![](img/ffd282b2d431f9765c707d3effca38b7_311.png)

I post。This level。Now it's when the progressions formed。

Let's just make sure the lab progression makes sense again。It's three way to do move with this one。

Oh， then it changes to two here。うし。So， this is actually two。This is actually。1。啊。So here we are。

From 0 to one。7。事啊。This pointer set to one， this pointer set two， at this pointer set to three。So。

 yes。

![](img/ffd282b2d431f9765c707d3effca38b7_313.png)

Okay， okay， let's see。 let's see what we have。Nice， we got a big lock。

They we should have 10 small blocks。A little bit less。And they should not be rotated。

His looks correct。い？Okay， now I should have the two one。Okayケ。Okay。Oh man's been so crazy。Okay。

We are spawning more， I。

![](img/ffd282b2d431f9765c707d3effca38b7_315.png)

41。How comepon 41，0。No。How come you respond 41？

![](img/ffd282b2d431f9765c707d3effca38b7_317.png)

But I still have a couple problems。We spawn the small guy inside the block。

 so we can't really do this。You can't really make this。The big ones， one， small ones。

We can't really make the big ones small ones unless we were supposed to change whole system。

 but I don't want to do this。So staff making， see。Big ones， small， small ones。

See all of this was for nothing。Yeah。We're going to make them spawn。唔起。Yeah。我呀。啊。

It's a letter of progression is。3。I don't this is correct。This is not。So but this is also not wrong。

So level。Sre changed。We don't need blocks。Okay。IAt this point when I will understand what's going on。

Have we ride the whole thing， what？What dude， we are so close。Yeah， really close。嗯。

But we can pretty much understand what's going on， I mean we should be if we really want to understand 100% of this math that we created in this episode and the previous other one that we did attaches。

We could we write the Tetris this guy again with the level of progression。

 but we should maybe have a more formal structure for the level。Programming， I suppose。But。

But at this point， all you're doing is like fine tuning。And we don't need to do the whole thing。

 all I want to do now is they want to add the power block。秀弟。The techs guy。

We're going to do like a random。Chance。24。But I， but， what I really want to do。

 I also want to do like， if we respond to or。If the level progression is3。

Because the library register should really be an。Yeah。Bandom chance。I得翻译。Very much。



![](img/ffd282b2d431f9765c707d3effca38b7_319.png)

![](img/ffd282b2d431f9765c707d3effca38b7_320.png)

Nice， okay， nice。So these guys oh crap。Okay， I've done that right。So the last part is on。



![](img/ffd282b2d431f9765c707d3effca38b7_322.png)

That was the last problem， I suppose， so。We were supposed to being the lab progression4。

 but apparently we were on lab progression。Oh， yeah， it was supposed me three。

 I remember changing that three。

![](img/ffd282b2d431f9765c707d3effca38b7_324.png)

这そ。

![](img/ffd282b2d431f9765c707d3effca38b7_326.png)

Okay， so I suppose it really should be。3。But not here。You should be three on the test in condition。

Oh， this is the testment condition。So yeah， it should be like if we destroyed all blocks。



![](img/ffd282b2d431f9765c707d3effca38b7_328.png)

Okay okay okay。Oh， not space invadeters。Not space invades， guys， not this time。い？Oh， crap。つ。

And maybe you're wanting floless， I don't know。

![](img/ffd282b2d431f9765c707d3effca38b7_330.png)

Oh， correct。Yeah， one four。ItWas not that much。Maybe we can do like。

And think you're like wanting two。So。So I think we should be able to。



![](img/ffd282b2d431f9765c707d3effca38b7_332.png)

To have called this guy a success。2。Our attack is level。

So you're going to have to play that a little bit more。At least for today。Think。

We can go on to the next thing。🎼s just super。🎼Our crap inver controls。No。Oh， man。STT。

There's another thing I want to do。 Quick thing。 I want to change the。The position in which。

You know H the。何？In the power ups or downs get destroyed。Yeah， we need more power。



![](img/ffd282b2d431f9765c707d3effca38b7_334.png)

Okay。

![](img/ffd282b2d431f9765c707d3effca38b7_336.png)

Yeah， that was too many powerful think。And。Let's go to the power。power玩不道。

Not par blocks sound of the par blocks。Whenever， whenever see， the position is less than。



![](img/ffd282b2d431f9765c707d3effca38b7_338.png)

。

![](img/ffd282b2d431f9765c707d3effca38b7_340.png)

就第一。2。

![](img/ffd282b2d431f9765c707d3effca38b7_342.png)

🎼Well， I didn't like to see the whole thing。

![](img/ffd282b2d431f9765c707d3effca38b7_344.png)

Looks perfect now another problem we have is the performance we are in an optimized build， right？



![](img/ffd282b2d431f9765c707d3effca38b7_346.png)

![](img/ffd282b2d431f9765c707d3effca38b7_347.png)

Let's see if you can。op presseds up。And the draw of 32 failed。

And I press up what happens the menu when I press it。



![](img/ffd282b2d431f9765c707d3effca38b7_349.png)

I had the inibility or that's what I wanted to do。

![](img/ffd282b2d431f9765c707d3effca38b7_351.png)

Oh。How， actually should the D multiply？一固定跟起不理。

![](img/ffd282b2d431f9765c707d3effca38b7_353.png)

It's not good。

![](img/ffd282b2d431f9765c707d3effca38b7_355.png)

So this bitnap is a huge bitnap。And it takes a toll on the performance。

So I think I'm going to change this bitmap。To be。A direct。All right，scribe Blake， good look。 Thanks。

 man for dropping by。 I'll see you in the next stream， hopefully。😊。



![](img/ffd282b2d431f9765c707d3effca38b7_357.png)

Thanks for dropping by man， hope you enjoyed this。So I'm going to remove， let's first of all， remove。

From the data folder。The force field。Because we can pretty much do that。That would be no problem。

Okay， so whenever we see the force。With that force field I'm going to remove the viap forest field。

And we don't have a bignet course because we don't load it。And here let's just dry。Position。

Disposition。As do a transparent route。I guess has to be a transparent day。

Draw transparent rotator back。Okay， and the color thats the important。Pure green。Oh。

 let's see what you need。In the transparent。碘有。I think I'm going to do。It just transparent to act。

Yeah， I'm going to do it transparent right。There's another one that I needed to use this。

 I don't remember which one。Clan。And I don't remember which one needed to use。ToBe transparent。

 but another rotated one， let me try everything thing。Yeah， I don't know。So。

So it's going to be a way lighter。 So this is actually draw transparent。Rs and pixels。

I would draw B in pixels transparent。That's a great name， is it not？Okay。

 so this would be the same thing as a。So now we just have a green or rectangle instead of the。



![](img/ffd282b2d431f9765c707d3effca38b7_359.png)

![](img/ffd282b2d431f9765c707d3effca38b7_360.png)

Yeah。

![](img/ffd282b2d431f9765c707d3effca38b7_362.png)

And。Actually， before we do the full transformation， we already did it， right？Before I do it。

'mGoing to。Go back to the optimized gu。And turn on the profiler just so we can have some real numbers。



![](img/ffd282b2d431f9765c707d3effca38b7_364.png)

Oh， I delete it from the photo I can just revert。

![](img/ffd282b2d431f9765c707d3effca38b7_366.png)

See， thanks for using source Control。

![](img/ffd282b2d431f9765c707d3effca38b7_368.png)

次。Oh， I should make that full screen so。I go up to 20。



![](img/ffd282b2d431f9765c707d3effca38b7_370.png)

That be put up。Screenshot of that。So。So this is the problem we have。go up to 20。

And the second for frame because midmps span like。Have two bit namess。I must have had like。头啊。No。

Why do have two bitmas？

![](img/ffd282b2d431f9765c707d3effca38b7_372.png)

Okay， yeah， we do have this small icon on there。

![](img/ffd282b2d431f9765c707d3effca38b7_374.png)

嗯。Yeah， so。Now let's go back to the full。Okay， thing or not okay to me。



![](img/ffd282b2d431f9765c707d3effca38b7_376.png)

Full solid color。🎼再来自得劝一圈。

![](img/ffd282b2d431f9765c707d3effca38b7_378.png)

So now we are locked at 16。So。Yeah。Our direct。Its like considerably more expensive。But。

We got the bitm down to like 0。06 milliseconds per frame， so we' got 11 milliseconds。

Of increase if we do that， and that's pretty much what we're going to do。

Except I'm going to do this inside of four。To get that stripe that we wanted。

still I don't remember how many pixels we have in the forest field' see。20， so yeah， let's do 20。嗯。O。

😊，So。The position is correct。Well just not correct。So the size。Is 10， right， So actually。

 the size is going be。Make like。え。嗯，Stripes， I suppose。There is going to be 10 divided by numberbri。

Tris。So this is just one stripfe。And let's called this like stripe。Nice。Tripe size。

And then we add to the y position。Well， what your like。At。淮成力。Player visual PY。Minus。き？Let's see。

 this track。Stripe size divided by number of sprites。We're actually tight。Okay。And this should be。

Why。And here should do add y。Plus， equals。And then this is going to be the invisibility alpha。Times。

成担。Right。は。F bye。I think this is correct。Yeah this is kind of re。But。What can you do sometimes just。

Have to get this thing working。看启。😊，Let's see if you still have。Okay。The size is not correct， though。

 oh， because it was the half size。It is enough。Isy enough to fix？



![](img/ffd282b2d431f9765c707d3effca38b7_380.png)

是。🎼Nice， perfect， but the position is not perfect。And the performance is great。🎼。Yeah， well。

 the reaction now is pretty expensive。But we can still run at 4k。



![](img/ffd282b2d431f9765c707d3effca38b7_382.png)

There's that。

![](img/ffd282b2d431f9765c707d3effca38b7_384.png)

Why is the position wrong。I think， yeah， I don't need to divide by two because it's the hatchag。

That's right。No。Great， that was weird。 I， I'm subtracting by the strip size。



![](img/ffd282b2d431f9765c707d3effca38b7_386.png)

Oh， times。thank you。This is。

![](img/ffd282b2d431f9765c707d3effca38b7_388.png)

Very weird。Let's just make the player of visual repeat。Now let's make the player visual P。Minus20。Oh。

 we're doing， I'm doing probably to the wrong guys。So you have to deal with both of them。Stripe size。

And this is the nuts。呃。Yeah。Okay， now everyone's small。10。



![](img/ffd282b2d431f9765c707d3effca38b7_390.png)

![](img/ffd282b2d431f9765c707d3effca38b7_391.png)

Yeah，Perfect。😊，So yeah， we did that performance improvement。More fuel stuff。嗯。

I don't know if we're going to do that today。The la transition thing。

Because that takes a while and we already worked。

![](img/ffd282b2d431f9765c707d3effca38b7_393.png)

只拿。Pro fatherther。We already did some nice work on the levels， well， maybe you can just start。



![](img/ffd282b2d431f9765c707d3effca38b7_395.png)

![](img/ffd282b2d431f9765c707d3effca38b7_396.png)

Yeah， let's just start。But before I start。I should。I'm going to go to the bathroom。

 so I'm going to take。A two minute break and then we can do。Then we can do the。

They have a transition，'ll be， that'll be hard as well。ok。😊，Okay。

 then I'll go and I'll be back in one second。Okay。Let's continue where we left off。

Which tools us we're going to start doing the loud transition。Okay。

 and let's try to structure this guy a little bit better。Then we did the levels in general。

Just don't spend a whole lot of time and complexity trying to understand like this thing， right？



![](img/ffd282b2d431f9765c707d3effca38b7_398.png)

So， yeah。So the idea is， we have a menu。🎼で現界。So instead of just doing this hard transition。

We want to do light。🎼呃。🎼I don't know。🎼What do we want to do exactly？I think what I want to do。



![](img/ffd282b2d431f9765c707d3effca38b7_400.png)

Because our options are， let's discuss the options， right。



![](img/ffd282b2d431f9765c707d3effca38b7_402.png)

We could add a special case in the game。Which know what I'm kind of inclined to do。



![](img/ffd282b2d431f9765c707d3effca38b7_404.png)

Or we could add another。

![](img/ffd282b2d431f9765c707d3effca38b7_406.png)

Thank you。

![](img/ffd282b2d431f9765c707d3effca38b7_408.png)

Yeah， I think when I add a special pitch to the game， let's just see。How that feels， okay。So。

 let's go to the levels。没有。喂。Yes。If the game mode is gameplay。Actually， when we change。It see。

And we change game modes。If we change to the gameplay。I'm gonna set。Like a level。Transition to one。

来不这具题。That。Sound。Good。So， would you like。然后。Transition。T。可以。So we said that to one。

Now when we update the game。We see here。If the level of transition， it' greater than one。

Res subtract。根据几。And。And we do， like。我们继续。Any else。一起。That would be the else。So。继。

So we should wait like one second of doing nothing， we should have probably a。Black screen， maybe。



![](img/ffd282b2d431f9765c707d3effca38b7_410.png)

![](img/ffd282b2d431f9765c707d3effca38b7_411.png)

Well。Fs well。If it's bigger than zero。

![](img/ffd282b2d431f9765c707d3effca38b7_413.png)

Okay。You should have one second half on black screen between letters。



![](img/ffd282b2d431f9765c707d3effca38b7_415.png)

Yes， stop having a black screen right that。

![](img/ffd282b2d431f9765c707d3effca38b7_417.png)

Pros sweet。

![](img/ffd282b2d431f9765c707d3effca38b7_419.png)

![](img/ffd282b2d431f9765c707d3effca38b7_420.png)

🎼え。Now have a black screen。没有。What I think I'm going to do is in the menu。I'm gonna do， like a。诶。说啊。

大到 transition先。开新的DT。And yeah， right now I'm going to do pretty much the same thing the whole game。

The whole menu。And I can split up maybe like two parts， just do like。没妞。Drying。

 so to clear the screen。We draw off your racks。We don't need or's see where we get it。

We draw the text。Maybe the text。The text we're not going to draw。That draw number。

And then we draw the logo， which we' probably also not going to draw。Yeah。

 let's just draw the basic thing。

![](img/ffd282b2d431f9765c707d3effca38b7_422.png)

![](img/ffd282b2d431f9765c707d3effca38b7_423.png)

And let's also。

![](img/ffd282b2d431f9765c707d3effca38b7_425.png)

What sound are you playing。

![](img/ffd282b2d431f9765c707d3effca38b7_427.png)

I don't know。A very cool sound。Let's add some screen shake。



![](img/ffd282b2d431f9765c707d3effca38b7_429.png)

![](img/ffd282b2d431f9765c707d3effca38b7_430.png)

Way better now。That I'm going to do。I have a， let's see。Yeah呀。Manual T。

 which will be a map Inter normalized。From 0， No， we start stop start with one， right。

 It's gonna be like。0。5。Not the DT。 Let's called that。一次。ち？知道。也。Now we're talking。

And then we are going to， let's， let's do like。你。Rightect。1。He？It's gonna be alert。Of， let's say。

 this guys in the left， right。 So this guy。The tea and this guy。 But this guy will be。

And this guy is gonna be。Plus。20 plus 5。Okay， correct1。Corr， let's see if we have some animations。



![](img/ffd282b2d431f9765c707d3effca38b7_432.png)

![](img/ffd282b2d431f9765c707d3effca38b7_433.png)

![](img/ffd282b2d431f9765c707d3effca38b7_434.png)

That was awesome。う。

![](img/ffd282b2d431f9765c707d3effca38b7_436.png)

But our either ourlets。That's French。还能吃。If our T is wrong or a product position is wrong。



![](img/ffd282b2d431f9765c707d3effca38b7_438.png)

Well， our teeth should just go from one。I'm sure this is the slowest。要 for my。



![](img/ffd282b2d431f9765c707d3effca38b7_440.png)

What is 0。Not sure。 Let's see the menu。That should go from one to zero really fast。



![](img/ffd282b2d431f9765c707d3effca38b7_442.png)

![](img/ffd282b2d431f9765c707d3effca38b7_443.png)

啊。I'm sure these values are correct。Oh， we were using the T， should be the menu tea。

Now I should be really quick and then stop with。But it's not enough。And。8费有。



![](img/ffd282b2d431f9765c707d3effca38b7_445.png)

![](img/ffd282b2d431f9765c707d3effca38b7_446.png)

And not enough。

![](img/ffd282b2d431f9765c707d3effca38b7_448.png)

We we。 know， We're not。

![](img/ffd282b2d431f9765c707d3effca38b7_450.png)

![](img/ffd282b2d431f9765c707d3effca38b7_451.png)

![](img/ffd282b2d431f9765c707d3effca38b7_452.png)

What's this。

![](img/ffd282b2d431f9765c707d3effca38b7_454.png)

Maybe we put that for a great point。And didn't。Take that out。



![](img/ffd282b2d431f9765c707d3effca38b7_456.png)

Okay。😊，Part。Oh the problem is nice。

![](img/ffd282b2d431f9765c707d3effca38b7_458.png)

Now， we should do like a drill off。Is parent erect？And we should do like the menu tea with this guy。



![](img/ffd282b2d431f9765c707d3effca38b7_460.png)

Man， this is so cool。

![](img/ffd282b2d431f9765c707d3effca38b7_462.png)

Now it's going to be another very cool thing。In the clear screen。Where do you get， like， the menu。作7。

Are wena collarer。What is the arena color？我这是掏而的来。Yeah。That's what we're going to do。

 We want to learn。好的。And 0 would be the arena color。And this would be one。

And then another by many fee。

![](img/ffd282b2d431f9765c707d3effca38b7_464.png)

I see。 we have。🎼awesome。Awesome， now let's start incorporating some elements。🎼你 it卡。



![](img/ffd282b2d431f9765c707d3effca38b7_466.png)

That starts doing the walls， so。你主还 we呢。对。Joina。对。So。This。Yes。Drying。Okay， let's see if we explode。

But。I don't want to do that。We want记。好面色。I'm probably going copy this guy and put that outside。

Since we don't have ordered renderery。We can't put this thing outside the if。Yeah。Oh， well。

 let's see。D t。Be的。

![](img/ffd282b2d431f9765c707d3effca38b7_468.png)

![](img/ffd282b2d431f9765c707d3effca38b7_469.png)

Cake。Now let's do some cool stuff with that。In the change game mode， if we are changing to the menu。

I're going set。Let's see。Ana left visual P。Well， I actually just changed the game。That's it。

If youre change the game alls have the arena， visual P。The last one。 How much。normal value like。

Just the hatch sign。Which is 85。 let's do like。Minus。安排。And let's do 95 for a。

And since we have the spring thing here， we should pretty much。



![](img/ffd282b2d431f9765c707d3effca38b7_471.png)

🎼一个机个。

![](img/ffd282b2d431f9765c707d3effca38b7_473.png)

Can even make that a little more extreme。

![](img/ffd282b2d431f9765c707d3effca38b7_475.png)

Animvation is so cool。 It makes the games so much better。😊。



![](img/ffd282b2d431f9765c707d3effca38b7_477.png)

Very much。啊。

![](img/ffd282b2d431f9765c707d3effca38b7_479.png)

![](img/ffd282b2d431f9765c707d3effca38b7_480.png)

one looked okay。 oh， we didn't do the top。啊。Nice visual tricks。 So top one is like 55。

I should like 60 and let's do 16 more so。では hundred0。



![](img/ffd282b2d431f9765c707d3effca38b7_482.png)

And that's差。In short。是。

![](img/ffd282b2d431f9765c707d3effca38b7_484.png)

![](img/ffd282b2d431f9765c707d3effca38b7_485.png)

But。I don't think I'm going to do this at this moment。うCould you like。B thirty two。They changed。

I short。来个 transition。And then we'll do a level transition。They I'm going to do like， changed。Like a。

Have。Okay， I'm going to do level transition。0 that。啊。😮，你来不。T是ion。O。Now。不然就 like。If the T。

So less than 0。5。Theleever。Transition to tap。几。😊，And what are we gonna to do here， going to do this。

Actually， know what changed our mind。I think it'll be better if I actually put it here， really。

But I only do this。If the level。7。来很久。Did nothing better。Maybe we want to。



![](img/ffd282b2d431f9765c707d3effca38b7_487.png)

Later on，Let's see so in the halfway my image。😊。

![](img/ffd282b2d431f9765c707d3effca38b7_489.png)

![](img/ffd282b2d431f9765c707d3effca38b7_490.png)

![](img/ffd282b2d431f9765c707d3effca38b7_491.png)

Okay， we're getting there。Now。

![](img/ffd282b2d431f9765c707d3effca38b7_493.png)

Let's draw some blocks， shall we。Let's do， like。Reer。啊。La。Rely black。Rubbox。



![](img/ffd282b2d431f9765c707d3effca38b7_495.png)

Now this should be the boring thing， right， let's see if we have the boring thing。



![](img/ffd282b2d431f9765c707d3effca38b7_497.png)

We don't。Didn't they get initialized？

![](img/ffd282b2d431f9765c707d3effca38b7_499.png)

B very point menu one4 eight。That see the blocks。No， they are visualized。This it just a P。P is 0。

Which is correct。SP。Oh， because we're not updating the P。



![](img/ffd282b2d431f9765c707d3effca38b7_501.png)

I suppose that's correct，So let's call that P to be and。哇。Block relative P。



![](img/ffd282b2d431f9765c707d3effca38b7_503.png)

可以。

![](img/ffd282b2d431f9765c707d3effca38b7_505.png)

Now we're not going to do this， right， we have， I think we have alerty too。So yeah。

 thats do P equals the nerve。The two。So the zero position will be P。We're gonna use tea， I suppose。

And then， I'm gonna to use。啊。Plus。Let's make it like。Iello。Not sure。 Don't know。

 what's a good number。

![](img/ffd282b2d431f9765c707d3effca38b7_507.png)

So it starts time。

![](img/ffd282b2d431f9765c707d3effca38b7_509.png)

嗯。Just turn on the light here。While I think。

![](img/ffd282b2d431f9765c707d3effca38b7_511.png)

So。

![](img/ffd282b2d431f9765c707d3effca38b7_513.png)

What if we do like one at a time？嚟。Let' do like。

![](img/ffd282b2d431f9765c707d3effca38b7_515.png)

So we go like have each blocks。

![](img/ffd282b2d431f9765c707d3effca38b7_517.png)

Index。Do you have block counts？I suppose you do have blackcom。So。Let's just assert， I。一会吃的多。啊。Max端。

What do we do with the next？I will get next。Noumb lock。Well。

 that really follows no pattern whatsoever。

![](img/ffd282b2d431f9765c707d3effca38b7_519.png)

Let's just make sure we the ice spread。

![](img/ffd282b2d431f9765c707d3effca38b7_521.png)

I， the nu boxes。Well， let's go back to the unoptimized build。



![](img/ffd282b2d431f9765c707d3effca38b7_523.png)

黐。I is。1024， so it got through all the blocks。Oh。Yeah， I right here。



![](img/ffd282b2d431f9765c707d3effca38b7_525.png)

That's what I want to know I want to know yeah we are in order。In this case。

 I don't want to learn in tea， just in tea。Let's learn in tea times。2。No。Let's do a safe block。

And block T is gonna be a map inter range， normalized。Of。Let's say，0。起完。But。So of just 0。

 I'm gonna do like， I divided by。It's not going to be perfect， but。

You can start and it's going to be this guy。That's。Yes we can get started with some。Gat。



![](img/ffd282b2d431f9765c707d3effca38b7_527.png)

I want not have it like an offset reach blog。

![](img/ffd282b2d431f9765c707d3effca38b7_529.png)

But I want that the other way around， so。

![](img/ffd282b2d431f9765c707d3effca38b7_531.png)

![](img/ffd282b2d431f9765c707d3effca38b7_532.png)

Today is the day to be surprised。🎼バイ。Our own stuff。



![](img/ffd282b2d431f9765c707d3effca38b7_534.png)

That's so cool。

![](img/ffd282b2d431f9765c707d3effca38b7_536.png)

记。

![](img/ffd282b2d431f9765c707d3effca38b7_538.png)

啊。That fast and has to be a。好的。

![](img/ffd282b2d431f9765c707d3effca38b7_540.png)

行。And the ts is drawn。

![](img/ffd282b2d431f9765c707d3effca38b7_542.png)

Oh。

![](img/ffd282b2d431f9765c707d3effca38b7_544.png)

The ones that simulate that have an offset are around， let's see the wall。



![](img/ffd282b2d431f9765c707d3effca38b7_546.png)

I surely make the。The wall， after the blocks。Just。这别。Maybe matter。Oh onward， Oh because。

It starts out as zero。

![](img/ffd282b2d431f9765c707d3effca38b7_548.png)

You're gonna make the。The transition little bit faster。



![](img/ffd282b2d431f9765c707d3effca38b7_550.png)

What do you guys think。

![](img/ffd282b2d431f9765c707d3effca38b7_552.png)

Oh， that was way too quick。

![](img/ffd282b2d431f9765c707d3effca38b7_554.png)

![](img/ffd282b2d431f9765c707d3effca38b7_555.png)

Let's increased just a little bit of the screen shape。



![](img/ffd282b2d431f9765c707d3effca38b7_557.png)

Yeah， when we coll。It's cool because the wall animation。It actually。🎼The animation actually。😊。

If you watch like the top left。You see that even though when we start when we finish the transition properly。

 it still is animating because it's the sameequium where we use。I really like。

I see the super breakout it was perfect as well。

![](img/ffd282b2d431f9765c707d3effca38b7_559.png)

We probably had a sun。ok ， so嗯。Yeah。

![](img/ffd282b2d431f9765c707d3effca38b7_561.png)

是 certainly。

![](img/ffd282b2d431f9765c707d3effca38b7_563.png)

嗯。つ。Here， well， see， I told you I needed this。I do like。Play。Bring。Aect。Okay。Transition play。Yes。

Sound effect。Let's say we played。 and let's play those。Gringen。Play sound。



![](img/ffd282b2d431f9765c707d3effca38b7_565.png)

谢。

![](img/ffd282b2d431f9765c707d3effca38b7_567.png)

It probably increase the volume。And sound。

![](img/ffd282b2d431f9765c707d3effca38b7_569.png)

![](img/ffd282b2d431f9765c707d3effca38b7_570.png)

Now should go back to 0。去。

![](img/ffd282b2d431f9765c707d3effca38b7_572.png)

也。😊。

![](img/ffd282b2d431f9765c707d3effca38b7_574.png)

Okay， now it should add brake sound effects now。It's going to be a little bit more tricky。

Because this guy's normalized。I think I'm going to need a map。Doesn't clamp。

We doing map constraintstrain trauma last。还没开一下。Because most times I want to the clamped value。

But in this case。We need the unclaimed value。Just because I'm going to clamp that afterwards。

 so block tea is going to be this guy unclaimed。And I'm going to say if。How do I want to do this？

Because I have to know if each block。Play the sound。

I'm just going to add like a huge array in the lab transition。Not really the best。

 but it'll work for now。Yeah样。So， if block。嗯。Blalock tea。It's less than 0。 It's less。to 0。

Then I can't first of all， normalize it。And then， I can also。

Seey that if the level transition does luck。Black play。Sounce。哎。😊，P。And see。

 whenever we destroy the block。Destroyed。Play sound， break sound。Yeah。😊。

See what else we do some volume low。I going make。Maybe not that low。Andless。你 play。Break block。

Sound like fact how many blockss you have。

![](img/ffd282b2d431f9765c707d3effca38b7_576.png)

やら。

![](img/ffd282b2d431f9765c707d3effca38b7_578.png)

I think I want to add a little bit more offset。For the block。 So instead just doing like the eye。

Time the number of the blocks is means that。Every frame one marks on to hit。Right。Yeah。

 going do like， it's gonna be。No， this has to be。This， but。I think。Block tea。 I w。

 Im gonna clamp that， too。Discussion is zero the first guy is going be zero divided by an ourrc blocks。

Well。It's going to be the items。

![](img/ffd282b2d431f9765c707d3effca38b7_580.png)

![](img/ffd282b2d431f9765c707d3effca38b7_581.png)

It's still safe speed， though。

![](img/ffd282b2d431f9765c707d3effca38b7_583.png)

Oh， this。

![](img/ffd282b2d431f9765c707d3effca38b7_585.png)

介少。

![](img/ffd282b2d431f9765c707d3effca38b7_587.png)

不し。I guess that didn't make sense。あそ。

![](img/ffd282b2d431f9765c707d3effca38b7_589.png)

嗯。

![](img/ffd282b2d431f9765c707d3effca38b7_591.png)

I don't know。 Let's see what happens。I you。

![](img/ffd282b2d431f9765c707d3effca38b7_593.png)

おき？

![](img/ffd282b2d431f9765c707d3effca38b7_595.png)

If I offset T by I。Well， I got fine。

![](img/ffd282b2d431f9765c707d3effca38b7_597.png)

嗯。

![](img/ffd282b2d431f9765c707d3effca38b7_599.png)

Yeah， it was way too low， I don't know if I saw that。



![](img/ffd282b2d431f9765c707d3effca38b7_601.png)

![](img/ffd282b2d431f9765c707d3effca38b7_602.png)

ISo that was。

![](img/ffd282b2d431f9765c707d3effca38b7_604.png)

Yeah， we kind of need a middle ground there。

![](img/ffd282b2d431f9765c707d3effca38b7_606.png)

Yeah。So I'm going to normalize that to zero。And one plus。I times this。So everyone should。啊， let's do。

Itretty much the same thing except I'm not going to take the blocks into a account。



![](img/ffd282b2d431f9765c707d3effca38b7_608.png)

First。知。😊。

![](img/ffd282b2d431f9765c707d3effca38b7_610.png)

![](img/ffd282b2d431f9765c707d3effca38b7_611.png)

![](img/ffd282b2d431f9765c707d3effca38b7_612.png)

嗯。

![](img/ffd282b2d431f9765c707d3effca38b7_614.png)

![](img/ffd282b2d431f9765c707d3effca38b7_615.png)

And we have a way to many sounds。I'm going to like every other three guys。吃万。T choiceice。



![](img/ffd282b2d431f9765c707d3effca38b7_617.png)

爱奇爱奇艺。

![](img/ffd282b2d431f9765c707d3effca38b7_619.png)

🎼P better。Can you even add more like。

![](img/ffd282b2d431f9765c707d3effca38b7_621.png)

Mly less。

![](img/ffd282b2d431f9765c707d3effca38b7_623.png)

啊。I think the other one was better。Me。Not this guy， I mean。Yeah。



![](img/ffd282b2d431f9765c707d3effca38b7_625.png)

Is the problem my？

![](img/ffd282b2d431f9765c707d3effca38b7_627.png)

![](img/ffd282b2d431f9765c707d3effca38b7_628.png)

Thank期。

![](img/ffd282b2d431f9765c707d3effca38b7_630.png)

Still too many though， I think I'm going to get like I'm going to put like a number of blocks。嗯I see。

I you like 30 minus the normal ox。是。

![](img/ffd282b2d431f9765c707d3effca38b7_632.png)

Let's see。 And let me draw this。 The number of blocks， let's say 10。You want to1。

The number of blocks， let say，300。Oh， actually one one。The number of blocks is 300。Well。

 we can't justify。Thatt by  10。How much is 20 divided by102。F button tennis。



![](img/ffd282b2d431f9765c707d3effca38b7_634.png)

K。

![](img/ffd282b2d431f9765c707d3effca38b7_636.png)

It may have a divide by。吔先。

![](img/ffd282b2d431f9765c707d3effca38b7_638.png)

Chance was0， so。Theme just going to do， like the minimum。M。1。20。

And also I'm not going to do like when it's zero。Because it feels like a little bit delayed。

Im going to do if it's 0。2。And also just going to。This guy in party。Co the max 0。



![](img/ffd282b2d431f9765c707d3effca38b7_640.png)

あ。Okay， okay， okay。

![](img/ffd282b2d431f9765c707d3effca38b7_642.png)

🎼点该覚で。

![](img/ffd282b2d431f9765c707d3effca38b7_644.png)

Point to us way too much。

![](img/ffd282b2d431f9765c707d3effca38b7_646.png)

![](img/ffd282b2d431f9765c707d3effca38b7_647.png)

Okay， let's just try to fix。This guy going be kind of tough。啊请你。I say block4 level。Just个 p。

We might actually have to do this the block。Like for example。爱奇。😊。

That's weird how my typing sounds like the box falling。P。



![](img/ffd282b2d431f9765c707d3effca38b7_649.png)

🎼It's basically。

![](img/ffd282b2d431f9765c707d3effca38b7_651.png)

I may hardco textures out of this thing。Like。

![](img/ffd282b2d431f9765c707d3effca38b7_653.png)

![](img/ffd282b2d431f9765c707d3effca38b7_654.png)

🎼But space invades。

![](img/ffd282b2d431f9765c707d3effca38b7_656.png)

I don' know why it's not sure in all of them。Let's put a breakpoint there。

Check out the spacing rid this one。So。We have， like。A lot of blocks， like 600 blocks。

And then I simulate the block for the level。Maybe the block teas。



![](img/ffd282b2d431f9765c707d3effca38b7_658.png)

Let me see。 block T is gonna be because T again。 Yeah， I would have to make more。



![](img/ffd282b2d431f9765c707d3effca38b7_660.png)

Reasonable。Equation there for the plot。

![](img/ffd282b2d431f9765c707d3effca38b7_662.png)

Well， space invades。Yeah， so let's think about this equation。Nice。😊，So let's。

 let's delete everything we did。That's your。 So we have this value T goes from one to 0。



![](img/ffd282b2d431f9765c707d3effca38b7_664.png)

We want。 let's see。啊，忘 to。We want like the first block。Maybe I just want to multiply that。



![](img/ffd282b2d431f9765c707d3effca38b7_666.png)

嗯。You know what， I like that idea， it's going to be super simpleful。

And they may actually work nicely。I going do T times。I that's that's gonna be too much。



![](img/ffd282b2d431f9765c707d3effca38b7_668.png)

But。那就是。

![](img/ffd282b2d431f9765c707d3effca38b7_670.png)

🎼诶，不。

![](img/ffd282b2d431f9765c707d3effca38b7_672.png)

![](img/ffd282b2d431f9765c707d3effca38b7_673.png)

That story not what I expected。

![](img/ffd282b2d431f9765c707d3effca38b7_675.png)

Oh， it should be like tea。Times。I divide it by the number of blocks。So， should be like。Like plus one。

T。切。One plus。

![](img/ffd282b2d431f9765c707d3effca38b7_677.png)

请下。

![](img/ffd282b2d431f9765c707d3effca38b7_679.png)

T goes from zero to1。 This guy should be like zero for the first block and one for the last block。Oh。

 it should be like。T。😊，Plus。T times1 plus this。

![](img/ffd282b2d431f9765c707d3effca38b7_681.png)

I think I got somewhere。

![](img/ffd282b2d431f9765c707d3effca38b7_683.png)

Hey， can you tell me which age to start coding coding I mean？I think the very first。

Llananako I wrote I was like 13， it was action script for flashlash because I was very into animation back then。

So when I learned about flash， I did things like。So you go to animations like you play one scene。

 then you go to the other one。Then I learned about buttons so I could click on the button and go to another animation did like menus。

Then I stopped for some time and then I learned C sharpr。🎼Probably like。It was 15。

And I played on with the unity a bit。Then I was straight， I went straight to unreal Rio。

 what your going me to start？

![](img/ffd282b2d431f9765c707d3effca38b7_685.png)

Do you know like zero code or do you know like the very basics of coding？

And depends on what you want to do if you want to make games。I recommend that you learn C。

Or C plus plus C plus+ is really more complicated than C when you're starting out。

 so I don't really recommend that。But depends actually depends on a lot of things if you want to just if you like game design and want to do quick games。

Then I suggest you download like。Godo， the Goddo engine， it spells like G OD， OD。T。



![](img/ffd282b2d431f9765c707d3effca38b7_687.png)

Go do， yeah。If you download the Goddo engine， that's for free， also download game game maker studio。

That's not free， though， but there is a free version or unreal。

Those are the easiest ones or if you want to get started making games because it's visual programming。

It's really， really powerful， I。

![](img/ffd282b2d431f9765c707d3effca38b7_689.png)

啊。II did my full commercial game。Using a Justal res visual program。



![](img/ffd282b2d431f9765c707d3effca38b7_691.png)

Check out the game I did， and I don't even consider I actually knew how to program。

 and I did this game。Because all I did in the beginning was played around connecting nodes。

In unrealreo， if you go to my YouTube channel， you can see the progress。You see as YouTubetube。

com/dday Dan。You can see like the progress of that game。 That's pretty cool。

 So I started out just making 3D characters。😊。

![](img/ffd282b2d431f9765c707d3effca38b7_693.png)

![](img/ffd282b2d431f9765c707d3effca38b7_694.png)

Then I was learning about programming in the Ri so。Learn about how can I move a character。

 so it's very one step at a time。When I then the game was released for the PS4。

 so that's in the PS4 channel， it's a pretty cool Playation channel。When I finished this game。

 I realized I didn't no programming and I wanted to learn that for real。

But I already had the basic idea。 And once you do have the basic idea， it's a little bit easier。

 So I'm going to my YouTube channel a。Gay programming tutorial playlist。So you can watch that。

 Let me Let me leave my YouTube channel to you guys。

 You can go there and you can learn about game programming in C plus+。 I expect that， you know。

 programming like in a general sense， like what's a variable， what's a function。Very basic stuff。

 But that you do have a， I mean， if you want， you want to jump straight in， you can。

 I really think this gonna be pretty cool。 The first one is already out。

 The next one gonna be out in a couple days。😊。

![](img/ffd282b2d431f9765c707d3effca38b7_696.png)

![](img/ffd282b2d431f9765c707d3effca38b7_697.png)

And there's， you know， there's some theory behind it or I explain what's programming and what's game programming。

 how the game is built， then I guess already didn't know downloading the software I need to start programming。

And I do a very simple program， so that's a nice tutorial what about web development。

 web development is tricky。Because web development is you have to learn what everyone's using at the moment。

So unlike C and C++ and gain development， you can't learn the fundamentals。you can't。I mean。

 if you go to like。

![](img/ffd282b2d431f9765c707d3effca38b7_699.png)

And if you go to handade heroro， if you want to learn like C plus+ or C for realo。

But it's really hard， it's not like for beginners like more intermediate， you can do the intro to C。

 which is more like intro to an intermediateidity level C。



![](img/ffd282b2d431f9765c707d3effca38b7_701.png)

You can watch the five days。The video is pretty old， I mean I think it' 2014。Yeah， 2014。

 but everything that he teaches in this video is exactly the way he teaches。No， no。

 no mystery if you watch web development from like 2014， but you can go way back， I mean。

 2014 is not that long ago， we can watch a C tutorial from way back like at least。

10 years ago and still get 100% of what it teaches。 web development。

 you can't because everything changes really fast and nothing's robust to the point that they use it for a long time。

 So have to learn what's on。

![](img/ffd282b2d431f9765c707d3effca38b7_703.png)

That what's people using at the moment， the way I learned because I did work in in a web development company for a while。

 I developed like their website and a portal where people could download and actually put their CV and then we would extract information from the CV to help them find the right internship for them。

In this case， I just went to Uudemy。Which is a， you know， a online no course， website， whatever。

 and you can you can go to like web development。

![](img/ffd282b2d431f9765c707d3effca38b7_705.png)

And you can search whatever you want here， you can do like front end CSS stuff。Or like。PHP， no GS。

 I learned no GS for the for that job， so I took a course。

I don't remember which one I took was was pretty decent。I watched like half of it。

And don't remember which one。Yeah， but then' have to learn what's， you know。

 on the fad because a couple years from now， nobody's going to use this one I have to learn another one。

 So that's the difference。 So it entirely depends on what you on the program。



![](img/ffd282b2d431f9765c707d3effca38b7_707.png)

For you to get started， but C is a very fundamental thing。 So if you learn C pretty well。

 you'd be able to learn other languages pretty easily so I suggest that you learn with a more solid thing like C that doesn't change didn't take what 50 years then learn what's what's I know what everyone's using and then one year from now I have to。



![](img/ffd282b2d431f9765c707d3effca38b7_709.png)

And again， that kind of sucks。ok啊。I don't remember how it looked for this time。



![](img/ffd282b2d431f9765c707d3effca38b7_711.png)

🎼高强。

![](img/ffd282b2d431f9765c707d3effca38b7_713.png)

I think we are。So instead of doing plus， I think it can add like a multiplier like。5。T times1。

Now I should really， I should really add one。

![](img/ffd282b2d431f9765c707d3effca38b7_715.png)

Yeah。

![](img/ffd282b2d431f9765c707d3effca38b7_717.png)

I mean。Is that the same sound problem？A violation。Reading location， channel count， sample。Oh man。

 we do have to take a quick more careful look at the sound later on。Sample count，17。S eight times。

It's weird。Trying to access。Sample number 14。

![](img/ffd282b2d431f9765c707d3effca38b7_719.png)

40。Thousandand。If we have an assert for this sample， let's do an assert。For a sample。

 so you can probably catch bug like that。I kind of sucks， thank no problem， man。嗯。一知。Whenever we。

Get the sample。We are clamping that to the。The position has an integer。And a sound sample。Minus。

 this is drawing。But that's not just lose Al three enough thoughts here。

 we can do it like in a polished passing the engine。

But I think I want to do like the OT reader and asset thanks for anyone can do like an overall。Okay。

😊，啊。That's totally not what I expected。By multiplying that to a a small number。

If I multiply T to other things。

![](img/ffd282b2d431f9765c707d3effca38b7_721.png)

Yeah， I think has to be greater than one suppose。

![](img/ffd282b2d431f9765c707d3effca38b7_723.png)

Yeah， has。So I suppose it was right to do one。

![](img/ffd282b2d431f9765c707d3effca38b7_725.png)

Plusで。

![](img/ffd282b2d431f9765c707d3effca38b7_727.png)

![](img/ffd282b2d431f9765c707d3effca38b7_728.png)

That's Greek， quickly iterate。

![](img/ffd282b2d431f9765c707d3effca38b7_730.png)

🎼So T is pretty nicely50 T times。one point zero two。



![](img/ffd282b2d431f9765c707d3effca38b7_732.png)

Should also be pretty。

![](img/ffd282b2d431f9765c707d3effca38b7_734.png)

So。I goes from nano blocks to zero。So if you do like I divide a number of blocks。

 we have a number from one。Yeah， so see that's the problem。They should be like zero， zero。

Should be a small number， not at large number。Yes see just thinking about the problem a little bit。

I think now we can play around this a little bit more。



![](img/ffd282b2d431f9765c707d3effca38b7_736.png)

![](img/ffd282b2d431f9765c707d3effca38b7_737.png)

Nothing is changing。0。1 times。Oh， this， this already goes from zero to one。 so we're going like。

So must can find that by 0 all the way to1。

![](img/ffd282b2d431f9765c707d3effca38b7_739.png)

🎼你有。

![](img/ffd282b2d431f9765c707d3effca38b7_741.png)

Okay。I guess yeah。What's啊。It's weird。It's really weird， I mean。

I think I'm going to do this a little bit different。 I'm going to do this。mGoing to assert。

There we have a life。Then we're gonna to do。At the very end。Block plus plus， I'm going to like。And。

Ile0， I。That' the number of blocks。O， syn text error。



![](img/ffd282b2d431f9765c707d3effca38b7_743.png)

系。那是。

![](img/ffd282b2d431f9765c707d3effca38b7_745.png)

It' working now。O。です。But now they're all falling at the sink。



![](img/ffd282b2d431f9765c707d3effca38b7_747.png)

Because we're not offsetting them。 Now we're just changing their speed。

But this is a little bit better now。

![](img/ffd282b2d431f9765c707d3effca38b7_749.png)

We can just now just add to this instead of more。

![](img/ffd282b2d431f9765c707d3effca38b7_751.png)

![](img/ffd282b2d431f9765c707d3effca38b7_752.png)

You I add 0 all the way to1。

![](img/ffd282b2d431f9765c707d3effca38b7_754.png)

ok。But。Actually。If you're going to add 0， all the way to one。

Someone's going to start about this one so this guy can actually be something like you。



![](img/ffd282b2d431f9765c707d3effca38b7_756.png)

Since we are adding in not。

![](img/ffd282b2d431f9765c707d3effca38b7_758.png)

![](img/ffd282b2d431f9765c707d3effca38b7_759.png)

![](img/ffd282b2d431f9765c707d3effca38b7_760.png)

![](img/ffd282b2d431f9765c707d3effca38b7_761.png)

Let's do this guy， at times。

![](img/ffd282b2d431f9765c707d3effca38b7_763.png)

Okay， thanks。

![](img/ffd282b2d431f9765c707d3effca38b7_765.png)

Yeah， I think。No， let's do that。 again again。 the block T。Tll use the map again。

 now that we have this little a little more figured out， so。

The block T is going be the map in normalize， so。I want to go。This is from zero to one。

Does that make sense？Yeah。

![](img/ffd282b2d431f9765c707d3effca38b7_767.png)

The other way。

![](img/ffd282b2d431f9765c707d3effca38b7_769.png)

Well， actually， it doesn't make sense。We're so close。We are so close。But not there yet。

This guy goes from zero to one in the first guy。So everyone should actually end in  zero。

 So this should be。0 plus something， right so。But it should really be a small number。

 so let's do like because。So， everyone should end。Everyone should end well。



![](img/ffd282b2d431f9765c707d3effca38b7_771.png)

Everyone should end in the correct place。

![](img/ffd282b2d431f9765c707d3effca38b7_773.png)

They kind of don't。

![](img/ffd282b2d431f9765c707d3effca38b7_775.png)

![](img/ffd282b2d431f9765c707d3effca38b7_776.png)

Now， if we just add an offset。主题。

![](img/ffd282b2d431f9765c707d3effca38b7_778.png)

系。If you just add。Thisob。

![](img/ffd282b2d431f9765c707d3effca38b7_780.png)

嗯。

![](img/ffd282b2d431f9765c707d3effca38b7_782.png)

However， we have to speed it up。In order to make sense， so it's going to be like this。

 this addition times to， for instance。

![](img/ffd282b2d431f9765c707d3effca38b7_784.png)

![](img/ffd282b2d431f9765c707d3effca38b7_785.png)

That's where we started getting。The number of blocks， this going to be from  zero to one。Tea is。

From zero to one as well。

![](img/ffd282b2d431f9765c707d3effca38b7_787.png)

If you just add that， they're going to be static， right？So。



![](img/ffd282b2d431f9765c707d3effca38b7_789.png)

There are some of them who start up there and some of them who finish。If I do， like1 minus。This。

T plus1 minus this。

![](img/ffd282b2d431f9765c707d3effca38b7_791.png)

We should go like halfway。

![](img/ffd282b2d431f9765c707d3effca38b7_793.png)

But if T goes。

![](img/ffd282b2d431f9765c707d3effca38b7_795.png)

Twice as far。

![](img/ffd282b2d431f9765c707d3effca38b7_797.png)

![](img/ffd282b2d431f9765c707d3effca38b7_798.png)

Okay， I think we should not do a map inter normalize。So T is already from one to0， right。

 we want everyone to end at  zero。But if we just， if we just forget about the map internal internalize and just add。



![](img/ffd282b2d431f9765c707d3effca38b7_800.png)

Well， that's what we were doing， right。 We should have side offset。



![](img/ffd282b2d431f9765c707d3effca38b7_802.png)

But they don't get to finish。So I need them to start， offset it。Offset。Right。So if I do like。

You had do your team minus this。

![](img/ffd282b2d431f9765c707d3effca38b7_804.png)

嗯。They start out。🎼Together。🎼ペジです。

![](img/ffd282b2d431f9765c707d3effca38b7_806.png)

Oh， myy ver。我北京。嗯。So。That's why it looks a weird number of blocks。This one。It's great tour equal。

Greateaer than or equal to the zero。

![](img/ffd282b2d431f9765c707d3effca38b7_808.png)

I think we got somewhere。理解。Yes。That's where we wanted。



![](img/ffd282b2d431f9765c707d3effca38b7_810.png)

You can probably。Can probably start out。

![](img/ffd282b2d431f9765c707d3effca38b7_812.png)

Really far。 know。Yeah。

![](img/ffd282b2d431f9765c707d3effca38b7_814.png)

Yep but not that far。

![](img/ffd282b2d431f9765c707d3effca38b7_816.png)

Now we have a start game sound， I thought we did。star。



![](img/ffd282b2d431f9765c707d3effca38b7_818.png)

![](img/ffd282b2d431f9765c707d3effca38b7_819.png)

Well， are we playing that sound？So I game sound we are。

Maybe I should increase the volume a little bit。And I'm also going to play that sound。是。

Because this is like we should have a sound whenever we finish。D啊。Never refresh La transition。喂。

Like here， so。If。来波 transition。Dot。喂。😊，Well。It's a really bad name。Let's go that finished。啊。

Not playing anymore。And when， we're going to0 that。But we're going to set。欢迎 to true。Okay。

And we should add。O。

![](img/ffd282b2d431f9765c707d3effca38b7_821.png)

看后器。🎼We haven't。

![](img/ffd282b2d431f9765c707d3effca38b7_823.png)

🎼大いつ。The problem is it's a be。迟。Seeid the wind sound。I think I'm going to use the swing sound。

 I I don't think we actually used it。Because it's kind of weird when。See we didnt use the文。

So let's use them in sound sound。It's called that。嗯这个讲。Do when。我也在这。没 sound。Okay， now。

Whenever we finish the level transitions。です。

![](img/ffd282b2d431f9765c707d3effca38b7_825.png)

Oh。Okay， yeah。 I don't know if you guys remember， but some of our sounds were not。



![](img/ffd282b2d431f9765c707d3effca38b7_827.png)

Ncorect。sampleample rate。So we do have to change that。Let me read quick things。Somem here。Ex region。

Let's render that。Stereo。lu。That's ground for。Data assign attacks change that to win。So。嗯嗯嗯，O。



![](img/ffd282b2d431f9765c707d3effca38b7_829.png)

Okay。Nextxi。

![](img/ffd282b2d431f9765c707d3effca38b7_831.png)

我 in done。来起来起来吃。

![](img/ffd282b2d431f9765c707d3effca38b7_833.png)

But I think when I do the other way around。you win。Which I'm actually called low sound。And actually。

 call。さ？いす。等一下。And then the start game。

![](img/ffd282b2d431f9765c707d3effca38b7_835.png)

那 play the loads。Well。Actually going to play。That on the change。And you， when I。

 when I go to the gameplay and play。And play the los。Okay。那这个完了。L sound。嗯。



![](img/ffd282b2d431f9765c707d3effca38b7_837.png)

But yeah， I think that'll work。 A couple things。I want to set the volume a little bit down。

And I wanna set the。The speed multiplier。So like。Maybe we can change that on Re as well。



![](img/ffd282b2d431f9765c707d3effca38b7_839.png)

な like。

![](img/ffd282b2d431f9765c707d3effca38b7_841.png)

That's the end of the sound I thing I didn't like D。



![](img/ffd282b2d431f9765c707d3effca38b7_843.png)

So I suppose the end of the sound is the start game。



![](img/ffd282b2d431f9765c707d3effca38b7_845.png)

没想。Thats。That's you。

![](img/ffd282b2d431f9765c707d3effca38b7_847.png)

No， it's not the start game sound， is it really the low？那孩子在了。



![](img/ffd282b2d431f9765c707d3effca38b7_849.png)

The end of this sound， I don't really like it。

![](img/ffd282b2d431f9765c707d3effca38b7_851.png)

🎼要落ちな。Something else。What sound is that？是。Yeah， we're like。We are playing。

 Let's see what sounds We're playing。Interface sound。So， yeah。Are plane。So。Bririck sounds。 Oh。

 we're going play a ton of brick sounds。哈。I think that actually may be impossible for us you。

To see what sounded。Yeah， I know what let's start removing the sounds， so let's not。



![](img/ffd282b2d431f9765c707d3effca38b7_853.png)

喂。So let's see what sound playing。We're playing the spring。

 which should be okay in the break that those are the only two。So， that's move。报名啊。pretty cool， but。



![](img/ffd282b2d431f9765c707d3effca38b7_855.png)

It's a lot of work to get these details down。

![](img/ffd282b2d431f9765c707d3effca38b7_857.png)

So it's not it。

![](img/ffd282b2d431f9765c707d3effca38b7_859.png)

Place。Well， we can actually try to figure out what sounds that。It's not the win。



![](img/ffd282b2d431f9765c707d3effca38b7_861.png)

谢谢。Yes， it the our game。Oh。因为这是事。好的，那。Okay。We do。So， this。Should not。整。



![](img/ffd282b2d431f9765c707d3effca38b7_863.png)

That's weird。

![](img/ffd282b2d431f9765c707d3effca38b7_865.png)

That's really weird， but。see if we comment any place out。我理解。Yeah， I have to do like the load sound。



![](img/ffd282b2d431f9765c707d3effca38b7_867.png)

Okay should be back to normal now， I mean， normal， I mean。



![](img/ffd282b2d431f9765c707d3effca38b7_869.png)

And then， maybe。When we finish。Level transition， Thank you。哦。De， delete that。

I will transition that plane。あ。え地域？Thank you true， yeah。So for some reason， we deleted that。Okay， so。

Maybe you could add the old sound。play。Splain。We said the level transition that。False。Then we play。

But we're probably gonna gonna play like。The old sounds pretty cool。



![](img/ffd282b2d431f9765c707d3effca38b7_871.png)

还有。想。

![](img/ffd282b2d431f9765c707d3effca38b7_873.png)

Yeah。Maybe等 a full volume。

![](img/ffd282b2d431f9765c707d3effca38b7_875.png)

It's kind of like something like failure。You should make that low enough just。



![](img/ffd282b2d431f9765c707d3effca38b7_877.png)

Yeah， let's try the start game sound again。

![](img/ffd282b2d431f9765c707d3effca38b7_879.png)

![](img/ffd282b2d431f9765c707d3effca38b7_880.png)

![](img/ffd282b2d431f9765c707d3effca38b7_881.png)

![](img/ffd282b2d431f9765c707d3effca38b7_882.png)

Maybe we can do it like this， but it would change the。That's a speed multiplly。



![](img/ffd282b2d431f9765c707d3effca38b7_884.png)

Light deeper。

![](img/ffd282b2d431f9765c707d3effca38b7_886.png)

Okay， I think。I think they'll be good enough for now。



![](img/ffd282b2d431f9765c707d3effca38b7_888.png)

Okay， and let's just。Yeah。It's pretty easy for us to make。TheMa transition right now。



![](img/ffd282b2d431f9765c707d3effca38b7_890.png)

哎定。嗯。Let's try making the main transition。The thing about the man transition is that it's the same thing。

But。唔知。是诶 was it called。Well let's go to the correct。有要来不？The draw level transition啊。

Same thing we want to do。For the menu。仲t下。There havent many like worth minute。Game。千传冇力。So。

This is basically the same thing， but instead of passing this value。Go to pass one minus。 So do the。

Other the opposite animation。And we can even make that a little bit attached because the menu should feel a little bit sner。



![](img/ffd282b2d431f9765c707d3effca38b7_892.png)

Okay那 see我厉害 not sure it's going word。

![](img/ffd282b2d431f9765c707d3effca38b7_894.png)

Entirely， now it doesn't work。Oh， because in the sea。嗯。Transition T。Yeah， you have to set that。

What else it in level。

![](img/ffd282b2d431f9765c707d3effca38b7_896.png)

Okay， that should be it。

![](img/ffd282b2d431f9765c707d3effca38b7_898.png)

Okay， but I have to change。

![](img/ffd282b2d431f9765c707d3effca38b7_900.png)

う。

![](img/ffd282b2d431f9765c707d3effca38b7_902.png)

See， I want to make that really， really faster。还是来。Almost1%， maybe I'm going to do a different。

Maybe we're going to do a different one for that menu， which probably just economy。



![](img/ffd282b2d431f9765c707d3effca38b7_904.png)

![](img/ffd282b2d431f9765c707d3effca38b7_905.png)

那天有然吗。爱奇艺爱奇艺。

![](img/ffd282b2d431f9765c707d3effca38b7_907.png)

![](img/ffd282b2d431f9765c707d3effca38b7_908.png)

Maybe there'll be no problem for the， for the first guy， for the first。

Look if I make the menu drawing afterwards。Because it looked weird in the game and since we don't have a drawing order。

Yeah see。🎼But I guess the menu looked。Think think we to do it a different。

It's going to be way simple。So I'm going do like。Draw leverage。就。And。

And we're going to start out as doing。啊。See。Yeah。😊，But I need， let's see， these wrecks。

Be done in the very end。And also， probably。Probablyably this as well。 And the menu T。

I'm not going to have a meeting team going to do it at normal。The normalty for the menu。Yes。

 see menu T and U T B。

![](img/ffd282b2d431f9765c707d3effca38b7_910.png)

Because I wouldn't star immediately。

![](img/ffd282b2d431f9765c707d3effca38b7_912.png)

🎼う？

![](img/ffd282b2d431f9765c707d3effca38b7_914.png)

嗯是是是是是。I don't think I'm gonna animate the bricks。I don't think we're going to animate them。

Sulate them。Im I draw them， but I'm not going to any。And this clear screen thing。

Do doing a clear screen。Clear screen。 I'm gonna to do a。Correct。D correct。Oh。

 I can just draw a right no， has to be a。And then I'm gonna就说。0，0。Hey， oh， man。 thanks for rating。

 I just realized I was read by Dragon's La，0，3，0，5，3，1。 Thanks a lot， man。😊，Thanks a lot。系系 jo喱。Hey。

 how are you doing， guys。Pizzso said learn Python， most popular and fast language。

 you can do anything and everything。 Yeah， a lot of people like starting out with Python。

 which has a lot of libraries for you to use。Yeah， and it's especially if you're going to go through the machine learning。

Space， that's where it's most used do 21 views Thanks a lot， man。

Pretty cool let me explain what I'm doing。So you guys can。Understand a little bit。

I'mJust going to comment this out。

![](img/ffd282b2d431f9765c707d3effca38b7_916.png)

So。The idea。🎼Yes this is。Starts out as a normal breakout game。🎼So we just。

🎼Playing I red B and I've been doing the whole thing on stream so you can watch the whole process。

 it's C and it's from scratch so。From the very first line of code。

 you saw me typing on stream and you're going to watch a whole thing and maybe learn。

We did a lot of stuff already， the game is pretty much on scrapping mode so in terms of like。

Things to do。 We are finishing up some details like La Trans now。

We improve a lot of some of the other game modes， so because this is the first level， right？And yeah。

 we are working on this leverage machine。あ？And then we had like a breakout with some。P ups。

🎼So we can have like some crazy balls and know， chip shotss。🎼And been thisまてこ。

And these red ones are part down。I just my controls I inverted can see that on the there， yeah。

And then we had the cool ones。This one's breakout tes so the idea for the game。

 the actual idea was what if every arcade game had to be like breakout？So we've had breakout Tes as。

H。念。啊。🎼オッケー？And then we we had breakout， oh， that was breakout P。🎼And of spoiled。

 this is breakout ts。好。Yeah。Okay crap。🎼Okay， and then we have a breakout pace babies。 This much。😊。

This looks awesome， thanks， thanks man。So yeah， this one's great。

We've had a lot of other ideas as well。 for game。 people had all sorts of crazy ideas for like arcade games that could be adapted to break out。

 Or I think I think I have to expand our power up。😊，Yeah， so these are the game mode that we have。



![](img/ffd282b2d431f9765c707d3effca38b7_918.png)

And mean this game is pretty complete， I mean， if you go to the YouTube channel。

 which is YouTube icon on slash Dan say Dan。

![](img/ffd282b2d431f9765c707d3effca38b7_920.png)

You can watch like everything from Let me pull up the playlist here。

We did like soft and rendering ourselves。We didn't like collision stuff。Did like game mode system。

 program the game mechanics， the game design coreps， which was changing like the Space invade guy。

Some gameplay improvements， game field， so this we worked a lot on this to get all sorts of crazy animations on the game。

Particle system。And then we improve the graphics by doing rotator things， doing bitns。

 doing subtics or accuracy， we did the audio ourselves。

 so we program the audio system and the audio mixer， and we paralyze that。They did the main menu。

 the save system， so we save your high start to a file in the levels that you unlocked。

implementedmple the sound， the sound effects， finished the mixer， we through the menu。

 and then we had to optimize the game and we' got the game running five times faster。

That was pretty cool。😊，And then we did some gameplay improvements with animation audio overall our robustness。

 Then we added thetes level。 That was pretty cool。 This was the whole stream and we added the Tes Last stream we added a a camera system for the screen shake and we red didid the collision system from scratch This stream。

 we improved a lot of gameplay and also did small stuff and the big thing we're doing now is the level transition。

😊。

![](img/ffd282b2d431f9765c707d3effca38b7_922.png)

![](img/ffd282b2d431f9765c707d3effca38b7_923.png)

The start gameplay looks perfect， I suppose， but they have to finish the out and I think we're pretty close。



![](img/ffd282b2d431f9765c707d3effca38b7_925.png)

Just have to draw this rectangle here and。And just drive me。

 this will be the color and this will be the alpha。



![](img/ffd282b2d431f9765c707d3effca38b7_927.png)

Maybe， baby is gonna。🎼Yeah， I suppose that no ability maybe。



![](img/ffd282b2d431f9765c707d3effca38b7_929.png)

![](img/ffd282b2d431f9765c707d3effca38b7_930.png)

Yeah， but we do have to。We do have to keep this guy supposed。

 So we are going to have a little bit of an overdraw。In our。In our menu。

But I don't think that's such a big problem。

![](img/ffd282b2d431f9765c707d3effca38b7_932.png)

We're going to have like a little bit of open draw。



![](img/ffd282b2d431f9765c707d3effca38b7_934.png)

Let's try that。I'll have to do the optimize。And the optimization was for the games you won at 4K。So。



![](img/ffd282b2d431f9765c707d3effca38b7_936.png)

Yeah， that was that was that was really cool I mean didn't even spend that much time。



![](img/ffd282b2d431f9765c707d3effca38b7_938.png)

Yeah so。

![](img/ffd282b2d431f9765c707d3effca38b7_940.png)

🎼Yeah， we are definitely not。🎼文有。We're going to go back to the menu。



![](img/ffd282b2d431f9765c707d3effca38b7_942.png)

![](img/ffd282b2d431f9765c707d3effca38b7_943.png)

🎼Yeah， I don't think it。I think it's perfect。Yeah。

![](img/ffd282b2d431f9765c707d3effca38b7_945.png)

Just wanted to drop by to thank you for the live streams Andy Cor the archive attending the process of viewing all the previous content currently I'm in the second video dude。

 thanks so much。

![](img/ffd282b2d431f9765c707d3effca38b7_947.png)

I really appreciate that you are enjoying it。Thanks for coming。Yeah， you know。

There are a lot of videos。But we are pretty close， man。 I can feel。 I can， I can smell the end。

 The end is getting close。And they are going to be here on YouTube。Forever， and。

And I'm also going to release the tutorial series， so this is like how the program are getting to+。

 which is like if people are having a hard time。Following the live stream。

 because live stream has to be a little bit crazy because we are doing everything live， right？

But you know， you get a lot from it。But if we want to more structure step by step think the tutorial can really help and it's pretty quick as well so I'm going to do more tutorials this week it's going to be really cool。

 I think。

![](img/ffd282b2d431f9765c707d3effca38b7_949.png)

I think we are done for today。I think we are we've just been rated and it's kind of sad to finish the stream with 14 viewers。

 so I think I may actually have to rate someone else right because I was rated。

Dregl got me a lot of people from history， so I think going had to。

Make these people and find another cool game development stream。So we did the main menu。

 which is the game thing and this heart level transition。Okay。

 and I think this whole review stuff add a sound to that。I think I'm going to leave that。

For the final game pass like。This game pass。And because next time I think I'm going to do the Async ODG reader and the asset cooker。

Not sure we'll be able to do them both in one stream。

But that'll be a cool challenge because the thing is， our audio files are pretty huge， right？

Let me just show you guys we are we have like。Yeah， 26， I mean it's not huge， but it's kind of big。

 so we want to do an OGG reader which can read very small and decompressed files。

 but it'll be a problem because they'll take a while to decompress so' going to probably go have to do that with our job systems that we created on the previous stream have to apply that you our OGG reader that are going to be pretty cool。

And then as a reader， that as a cooker， can be to generate a single pack file。

 so it would be easier to read and distribute the game。 so you don't have to， you know。



![](img/ffd282b2d431f9765c707d3effca38b7_951.png)

Have all these PG filing though。どすか。

![](img/ffd282b2d431f9765c707d3effca38b7_953.png)

Well see here at live streams， but tutorial any reason for the switch。

 I didn't want to teach how to compile a C program in Viual Studio。Because it kind of sucks。I mean。

 for the setup because you do have to run from a command shell， you can't。

You can't create a C project if also to you， so if you do like CL and pass a C file。

 then it will compile as a C program。But that's the only way you can do that and I didn't want to use another program because you just is the like the most user。

God hip see with him as， Yeah， exactly。 That's the thing。 man。 So I didn't want to。

 I since it was like a beginner series， I didn't want to teach。 I didn't want to teach， like， how to。

😊，Howp to set up the command shell and do it in a command line。

 then create a badge file like we did for this series。



![](img/ffd282b2d431f9765c707d3effca38b7_955.png)

I didn't want to teach all that。So。I just download the Vi Studio and just started you know a project。

 so that would be C++， but it'll be pretty much see like C++ going to I'm not going to do all crazy。

I wish it would give me C 11， but it doesn't yeah it。Exactly， man。 MS SVC， you like C。

Which is it's kind of bad I was playing。Jokes and you Windows users， Ana Linux。I have such proy PhP。

Okay， yeah， the thing is。呃When you。When you're using Linux， there are。

Quicker tools for you to get up and running Exp suppose， which is great。However。Well。

 this game is not going to be that big， but in the next game， that can live stream。

And we do like open GL and crazy hop shading stuff it's way easier to debug with Nvi tools and those are for Windows and stuff so that kind of sucks this developing aspect and players use Windows and Windows sucks。

But。All ass is pretty bad today， I just use scratch for everything。

It's pretty cool because when I search like game from scratch。

Which is like the name of the series that I make it like game， you see from scratch。

 you see all sorts of like。Of like， games in scratch， like。I supposed to dontate anymore。

 Yeah it's scratch， dodge the ball， easy game tutorial。Hard card programmers， absolutely。



![](img/ffd282b2d431f9765c707d3effca38b7_957.png)

So I think you're going to answer today， you can download the game and the source code for free on the HO page。

 which is dzd。h。o。And you can just click on this game and you can download each episode separately。

And the license it's pretty much not exactly the what you want。

So it's either a public domain or you know， you can do whatever you want， whatever you choose。

Do have live live stream schedule， not exactly I mean， since I do this on my free time。

 it's a little bit hard for me to schedule live streams。Yeah。

 but I'm going to I'm going to assume I'm going to do a live stream on Wednesday。It's around 8 PM B。

 Brazilian times， So let's see。

![](img/ffd282b2d431f9765c707d3effca38b7_959.png)

Brazilazilian time right now。啊。我接听。产着。And right now， it's like。6，50 PMm in Brazil。so。

Around like one hour from now， Wednesday， I'm probably going to live stream and this is the best time I doing workdays。



![](img/ffd282b2d431f9765c707d3effca38b7_961.png)

Wch is a little bit better for me。But yeah， but before that。

 I'm going to post a tutorial that I'm working on。

![](img/ffd282b2d431f9765c707d3effca38b7_963.png)

So if you go to my YouTube channel， you can see every live stream， oh a， how are you doing， man？

Brazilian Portuguese。In the words ofest esteemed former US president， how many people is a Brazilian？

Brazilience has like an exotic animal， isn't that？Who and what is a Brazililian？Okay。

 and you can watch the whole thing on YouTube。From the very line of code and I explained most of it right throughout the process and have any questions can just drop them on the chat or in the comment section。

And you can also。Go to my tutorial series where I'm going to teach her step by step。



![](img/ffd282b2d431f9765c707d3effca38b7_965.png)

A beginner friendly。Tutial， how to do game programming and that's going to be pretty， pretty fun。

 I think。

![](img/ffd282b2d431f9765c707d3effca38b7_967.png)

So that's it， I think I'm going to rate someone since I was so kindly rated by dragonagonslay。



![](img/ffd282b2d431f9765c707d3effca38b7_969.png)

I feel。I feel the moral obligations to rate someone。So let's， that's， well，Once。Ictor well in any。

How am I supposed to search for creator？あ。Oh， is there a game development？Yes， the social norm。

Game development， dude， how am I supposed to browse in here。Cgories。迟啊。GHub， yes。



![](img/ffd282b2d431f9765c707d3effca38b7_971.png)

So let's see who are developing games？嗯。RRPG game Dev with unity。

 did that sound good on before plugging design？A do weino to un that's really cool。

 I guess looking for science and tech。 Yes， that I was suppose I was looking for a creative。

 but yeah。😊，I think I'm going to read this unreal real plug guy， what do you guys think？That's rad。

 that'll be pretty cool Okay， so as always， we can go to my YouTube channel and thanks a lot for watching hope you enjoyed this live as much as I did and thanks for the raid again Dragons later。

 that was pretty cool。😊，And I'll see you guys next time。

