# 【从零开始用C语言制作游戏】 p18 Making a game in C from scratch! Ep 18： -Level Design and Gameplay -BV18i421a7DD_p18-

Hello everybody welcome to this new live stream in the series where we are creating an entire game in from scratch。

 if you have been following along saw the game progress all the way from nothing。😊。

And we wrote every line of code you got to see that on stream and all the way to where it's now。

 and it's in a great position if I say so myself， let me show you guys。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_1.png)

The game running， first。🎼嗯。And it。🎼ううう。So last stream， we had a lot of improvements。

Both in terms of the feel of the game O。🎼And we were testing。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_3.png)

The sound with rs and we made every block。It made every block give a power up or a power down。

 should I say？And let's say slow， yeah。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_5.png)

That's going to remove that real quickly。And if you go to my YouTube channel， which is YouTubetube。

com/danay Danan。You can watch the whole series。ItFrom the very first episode all the way to where we are now。

 and you can also watch。My tutorialctorial series。Which is how to program us again in C++ and in this R series。

More focus on beginners so you can go like a step by step and see the whole process of this stream is more like a let's just sit down in program but I will explain things that will come。

Come up against I you should say and if you want download the source code for free。

 you can go to the HO page with dd。h。o and you can download here in the game。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_7.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_8.png)

Not every episode's game and the source code。So you can learn and do whatever you want with it。机。😊。

Yeah， it's been a lot of absolutes。 I think we are coming to a。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_10.png)

Nice space。Now we finished yesterdays stream。With two bigger things in mind to do。

 first one is thetes level。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_12.png)

Because we worked on these four levels for some time。Which was the original breakout？



![](img/f50787a48fc38bca0b94a2fc47cf7c96_14.png)

The super break out， which has arms and iron downs。See。

 turning the volume for you guys little bit down。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_16.png)

And the pong， and we improved the pong last stream。

 and I think it's like way better see that was a collision book actually there that。

But the game itself。It's very better。Yeah。🎼嗯。🎼Yeah， it also improved like the ball size。

 things like that， that was crazy。😊，And the Space one。I think I。You to change but you're sounding it。

Things may be too loud and too deep。But okay， so let's start doing the the techest one， hey， Marcus。

 how are you doing， man？

![](img/f50787a48fc38bca0b94a2fc47cf7c96_18.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_19.png)

Nice to see you here。Or main in advances， dude yes， we we worked on the game for， I mean。

 now we have like a large consistent frame rate， have an awesome menu。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_21.png)

We worked on the Hong game mode last time， have like better looking ball and better looking。🎼啊。

Sounds also better sounding sounds。🎼九年。And that they're going to work on a new level。

 that's going to be a really， really cool I think。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_23.png)

Before we do that， I'm just going to just set the play movement sound。

Let's see let's change the volume down a bit。Let's add。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_25.png)

The pitch a little bit， let's see。🎼Okay。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_27.png)

えビで。Is still。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_29.png)

Too loud。So。Oh， in fact， if you just keep that maybe 2。5， multiply that light。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_31.png)

By smaller number。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_33.png)

I really like the way it is now， I think。Maybe I can even increase the guy a little bit。你 just。

Maybe this guy as well。Doing like01。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_35.png)

What's the range？

![](img/f50787a48fc38bca0b94a2fc47cf7c96_37.png)

🎼Yeah。I think that's good， so let's do the that level。The idea， not entirely sure， the idea。

But it's basically going to be like blocks of blocks。They're going to come down smoothly。

And maybe rotate。Not sure。And I think they're going to keep。

I'm not entirely sure how I want this level。Let's just started playing around with it。Let's do。

 Let's see， feeds。我 the老爸的。えちし。Make this the last level， probably。It change， well。

 the names are all wrong now。Sp like3。啊。Tatris。And I think that that be the correct order Okay。

 now there are a few things we want to do。 first of all， I want to set a color。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_39.png)

To the level。 And I found a pretty cool website， me see if I can。That has like tons of color。

Coed palettes。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_41.png)

AndThat's the one。So well if you can load yeah。So you can get like an interesting color palette for the des level。

 it's supposed to be really colorful。Let's try a colorful。嗯。Yeah， maybe maybe this combination。

 like the background， let's try this one。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_43.png)

E2 C 499 for the background well not sure which ones which no arena color。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_45.png)

你 two。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_47.png)

Do each of the C4。And then， let's do。E，8， a 7。Let's see。

 And we should probably also in the menu not have to add the name。Main your text colors。来过哪。Okay。

 and that's do。And we shall， we should also have to add。invalid， let's see。Here。😊，Here， yeah。

Let's just copy the pond guy。こ。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_49.png)

Yeah， I think thatll be enough。Nice， well， these colors。And we look blindly， oh my God。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_51.png)

🎼Yeah， the problem was the Greek。The green contrast with this color was。嗯。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_53.png)

We don't want to relaxing。And we're going to try these two colors。This one for the background。

 AD0bD9 E。See？エビティーなイ。And let's do 898。Let's see。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_55.png)

🎼你边是没事。🎼Yeah。I have like darker colors for。W。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_57.png)

Yeah， I think my a attract Dr color her for the inside。Let's just divide everything by two， so B。

Should be like six。Lines stuff like that。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_59.png)

It should be like 49。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_61.png)

7。🎼Okay， this is Ben。like that。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_63.png)

Now。Let's think， well let's just pull up a t。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_65.png)

Reference， what are we working on， We're doing a game in C from scratch。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_67.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_68.png)

And this is what we have so far， and I've been live streaming the entire process。

So it started out as a breakout clone。But then we add a couple of cool mechanics， like the first one。

Nice quality， yeah， we did that by hand。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_70.png)

Doude， just。It's funny， I here to say that。😊，Because that's the font。Lets seeYeah， there you have it。

And the reason we did that。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_72.png)

Before you guys make a lot of fun of me。Just we have this animation right here。🎼On the bottom text。

 can you see that？🎼The movie。Colorors。I mean， we could have done that in other ways。

I even like two bit maps and one masking the other one， but this one。

It was kind of easy and it was kind of cool well？Crazy stuff。Yeah， well， so yeah。

 and then we added pars， let's see if you get like how。

Going back to what they're creating so this the coolest part is the meteor comment。

Let we collect a couple power， these are pared down， so if we。If we hit these。

 oh we have bad attacks now， now the blocks are strong so we can't。Our back。Nice。Nice。🎼Okay。

 and then we added the cool things， I how you how you did that in the font you mean yeah。😊。

That was really， that was really funny。😊，Uh so the basic idea of the game is that what if like older Ar games do as far。

 then I celebrated and lost。But if other acade games were like green out， So we have like。

breakout palm。And then we have like brick out of space invadeers。This one is pretty cool。

Which one has its own。パってくるみたい。い。And now。We are about to create breakout techniques。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_74.png)

So yeah， that's what're going we're going to do。 Let's， let's look at a attach as reference。

 Let's see just first to get some shapes。 I mean， it shouldn't be that hard。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_76.png)

Right， but。Let's see， is that the original one that is effect？Well， these are our classics， right。

 this one。And this one。 So let's do the two of them。

 I think we're going to do the same thing as I did with the invader。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_78.png)

Which is the same thing I did for the software re rating tax， to be honest。Oops， yeah， okay。

 this great。Which is a。What level invader。Yeah we have a spwn intor。And。Let's do， like。A spa。Well。

 I maybe we can do it directly that on the text。太确。O。😊，Which is going to create a few blocks and see。

Get next available blocks at the life set the。Offpset。See。And the collar in the speed multiplier。

Okay， that's。That's about right。That's what we need。Let's just see what we have if we are。Okay。

 I'm going to close an open4 quarterr because I lost the reference。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_80.png)

Of the position of the。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_82.png)

Of the compiler buffer。Nothing it's going to be just easier。Okay。

 now let's go back to the ttriris level。嗯。Okay， let's do。

Maybe I'm going to try for bigger blocks this time。Yeah， relative of P。Worrry about that for now。

Let's not worry about that。That。And the color， but I have to play around the color。

You probably make a Ram color。Yeah。Randdom。It range 0 to55， probably make brighter colors。

 let's say 100 to 55。Yeah。I think that'll look nice， well。太有了。Have to experiment。对不在。

And the bosss be multiplier mortgage。Do anything。So convert from in to U8。Do those by hand。对。😊。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_84.png)

That's see if you get， like we should have like just one block。🎼Here we do。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_86.png)

I kind of like the size。This gonna be cool。So。嗯。Let's do a。Shapes。All right。

 which should be pretty much same thing as a text。We do better render。7。😊，Yeah， this guy。

It has a fixed height， though。Let's， let's try。Okay， and。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_88.png)

So let's make like every shape。You can try three by three。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_90.png)

So the first one。Is this one。And the other one is the。Its like。This one。Yeah。

I did the two of them for now。啊。Go do shapes。K。😊，Maybe this would be a time level。Or maybe not。嗯。

I don't know about that。No I think this is going to be a global。I call that trus ships。Titrus。

 and then we're going to do like， sponge shape。Poat， we're going to pass a number。

 so we're going to spot the first one。Yeah。😊，Okay， kind of like that。

And this is going to be done in the shape， so just going to spawn tap。啊。shapepe。😊，给。😊。

I'm gonna get like a shape。It's going to be tetrous shape。Inindex。Index。Danner can do like。

For let's call that。Trous shape。3。K。And for every guy。We should。Go through the whole thing， so。She。哎。

😊，Yeah。No， is this correct？No， this is wrong， I。I should let me see I with。诶。Get letter index。Yeah。

 okay， so this would。I'm just going to copy that。Because this is the thing once you think about。

One problem once。You can really。Make it like really faster， they just not think about。Here again。

 unless you need to， which is okay。Now， let's see you're going to run the text height and the same thing here。

And whenever we do here， let's do the get the next available block thing。Yeah。Okay。

 and I'm gonna to set the right of P。To the P。Whatever that is。Okay。And see。Let's see。

 where are we setting the P？Well， maybe you can just set that。For now。Okay， index。

Typo first typo of the night。Letter。しい？Okay， so we should really add like a。Block。L。Of sizeize。

Let's make that I'm going to try a little bit larger than what we tested。With before。

And this I'm going to add。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_92.png)

Should they be stuck together， maybe you're going to add a little bit of spacing。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_94.png)

Yeah。Spaccing。I a point one。So we set block， then we set。The way to the block。It's a block。

F size x times 2。Plus space。And then we just sink thing for the wine。Okay啊。Yeah。

 I'm going to do this， we need the original X。P to x。And let's do。Shi height minus1。

Fcodeers that's some kind of vim like editor yeah， it's more like an in like editor。

 but that's the basic idea so I'm writing the code4codeder and'm going to run on a Vi studio。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_96.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_97.png)

Yeah， but I really like for codeer， you can get the free version it's pretty complete， I think。

No need to set the colors or the next color。 I'm gonna， I'm gonna create the random color here。

 So color。So for every block， they're going to have the same color。How you like。好的。OhYeah。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_99.png)

Okay， now let's see what we have。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_101.png)

