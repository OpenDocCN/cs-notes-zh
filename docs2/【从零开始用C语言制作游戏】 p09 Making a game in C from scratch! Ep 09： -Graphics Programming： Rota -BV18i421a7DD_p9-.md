# 【从零开始用C语言制作游戏】 p09 Making a game in C from scratch! Ep 09： -Graphics Programming： Rota -BV18i421a7DD_p9-

Hello everybody， welcome to this new live stream where we are creating an entire game in C from scratch。

😊，Well， if we have been following along， you saw a lot of progress。

 actually in the last couple of episodes where we started focusing on the gameplay part。

 like improving the field， improving the animations， adding particle systems。

 all that sorts of crazy stuff， so you got to a pretty solid idea what the game plays is going to be for the game。

And in case you haven't been following along， you can go to my YouTube page and see all the past episodes so you can watch ever since from the first line of code that we typed all the way to where we got。

 which is pretty cool， let me show you the game， how it's running out。



![](img/886a749eaaa9f80910ebb04a9f92609c_1.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_2.png)

So we started with a small breakout clone， that's the base idea。And then we quickly started。

 you know， playing around with the game modes and the idea of the game is。我的。

Breakout was the only arcade game that you was supposed to have， so all other arcade games。

Would be breakout based games like this。 This one is P。嗯。Go pretty hectic。For a moment there， so。诶。

And we got space be as well。And we're going to do a lot more。 So that's the base game players。

 We're going to explore all sorts of other games。 And I was thinking about at least like Tes。

 junkie Kong and。😊，I don't know， we can think about all the sorts of crazy games that we can。

We can do right， but in order to do that， we are going to spend some time now making the engine a little bit more robust。

So oh， and if you want to follow along， you can download the game and its source code for free on HO so you can just come here Dan Z d dot h dot io and can download the game in the source code I just updated the page with。



![](img/886a749eaaa9f80910ebb04a9f92609c_4.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_5.png)

Nice gifts。Yeah。😊，So that's it， let's start programming。



![](img/886a749eaaa9f80910ebb04a9f92609c_7.png)

So this is what we're going to do， we're going to take a step back。

And focus a little bit more on the game engine so we can make it a little bit more robust to make some cooler things so。

A couple of things that we noted that we wanted to do。In terms of like aery。

 most rotated racks and bitmaps。So I think I'm going to pull that and possibly also going to do like sub pixelel accurate。

Arange。Maybe do that I don't even know if you're going to get to all that。Today。

But let's just start two minute。 So the basic idea is we have right now。The Windows platform layer。

 which creates like allocates a pixel buffer。Like this and the game has access to it through this render bufferstruct。

And we created a。Ranging system， really basic， that can do like all sorts of operations like we can draw rectangin pixels。

We can draw a transparent rectangle。There we added like doing a。Alert， and yeah， then we do like。

B some independent stuff。Like moving from pixels to world and world to pixels。And that's about it。

 Yeah， we also did like some helper functions as well as this hackggy thing to draw number。

 So what what to do now。😊，So you want to do like a draw， rotated。Righted。Correct。

 and right now all I'm going to do is copy from the rotated rack。

And then I'm going to start changing that a little bit。You know what， in fact， I'm going。

 So I'm also going to。Get the rotator rack in pixels。Just so everything is here， so this is like。でes。

We first transform， and then we rotate。Rotate reacts， draw rotate it。And we're going to take a point。

 half size。Canand be angle， and let's do like。In这。Okay， so that's the basic idea。

 And now let's just call this function so we can play around with it So drawer rotated。Rerrect。

 and we're going to pass。0。You know。Po position， let's do。3，3， for the size。

And let's animate as you like。Ngle机器。点过。考虑。あしたり。嗯。Stay floatat。Part A， kind of slow start。Okay。



![](img/886a749eaaa9f80910ebb04a9f92609c_9.png)

Now， we should have nothing， I mean， just a， yeah， just that rectangle。 Now。

 let's start playing around that。 We need a couple things， first。



![](img/886a749eaaa9f80910ebb04a9f92609c_11.png)

We are going to calculate where are the。The vertex。Of the rotateator react， so we need。



![](img/886a749eaaa9f80910ebb04a9f92609c_13.png)

To yeah， so our base points。A。Are these guys， right。But in fact， let's do them on。

Then we're going to convert that。这着啊。Then we can do like。up these guys。LetSee。

Then we're going to clean this up。Just， just get started。没有完。Galaxy。Conversion from。

We're going to do more elaborate things than just this cast。バら。One step at a time。O。Looking good。

Hey Marcus， nice to see you again。Today we're going to tackle some。You know。

 graphics programming and as's do some like rotator act bit nets， maybe sub pixel of accuracy stuff。

So first of all， we have to calculate， we have the points。

But now we have to rotate them so that's the basic idea in order to rotate we're going to think about as a matrix transformation。



![](img/886a749eaaa9f80910ebb04a9f92609c_15.png)

A rotation matrix is just basically the cosine。The sign that's for the x axes， and then a minus sign。

And then we have the cosine here。So we're going to multiply by this matrix， or we can just like do。



![](img/886a749eaaa9f80910ebb04a9f92609c_17.png)

呃。Yeah， we can do like individually the points as well。

But I think it'll be easier just to construct this matrix then we can like up to my later on if we feel it's necessary so in math。

Let's do a matrix。2 by two。对。😊，Let's do M2。And then。Let's say， of。2 by two。This guy advantage。

And then we can like specify。The orientation it there， so it's going to be in terms of memory order。

 that's you like01。And then，1，0。Can play wrong with that。So the thing is。啊。

You want to build a matrix like this。Math， yeah， well， we are in， we are in for some math today。

 Hopefully it's gonna not going to be like too crazy。😊，Let's。

 let's just create like an identity matrix for now。And。I don't think it's goingt work。Tform no。

 it did work。 I love math。 Okay， so maybe gonna help me today because。😊，Oh， you said， the good sense。

 right， because we're been doing some， some nice math today。 First of all， we're just going to。😊。

Multiply these vectors by this matrix。Let's do like here。A2。Like in line。Me too。好。2， V2。

I'm going to take a matrix。 I'm going to take a fracture。Okay。😊，So the result。Vor is gonna be。



![](img/886a749eaaa9f80910ebb04a9f92609c_19.png)

So that's just a quick reminder in terms of matrix multiplication， let's say this AB。史啲。

And then we have。That was pretty bad drawing。 and they don't have x and y。

 So the result is going to be like x。A X plus B， Y。Times C。X C plus。Plus， D， right， okay。



![](img/886a749eaaa9f80910ebb04a9f92609c_21.png)

Pretty easy stuff。 And I'm putting here in the size。Okay， so so it's v down x。Times， M dot。0，0。

 right。And they we're going to do plus。呃哎。とじゃなく。Do V dot y times and dot。0，1。Yes。

I think that's correct。 And they're going to do the same thing。But with one，1 and  one，0。Okay。😊。

And then I think its likely。And now we're going to create these vector。

 and maybe I can just like enline them and line them here。So。Would you like move。

I love the cross product。Well， since I haven't done much 3D stuff by hand。

 you know with no ranges in all libraries， I haven't got much to the cross product part。

But the idea is pretty cool， though， but just I don't have much practice implementing。

Operation that involved their cross product。Maybe you can tell us a little bit of story about it。

Some cases you program with a cross product that that can be pretty cool。

 So just the transform and the factor。So we should have the same thing。

 right that we're passing the identity matrix and convert from F32 to B2。I have to。哦。

Okay we're going to have to build this individually。I'm sorry， not individually as a whole factor。

 so you're going to have like。I do like the min。Which is x0。Right。Then I'm going to do。坏笑。Okay。😊。

have the max。Which is same thing， but plus。Okay， and now we're going to do。You mean that X。ExStex。By。

Next。Mean reefinition。嗯。😊，我的命里面。特别是。Oh yeah。たしてて。

![](img/886a749eaaa9f80910ebb04a9f92609c_23.png)

Max。Okay， now let's see if nothing changes。 Nothing should change。 Okay， nothing changes。

 Now let's start playing around with that， let's。

![](img/886a749eaaa9f80910ebb04a9f92609c_25.png)

I play around the matrix。Okay， so we should。Do the transform？Before。We applied these guys， in effect。

I may just apply these guys。In the matrix。嗯。Thinking about it。没A呀。

Like or maybe you can do like apply the scale by hand first。Yeah。

 we were eventually going to do everything on the matrix。But for now。

 let's just do one step at a time。 So this is going to be。Me and dot X。M的 fly。So， like。所以呢。Do every。



![](img/886a749eaaa9f80910ebb04a9f92609c_27.png)

So。Okay， now I have。Your rececttangle。Okay， so now we're set up to do some matrix training in fact。

 let's just take the time and do that。

![](img/886a749eaaa9f80910ebb04a9f92609c_29.png)

诶。嗯ん。I'm not sure if I can just multiply it。Like， here。And not do that there。That maybe。I'm just。

 I mean still doing the half science， yeah。And then I don't need to do this as well。



![](img/886a749eaaa9f80910ebb04a9f92609c_31.png)

Yeah， that's going to be way better。See， okay。

![](img/886a749eaaa9f80910ebb04a9f92609c_33.png)

So， yeah。That that's called， it's called like a。Or maybe a。As for scale。Okay， way better。

And then we can clean this up later on， I'm not sure we're going to do like。

Hmodgenous coordinates for the position because this enough just to add it later。

Although maybe we could be smarter about this edition。Yeah， let's do like。A。啊。Like。对。

And then I'm going to do this。可以。😊，H。😊，Yeah。😊，And then men's going to be aV2。Man， position to be。

 same thing。Okay。Nice cleanup。

![](img/886a749eaaa9f80910ebb04a9f92609c_35.png)

N不敢。Well， let's see if nothing changes。

![](img/886a749eaaa9f80910ebb04a9f92609c_37.png)

Okay， so we mess that up。Oh yeah， okay。Is enough， small tables。Okay。

 now let's play around with the angle。 First thing， we should transform the angle to， let's say。

 from degrees。To radiance。Okay， so we need that in math。Not sure what to put it maybe up here。Dr。 Ra。

 then we' also going to like this。

![](img/886a749eaaa9f80910ebb04a9f92609c_39.png)

Hi。That's he pie。

![](img/886a749eaaa9f80910ebb04a9f92609c_41.png)

Yeah， they don't give us。32 let's just did the whole one。Whole thing。



![](img/886a749eaaa9f80910ebb04a9f92609c_43.png)

Let's get more decimals。6 F， Okay， so this is going to take。Anle。It's going to return。

 I always get that wrong， Maybe Cl style can help me。In order to convert from degrees to radiance。

I have to， yeah， I have to divide。By，1，8。And multiply by pi。So maybe I can just it， yeah。

Is this correct？Let me see if we have many， let's check this out。If you have like。90 divided by 1，80。

Yeah。啊。Yeah， okay。Looks about right now。We have to make this matrix that's just scaling now。

 we should make this a rotation matrix as well。So。Like I said in the first。Part。

 I think I drew on top of that。 We have to calculate the cosine。And the same。And then。😊。

We have to build like the other matrix as well and then multiply them together。嗯。Yeah。

 this is like the。Okay， maybe。 oh， maybe we should do。Yeah。Let's， let's do the matrix multiplication。

 Then we can do like。Later on， we can optimize that as well。 So this is this kale。

Because I'm not sure。I'm pretty sure I can't。Well， I don't know。 let's check out let's do。

The transform matrix。Okay， so the idea is this is the sign。Well， I wasn't expecting this to work。

 Do we have the library。Maybe Windows uses the library。Yeah，没 sure。Okay。

 so let's just try the rotation， this should be like cosine。Should a minus sign。

This should be the sign。Let be the cosine。

![](img/886a749eaaa9f80910ebb04a9f92609c_45.png)

Well， not sure what's going to happen。Okay， we have a tiny guy and。



![](img/886a749eaaa9f80910ebb04a9f92609c_47.png)

Doesn't look right。Should really be time because we stopped doing the guy。啲 angle个系。

So let's just increase the size for now and not worry about the scale。Maybe are go to work come back。



![](img/886a749eaaa9f80910ebb04a9f92609c_49.png)

In a while， so we're not just the first kale。Okay， we have some movement。



![](img/886a749eaaa9f80910ebb04a9f92609c_51.png)

It's just。

![](img/886a749eaaa9f80910ebb04a9f92609c_53.png)

Oh， in fact。This shouldn't be working what should be working， though。

 is that that we should know the mean max that's work。 So we're going to do a draw。

Arrect on the points。Right， so you're going to do a man。呃。As well with let's just do it。Nice。

He have size。Okay，哎呦。😊，And we way too much ahead at that point， have to do slowly。

As you like one by one。And then you can do P half size。And then we're going to do like。I do orange。

Okay， so we're going to draw the min。The max。As well as the other points， right， which is。

Like the men， the max Xs with the men Y。And the other way around。



![](img/886a749eaaa9f80910ebb04a9f92609c_55.png)

So I want to see the points that we are conceiving， right？



![](img/886a749eaaa9f80910ebb04a9f92609c_57.png)

别来。Yeah， this has to be。