Okay， I think that was a huge success。And our first try well。Yeah， we just forgot to delete。This guy。

 we don't need that anymore。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_103.png)

Yeah， that was exactly what we needed。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_105.png)

Bads school is kind of boring。You know what I'm going to do， I'm going to get like。Yes。Gandom color。

AndIt's going to be pretty bright。And then let's do like color。Go do like。Choice。

We get a random choice。Cricing 3。Let's do like。This like。And let's see if the choice。Is。0。

Color will be。The random collar， then 255 minus the ring。And then 255 minus0。I点。ok。😊。

And then we can do the other variations like this is for a red brick。Let's try a brick。Oh， bricks。

 what they're called， I suppose。In a Texas。Okay。And then let's do the blue one。

Which is the same thing。Just changed here。And now， let's do the。2。What do I copy？Okay。

 I did got there it was just confused like two。3。Let's do four， which is going to be orange。Yeah。

 Steve， that's。you do something like this。Okay。Then that's。5。Which should be。

Can play around with that。A bit more potentially uninitialized variable。We， can do it now。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_107.png)

Okay。来 see。Wow， that was a pretty boring call。Oh， that was a nice spot。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_109.png)

嗯。Not sure I like our random though。や当。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_111.png)

🎼I think that was doing right。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_113.png)

Yeah， that's green。Let me make， like， 200。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_115.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_116.png)

Let's try these colors。Red。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_118.png)

I suppose our random choice is not。Work。还是天。We now to the 320。Yeah， this meant to be a bold， Okay。

 so I'm going to do like a ran。Yeah， kind of a misremembered how it did the。How we did the。

Random choice thing， so。A0，0 to 5。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_120.png)

Okay。Is see。😊，Oh， that's better， way better。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_122.png)

Okay。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_124.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_125.png)

I don't know if you if you got like。These colorsers。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_127.png)

Should be like。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_129.png)

Almost orange。Iose。I think I'm not going to reset。Yeah， I suppose that crazy red one。Think that one。

Dude， nice。I'm not sure if we already win the game or if we have to do anything else。Well。

It's maybe a bit too hard。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_131.png)

Okay， so we do win the game。So respond t shape。ok。😊，Now。Let's make them move。

 I want the shapes to move like individually。So I can't。See， we have like。

We have like the enemy P and the enemy Ep for the palm， the same thing for the invaders。For the ts。

Think about an array of those， let's say。How many shapes？Maybe 10 shapes。

 so let's try 10 shapes from now。Let mean。I call that check P。I'm going to add 10 shapes。

Same for the DP， or the DP is always going to be the same， right？So， yeah。

So whenever we receive an index。一次。Im to call this shape index。I'm going to receive。Like a a。

Shape P index， which is a kind of a bad name。But。That'll have to do now。In fact。

 I think going do this differently instead of setting dis guys。I think I'm gonna。

 I'm gonna do like this， the shape pe。And。This is like。Last shape index。So， the basic idea。

thinkI think that would be the best call， which is like we have the shape piece。

 let's see we have two shapes。Okay。😊，And they have different Ps and are're coming down。

Let's say these are blocks， like0，2。Zer one， two。3。So we do three and these are blocks。5ive to7。4，4。

5，6，7 PM。In this case， I want to store。诶。Yeah， I want to store these guys so the last shaping index。

 so I'm going to store like three， seven。And the position。Okay。😊，来 if we。2。Of。Pluss each。Is stores，3。

是。几。😊，Yeah。😊，I think that'll make sense now。We specify index。

And then we should set that to the last year and then last return。Returns。Last。O。😊，Which is。Well。

 should it be the next lesson？Next。They have a block。Maybe if you can just set the。The nu blocks。

So I don't need to return that。I would ever respond。Tts shape， respond shape。Then much you like。

And then we set。See the level state。Theteris。Dot， we have the next shape here。给以。😊，But we also have。

The less shape index。At this。It's going to be。这 number blocks。-1，0，1，2，3。Yeah。

I don't like how they turn now， maybe maybe I'm thinking I'm going to structure。

Thing's going to change the way we did the audio painting that turned out pretty well。

I think I'm gonna do the same thing。They want to do the same thing for the。For the block。

 So in the block。We have a round of P。And a P。Let's have like a master， like a。Parent。

And they'll be a pointer and it can be no， it can be no， okay？So。Whenever we on the block。Like。

 getlock。You have next available block。Maybe I should zero the block。So the block is gonna be the0。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_133.png)

0。I just see if we broke anything by zeroing the。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_135.png)

Everything looks fine。Okay， now we have the blocks。And they have now a point to the guy。

 so whenever we go to the game。Like update and see balls they par blocks。Riner balls， wall movement。

 draw head。So whenever we got like point or two of the block。Here， we。

We simulate the block for the level。Similulate life for level。

So I don't think you're going to need this。Oh， we do。Because we may。Yeah， we do need this。

 but we don't need this edition。Yeah， so the block P。In this case， you'm going to see like if。

We have a parent P。The black hill directly。Plus。Apparently。If you don't。

Rather than we just use the re in for construct。You are correct compiler， as always。Nice。

 now at this point。We don't need to do。This， well， suppose we do it。This is kind of a。アピ？And taste。

Okay。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_137.png)

Now we probably broke a movement。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_139.png)

Yeah， we broke the movement。And now whenever we start the pond game， for instance。Just here。

We say create black black。I'm going to add a new parameter。Here。Yeah， well。AT。

Should read a V2 I had a float pointer。This should be the oh I no， I think this corrects parent P。

And this one said lot。Parents came to them。This guy。Nothing think。Oh， we you use。

In these two situations。嗯。我 also说 ponded。Tacts are going to work in a second。

 and invader let's do it。Invator。I'm also going to。Set the block。Parent P to level。State。Evaders。

Dot enemy P。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_141.png)

Okay， okay， I liked that， let's see your words。🎼どこです。可以。s our breakout。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_143.png)

Okay， perfect now we are in a good position now。To in the draw sponge shape。Here。Here。

 we should also add。诶。先一。系啊。Let's go there。St。Shape edit。Which is also a bad name。Now， in this case。

 whenever we create the block， I'm going to set the block。Parent P is gonna be。

Maybe I can pass that directly。Let's pass that direction so2。Parent。第一。😊。

And here we're going to do the level state。Dot t。Dot enemy。P enemies， P is both。Maybe just enemy P。

 or recall call that shape P。 I maybe we did shape P。At 0。Ts。I forgot to add that。Ter。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_145.png)

ok。Now we didn't do anything with it yet。Oh did I miss Golet， no。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_147.png)

Now。You know what？I'm not sure。But this may not be necessary at all。

I think this is just a huge wage always of time。那就在这个。I am just going to。And。Is going to add。那就行。

Although it is a nice cleanup。And now we are more powerful if we want to do this。嗯。

I think we're going to end up just。Setting， let's see。Setting this guy， if you have a parent P。

Do this， I'm going to do something different for the。Tatris。嗯。Which is just at a constant speed。

Yeah呀。😊，嗯。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_149.png)

Okay。I think that's going to be。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_151.png)

If it's the Tetriris， block P is going to be the relative。30分之。10 years。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_153.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_154.png)

Well。Why didn't we do anything。Okay， we also have to set about。So this is gonna be the recipe。

And this would just be a fly。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_156.png)

🎼唱去。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_158.png)

It's going to be really really hard。Think。Yeah， maybe like one stick。

Would probably be detrimental to the whole thing。So。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_160.png)

Not sure if it's going to be a nice game motor or not， but the plan started out as a knot。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_162.png)

🎼S。Well let's start， that's all like。She。あの。Let's start that at like。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_164.png)

Okay， think。T到 be cool。It that'll be cool。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_166.png)

That's it like。没。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_168.png)

65 will be enough。🎼Yeah。🎼Wellれ。Fab cols， mess up。We're going to take steps of neighborhood。🎼7。は。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_170.png)

What do you guys think？

![](img/f50787a48fc38bca0b94a2fc47cf7c96_172.png)

🎼I don't know。🎼Yeah， see。Maybe you should make that slower。

Sosly if you are bigger or slower and bigger。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_174.png)

That's going to be pretty hard still。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_176.png)

I'm not sure I have to iterate。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_178.png)

じ。Let's also， make the menu。I do like。What's the position？P。First P。Let's do， like。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_180.png)

Peace these guys out。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_182.png)

🎼Okay。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_184.png)

Think we had a little bit more spacing。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_186.png)

That make that a little bit easier as well， let see。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_188.png)

Okay， nice， nice， nice。I think think that'll be cool。So I'm going to set like an X。嗯。

I'm to set that to0 the beginning。Yeah。And know what？Maybe you should get like a random sheet。

I think。For now let's keep like this Okay， now what Im what I want to do is in a wind condition。

We at the level。And we are。And we can check。At this point， it manager to like。Level score。Pe。When。

Let's call that level。But if it returns true， I'm going to return。So in the levels score changed。

Like returns。Yes。😊，是。啊。Actually， I don't think I need that if I add more blocks。

 this number of blacks going to change。Well， I'm not sure， let's see。Don't know。

 The idea is that I'm trying to do。That whenever we score point。I'm going to NVR。Yeah。This game。

I'm gonna see if we are supposed to finish。We're going to respond another shape of shape。pon在。

I'll that to it。O。😊，Okay， I think I liked。这し。感始。Okay， I'm going to pass same thing， zero to zero。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_190.png)

So whenever we finish one shape， we should get another shape。Forever。🎼close okay。🎼女牌儿。🎼好，我顶到哦啊。😊。

Those are clothes， let's see。Okay。Fai。It's way easier too。Do it like this。

 you have to try to get it ball 100% lined up， which is cool I suppose。🎼给你。Hello clonene。

 how are doing we man， they were doing the Teettris game mode？Okay， nice。And no shape appeared。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_192.png)

Next， that's what we need。O。😊，I'm going to spawn a random。Random F 32 range。I'm going to do like。

 minus the arena。Have size。We're going to have size x。That's for the first argument。

And I'm going to leave a random shape for now。那就来。Range， which is 0。And。系有。There are no haircut， Yes。

 you know， from time to time。You this is my the way I work with my hair。

 I let it grow for as long as it's comfortable here in the hot。😊，Brazil， weather。

Thanks and then I cut as short as uncomfortable' comfortable with so I get like the least amount of work relating to hair so。

😊，And then it grow pretty big then I cut it really short then I let it go pretty big again。

 that's like how lazy I am in terms of hair。I used to grip my hair long。

 but that is going away already。How are you， man？So at least one day I will have to get haircut。嗯。

Well， but I think you do need to know， make sure just on 25， okay， so we're pretty young as well。

I have a few friends that choose to make to be bold 100%。And it you know it' also hard work。

 You know， having no hair is also hard work。 So I don't know if we're going to be 100% work free in this case。

😊，Shait count two shapes for now。You can probably rotate the shape， that would be cool as well。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_194.png)

🎼感心。I think this is going to be a cool game mode。Because a bit more chill。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_196.png)

Then the other ones。At least in the beginning。Yeah。Okay， at was no pointer， yeah。

 we should really be like minus one。see。So。确实。She。Com。マナ1。No game mode， Yeah， we are doing yeah。

 Im supposed to they were supposed to be called game modes in the beginning。

 but we just call them levels。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_198.png)

Pdue the Teettris one。And this is going to be pretty cool。So we added like a couple new systems。

🎼So we could at like。Let's see yes。🎼それくれ。🎼Oh thisかにですかに。🎼Sounds cool。 Yeah。

 things's gonna be a nice one。😊，Because it's going to be 100% skill dependent。So。

Like that ones are a pretty good advantage as well， but this one's going to eat ornaments。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_200.png)

好听。I failed， let's add。I said the lose condition。Same thing with this invaders。It is yes。自己煮去食糕。Yeah。

Here on。Simulate level。 We go through each。あ。Do evar player completion tests。心累 block。Okay。

 so same thing for t。We're going to change the P， and。Oh， but it's interesting。

 we just said lose life in the invaders。Oh， but because this happens a lot。会嗯。

So this is kind of a hack。Were just call lose life。And lose life just。You know。

 we should really call game over， I suppose。Yes。嗯。Well， you just like。Instead。Q。Yeah。That'll do。

 I think。Okay， now。In this case， if the block P。Dot why。Minus the block。Havelf size。Dot why。Correct。

Yes。If that is less than are equal to。How much we did the thing we did yeah the player position。

In this case， I went to lose life。And actually this to kill。不吃了好久。These guys。

And this guy should not beans to kill， neither shoot this guy。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_202.png)

Okay。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_204.png)

Do we have。That cheat to make the。To make the， what is it is called the D T multiplier。第一。😊。

T multiplier。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_206.png)

Just we can test if we broke something。face。I suppose itll be hard test。Unless。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_208.png)

Unless we do like both of these guys。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_210.png)

Okay。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_212.png)

🎼无近。🎼咁 my god。So。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_214.png)

Yeah。This is not going to work。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_216.png)

I'm gonna assume it'll work， but。Because we didn't do anything too dramatic。Then we can just。

Pay the trick， play Te slim。🎼当系。I think it would be a nice change of pace。Oh。

 I think that felt right because that touched me。🎼Did not。I surely just do。

Wow so much for doing nothing。Do nothing win Yeah， let's like try to do nothing。Oh我说。Oh。

 help us again。Let's see。Oh man， that was so close so many times。Okay， so I failed。It would be great。

あて。Yeah， I'm not sure the position was 100% though。Just test that。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_218.png)

Yeah， okay， that was good enough。Okay， now let's play around with the spa of the blocks。

Spawn on the levels。Spon touchious shape。So now we are supposed to know how many blocks we spawned already。

So。I。State。Let's call that。Fpond。Okay， then we're going to add this。This guy。And okay。

 so whenever we。Son a shape。I'm going to set the level。State。That tris。Dot shapes bond。Okay。

 and whenever I。ever try to call him this guy。Let see give。Our shapes， let's say。阿次。Tensships。

 I don't know。So if it's less than 10 chips。Let's fund more shapes。Maybe I should。嗯。Okay。So。Okay。

 so if you are。Maybe we should test this first so when we。When we finish the game， like， no。Yeah。

 okay， so when you finish the level。If we only spawn to one， we're going to spawn this guy。So。

And test。Sky is less than。2，3。Okay， and if it's one。And is paw another one。Okay。

 so were supposed to like if we are one， another one， then we。This is actually two。Yeah。

I think thatll work。I'm I'm miss。Okay。Now we should。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_220.png)

Have two shapes in win。This is going to be full of close calls， I think， this level。🎼オケ。

It was fun two and one of them was weight。Much。嗯。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_222.png)

What shape is that？

![](img/f50787a48fc38bca0b94a2fc47cf7c96_224.png)

It was really weird if we respond three shapes。Do this。That was really weird， so。Let's do， like。

Max X。X， X。Let's do the next。It's going to be this guy。Minus。F。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_226.png)

Just find a new one。Nice。嗯。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_228.png)

You know what I'm going to do to be more interesting？Let's do like。If。We lost。

And we just spawned one block。I'm going to spawn another block。Okay。😊，And then。If else。

The blocks destroyed plus one。Is equal to the nub， so if there's one block missing。

And if we spe two blocks。Then'm going to respondwn to more blocks。Okay。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_230.png)

But。Yeah。😊，Maybe we probably had a timer。At this point。Because yeah。

 to make that a little bit harder。Let can just see how it's going to feel with。Two blocks at once。

🎼I probably add our downs。🎼As well to this night。So I got no block。

Maybe this level should should have a little bit of a progression。

 maybe it's going to start like this and the end the plugs will rotate。that can be cool。Yeah， okay。

So now it's gone。🎼很好。🎼哦。Okay， I liked that， let's add a little bit of progression in this sense。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_232.png)

Let's。Do you have like simulate。Block for level。Yeah， we do。🎼嗯。I can just make sure。Yeah。

 we first call the simulate level， then we call the simulate block for。So。I want to spa。Yeah。

So I'm going to add like a max。I know， like。Last block。Next。Let's do， let's block。PY。Last is a。

 let's call that。Top block Py。Okay， and then for every block， I'm going to see like。The block。PY。

Is greater。Then the top block P。Which is in the， let's see。See the level state dot tech。

If this the case。And we'm going to set that。The block。TY and she also add like。No need。就是。😊，Yeah。

I should also wear like a post simulate level， you know I need that， yeah。The simulates level。I。

Tacts， well， we don't have a t。 let's add。For three tis。I must set this guy to little very tall。

So we don't know if we got， yeah， I'm going to add a post。Singulate。外后。

And after we do the whole thing。Yeah， that's after the whole thing。Call that posts。新的。

So it's going to be the same thing。But now we'll be able to， you know， express like。Other ideas。Like。

 if。Let's say， the level。State do。Tris。Dot， well， don't mean？Top block P。

 I almost type top most block P。But it would have been wrong anyway。If this guy。If this guy is zero。

I'd say if it's。That they are equal to 0。We can do like。At our final。Waavs of blocks。

I'm going to add two rotateating blocks。Okay， and I thinkll there'll be enough。For this like。

 I don't know， maybe it's going be too short。开始。😊，If。The level state。Dot oh， man。

I think today's a bad variable named Dave because shapes the font because I don't remember the variable names。

Okay， so if we have spawned。Is it four shakes？Yes， if you have S four shapes。

And the other one just went past the middle of the screen， went spawn two more shapes。

We're on line 836。Swn。I just should be respond to more shapes。

Maybe all of them should rotate at this point。Well， let make the two of it rotate。ok。😊，So， let's see。

I spa two of them。And that would be the end， I suppose。X。Hard codeed。And。H。O。

I think this is enough for like。Pos level undefin it。Oh， I call that old simulateim robot。No。

AndI did realize that something was wrong， but I couldn't。Remember which one。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_234.png)

Okay。Okay。😊，Now。🎼Let's play。 and let's see the link。 Let's see if it's like。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_236.png)

Oh， man， close。🎼哦。So whenever we get to one block of this guy， we should spawn two more。

So we have one frame， yeah， we had one frame。Problems。

🎼And whenever these guys hit the middle of the screen。Oh， I think it's going to be too hard。

I don't know， I don't know what kind of idea is。Oh， I pin on blocks on top of each other。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_238.png)

Okay， I kind of liked that， to be honest。I kind of liked that。How are we supposed to avoid that？Okay。

And then we're going to make those guys rotate。A couple ways we could solve that。

 not sure which one's the best。You could partition。This going into playable areas。

How many we need that see？

![](img/f50787a48fc38bca0b94a2fc47cf7c96_240.png)

何？Oops， let's suppose this guy is like three in length， which is going to be like the biggest。

I can also write my name just for fun。With t blocks。So I suppose this。Yeah。

 I was supposed to have like five lanes。O。Five lanes。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_242.png)

So。I'm not sure maybe the beginning of the game。I'm going to make the order。Yeah。It like。L。哦。Yeah。

 I think。I think that'll be the best call， and let's make10。Sires。Okay， now whenever we。Start game。

Tatris。Which we should make Elaine spa oer。How are is supposed to make that？

There are a few ways to get random numbers to behave the way you expect them to behave。

Because if you just set these guys to random。Maybe we could just fill this array with random numbers。

And then we make sure that they don't repeat。I'm not sure。

 I'm not sure the best way to fill these guys with a referendum。Yeah， so。Just to be clear。

 the idea is to be something like have five length that six like zero four well。

 first one should always be three。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_244.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_245.png)

0，1，2，2。T be true， so it should be like something like this。We can't hard code that as well。

I think I'm just going to cheat。And hard code that。And change the。I don't know。 I don't know， man。

Because these are the kind of authenticity things that we spend a long time getting buggy like weird cases that the guys are on top of each other。

Or maybe we can just get a random one。And make sure。Don't know， the best way。嗯。

Let's just set the length paw under。To a hard coded thing。So starting out to zero。That you like。Why。

Then we do。4，0。Then we do， actually。这推接。And then we do。2。2。Before。And then let's do one。3。0。Yeah。

 I don't know， I don't know， man， I don't like that。Oh， I can't initialize the array like this。Well。

 that's some syntax。I'm not sure。The best way， well。You know what， I'm not going to。

I' not going to think too much about that。And let's just do the。I think by hand。3，0，2。4，1，3。And 0。O。

😊，Not sure this is。You know what， I don't like that。Let's do array of like last。lengths。啊。Okay。

 and we're gonna to do。And we're going to do the last four lanes。And we're gonna do like。Okay next。哎。

So the thing is。Whenever I spawn and attaches shape。Max。Thanks。Not going to get this guy。

But I'm going to calculate it。This。No， actually， this is。It's strong， but that's。

Do one step at a time。To few arguments。Oh。That's wrong。Yeah， this is what I want。Okay。😊。

Whenever respond， the t is shape。です。谢生。😊，O。Now。Crculate the XP， so。By grand。Maybe be random。

And range， let's do。Wonder four， so five lanes。Well， that's like minus2 to2。

 So that's going to be easier for us to do the。And for now， let's just spawn the XP。It's gonna be。

The whole size， which is。This guy。Plus。The arena have slide。So。This times this guy times two。

Times this guy。Okay， so this is like the full range。And if I divide that by five。

 I get the lane size。And Dan。I just made sure that it's like a random lane。O。😊。

Let's see if we respond in correct positions。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_247.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_248.png)

Okay， so we got our random lane I think this wrong。🎼ごめ。I like that's out of fact。

🎼And I was like really strong。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_250.png)

🎼やち nice。Oh yeah， we try fix that， so this the lane is working so we have to make sure that they don't spawn at the same lane。

So I'm just going to make sure that the last lane is different from the current lane。

 I think that's the only thing。And it's going to be way easier。Last。Okay， and let's call that。

Level state。Tattra do lastle。Equals。Family。ok。😊，But we should also fix that problem。

 And the problem is we are spawning。There's like one frame of them showing up right in the middle。

Let's see。Oh， because we probably spawn them after we simulate them。Yeah， when we hit。Let's see。

Does it called it him。When。Testment condition level， score change。So。Respon the touch with shape。