![](img/886a749eaaa9f80910ebb04a9f92609c_59.png)

Dr this guy。

![](img/886a749eaaa9f80910ebb04a9f92609c_61.png)

Okay， and I still see nothing， so let's go back to the good old scale。

And see if our points rendering guy is correct。So I don't see the points。Maybe边 I should make it。黄之。

I'm drawing that at the min。And the max， oh， but it's in pixels， this guy。

So maybe I don't want to do any。Yeah， I don't think I'm going to do the pixel transform。

At that point。Not sure， since this guy's just a。A deepbuging guy。I'm just going to like。I thebumin。

And do we devbu Max？

![](img/886a749eaaa9f80910ebb04a9f92609c_63.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_64.png)

O。But， let's see。

![](img/886a749eaaa9f80910ebb04a9f92609c_66.png)

啊。

![](img/886a749eaaa9f80910ebb04a9f92609c_68.png)

Let's go back into。

![](img/886a749eaaa9f80910ebb04a9f92609c_70.png)

This。😊。

![](img/886a749eaaa9f80910ebb04a9f92609c_72.png)

Okay， this is a 30 by 30 rectangle。But these guys are wrong。

 I think I'm going to debug just to make sure。

![](img/886a749eaaa9f80910ebb04a9f92609c_74.png)

We are getting what we expect at this point before we actually do the signine and the cosine。Okay。

 so。We get， oh， probably have to turn off。

![](img/886a749eaaa9f80910ebb04a9f92609c_76.png)

Optimized flag。Otherwise， we're only have instructions all over the place。嗯。😊。

So only when we are optimized， we have the library。TheCRT。That's certainly wrong。Maybe I don't know。

 That's a those thing， but we are going to be like。Can include。S TD。

 I don't know where it's called sign defined CR T。

![](img/886a749eaaa9f80910ebb04a9f92609c_78.png)

嗯。S T。Co F。someone shows me。Where it is in which include file。



![](img/886a749eaaa9f80910ebb04a9f92609c_80.png)

Math dot。 yeah， Mor。 Yeah， just math that H， okay。Yeah， at that age， I don't know。

 my my brain was pretty dead at this point， okay so。



![](img/886a749eaaa9f80910ebb04a9f92609c_82.png)

Let's go back to button。啊。Okay， so we have。I'm sorryrry。Actually totally threw you there， Yeah。

 thanks。So P0， half size is 30 angle doesn't matter for now and color， okay。I there multiplier。

The size， okay， the angle。So we calculate the co signine and the sign。And look， right。

And then we do the matrix now。We are creating。Yeah， let's see。 We're， we're multiplying。

Let's see the minimum， the minimum is like minus。204。And this guys is plus 204。Pixels。

And then we offset that by the century。Yeah， I think that's right。Think that's right。



![](img/886a749eaaa9f80910ebb04a9f92609c_84.png)

Yeah， but we're not getting the correct display there because we shouldn't really。Do。

This at this point， we first should build like the main and the max。Without transforming。

And then we should copy those， which are like。In。And at this point， we are at still at unit space。

 but we're just calculating it。The correct points。So we do。该。ですか。



![](img/886a749eaaa9f80910ebb04a9f92609c_86.png)

Okay， nice。So this is what we expected now this is pretty huge， right？



![](img/886a749eaaa9f80910ebb04a9f92609c_88.png)

I had to do like one。So we have the points now if we we go back and do our。And do our s cosine here。

I think I'm going to do two mates。To yeah， let's do like。Scale matrix and a location matrix。

 then we can optimize that later on。 But then this guy should really be multiplied by the rotation。你。

And yeah， and then。Reco to show the points。And then at this point， we do this scale。That这个。

Decoration of scale。 We already have scale。 Let's like scale or transform。Oh。

 we actually have a global scale。Rotation。Roate。Then that's for this coine。sign。Mus3。



![](img/886a749eaaa9f80910ebb04a9f92609c_90.png)

ok。Now let's see what we have。啊。😮，It'sStill not working。



![](img/886a749eaaa9f80910ebb04a9f92609c_92.png)

Okay， now let's go back and debug Now that it's somewhat nicely structured。 So our angle。

Is pretty small。

![](img/886a749eaaa9f80910ebb04a9f92609c_94.png)

That's just pass like a known angle。Let's pass， like 45。



![](img/886a749eaaa9f80910ebb04a9f92609c_96.png)

Let's firstly see what we have。Yeah。Calculate。So。45。Is 0。7， I don't know。



![](img/886a749eaaa9f80910ebb04a9f92609c_98.png)

Is do like 45。这个意思。In ready。呃。😊。

![](img/886a749eaaa9f80910ebb04a9f92609c_100.png)

ok。So this a lot， it's not correct。

![](img/886a749eaaa9f80910ebb04a9f92609c_102.png)

45。

![](img/886a749eaaa9f80910ebb04a9f92609c_104.png)

Oh， okay， no， this is correct， I don't they're wrong guy。And the cosine and signine。

 they look correct。And we're building the rotation matrix。

 maybe we've got these guys wrong in terms of position。Okay， so we built the rotation matrix。Okay。

 then we multiply， we create the minimal， which is。P minus half size。

 then we multiply that by the rotation matrix。And let's see if this is correct。So。Yeah， see。

 it's not correct in terms of the memory order。No， it is correct。 Parly， it is correct。No。



![](img/886a749eaaa9f80910ebb04a9f92609c_106.png)

I'm getting all confused now。This。Our matrix。Looks like this。



![](img/886a749eaaa9f80910ebb04a9f92609c_108.png)

Okay。Now， at this point， when we do the multiplication， we are doing。The the first guy。

 which is like the sign。And then this guy， which is the cosine by the x， right？

Let me draw that again。So this is s sorry， this is cosine， this is sine。This is minus sign。

And this is cosine。So I suppose we were correct， right， we're doing X。0，1， like 0，0。召云。Yeah。

 zero1 should be minus。

![](img/886a749eaaa9f80910ebb04a9f92609c_110.png)

Your regret。

![](img/886a749eaaa9f80910ebb04a9f92609c_112.png)

But。Let's see。The result， men。Yeah， let's do the the the next。 Let's see。 So the star matrix。

And this is our factory。We're doing 30 times this guy。Oh， now， okay。Plus，30。Times this guy。



![](img/886a749eaaa9f80910ebb04a9f92609c_114.png)

Actually， what do we expect？We expect this。

![](img/886a749eaaa9f80910ebb04a9f92609c_116.png)

So we do expect some of them to be zero。In the。Yeah，0。-42。And this one。Is 0，42。So you know what。

 that kind of looks correct。To be honest。So。And this guy's going to be zero。-42。See， this is wrong。



![](img/886a749eaaa9f80910ebb04a9f92609c_118.png)

This is wrong you。Our drawing thing， so our four points。

Are actually man your nuts making a game from scratch。 Is it hard someday using it or something else？

Good night。 Good night， man。 Thanks for dropping by。 I have used engines in the past。

 I have used unity for a while， and then I shipped a game using on Rio for the PS4 and the PC。😊。

I spent like three and a half years working on that game。

 so I did like I have been using on real for five years。And。

I know kind of got tired of it and started doing some engine programming you know we're doing。

Again game from scratch on a live stream， that's the thing， that's the hardest part。

Because I have to do like these structured things and there's a little bit pressure also。



![](img/886a749eaaa9f80910ebb04a9f92609c_120.png)

But we are coming along like you foresee the game， just ignore the。



![](img/886a749eaaa9f80910ebb04a9f92609c_122.png)

Those other points， we we have a pretty cool breakout kind of game，'s let's get the power up levels。

From scratch， and we I recorded everything on stream so you can watch like from the very first episode。

All the way to you know， what we have now and hopefully the game's release of sorts， yeah。



![](img/886a749eaaa9f80910ebb04a9f92609c_124.png)

I'll kind of clicked away， okay。

![](img/886a749eaaa9f80910ebb04a9f92609c_126.png)

So。I suppose this is wrong， let's go back to the grid。This is wrong。

 So if we have this as the mean and this is the max。The other points are like。This one， let's say。

 let's say this is like。0-40， right that we got。 And this like 0，40。This guy's supposed to be 40。

0 or minus-40。 these guys supposed be40。是呀。It's the other way around this has motivated me for going back。

 thanks。哼。😊，That's awesome man， that's like the goal man of these of these streams。 I mean。

 you guys should also pick up a few things like learning some new things。

 but also you know just start doing I was motivated by people doing streams as well so。😊。

That's awesome， nice to hear you。Okay， so this is the part we got wrong。 So we should also。

Get these guys inverted， right， We're going to have two。Think about that a little bit more。

 let's just see a more correct result。

![](img/886a749eaaa9f80910ebb04a9f92609c_128.png)

Have you reached the screen again， yeah， absolutely。



![](img/886a749eaaa9f80910ebb04a9f92609c_130.png)

Absolutely， man。 streaming is really cool。 It's a different kind of challenge， right。

 because we do like programming for reals during the day and。😊。



![](img/886a749eaaa9f80910ebb04a9f92609c_132.png)

Yeah time just cool to see。 And I'd love to see that like some math related stuff clone style since you say that math was thing。

 Maybe I could learn a thing or two on your earth stream as well。 So we are correct。

 Let's just speed this up like a lot。😊。

![](img/886a749eaaa9f80910ebb04a9f92609c_134.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_135.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_136.png)

times five。Okay， so we are correct。 Let's speed up even more。 and let's just decrease the size。



![](img/886a749eaaa9f80910ebb04a9f92609c_138.png)

Just got learning。 I just love learning。 Yeah， and that's what you gotta do。 man， I mean。

 you don't have to be great at it。 If you love learning， you're gonna be great at it eventually， so。

😊。

![](img/886a749eaaa9f80910ebb04a9f92609c_140.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_141.png)

I know， just like game engine programming， right， This is also learning experience for me。 I mean。

 I did like the commercial games using engines， but without engines。

 this like the biggest game I'm making This is a breakout guy， so。😊，Yeah。😊。

All you have to do is keep learning。Okay。Also， the points they rotate， what？Oh yeah， the points， man。

 that's what we' were doing， so we got the points。And that's like the the dates of what we need it。

 Now， all I have to do now is to check。

![](img/886a749eaaa9f80910ebb04a9f92609c_143.png)

诶。These these guys here。Weather they。Whether they collide or not， and in fact。

 I should just do like draw reacting pixels so we can go back to our the single matrix guide。



![](img/886a749eaaa9f80910ebb04a9f92609c_145.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_146.png)

So let's just review what we got here。Can start to get confusing。 So we have。

 we receive all this info right， Then we do a couple matrix we do a scale matrix and this is like the。

This is really the。This is really the world。To。Pixels scale or transform。

Then we do a rotation matrix， so this guy'm going to do it like down。Okay， so first all。

 we do our local transform our object transform， let's call it that and calculate the min and the max。

 okay and then we change these guys to pixel coordinates。Like this。Change to pixels。

 And these are in pixels。 So then we clamp the pixels， and then we reduce do the thing。

 The basic idea that we should do now。

![](img/886a749eaaa9f80910ebb04a9f92609c_148.png)

Is if we。We should do like a collision detection for the pixels。

 which are like let's just try to draw this in the guy here， okay。

 so let's say this pixel is a point。Here， right， all we need to do is see if if it's inside this rectangle or not。

 we have done collision in the past。

![](img/886a749eaaa9f80910ebb04a9f92609c_150.png)

We've done a let's see co we yeah， we did this is colliding thing。

 which was the AABB versus the AABB。 So the question was， if we have a point here。

 is this guy colliding and just test。

![](img/886a749eaaa9f80910ebb04a9f92609c_152.png)

That's it if。It was greater than the mint and smart than the max for all the two as。O， O B B。

 we're going to do O， B， B， right， which is a。Yeah， oriented baing box。

And I don't know if there's thing such as OobBB。Maybe object。 No， yeah， I think it's just O B， B。

A into the boing box。That's what we're going to do。



![](img/886a749eaaa9f80910ebb04a9f92609c_154.png)

And。Yeah， it's going to return a blue and we're going to see like this。

 we're going to do like OBB point。Versus OEB， and I should really do like AABB versus AabBB。Yeah。

 I think we started out as Dad we went back。Okay， so point versus O， what do we have。

 you have a point。But the thing is， this is like a pixelel coordinate。So this is really like a point。

Now this is really good， I'm not sure if we should do this like it floats。Or not。

I think I think this guy， this has to be working away。 So let's call that P。For the OBB。

Wech should really like bass erect like a。Let's call like erect。对。And they' wreck。Should be。2。

And there actually be。A you are right just OBB， for some reason I had remembered that Yeah， OBB。

 it's going to be cool So we need a rack a rack is going to be a， let's say point0。Point1，2。

 maybe we could do like an array。It's colliding。して。近らで？Okay， so for now， we have a right。And the。

This guy。Let's see where do we create Yeah， I've had the max min。Let's do like here。Right。

We do have some cleaning out of my head。Should be like me correct。Max。们。And then we do this guy。

Just like。啊。Result。Resolved dot P0 is the man。And then we do。They would do。let say。Yeah， men。Do why。