And we said， oh， we should we should also set yeah。The题。K they'll fix it now。

I'm going to set that right in the lane， but let's like if。Random lay。Is equal。To the random lane。

ToThe last run of me。A mean。玩哦。Its equal。And like a max iteration。Do it this guy again。

And then we do like the next integration minusine。And do like tens。And。If max duration is 0。

Can we just set that to like this guy plus one。This is really bad luck GiHub。

 you can download the game。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_252.png)

At HIO， as well as the source code。So I'm going to drop that link in the description。

You can download it the。Yeah， it's dayd。h。o you can come here to download now。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_254.png)

You are welcome to give me a tip， but you could just click no thanks。

 just take me to downloads and then you can download every episode to our code and the executable。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_256.png)

And you can go to my YouTube channel， which is YouTubebe。com/dza Dan。

And you can watch all the live streams from the very first line of code that we wrote。

 everything' is recorded， the whole process to this point。

 and we did everything from scratch and ourselves that's pretty cool I think。Yeah。

 you can check these sources out。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_258.png)

And if we have a max iteration。The random lane plus plus。But if the random lane。

It's great for you go fire random 199 zero。 so I'm going to wrap。Nap。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_260.png)

Yeah， sea can be a beast。 Yeah I really like seeing man， I mean， we did an optimization stream。

Was like。Yeah。Absolute 16， and we got the game， it was running at 66 milliseconds per frame。

On a 4K display。Of our softwareer render， and we managed to get that down to 12 milliseconds per frame。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_262.png)

If you go full screen on the game。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_264.png)

🎼I don't know who guys can see， we are sleeping， right so？😊。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_266.png)

We were sleeping at a locked 60 frame% at a 4K display and I was software Rer and we didn't do that much of an optimization job we just did a very simple theme of understanding the code and not doing anything too stupid。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_268.png)

And the other idea is we could have done C， we could have done motor thread。

 we do do motor thread for the audio， we could have done to the randomium as well。

 but we don't even need it man。And that was really， really quick。ok。Now。

I suppose this should be right， so I'm going to do like。啊。Random lane。And if it's minus1。

If random name。It goes to minus1。I'm going to do this whole thing。Otherwise， just go。So， yeah。

Random lane is gonna to be。Next one。- one。That one。Right2。Nice one。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_270.png)

Let's see if we should brought this step。Okay， so this is wrong right off the bat。

 so we are going to step the code。Because we got the first part running。You know first try。

 I suppose we should get like the whole thing running。But I don't know。 that's just that。

 So random number is2， so we should not do。This， let me should set the last lane。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_272.png)

Oh， you know what， let's do an unoptimized build。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_274.png)

So。Then we set the last length to two。And I suppose this is okay， so yeah， this is wrong。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_276.png)

This is supposed to be the very left position。Minus this guy。 So this is going be。

 they're going to have signs。Yeah。-5。I'm going to start out。Actually described those five。

Let start out here。 they're going to add。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_278.png)

Yes， the number of lanes that we can。So random name two。That lookss correct。Well。

 but where are the guys。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_280.png)

Yes， plus。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_282.png)

O ok， ok。Okay， so it's not。🎼Cented。妈。啊0。Now we're going to spawn at lane minus-1。

 so let's get a real number zero。And yeah。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_284.png)

You just said that the last lane not to zero， that looks perfect。Except for this guy。So。The random。

Lane。The amount of size we have， which is like。From minus arena size half size times 2。-10。

Proed by five lanes。Correct， correct。Times the number of random lane that we have。

This looks correct I think。That you give us。The amount。Berlin。And this should be like our offset。

 and we're going to start out at the minus half size plus5 position。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_286.png)

Let me step through this code。And let's see。We are-16。 I was expecting it to be 0。

So let's see why we are not zero。This guy's 32， so 32。Perline。Inner're supposed to be in linked2。So。

0。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_288.png)

Yeah， this not entirely correct。Does if you have like five lanes。The lane size is 32。

 I think this is correct。Or we should really add。Half of a length size。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_290.png)

So。So I'm going to call this guyline。La。Size。And then we're going to do it this guy。

Which is the leftmost ordered plus half。Of the land says or lane save。拜e。Plus， is sorry。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_292.png)

I think now should be good to go。Yes。Yeah， that's pretty safe。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_294.png)

And let's try adding rotation， oh let's me go back to the optimized mode。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_296.png)

And let's try adding rotation of the blocks for the last two blocks。Doude those some huge particles。

Nice。So we' got a bad position。We stop。And let's go。Let's see， our。That whole state。Well。

 I have to go to somewhere valid。Let's go to the W 32。Okay。The level state Tes。The left lane was  -2。

So in the very first lane。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_298.png)

Okay， so our problem is。Our names go from zero。-2。But we are operating as if they go from0 to4 well minus2 from 2。

 But we are operating on them as if they were going。From zero to four。

 So if the random is greater to， yeah， this is this is nice。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_300.png)

I may actually limit particle signs。Its because I think it's a bit too big for these。アしピ。

Now we've got two guys。🎼是吧看着 light。🎼The way they are。Awesome， really awesome。So yeah， these guys。Oh。

 there's also a problem on the last one。🎼These guys should be getting rotate once。🎼Dude。

That was a really， really weird collision bug。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_302.png)

By rotate it， I mean rotatedy。其实啊。Think this is going to be good， a couple problems。What if。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_304.png)

The plane destroys the two。Blocks from the third wave， not the last wave， the third wave。

What if it destroys them both？Before he gets to here。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_306.png)

So if he destroys all of them。Which is like。Changed。If he destroys all of them。

And there's only one spot。 Okay， but if there is actually。For respond。

It means that he destroyed that。Before they got to the center。This case， I should just spawn to。

And that should be the only thing I need。Everything else should be taken care of automatically。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_308.png)

🎼Oh man， let's go。🎼Nice。🎼awesomewesome awesome。🎼Yeah， I think you'm gonna to add power downs。

Just to make that in morning。🎼Oh that was that。🎼系钱。🎼Okay。Now we got to a pretty cool level。

 a pretty cool point time almost。Okay， you know what， let's？Let's rest。This level for a while。

So we can play that a bit， just make sure it's good。🎼エンでアメや。Dude， that was that was awesome。拉死么。

🎼We could probably also。ネット。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_310.png)

Make them move slowly， slower， I think we're going to do that。I do like similar。は。Or level。

And let's just add of like a fixed multiplier。Let's make， like。Yes， that's for a coder， the editor。

I really like it， I think it's really， really cool and canal do that for free on each child。

If you want to， I haven't gone much in the customization thing。バら。

But it can go crazy and just the auto intentdent。I think that that alone makes it really。

 really cool and they also call that like。Virtual white spacing。Because there's no。

 see if I press the left key， the left arrow key， it goes up because there' is actually nothing here。

 So I can't even mess around with this。 This means nothing。 It's just like a visual thing。

So I don't have to worry about indenting like at all。And who likes to spend time day？So， yeah。

So let's just make that thanking going to be。I think that's gonna to be everywhere。It'd be better。So。

In the block， I'd say。Is say if we add。This is 0。And this。It's like。When一 spa。

The text shape goes to like 65。I'm going to hard code。this guy， I'm going to call that。スピ？

So the speed。Will be。65。Or half of that so。32。5。Plus。Block route of people。ok。😊。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_312.png)

So if we are in the center， we go， we should really be here if we are。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_314.png)

If you are up there。啊。😮，Actually， this is wrong， this is actually the full 30 6 mile okay。Now。

This should be like。呃。Really big here and really small here。 I think that's what we want。

So I'm going to multiply that and it's also a a little bit of a multiplier right。八十は。好 maybe。

And then multiply that by the speed。I think we have a core result in the of right。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_316.png)

That see。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_318.png)

The idea is that it is going to go pretty fast in the beginning， but slowly in end。

 so see this pretty fast。WeLike， oh my god。Are they supposed to beat these guys？

But it's already slowing down。🎼So it's way more manage。I really liked this solution now。Dude。

 that was a great call。That made the game plays so much better。What was？



![](img/f50787a48fc38bca0b94a2fc47cf7c96_320.png)

Well， their position is different。They're going at different speeds。O。ok。Yeah呀。

We can't really do that。We should really tag the block。As like。Belongs to this guy。

 I was wanting to avoid。This。But I suppose there's no。There's no way around that。嗯。

So I suppose we need to know。后悔啊。So I'm gonna to add like a level。クす。Civific。谢谢。ABlock。来ful。うそ。And。

 let's do。Like La info。Do you like。原因。呃。This guy's going be just。嚟。谁？I now that we have this。

 we've probably simplifyified a lot of our decisions。Yeah， but we are going to need this anyway， so。

但是。So instead of the shape Id， I probably need the position。So， yeah。Okay， so。N we do this。

I'm going to add。I think I liked these values。And I'm going to add。To the level state。Theteris。

Dot block。Our that。I'm going to call that enemies。P。We block。来不。Whats that。I have a specific。那是搞的。

Dot shape I。Okay。And we're not going to set。不要道解。Just a。And then when we simulate the level。

Theteious。I going go through all。So I'm gonna to go like from the first one all the way to。

LikeLalstate。ta。Thatts bond。I don't remember。This is called。Shapeped spawn。

 should really be spawn shape， I think。Shaped long。I suppose so for every shape we。I'm going to set。

The level。Stay dot taxes， again dot enemies。P。Jo why。Plus， equals。To this guy。And this going to be。

But actually starts at zero， so it's going to be。0。0265， I suppose。

So I'm going to make like 6 to5 minus this guy。So now goes。From minus。s five。All the way to0。

Which is correct。Okay， now let's add。82。Enemies P。来写。8at？And whenever we respond。Trous shape。

LetSee whenever we add。So shape spa， I'm going to assert。That the shapes pond is。

Le then are equal to the array rate count。啊，等来夫。St。Tetris。Dot an。Okay。Okay。啊。Enems P。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_322.png)

Okay， let's see。We talkedd a lot of code。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_324.png)

Yeah。So yeah， not exactly what we wanted。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_326.png)

So。Oh， we didn't hop that by the。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_328.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_329.png)

等。That was like the theme of last stream。It's kind of funny that we saw back with was。🎼プリコ？Oh， man。

That's not going any slower anything。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_331.png)

嗯。R of P。Then， I'm going to add。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_333.png)

皮。Wellll this should make the blocks just like。🎼Not move at all， and they don't。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_335.png)

So was's probably the way we were studying。It。哦，我 not下你的。We're not selling the。

That's one problem we're not saying this。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_337.png)

Now I will not send the shape。 I D。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_339.png)

Forgot to do that， so let's just make sure that this first shape moves the way we want that。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_341.png)

🎼そう一。🎼So yeah， it's quick， but not too quick。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_343.png)

And it's already slowed out。So our math is probably wrong， but we're not set the shape anyways。

 so it just should be zero so let's see。He。So the enemys P dot y。Increment that。Oh， this。

This is wrong。Oh no， that's not wrong， I mean， theoretically this is wrong but。

That's step to this code。 So levels at line 952。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_345.png)

🎼theyre not。So RO Y is zero。So 65 minus0 should be 65。65。