Max do。X。I think this is。Sの。Later on， this the max。Okay， so。We have a wreck。This guy。

 I can just do like。Right。いすよ。1，2，3。啲。哦。嗯。We were actually doing that with the D man， guy， so。Yeah。

 that's do。Like this。This is like really stupid just for debu purposes。



![](img/886a749eaaa9f80910ebb04a9f92609c_156.png)

Okay， let's see if you are in the same shape， we are， oh， actually we are not。



![](img/886a749eaaa9f80910ebb04a9f92609c_158.png)

You only see three points。One， two， three， so maybe this is wrong。Yeah， this is wrong。Okay。😊。

Let's see。 Okay， We are back to normal。 Now we have direct， and we can now work on our。

Rect versus P versus right。回避。So the basic idea is。



![](img/886a749eaaa9f80910ebb04a9f92609c_160.png)

Let's say we have these points。If I subtract this these guys， I have an axis like this。

 same thing for this other guy。

![](img/886a749eaaa9f80910ebb04a9f92609c_162.png)

So I can find out the x， the x is just by doing this。But we also， we do have the axes。

They are these guys。So maybe I should not make that a general guy。

In a what I'm not going to do like the point I'm going to do。ALittle bit slower。

 so I'm gonna have like the X axises。And the X axis is gonna be。Cos。

And're going to have the line axis。Which is minus- sign plussine。Okay。😊，Now。啊。Yeah， well。

 let's just keep the matrix for now。I don't know if's going to keep that later on。Is the sign cosine。

 Yes， we are using the math scanner library for that。So。This is the first library。

 we were probably going to use like another one for image but。Yeah。

 I don't see like the value writing our own technicalical science stuff。I don't know。But。But yes。

 it is Okay， so we find the cosine and the signine。



![](img/886a749eaaa9f80910ebb04a9f92609c_164.png)

And then we build， let's just see if we have the same thing。We do， okay。



![](img/886a749eaaa9f80910ebb04a9f92609c_166.png)

So now since we have the axes。We can do the rotation， little bit。Easier， so we have the axes。And。

Let's first of all， let's go back and do like。For every every pixel， right， as do like。

They're buffer for Han。And it does enjoy。And now this should be like the collision test， right。

 Like if the P。Like is colliding。Right。This should be the collision test。

 So it's going to pretty much like。It' going pretty much like。If the P。Same thing here， right。

 the Px。Is greater than。The mint， we should call it that min max， I think。Yeah。

 that's you like we do have newex。 so men。Dot X， I think we got a way ahead of ourselves doing all those right things。

 kind of gotta excited， okay。😊，So if the P dot X is larger than the min P。

And it's smaller than if you really do like larger。And it's smaller than the max。

And the y is larger or equal。This guy is smaller。This guy。Okay。This is the basic thing we want to do。

 but we are probably going to have some conflict in units。



![](img/886a749eaaa9f80910ebb04a9f92609c_168.png)

And I'm going to have to solve them。Let's see what we have。



![](img/886a749eaaa9f80910ebb04a9f92609c_170.png)

Yeahve seen seen nothing。It's probably unit thing， so we are here in pixels。Correct。

And we should really focus on these guys。Right， the mini max that we calculated based on these castle。

 This one is the I。X 0。And this ones the eye。One。And the minimum is， I。Heck O y 0。



![](img/886a749eaaa9f80910ebb04a9f92609c_172.png)

谢谢は。

![](img/886a749eaaa9f80910ebb04a9f92609c_174.png)

Is this not correct？Well， if you take this out， we should have like。The whole screen right。



![](img/886a749eaaa9f80910ebb04a9f92609c_176.png)

I see。And we do， and then we crash。But we do have the whole screen right。Yeah， okay。



![](img/886a749eaaa9f80910ebb04a9f92609c_178.png)

笑了。Oh。We're testing P。x， that's really stupid。You should test like X。Which is like the big important。



![](img/886a749eaaa9f80910ebb04a9f92609c_180.png)

Yeah。So we're doing that in pixels for now， and we have the same thing。



![](img/886a749eaaa9f80910ebb04a9f92609c_182.png)

Now。You off doing like。

![](img/886a749eaaa9f80910ebb04a9f92609c_184.png)

This calculation like this。In in fact， I'm going to do like。If x minus the mean。

It's greater than zero。And if the x minus the this guy。It's less than 0。

Just organizing the code a little bit。For us to make the。The jump。To our rotated react。

 reach the whole point。So let's just check out the code。And we broke it。Yeah。Okay。

So this is the thing that we want to change now why are we doing this， let's let's draw。



![](img/886a749eaaa9f80910ebb04a9f92609c_186.png)

Right now， we have a。Let's say a pixel， let's say we have like 15，7 in terms of pixel， right？

And we want to draw， like， from a。10 let's say 10。Five all the way to 20。10。好。It like。10。10。20。5，20。

这。Okay， so what we are doing is just like subtracting this guy。From the min， which is five。

And see if it's greater than zero。 So if it's on this side and then we do same thing。For this guy。

But we can do， we can do it like this。Because we know this axisxes。Is。Aligned。Correct。😊。

So we can just pretty much test like this If our axes not aligned to this guy， like if we have like。

I me put in a different color if we have like this。What do you really want to test？

is the dot product of this guy？With the axes。Which goes from like zero to like one here and more than one here。

And the last one here， if it's positive means that it's on this side and in this case。

 if it's positive， it's this side， then we do like the whole thing。If you do like for the four。Guys。

 we pretty much make sure that we are enclosed。On this rotation。



![](img/886a749eaaa9f80910ebb04a9f92609c_188.png)

Okay， so that's the basic plan we're going to do。So this is what we have to change。

 and I'm so not sure we should do that in pixels。But， w。



![](img/886a749eaaa9f80910ebb04a9f92609c_190.png)

If this was I mean。And I don't think we do。 I don't think we do。 So we are going to do like。



![](img/886a749eaaa9f80910ebb04a9f92609c_192.png)

Dix so he。And I'm just going to run。Yeah。Now this is going to be like x。And why。So we have a TsLP。

I can just take out that one。Weally annoying。啊。Yeah。I know it's not。

Initnitiallyial I am in the process。U， okay。So we've had the pixel P and now all we have to do。

Is calculate。How much it is on each axis。Let's say呀。Let's call that。Projection zero， correct？

And the projections， let's say like projection。

![](img/886a749eaaa9f80910ebb04a9f92609c_194.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_195.png)

It's called project2。So the projection right now is just this guy。We're just like pixel soap。P到X。

Minus this guy and。And I don't think I'm going to do that。On a pixel now。

So this is going to be the minX。ok。So。嗯。This is。So this is the same thing， right？Can go back。

 I think I'm going to do a like step by step again。Projection 0。Rejection1。Projection 2。Projection。

Okay， so the two is going to be this guy。Minus the。This is meanwhile。And max。



![](img/886a749eaaa9f80910ebb04a9f92609c_197.png)

Let' see if。Still we have the same result。Is for codeder free there's a free version。

 which is the one I am using。 You can go to each。

![](img/886a749eaaa9f80910ebb04a9f92609c_199.png)

I think。Yeah， for a coder， we can go to each dialo。



![](img/886a749eaaa9f80910ebb04a9f92609c_201.png)

And search for code there， see。Yeah。And you can download the free version here。

And it's pretty complete all there's lacking is the customization layer。

 so want if you don't want to do like and you can do like everything you want like you can change the whole editor。

 but if you don't want that you can download the free version， but the paid version is like $12。

It is similar to Vom more in， it's more like EX。But I think he's more intuitive than he makes a lot more intuitive。



![](img/886a749eaaa9f80910ebb04a9f92609c_203.png)

But there are a lot of customizations to make it look pretty much like them in a lot of different ways。

 or even a。

![](img/886a749eaaa9f80910ebb04a9f92609c_205.png)

Eax， yeah。The next I also thought it was pretty bad to me when I used it for a while。

 I didn't like it。Okay。But。Yeah， so fourcode is not like Eax。



![](img/886a749eaaa9f80910ebb04a9f92609c_207.png)

But I don't know， I think it's more like， okay， so I don't remember if you got it work we got so it's the same thing now。



![](img/886a749eaaa9f80910ebb04a9f92609c_209.png)

So what I'm going to do is I'm going to change to test everything if everything is greater than。

 because remember， the idea is to use the dot product。



![](img/886a749eaaa9f80910ebb04a9f92609c_211.png)

For everybody， I'm going to test if that's greater than what so really step by step。



![](img/886a749eaaa9f80910ebb04a9f92609c_213.png)

So if it's greater or equal。0。But now we have to change the sign of these guys， right？So。

 it's basically。啊。like this。Do you play drums， I do play drums。You can see。I have。Pretty cool。

 I bought a acoustic drum。 But since I live in an apartment， I can't play acoustic drums。

 So then I converted that drums to an electronic one with a muted， muted， I't know， mesh heads。😊。

And we're triggers。So that's pretty cool。Qu yeah， there's the high hat， the high hat is a let me see。

😊，The high hat is the electronic pad。 You Can also see one here。And it works pretty nicely。

And it was pretty cheap to convert instead of by buying the best electronic film cell I could know。

Because those can get pretty expensive， so I did the conversion and。



![](img/886a749eaaa9f80910ebb04a9f92609c_215.png)

I'm pretty happy with the results。

![](img/886a749eaaa9f80910ebb04a9f92609c_217.png)

Okay， so yeah， same thing now we're pretty much ready to change what we need to change and what we need to change is this guy。

So instead of just subtracting。The big so。

![](img/886a749eaaa9f80910ebb04a9f92609c_219.png)

To this guy。We just like。Let me go back。Yeah。So stop just of attracting the pixelel？

Subtract like 15 to dis guying get five。He set I doing that。We are going to get the thatt product。

Of 15 projected on this guy。

![](img/886a749eaaa9f80910ebb04a9f92609c_221.png)

ok。😊。

![](img/886a749eaaa9f80910ebb04a9f92609c_223.png)

And this guy。Well， we know what this guy is。 This guy is just like 0。Is that correct？Yeah。

 this guy is this guy minus this guy。So， yeah。

![](img/886a749eaaa9f80910ebb04a9f92609c_225.png)

So we're going to do the。Do we have the dot product， I don't think we do。Yeah， we don't。

So infer vector， I' still like。いちゃ。2。Maybe I'm thinking， doesn't metal H have dot product？

Ticking up open jail， I'm not sure， but。I don't like like using this for everything。 So just for。

Sign up。And cosine F。So yeah， okay， so someone says no， so he doesn't have， but even if it did。

These kind of math operations is nice to write by ourselves just so we know what actually goes on because that's pretty important to learn and one of the goals of this project is just to learn。

It really does make sense to at least know this kind of stuff and like how to use it and how to。

 you mean the matrix multiplication。Yeah。Yeah， we haven't written a matrix versus matrix。

 we did like a matrix versus factory。Okay。So when I'm going to return here。Is a dot X。Times B dot X。

Plus a dot I times v dot。That's it now。This guy is going to be the dot product。

And we have to make sure this is correct of the。Pixel。



![](img/886a749eaaa9f80910ebb04a9f92609c_227.png)

好 pixelel。With direct。

![](img/886a749eaaa9f80910ebb04a9f92609c_229.png)

52， rec one and rec。0。So。This is the Ph idea。 We have this guy minus this guy。

 which gives us this guy。

![](img/886a749eaaa9f80910ebb04a9f92609c_231.png)

And then we project this guy onto this guy。And that's going to tell us if we are on， let's say。

 this side or this side。

![](img/886a749eaaa9f80910ebb04a9f92609c_233.png)

Okay， illegal forstruct。 What's illegal for structure。 Yeah， correct up。哦。



![](img/886a749eaaa9f80910ebb04a9f92609c_235.png)

Now I'm going to step this before even we do for the other ones， just make sure so pixelixO P。

 you were testing。What makes our destiny very first pixelel。Okay。And that we get we have zero。

 so we're probably wrong， now let's do that again。Okay， so a， so。This is the first point。B。

This is the second point， I' see。Yes， this kind of looks correct。Okay， now that's the dot product。

 so we have10。And we have。Okay， so that wasn't correct， we have minus。



![](img/886a749eaaa9f80910ebb04a9f92609c_237.png)

I was expecting zero。Oh， because we are rotated， but I'm not going to pass rotation yet。

Just so it's simple。

![](img/886a749eaaa9f80910ebb04a9f92609c_239.png)

Okay， again， let's， let's do it。 Okay， so now we have 0，0， and we have。I suppose we were just wrong。

Arrect。Let's say P0 is this one。Yeah， our's pretty wrong。



![](img/886a749eaaa9f80910ebb04a9f92609c_241.png)

Let's see。We have men。And we have Max。This should be like Min X。



![](img/886a749eaaa9f80910ebb04a9f92609c_243.png)

And Max what， I think， yeah， I don't know。I don't know why we did that。This should be a min X， max。

 y。The max X。

![](img/886a749eaaa9f80910ebb04a9f92609c_245.png)

Today is like a weird day， but it's a math day。 So it's probably why it's a weird day， Okay， so。Okay。

 these look better。Okay， let's see。 Okay， this is correct， I think。So we should really have a。

Could you explain why you're using two IDs to use， yes。

 I'm using a visual Studio just for the debudgging and I'm using visual。

 I'm using forcodeder for text editing。

![](img/886a749eaaa9f80910ebb04a9f92609c_247.png)

So yeah。And I compile in here， running with AutoM。

![](img/886a749eaaa9f80910ebb04a9f92609c_249.png)

Which we set up that on the first day， so yeah， that's why we're using to software。啊。

So the dot product turns out to be zero。I don't think that's entirely correct。



![](img/886a749eaaa9f80910ebb04a9f92609c_251.png)

Like。

![](img/886a749eaaa9f80910ebb04a9f92609c_253.png)

Oh， because we were offset it by the by the men。So this really should be。This really should be。

The pixelix P plus。The min， the mean is like the。

![](img/886a749eaaa9f80910ebb04a9f92609c_255.png)

The origin， let's put it that way since we are。

![](img/886a749eaaa9f80910ebb04a9f92609c_257.png)

Using that as origin， so。Yeah， we are going to have to like do a another。This later on。



![](img/886a749eaaa9f80910ebb04a9f92609c_259.png)

Is it convenient。 I think it's pretty convenient。 I mean， I can alter pretty quickly。😊。



![](img/886a749eaaa9f80910ebb04a9f92609c_261.png)

And I think this is a great tax editor， and I think its a pretty good debugger， so。



![](img/886a749eaaa9f80910ebb04a9f92609c_263.png)

I guess I get the best of both people because I don't like this text editorer at all。

 I don't like it。 So I think I get the best of both worlds doing this。😊，And it's not inconvenient。

 I'd say。Okay， so the pixel P。Yeah， maybe this is a little bit better。Let's see， so。We are huge。

This is not correct。I expect to be hugely negative。

So let's see the values we got to understand the program。So， you're subtracting。500。

 which is the minimum P。

![](img/886a749eaaa9f80910ebb04a9f92609c_265.png)

Yeah， we should actually be doing the other way around this guy， man。This is true。

 I think that VS is one of the greatest des it does， especially when you compare it to like。



![](img/886a749eaaa9f80910ebb04a9f92609c_267.png)

Linux with like command line debugging， command on， guys。Really， yeah。

 so I really like the debugging here。Okay， so。Let do we have more time， we have a。Which is。



![](img/886a749eaaa9f80910ebb04a9f92609c_269.png)

This point， like， let me draw。It's this point。

![](img/886a749eaaa9f80910ebb04a9f92609c_271.png)

Oh， but you are right because we were subtracting。Yeah， we wanted this axes。



![](img/886a749eaaa9f80910ebb04a9f92609c_273.png)

Plus suppose we were correct。

![](img/886a749eaaa9f80910ebb04a9f92609c_275.png)

And B。Yeah， so this is not going to be right， we were right。This guy is negative。

 It should really be positive。 We are respecting this guy， okay。



![](img/886a749eaaa9f80910ebb04a9f92609c_277.png)

Again， let's do it one more time。 The problem is in our dot product， really。



![](img/886a749eaaa9f80910ebb04a9f92609c_279.png)

So。

![](img/886a749eaaa9f80910ebb04a9f92609c_281.png)

We are dot， actually， I think the problem is。No， the problem is really this guy， yeah， the pixel P。嗯。

Yeah。This guy。This pixel is like up here。

![](img/886a749eaaa9f80910ebb04a9f92609c_283.png)

嗯。These guys aren't in pixel。

![](img/886a749eaaa9f80910ebb04a9f92609c_285.png)

So， let's say， this guy returns。A factor like。0。400。And we want to know。

Whether or not we are on this side。And to know that。We are projecting。This pixel onto this guy。嗯。😊，Y。

Let's understand that one more time。

![](img/886a749eaaa9f80910ebb04a9f92609c_287.png)

We were working pretty much until we started doing the dot project step。

 so let me take this guy back。And go back to the。

![](img/886a749eaaa9f80910ebb04a9f92609c_289.png)

So， we are。We got to work， okay。

![](img/886a749eaaa9f80910ebb04a9f92609c_291.png)

But we want to do that with a dot product。

![](img/886a749eaaa9f80910ebb04a9f92609c_293.png)

So the basic idea is。Let'd say we have。A pixel that we want to test。And we have these points。Correct。

Yeah。😊，This vector。Oh， maybe I should I should offset that by the minimum guy。



![](img/886a749eaaa9f80910ebb04a9f92609c_295.png)

Or just subtract， Yeah， I think the problem was this go back once again。

I think the problem was this guy I should really subtract。



![](img/886a749eaaa9f80910ebb04a9f92609c_297.png)

Because。Yeah。

![](img/886a749eaaa9f80910ebb04a9f92609c_299.png)

I don't want to push him further， I want to pull him back。By this amount， so I'm going to subtract。



![](img/886a749eaaa9f80910ebb04a9f92609c_301.png)

，The pixelixel P， which is this。

![](img/886a749eaaa9f80910ebb04a9f92609c_303.png)

So little。So let' see。What do we have？啊B。Okay， so is this axis as we expected。



![](img/886a749eaaa9f80910ebb04a9f92609c_305.png)

P is like 0，0。 We expect that。To be on our left， x y。 considering this is still x is the aligned。

 Yes， now we have minus this guy。

![](img/886a749eaaa9f80910ebb04a9f92609c_307.png)

Okay， I think you're getting somewhere。

![](img/886a749eaaa9f80910ebb04a9f92609c_309.png)

So we're going to do the same thing like this is the dot yeah。

And the same thing for the other projections。 So we do。



![](img/886a749eaaa9f80910ebb04a9f92609c_311.png)

This guy， which makes sure that we are on this size， this site， then we do the other guy。

 which is this one。

![](img/886a749eaaa9f80910ebb04a9f92609c_313.png)

That makes sure we are on this side。But it is the other way around， right？We were doing。

 we were doing pixel minus mien。So， this is actually。The other way around。But negated。

Is that correct。嗯。😊，Wellll let me just tap in and see。



![](img/886a749eaaa9f80910ebb04a9f92609c_315.png)

What we have at the other guy， so。First one。We get minus a huge number， okay？The second one。

We expect to get positive， huge number。And we do。So I think we are again somewhere。



![](img/886a749eaaa9f80910ebb04a9f92609c_317.png)

And。

![](img/886a749eaaa9f80910ebb04a9f92609c_319.png)

Now we do the same thing for the Y。Which going to be 0。



![](img/886a749eaaa9f80910ebb04a9f92609c_321.png)

And 2。Okay。😊，And now， let's see。

![](img/886a749eaaa9f80910ebb04a9f92609c_323.png)

What do we have。We expect。Let's see what we expect。We expect。Negative huge number。

 positive huge huge number， and those are the two that we tested。Here we expect。



![](img/886a749eaaa9f80910ebb04a9f92609c_325.png)

We are testing。 let me go back to this image。 We are testing now。This aes。Right。

So when we project against。So we expect， again， positive， huge number and positive。



![](img/886a749eaaa9f80910ebb04a9f92609c_327.png)

Small， negative， huge number。We' got the other way around。But yeah， I think my。

 I think I was just confused。 No， I wasn't just confused。 this is really wrong， okay。嗯。Okay。

Let's see。Why do have the statement in line V2， how do you understand this？



![](img/886a749eaaa9f80910ebb04a9f92609c_329.png)

啊。I don't know。In line， I usually put like either internal。

 which means it static because this is a unity build。So I put internal in everything。

 so if could go to like windows。Internal。go to game。Internal， internal， internal， yeah。

 so it's pretty much internal and the return type。So that's the basic thing and here。

 instead of internal going in line。And the return type。In blind view， too。

I'mNot sure it's pretty easy to understand anything。



![](img/886a749eaaa9f80910ebb04a9f92609c_331.png)

Okay， let's go back to our debugging。These two guys look correct， I think， oh。

 I should really start from scratch just to make sure。Then we have like the zero zero guy。

 which should not be included， well it's not going to be included because this was negative。

But let's just check out this guy， So we are passing。700，400。And 500。



![](img/886a749eaaa9f80910ebb04a9f92609c_333.png)

Yeah， so this is wrong。Maybe， maybe I should， yeah， I should do it like this。No， you know what。

 This is better。 So we are doing like a counterclockwise definition for direct。Couner。Clockwise。

Whats。Thanks， no problem， man。Okay。So if we are doing clockwise points。

Let us go back to the renderry。We should not do like two， one， we should do like three， one。3，0。



![](img/886a749eaaa9f80910ebb04a9f92609c_335.png)

Okay， so we got。This vector， we were， we were getting this vector。



![](img/886a749eaaa9f80910ebb04a9f92609c_337.png)

Okay， let's just see you one more time。Okay， we are still wrong， but。We are very， very slow now。



![](img/886a749eaaa9f80910ebb04a9f92609c_339.png)

Which is not unexpected。Because we're testing like everyone。嗯。



![](img/886a749eaaa9f80910ebb04a9f92609c_341.png)

But we are going to， yeah， we're going to fix that later， but now let's debug that one more time。あし？

Okay， so we have。700。And 256， okay， then we have。500 and27。



![](img/886a749eaaa9f80910ebb04a9f92609c_343.png)

This is still not correct。It's either。Oh， okay， so I was expecting to。To the max。That's funny。

 That's what we had last time。

![](img/886a749eaaa9f80910ebb04a9f92609c_345.png)

So this， this guy， which is like， let's just check out the men。

It's minus and minus so the min is this guy。

![](img/886a749eaaa9f80910ebb04a9f92609c_347.png)

How do the men。For the zero position。

![](img/886a749eaaa9f80910ebb04a9f92609c_349.png)

And then we do the min， oh okay， we're doing it like this。So。



![](img/886a749eaaa9f80910ebb04a9f92609c_351.png)

So that's okay， again， we do it like the min， and then we do the max。



![](img/886a749eaaa9f80910ebb04a9f92609c_353.png)

And then min， then we do the max， and then the min and the max。Okay。And this guy should really be。

The men。

![](img/886a749eaaa9f80910ebb04a9f92609c_355.png)

And this guy。Let see。I see what we have。Okay。Let's do go one more time。Yeah。

 math stuff if you don't get like 100%。Turns out to be really panicky， let's just see。Yeah。

 this is correct， I think， so our sub is 500， 400。500，200。Yeah。It about right。

 So we should have like a。We should have a positive。Dctor。On why。Is that correct， Let's see。

 We do have a positive background on mine。Yeah。😊，So， we have。Have。Okay。

But I don't think we hit this at all， do we no we don't。嗯。Let's just cheat。



![](img/886a749eaaa9f80910ebb04a9f92609c_357.png)

And go through the。The guys we know。Should。Let's just start with the guys we know should be hit so。

Excellent。

![](img/886a749eaaa9f80910ebb04a9f92609c_359.png)

So let's debug that。 Okay， so now let's see。The x is this guy and the y is this guy。Okay。

And now that we。We added the base。Here are these。Weird numbers。I wonder why。

They really should have been exact， I think。Let's runttle through these guys。

So rotation matrix should be 10， yeah。嗯。Okay， so the mean is minus 10， the max is 10。Okay， aspect。

 okay， yeah， because we changed the pixels， so it's going to be a little bit finicky。That's okay。

 Yeah， so yeah。We expect a little bit of that。A bit of an error。

 So let's run that a couple more times。Do have。Okay， so this。

 we expect this to be correct because the pixel is five。64。2，72。And when we subtract the origin。

 we have a positive guide。Oh。You know what， we should have like a positive one X and Y so。です。Okay。

 now we share are positive on X and Y， and we do， okay。

Now we're subtracting the first guys that are equal in y in different than x， okay。

Now let's the do product， that's the part that we are propagating right。So this is this guy。

 and this is a positive X。 So this should be positive。It is。Now， this guy。一次。702，72。Okay。

 so this should be。I think this is going to be negative。Negative x。



![](img/886a749eaaa9f80910ebb04a9f92609c_361.png)

So I think these are wrong。

![](img/886a749eaaa9f80910ebb04a9f92609c_363.png)

Yeah， these are wrong。 We are testing these guys， this guy。



![](img/886a749eaaa9f80910ebb04a9f92609c_365.png)

And this guy。But we offset at the point。Based on this guy。So this really should be just this guy。

The thinkel P。ok。😊，Now。If we do that， we should really offset。I should really offset。This guy。

By this guy。And then this guy I should upset。By this guy。



![](img/886a749eaaa9f80910ebb04a9f92609c_367.png)

Because these were starting out here， it should be positive。Means this way。



![](img/886a749eaaa9f80910ebb04a9f92609c_369.png)

Yes， I think we are just like the collision stream。

We have to do like we really have to do step by step so we can understand the full thing。Do't we too。

To a few arguments。Or about two so。Just good。Okay， so this one。



![](img/886a749eaaa9f80910ebb04a9f92609c_371.png)

To be this guy。

![](img/886a749eaaa9f80910ebb04a9f92609c_373.png)

Okay， let's just see。 Oh， okay， and we are back。拿佬。



![](img/886a749eaaa9f80910ebb04a9f92609c_375.png)

Okay。And that's not cheat， let's do the whole thing。They're gonna be super slow。



![](img/886a749eaaa9f80910ebb04a9f92609c_377.png)

Yeah。