And we just have checked that of various small numbers。 So we should just。Add a little bit now。

Next frame。Our wise， a little bit。It's negative。嗯。Okay， so if you， if we are negative。

We're getting a greater number， not a smaller number， so。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_347.png)

还是好。I suppose this is wrong if we start out at zero。And at minus 65。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_349.png)

No， yeah， this is exactly what we thinking about， I'm not sure。What happened there。 So this guy。

And this guy。It's getting larger。65 minus 68 is like three。Oh， it's minus-02。65 minus-3。

So it should be just like 65 plus。🎼还是。65，60。like -1。65 plus minus-1 is 64。Oh。Yeah。Okay， you know。

 this corrects because this is hard coded。The check that was pretty stupid。

 let's just see the result。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_351.png)

🎼でぷ。🎼での？Let's see if you're going to get faster。🎼Yeah， I think。

This drag record just just very slowly。You pretty much stop halfway through。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_353.png)

They're making 65。Plus， this guy。They'ing going to make twice as much。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_355.png)

I think that was the better that we should had。It's pretty fast then I'll encourage you。🎼がねてる。

Maybe these guys should use sub pixelixel accurate。🎼Yeah， see how。 Yeah。

 these guys should be something。Smaller。🎼Let'sJust see if it actually will stop or if I'm going to adapt well。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_357.png)

🎼おす。Oh， because we were incrementing that。Oh no， this is the shape I think think。O。Okay。Let's just。

这 the shape I。Never respondwn Tirus block。他 just。And we're going to set the block。🤢。

We also we could also play around with this now're going to set the block。Level specific。Dot。好，我在切快递。

2。おわ。The number of shapes bond， -1。Okay， and this guy's going to be one。Plus。The shapes sp。你就是。

Times like 0。1。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_359.png)

Okay。Now， that's play to see how is that。🎼うんだ。么ね。Okay， I really liked it， really liked it。🎼Re了。🎼经到。

So I'm going to add for the second block， I'm going to add power downs。For the third blocks。

I'm also going to at par downs。🎼These guys will be rot。🎼Me。🎼啊死了。阿死。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_361.png)

🎼So， yeah。は。吓。😊，哈。😊。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_363.png)

Isn't that cool， I think that's pretty cool。I think I can more levels now。Yeah， I liked。

 I really liked it。This guy can be a little。More。啊。And then let's say。

 so for the second guys and third guys， I'm going to add power downs。Let's see。 Tes shape。

This is pretty weird code。This。Yeah， it is just nuts's。嗯。But at this point。I'm going to， yeah， like。

If。嗯。The shapes spawn。Its one。Or say。wo。But it's less。 if it's greater than or equal to one。Actually。

 two。And。Greater less than are equal to let's say。Two， three， four， so four。Go to set the block。

Bar block。Intergering range。It're going to be all the way from。来。Per up。Last plus one。To the。

Poward count。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_365.png)

Oh， actually， this is like。🎼In everyone well。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_367.png)

And I think you're going to make the par blocks really big just。So I failed。🎼啊。Okay。

 these guys should be par downs。🎼They do。Every' pretty hard。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_369.png)

I don't think these guys will give just。Just a second one。Just。Give par downs。

And let's see if I can increase the size of the par。Power block。Yes， we do have the half size here。嗯。

How am I going to specify that？

![](img/f50787a48fc38bca0b94a2fc47cf7c96_371.png)

Now I'm not going to worry about that that's hard enough。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_373.png)

So the R is really weird。Looks like an A。🎼那选个。🎼な这。I'm like， oh my God。

 why did I you have to make me hit it？🎼Its going be really really cool。🎼好め。🎼なイス。These guys。Yeah。

 so it's definitely a different level from every other one。Oh。Okay， now it's getting harder。

And I think the last one just have like， two shapes。And rotate。

And then maybe' going to have one more that it's like three shapes that rotate and have power downs so that's going to be like a full on。

Cycle there。If I managed to get that far。🎼Yeah goes。Now I'm kind of scared。Yeah。

🎼This guy is pretty cool。This point importance。🎼So。These guys should be rotating， I'm crazy。🎼O嗯。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_375.png)

I think I like it。Let's make the rotation part。How about that？

m maybe today's going to be just Texas state。And then。Next time you can do like collision。

And the few stuff。And I know what's that。Maybe enough for the game， then we do the polish pass。

I think they'll be a。A nice call because then it will be around 2025， I think。

 because I'm going to do a couple polishes。Maybe these guys are going to take two streams。mabe。

And for the gameplay Explor， yeah。Because gameplay takes a long time。

And I think you guys got the idea。Maybe we're going to do a couple levels offstream。I don't know。

So let's add rotating blocks， so a couple things for the catch game， rotating blocks。And。

Rotating blocks。All two rotium blockss in。So I am going to take like a。Onehy not break。

If I get more water because my voice is running out， would you be interested in making games in rust？

嗯。Not really。 I mean， I'm using C。Because I don't like crazy stuff。And the compiler。

Not letting me compile code because he doesn't think it's correct。I classified that as crazy。I mean。

 I really understand the use case in bigger projects。But this is just a project for a fun。

And I'm just doing games for fun。 I'm not doing games like big games commercial games anymore。

 So this is just for fun。 and I don't really want to be fine with a compiler。

 I want to compiler with my friend。 That's one of the reasons I' don't to use C++ is because it's like really crazy。

😊，So yeah。Not really interested。But who knows， I'm not going to say I'm never going to use rust。

 but not right now， I think。And I don't really have with the games this scale， which is pretty small。

 I don't have the problems that Ru helps with like aesthetic type checking， aesthetic。

Memory checking and stuff， pointer stuff， we'd also have the create stuff with pointers。We did the。

Today， even。And I'm not sure how Ro would like this。We added to the block。

We did that to the audio as well。A pointer to a V2 here， which the parent be？

This is like probably not very recommended if you're doing like bigger projects with more people on the team because this is very unsafe。

 so to speak。 But for this game there we're almost done， I mean， who cares。 So yeah。

 not really interested at this point。 But who knows later on， not sure。

Wt me a break to get some water。get my voice back a little bit and then we're going to go back and finish the ts level。

 which we're going to add。These two things， rotating blocks。And the routine box pro。

 I think that can be a good level。If we manage to get this far， it's going to be a hard one， though。

 okay， be back in a minute。Okay， so let's do the final thing we need to finish this level。

 which is the rotd blocks and the rotating， I don't mean like full rotation like we did。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_377.png)

With the particle system。I mean， like。This is the block。And then it'll become this block。

drawraw that。And then it'll become this black。And then it'll become。这 one的可能性。Okay。

 so this is what we need to do， we want the block to animate like this。Now。I think I'm going to add。

A couple of things， like。I think， each block。Not sure how I want to do this。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_379.png)

Because let's demonstrate show you guys how we're doing this at this point。Just like， spawn。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_381.png)

Okay， so we have specified。These guys。And what I probably want to do。Maybe。

 maybe I can hard code this。嗯。Because like this guy， let's say this guy is zero。

 let's talk about this guy。This guy is 0，0。And then， let's say。Well。

 can we make that a general thing？I think you can make that a general thing。

So if we assume a three by three。Matrix， so to speak。What the blocks？

And then we just swap the X and Y。Yeah， I think I kind of like this solution。

 So let's say we have four mates， four matrixes。😊，Matrices therefore four matrices。Like。😊，And then。

 we just specified。Specify the first block position。And we save that。And whenever we rotate。

 we just change the x to my。And here we're going to invert the x。And。

And here we're going to invert the X and y。Okay， I really， really liked it。

 really liked the solution。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_383.png)

We liked it。So I'm going to do something like this。And for the P。Yeah。

I think that's the only thing I need。I think that's the only thing I need。Now。

I probably make this a global。Timer， so I'm gonna add like。A rotate。Tr。

And whenever I simulate the game。Well， let's just make sure we didn't break anything。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_385.png)

We should not be 100% centered now， and we can probably change that yeah。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_387.png)

I change that。 So the base P。So being this guy， I'm also going to offset that。Byuy this much。So。

We'm going to make that。I'm not sure I'm doing that with my head。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_389.png)

Yeah， I'm just offsetting that in the air。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_391.png)

🎼So yeah。Scra though， minus， yeah， should be like。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_393.png)

Okay， I's see。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_395.png)

Perfect now。We want to play around with a P。In some circumstances。ok。

So whenever we finish the rotate。I'm going to get。All the blocks that are marked。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_397.png)

From like this guy up and rotate them， I really， really liked the solution。😊，I think I even。

I don't know， I really liked it。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_399.png)

不觉大。Okay。No， this is not fun。 This is。This is。Okay， now whenever we simulate the level。M late。来咯。

We are going to。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_401.png)

And is that is that same thing I mean？Right here。We change。We make the minus。 the y will be minus y。

It to be x minus y。 this is like， This is X， Y。 This is x minus y。This is。Minus x。Mus y。And this is。

Yeah。And this is minus X。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_403.png)

So I're probably going to save。The rotate。lel都ate。はい。Okay， now whenever we simulate the level。

I'm just going to see， French shape。I'm just going to increment。Let's called it detector。Okay。

Then we're going do like。Tatris。Roate T plus for Z T。And if the。This guy。ItGreat greaterer to。

Two two seconds。We're going to zero that。And then we're going to go through all the blocks。So。来。

throw the blocks and if they're alive。And if the block。Level specific。Dot。啊。A shape I。So。

If are shaped。I D is greater to， I'd say we'll go 1，2，3， forces here2 equal than 5。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_405.png)

In this case， we're going to see。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_407.png)

How I'm going to add and this I'm going to set the tes。Rotate， I。Plus， plus。

 that what would you like？If this guy is greater than four。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_409.png)

Its back to。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_411.png)

Now， guess's going to。If it's  zero。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_413.png)

If's 0， I'm going to set the P。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_415.png)

手抓系。The block。P， X。And this would be the block。TY negative。Okay， think I just。Do this。可以。😊。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_417.png)

Else if we are one。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_419.png)

We're going to go this transformation will we already inverted。 So I'm just going to invert。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_421.png)

The X。And in this case。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_423.png)

I'm going to reinvert why。有是情。So， in this case。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_425.png)

going to real to why。And in this case， we're going to real the X。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_427.png)

Okay， that looks good， that looks good， I think。Just for testing， I'm not going to。

Do this if maybe you're like for everyone oh。啊。O27。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_429.png)

I see if you got a rotating block。Wow， that was like the best run I ever did and that was the second best run I ever did。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_431.png)

They're not rotating。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_433.png)

Put a breakpoint line。Nine， five fives。The letters。ok。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_435.png)

OhWell， we are optimized but。That's not the ultimate。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_437.png)

Okay， rotate I is zero， so we should。We shouldn't like the P。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_439.png)

Oh， we're not considering the P， oh， this is wrong。So I forgot about hard work。

 this should be the reality。The P is calculated every frame。Based on the parents。Okay。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_441.png)

Now let's see some rotation going on。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_443.png)

So what happened was RP went all the way down here， oh， okay。嗯。Okay， so you know what。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_445.png)