![](img/886a749eaaa9f80910ebb04a9f92609c_379.png)

And。Before we do the jump。In fact。This should already work。

Because we are getting the subtraction as the axisxes。See， these guys。

 I can really calculate them up here and we're going to do that。

We're going to optimize this later on， but just check out， I think。

This me do you guys things going to work？Do you guys think that if I put angle here？

This is going to work。We expect to see a rotating。Rectangle。



![](img/886a749eaaa9f80910ebb04a9f92609c_381.png)

I don't know。We are。 We are wrong。But our。而。Mulplication is wrong， probably。



![](img/886a749eaaa9f80910ebb04a9f92609c_383.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_384.png)

That is like 45。小肥 hand。

![](img/886a749eaaa9f80910ebb04a9f92609c_386.png)

That's do10。

![](img/886a749eaaa9f80910ebb04a9f92609c_388.png)

Yeah， these guys。

![](img/886a749eaaa9f80910ebb04a9f92609c_390.png)

Let's do 45 again。And let's。Go against with these guys。Okay。So the Max and min。Yeah， this is wrong。

Let's go one more time。So our angle is 45， yeah， our angle now is in a radiance。Okay。

 our P is 0 and our size is 10。Cosine signine， minus sign。Cose。This looks correct。

Our rotation matrix。Looks correct。But。This guy。-10 and 10。I don't know why we have0。Oh， okay， no， oh。

 okay， this is correct。So we have zero。-14。And our max is 0，14。 You know what？



![](img/886a749eaaa9f80910ebb04a9f92609c_392.png)

We can't， we can't do this。 this is the this is messed up。 That's why we got confused。

 That's for why just find out what I'm talking about direct。You can't do this。

We should do actually we can， but we should do this like up here。Then we multiply each。

Access each point individually。Yeah。This is correct。So it's going to be wrecked。For the。啊。同。

So're going to multiply。By the rotation。What lips use for rendering， No。

 we're not using any libraries。This is the thing。That's why we're having such a hard time having rotate rectangles。

Because we are doing all， all by ourselves。 See， this is actually setting the pixel color。😊，By hand。

 so no libraries and we did a lot of stuff we did alpha blending already。

 but now I don't know if you saw the state that's the state of the game Oh we got that huge thing。

Let's just removed that。Just to show you the state of the game。Oh。Can I just return it if zero D？



![](img/886a749eaaa9f80910ebb04a9f92609c_394.png)

Okay， so this is the game that we have so far。 and everything was written from scratch。

 And today it was the first time that we use the library， which was。😊。

The math library in the the CC library for。For sine and cosine， but the rendering we did ourselves。

 the collision we did ourselves， the particles we did ourselves ourselves。Yeah。

 I think it's gonna look a lot better when we。

![](img/886a749eaaa9f80910ebb04a9f92609c_396.png)

When we do more stuff like this， but turning pretty interesting Could you show the code higher create graphics window Sure。

 but if you want to come here to YouTube and I can。



![](img/886a749eaaa9f80910ebb04a9f92609c_398.png)

Can link it to the YouTube page。You can check out the whole process。

 we started out with the blank file。On episode  one， and I recorded all the streams。

 so you can watch the whole process of the whole thought process， but really quickly。😊。



![](img/886a749eaaa9f80910ebb04a9f92609c_400.png)

We are calling Windows stuff， right because this windows， so we create a window in Windows。That's it。

 we just create a window class and then we should call create window。

And then this is like for mouseo stuff that we do later on， So we gather inputs。

 this is like input from Windows， okay， and this is the rendering。So we show we say Windows， hey。

 Windows， this is our pixels that we allocated up there。 This is our our pixels。 this the size。

Show to the window。 So this is the call。 that wasn't too hard。 In fact， I've done that a lot。

 So that's probably why it wasn't too hard。 since I haven't done this a lot。

 That's why I'm having a little bit of a hard time。 or you are getting there， so。呃。

We were doing the wrecks， right， Yes， this guy。 So I'm going to multiply each of the wreck。

Dot P and I。Like this。Okay， now I'm probably going to do a make rec center。Center half size。Right。So。

Yeah。Yeah。Okay。😊，And the men。It's just the。0 P does0。

So this approach of menticing the pixels is fast where you think， I mean。

 it's ways lower than the GPU， that's for sure。If you wanted to do like the fascinating way possible。

 we wouldn't do that at all。But I think it's going to be fast enough for this game。

 and that's the point if it's fast enough for this game and we can learn a lot about graphics programming by doing things without the GPU so we know the whole process。

That's worth it and it's also。Yeah， I think that that's the point it's going to be fast for this game and it's also pretty good learning exercise。

They can delete it something， yeah。Okay， so we don't have that， let's make that。So we have a。

Inline right too， make correct center。诶。Center half size。 This is the center。 This is the。Half size。

And same thing here。But的面。Is the sea。Well。Yeah， know， in fact。

 I'm just going to call it that good guy。To return。Make correct Mmax。And a man is going to be。

If two of the。Center。Minus the half size。And then。不すね。在什么？Okay。Not convert。This guy to a float。

That's。Likeです。Man。嗯。😊，Yeah， and I think we have to do the same thing。

I'm going to optimize this later on。But this is just for。Are de buding。Poins。Okay。Okay， then we add。

The皮。Yeah， this is pretty。So even for a software rainry， it should be slow， this is stupid。

I may be wrong but the carro lip do the same。 I'm sure I'm sorry I don't know that lip。

 but I'm sure there are a lot of。Libraries that do software render。

Because it's great for learning and it's really easier to debug。

 especially when you do like more advanced stuff way easier to debug。So。Whenever I see men。

So I think this is going to。Are we using this， I don't think we are using this。Oh。O we are。

This is just。0。

![](img/886a749eaaa9f80910ebb04a9f92609c_402.png)

Let's see if we still see the same thing。

![](img/886a749eaaa9f80910ebb04a9f92609c_404.png)

No， we are wrong。 Our rats way over there。So。That sucks because we got to a nice point。

 but in order to clean up to the next part， we did all sorts of。So we could have messed up。A lot of。

 in a lot of ways， so。I can just go back and see that we don't have oh。



![](img/886a749eaaa9f80910ebb04a9f92609c_406.png)

We are totally wrong， first of all。I can just pass zero again。But even our。



![](img/886a749eaaa9f80910ebb04a9f92609c_408.png)

Points were wrong at this time， so yeah。I you guys quickly understand the code here。

 so this shouldnt matter。So， this should matter。Okay， so we've got the Dmion and Dmax。That's weird。

Because。This guy， the D mean and Dm， is what you're using for the points。

And that messed up the points。So I think our act is wrong。So。先制。Minus the half guy。Oh。

 we were doing Maxim。That's not very intuitive， me Max。

Just mentioned you are using a C plus plus lights instead of C。 Yeah， I am。诶。

I think it's easier to do that。

![](img/886a749eaaa9f80910ebb04a9f92609c_410.png)

You know， I wished there were a couple of C+ plus things in C。

 just a couple like default arguments is a big thing for me because I think it makes life really easier。



![](img/886a749eaaa9f80910ebb04a9f92609c_412.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_413.png)

But。But this is C， so。I do some seaside clinics as well。Okay， so let's see。 Yeah， we are still wrong。

 for some reason， our points。

![](img/886a749eaaa9f80910ebb04a9f92609c_415.png)

Yeah。That's debug again。So first of all， we construct our rectangle。Which is 10。天天嗯。Yeah， see。

 it's wrong。 You're supposed to be-10。

![](img/886a749eaaa9f80910ebb04a9f92609c_417.png)

-10。Man Max。

![](img/886a749eaaa9f80910ebb04a9f92609c_419.png)

That's stupid。 So do you have any other protest see。 Yeah， I do have。 I actually。

 I've done a lot of protest see。 I've done like a web server and see。😊。



![](img/886a749eaaa9f80910ebb04a9f92609c_421.png)

I did a computer programming language and see， I did a few other games and see if go to the HI。

 you can see the other games。

![](img/886a749eaaa9f80910ebb04a9f92609c_423.png)

Like。Yeah， these two were in C as well， this was C++。This was using a real engine。So yeah。

 I've done a couple of things and see。

![](img/886a749eaaa9f80910ebb04a9f92609c_425.png)

Not too too much， though， okay。

![](img/886a749eaaa9f80910ebb04a9f92609c_427.png)

Man Max。 start out the man。 what's the next， let's。D again， so now this should be minus-10。It is-10。

10， Then I expect it to be。Minus10。

![](img/886a749eaaa9f80910ebb04a9f92609c_429.png)

Tam， dude， this is。Yeah。Menax。Max it。

![](img/886a749eaaa9f80910ebb04a9f92609c_431.png)

Okay。From。Programming language like seat Python。I don't know what to mean。



![](img/886a749eaaa9f80910ebb04a9f92609c_433.png)

C， just these projects were in C， yeah。

![](img/886a749eaaa9f80910ebb04a9f92609c_435.png)

It's good to see。Yeah， these reacts are really wrong。 I don't think today's a nice。

It's a good programming day， but I really want to finish this guy。So 0 and 10。 So this should be。Oh。

Okay， I wanted to step into that， so it is minus 10， minus 10。us10，10，10，10，10， minus1， this is nice。

So we should really just do that。Yeah。So-10-10。 Oh， we're just getting the P。 Oh， but it is。 Oh。

 I'm sorry。 I thought I' find the problem。 I didn't find problem。 So the P 0。



![](img/886a749eaaa9f80910ebb04a9f92609c_437.png)

嗯。Yeah。These are the super mistakes that。Takes a long time， too。



![](img/886a749eaaa9f80910ebb04a9f92609c_439.png)

The track。

![](img/886a749eaaa9f80910ebb04a9f92609c_441.png)

Now you should be back to normal。And we are not that normal。



![](img/886a749eaaa9f80910ebb04a9f92609c_443.png)

Because these guys。We correct。See the problem is when I don't fully understand 100%。

 I saw a meme the other day。

![](img/886a749eaaa9f80910ebb04a9f92609c_445.png)

I just tried a lot of different stuff。But let's drop and you guys can understand as well。



![](img/886a749eaaa9f80910ebb04a9f92609c_447.png)

啊。Okay， we have now direct Act minus 10。-10。in-10。1010。10。10。マ1。啊。No， actually， this。



![](img/886a749eaaa9f80910ebb04a9f92609c_449.png)

This was correct。

![](img/886a749eaaa9f80910ebb04a9f92609c_451.png)

Okay。So。So， let's。more time， so。So minus 10 minus10 have 10， minus 10。10，10，-10。



![](img/886a749eaaa9f80910ebb04a9f92609c_453.png)

O。😊，This is what were supposed to have at this point。Let's check out。in- 10， minus 10， 10， okay。

 is what we have。Now， when we multiply the matrix， the react should。Should be， let's see。We have。

The bottom point。They have the top point。Yeah。知。😊，We did all stuff to get to this point。

And that's not correct。We are multiplying each of the points。By the rotation of matrix。



![](img/886a749eaaa9f80910ebb04a9f92609c_455.png)

Oh， you know what。Not that this is going to matter for now。But this guy should really be zero。

But we are zero， but if you weren't zero， it would be all over the place。

 let's just see what will happen。I mean， we are all over the place。Not that we are incorrect， but。



![](img/886a749eaaa9f80910ebb04a9f92609c_457.png)

Numbers there。We will add sound， Yes， we will add sound to the game。



![](img/886a749eaaa9f80910ebb04a9f92609c_459.png)

And hopefully we'll do that。When we finish this sing pass。



![](img/886a749eaaa9f80910ebb04a9f92609c_461.png)

How am I going to do that， I'm going to indirect sound？Which is like the Windows library。And。Yeah。

They're going to pretty much on and then the mix are were going to do by hand。Okay。

 so we make direct。Yeah， I'm not going to worry about the P for now， it's going to be wrong。

 but I'm going to correct that later。

![](img/886a749eaaa9f80910ebb04a9f92609c_463.png)

I don't know why I got that wrong， man， this was supposed to work。

What are we not understanding about the program？Im passing minus-10， minus- 10，10， minus 10，10，10。

 minus10，10。ok。Okay。Okay， let's check out the rec。So。This is correct。This。It's not。Correct。Oh， oh no。

 this is correct。Oh， I got that wrong， we are correct。



![](img/886a749eaaa9f80910ebb04a9f92609c_465.png)

Dude， we are correct。So， in fact， I'm going to save。Yeah。This is wrong。

 this is why we're not correct。Rect to， correct。Thes react， and then we do that。

So we were changing the rack to be better and we had the old system that was wrong。



![](img/886a749eaaa9f80910ebb04a9f92609c_467.png)

Okay， okay。Nice， we are back to having the。

![](img/886a749eaaa9f80910ebb04a9f92609c_469.png)

带了那。

![](img/886a749eaaa9f80910ebb04a9f92609c_471.png)

Go back to having the angle working。知。😊，Oh indeed， we do have some weird behavior there on the left。

 see。

![](img/886a749eaaa9f80910ebb04a9f92609c_473.png)

So we're getting there slowly， but we are。And。This doesn't matter for the player， right。

 automatically manage that is we managed to make it but it does matter for our learning process just it's nice to make mistakes at this point。

Okay， so。嗯。We got to this point and then we changed that to the screen。

Aspect ratio to the screen position。Right， we multiply and we add。Okay。Now。

Let's check out these guys。 We have the pixel position， and then we do。你。Yeah。

 let'slie but I'm working in the university I doing the particle shapes properties calculations see。

 But what we are doing is amazing。 Maybe I'll do some concepts you are implementing now。

 Thanks so much for sharing。 Do no problem。I really liked。That you liked。 And I check out。

 we did particles。 We didn't part of the last couple streams。

 but last stream was the big particle streams。 So we can check that out on YouTube。

 And if you have any question about what we did， that went way smooth smoothier than what we're doing now。

 But this going to help the particles。 because right now。😊。



![](img/886a749eaaa9f80910ebb04a9f92609c_475.png)

It certainly be quite hard to see。The particles they see they don't rotate， they just move。

When we add， well， it's hard to see。Yeah， it's kind of can kind of see here。



![](img/886a749eaaa9f80910ebb04a9f92609c_477.png)

Yeah， there， we're going to add random rotations in particles。

That's going to add the visual appeal a lot。So let's debug these guys。



![](img/886a749eaaa9f80910ebb04a9f92609c_479.png)

啊。Okay。So the pixel。All the way， the zero pixel， right？This guy's really negative。Really positive。

 really negative， really positive。It's going to take a while。Let's see。喂。

The guy here on the far left。God was were correct。Okay， so the projections。Or worked。

And the pixelixo P。The pixelix P looks correct。

![](img/886a749eaaa9f80910ebb04a9f92609c_481.png)

Oh， okay， stupid mistake。 We should increment the pixel， even if we don't。 Oh my god。



![](img/886a749eaaa9f80910ebb04a9f92609c_483.png)

Even if you don't。Paint them。Oh， victory。呵呵。😊，So we finally managed to add the rotating rectangles。

Thats great need。

![](img/886a749eaaa9f80910ebb04a9f92609c_485.png)

So what we're going to do now is clean this up， optimize this up。



![](img/886a749eaaa9f80910ebb04a9f92609c_487.png)

And then， maybe。Add that to our particle systems。And I've seeing particles， I mean， real particles。

 okay， you're talking about like physics particles， not explosion particles。 Yeah。

 I know nothing about those。😊。

![](img/886a749eaaa9f80910ebb04a9f92609c_489.png)

I that was really funny。

![](img/886a749eaaa9f80910ebb04a9f92609c_491.png)

It must have thought， okay， these guys's pretty crazy。Okay。

 let's just see up close what we have because come on， that was pretty cool， right？



![](img/886a749eaaa9f80910ebb04a9f92609c_493.png)

What we may want to add later on is actually sub pixelixel accuracy， so。

We should have like a smooth border here。Even things does it see？Yeah。Should add that。Later on。

 but I think we are perfect for now。Yeah。😊。

![](img/886a749eaaa9f80910ebb04a9f92609c_495.png)

So。Couple things we're gonna gonna clean up， right， First of all， we don't need to do that anymore。

 So let's just。Destroy this。In fact， no， I think we can describe that。啊。

So we're going to optimize this， which is the main are you talking about anti As yes exactly。

 but we're going to add like a， I think we're going to pretty much hack anti avium and we're not go to like a full anti avisacy。

I don't know if that makes sense or not， we're going to try a couple of things。But yeah。

 let's see this is the main problem right， we are doing like repetitive things like over and over again。

 we can probably save。This guy。And this guy， oh。Yeah。So this guy， I'm going to call that axes one。

 two， and three。So like aes。完。A is one。Was this guy。F is 2 and3。And two is 0，1。The other one is。3。

Well？0，3。Okay， these are the axes。We are going to test against。Okay， dude。 That was pretty cool。See。

 once we get to work， which is the hard part， cleaning up， way easier。But that's kind of obvious。

 right？You can also。Let's see。 we have。Okay， let's just make sure we didn't break anything。



![](img/886a749eaaa9f80910ebb04a9f92609c_497.png)

And we didn't。Pretty cool。 prettyty cool。

![](img/886a749eaaa9f80910ebb04a9f92609c_499.png)

Oh， we should also do like。A draw rotangle， transparent rotator rectangles for the particles。

The one step at a time so。First optimization， done， second optimization， this guy。You can do like。

Like the。Relative。And we could also do。The park relative to the same point。But yeah。

 I don't think they'll matter much so。Pixel。Oh， this， yeah。So。Call that pixelix P braille。1。

Pix O P realm。Then I'm going to do 2 and 3。So this is the pixel around2， and this is the one again。

1 and this the pixelix。

![](img/886a749eaaa9f80910ebb04a9f92609c_501.png)

Okay。

![](img/886a749eaaa9f80910ebb04a9f92609c_503.png)

Let's see。 We are still working， nice。And okay， so in fact， now we're just learning a lot better。

 to be honest。

![](img/886a749eaaa9f80910ebb04a9f92609c_505.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_506.png)

I mean。Not a lot better ands still pretty bad and our player gets way out of hand。



![](img/886a749eaaa9f80910ebb04a9f92609c_508.png)

When we are in a slow frame rate， let just check out why just a second。嗯。Let me see。

 where's the drop player here。

![](img/886a749eaaa9f80910ebb04a9f92609c_510.png)

I can see the target position to so we can see if there is actually a movement problem。

Or scale problem。

![](img/886a749eaaa9f80910ebb04a9f92609c_512.png)

嗯。Yeah， this is actually maybe a scale problem。

![](img/886a749eaaa9f80910ebb04a9f92609c_514.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_515.png)

Yeah， it is a scary problem。

![](img/886a749eaaa9f80910ebb04a9f92609c_517.png)

So。I'm not going to fix scale now， but I'm going to write this down。In the see。This guy。😊，6。

Players scale。At low。Okay， let's go back。To our and this is pretty much S。Sint。

 they can make it Now this is also a problem because we're going through the whole screen。

And we don't need to do that。 All we need is like the smallest。The smallest。Guy in here。

And we can also optimize this， but I don't think this will matter much。

So in order to do the smallest guy there。All we need to do。Let's， let's do like this。嗯。

So this is like the min。Man bound。Yeah， and the min bound is going to be。0，0。

You have to do inside a main C file and not somewhere else。 I dont know。

 it's just more convenient this。Fies like 1100 lines。

So I'm not afraid to put a lot of stuff inside here。This is way more convenient， I think。

Don't you think， I mean， it's already here， I just。买啥子都。Sometimes I do do a to do file。バラ。

But only if it's like a bigger project， I think， renderer buffer。Looks nice， thanks。 Yeah。

 I don't know。 I don't think it's like the most organized。😊，Thanks ever。But it's somewhat organized。

So we had to min bound and the max bound。So let me calculate。The note P。You're like， if。This guy。

DotX is less than。嗯。I just是。I just trunccate。I should， I should truncate the。Yeah。

 I'm going to do like a trunk heat。X truncated， truncated。I don't think we have truncet do。AlLet's。

Lines。Truck。And then I'm going to return。And then I'm going to do this here。Class one。

It also would you like around。Oh。See， that's why I don't like important libraries。

 they already have a seal。嗯。CF。过。They also have a trunk ca。啊。And Kate。Cal F。

 they have seal and seal F。咁晚。Let's just use stairs。But yeah， I we learn how to do it okay。

 so let's do itron。Of。卖笑。I'm not going to name it nice seal。I just accept the defeat。The X。

 and let's do it like dot y。て理。会就洗了。Yeah， I'm not sure how they attack it so。The lot to end。

So it's supposed to be trunk， right， flow to it。Dude， what' the problem？Tncet。

I'm going to do my version。And I might as well call it my， my that I'm getting。So I want a truy。😊。

It's called tru K to F。This is seen on Thursday， yeah。Yeah， well。

 but they're not spoil if they are doing a library for C and they know it's not namespace。

 they sort prefix the library should be STD。On this course seal。So。Yeah， it's not C's problem。

 It's their problem， I think a library problem， so it's going to return。And a。啊。I'm going to do like。

F32 and break my pattern just so you can get like COF 32。Sorry I ran to。Okay。So， try。F 32。COF 32。

Okay， nice。Now we can test if。The truncate version of x is。Less than the min bound。Dot X。

The min bound on X meant to be equal to this guy。Then we do that for。All of the other stuff。Ex。系。好。

I would subscribe。No， this is not correct。If the max bound。Creer than that Max found。M balance。

Max round。Ex round。啊。Yeah， this should be the。Okay。Now that we have this information。

 we can optimize it and this is going to run way faster。 Let's do like。YC。啊，你好。Thisす。This is that。

Man bound to by。This the next。Bye。打 by。And this is a moon downt dot X。It is the next bow。Tod。Okay。

 let's just this code。So we got the minimum and maximum balance。Yeah。

lookss correct I'm going to step this code because this is kind of a big deal optimization。

So if this isn't working。

![](img/886a749eaaa9f80910ebb04a9f92609c_519.png)

Oh，We're going have like。Some headaches later on。Let's say we are passing， We are supposed to draw。

那行。呃。First， draw。These guys， 563。272， let's say our minimum balance。0。0。

So I think the max is working。Max x is 7。Yeah， next X is working。And max Y is also working， no。

 it's not working。

![](img/886a749eaaa9f80910ebb04a9f92609c_521.png)

So we messed this up。If the truncated。Version of X。It' less than the minimum。That's the农。

If the trunk if the seal version is greater than the max， oh。



![](img/886a749eaaa9f80910ebb04a9f92609c_523.png)

放的卡。So see， thank God， we well。

![](img/886a749eaaa9f80910ebb04a9f92609c_525.png)

No， this probably was going to work， so think I you fix that。



![](img/886a749eaaa9f80910ebb04a9f92609c_527.png)

In our debugging thing。Okay， now let's see we have。You see our minimum is still zero and our maximum。

Now we're super wrong。Did I do like everything？

![](img/886a749eaaa9f80910ebb04a9f92609c_529.png)

Max bone X。Max bound X。Yeah， F 32 is just32 bit float， yeah like。Just。I think it's easier to type。

And it follows the other pattern for int。As well。嗯。X。



![](img/886a749eaaa9f80910ebb04a9f92609c_531.png)

Dude， this should be easy to write， I don't know， todays pretty slowly。Pre simple so。

The minimum bound is 0， and it's got X， T， X。

![](img/886a749eaaa9f80910ebb04a9f92609c_533.png)

Okay， so the problem was I need should lies that wrong， so the minimum bound。This guy。哎呀。



![](img/886a749eaaa9f80910ebb04a9f92609c_535.png)

I don't know what I was thinking。Yeah， this may be a sign too。Is it safer to use this set of double。

 for example？A safer， I don't know what you meant for safer， I mean。

You use double when you need a lot of precision。And。

Like let's say you're doing like a movement system for a game and you store the X Y position in double。

And you go all the way from zero， zero， which like the center of the world。

 which you have huge precision。All the way to like 100，000 kilometers the other way， right？

If you want like centimeter precision， you're probably going to use double or like break up the world in segments and things。

But that's the use case for double， not safer， I think。So I'm not entirely sure what you mean。

So their minimum bound x， let's see。Okay， I think we are correct。

 We expect the minimum bound x to be 563 and an maximum to be 7。563 max 701。

 Actually this is correct。And then the minimum y we expect to be 272 and the maximum 2409。So 272。

For 09， now we're talking， and now we should run pretty smoothly and we do。



![](img/886a749eaaa9f80910ebb04a9f92609c_537.png)

Oh， but if we are wrong， I'm wrong。

![](img/886a749eaaa9f80910ebb04a9f92609c_539.png)

Okay， we are wrong because of。This guy。Yeah， we remove that when we did the whole screen。

 now I can put that。

![](img/886a749eaaa9f80910ebb04a9f92609c_541.png)

Okay， oh。

![](img/886a749eaaa9f80910ebb04a9f92609c_543.png)

Men round X。

![](img/886a749eaaa9f80910ebb04a9f92609c_545.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_546.png)

Okay， we are back to normal and we are running pretty smoothly and this is the deep build。

 So if we build that on the。

![](img/886a749eaaa9f80910ebb04a9f92609c_548.png)

The normal bill is going to run even fasterier， so this is pretty perfect I think。



![](img/886a749eaaa9f80910ebb04a9f92609c_550.png)

Yeah。Let's。Let's go back to the rotation， which was the whole point of today's stream。

 I think we're going to keep just that rotation and next time can do a bit maps and never do like entire if we need。

Safe means， for example， if difficult pilots can take different outdoor bites。 Yeah。

 I know what you mean。😊，Like for some platform。That。Yeah。Like can some platform， maybe。

Itt is not 32 bit like then we do it like this。And maybe float isn't 32 bit。呃。I don't know， I mean。

 if this game was supposed to last like 10 years， I'll be a little bit more worried about that。

 but it's also easy to change， but。But no， I don't think。

 I don't think there is any platform that C compiles to that float is not 32 bit。

 Well maybe some like。Some like， I know， embedded device， but。



![](img/886a749eaaa9f80910ebb04a9f92609c_552.png)

Yeah， I'm not too worried about that for this project。Perfect， is it not perfect， this is perfect。