Our we want that P to be local。 like this guy has to be zero。 And that's not the case。

 We're setting like the whole thing， so。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_447.png)

Yeah， let's go back to a respond。Tactas shapes。And this guy。 So this guy， why should be。あセピーですか。

So this guy is just going to be。This guy。And0。But。That's the P。But the level state。Dotteris。

Dot enemies P。In the shapes sp position， I'm going to move this guide。Afterwardward。

I think I'm going to do this like the last thing。S。F。I'm going to change that to life。Number one。

那就 be。Expon。Okay。😊，I're going to set in me be Shas bond to this guy。Oh。You know what。

 let's make that。That's made like leveltes。Tes。Okay， and let's see。 whenever we see a level weight。

I should start。Okay， syntax error。Be2。😊。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_449.png)

At see， at at see。🎼Okay， it was offsetted， but。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_451.png)

Okay， our rotations are wrong， probably。This guy is X and Y。Oh， yeah， this is like wrong。

The X becomes the y。Yeah， so let me。Yeah， I was thinking about that when I dropped。

 but when I did this guy， it was all wrong， So this is X and Y。And let's see if this is like。

It is like， I know，2。One， odd。Take that one， two。是吧。This is supposed to be like0， one。Yeah。

Pronounced to be supposed to be minus one。0， so。And that and this guy。We should。

Think this is correct。And this is probably like this。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_453.png)

Okay。😊，Let's see啊。At。But this has going to work， I think。So first guy is going to be。

Minus y or minus。Why am this guy's going to be collegebacks？And then we go back。

 so we'm going to change again。But all of things we' going to be negative。

This guy is already negative。This guy's gonna be。I think。Entirely sure。And then I'm going to。

Sp them one more time。And。Yeah， the first。Then the why。And then the x should be  united。

On the why position。I suppose。嗯。Yeah， I'm pretty sure this is wrong we have to do that more carefully。

 but who knows and the last one I'm going to swap them again。And the。

The x is going to be yeah like this。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_455.png)

我要。Let see what's going to happen， I'm not sure I don't know what will happen。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_457.png)

🎼あ、オッケー。Okay， now'll be。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_459.png)

Okay， first of all， our offsets should also include the YO。In the spa。In spontaneousatious shape。

This should be both see。This guy。Call that upset。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_461.png)

Okay。😊，And I think we got something wrong。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_463.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_464.png)

Yeah。Which should really be upset， like。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_466.png)

Mus1。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_468.png)

Let's stop the rotation for now。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_470.png)

Let's just make sure we got that offset。🎼Uually set。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_472.png)

And we are not。The y is problematic。 The Y is inverted。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_474.png)

Okay， now the X was correct as suppose。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_476.png)

🎼W was whatでしました。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_478.png)

You know what？We start off。We should add， like。王府街。Left。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_480.png)

Let me put a breakpoint here at a 393。Let's see， oh， not， not。Not like this。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_482.png)

行。Okay， we should also。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_484.png)

🎼爱奇艺。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_486.png)

Well。So our offset is minus8， our half size is four。Let's see。 We expect。I suppose scrap。1 is 8。5。

 so at this point。see， at this point。Our x should be 0， and it is 0。So I suppose the lane is wrong。

Let's see what we said the lane， like the enemies。 the， this guy should be0， something。 Yeah。

 it is up。 Oh， we should also， we should not remove the initial offset to that guy， so。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_488.png)

Yeah， so this offset。Has to be used。Here as well， so。Oh， it is used。

So I suppose it's not supposed to be， yeah， it's not supposed to be。Block have size unde declaredlar。

ペシなんでくれる。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_490.png)

爱情。Okay。I think this is 100%。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_492.png)

TheB should spa a little bit。A little bit up now。see。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_494.png)

And we were using that some other place。🎼You just see。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_496.png)

， this is。It's pretty。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_498.png)

🎼Oh， it was used on the speed， lets see。🎼Yeah， I think you I have changed。🎼Is it just slowing down？



![](img/f50787a48fc38bca0b94a2fc47cf7c96_500.png)

本呢。Not呃。I'm going to make that a constant。Fine。I'll just change that。70。Go to make this like。Tatris。

Shape。一秀白。Okay， and whenever we。So at the speed。 So it's in the singlelay now。ああ。7。In the block。嗯。

I was just silly。是没了。This point， let's see。 we。This guy to one of 30。

 which is like supposed to be twice as。And that's probably。I就。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_502.png)

Dude， what is wrong with our col？We're going to look into that next time anyways。

I didn't know it was this busted。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_504.png)

It's a little bit too fast， I think。We're going to decrease that by。So it starts， starts off。Oh yeah。

 because this guy has to be。ok。Let's now turn the rotation back on。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_506.png)

Let's see how that looks。🎼So why。RI is plastic。I think。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_508.png)

Yeah。We are supposed to start Oh， okay， the Y is different， is it not。No， it's same thing。Oh。

 because we are decreasing in the y， so yeah， the y is supposed to be there。Is that correct， yeah。

 because this is the other way around。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_510.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_511.png)

Okay， let's see。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_513.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_514.png)

I think the math is right， but of course it isn't but。Let's see what the problem is， this P。

Should be。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_516.png)

Mine is the offset motor， let's see。I is 8。5， okay。And this guy should now be。0 minus8。5。Oh。

 minus 16， okay because the offset。Okay， the offset should not be， should not be signed。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_518.png)

Let's see。 Yeah， this， the offset， we do。Minus the offset。What it's the outet。Okay， okay。🎼谢一。Okay。

 I suppose you are correct。We are correct。Wow， that was really cool， but7 was too project。

And it's easier to see on the other guy。🎼そげじゃないけ。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_520.png)

Well。よし。Let's hardcode that。 let's change the 70 back to 65。And then。Let's make sure whenever we。

Fwn theteris shape。When I receive a random。Yeah。That's me like this。So， we always。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_522.png)

I was getting the first guy。65 was。Okay， so。I think our why is wrong。

I'm going to run through this guy one more time。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_524.png)

This guy。Because we should actually make like relative to the previous one， so this。

This transformation right here。Should be。Like this is， let's say this is zero1。Correct， 0。我。

You want this guy。To be  -10。 So the first one。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_526.png)

First one is supposed to be correct， let's see。き？First one。

 we inver we place the y on the x and invert that。 So this is one should be minus1。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_528.png)

And this is zero， so。-1。何じ。ok。Now， this is like。This situation here。This transformation here。

We are supposed to to be。I see， now this guy is -10。Yeah。Its supposed to be minus y。

Which is what we are doing when it's why now this guy。ItIf it's minus-10。We want it。To be0 minus-1。

So it's going to be。嗯。Do I。Yeah，'m going to change the y here， remember this is not y。

Im to place the white here。And then minus1 I'm just going to place the x here。

 so no need to change the sign。This we got this shape now。Which should be0。I right。Yes。

 now for the last piece。I want to end up being one。0。

So I'm going to place the minus y here and X again。Yeah， so。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_530.png)

We're going to run through the other shapes as well。So just like。We change the sign。

 we do nothing to change the sign again。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_532.png)

This guy。And then we for the last one。It's when it's 1，0。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_534.png)

Yes do not just。Swap like this， okay？

![](img/f50787a48fc38bca0b94a2fc47cf7c96_536.png)

Now。Let's see for another shape， let's see this guy is one one。那啊。Yeah， this guys one， one。

 this guy's one minus one。Yeah。So this is0 minus1。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_538.png)

So we don't do anything。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_540.png)

This transformation。1， one， yeah。Then yeah。No， this iszebra one。This is great。0ero one。

And this one is one minus one。关。Yeah， and at this point， let's see should be one。one。And。

That's what we're gonna to do。Correct， one， one。This point should be。Should be  -1，1。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_542.png)

So， yeah， I think。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_544.png)

Let's try that one more time。Okay， I just think we are swapped。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_546.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_547.png)

You see can if I decrease the guy。🎼说理解。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_549.png)

And what is that？Normal shape。呃。7。Normal shape。Is。Yeah， the first one Yeah， tolerance is right， okay。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_551.png)

牙子。🎼This is the first shake。🎼Looks good。Now this one， the X， the y ist important it。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_553.png)

why。不是。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_555.png)

Yeah， we should probably do like one at a time。🎼So。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_557.png)

🎼あ。😮，🎼And the X should not。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_559.png)

🎼Have been inverted。哦。But just to be 100% safe， I'm going to make this guy even。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_561.png)

Seconds。🎼So this is。Correct。Perfect。🎼Now， let's go again。Yeah， I think， think。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_563.png)

I think that's more correct at least。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_565.png)

I。Let me go back。谢一在。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_567.png)

2 will。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_569.png)

Okay。🎼Perfect。🎼Perfect。🎼Andベ。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_571.png)

I think there's 10%， so were' only going and do this these guys。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_573.png)

Let's。Go。Oh in 70 is oh 65。Still too much。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_575.png)

And I can probably go back。In。B。T。啊啊。Is that called。一心。Yeah。😊，来不。This guy。

Let's increase this kind a little bit。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_577.png)

一始唔ち。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_579.png)

Do we have some crazy artifacts。What has to do with the rendering hardware？When we destroy the block。

Well。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_581.png)

Whenever we lose also， let's try to lose one first because they'll be easier let me just reset the game。

🎼Okay。That's weird。That's weird。Okay。So you still haven't drawn anything yet。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_583.png)

And then， we。You said the score instead a start game。And on start game。We said到。Ll。Oh。

 theres just a plan。And then， we。Their life。The current level， zero the level state。Reet balls。

We should probably reset the blocks as well。Zero， oh， we zero the blocks。Okay。Theres other particles。

And we spun in a shape。I think this will have to be done in the end of that level。

Because this shapes。Well， I do set the enemy tea。To 060， which is correct。And then， okay。

He saidid Shakesbe， you won。企。Now。Block py。Is greater than the。J。What's going on here？😮。

The blocklock PY。It's greater than the。top。I'm not sure it's not going to change anything but。

This is wrong， we should return at this point。But the block top， okay， yeah。Oh。

 because we are in the middle of a loop here。Yeah。Yeah， this is really wrong。

I probably have a flag or yeah， we do have a advanced level。Is it set， no， it's not set？

I think I'm just going to set that。No， advanced level。Not sure， not sure I'm going to structure this。

The crazy hackck。Yo man， how are you doing？Let me show you what I've been doing today。

🎼It's been pretty cool I think。Have a new level。Just ttrous。🎼Yeah， there is a problem。🎼スパ？

That prompt's not supposed to happen。And。🎼中要你玩。Really well？I a little bit tired， he should be told。

But I do want to finish this thing。🎼But this is going to be a little bit hard。

 our collision is great for back， this is going to be a little bit hard。🎼Because it has to do。

🎼Oh man so。I thank you for the tips I finished interview trip to see from him here with the guy teaches being interesting awesomewesome man。

 yes， it's really cool and he's such a great programmer。🎼It's really cool man。

 it should really start the main series now。It's awesome， don't be discouraged by the size。

Because the results are pretty cool， I have a couple things I want to change here。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_585.png)