![](img/886a749eaaa9f80910ebb04a9f92609c_554.png)

Now we should play around with this， just in fact， just one more thing that maybe we can optimize。嗯。

This whole thing here。嗯。那是。Like。Speed。Maybe。You are single。Mattrix。F方。这ね。Yeah。I don't know。

So let's now start using our guys。I'm going to do in our particle system。你说。啊。Bed particle。Oh。

Brainner particles。Let's do a draw。Transparent。Rotated。Then we can do。A屁。An。Okay。

 and for a transparency。Trans。What can just。对。😊，Alpha enemy we should also take an alpha。Okay。

 undefined。Oh。Yeah， you know what I'm only going to do。T I rotate a transparent x for now。

You're going to think about a better name later on。And then we're going to add。And。Okay。Okay。

 now let's do when we spa particle。We should take in。angle。So。

An explosion should have randomom mangos。So I'm going to do random F32 in range。Let's do 0，2，3，16。

And block the stride should be zero， the angle。さ。And render render the ball。Okay， this one。



![](img/886a749eaaa9f80910ebb04a9f92609c_556.png)

This one's it's going to be cool I'm going I need when we spin the ball I'm going to set。

 let's say if the ball is going this way， the ball is going to be a square but the particle is going to be rotated。



![](img/886a749eaaa9f80910ebb04a9f92609c_558.png)

So I need to find like。A find。呃。And go something like this。

 what do you think should the programmer even in C pay a lot of attention to making the program smaller in memory during the execution？

We have a lot of RAM actually in the future we have even mared to be6 where it doesnt matter or not。

This is the thing， in my opinion。😡，Depends on what you're building。So if you're doing like a castle。

 like this guy， if you're doing like command prompt。

You don't want to span like a whole bunch of rain， you don't because people are going to run like a ton of these。

I'm just going to leave this guy running like I'm doing now。So。Like。

Don't use like more than you need that's that's the main， don't use more initiate， however。

 when you're doing a game。And you're expected it to be the main thing。

 if not the only thing the player is running。So you should be able to use this memory right so you are free to use that。

 you should not use it for no apparent reason， but I think you should use that reason to make the game better so if to make a game faster or maybe avoid loading strings。

And。Yeah， so I think depending on the application， you should really use this RA。To make it better。

 but not likely。 So yeah， I think。They should be aware， but not to make it smaller necessarily。

 but to make it use it more I't know。More interesting in terms for the user， I suppose。Yeah， okay。

So I'm going to do like a find angle。I'm going to make a like fine look at angle。

 this unreal reals name for this function。But they return like a full quaernion， but this is like 2。

 so find look at angle。And I go into pass。We're going to pass。嗯。The speed， right， the ball。D P。

 and actually， before I do this。What best。Getting kind of ahead of myself。Let's see if we are。

 if we run， yeah， we see particles。

![](img/886a749eaaa9f80910ebb04a9f92609c_560.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_561.png)

And we run pretty well。 Oh， we have to claim the alpha。Like we did。Yeah， I have to claim the alpha。

 let's see， that's the only thing we do here。Okay。

![](img/886a749eaaa9f80910ebb04a9f92609c_563.png)

So。Back to normal， I suppose。 So now let's do the thing。

And we worked hard today for like two hours to do past the radius vector。

 you can show the director of the particles movie。

![](img/886a749eaaa9f80910ebb04a9f92609c_565.png)

The radius vector。I'm not very a math guy， I'm sorry， I don't understand much math。The radius vector。

 what is exactly is the radius vector。I think I'm just going to pass the speed， is it not？

Can show the direction of the particle moving。Yeah， I think， I think that's， that's。

I suppose I'm not sure， though， oh， in fact， we are supposed to have random particlesels already。

 are we not？

![](img/886a749eaaa9f80910ebb04a9f92609c_567.png)

I forgot about that， and apparently we don't。

![](img/886a749eaaa9f80910ebb04a9f92609c_569.png)

Oh， because we don't set it。Yeah， the spa particle。Receives the base here。

The angle in which we really set it。Radius。The vector that has an initial point at 00。Nice look。

 Thanks。 Great bullet， V E。😊，呃。Yeah， yeah， so we were talking about the same thing。Yeah， but。



![](img/886a749eaaa9f80910ebb04a9f92609c_571.png)

I didn't know it was called a radance vector， so I have like two vectors。

 this like the old P and the new P。Let's say it's going like this， right if I subtract these guys。

 I got this vector that is pretty much。Yeah， it's this factory。



![](img/886a749eaaa9f80910ebb04a9f92609c_573.png)

So the other two are point I suppose， and this is the actual vector。I'm C plus plus programmer。

 That's awesome。 dude。 C plus plus Its really cool。 It's pretty much like C。

 except it has more features。 Some of them are pretty cool。 Some of them are pretty confusing。

 watching my enemy。😊，You're watching your grandfather， actually。

You're watching the wiser version of C++。呃。Okay， so we're going to do the find。



![](img/886a749eaaa9f80910ebb04a9f92609c_575.png)

Okay， no， actually that's test。If we got to work。

![](img/886a749eaaa9f80910ebb04a9f92609c_577.png)

And we are super wrong。 And I， and I。Okay， we are super wrong several ways。

If it's easier or more direct you see， yeah。I like to see because the cold is way more direct。

 so I don't know if you guys remember。

![](img/886a749eaaa9f80910ebb04a9f92609c_579.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_580.png)

But we had a problem that I postponed now I have to fix the problem。

 see the parcos were all over the place。

![](img/886a749eaaa9f80910ebb04a9f92609c_582.png)

That's because of the order。 we are doing the matrix stuff， so。



![](img/886a749eaaa9f80910ebb04a9f92609c_584.png)

We can't。Or do we we can't do this guy here。The first。Have to rotate。The first have to rotate。

Then we should add。The speed。Like this。The position。一。😊。

I have a problem with public space tried multi threading。Okay， yeah， I kind of missed this the chat。

 I usually see too， if it's easier。Your name is Python but。



![](img/886a749eaaa9f80910ebb04a9f92609c_586.png)

Yeah， we're going to do multi threadread when we do audio， you know。



![](img/886a749eaaa9f80910ebb04a9f92609c_588.png)

Okay， dude。Okay， this is not correct yet， but this is any correct。



![](img/886a749eaaa9f80910ebb04a9f92609c_590.png)

So another problem is we should add this guy， the P。Before。We multiply it。

They I actually do like a full matrix。Yeah。Which is this guy。The first ad。Then we multiply。

Then we do。The other position。So， yeah。Not entirely happy with the way this is structured。But。

It's good enough for now。T。It's not a member of V2。

What's the input event you can make much more fluent if thepoleonos type threat， a good idea。呃。Yeah。

 since this game is going to run pretty fast because it's prettymogging。

 I don't think I'm going to do like thepoon on a different thread。This time I'm getting the input。

 I just at the beginning of every frame， get all the messages that window sent to me and check for like key key stuff and then get the mouse at this point。

I'm going to use threadready for audio。Definitely， because that's really important。And also。



![](img/886a749eaaa9f80910ebb04a9f92609c_592.png)

Probably rendering， depending on the art performance。 but I I am going to。Check the， O。

Check the performance before you do that like profiling。



![](img/886a749eaaa9f80910ebb04a9f92609c_594.png)

Oh， see， see how cool is that。 I think our explosion is wrong。😊，嗯。Partrticle explosion。

I think our explosion is wrong in this sense here。Renom bilateral。Times 10%。Tch the day size。y， see。



![](img/886a749eaaa9f80910ebb04a9f92609c_596.png)

That's wrong。We have a real nice side in my head thanks。Okay。This is starting to get nice。

The life or the explosion particles are still。

![](img/886a749eaaa9f80910ebb04a9f92609c_598.png)

Not。Justly so life is going to add。A random bilateral， which is minus1 to1 times。

10% of the base life。Numbers are right。Let's not do that。Let's not do that。



![](img/886a749eaaa9f80910ebb04a9f92609c_600.png)

Do write everything in one line。

![](img/886a749eaaa9f80910ebb04a9f92609c_602.png)

I will show my quote， of course， okay。Yeah， see。 now the life looks consistent。 So does the size。



![](img/886a749eaaa9f80910ebb04a9f92609c_604.png)

So this says this was supposed to be pretty easy， right in going to end。To the size， a random number。

That's 10%。Offf the base size。We are going to add a random number。That's 10%。O the base life。

Or maybe the life， oh yeah， I don't know。It to simulate important things in separate strings。

I don't know what you need。

![](img/886a749eaaa9f80910ebb04a9f92609c_606.png)

嗯。Yeah， I don't know， it kind of look bad， I think。Let's try this based invade。嗯。😊。

That's pretty cool， man。Sorry to get nice。 But before we try to fix the exp， let's just do the。



![](img/886a749eaaa9f80910ebb04a9f92609c_608.png)

Yeah。啊。ILet to define。Look at rotation things， so this is going to be。糕。Anle equals fine。Look at。

Votation。And then。I'm going to pass。挂。Yeah， moved to pass。The ball Dp。A're going to pass like up。

I should also can like get。Vactor rotation。Then I'm going to print。电个。

If you have certain space in strength for an okay。Yeah， then I'm going to do。Like。

 where do you have like。Decrease。So I'm going to do an inline F 32。Get vector rotation。And。

So what I want。嗯。

![](img/886a749eaaa9f80910ebb04a9f92609c_610.png)

I see。😊，Yeah， it's like the arc。Yeah， I think。J ofvis is going to know this better than I do。

 But I want like the。

![](img/886a749eaaa9f80910ebb04a9f92609c_612.png)

8，102， right。

![](img/886a749eaaa9f80910ebb04a9f92609c_614.png)

嗯。Yeah。

![](img/886a749eaaa9f80910ebb04a9f92609c_616.png)

The a tangent。So do we have the arc tangent？

![](img/886a749eaaa9f80910ebb04a9f92609c_618.png)

嗯。Let me see again。Y x。

![](img/886a749eaaa9f80910ebb04a9f92609c_620.png)

被道啊。right。X。But we need more stuff， right？啊。Missing crazy before V。What is that supposed to be。

I like your quote a lot， thanks。The first part， there's no problem， dude， it's all good。

You don't have a V2。No， we don't have a big tool。

![](img/886a749eaaa9f80910ebb04a9f92609c_622.png)

I she looks superb。I thank you。 Okay， so got one。

![](img/886a749eaaa9f80910ebb04a9f92609c_624.png)

Yeah， okay， nice。 Now let's do the A 12 thingme。We are tangent。But do we need the any E。

Compver it from double to end to have。

![](img/886a749eaaa9f80910ebb04a9f92609c_626.png)

F， we do。Maybe it's going to work。-1，1。

![](img/886a749eaaa9f80910ebb04a9f92609c_628.png)

2， yeah， this， this， I think this is in a radiance。 Let's do like。Red。To dig。When we do like dang。

Let's see with the other one。Red to egg。Youre take a。And it's going to be。



![](img/886a749eaaa9f80910ebb04a9f92609c_630.png)

嗯。

![](img/886a749eaaa9f80910ebb04a9f92609c_632.png)

Okay， this looks， looks perfect。Come on， wait。I was looking at the particles。ok你。

They look almost nice。 See， this looks perfect。😊，This is exactly what we wanted to do that that was awesome but this the size looks wrong。

 this side。AndWhy do we crash？Pixel was， let's see where do we try to render。

Minimum bound is minus-1。

![](img/886a749eaaa9f80910ebb04a9f92609c_634.png)

Yeah。小。嗯。😊，Minimum bound。And it should really be like。You mean bound X。It's going to be。Yes。Camp it。

2 clam 0， to render buffer。Dod。Mean a bound。And a mean balance why？Do the same thing。

And then I'm going to do the max。The same thing， so。



![](img/886a749eaaa9f80910ebb04a9f92609c_636.png)

But I was going to crash。But our particles only look right。If we are positive， I suppose。Oh。

 this looks right， I think。Okay， so this is wrong。But now， this is right。



![](img/886a749eaaa9f80910ebb04a9f92609c_638.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_639.png)

Have good night， man， have a nice。Sleep。So， this is。This is working okay。You know。

This is also working， okay。嗯。I don't know why we're getting like。Yeah， value is like1 thousand。



![](img/886a749eaaa9f80910ebb04a9f92609c_641.png)

Maybe it's because we're not normalized。

![](img/886a749eaaa9f80910ebb04a9f92609c_643.png)

Let's， let's see the8 and 2 guy。Keeps getting better。 Thanks， man。 it does。

 Today we implemented rotator rectangles。

![](img/886a749eaaa9f80910ebb04a9f92609c_645.png)

So our particles can use that。 But it's almost 100%，100% Yeah see that case didn't work。

 So we're doing like some。

![](img/886a749eaaa9f80910ebb04a9f92609c_647.png)

Matthew， so this angle is the8102 X， Y。Of this guy。

 it returns the angle between the array to the point x Y and the positive x axis。

Confly to minus pi to pi well。Apparently， this is not working， right。

 because we didn't get way more than minus pi。

![](img/886a749eaaa9f80910ebb04a9f92609c_649.png)

That just。To be safe， this is not it is it？

![](img/886a749eaaa9f80910ebb04a9f92609c_651.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_652.png)

That's plains slow motion。It's too fast for me。D T is time。



![](img/886a749eaaa9f80910ebb04a9f92609c_654.png)

ok。We have 1，80。I suppose it doesn't matter， right， but。We are wrong。

I think we are offset by 90 degrees。

![](img/886a749eaaa9f80910ebb04a9f92609c_656.png)

This is correct， see。Yeah。You are proud I'm not sure why。



![](img/886a749eaaa9f80910ebb04a9f92609c_658.png)

me see here。Oh， because our zero is considered to be。Not turned to the， but turned up， yeah。

 so we are said 90。

![](img/886a749eaaa9f80910ebb04a9f92609c_660.png)

So all I need to do is like subtract 90 from this guy。



![](img/886a749eaaa9f80910ebb04a9f92609c_662.png)

I think。

![](img/886a749eaaa9f80910ebb04a9f92609c_664.png)

Let's see， Yeah， I have pretty weird numbers。But it it looks correct。一次。Okay， this looks perfect。

Perfect， indeed。And I think it's perfect now。Yeah。I think our trail is perfect now let's fix the explosion particles because they don't look too nice okay。

 this is not。It's not correct。嗯。😊。

![](img/886a749eaaa9f80910ebb04a9f92609c_666.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_667.png)

That's a little bit more controlled experiment in this guy。So， find。So I'm going to， I have an angle。

Yeah。I a name个。呃。Between I and't know。Let's see。Let's say  zero， zero。And the ball。

And then I'm going to draw a transparent rotate row。0，0。Let's do。2，2。H歌。Stwide。



![](img/886a749eaaa9f80910ebb04a9f92609c_669.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_670.png)

ok。This looks correct。Now let's see if you are going to keep tracking the ball。I don't know， man。

It looks super weird。

![](img/886a749eaaa9f80910ebb04a9f92609c_672.png)

I think we are missing something。 I may。 I may end up just cheating。looking at my other code base。

Because I'm really tired at this point。But。Yeah， you know what？I think the problem is， we are。

We are getting the other way around， so。We should really do， like。Shouldry就 like。Fine。

 I'm going to do like find。这取。And it's called that A and B。And I went to。S。These guys。诶。😊。

Geometrical thing like this is complicated it。 Yeah， I always get these things wrong。

 I don't have enough practice。 That's why making this a lot by hand is good。It's a good exercise。

 really。A redefinition of A B。Do have a day job， I do， I I have a startup。

That does help students get internships here in Brazil。 I， I do all sorts of stuff there， but mostly。

Mostly like the web portal programming， that's where I like programming C and my free time。Because。

I don't know。Web， it's not really fun。So yeah， I like to do games for fun。Okay。

 and then we do like the find look at rotation that I'm going to do。

Going to this is the starting point and this is the endpoint that's what I want。

 So let's see if now this is a little bit more correct。



![](img/886a749eaaa9f80910ebb04a9f92609c_674.png)

We're used for， I'm using node GS。

![](img/886a749eaaa9f80910ebb04a9f92609c_676.png)

P P now yeah， I use node GS。For no particular reason。



![](img/886a749eaaa9f80910ebb04a9f92609c_678.png)

I don't like them。Like。I don't like any of them honestly。But it's got to be done so I do it。

I don't know why they rotate so much。

![](img/886a749eaaa9f80910ebb04a9f92609c_680.png)

Let's upon the animation is pretty cool。 Let's print。



![](img/886a749eaaa9f80910ebb04a9f92609c_682.png)

And勾。So 360， that's acceptable。60 kind of acceptable should be0。Well， the angle looks okay。

To be honest。

![](img/886a749eaaa9f80910ebb04a9f92609c_684.png)

嗯。

![](img/886a749eaaa9f80910ebb04a9f92609c_686.png)

Let's do something else。 Let's do， like。Ango。Let's do static。Equals0。Just for the testing。

 then let's do like static。啊。Then we do like， if calendar is greater than。One。Counter minus equals 1。

Then we do like the angle plus equals。I know。30。2。Maybe the string rotation can be a good feature instead of a bat。



![](img/886a749eaaa9f80910ebb04a9f92609c_688.png)

I still have a bug。I don't know man， this is kind of a fundamental thing。

 so let's see if we rotate 30 degrees every second。😊。



![](img/886a749eaaa9f80910ebb04a9f92609c_690.png)

Actually， we do have to increment the counter。

![](img/886a749eaaa9f80910ebb04a9f92609c_692.png)

Okay。That there's about  third0 degrees。No， in fact， no， I I think this is wrong。



![](img/886a749eaaa9f80910ebb04a9f92609c_694.png)

Yeah， I definitely we had like twice in90。Oh， we had a three times in got90。No。

 I think this is correct huh。😊，No， I think this is correct that's。Frequent。



![](img/886a749eaaa9f80910ebb04a9f92609c_696.png)

No， add。 this is correct。

![](img/886a749eaaa9f80910ebb04a9f92609c_698.png)

So our collision is correct。If we set our collision to。Yeah， so this is correct。

 so this is the problem。You know what， I'm gonna look just just quickly。For reference。

Where did I do that？えゴ？Yeah。It's pretty much what we did。It's actually exactly what we did。😊。

Maybe you got the。Iitial line is not constant。

![](img/886a749eaaa9f80910ebb04a9f92609c_700.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_701.png)

Mus。3，60，3，60。

![](img/886a749eaaa9f80910ebb04a9f92609c_703.png)

Yeah， this is like super weird。Com on。Red。To， maybe this is wrong。You know。

 I think we haven't guessed this is Ron。I'm doing， let's say if we are 90。来。Yeah， this is wrong。

The angle， divided by。180 note。You by pi times 180。90 times 180。系 very pie。No， Reg to degree。

 So if we are pi。

![](img/886a749eaaa9f80910ebb04a9f92609c_705.png)

Yeah， okay。Okay， so the problem was， Im pretty sure， yeah，-90。 Yes， I think we are perfect now，90。😊。



![](img/886a749eaaa9f80910ebb04a9f92609c_707.png)

Problem was our。Yeah。

![](img/886a749eaaa9f80910ebb04a9f92609c_709.png)

Okay， look at that。So the problem was really our。那。Degrees to ra。 We did that super fast。

 and we actually didn't think about it。There you go。Les of the day， don't do things fast。

 especially when you're retired。

![](img/886a749eaaa9f80910ebb04a9f92609c_711.png)

Let's go back to normal， let's see far square keeps track our ball， it does。

And our particle trailer looks perfect。Now， this is way cooler， I think。



![](img/886a749eaaa9f80910ebb04a9f92609c_713.png)

Yeah。Really， really cool。 So let's。😊，We're almost done， let's just finish the exp。

We do a random rotation， and we do。诶。D B scale。嗯。

![](img/886a749eaaa9f80910ebb04a9f92609c_715.png)

Yeah， no， I think we are correct。In fact， but our life is too short。



![](img/886a749eaaa9f80910ebb04a9f92609c_717.png)

Yeah， that's a little bit of life。In the explosion。Yeah， so。Yeah。This is way too short。

Let's do point。3。Yeah， think。

![](img/886a749eaaa9f80910ebb04a9f92609c_719.png)

Okay。Nice。And maybe this explore the。Maybe this explosion shouldn't have rotation or any rotation。

I don't know， let's see how this looks in the other levels。In fact， I normally see the wall。

I think the wall particle should be white as well。

![](img/886a749eaaa9f80910ebb04a9f92609c_721.png)

Yeah， let's see the wall particle。 So ball。あとば。If we hit。Respon。Starttop doing the warm color。

 Let's do light。O以。Yeah。And this also should be a little。Are you using。

To compile your code individual the visual suit， I'm just using the visual studio。

I initialized forcodeder with the Vi Studio batch files so I can do like CL to compile and then I'm going to press out and I run this a build batch file that runs the compiler so。

For a code for text editing， use your Studio to compile batch file and your your Studio to run and debug and anything like that。



![](img/886a749eaaa9f80910ebb04a9f92609c_723.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_724.png)

Okay， yeah。Okay， I think we can call that a success。Although it wasn't a very quick success。

 but we're not looking to to do again quickly in case you haven't tell， couldn't tell， right。

 we're looking to do a game and learn a lot。And I think today we learned a lot I'm going to review the code just yesterday。



![](img/886a749eaaa9f80910ebb04a9f92609c_726.png)

Today we learned a lot we did mostly。Let's do the。Reing。Mostly this guy。

Which is the draw transparent rotate wreck。So we build up our rotation matrix， set up erect。

Multiply the rotation matrix， change back to the aspect ratio。And。Apply that， got the pixel bounds。

And then we did the doc product projection。So。

![](img/886a749eaaa9f80910ebb04a9f92609c_728.png)

Yeah， I would say。We had a good victory today， I can even go back to my to do。



![](img/886a749eaaa9f80910ebb04a9f92609c_730.png)

And we move rotator bags next time I'm going to do bitns。

 which now that we started doing this kind of stuff shouldn't be too hard， but I know。

 every time I say that's not going to be hard， it's hard it's maybe I gonna say be super hard I know。



![](img/886a749eaaa9f80910ebb04a9f92609c_732.png)

That it's going to be easy。 Let's just see how everything looks。The is a aircraft。Awesome。😊，Doude。

These guys are super cool。啊。Super cool。Yeah， these particles effects are really cool。

I think the size of the particle should be influenced by the size of block。See。

 because these are probably too big and these are probably going to be huge， right？Yeah。



![](img/886a749eaaa9f80910ebb04a9f92609c_734.png)

So， I'm going to。Spawn explosion。We have a base size， so。Explion， whenever the block is destroyed。

We're going to do。Yeah， let's get the block half size。



![](img/886a749eaaa9f80910ebb04a9f92609c_736.png)

Let's see。

![](img/886a749eaaa9f80910ebb04a9f92609c_738.png)

何ち啊。I think I put that in the wrong argument。诶。Deep P scale based size， so。

The D P scale is looking And this is the base size。 So it's going to be block。Have sides。

Maybe I should do like。And have size X。

![](img/886a749eaaa9f80910ebb04a9f92609c_740.png)

Yes， thank for the stream。 I was a very fun stream。 It was kind of a。😊，Hard on my brain。Yeah。

 I maybe I should divide it by tours。

![](img/886a749eaaa9f80910ebb04a9f92609c_742.png)

This was the perfect size。So instead of， maybe I'll just get the Y。



![](img/886a749eaaa9f80910ebb04a9f92609c_744.png)

Let's see， so it was pretty fun。It' was great that we got to working to a great point。

 I think I really liked。Po got。Tms of the rendering。Yeah I maybe it's a bit too big still。

 let's see these guys。继续。Now， that's pretty cool。How in for controls。嗯。I don't know。

 Maybe I'm going to have to hard code。你啊。The particle size because I'm feeling at this。Too small。

Oh thank God it， I was saved。An invincibility。嗯。I don't know。

 I think we're going to keep it like this for a while。



![](img/886a749eaaa9f80910ebb04a9f92609c_746.png)

Yeah。Okay， so I'm going to post。The game and the source called onIio， so if you come to dNzd。h。o。

 you can download them both for free， just click on this link， first game。



![](img/886a749eaaa9f80910ebb04a9f92609c_748.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_749.png)

And then you can come here and download each day of sorry with， so you can download the first day。



![](img/886a749eaaa9f80910ebb04a9f92609c_751.png)

And all the way through today， which is I'm going to post now。

And you can watch the whole thing on YouTube。So if you go ahead and watch from the very first episode。

Then we started with a blank file all the way to today。

You'll be able to see the whole process airline of the code being typed。



![](img/886a749eaaa9f80910ebb04a9f92609c_753.png)

So yeah， that's it。 I hope you enjoyed this drink and also learned， I learned a lot。 So that was。

 that was pretty cool。 and hopefully。😊，By next time we'll start expanding the render even more by adding Biap support。

 then we can make like a Binap for the power up， which is going to be great for the gameplay as well。

So。Subscribe to your YouTube channel as well， thank you Yeah。

 please do the YouTube channel is Dan the YouTubebecom slash Dan Z Dan。



![](img/886a749eaaa9f80910ebb04a9f92609c_755.png)

Can't post the link here， just make it easier。And。Yeah， and'm going to post all sorts of stuff。

 I'm doing like these highlights as well。 I don't know that's pretty cool， but it was a lot of work。

😊，And also getting some clips。So。So thank you guys， Al subscribed Thanks man next time。

 which I think is going to be tomorrow， probably at the same time， maybe a little bit earlier。

 not sure。We are going to be back to do some bitM。And hope it's going to be a little bit smoother。

 but who knows， and maybe then we can do some sub picture sub pixel of accurate brainry。



![](img/886a749eaaa9f80910ebb04a9f92609c_757.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_758.png)

I don't know， I mean， we， I don't think we need that for the for the particles because it's super fast。

 but for the ball and the player。I think that's going to be desirable。Yeah。



![](img/886a749eaaa9f80910ebb04a9f92609c_760.png)

Probably。Okay， so thank you guys for watching and I'll see you next time， cheers。



![](img/886a749eaaa9f80910ebb04a9f92609c_762.png)