Wantna make the。Wanna make the， let's say， I that simulate。Level。I to make the speed。たちだろ。Yeah。

 I want to make this feed。What they going to say about？Yeah。😊，Yeah， man， it's really cool， I mean。

 through follow the series up to like I followed。When I first started， I followed like。40。

But I was casually following it then。I started to learn for real。

 So I started all over again and did like， I watched one episode and tried to program my own version of handm madeade heroro。

 right， I did that up to2200 and something。😊，Yeah， 200 something then I quit。In the good sense。

 maybe have to work that on me， but I was doing some quick sneak peeks through some videos in looks so frustrating ready。

 have slow results。It depends man， I mean， yeah， in the later part of the series， that's true。

 but in the beginning that's not true at all， I mean in a in a couple of vessel。

We're going to have some crazy， crazy results。Yeah， I mean。

There are a couple of slower series like the debug part， a little bit slow。嗯。That I can remember。

 but if you watch that twice this week， I usually I usually watch it little bit faster。

And if there's like critical point， I just go back and watch that slowly。So。So I didn't I didn't。

I didn't spend。Too much， I mean， it was a long time， but it wasn't that long。

He was just showing a great pixel T map with in the 30th video。 Yeah， I mean， but。

What he teaches I think that's why did this series。

 this series is to be the quicker result version of Hemi heroro， so we had a gameplay on day two。

 right？But the truth is。He's the time to do a robust engine and we're not doing that in this series。

So we're going to learn how to actually do audio for realels and the whole thing。

 going to be theory behind it。And then they're going to learn theory behind everything up to that point。

Like and bitnps and he does some Tao Chung thing that was pretty cool that was a really hard for me to understand at that time。

But yeah， so it's a。 So you gotta， got a。Got a approach there with the mic setup up。

Really exploring a simple space， right？And。Yeah， and then the other hand。

 I have my intro that I just started。 I don't I don't think I showed you that。

 I don't think I showed you。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_587.png)

I started my how to program in S++ tutorial series and this is actually a tutorial series so I go step by step I have some like cool drawings I did。

And I go like， step by step。And hopefully，'re going to have a cool game。 And it's gonna be even。

 even faster。 It's gonna be like。😊，Seven to 10 minutes video minute video。

Then I'm going to edit that together just to show the main thing I've never question yeah。Yeah， this。

 I only have one video so far。Because they do take a long time to make。But I really。

 really liked the result and people also did， I mean 200 years already， it mean like two days。

And 200 views is a lot for my videos。Yeah， I think let me show you the link Oh it's my it's not my YouTube channel。

 right？

![](img/f50787a48fc38bca0b94a2fc47cf7c96_589.png)

Okay， so hopefully I could just finish。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_591.png)

The。🎼Yeah， I was the col of them， right。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_593.png)

It's weird like the first frame。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_595.png)

Yeah I have to delay that。What are I doing the spacing invaders。Like in the loose。Life， true。I just。

 I just I don't know。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_597.png)

I think this is also wrong for those space invaders。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_599.png)

Do you think that's folly？Do you think that follow me？

The make series would be great to improve general knowledge and see or maybe there's another message getting less time because I am planning to apply for a job in the future that would require CPC+ plus I am planning to study a path。

 maybe I should be thinking about some AI part students see，'m not sure yeah。

 the thing is if you're looking for a job in that sense。

🎼We should really see what kind of projects the company makes。And it should do that。So probably not。

Handmade hero， I sure probably that's not the best path， yeah。

So I suppose it's AI since you mentioned AI。I think you should。Do a little bit of the he heroines。

Just because。He does teaches a lot of programming in general。

🎼But just enough so we are really comfortable seeing， I mean。

 maybe we really comfortable being confident enough。🎼To be able to create your own projects。

 both searching for already existing solutions and tutorials， we're already creating your own stuff。

So I suppose， yeah， if you're already on that level that you can express your own programs。

I really think we should just go ahead and focus on whatever。

That job requires if it's AI just focus a lot。On AI and the practice will make you better really。

 in terms of like programming in general。So yeah， so even if you focus on a small project， small。

 by mean I mean a focused project you can focus on a like specific project with AI。And do that a lot。

🎼Like every day for like up。Some time。🎼You are a general。

Programming lot knowledge inC will improve a lot， so you have it can be。Go to be easy on that sense。

Cool， actually one， I actually watched the first three videos and I had a few the main lounge I was going to get it just about to win those lips and how to make things。

I in the favor。Let me see if I can。Maybe you can watch。🎼で。🎼Let me just。🎼Well。

 I'm not going to tear around the main amount。But check out。🎼The engine architecture video。

Then I think they want after that。🎼I believe I'm going to watch our series yeah my series is going to be pretty cool because it's going to be pretty focused I。

😊，So you're going to get the best big for your product， I think， and yeah。데이터웨이プ 있고。🎼バラ。

I think maybe in the meantime， why I don't finish series。You can watch the architecture lecture。

 the An architecture lecture， and starting from that， maybe watch three or four videos。

That's after the we those stuff。And then he starts creating like the tile maps and things like that。

And you're going to learn because the main thing that I think you can take away from Mes。

🎼Is a semantic compression， which like his way of programming。

And he also wrote about that on his blog， so you could probably take a look at that as well。

 so take a look。🎼About semantic compression on his blog。After I test this。

 I could probably link you to that to that blog post。🎼But a semantic compression。🎼The main thing。

And and watch that。And watch that。Architecture， angel architecture。Video。

 start and probably a couple months after that as well。So that's going to be a good introduction。

 I think， so the main points about general programming data。🎼Cool， yeah， no problem。

 let me tell you that works out for you。😊，This is taking a long time man。🎼And。

It's also see if the results are going to be visually problematic。Let's be honest。

I don't think it matters because。🎼I think we want to change that， anyway。But I don't know。

 that's just。Keep good for a while。🎼Yeah。🎼You。🎼Yeah that picking up speed， finally。

🎼Maybe just the pitch changed。🎼Now we would thinks picking up mys speed。🎼う。

Maybe like three more passes。Yeah， two more。🎼客室的。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_601.png)

Yeah， we do we did have。To accelerate the game。But the game broke like like crazy。

 So that what I'm going to do with which I should have thought about that earlier。

You justt increase this speed。In which they are that movement。Yeah。Yeah， let's do。 like。

 let's just improve this guy's D。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_603.png)

Yeah。So but that was I don't know。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_605.png)

Even more。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_607.png)

50。But we do have to pay attention though。Oh。I think it looked fine。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_609.png)

我要。Yeah， it looked okay， I think。But we still have to。I lose life。

If we are supposed to do an insta kill。Instead off doing this。I'm going to。

Set the advanced level true。Actually， I'm going to send the advanced level。Yeah， true。

Yes said the advanced level target。To current level。We're going to introduce this variable。

So advance。来不。We're going to have a advanced level target。Okay。And at this point。

 whenever every we advanced level。We should really do that。Level target。

And whenever we advanced level here。So in the picture。Let' set the defense。Level target。

 current level plus one。爱次。然后。Start game， you said that false。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_611.png)

Yeah。😊。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_613.png)

Let's see一下 download。Oh， Russell trying adding a sub pixelixle things to that。🎼七が7。 it worked。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_615.png)

Okay， and that was pretty easy， but that took the longest time just to。I don't know what happened。

 My head is kind of empty now today， I suppose。So I'm going to play a little bit of that level and I think that would be enough for today。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_617.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_618.png)

Oh， let's also just try well。你的。Blocks。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_620.png)

I dont know。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_622.png)

JustThink about using the subpix or accuracy renderer for the block。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_624.png)

If you should your life， fits greater than some size。Yeah， let's do that。In the， let's see。

Let's see our start game。Ihy don't we have our spawn。Tuches shape。

So if it's greater or equal to four， let's do this test。In the game。When we draw erect。Or yeah。

 let's do this silk kick so okay。I red draw direct for the see。Does the ball。Is the particles。Okay。

 this is the。This is it。going to like。Oh this kind of weird button Is to like if blockss。Have size。

X greater or equal thats do at9。来。We're going to do a septicel dry else or not。Yeah。3。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_626.png)

Right。Let's see if that's going to look great。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_628.png)

That looks way better。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_630.png)

And let's see the performance。 Well， since we have just。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_632.png)

F blocks。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_634.png)

Oh， but are we not optimized or I think yeah， we're not， thank God。

 because we're running pretty badly。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_636.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_637.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_638.png)

Yeah， this is awesome in the pawn game。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_640.png)

Maybe啲。You know what？I'm going to do them， I'm going to do it for all of them， for all the blocks。

 the。走色。你首。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_642.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_643.png)

Yeah， we don't have that many blocks anyways。So。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_645.png)

And I think it's going to look way better in these levels。

 it's just wasting performance with the blocks them move。🎼うん。🎼我 like。🎼Thisなしま。

Since it's a pixel accuracy， we do see a little of bit of here and I't think it's a problem。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_647.png)

🎼It's a little bit of the wall。🎼嗯。Yeah， it's even kind of stylish， so let's accept that as a feature。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_649.png)

And let's check out this guy， yeah it's way better。Yeah。Tacts fund。

This one looks the best because they move pretty slowly。Yeah， look at that， that's perfect。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_651.png)

Okay， so we still had the problem。So we're not done yet。You still have the problem。

When we do the when。的き。In condition。来夫。Square changed。But that's weird because this。

Task for condition。Oh yeah， we do that in the middle of the thing so I think I'm just going to add this to the post level thing so。

Yeah。Maybe I should。 I should。just add a。Yeah， I think want to do this。

T that's going to be a little bit cleaner in the Texas level， I'm going to have like。A post。Level。8。

Shapes。Okay， so it's going to be zero by default。And in this case， I'm gonna set like the。

Levels take Teris。Dot post level sponge shape plus equals to one， so plus plus。And in this case。

 you're going to offset that。九9。Okay。😊，先等你。I can probably。A bit better。Okay。I I'm going to post。

simulate level。Tents。It's also doing like the four。Okay。

Then I'm going to do a spawn t shape passing minus one。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_653.png)

Okay， so that should be fixed。And let's put a limit on the particle size。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_655.png)

Fn explosion。It'spon partners。Have a base size。Let's see block。Detried。Yeah， that's your like he。

The men。Of this guy。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_657.png)

I say two。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_659.png)

开始。🎼Yeah， this is way better。Yeah， this is perfect。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_661.png)

う。And I should also make the ball。Use the sub pixel。到。啊。How do we draw？Alright。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_663.png)

Bander balls。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_665.png)

I think that's going to be smooth also。Yeah， I don't see that much。Since we're not fenc。

🎼If we really focus on the ball we see that we be a couple of frames。

I don't think there's anything we can do about all that， to be honest。

Im master for use like Fiallist。🎼Can I going in this project？The soundtracks。

 the school makes the difference in X thanks man I'm still learning about making music。So。

Awesome to see。And she liked it。うう。🎼う。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_667.png)

Oh， look at those space invades。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_669.png)

Okay， I'm going to take that。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_671.png)

But。Now that we don't。We don't。Increase this guy at that point。Well， that does make sense， right。

 that let me track explain because we finished the game and we shouldn't have finished the game so。

In the level score change， I'm going to return whether or not we should cancel it。A board。

 let's call that。 So if it's true。Okay。😊，So level score changed。Theseer two， like。Returns。If we。

Should。Aort。第。The test。Proed。This case。True。Yeah。you guys back in。This case。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_673.png)

Okay。行。Oh。Nice。🎼Okay。shapepes spawn。We're probably。You go to their rate count。Yeah。Who is this guy。

 I don't recognize him。You know I。To go after me to understand。

But I told that to clone style earlier。The way I operate with my hair。

Does Ita grow as big as I'm comfortable with？And then I cook that as short as I'm comfortable with。

 so I have the minimum amount of work。With my hair。

 so you're probably going to see through the live streams' getting pretty big again。

The ain't going to see me trim that。Pretty small again， so pretty short again suppose。

I was a bit slow on my part to get the joke。But in my defense。

Today's been a crazy live stream I mean I really enjoyed it。

 we created the Tes game from nothing other the way to pretty pretty complete， I think。

 I mean once we solve this problem。😊，Yeah， so I need to post simulate。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_675.png)

Okay， yeah， the problem is。Yeah。😊，I the post simulate thing。We should reset that variable。So， yeah。

 post simulate。And then we set that back to zerooo。Because。あ。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_677.png)

Otherwise we are going to keep spawning like crazy。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_679.png)

🎼なち。🎼あめ。A you getting that I understand% correct？I would dude that takes the collision。

We're going to do that tomorrow。No， not tomorrow， probably probably thanks stream。

I'm sure going Saturday。🎼う。🎼う？Yeah。查。Oh， we're almost talking。🎼Nice。🎼One more。Okay， I'll take that。

🎼Okay， that was perfect， solved problem。It goes to destroy all blocks before they truck in this game mode it is。

🎼Re。🎼Yeah。🎼行。The last wasn't intense， I think it may be too hard。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_681.png)

To be honest， I think the speed， let's change the speed。Yeah， that's hard。

But that red light wasn't it。Yeah， man。That's way too hard。Let's do the simulate。Level here。

Let's play around with the speed。N。Let's make that way。Oh， sorry to changed the wrong one。This guy。

And change that to maybe。I don't have a bot。What are you what are you trying to know， man。

 I can just ask。I don't have that many frequently asked questions anyways。😊。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_683.png)

🎼I don't know yet。 Okay。Okay， nice。Now this guy has the par downs， I really liked this level。

In terms of this structure。Ill think about， but it's really hard。Well。

 since our collision is problematic， it's even harder than it should be。Oh， my god。🎼And。That's wrong。

 which probably should have gotten two。And these should be the rotated ones。And they're not okay。哦。

No I suppose it is correct， these should be the rotating ones let' see。And I'm not rot either。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_685.png)

Okay。Is this correct， though？Let me cheat。And let's do like， lose life。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_687.png)

I上 lose life。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_689.png)

Well， but we have a few problems， right？The rotate。Is wrong。If our specific shape is greater。Then 5。

Can we rotate。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_691.png)

嗯。I don't know。🎼I know。🎼です。🎼エスティ？Adang。Yeah， okay now that's correct and we've got two wow man。

 I don't know what happened。I probably watched the video I'm going to do that。

🎼Because probably we described too early or too late。But these guys are not rotations。🎼Let me。

Let me stop the game and let's go to the。🎼Levels 9， out9。🎼あルラぱぱパ。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_693.png)

🎼一？🎼So， yeah， this is certainly not。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_695.png)

🎼Let me。Great point？

![](img/f50787a48fc38bca0b94a2fc47cf7c96_697.png)

Okay， rotate， let's see oh， we are in the crap。We are in the optimized build。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_699.png)

Okay， so I think this would be the last。 I said that a lot today。😊。

But I think this would be the last thing we need to solve。🎼Nice。🎼Nice， almost nice。Me。🎼Yeah。

So this was perfect。い。Oh， dude。How about that？🎼Okay let's。Se the break front here。Frame。Let's see。

 I rotate。Let's set that too。ok。Now。What happened。What？😮，Happened。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_701.png)

Oh， we say return。Oh， dude。Levels。Okay。Yeah， this should be continue。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_703.png)

Okay， now we can probably go back to losing to life。And I think。That will be the end。

Of thetes level at the least for now。It's pretty hard， but I think it's interesting。

There's probably another bug。🎼That bugが。That bug that happened when we are。🎼ほあ。啊some。awesomesome。

What is wrong。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_705.png)

So I'm going to leave it like this for today， not sure about maybe one thing that could be making it easier to place have some line。

That would show the path that the ball would go and introduce the platform。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_707.png)

You mean like a。Like。啊， let me。Try to understand what you need。Do you mean。Something。Like this。

But maybe that goes all the way here， exactly so I didn't understand。Well， that could be interesting。

But that could be visually。Too， too much， I think。That is one idea that we couldn't。

 I like this idea a lot。This one， I'm not sure， I mean。You can pull the features。

 but I think it'll be worth trying， maybe。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_709.png)

So I am going to write that down。Because we finished。

Quotes that you do and I am going to write and note to myself that play Te。And write notes。

Play like our tennis。 You write notes and review video。😊，Before， I don't know。3，38。

Because I didn't know the time。And see。A bug。In the。in啲啊。Shape on。I think it。パ threeうで。

Individual shapes， I don't know。It's going be it's going to be hard to by。

Then not using OpenGL nor SDL。 Youre correct。 This is not using。pen， in fact。

 this is our rendering code。I typed open GL here and that was nothing。Our software rendering。

Is the whole thing。 so it's like  a thousand lines or you have a couple of 1 thousand lines file。

 we have levels is  a thousand lines， So the render is 1 thousand0 lines， let's see game。😊。

Gaming 700， almost 100 Windows，600。Inception。So we're doing everything by hand。

 we have the very simple ones like clear screen that we iterate through all the pixels and clearing them。

And we have more complicated ones like。Draw text。Well。Yeah， I suppose that doesn't count。 Hey， Ivan。

 dude， awesome to see you here， man。😊，Let me show you the game。

 we worked with that a lot today and we also have a recursive。

 we also have draw direct with subject of accuracy。That was awesome。 First time live。 Yeah， man。

 in what time zone you are in Italy， right， Italy's probably early morning now， is it correct。

 That's awesome because actually， I don't say this like usually。 But today。

 I got really excited because we managed implement the whole Tes level in our breakout game。

 That was pretty cool。😊，We have a， like the draw bit map。 So if you can download the the the I。

 you can download the chat。 No， you can download the。😊。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_711.png)

The game recursive and check out how we did that on HIO here in the very first day we implement the rendering so you can go to YouTube channel and watch the first day。

 which we implemented the first very other rendering And then later on we did like rotated rectangles and we did。

😊。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_713.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_714.png)

Bit maps。And you can download each of the source codes and play around with that。

 just pick download now。You're having to give me a tip where you can just skip that and just download。

 Yeah。 so can watch the series see how we did the render with no SDL and no open gel。

 It's pretty cool。 I remember picking a bouncing ball in the same and we share the source code。😊。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_716.png)

Oh， that's really awesome， is that x86 or S 64 Stan？Yeah， four o'clock， quite a night animal。

 but have you left， I mean， you just woke up or you still haven't go to sleep well， it's the latter。

 man， wow， you're really a night animal。😊。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_718.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_719.png)

Let me show you what we have now。So we finished this menu and we optimize that to run no still a woke so I can't feel tired。

 I'm tired， but it's still like 11 pm here so I'm not I shouldn't be tired， you should't be tired。

And I' just take that menu。Yeah， it's kind of inspired by Stephen Salage Ro。

🎼Have you turn your volume up a little bit？Just so can I hear the music？Yeah， so we have like the。

Now， like the breakho clone， that's the first level。That's not too exciting， except。I didn like。

 are you？ういい？🎼Yeah呀。I can move。Trulyo good80s I mean。

It's a bit modern in terms of like the game feel and the animation and article and stuff。

But the idea was to get the best both world aspectss。Ca I wasn't even around in the 80s。

 so I don't know exactly the feel of the 80s， so all I can do is apply my 21st century twist to it。😊。

对。There so this level。Just a wall level。We have power ups and power downs that we can get。this one。

 this one made us vi。What else？The comics the best one。敢带走。🎼Oh， crap， okay。🎼へんへ。🎼圆糖。Hong breakout。

 that's the idea of the game， I mean we should really。

 it is to like what if every Arcade game was like breakout over it？I got that far out。Okay。

 and we got Congress the first one and we proved that a lot last stream and I think that's pretty cool made it pretty fast。

🎼And now it's really terrifying， suppose。🎼你 the good。🎼看到不菜信耶。🎼欧耶，哪有找成了7氛钟面了喂。🎼爱人命。

It's really fast pace。In contrast， the Tes， which one that we used the red ball was looking so powerful。

 yeah， the comment was awesome and we didn't increased the size of it last stream that was pretty cool。

🎼So Tantris is the one that we play today。And I don't know if it's 100%， but it's getting there。

So we committed that， we had to restrictstructure a lot of stuff to make sure that oh crap helps closed。

🎼。🎼う。That was a nice move was it okay， yeah， I did it。🎼嗯。Yeah， see， a collision。

 the collision is still still wrong， we're going to review that next stream for sure。

And I think that's the only thing that's really missing maybe。🎼And little bit a screen shake。Yeah。

 I still have to work on this level a little bit。🎼啊。Yeah， I'm not entirely to sure it。

🎼But I to blue that。It's got an idea maybe it's already in。🎼休剪。Oh， nice， those people。🎼春节这。Yeah。

 with the collisionlegia problem。还始闹。就这样。Oh， actually。

 I'm just getting the same shape now because I'm coming at that code out to go back to the way it was。

And these guys rotate。🎼No。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_721.png)

🎼Yeah。I didn't going to lose it I lost， but we got to the rotating guys。

 which were pretty cool and we found a bug that we can fix before we end the stream。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_723.png)

So in the level， let's go like random in。Is that， Let's go。This， this thing。

In a level or a specific play mode， the walls come closer with time passing by。That's really cool。

Oh man， the stream dropped。I think。It says zero kilobytes per second。

I think I lost my internet connection and I did。Well。切。That's a buner。

 but I was about to finish anyway。But。I'm going to note Evanvan's idea。

So I can play around with this next stream as well。Okay， I think we are back， no， we're not back。

They're not back。Okay， so yeah， I'm just going to finish the stream。 Thank you for watching。

 I hope you enjoyed and learned a lot。 We did a lot of cool stuff today。 If you w to follow me。

 just subscribe my YouTube channel where you can see all the crazy stuff shapes all the crazy stuff I'm doing。

 not only the the slide stream， but also the programming series。

 the tutorial series that I just started。😊。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_725.png)

That's more beginner friendly and its more stepback step approach， that's pretty cool。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_727.png)

You can download the game and the source code for free on H is dzd。h。o。



![](img/f50787a48fc38bca0b94a2fc47cf7c96_729.png)

Thanks for watching， I'll see you guys next time， See you then。

