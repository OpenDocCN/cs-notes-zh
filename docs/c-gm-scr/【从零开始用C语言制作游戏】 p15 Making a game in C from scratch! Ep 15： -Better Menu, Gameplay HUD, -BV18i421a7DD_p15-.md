# 【从零开始用C语言制作游戏】 p15 Making a game in C from scratch! Ep 15： -Better Menu, Gameplay HUD, -BV18i421a7DD_p15-

Hello everybody welcome to this new live stream where we're creating an entire game in from scratch。

 This is episode 15 of our series and the game is coming a long way。

 I can actually say that it's almost a good game Well it's pretty much a good game I think we have a lot of polish to do although it's a simple game but I think it's getting to a nice point we have a lot of polish to do still and a lot of gameplay increments as' for that way。

 but it's coming along pretty nicely。😊。

![](img/1850b42de83cdf80b178739039962045_1.png)

If you haven't seen how the game is so far。

![](img/1850b42de83cdf80b178739039962045_3.png)

🎼です。🎼幸です。あや。So we've implemented a main menu last time around， well， I think was the stream for that。

And we have like the basic breakout idea， so that's what we did。

 we added some nice sound effects to go along with our animations。

Now our particles and things like that。呃。Yeah。ゆジ。Heい。



![](img/1850b42de83cdf80b178739039962045_5.png)

Okay， so that's oh， but that's the first one and the second level has power ups and power downs which were of the first ideas that you guys had on screen。



![](img/1850b42de83cdf80b178739039962045_7.png)

And then we added that。So we could expand the gameplay。that's pretty cool。And after that。

 we started doing the crazy game of was like P。And space invades。

 so that's the point where we are now， I think we're pretty solid in terms of gameplay。

I'm really enjoying it so far。呃。Yeah， I think it's pretty nice。

 but we still have a little more stuff to do like content， so we have to do more levels。

 also have to improve the gameplay， things like that。



![](img/1850b42de83cdf80b178739039962045_9.png)

Okay， if you want to follow along， you can download the game。



![](img/1850b42de83cdf80b178739039962045_11.png)

On HO， which is Dan， say Dan。hi。o， you can come here at the break Arcade Game out。



![](img/1850b42de83cdf80b178739039962045_13.png)

You can download the executable for last time around， last episode， as well as the source code。



![](img/1850b42de83cdf80b178739039962045_15.png)

If you haven't watched sourceur code， you can go to my YouTube channel and I really recommend to subscribe to my YouTube channel because there are a lot of cool stuff coming on。

 I think。I have some great ideas these past few days on what to do on the YouTube channel because this game pretty much come into a close。

 we should have and I guess like1 more streams。Something like that so we could ship the game at 25 so after that I have some pretty cool ideas of what to do next so you can pretty much subscribe to see all the changes and here in the YouTube channel you can see all the episodes from the very first one where we started with the blank file and we typed everything on stream so you can watch the whole process。

Everything， I don't know。 There were a lot of stuff from rendering to collision to the gameplay to like the game field improvements。

 animation and particle systems and juic net and。The graphicras and rotated rectangles and bitmap support。

 audio and parallel， all sorts of great stuff menu。 We did all of that stuff。😊。

And you can see the whole thing and learn hopefully， but now let's improve the game。

I have made some notes。

![](img/1850b42de83cdf80b178739039962045_17.png)

So I'm going to just to load the project here in far quarter I made some notes of what to do based on I played the game a little bit。

So啊。Yeah， we had the collision problem last stream。

 and we're going to fix these guys hopefully quickly so we can focus on the UI gonna make a better menu。

 I've had some pretty quiet ideas for the menu。😊，Then we can do。

We can show the timers and we can improve the UI， the pause menu， things like that。

Maybe we can improve the levels as well。 And if there's time and energy left。

 we can start doing the other RK games because we did P， and we did。😊，We do spa invadeters。

 maybe we can do ts。

![](img/1850b42de83cdf80b178739039962045_19.png)

Okay， now one of the things that I wanted to do， which was just a small cleanup thing。

Not sure how well this has been out。Here， but I want the forest field。To be at a very background。



![](img/1850b42de83cdf80b178739039962045_21.png)

Yeah， see how the power ups go behind the force field and it makes a little harder to see especially the power downs。

 so that's what I'm going to change should be pretty easy so I have the force。P油。😊，Yeah。

 and like here I draw the first field。 I surely draw that。Before the power ups。

 let's see where I draw the power ups。P blocks here。So， it should be。Yeah， should be around。

Really up there， so。Yeah。It' gonna， I'm gonna remove。Let's see， the。Forse。Let's take that out。

Oh yeah， we did this thing about invinsibility， yeah。It whole thing。Copy that。Let's go to the。Power。

Block， let's see。 here。 Here's where we render。The par blocks， correct， yeah。And the before。Well。

 let's do the first thing。Do this。 And let's call that。Forest field。Mnerity。

And this is the force field， I am not going to decre invisibility at。And this is the subdixel。Yeah。😊。

Okay， our still no need to do that as the player render。 I think this is good to go。

What else And okay， so this is the force field effect， let's remove it from here then。

 so I need to do this。No need to do。Let's see if we are in a good place。



![](img/1850b42de83cdf80b178739039962045_23.png)

You know， I'm going to turn your volume down and I'm going to turn my speakers up so it's going to be the most pleasant thing。



![](img/1850b42de83cdf80b178739039962045_25.png)

F you guys。Let's just go out a little bit something maybe I can turn them both on。



![](img/1850b42de83cdf80b178739039962045_27.png)

Yeah， I think it's not and up so you guys don't mind。I have my speakers on。



![](img/1850b42de83cdf80b178739039962045_29.png)

Yeah， just a little bit of sound。🎼ケ soラs see。

![](img/1850b42de83cdf80b178739039962045_31.png)

Okay， so looks great。7月8的。O， Sir。I couldn't actually see。

See how the productss are on top of the course field so first mission accomplished that was easy enough。



![](img/1850b42de83cdf80b178739039962045_33.png)

Change the sound signed and music names。 Okay， so yeah， that's more of like an organizational thing。

In the data folder， I put everything on the side effects， but I didn't actually put the sign。

And the music， So I'm going to put the sign here。All that sign。Sign。We will be some effects。3。😊。

And I can delete this guy。And then， oh， we did sexis last time， that was pretty cool。诶。In the music。

 I created this V02 for the music， I'm going to delete the old music。And I'm going to。

Just rename the new music。It's not different， not much different， just a little experiment。

 I don't know if you guys will be able to hear that。Yeah。

It' a little bit faster before it goes to the。🎼です。

![](img/1850b42de83cdf80b178739039962045_35.png)

Yeah， like this。Well， it's pretty similar。I think I like this one better。

 so this name is going to be the same。And also created a logo for the game。



![](img/1850b42de83cdf80b178739039962045_37.png)

I'm not sure this is the final version， but we'll use this version for now。

 we're going and come that in the main menu today， so this is the logo。

I made two variations like light and the dark great Arcade games out。



![](img/1850b42de83cdf80b178739039962045_39.png)

I think that's a pretty bad name， but what can you do？I don' to worry too much about that。

 it's just learning projects for fun。So it would change the sound and music names。🎼Whistle too loud。

 Yeah， I think the whistle reaches the ball。

![](img/1850b42de83cdf80b178739039962045_41.png)

It's way too loud。

![](img/1850b42de83cdf80b178739039962045_43.png)

And in fact。I don't think I need to put the whistle on the。It's called ball sound。Yeah。

 I don't think I'm going to add the whistle to the other balls。

I think this would be just for the first ball。And the other balls will have the come sound。

But not the。So。Yeah， it's just said。Like this， I' called that。宝我箱。

And we have like place down for the ball sounds set the volume to zero set the fade speed pretty set the source。

And then we add the comment loop。Okay， and now， in the， in the sound。Well。Buse。I that sound。大量能来。

Yeah， reset ball said thats  zero。And here， when we reset the ball， gets that of next available ball。

Where do we update here， I think？Yeah。So if we're going up， going to put that a little bit。

We bottom a little bit down like 0。08， and we are going down。I think that distance factor。

 which is closer to get， we can probably。Mly that by something little。Less。

And then maybe this guy can be a little less as well， maybe this guy。Hい。This is zero right。



![](img/1850b42de83cdf80b178739039962045_45.png)

Okay， let's stick on this。

![](img/1850b42de83cdf80b178739039962045_47.png)

Yeah， I think that's okay。Wasn't too big of a difference， but。We try that。

Let me try listening a little bit louder。

![](img/1850b42de83cdf80b178739039962045_49.png)

![](img/1850b42de83cdf80b178739039962045_50.png)

I like that。Turnout volume back up。Okay。

![](img/1850b42de83cdf80b178739039962045_52.png)

They were so loud and there is some case where the triplerupal shots continued to play after destroyed when there are comets。



![](img/1850b42de83cdf80b178739039962045_54.png)

But I think we just removed the whistle from the triple shot。



![](img/1850b42de83cdf80b178739039962045_56.png)

That might actually just have been solved。The whistle kept playing after。s got a car。Try that again。

I know， I kind of miss the whistle sound for the triple shot。

I think we're going to undo what I just did。

![](img/1850b42de83cdf80b178739039962045_58.png)

と。Yeah， I think I might actually。嗯嗯。😊，IThink am I actually just。Keep this guy。For the first three。

Yeah， this is this is hard。啊。Well0。To high。

![](img/1850b42de83cdf80b178739039962045_60.png)

Well。Sure that was a great idea okay。All you can do space es。I think we'll have a better chance。

super was shop。し。第二。we do have to hit the comics。给他们でき。Let's try that again。



![](img/1850b42de83cdf80b178739039962045_62.png)

Yeah， see how the whistle still playing， but I think that that was okay for the whistle sound and this condition。

 but yeah， there's some case where the tripleple shot continued to play after the。

At some point when the ball was destroyed。嗯。Yeah， when we do like zerostruct。

Let's see if you do zero for the ball。That's the only case。Let's try。Let's try。Well。

Kind of lost my trainer thought here。 I'm trying to look where the the ball。I dot sound。Okay。

 so how we do reset ball。And process ball。Okay， so we0 the volume。Prossible in D PI down。

And it was destroyed on D P Y down。I suppose that's maybe called every time process。Process ball。Oh。

 this is only called。This is only called when we do the block condition。 But if we exit through the。

So the wall condition lets to wall。是。Play a role。No， let's try ball wall collision。

W reached end of the arena。Reset。No， this is the good one。Erease the ball size。

Process involving with D P I done。 Yeah， we do this。 So I'm not sure。Why we still hear the sound？

Let's put a break point。In process whileing DPI down。



![](img/1850b42de83cdf80b178739039962045_64.png)

And let's see if you gets the property called。

![](img/1850b42de83cdf80b178739039962045_66.png)

Oh， it's because of the comments sound。Let's see when we get like。包。卡了。Yeah， when we render the ball。

 we're not supposed to render the ball right at this point。我未。If you have a。AComt sound。Let's also。

Not sure I'm going to for a breakpoint。Here as well。



![](img/1850b42de83cdf80b178739039962045_68.png)

Well， we can check that。来来起来去。诶。🎼Let's see the state on that break point。Okay。

 it's going to be called a lot。That's pretty we went here then。



![](img/1850b42de83cdf80b178739039962045_70.png)

Okay， so now。We are destroying one of the balls。

![](img/1850b42de83cdf80b178739039962045_72.png)

Yeah。And。Has a sound。 So we're going to set that volume to 0。And the comment。Sound to zero。

 and I said it's inactive all so。Possibly。

![](img/1850b42de83cdf80b178739039962045_74.png)

Yeah， I said that to enact so I think the problem is maybe cold order。So。If we， let's say。

 render balls no。

![](img/1850b42de83cdf80b178739039962045_76.png)

I don't know。知。facting not pause the game real quick here。Yeah。

 our own pause is not working properly， let's just fix that because it's nice to be able to pause game。



![](img/1850b42de83cdf80b178739039962045_78.png)

So啊。When we set， like， mouse。玩。Mouse。So we went and reppo the game。We changed the like mouse。

And then we set it to paused and unpaused。嗯。Okay， let's see lock。Set cursor position。

 here we reset it。On the activate app。It's also set。Yeah， you know， instead of doing like this。

 I'm going to do like。If。We are now paused。Okay， just say like。The like mouses。えコス。



![](img/1850b42de83cdf80b178739039962045_80.png)

And I so if we are paused， we shouldn't be locked。I see。So I lot。Okay。we fixed that problem。Yeah。

So I can definitely hear the whistle。I'm going to turn your guys volume down just so you don't go crazy。

I think I can hear the whistle， so I've got a put of break point somewhere。And。

Let's see things like balls。So flags are set to two。That's okay， so they're not active。

 let's see the sound。The target volume is on for some reason。嗯。所以啊。Let see sound。Yeah。

 theyre both on。

![](img/1850b42de83cdf80b178739039962045_82.png)

![](img/1850b42de83cdf80b178739039962045_83.png)

You of me put a break point。On。On the balls， let's see， on a target。

 a data break point here on the balls。1。比较强。Dot sound。那我。Sound out。哎你好。We do death for both of them？

Playing sound has no number target volume。阿诗。Try this volume and I spell that around。Target。好。O。

一直 point。Yeah。Okay， and let's also do that for the other one。Balls 2。ok，下次。Okay。we see the culprit。

So。Oh， this is ball too。Yeah。Let's see which ball is that？No， because we。Yeah。

 we respond to more balls。Can now we hit the end， we should set that to0。

So let's see you set the charging volume to zero。Let see。Sound。Tur volume to zero。



![](img/1850b42de83cdf80b178739039962045_85.png)

Okay， let's keep going。And this is that see which ball is that？So we set the target volume back。

 Yeah， so this is probably the same ball。So which one is that？Flas 2。Oh， this is this ball。

 so this is correct。I think。This ball is still active。 No， if it's flexs too， it's not active。

So we should reveal that we collided with the player， we collided with the wall。Yeah。

 so this is the problem if we collided with the wall。And we process the ball DPS2， you know。

 not do the。This should like break。Out of this loop， I think。Yeah， so we're rely 400。 Yeah。

 I think we found a problem。 We're only 400。Of the game。And if we collide either with the left。

 the right or the top。Thats do like that。Arena。We can。

 we can pretty much not consider the game over because we are。Well。

No what I'm going to do this a little deeper I' going to do like。Update sound。Yeah。

 and then at these， these this point。Go set that big sound too。Actually。

 the update false is going to be if the update sounds going to be if I am active or not。

 so if I am active， I'm going to update the sound if I am not active。

 I'm not going to update the sound。And this， I really don't care。I also don't care。 Yeah。

 So if updates sound。

![](img/1850b42de83cdf80b178739039962045_87.png)

And so。I think they'll fix it， let's take a listen。



![](img/1850b42de83cdf80b178739039962045_89.png)

So we need to see the case。Yes是。Okay， sound was a no pointer。Which sound do we try to play？

Redirectect sound。Okay。嗯。I don't know what happened。 What was the earth。Sound was no pointer。

 or it doesn't say it's a no pointer。Maybe that's a threading problem。Okay， that's weird。Well。

 let's put an assert。

![](img/1850b42de83cdf80b178739039962045_91.png)

At到 audio say。This point。That's a search。Sound。So。And。Were the same here and out。

We don't have a sound。欲しいよ。

![](img/1850b42de83cdf80b178739039962045_93.png)

That's weird。Let's try that。Yeah， I think that fixed it。That sounds pretty cool。

 what do you guys think？

![](img/1850b42de83cdf80b178739039962045_95.png)

Okay， I like that， so we fixed that problem as well。Collion bug。 There was a collision bug。

 I don't know if you guys remember。 I even yeah， this at this point of last stream。

 There were a weird collision bug。 And I was reviewing the code just to make sure that it wasn't weird。

And I think we have like a old thing。 I don't remember exactly why we put the。

Sa about collisionition。Blld vision test fee。And we actually even put a comment like we weren't sure where to put this。

 I think I'm going to remove this IDR entirely。And a collision。And we'll do like。

 we're going to use the desired key whenever we need to try to collide the ball。

So this case we're to use the bow desired key。Let's see what else let's do like validationation。Test。

第一个是。You can just review where where it's calling like。Yeah，Okay。Yeah， I think there'll be a just。

Push the window。

![](img/1850b42de83cdf80b178739039962045_97.png)

Open。I think there'll be a better behavior because theyre old collision P。



![](img/1850b42de83cdf80b178739039962045_99.png)

🎼Was mostly。Something that out。We' were doing when we were less sure。

 whether we're going to sweep or not。I think it's going to be a more precise provision。

🎼Need check first level。I not mistaken it was like near the wall。

But we're going to have to leave that Nicole for a while。

Just to see whether or not this is going to work。This looks pretty solid。Okay。And if you。

Come across any weird bugs， we can think about that。We are getting to a pretty solid game plan。



![](img/1850b42de83cdf80b178739039962045_101.png)

Yeah， okay。Now reject the collision and remove the but and' going to remove。Yeah。

 I took that decision like when I was thinking about what levels to do。

 like we had some market email this month said snake， we can probably do a snake。

As an acade game for a breakout。We had this two ball level that we played around with。

Let me just see if I can still play it， I'm not sure。Stay。



![](img/1850b42de83cdf80b178739039962045_103.png)

Let's see if I can play the stadium or maybe we broke that for some reason。Yeah。Looks pretty cool。

 I think。But the idea is we have two balls。And the blue ball only destroy blue blocks and the orange ball only destroys orange blocks。

The problem was。It wasn't like two random sea at this point。

It was hard and we tried putting it out at the ball speed。



![](img/1850b42de83cdf80b178739039962045_105.png)

But see at some point yeah， that was pretty much impossible see so and I think it goes outside from the base idea of the game enough that I think we should just cut that so I have some ideas of how we should go if we were to reconsider。

These guys。But。Yeah。Not gonna well。Maybe we could do like the blocks randomly spa thing。

By the twovol level。I'm going to cut that so。I cut out the rival system。Can we already did that。

 let's move some of the power up still do the live system。呃。So yeah， review。

 they're not going to actually do the tool ball level。

 we're going to focus more on these acade game ideas。

We're also going to remove the functionality of it， not just the。Not just the like。

F level name and stuff。So。We're going to remove this guy。

And I'm also going to remove like yeah the ripple collar。See rival。

 move the ball rival and the ball fixed speed。So。Fos fixed speed。Well， I actually。

 everybody fixed speed， right， Yeah， so this should be the correct behavior。Again。

 this would be the correct behavior。Not going to worry about that anymore。

I'm not going to worry about that。We going move that as a parameter for the block block。

parameter let's remove that Ill be see blur。zero parameter？The one， look at two。The zero effect。

 this is the chanceor and with the chance。Also。We're back just having all the levels in。Okay。

 let's see what else。If we are rival， A， if we are rival B else， so。



![](img/1850b42de83cdf80b178739039962045_107.png)

This goes just to a single ball drawing。 Okay， I see。



![](img/1850b42de83cdf80b178739039962045_109.png)

Okay， now remove that functionality。I think。best call now this is just some ideas for the menu and that's what we're going to start doing now。

Let's improve the menu， and。Because when we implemented it？

It was just like a quick idea just to know see。

![](img/1850b42de83cdf80b178739039962045_111.png)

How we work to interact。The guys， but we actually want level names out of these guys as well I was like a logo and like created that stuff。



![](img/1850b42de83cdf80b178739039962045_113.png)

![](img/1850b42de83cdf80b178739039962045_114.png)

So。Yeah， let's see。 Let's improve that。 So we have the menu file。And we can do like。

Simpr stuff like draw bimap。And let's also load。Loode。骗题。It's also a load light。The logogo。Light。

And a little dark。I see the names。It's logo light and logo dark。Did。Over light。老个。D。Okay。

 so we let do like this map。而。Okay， and let's just draw one of them just to see。

And it takes a position。Let's do zero。钱。😊，Size。Let's see the logo aspect。

 I'm not even sure what aspect I say that。Because our Raer doesn't care about。

Whether it's a power of two or not，This guy。ありたで。嗯。😊，Ptty weird aspect。Well。

 I don't think I'm going to care much I'm going like to。So if we do 10。你 the why。We'll do 20。3。Okay。

 so this the size， let's see what else。And this is1。I was a rotation， I think。Now， let let me see。

What the actual parameters are so we draw。Oh just the auto multiplier， so I'm going to pass one。

Syntax error。

![](img/1850b42de83cdf80b178739039962045_116.png)

Okay， that's it。

![](img/1850b42de83cdf80b178739039962045_118.png)

🎼Ohお nice！

![](img/1850b42de83cdf80b178739039962045_120.png)

Like that。Go do a little bit bigger。 I'm going to do chance。Dot 15 times 3， maybe0，30 dot 45。And。Oh。

 actually， it's 2 to 15。Times 36 and 60 for。

![](img/1850b42de83cdf80b178739039962045_122.png)

I see。 maybe too big。Yeah， well let's make like this guy types。



![](img/1850b42de83cdf80b178739039962045_124.png)

w five。53。8。実て。Let' see， this size。Yeah， still too big。确实。😊，I think2的。



![](img/1850b42de83cdf80b178739039962045_126.png)

Yeah， 20 was okay。

![](img/1850b42de83cdf80b178739039962045_128.png)

And let's move that up， you know what， I want to do something different。Well， no。

s let's do just like one step at a time。Just got a little bit up。Maybe a little bit more。



![](img/1850b42de83cdf80b178739039962045_130.png)

Okay。

![](img/1850b42de83cdf80b178739039962045_132.png)

And let's move these guys down。This guys。

![](img/1850b42de83cdf80b178739039962045_134.png)

Next。See。Okay， way better。

![](img/1850b42de83cdf80b178739039962045_136.png)

🎼呃。Start of doing like black。

![](img/1850b42de83cdf80b178739039962045_138.png)

Let's do。greenreen kind of color， a dark green。

![](img/1850b42de83cdf80b178739039962045_140.png)

Let's do like 0，0。

![](img/1850b42de83cdf80b178739039962045_142.png)

33 want one。🎼違っ大学。

![](img/1850b42de83cdf80b178739039962045_144.png)

Is too green。I should call 1，0，5。

![](img/1850b42de83cdf80b178739039962045_146.png)

![](img/1850b42de83cdf80b178739039962045_147.png)

Nice， but we are going to change the logo， right， so we are going to do like。

We have the current time。プ like。Let's do like a。Music。呃。A note。Eth note， timer， T。

And then wecrd the is milk timer。买 the地T。And if the music a't no timer， let's call a like。music。

Let's define find a music tempo。It's 1，30。So， if the。Music is no tea。Is greater or equal than。

The music To that beats for a minute。But。W multily by two because we have like these guys and this is in seconds。

So we're going to do 60 divided by that。 let's see if that makes sense。If we have like a temp of 120。

 let's say it 65 by 120， we have。0。5。Yeah， one beat every half a second。For a quarter note。



![](img/1850b42de83cdf80b178739039962045_149.png)

But this is a eighth note。 So it's going to be like。sixty。Divided by6 2，40， yeah。



![](img/1850b42de83cdf80b178739039962045_151.png)

This looks correct。And if we are， we are going to。Do you like。看到是。A quarter。This is an eight note。A。



![](img/1850b42de83cdf80b178739039962045_153.png)

Let me just see how that's built8 B。😊。

![](img/1850b42de83cdf80b178739039962045_155.png)

No。呃。

![](img/1850b42de83cdf80b178739039962045_157.png)

Yeah， is that correct？Yeah， that was great。So in the eighth note。E note。And our time。Okay。

 let's do it like 60。Bye bye。There's a temple times two。So if we are greater than then we subtract。

一条产。And now I'm going to switch。And they like， use light。老公。Equals。you like。Okay， and then like。

 if use light logo。Else。I going do the dark。Okay， and let's see how that looks。Conferation。



![](img/1850b42de83cdf80b178739039962045_159.png)

F 32， let's see。

![](img/1850b42de83cdf80b178739039962045_161.png)

I't know if felt like that。

![](img/1850b42de83cdf80b178739039962045_163.png)

What do you guys think？I'm not sure。🎼お？

![](img/1850b42de83cdf80b178739039962045_165.png)

![](img/1850b42de83cdf80b178739039962045_166.png)

Maybe I should actually do like a。I was doing music。6。Teenth note time。I'm going to， like， a。

And we're going to do like a six。天。Note count。So， this one is。6。那7。AndSa。Okay， but every 16th note。

Go going to criminal an account。呃。And if they count。Is three dental switch。Else， if it's 4。

're going to switch again。And we're going to set count。Musics。6。16。I think that's correct。

Conver undeclarated fire 6。8 notes is going to be the 16 note time。No time。Count， it's this 16。



![](img/1850b42de83cdf80b178739039962045_168.png)

飞了。😊。

![](img/1850b42de83cdf80b178739039962045_170.png)

But I may actually switch from the light of the dark。Well， she just。



![](img/1850b42de83cdf80b178739039962045_172.png)

Shart using like。I think that's a little bad。But there are a few problems。Like if you go back。



![](img/1850b42de83cdf80b178739039962045_174.png)

See you're not sink anymore， because this shouldn't be actually dependent on the。

Shouldn't actually be dependent on the menu？嗯。So maybe in the game update。

We update stuff like a date。menu。You can do like， two。Well要。

I'm just going to put this whole thing there。I'm going to put a comment。

This is here to make sure the。The timer is incremented， even if。那。ね油。But。Does。



![](img/1850b42de83cdf80b178739039962045_176.png)

ok。Now， let's see if we are seat。

![](img/1850b42de83cdf80b178739039962045_178.png)

![](img/1850b42de83cdf80b178739039962045_179.png)

Okay。

![](img/1850b42de83cdf80b178739039962045_181.png)

I think this is pretty cool。啊。Or maybe it's just kind of。Kind of weird。

But another thing we want to do for the menu。

![](img/1850b42de83cdf80b178739039962045_183.png)

You actually have text on a game。And I thought about that for a while。And the thing is。

I'm pretty sure I want to be able to draw a text like。Like the level name。

So I speak about just import a font。But in know what， this tax looks pretty good。

This kind of text because it looks like the blocks， right？

🎼But I want to animate each black color individually。So I am thinking I am going to implementment。

A font。By hand， just like we do with the text。Just so we can。Just so we can， you know。

 animate this guy incrementally， you know？There's going to be a bit of work。

 but I think it all bit turn out but so I have made some notes。



![](img/1850b42de83cdf80b178739039962045_185.png)

On the space I for the load boom， so the blocks are 1。6 aspect horizontal， and they have 0。

4 of spacing。This is relative to like one height of the black。

So let's add the ability to draw text on the menu， right？And yeah， let's do like。

This is like the update。And we're going to do the text。ok。😊。

And the way I think I'm going to do this is actually have a。I'm going to do something like this。

Let'd say I'm going to dry an a so。It's going to be。



![](img/1850b42de83cdf80b178739039962045_187.png)

I already have a， so let's see how I do that。So it's like blank。



![](img/1850b42de83cdf80b178739039962045_189.png)

Two guys blank。Right， then this is like this。Then this like。Then this is like this。

Three more thing thing we did the space invade， if we go to the level。And favor。Cre be， see。

We specified that one ASI， and then we parsed。

![](img/1850b42de83cdf80b178739039962045_191.png)

That text， So I think that's what I'm going to do。

![](img/1850b42de83cdf80b178739039962045_193.png)

An two and then。So it's like two of these guys。And period out these guys。So。

This is what I think when I do。 So this is a sharp pointer， that's called that letters。

A letter table。Al。But this is actually going to be a two dimensional array。

And this guy is the first one。And we're going to do like A and B。That其 you方排的。To many subs。

Too many initializerrs， well。Let's try doing that in the interiors just so。If you do， like。It。

R equals。This works， right？You're like this， this is substitute because for each guy。

 we have an array。

![](img/1850b42de83cdf80b178739039962045_195.png)

Like this correct？No嗯。It's called that C。2。嗯咩。channel array。也喜环。



![](img/1850b42de83cdf80b178739039962045_197.png)

![](img/1850b42de83cdf80b178739039962045_198.png)

Okay， yeah， we don't。Yeah， we have to tell like。This guy's gonna be。对。This is going be like one， two。

 three， four， five， six， seven， seven。感 see。Okay。So this is the basic idea。And。



![](img/1850b42de83cdf80b178739039962045_200.png)

🎼Not sure how long it's going to take for us to do， like most letters。



![](img/1850b42de83cdf80b178739039962045_202.png)

Like this should be enough， let's just test and see like here。Drropaw text。

Maybe this would be the render。D I's going to take。Tex。A。And the size。And I color。

Now let's just draw a rank。O， so the P will be P。I do， like， half size。It's gonna be。Size。Size。

K一该那个就P。Havelf size。Color。Yeah， and then here in the menu， let's draw。Let's draw something。Test。Okay。

 let's draw that。0。I' like to do a10， the size 1。And the color， let's do pink。



![](img/1850b42de83cdf80b178739039962045_204.png)

爱。

![](img/1850b42de83cdf80b178739039962045_206.png)

Okay， now。What we want to do。Is to get the letter。So。4。He put text。At。Plus。We're going to do like。

Lettter。Maybe the letter table。At。Let's see。At。Minus。诶。20别了。A minus x。呃。Yeah。強よ。Is that correct。

 I think it is， that's just copyied from the invader guy because we already did that。So。Yes。

This is what we want to do。Ourrange requires a brace enclosed。你这来。This is it now。啊。Same thing， right。

 oh， but we。Yeah。So we're going to run， I'm going to hardcode this seven like。Text height。Tt tight。

And for the text height。We're going do like， text。We already have the act。Let's do like。Letter。At。

Okay， and then the ad will be this guy， and if it's not。We are going to spawn a rat。Okay。

 then we have。The size。Times 2。But we also wouldn't have to add the space， right？

And this is also the sizeine times2。And I'm going to save the original X。低一点的。Should be up here。

Letter table cases。Peter。Letter。He。Yeah。

![](img/1850b42de83cdf80b178739039962045_208.png)

Let's just see what we have， oh， we don't have a tax so we should crack yet。



![](img/1850b42de83cdf80b178739039962045_210.png)

Let's do A B， A B。

![](img/1850b42de83cdf80b178739039962045_212.png)

Is do AABP A。Just for fun。Okay， we still crash so let's。Let's see what we have。

We should be getting AABB A。At  zero zero going save the position and the half size。

Havelf size is huge right away。呃。The letter adds， so we're getting the first。Guy。This guy。Is yeah。

 it's space0， zero。 Yeah， it correct。Okay， so we're going to go for seven roles。

And this should be like。Space。That's the first row。Don't draw or just incraement。Wer。And we draw。

Now we should be at zero， so we go back to lines problematic Oh， no， this is correct though。

Andll go back。Then we。See， yeah， it is extract。See how we crash。Cash at I is 0。

And the letter at is B。The letter。It problematic， so。This guy is B。Well， a minus B。



![](img/1850b42de83cdf80b178739039962045_214.png)

Oh， it' minus one。So I guess we were right the first time。This guy。Minusで guy。



![](img/1850b42de83cdf80b178739039962045_216.png)

That's okay。Oh， nice， nice， nice， nice。 think we are gonna。😊。



![](img/1850b42de83cdf80b178739039962045_218.png)

Go to a nice。

![](img/1850b42de83cdf80b178739039962045_220.png)

Ptty cool， right， but we we shouldn't do this， we should just。😊，The spacing。

 that's what I mean by spacing。 So I'm going to add。The size。直接试间。Have size。

So this is going to be light。Thanks one。6。To the point4。This is actually be。你选择。Oh， sorry。

 we actually should。The X。The Y would be the original， right？Yeah， the would be de original。

 So it's just the other way。

![](img/1850b42de83cdf80b178739039962045_222.png)

🎼那。

![](img/1850b42de83cdf80b178739039962045_224.png)

Lets just go back to where we were because we're kind of working so we can understand it。Originnal。



![](img/1850b42de83cdf80b178739039962045_226.png)

7。😊，🎼Nイス。🎼まら。Andm going finish a letter。🎼Instead of changing the why。



![](img/1850b42de83cdf80b178739039962045_228.png)

I's just try to increment the X by。T X。Plus， equals。



![](img/1850b42de83cdf80b178739039962045_230.png)

This翻应个字。

![](img/1850b42de83cdf80b178739039962045_232.png)

Oh that's okay， yeah， we must do like。

![](img/1850b42de83cdf80b178739039962045_234.png)

Oh， we don't need to do this。啊。

![](img/1850b42de83cdf80b178739039962045_236.png)

い。Because this is at the end of every。So I guess this was correct。 Yeah， this was correct。

And I'm going to do this again， I have a little letter， which is like you。



![](img/1850b42de83cdf80b178739039962045_238.png)

![](img/1850b42de83cdf80b178739039962045_239.png)

And then we also change the original X to P。

![](img/1850b42de83cdf80b178739039962045_241.png)

![](img/1850b42de83cdf80b178739039962045_242.png)

Okay， but this should be plus。Yeah， and this should be like。If I is not。Text hide minds。



![](img/1850b42de83cdf80b178739039962045_244.png)

it's kind of a hack。

![](img/1850b42de83cdf80b178739039962045_246.png)

So this is bad。And we are also going to reset the why so。P dot Y， is's going to be the regional Y。C。

对。

![](img/1850b42de83cdf80b178739039962045_248.png)

Okay。

![](img/1850b42de83cdf80b178739039962045_250.png)

Nice。Then just go back to the game。

![](img/1850b42de83cdf80b178739039962045_252.png)

0。6 aspect， that's what we have。

![](img/1850b42de83cdf80b178739039962045_254.png)

But。Spaccing is not correct， spacing this guy。So。Yeah， we should add like size times 04。Oh， no。

 actually， it's size。Not 1。6。Space and times two。

![](img/1850b42de83cdf80b178739039962045_256.png)

Okay。

![](img/1850b42de83cdf80b178739039962045_258.png)

Is that correct？I think we have a hard code， this is going to be like one， two， three， four。4 guys。

So I'm just going to set the x to the original X。 I'm going to add。



![](img/1850b42de83cdf80b178739039962045_260.png)

Times 4。Fe。

![](img/1850b42de83cdf80b178739039962045_262.png)

This is weird。I want to offset， okay， so then I'm going to call that。Like， block offset。X。

And I'm going to do four of those。Block offset at X。



![](img/1850b42de83cdf80b178739039962045_264.png)

Okay。😊。

![](img/1850b42de83cdf80b178739039962045_266.png)

And also， going to。

![](img/1850b42de83cdf80b178739039962045_268.png)

So the first line is okay but。And we reset。

![](img/1850b42de83cdf80b178739039962045_270.png)

First， guys all wrong。Oh。呃，Got the other way around。 So I'm gonna set the P。🎼Y。

 the original x and the P P y original Y， and takes， okay， this is better。



![](img/1850b42de83cdf80b178739039962045_272.png)

It still hot that so。

![](img/1850b42de83cdf80b178739039962045_274.png)

But the space is not entirely correct yet。Block offset。Because they do have to add。These guys。



![](img/1850b42de83cdf80b178739039962045_276.png)

Right。

![](img/1850b42de83cdf80b178739039962045_278.png)

And should be。サイムスエ？Attheci。

![](img/1850b42de83cdf80b178739039962045_280.png)

Okay。

![](img/1850b42de83cdf80b178739039962045_282.png)

It's a little bit better。But this guy， which is the ladder spacing， should be。A bit more。

 think I didn't think I measureded that。

![](img/1850b42de83cdf80b178739039962045_284.png)

But if you do like dos size， maybe that should be enough。



![](img/1850b42de83cdf80b178739039962045_286.png)

I'm just going to。Time to do， I'm just going to eyeball that。



![](img/1850b42de83cdf80b178739039962045_288.png)

![](img/1850b42de83cdf80b178739039962045_289.png)

I think that's enough。Let's do a more decent call。

![](img/1850b42de83cdf80b178739039962045_291.png)

And I think we are off to a nice place。 Let's do a smaller size。 And let's see if we break or not。

 I don't think we should break。😊。

![](img/1850b42de83cdf80b178739039962045_293.png)

We don't。Awesome。😊，Awesome， awesome。🎼Just before we do。Just before we do the full。Animation thing。



![](img/1850b42de83cdf80b178739039962045_295.png)

I'm going to pass a array of colors here。We'm going to call like current。And I first called it。Okay。

😊，那就color。Equals colors。First call。So you like the next color。肚屁。嗯。Next color。

And whenever we finish a letter， which is here。I'm going to do the same thing。Get the next color。

And like， if max color is greater。Two or you go to the array count of colors。

Im Joe is going to set the next color。And want to do the same thing。

So now we should be able to patch a swan collar。Not sure this going to work， though， this syntax。

Like color， yeah。Yeah。😊，I'm to do like， array。嗯。Oh。

 I'll lets do the whole thing I'm going to pass like。Aray count。Al。Yeah。Then I'm going to do one。

As you来。So instead of doing the array count。And just。Do you like。Cot。Color count。Yeah， this like。

How we should。好的。How you do Step。I suppose。嗯。Oh， it because it's an inter that what the problem is。

Or， maybe recount。あです。Let's see if you can get like back to the array guide。Okay。

 maybe we can just pass the array， let's just see if this works。



![](img/1850b42de83cdf80b178739039962045_297.png)

![](img/1850b42de83cdf80b178739039962045_298.png)

Yeah， oh it's white。That's just trying to see something different。



![](img/1850b42de83cdf80b178739039962045_300.png)

![](img/1850b42de83cdf80b178739039962045_301.png)

Okay， this works now I're going to do the array thing。And let's try do the array count colors。



![](img/1850b42de83cdf80b178739039962045_303.png)

Aray count。P。Let's see。 what we had。

![](img/1850b42de83cdf80b178739039962045_305.png)

Yeah， well， it's just work。违章。这个呢就的。这' not whole point I think。Okay。

Now let's see what we have if we pass two colors。Let's do three college。



![](img/1850b42de83cdf80b178739039962045_307.png)

![](img/1850b42de83cdf80b178739039962045_308.png)

🎼啊。

![](img/1850b42de83cdf80b178739039962045_310.png)

🎼我要。That didn't work。That's not well kind of work， but that's not what we want。

 it's going to do like first color。And then。Next color is going to be the first color。And this。

Going to do the same thing as next color。 if is first color。

And then I'm going to change the next color。

![](img/1850b42de83cdf80b178739039962045_312.png)

Here。Okay， that's what we wanted。But that's not entirely correct。The A is correct。

First Ace correct F tech， Ace not。

![](img/1850b42de83cdf80b178739039962045_314.png)

嗯。

![](img/1850b42de83cdf80b178739039962045_316.png)

![](img/1850b42de83cdf80b178739039962045_317.png)

Oh， which Russell。Likeです。

![](img/1850b42de83cdf80b178739039962045_319.png)

![](img/1850b42de83cdf80b178739039962045_320.png)

Okay， this is perfect， I think so what we are going to do。We're going to do like。Color。Well。

We're going to do like。Menu text。Colors。Then I'm going to do the array con of the menu text colors and going to pass。

The the menu text。Haring。好了。可手。メニュー？Taxt colors。Manual tag starting colors。How was that？

Intertex starting color。Yeah。So this guy's going to be actually a 38 array。And。

Let me open Photoshop here so we can get the logo callers。



![](img/1850b42de83cdf80b178739039962045_322.png)

If you guys have any question， be sure to drop them on the chat。



![](img/1850b42de83cdf80b178739039962045_324.png)

And I'll do my best to answer them。Let's see。😊，That's。And these colors like。LetSo have this pink。快有。

啊。To this guy。So this bank， we did， this guy same thing。WellI suppose it is。No， yeah。

 it's not supposed to be so。It's a bit small problem。 then I'm going to see that on the logo。Okay。

Okay。And。Last one。O。Okay， let's see。 Now we're going to add。Let's do have since the 16th note。你啲诶。嗯。

So every 16th note。Plus plus。If menu starting color is greater or equal to the array count。

Many of text colors。Manual text， starting color。miss。



![](img/1850b42de83cdf80b178739039962045_326.png)

啊。

![](img/1850b42de83cdf80b178739039962045_328.png)

Nice， it's gonna be a fun menu， I think。I'm going to add these guys all over again。But。

Within third at order so。7。😊，I'm gonna add this guy。And want，80。I think I have 918 twice。0，8。A a 。

Yeah，P在。Okay。This one after the A80。And。A91，80。Then this guy。the D80。Then。48。A0。And then this guy。



![](img/1850b42de83cdf80b178739039962045_330.png)

Sure we could program that。I know they abuse。

![](img/1850b42de83cdf80b178739039962045_332.png)

Okay， there's a small bug。On everyone except the first letter。



![](img/1850b42de83cdf80b178739039962045_334.png)

🎼いや。I don't know， oh， that pause feature is really awesome， by the way。I don't know what happened。

 Let's see。What color is this。

![](img/1850b42de83cdf80b178739039962045_336.png)

Maybe 0， maybe1。

![](img/1850b42de83cdf80b178739039962045_338.png)

Maybe we ref you from the wrong place。嗯。Let's see。Color oh。The now， okay， the recount menu。

Tex colors。If we are greater than。The color account。Are equal to， yeah。So the next color to zero。

Yeah， this is wrong。Should be like this going to pre increment。The guy。

So should be shouldn't increment。This point。Mar tests got so I'm going to set first call then I'm going to increment in。

The color test。C， then fetch the color。Yeah， same thing。This will。



![](img/1850b42de83cdf80b178739039962045_340.png)

Better。Okayー。

![](img/1850b42de83cdf80b178739039962045_342.png)

Okay。That's pretty cool。 Do you guys think that's cool。 I think that'll be pretty cool。😊。

这 thing on的 menu。So what I am going to do is going to be pretty boring， but we have to do it。

 so let's do it is all the ladders。At least all that we care about。Which would be all of A， B， C， D。

 E， F，G， I see how long it would take just to them。So this would be the C。Now， that was。

Quicken enough。D， same thing as the B。But like this。TheE should be easy enough。系对来。点开。And the G。

 the G， let's see。And in the menu， let's test all of that。I do。



![](img/1850b42de83cdf80b178739039962045_344.png)

A。ABCDE。Nice。See， it's not that part AB，C， D E，FG。H。这。K H。

I'm not as familiar with the letters in English。😊，Okay， we have a small problem。

That we don't have a center。See， the T is not actually centered， do we have four。Ah， don't like that。

I think I'm just going to。

![](img/1850b42de83cdf80b178739039962045_346.png)

嗯。I don't know it's going to look pretty bad， I think if you do it like this。Let's see well。

 but if we offset that properly， maybe we'll not look at it。



![](img/1850b42de83cdf80b178739039962045_348.png)

It doesn't look bad， but if I put another letter in after that， that would look pretty bad。



![](img/1850b42de83cdf80b178739039962045_350.png)

Yeah， so certain letters should have smaller spacing。Maybe I'll hardco that。Yeah。

 Ill hard code that so。在这。Yes。This guy。So。Is that a5， yeah，4， A，B，C， D， E， F， G， H， I。



![](img/1850b42de83cdf80b178739039962045_352.png)

I think thatll look okay。

![](img/1850b42de83cdf80b178739039962045_354.png)

I think I'm incr that。あ。Lettter index， letter table。



![](img/1850b42de83cdf80b178739039962045_356.png)

See yeah， I'm going to say the letters in Portuguese the easier。



![](img/1850b42de83cdf80b178739039962045_358.png)

Now this is。So let's go back。J。几号对不对学的。Yeah the。KK。I already have a case like this。

 so let's just copy that。Okay。Oh。Pretty easy， I suppose。And。This may have to be5。Yeah。

 because then we can do like this。嗯。Let' see。Not sure how that'll look。X。



![](img/1850b42de83cdf80b178739039962045_360.png)

![](img/1850b42de83cdf80b178739039962045_361.png)

Wow。If we managed to get that on the screen。

![](img/1850b42de83cdf80b178739039962045_363.png)

![](img/1850b42de83cdf80b178739039962045_364.png)

ItsSeaing enough。So let's just do the other ones。 Allright， very much halfway。Halfway through。

 I think。The M will be kind of hard。And also has to be。Maybe if I removed。P。Same thing as a。

 but without。The other leg like this。Q。他应该是你 do our them。That this end up。TR。Same thing as P。

But to an additional lag。Well， it should really end like this。S。see。Okay。Oh， I'm doing。

Doing five for all of them。Yes。Now， that's not。Let's go back to doing four。Q all do5。Then R。

 let's do4。And then let's open the software render here。And do do like。M。And O。P衣。Q。R。S。Let's do。

For as well。Okay， and let's see how that looks。In the menu。



![](img/1850b42de83cdf80b178739039962045_366.png)

![](img/1850b42de83cdf80b178739039962045_367.png)

I may change the Q to not have these guys。

![](img/1850b42de83cdf80b178739039962045_369.png)

あ？Well， nothing changed， okay， yeah， I got the wrong back。



![](img/1850b42de83cdf80b178739039962045_371.png)

这 is that哎。

![](img/1850b42de83cdf80b178739039962045_373.png)

![](img/1850b42de83cdf80b178739039962045_374.png)

Let's go back here almost done。 team also。T will just be three。Okay。😊，So let's go back to softer。

Rery。Oh， and let's do。Let's do it through。t。要。Let's go back to doing。4。Yeah， do it like this。Now。

 he use the same thing as you， so。But I'm going to make that。S you want more。で。W you。

I don't think we're going to use all of them， but。It's nice to be able to express text so we can constrain ourselves we terms to letinate things。

So， that's it for W。呢啲咁你。guessし。X。嗯。😊，Well， not sure。 Like that X， though。Andbe can do。Yeah。So。

Would you you like。V w。Why。Why are we doing this。It should just download a font。Well。

 I think they'll be quicker。And the last one。An actor。We forget。How boring this was。

We could probably migrate our number system to this guy and maybe like do print。

Numbers or print text。ありがうございまし。This is like。O。Now， let's see。



![](img/1850b42de83cdf80b178739039962045_376.png)

That looks。

![](img/1850b42de83cdf80b178739039962045_378.png)

Well， mess up the V。Spcing。To然。So see why。X。但不要偏嗯。Yeah， we got one。



![](img/1850b42de83cdf80b178739039962045_380.png)

Okay。

![](img/1850b42de83cdf80b178739039962045_382.png)

And it's probably removed this guy from the wilds。放 the w。



![](img/1850b42de83cdf80b178739039962045_384.png)

![](img/1850b42de83cdf80b178739039962045_385.png)

They'll be good for now。 Now， we can start properly。After all that work。

 we could start doing like level names。So。Level names。Let's call that。Break。Out shut at this pace。

 breakout。Let's do super。Break out。Then Ill do。好。On the space invadeulators。Okay， now。I draw text。

Still was drawing like。Draw a number like this。嗯。Yeah。That's。Have color， let's do like。

Your color will be like this。Okay， and then we can just。です。So level names。哎。And I would do like， P。

I going do like 0。4。What you the menu text colors。Well， that's you like。Just to start off let。I want。

And0。

![](img/1850b42de83cdf80b178739039962045_387.png)

![](img/1850b42de83cdf80b178739039962045_388.png)

But yeah， we don't have a space。I think。本。Breakout break out on yeah。Well， we do have a space。

Although we don't hearing is the letter。' see。If this guy。Space。We should just。Youcro。And set here。

Matter index。我 do。

![](img/1850b42de83cdf80b178739039962045_390.png)

Yeah， but that wasn't the problem。 Let's see。Level 0， trying to write breakout。And we crashed。

At the letter。That was a no letter。-33， the letter index。The space， yeah， but I test the space here。

If we are a space。Oh， no， it's correct。If you are a space。We should just。Well。

 let's put a brief one here。And that's test。Let's see， B。Okay。R， E， A， K， space。 Oh。

 that was a stupid mistake。

![](img/1850b42de83cdf80b178739039962045_392.png)

We should continue。

![](img/1850b42de83cdf80b178739039962045_394.png)

The look。Correct， yes。Lergy。Breakout。s perfect。

![](img/1850b42de83cdf80b178739039962045_396.png)

This is going to be a little bit more work， I suppose。Because I may actually try to break the line。

Then I have to think about alignment。I think I'm just going to get that a little bit better。

 So the original。I'm going to set like。First。X。下你讲的。But I want to see at the X。To the first X。ok。😊。

Then I'm going to move the Y。Kind of move the Y， like the half size。Times the text height。Times 2。

Illegal for astruct。

![](img/1850b42de83cdf80b178739039962045_398.png)

一 see。

![](img/1850b42de83cdf80b178739039962045_400.png)

Yeah， but the act。So I set the first action the original。



![](img/1850b42de83cdf80b178739039962045_402.png)

🎼Okay， is a bit better。Let's do like plus two。

![](img/1850b42de83cdf80b178739039962045_404.png)

オッケー。

![](img/1850b42de83cdf80b178739039962045_406.png)

Yeah。But。We have to work on that more unfortunately， yes。Let's do like。If we are locked。

 do this if you're not locked。If we are hot。And then， the else。Forgot我 color that was。Okay， so。

If you are hot， that should be。If we are hot。We draw like this。With the menu colors。

If you are not hot。To draw， just draw a light so。Do that。And in this case。

 it goes throughout the top。

![](img/1850b42de83cdf80b178739039962045_408.png)

7。

![](img/1850b42de83cdf80b178739039962045_410.png)

It's going to be cool， I think， me take out this shape。



![](img/1850b42de83cdf80b178739039962045_412.png)

![](img/1850b42de83cdf80b178739039962045_413.png)

And。Let's not put the sound if we can't change the hot level。

Like here we try to change the hot level。Let's do like no hot level。And then we see if it's valid。

Like this。Let me just a search。That。It's not locked。Then at this point， we said the no hot and if we。

And if you are not locked。We set the hard level to them。



![](img/1850b42de83cdf80b178739039962045_415.png)

![](img/1850b42de83cdf80b178739039962045_416.png)

I that was two for。Oh， yeah。Start out as 0。Old hot。We've got the new hot。Oh yeah。



![](img/1850b42de83cdf80b178739039962045_418.png)

Yeah， I'm not sure that was the best call though。

![](img/1850b42de83cdf80b178739039962045_420.png)

Like。Else should play like a locked level。Its like they're redirect。Sound for now。Okay。

 that wasn't pleasant。

![](img/1850b42de83cdf80b178739039962045_422.png)

啊。Yeah， I don't know。

![](img/1850b42de83cdf80b178739039962045_424.png)

![](img/1850b42de83cdf80b178739039962045_425.png)

Let me start out。5ve。Forget the clamp。Well， let's do like the L count。

That should be like an invalid level。And we're going to clamp。And we press the button on a clamp。

well。你跟人个就 if。They are heart。Is less than this guy。And。下来。



![](img/1850b42de83cdf80b178739039962045_427.png)

![](img/1850b42de83cdf80b178739039962045_428.png)

Nice。Okay， this is way better， but then every time we begin that menu。



![](img/1850b42de83cdf80b178739039962045_430.png)

I don't know that's。Now， let's just keep doing like this Okay。

 now I'm going to have to center the text。And this is some work， but I think。

It'll be good in the long run。 and by the long run。

 I mean in the next couple days because it's getting down。 Sound look nice。😊。



![](img/1850b42de83cdf80b178739039962045_432.png)

![](img/1850b42de83cdf80b178739039962045_433.png)

![](img/1850b42de83cdf80b178739039962045_434.png)

I think crowd background is still pretty boring， though。



![](img/1850b42de83cdf80b178739039962045_436.png)

点个就 something inな。Photoshop， maybe， I don't know。Okay， now。

What what I want to do is put around the text， and I'm going to draw a rectangle the size that we consider。

For this guy。Just so we didn't know we are good to go like we could probably just。

Directing my the position， and I'm going to do that。I draw at the P。And I'm going to do like。T make1。

And I'm going to do like。

![](img/1850b42de83cdf80b178739039962045_438.png)

不要。Is that correct？

![](img/1850b42de83cdf80b178739039962045_440.png)

Okay so， but let me draw that。

![](img/1850b42de83cdf80b178739039962045_442.png)

![](img/1850b42de83cdf80b178739039962045_443.png)

原来不就死了。イ。

![](img/1850b42de83cdf80b178739039962045_445.png)

Yeah， let's do the standard text， let's just bite this bullet so in them。Text。A line。来。😊，Right。ません。

Okay， then I'm going to take。てい。啊呀。Now。Every time we start a letter。You're going to like， X。Plus。

 equals like。Calculate。喂。This for every letter。Yeah。For every letter。I'm going to see。For every。Yeah。

 it should be like here the beginning。To calculate。word。Aline。Like。😊，诶。Get。Word align upset。

text line。I'm going to pass the word。Which is that。Okay， and here。We're also going to do this。Yeah。

 I think this is correct。 So internal。Oh。Should be， really。Size times the。

Get toward a line offset or take a text。L。And a word。那没去。Okay， result would be zero。

And do like count。And let's do four。Word。Well， while we have a word。And that word。Is not space。应该是。

Okay， and what we're going to do here。Is simply offset， like add to the result。count。

 So count just plus。Did you like。参考。And then result is' going to be plus equals the text。

Letters spacing。Spcing here。the index。Okay。😊，Matter index。Get the result。D the result。

 I'm going to def that。买嚟听。And oh， this。Should give us like the amount。Oh， this is wrong， actually。

do this。The result is how much incremental on the whole word word。So。Yeah。

 we're going to be like if text align equals to text align left。to zero， we can do that。

On the offsetset。 On the outset。Did I say。And then， if it's right。It's right line。

We can just return the result。 I believe。 Oh， we should also add this。呃。Should I like this？

And the block offset sense。嗯，算算算算。Do you like。Okay， then we turn the results for the right line。

And if it's text to line。Text align center。Return the result。Half of it。I think。ああ。Let's see， size。

Lettter at。Okay。Yeah。😊，Let's do。Text。A line left and let's see if we didn't break。Next one， left。

And text to align。

![](img/1850b42de83cdf80b178739039962045_447.png)

![](img/1850b42de83cdf80b178739039962045_448.png)

Let's try for the selected guide just for fun。Um which you wants dislike the guy。

 this dislike the guy， let's do him。

![](img/1850b42de83cdf80b178739039962045_450.png)

Do the guys think's going to work first try？

![](img/1850b42de83cdf80b178739039962045_452.png)

![](img/1850b42de83cdf80b178739039962045_453.png)

Well。Okay， so we almost got it working the first time。

 well I'm not sure but should be minor the result and the result time。



![](img/1850b42de83cdf80b178739039962045_455.png)

Okay， so this was kind of unexpected， let me just see the center。



![](img/1850b42de83cdf80b178739039962045_457.png)

Well actually it was pretty honest。Um text the lane。That you like。Ling。Theyt do like。



![](img/1850b42de83cdf80b178739039962045_459.png)

![](img/1850b42de83cdf80b178739039962045_460.png)

So this is just wrong， the center， the left one。Is the center Oh because the half size。

Proably the right one。

![](img/1850b42de83cdf80b178739039962045_462.png)

🎼一？See how the brake super centered。And it doesn't， they don't need。



![](img/1850b42de83cdf80b178739039962045_464.png)

It only works for the first word， but okay， so let's fix that here in the software。Rinery。

So it's going to be minus times 2。And this is this。



![](img/1850b42de83cdf80b178739039962045_466.png)

So in the right， let's see。

![](img/1850b42de83cdf80b178739039962045_468.png)

![](img/1850b42de83cdf80b178739039962045_469.png)

看了。I don't know。

![](img/1850b42de83cdf80b178739039962045_471.png)

Let's just work on this guy， this guys important my least for now。

We should actually save the maximum guy。And Ill set by it。Not sure why this invaders。



![](img/1850b42de83cdf80b178739039962045_473.png)

We're like this。You should probably do like a little more structured tests。Let's just。Let's just do。

 like。Test。Like this。Pass。少少啦。5。Nice to like。Ill do。ning centerensed and remove the。Right for now。啊。



![](img/1850b42de83cdf80b178739039962045_475.png)

而情。Okay， let's put。Text well it has to be in the beginning， right？So the first word is correct。

 second word is not correct。

![](img/1850b42de83cdf80b178739039962045_477.png)

I think I passed the wrong value。 Oh yeah。 I did text the line。Text， this should be the letter app。



![](img/1850b42de83cdf80b178739039962045_479.png)

![](img/1850b42de83cdf80b178739039962045_480.png)

🎼Okay。Better， but still not working。

![](img/1850b42de83cdf80b178739039962045_482.png)

Is the letter add plus one？And here we can assert。That are。Well， let's do that。Short that the word。

Existists。

![](img/1850b42de83cdf80b178739039962045_484.png)

🎼Oh。See that？

![](img/1850b42de83cdf80b178739039962045_486.png)

It worked。Awesome， really， really， really， really awesome。 I'm going to drive this guy。😊。



![](img/1850b42de83cdf80b178739039962045_488.png)

We is got from Alexey。

![](img/1850b42de83cdf80b178739039962045_490.png)

Okay，' going to remove， I'm going to reduce the size a little bit。I do like。int4。Size。Awesome。

 how' did you guys think about that for the man？Maybe you all think this is really ugly。



![](img/1850b42de83cdf80b178739039962045_492.png)

I don't know。开 about。

![](img/1850b42de83cdf80b178739039962045_494.png)

But。

![](img/1850b42de83cdf80b178739039962045_496.png)

边度几 cool。

![](img/1850b42de83cdf80b178739039962045_498.png)

Okay， and I'm kind of liking it。 That's do the numbers。And do。我啊。I want to do two， which will be。

Well。

![](img/1850b42de83cdf80b178739039962045_500.png)

Let's not worried about the numbers for now。Just going to keep the numbers of standard as we move。



![](img/1850b42de83cdf80b178739039962045_502.png)

The P， let's see， the P a little bit。Up， let's do minus5。And the job number and move that。



![](img/1850b42de83cdf80b178739039962045_504.png)

Don， let's say point。嗯。

![](img/1850b42de83cdf80b178739039962045_506.png)

Well， let's do like it's going to be a hand let' do like this。Then do minus。



![](img/1850b42de83cdf80b178739039962045_508.png)

It was a bit too much I was 12。see。Well， they're not centered anymore。



![](img/1850b42de83cdf80b178739039962045_510.png)

Not sure what happened。Thought was maybe the size。Well， that's kind of hard to see。哈。I's still like。



![](img/1850b42de83cdf80b178739039962045_512.png)

![](img/1850b42de83cdf80b178739039962045_513.png)

Yes。

![](img/1850b42de83cdf80b178739039962045_515.png)

Let's go back to point。Or maybe just not taking the size into a council。



![](img/1850b42de83cdf80b178739039962045_517.png)

Yeah， we are not。Okay。Let's see。Size times 1。6 times 2 size1 times times2。Let's do left align。

And make sure that。

![](img/1850b42de83cdf80b178739039962045_519.png)

Maybe should be left lines a align left。

![](img/1850b42de83cdf80b178739039962045_521.png)

![](img/1850b42de83cdf80b178739039962045_522.png)

Okay。Now let's go back。Yeah。

![](img/1850b42de83cdf80b178739039962045_524.png)

Let's see if 0。5 is 100% aligned。

![](img/1850b42de83cdf80b178739039962045_526.png)

Li too much， actually。

![](img/1850b42de83cdf80b178739039962045_528.png)

![](img/1850b42de83cdf80b178739039962045_529.png)

So we're not going far enough， right？see。Block。Times the number of letters。Plus。One letter。



![](img/1850b42de83cdf80b178739039962045_531.png)

嗯。At me。Step into that。But that's why it makes it too fun to debug。爱行。

So we're supposed to align center。The word breakout， so the break， the break is working。B is working。

いやし。Super break out。So yeah， let's see the out。Okay， I suppose this is correct， but it's wrong。

 w that doesn't make sense， right？Yeah， everyone is wrong， actually。



![](img/1850b42de83cdf80b178739039962045_533.png)

🎼I should be like， twice as much。

![](img/1850b42de83cdf80b178739039962045_535.png)

没必。

![](img/1850b42de83cdf80b178739039962045_537.png)

This is a bit better， but it's not 100%。

![](img/1850b42de83cdf80b178739039962045_539.png)

You'm going to accept that。Like。This。It's not 100%。

This word has a version one and then don can go back and their robots pass。



![](img/1850b42de83cdf80b178739039962045_541.png)

And I improve that。

![](img/1850b42de83cdf80b178739039962045_543.png)

Where is our draw。

![](img/1850b42de83cdf80b178739039962045_545.png)

![](img/1850b42de83cdf80b178739039962045_546.png)

![](img/1850b42de83cdf80b178739039962045_547.png)

Can let's move everything down。So that it makes space for our title。Min- 10。



![](img/1850b42de83cdf80b178739039962045_549.png)

17 is too much， minus 15。

![](img/1850b42de83cdf80b178739039962045_551.png)

Maybe we're going to do like  minus 17 and this guy would be a minus。



![](img/1850b42de83cdf80b178739039962045_553.png)

13。

![](img/1850b42de83cdf80b178739039962045_555.png)

That wasn't right。The drug number is correct。 This guy should be like。



![](img/1850b42de83cdf80b178739039962045_557.png)

![](img/1850b42de83cdf80b178739039962045_558.png)

Yeah， the drone number is attached to it。Somewhere。High sports。That's weird。Draw number， oh。

Minus 17 minus the P。

![](img/1850b42de83cdf80b178739039962045_560.png)

Okay so。

![](img/1850b42de83cdf80b178739039962045_562.png)

啊。12 see。

![](img/1850b42de83cdf80b178739039962045_564.png)

![](img/1850b42de83cdf80b178739039962045_565.png)

It kind of works for now。呃。Be able do the creative by thing。Well。

 it's already going to break the sensor test。The center。So then be like created。By Dan Saden。哦。

Space right now is break line。I'm not going to do space client going。This， so we're going to do like。

Break。I'll super break out。Probably do your like back slash in。八。Facace invaders on lives， okay。Oh。

 actually。Let's do0，10。And let's do like。5。Let's do like。Almost white。Well。

 I don't remember what these guys are。Color count，1， index 0 All to text All。And let's do the。

If it's space。How safe。Space。We just。冇。はい。嗯。哎呀好。Letter spacing。Yeah， those do like default。

We'll do  for。Okay， function U 32， yeah， so this case。Color。

It's a pretty bad design and taking a point at well， I'm not sure。You 32， yeah。



![](img/1850b42de83cdf80b178739039962045_567.png)

Okay。

![](img/1850b42de83cdf80b178739039962045_569.png)

Yes。Well， let's do just create。

![](img/1850b42de83cdf80b178739039962045_571.png)

![](img/1850b42de83cdf80b178739039962045_572.png)

it's way too big。This guy was way too dark。Iice dude。Yeah啲。嗯。And we also grow。S。



![](img/1850b42de83cdf80b178739039962045_574.png)

![](img/1850b42de83cdf80b178739039962045_575.png)

But we also have to take into account。I always have to tip， hey， cloneed。Nice to see you， man。

 Cha's been quiet quiet today， so I was looking for it， not sure。If you just arrived or not。

 nice to see you here。 After all， this is a。😊，Tturriday afternoon， is it not？But hey。

 I'm just making games， dude。If。The at。Is space。We'll do this。For the。

This is kind of dumb what we're doing。Like really dumb， if we。If we held a little bit more here。

 not sure that's the right word， but。We would probably just。Probably just import a font。

It's not that hard。But。

![](img/1850b42de83cdf80b178739039962045_577.png)

But I know， this effect's pretty cool。 Yeah， I just got here just moving。Not too long ago。Oh， really。



![](img/1850b42de83cdf80b178739039962045_579.png)

Ptty cool。Yeah， we are implementing our new menu。 Let's see how it looks。😊，That's right。3。



![](img/1850b42de83cdf80b178739039962045_581.png)

Well。We are not doing so well， are we？🎼Soう。We are on our way。🎼あいやいや。😊。



![](img/1850b42de83cdf80b178739039962045_583.png)

Yeah， know， we're gonna to put it in that way， I also got excited because it being like a grunch work。

😊，I' see if I can get like space goal well， it can get space。



![](img/1850b42de83cdf80b178739039962045_585.png)

It's being like u look way better in the first version definitely。

 I still don't like the background but we can probably fix that later on。

Maybe just add a little bit more color， maybe I't know。But the thing is， we did our font by hand。

In by hand， I mean stupidly by hand， just so we could animate each。



![](img/1850b42de83cdf80b178739039962045_587.png)

Guy individually see the punong guy。How moves fit each block ands like that。



![](img/1850b42de83cdf80b178739039962045_589.png)

So we did our render。Like specified each possible letter then。That was a lot of work。



![](img/1850b42de83cdf80b178739039962045_591.png)

See then， yeah。It's kind of inspired by。

![](img/1850b42de83cdf80b178739039962045_593.png)

Steven sausage， I don't know if guys play that， but the menu is really cool， Stephen。Yes。

South Europe。Me女。That's a really crazy， crazy menu， let's see。



![](img/1850b42de83cdf80b178739039962045_595.png)

你 yeah。🎼It's really cool， I think。😊，It's really fun。It's kind of sad。

Because they're going to or burn all these sausages， yeah， that's really great。But。

It's a pretty cool man， so I like me making a day like that so。We are making。

The title blinks Qua music and also add the created thing。

 let's just make a little bit smaller as to like 025。



![](img/1850b42de83cdf80b178739039962045_597.png)

ForSome reason we can't add space here， why not。

![](img/1850b42de83cdf80b178739039962045_599.png)

We crash here at the app。We were trying to get the letter I I is zero。

 so trying to get the first letter of。Well， it failed。Text is created by letter add is space。Oh。

 forgot to continue。

![](img/1850b42de83cdf80b178739039962045_601.png)

![](img/1850b42de83cdf80b178739039962045_602.png)

Okay。Love the meat package design， yeah， man。

![](img/1850b42de83cdf80b178739039962045_604.png)

It's really， really fun we got no text now what what happened？



![](img/1850b42de83cdf80b178739039962045_606.png)

Sta role is a pretty pretty nice game， yeah， space broke everything man。😊。



![](img/1850b42de83cdf80b178739039962045_608.png)

If we have a space， all we're going to do is。And。The Px， the block offset times 4。by two。

 this looks correct。Let's just do it like this。So。And now we just get to buy。

I think this is the problem。You've got a space。Yeah， this is the problem。



![](img/1850b42de83cdf80b178739039962045_610.png)

We should continue here。

![](img/1850b42de83cdf80b178739039962045_612.png)

Yeah。Okay， finally， let's take that back。

![](img/1850b42de83cdf80b178739039962045_614.png)

This bag， let's see。

![](img/1850b42de83cdf80b178739039962045_616.png)

Okay， created fivebe but no space。大谢。😊，A lot。Oh， we should also add the original act。Original X。Well。

 not sure， though， me see， yeah， we do have to do that。



![](img/1850b42de83cdf80b178739039962045_618.png)

行。

![](img/1850b42de83cdf80b178739039962045_620.png)

Okay。So created by Dan， Z Dan。And we'm gonna do。On a live stream。我去。Develop。At。YouTube。

 we don't have a dot yet。Docom and we don't have plalist too。



![](img/1850b42de83cdf80b178739039962045_622.png)

YouT。🎼And try play around。

![](img/1850b42de83cdf80b178739039962045_624.png)

Okay， so I'm going take the menu of the。The logo， and I me put that a little bit smaller。Maybebe。10。

10。创你。

![](img/1850b42de83cdf80b178739039962045_626.png)

15。那ち。

![](img/1850b42de83cdf80b178739039962045_628.png)

Yeah。😊，啊。So。If we do like 15 times 2 do 15， got 32。 25， let's try that。32 do25 well。短精。

Let let's move that up。れルべ。

![](img/1850b42de83cdf80b178739039962045_630.png)

I see。😊。

![](img/1850b42de83cdf80b178739039962045_632.png)

可以。Can also move the logo up。

![](img/1850b42de83cdf80b178739039962045_634.png)

Li bit more。

![](img/1850b42de83cdf80b178739039962045_636.png)

Can you a bit better。'mNot sure about hiery。 I don't know if。



![](img/1850b42de83cdf80b178739039962045_638.png)

![](img/1850b42de83cdf80b178739039962045_639.png)

Maybe I'm going to do like created by Dan's Aideden。Dan they Dan， and then on a live stream。

 I'm going to put that。Smaller life。2。Then I can just。



![](img/1850b42de83cdf80b178739039962045_641.png)

![](img/1850b42de83cdf80b178739039962045_642.png)

Yeah， still pretty big， though。2， let's make。欢迎。15。13。



![](img/1850b42de83cdf80b178739039962045_644.png)

Thanks。

![](img/1850b42de83cdf80b178739039962045_646.png)

Okay。Think it'll be better。 Let's try point。Bye。

![](img/1850b42de83cdf80b178739039962045_648.png)

Then。

![](img/1850b42de83cdf80b178739039962045_650.png)

See， our standards not 100% yet。Let me just review the code many clone type can help me out。So。

We have a problem。🎼With our alignment。Well， aly。Maybe change the background。🎼那し。



![](img/1850b42de83cdf80b178739039962045_652.png)

Maybe two of blooms that I've。Color。不' see。啊。Are centered。Our block offset。

Just how much this one block？Offsets。Is 1。6， which is the side of the size times  two。

 because that's the whole size。Times the spacing times two， I think that may be the problem。



![](img/1850b42de83cdf80b178739039962045_654.png)

![](img/1850b42de83cdf80b178739039962045_655.png)

Well， maybe that was too。Not sure why。

![](img/1850b42de83cdf80b178739039962045_657.png)

Now see this is lot wrong。So。ok。Now we add。In case we have。In case we have we get the ladder spacing。

 which the number of blocks that he occupiedccupies multipied that by the block size。

And add one size。Why do we add one size？Well， that's for this pace that suppose， right？



![](img/1850b42de83cdf80b178739039962045_659.png)

啊。Yeah， the text at the bottom is correct。

![](img/1850b42de83cdf80b178739039962045_661.png)

Well not entirely correct。

![](img/1850b42de83cdf80b178739039962045_663.png)

Timm going to get me some water because I ran out of water。And then maybe I can think about that。



![](img/1850b42de83cdf80b178739039962045_665.png)

Probably print some stuff just to make sure。

![](img/1850b42de83cdf80b178739039962045_667.png)

![](img/1850b42de83cdf80b178739039962045_668.png)

I think the background color was better， but I don't like the created eye color。

I think it's too bright。Let's try adding like a little bit of red。So， let's do D。



![](img/1850b42de83cdf80b178739039962045_670.png)

![](img/1850b42de83cdf80b178739039962045_671.png)

Okay， kind of like that。

![](img/1850b42de83cdf80b178739039962045_673.png)

But check this out if I。

![](img/1850b42de83cdf80b178739039962045_675.png)

Copy the whole thing to the first guy。goes on crazy the alignment。



![](img/1850b42de83cdf80b178739039962045_677.png)

I'll let me just。

![](img/1850b42de83cdf80b178739039962045_679.png)

Yeah， this looks sway better。

![](img/1850b42de83cdf80b178739039962045_681.png)

I think I may copy that part of the logo collar。

![](img/1850b42de83cdf80b178739039962045_683.png)

Like this color。And add that to the creativeby。But I really need to。Get that spacing working。



![](img/1850b42de83cdf80b178739039962045_685.png)

![](img/1850b42de83cdf80b178739039962045_686.png)

Yeah， this is better。

![](img/1850b42de83cdf80b178739039962045_688.png)

And I'm thinking that the background should be something like。



![](img/1850b42de83cdf80b178739039962045_690.png)

Like this。Yeah， that'll make it pretty cool， I think。嗯，苏以啊。

'Not sure how much time I want to spend with the center text thing。



![](img/1850b42de83cdf80b178739039962045_692.png)

But it's kind of a big deal right， so I'm going to get some water。

 I'm going to dig back in two minutes。Two mid break。Then when I come back， we're going to try to fix。

 fix that same position then maybe do this。

![](img/1850b42de83cdf80b178739039962045_694.png)

Ting on the menu。But our rotator rectangle doesn't support。咩按钮。Let's try it with that。



![](img/1850b42de83cdf80b178739039962045_696.png)

Okay， so I'll be back in two minutes。Okay。I think。Well， I know where to make sure that it works。

I'm just going to run through all the places that we add the peak。So if it's a space。

 we add the being and then we do the same thing here。Okay， now。If you go back a line。We。Yeah。

Now we add the block offset X。Every time we run through a non space。Gt。Well。Oh。

 because we write one block at a time， yeah。So draw a block。And then I the block ops have X。

And at the end。We had so。So we add the block offset x times the yeah， this is the problem。

So we add one block offset x for every。Block we have， which is the ladder spacing。Correct。Yeah。

 correct。We add one block of the fridge guy， and then we add another block offset。Oh no。

 then we reset the whole thing， so this is the only thing that we actually should do。For each letter。

So I suppose we were correct。Yeah。

![](img/1850b42de83cdf80b178739039962045_698.png)

So technically， we were correct， but we weren't correct。See， now this looks correct。



![](img/1850b42de83cdf80b178739039962045_700.png)

Or maybe mark for。Let's see。

![](img/1850b42de83cdf80b178739039962045_702.png)

![](img/1850b42de83cdf80b178739039962045_703.png)

![](img/1850b42de83cdf80b178739039962045_704.png)

呃。I can just run through that one more time， let see。We add to the block offset X。😡，4。

That's when we find。A space。 We have four blocks， plus one size。So whenever we find a space。

We had four blocks and on size。I don't like this。Cause you're supposedly already， already。

Adding two to the size and to the block offset， anything like that。



![](img/1850b42de83cdf80b178739039962045_706.png)

our first idea was just do this。

![](img/1850b42de83cdf80b178739039962045_708.png)

This is clearly， clearly， clearly wrong。Now。We run through the whole word， until we find。

Until it runs out or we find a doubles sch。Then you see if it's a space we do this， it's not a space。

 we get the letter index。And then we add the number of blocks that we were supposed to add。Oh。

I know this is correct。Times post size times。But this guy。I'm not sure what it's doing。

 we said that to the original X。This after writing a letter， right？And then we advanced。

A whole letter， so this is a whole letter， plus the spacing。So I think this is the problem。

I think this may be the problem。Yeah， so we are supposed to advance a whole ladder plus the spacing。

Like this is a whole letter。P spacing but。You are supposed to subtract the spacing at the end。



![](img/1850b42de83cdf80b178739039962045_710.png)

Because the last letter supposedly doesn't have a space。



![](img/1850b42de83cdf80b178739039962045_712.png)

Well。

![](img/1850b42de83cdf80b178739039962045_714.png)

I don't know they're going to the wrong size， I suppose， to the wrong side。



![](img/1850b42de83cdf80b178739039962045_716.png)

Let's do a much shorter test。And let's see now I'm going to do the created by things。

Let's a smaller test that you just created。Well。

![](img/1850b42de83cdf80b178739039962045_718.png)

![](img/1850b42de83cdf80b178739039962045_719.png)

Let's。

![](img/1850b42de83cdf80b178739039962045_721.png)

Let's remove this guy。

![](img/1850b42de83cdf80b178739039962045_723.png)

Okay， were clearly not centered。

![](img/1850b42de83cdf80b178739039962045_725.png)

Let's see why， let's go to our software render。And let's step through this guy。

Okay set the color and the first P should be0。 Yeah， and let's now see。Our word alignment。

 so the block offset size is 0。2。Size 0。8。Each block size。Okayay。And then for every。Letlatter。

We' are going to get the letter index and then add this guy， so the letter spacing。

For this ladder index。Is4。And then we add four blocks。With the blocks offset。And then add this guy。

 which is the amount of space。Between the letter and the next letter。And then let's just keep going。

 Let's see。2内衣。24， okay。24。Then we should start that like。Start at minus9。Oh。



![](img/1850b42de83cdf80b178739039962045_727.png)

Because we already computed the size here。At first， we weren't going to compute the size。

Then we we decided to compute the size。That's why it's wrong。



![](img/1850b42de83cdf80b178739039962045_729.png)

Nice。Okay， now this is perfectly correct， so we have the right line。



![](img/1850b42de83cdf80b178739039962045_731.png)

She's this guy。Then we have。Left a align。The center line。Its this guy。

And now it should be really good to go。Oh， tax， text。A line and。



![](img/1850b42de83cdf80b178739039962045_733.png)

还行。

![](img/1850b42de83cdf80b178739039962045_735.png)

Perfect。Now， let's go back to this guy and let's see how。How it looks。



![](img/1850b42de83cdf80b178739039962045_737.png)

That looks perfect。

![](img/1850b42de83cdf80b178739039962045_739.png)

And let's the by a little bit lighter。Let's do like， oh， turn out to BDA。Let's do like a。二点。

And I's do like。

![](img/1850b42de83cdf80b178739039962045_741.png)

Oh that didn't change much。

![](img/1850b42de83cdf80b178739039962045_743.png)

Let's doing an F。屎。

![](img/1850b42de83cdf80b178739039962045_745.png)

Let's do it， A 2。🎼Yeah。Okay， we are a lot better。

![](img/1850b42de83cdf80b178739039962045_747.png)

They're a lot better， I think， let me just put the text a little bit。The more。



![](img/1850b42de83cdf80b178739039962045_749.png)

![](img/1850b42de83cdf80b178739039962045_750.png)

And then let's do the whole YouTube thing。Instead of doing like the index， let's see， letter index。

We're going to do the get。Index。It can be numbers and all sorts of stuff。O。

And then I'm going to do a dot。Which just like this。You like。Yes。equals？Dot。Return。啊77。us8。Pouse one。

 that's really bad hack。Else， return。C， minus。So we can do like YouTube。t。



![](img/1850b42de83cdf80b178739039962045_752.png)

Now we do have YouTube doc。

![](img/1850b42de83cdf80b178739039962045_754.png)

Come。Slash。Let's do thelash。Its2。嗯。嗯。Let's see how many we have one， two， three， four， five。

 very half way too much。Let's try like this。1，2，3，4，5。And then this array。1。



![](img/1850b42de83cdf80b178739039962045_756.png)

嗯。Okay， so。minus8。Thislash was minus-18。

![](img/1850b42de83cdf80b178739039962045_758.png)

For some reason， or maybe I didn't put the if correctly， I don't think I did。



![](img/1850b42de83cdf80b178739039962045_760.png)

No I do。

![](img/1850b42de83cdf80b178739039962045_762.png)

I'm thinking we'm going to do like a shorter slash。



![](img/1850b42de83cdf80b178739039962045_764.png)

Well要。

![](img/1850b42de83cdf80b178739039962045_766.png)

I can't， really， maybe a longer one。One， two， three， four， five， six， seven。



![](img/1850b42de83cdf80b178739039962045_768.png)

![](img/1850b42de83cdf80b178739039962045_769.png)

I don't like that。Let's try a shorter one。That's what we did last time。

 was it's not let try like this， so。1，2，3，4。 So we go back to the normal size of four。



![](img/1850b42de83cdf80b178739039962045_771.png)

![](img/1850b42de83cdf80b178739039962045_772.png)

🎼Okay。On a live stream， we'll watch the development at YouTube our on Dan Dan。🎼はブック。

Let's try doing the last part which is the two rectangles。



![](img/1850b42de83cdf80b178739039962045_774.png)

In fact， let's not do that。 Let's a。So let's go back to the game。

 let's rest and up so menu we did that。Did that。 So we're going to do the show timers thing， the UI。

And it's hard to see， but're also going to improve that。

Then maybe we're going to go back to the menu and add the two rotated。好的。给。😊，Let's go。



![](img/1850b42de83cdf80b178739039962045_776.png)

嗯。🎼So。We can have color problems。One problem is if you are a little bit， well。



![](img/1850b42de83cdf80b178739039962045_778.png)

For some reason， it's really hard。就呃like呢。

![](img/1850b42de83cdf80b178739039962045_780.png)

I'm to remove this guy。🎼啊。

![](img/1850b42de83cdf80b178739039962045_782.png)

That's not the problem。Yeah， oh， this is the problem。When we resize the app， we should only do this。

Yeah， we should only do this。If。We are supposed to lockmail， so we 32 lockmail。



![](img/1850b42de83cdf80b178739039962045_784.png)

Okay， so let's go back to this point。See how if I make that a little bit thinner。

We start losing our guys on the left there。We could。Yeah。I think we're going to do this。



![](img/1850b42de83cdf80b178739039962045_786.png)

I mean。We have two options， let me show you guys。The first thing we could we could do is just to move them right。

 Thatll be the easiest thing。 But another thing we could do is to make different coordinate systems for different needs。

 So if， for example， we are here in the standard。 that's the basic coordinate system。 This is 0，0。

 We could add a coordinate system that's like set。We could do like a set center。Said center to。

To this guy， if we do this our 0，0 bit this independent or of where it is。

 then we could add them a little bit to the right。We could do that。



![](img/1850b42de83cdf80b178739039962045_788.png)

It may be the best call。But just to make it faster， though， I'm just going to。

Here where I render the player。Well， let's do like the live。

 I'm not sure what I do that lets see let live。Have player life。We have player life。

s probably to hear player like， yeah。We' just move that。Attle bit to the right， so。



![](img/1850b42de83cdf80b178739039962045_790.png)

Or maybe you could just add。

![](img/1850b42de83cdf80b178739039962045_792.png)

Today we're going to have size x， really。

![](img/1850b42de83cdf80b178739039962045_794.png)

🎼Plus？

![](img/1850b42de83cdf80b178739039962045_796.png)

Half the size of our guy， which just wants so。

![](img/1850b42de83cdf80b178739039962045_798.png)

Maybe not halfag maybe full size。

![](img/1850b42de83cdf80b178739039962045_800.png)

🎼Yeah。

![](img/1850b42de83cdf80b178739039962045_802.png)

Okay， and then I'm just going to move the square。A to the right。



![](img/1850b42de83cdf80b178739039962045_804.png)

And at like。A couple of my zeros， just for fun。

![](img/1850b42de83cdf80b178739039962045_806.png)

Yeah。

![](img/1850b42de83cdf80b178739039962045_808.png)

![](img/1850b42de83cdf80b178739039962045_809.png)

Okay， I think we are good。Maybe a little bit more。

![](img/1850b42de83cdf80b178739039962045_811.png)

Okay。I think that that's enough now in the palm level it's invisible。



![](img/1850b42de83cdf80b178739039962045_813.png)

Which makes me think that I may want to add a tiny black border behind him。

Maybe let's do like a dark gray order。I did that a little bit。Yes tiny it。这个。Then I can add like。1。

Yes。

![](img/1850b42de83cdf80b178739039962045_815.png)

Let's see。😊，Well， that's still not very feasible。

![](img/1850b42de83cdf80b178739039962045_817.png)

Let me add。A biggerboard like 25。We also show have full screen support。



![](img/1850b42de83cdf80b178739039962045_819.png)

It's not too hard and it'll make oh but begins we pretty， yeah， this is pretty bad。



![](img/1850b42de83cdf80b178739039962045_821.png)

嗯。So， we add。There are not times。Two point at N3。Oh， I'm sorry just steering a lot。Now。

 this should be X I times。

![](img/1850b42de83cdf80b178739039962045_823.png)

一阿子。

![](img/1850b42de83cdf80b178739039962045_825.png)

A bit better。And now it's smart Facebook。🎼And I'm also going to change the color。



![](img/1850b42de83cdf80b178739039962045_827.png)

Just so it's not exactly the same color。Maybe I'm going do a little biter。



![](img/1850b42de83cdf80b178739039962045_829.png)

Yeah。Oh， lookss pretty weird I think。Like that。

![](img/1850b42de83cdf80b178739039962045_831.png)

🎼オ。So that was part one of our interface things。

![](img/1850b42de83cdf80b178739039962045_833.png)

Now we should show the timers because that's the problem we have。Like let's see if we get a power up。

We do all that spring。Yeah， let's say we got this power， we don't know we have that power。



![](img/1850b42de83cdf80b178739039962045_835.png)

That's the basic idea。 So it's pretty easy。What we are going to do， see。

 that's another case where we could benefit。Where is my paint？



![](img/1850b42de83cdf80b178739039962045_837.png)

There's a paintbrush。Well， I think I close that。 Are we could benefit of having a。

Moveable coordinate system， like in this case， maybe we should align to the bottom left of the screen。

But this is the first game we're doing live。

![](img/1850b42de83cdf80b178739039962045_839.png)

I got to bother。Just going to， you know。Oh， and I just need a。Game polish。

 Let's do like or maybe more few that's。I do。Change。I make。没有。给play transition自。可。😊，N。

Now show timers。We render， let's see here in our level。Things like the instability， right？see。

's well。Oh这的 againO so。In频。Sbil T， let's say。It's one of the first things that we did， okay yeah。

That's what we do here。What I'm going to do is to draw the bitmap。

Right the disability power bit mapps。Let's see invincibility。

 Let's see what it's called with not invincibility。We're going to draw that。

 if the imibility is greater than。This guy。Where am I？不有て。Invinsibility。啊。T议。

Let's do the power the forest field。Firstse you goodmap。Where do we do that？Forse field。

I'm really computer right now for。Fd the bitmap。Let's do。What is it called。Bnet force， oh。

 force on the squares of force。Let's change that and we'll go place by place and see where we are enjoying that。

ok。😊，This forest food greenry。If we have a invincibility。We are going to draw a ginap。Okay。😊。

And it's going to be the bitm。Invin invincibility。Now let's just draw that in the middle of the screen。

Let's do like two， two。I don't remember what else we had。Alpha multiplier。 Let's do one。Yeah。



![](img/1850b42de83cdf80b178739039962045_841.png)

Okay。😊。

![](img/1850b42de83cdf80b178739039962045_843.png)

And we should also do just for the sake of testing， making test， oh， we do have。

You have that the shortcut。C。🎼Now， we draw the force gear。Now， let's do a nicer position。

 So in X is going to be the arena。Half size。Dot X。And why we might as well do the arena have size？



![](img/1850b42de83cdf80b178739039962045_845.png)

![](img/1850b42de83cdf80b178739039962045_846.png)

But it should be on top of everything。So maybe we should do， I'm not sure about that。

Because our rate it right now it's utterly dependent， so when you say draw， it just draws。

Maybe we should have like a queue to draw things later on。

But I'm not sure I don't think want to do that。I think we're just going to do that at the very end。

Like， yeah。Like， draw。Hud。Yeah。So we're going to do the Vmap， yeah， so。

 but that's only if the invinsibility T is greater than zero。



![](img/1850b42de83cdf80b178739039962045_848.png)

![](img/1850b42de83cdf80b178739039962045_849.png)

一次。😊，But going I'm going to do like a P。And it's going to be。This guy first。But we are going to。

 like。Add2。あ。

![](img/1850b42de83cdf80b178739039962045_851.png)

Just so we don't。Over like。And had like four。

![](img/1850b42de83cdf80b178739039962045_853.png)

オッケー。🎼And just to make sure we work at all resolutions。Well。

Let's do the cheat to give us like a lot of。

![](img/1850b42de83cdf80b178739039962045_855.png)

Invin delete。

![](img/1850b42de83cdf80b178739039962045_857.png)

So。Let's see if you are wider the or it's perfect。Are not。Now we are going to draw the guy。Here。

G ahead。And we're also going to draw the text。 So we have draw float。 I don't think so。

It the console thing I have。F 32。Print F32。Yeah。嗯嗯。I think I might just do like， draw。F 32。爱奇艺。

And we're going to take。Float。P。嗯。Size。Color。And 0， what is it。你啲。不要。更 hardco that。Okay。

 and I'm just going to call Dr F 32。And do the message。Message F you2 fail。The P， just the P。5e。

This guy。And what is this one？Okay， so this。Is the number。Number。ok啊。This would be a color。テ手いです。Nes。

Coer。Dr。Just see if you can still draw it light。Friend。



![](img/1850b42de83cdf80b178739039962045_859.png)

That's print or rate。

![](img/1850b42de83cdf80b178739039962045_861.png)

Okay， it works。 It works。 Now， let's move this guy to the renderer。And we have drawn number。Okay。😊。



![](img/1850b42de83cdf80b178739039962045_863.png)

Let's just said this guy。

![](img/1850b42de83cdf80b178739039962045_865.png)

And now we can do draw F 32。And I're going to pass the invincibility key。And the P is gonna be。

 let's say。A V2P。That's it。3。0。And we also have to add color in the size。



![](img/1850b42de83cdf80b178739039962045_867.png)

Not sure。那吃了气。

![](img/1850b42de83cdf80b178739039962045_869.png)

Way too small。Too much to the right。That's weird， because well， it's through10。Isn't that nice？

That's really nice。And when to finish doing this， we're also going to move the PY。10 up。ok。😊，Now。

 if we have comments， so we're going to do。Number of triple shots。And let's do triple shots first。

Number of trick shots。Well， what is it called。That's the levels。Our。Number of。Oh my god， number。这不啥子。

If it's greater than zero， they're going to do the same thing。But I're going to draw a。吹口。Same thing。

And we're going to do as an int， and we can do no。Leing zeros or one， I suppose。Yeah one。Same thing。

Same thing。Draw in， I draw。Number。I'm going to draw the number of。Chriooper shots， nice。

 We are doing nice progress now。 which's good。Because we were stuck a bit。For that， but visually。

 it's a lot of different。It's always nice。😊，And then we're going to go to the Com T。

 if it's greater than zero， we're going to draw the bitmap comment。Go to draw the comment tea。



![](img/1850b42de83cdf80b178739039962045_871.png)

就。Let's see。😊。

![](img/1850b42de83cdf80b178739039962045_873.png)

は。Isn't that awesome？し。

![](img/1850b42de83cdf80b178739039962045_875.png)

Okay，10 is way too much。That's maybe5。And also for the int。T0 was also too much。



![](img/1850b42de83cdf80b178739039962045_877.png)

Oh， missed it。These were left line， a right line。Text， we。Coming in hand。

But this is already weight better。Like 100%。

![](img/1850b42de83cdf80b178739039962045_879.png)

啊死。Really awesome。 Now let's add the par downs。😊，Same thing。Has strong blocks， which is a timer。

 so' copyied this guy。And then I add strong。And this is。Strong blacks。P p c。

Let's say inverted controls。There's also timer and is updated as a timer。Inverted controls。

P controls big map and。Whoa is that？哎对。This is the slow player。S。Turtle， yeah。Nice。😊。



![](img/1850b42de83cdf80b178739039962045_881.png)

Okay。Now it should be all good to go already， that was a pretty cool system。这个新。Doude making。

🎼This kind of a， I don't know， finishing touches。Although it does take a long time if you want to do it。

 right？It's just so much better。Wow， that collision was really。咁。What。你是。🎼Nice。Oh yeah。

 now we have strong blocks。I'm sure what happens。こ。This guy way too slow， I don't know what happened。

He's lower the wide。And may have to review that video like we did last time， the collision。



![](img/1850b42de83cdf80b178739039962045_883.png)

I to note that is a bug。

![](img/1850b42de83cdf80b178739039962045_885.png)

At a 3，10， so。五音。Ball， snow ball， but。

![](img/1850b42de83cdf80b178739039962045_887.png)

Okay， let's clear a little bit more。

![](img/1850b42de83cdf80b178739039962045_889.png)

I think I'm going to move the created by down。Create by， let's say， let's put it like 17。

And this guy， let's do it like。Tot move that up， okay。So，8。And 3。



![](img/1850b42de83cdf80b178739039962045_891.png)

🎼ケ？

![](img/1850b42de83cdf80b178739039962045_893.png)

I think the brake line is a bit too hard to see in the。啊，家长的乳液。Get this guy。



![](img/1850b42de83cdf80b178739039962045_895.png)

Let's do。bye。怎么去。I don't know， I kind of like that。



![](img/1850b42de83cdf80b178739039962045_897.png)

But then I'm going to move these guys。Just a little bit up。-16。And I also have to move this guy。

This guy。

![](img/1850b42de83cdf80b178739039962045_899.png)

🎼Okay。

![](img/1850b42de83cdf80b178739039962045_901.png)

I'm going to do super breakout like this。

![](img/1850b42de83cdf80b178739039962045_903.png)

🎼Nイス。I think I'm going to add like a rectangle on the title。



![](img/1850b42de83cdf80b178739039962045_905.png)

Yeah， let， let's do the menu。The pretty menu pass。First of all， I'm going to add。A wide rectangle。

Here， so I'm going to draw transparent， rotated rec。We're going to draw them。At the disgu's P。说的比较。

有企。Spend。So， it's can be。It's gonna be this guy's P。Yeah。Half size， let's say， well。

 what is this kind？15 up plus do like。17。Only I and I do like 60。Which should be more than the arena。

The angle 0， the color。Let's do like a lighter bluesome then do're like。7，7。AA FF。

Of a multiplier I it like can I animate that later on， I think？But I 0。5。



![](img/1850b42de83cdf80b178739039962045_907.png)

Well alerts。

![](img/1850b42de83cdf80b178739039962045_909.png)

Really bad。Take a little bit better。

![](img/1850b42de83cdf80b178739039962045_911.png)

I'm going to increase the size a lot。

![](img/1850b42de83cdf80b178739039962045_913.png)

The size， and I' going to decrease the sky a little bit is due like。



![](img/1850b42de83cdf80b178739039962045_915.png)

![](img/1850b42de83cdf80b178739039962045_916.png)

I don't know。

![](img/1850b42de83cdf80b178739039962045_918.png)

Maybe a little bit more。

![](img/1850b42de83cdf80b178739039962045_920.png)

I don't know， I don't like that。I me go to Photoshop。Let me play around this little bit。哦， ok。

Couldn't be a new， couldn't make a new guy。啊 ok，开始。Okay， I think I may add just this color。

As this color。And。Like this。And then as this color， I'm going to。Add like a lighter blue like this。で。

嗯。たちは？Okay。Okay， that already looks better。But I think I'm going to turn this opacity down to like。

Yeah。This is a little bit better。Just a little。So I'm going to， let's say， select。



![](img/1850b42de83cdf80b178739039962045_922.png)

This color。For the title thingme。And then I's say the capacity will be 0。4。



![](img/1850b42de83cdf80b178739039962045_924.png)

And then， this color。

![](img/1850b42de83cdf80b178739039962045_926.png)

Before the the clear。

![](img/1850b42de83cdf80b178739039962045_928.png)

I see how that looks。

![](img/1850b42de83cdf80b178739039962045_930.png)

That'd be better。Now instead of。

![](img/1850b42de83cdf80b178739039962045_932.png)

16 let's do 15。5。Okay。

![](img/1850b42de83cdf80b178739039962045_934.png)

And I'm also only going to change the hearts。Sa。Hot level。' Oh I'm going to do this。

If the what is it mouse D。Dy。What is the mouse key？I think likes a feet2I only if that。This guy is a。

Yeah，O。Museday pe。Input multiC P。

![](img/1850b42de83cdf80b178739039962045_936.png)

Okay， let's see。 Now we shouldn't have anything selected。Now as soon as we move。

Now let's try adding that crazy rectangle thing。

![](img/1850b42de83cdf80b178739039962045_938.png)

So we should have the arena size。And Im， I'm going to try adding that to here。

 And this is gonna be a huge overdraw。But this is the main menu。

 So I don't think there'll be a frame rate problem。 And even if there is a frame rate problem。

I don't think say mine is arena。I don't think we carry that much。

 but we're going to optimize probably。Everything。At one， and then that's okay down。Then that's add。



![](img/1850b42de83cdf80b178739039962045_940.png)

🎼Okay。

![](img/1850b42de83cdf80b178739039962045_942.png)

Itund be cool， I think。Let's do， like 60，40。And let's you like， full out。



![](img/1850b42de83cdf80b178739039962045_944.png)

🎼Nice。

![](img/1850b42de83cdf80b178739039962045_946.png)

Okay， but I'm gonna add this guy。Or the other one。And the same thing here。



![](img/1850b42de83cdf80b178739039962045_948.png)

![](img/1850b42de83cdf80b178739039962045_949.png)

Okay， developing minus three。

![](img/1850b42de83cdf80b178739039962045_951.png)

What do you guys think？It little bit weird。What was that？As violation， reading， location。

No hot level。So， our。Delta P now。Player visual P。Went to crazy levels。



![](img/1850b42de83cdf80b178739039962045_953.png)

喂hy。Because the frame rate dropped a lot。

![](img/1850b42de83cdf80b178739039962045_955.png)

Yan。So I guess we are into a little bit of an optimizing task later on。



![](img/1850b42de83cdf80b178739039962045_957.png)

Let's just draw the frame rate。D。Let's to。0， and I do it like。3。S子。



![](img/1850b42de83cdf80b178739039962045_959.png)

![](img/1850b42de83cdf80b178739039962045_960.png)

Oh， let's make it。

![](img/1850b42de83cdf80b178739039962045_962.png)

![](img/1850b42de83cdf80b178739039962045_963.png)

So we're not that that。I mean， we are dead。

![](img/1850b42de83cdf80b178739039962045_965.png)

But it's not that bad。I don't know I don't know。You guys know晚上好。



![](img/1850b42de83cdf80b178739039962045_967.png)

![](img/1850b42de83cdf80b178739039962045_968.png)

嗯。I think it was 90， right？

![](img/1850b42de83cdf80b178739039962045_970.png)

🎼And as you like this。 So this is seconds， right， so I'm going to multiply。Is by 100。

And I'm going to do it back。Let's draw it light。Actually like CT that you。



![](img/1850b42de83cdf80b178739039962045_972.png)

An initialitialize memory color。What's the color of an initialized memory？So you have 40 FTS。

 which is bad， but it's not that bad。🎼We definitely freak out about it。



![](img/1850b42de83cdf80b178739039962045_974.png)

Certainly， we shouldn't。

![](img/1850b42de83cdf80b178739039962045_976.png)

啊。That's错。

![](img/1850b42de83cdf80b178739039962045_978.png)

🎼Maybe we can compare just for the fun of it， let's see this is the final result final quote this is the sketch。



![](img/1850b42de83cdf80b178739039962045_980.png)

I think we're getting there， I didn't like that green， I think it was too strong。But for some reason。

 I can't move this guy either， although those here just close to that。



![](img/1850b42de83cdf80b178739039962045_982.png)

Okay， the for some reason， for some reason or debugging purposes。

 to the optimized version and let's see how run。

![](img/1850b42de83cdf80b178739039962045_984.png)

Okay， we are to 20。Miseconds per frame， which is again， not great。And our size break completely。

And now you can see the cursor。Oh， did we now。O。🎼でしょ。This is less worry。Its one a second before。🎼绝定。

🎼We went all the way， too。So I already know what to optimize。Just by showing the at。

Which is certainly the。Our real theater rectangle function。A our。That's not optimization day。But。

 that's a part。I' I put that on the other side of the screen， let's do it like。



![](img/1850b42de83cdf80b178739039962045_986.png)

![](img/1850b42de83cdf80b178739039962045_987.png)

The top right。

![](img/1850b42de83cdf80b178739039962045_989.png)

Let's do it like a little bit smaller。Let's move with it。Right。more。



![](img/1850b42de83cdf80b178739039962045_991.png)

But well。

![](img/1850b42de83cdf80b178739039962045_993.png)

Let's do black。

![](img/1850b42de83cdf80b178739039962045_995.png)

一嘅就系佢哋。I don't know what33 stand for memory code。

![](img/1850b42de83cdf80b178739039962045_997.png)

Already I didn't know why that was too。Something's wrong。



![](img/1850b42de83cdf80b178739039962045_999.png)

![](img/1850b42de83cdf80b178739039962045_1000.png)

🎼对呀。

![](img/1850b42de83cdf80b178739039962045_1002.png)

![](img/1850b42de83cdf80b178739039962045_1003.png)

哎呀过来呗。Let's do a little bit lighter。

![](img/1850b42de83cdf80b178739039962045_1005.png)

Let's do。Yeah， but not I'm not going to optimize stuff。

 but just to show that our menu runs at a 20 meiseconds per frame。And hurricane。R ons at 0。

9 give meiseconds。

![](img/1850b42de83cdf80b178739039962045_1007.png)

So， yeah。

![](img/1850b42de83cdf80b178739039962045_1009.png)

Just because of transparent rot erectane。啊，丢的。F is going on。



![](img/1850b42de83cdf80b178739039962045_1011.png)

Yeah。So this call is pretty slow， let's just take a quick look。

 we're not going to optimize that to date， certainly。But。The problem is。

 has to be really slow with trends。Has to be inside the pixels。Yeah。

So we can avoid calling thatash for this guy pretty easily this guy。Because that's just to get color。

嗯。

![](img/1850b42de83cdf80b178739039962045_1013.png)

This linking problem is really good。So。Yeah， can just get that color。



![](img/1850b42de83cdf80b178739039962045_1015.png)

And make it normal。Draw right。Like this。And they'll be already a lot faster。

Originion from flow to either to2。We don't take a rotation。



![](img/1850b42de83cdf80b178739039962045_1017.png)

7。😊，🎼对呀。🎼です。A lot faster。But now these guys。I could draw them as a bitmap。🎼I'll now it' down to 14%。

14。Okay， that's more manageable， manageable， let's also increase。

 let's take them out of the screen a little bit more。



![](img/1850b42de83cdf80b178739039962045_1019.png)

So this guy mine is an020。So if you do， like。

![](img/1850b42de83cdf80b178739039962045_1021.png)

啊。还有了。So yeah。🎼This is特 bad。🎼A little bit better。And we get a little bit of our own。

 so this is different dependent。

![](img/1850b42de83cdf80b178739039962045_1023.png)

We are supposed to improve that。Like， review the player。

W collision and I now make the size it the yeah， have to do that。For。But okay。



![](img/1850b42de83cdf80b178739039962045_1025.png)

Let's keep going。How does that look？I think that's okay。



![](img/1850b42de83cdf80b178739039962045_1027.png)

I see how it looks in the beginning of the game， not see。



![](img/1850b42de83cdf80b178739039962045_1029.png)

It's funny that we don't get the sound。🎼So now I'm going to assume our DP is broken。



![](img/1850b42de83cdf80b178739039962045_1031.png)

And you know what？Let me change to cater a little bit more。Is a hot guy。Self just。Like， if。Ese。好，来不。

Is L。illegallllegal else。They go else。嗯。那ok。Thank you。



![](img/1850b42de83cdf80b178739039962045_1033.png)

![](img/1850b42de83cdf80b178739039962045_1034.png)

This is better。And that color is too dark think。ThisThis color is to dark， let's do light。5。

🎼Maybe that still be too dark。Do 8， that's。

![](img/1850b42de83cdf80b178739039962045_1036.png)

![](img/1850b42de83cdf80b178739039962045_1037.png)

And now whenever we go back to the menu， I'm also going to set the hot level to the outcome。

Whenever we go to the menu， see menu case here we set all that。



![](img/1850b42de83cdf80b178739039962045_1039.png)

![](img/1850b42de83cdf80b178739039962045_1040.png)

Rd， that didn't do me。Hot level。To the account。

![](img/1850b42de83cdf80b178739039962045_1042.png)

![](img/1850b42de83cdf80b178739039962045_1043.png)

Oh it did work， maybe I just maybe the league couldn't figure out that I could change them。Okay。

 let's see what else we have。

![](img/1850b42de83cdf80b178739039962045_1045.png)

We okay， so I， I think we are。Pretty much done。🎼I mean。WeHave a lot of stuff to do honestly。



![](img/1850b42de83cdf80b178739039962045_1047.png)

But I think we are pretty much done in terms of what we wanted to do today。

I don't think I'm going to do a pause menu for this game at all。



![](img/1850b42de83cdf80b178739039962045_1049.png)

Because they aren't pretty short levels。It wouldn't be hard to do。

 but I don't want to spend the time on that。

![](img/1850b42de83cdf80b178739039962045_1051.png)

Okay， we could work on better levels。I think I'm going to do that next time。

I just want to do like half more hours programming。Or we could do like Mara stuff。

Screen Sha makes our live animation。Review the size and the player rock collision and then sound to that make the size have a Dt。

 I think I'm going to do this。But that's important enough。系。I wrote that like。Start transition。

Because I think that's important enough。That I take some time to。



![](img/1850b42de83cdf80b178739039962045_1053.png)

🎼Throughve that so。Well， second of all， if we move our mouse really fast and exit the window。



![](img/1850b42de83cdf80b178739039962045_1055.png)

What a low frame rate。That' because of polling。That'll be more problematic。嗯。mouse这 mouse。一批。

They calculate the mouse TP， every frame。By getting the current。Nowice's pointer。Subtracting that。

With the screen center。Andlocking that back to the screen center。Not sure that's very reliable。

Let's do a print to the2I。And， let's。See those values。To me， it'd be hard。2。

Figure out what's going on。So。你确认了我。喂啊。The2， eye。Well。Copy this guy。能 change。二 two。哎。Number。He2， I。

社区。就哎。And now we could add text messages， but I'm not going to bother doing that。B I in case。UVQI。

对请说。Number。B2， I fell dot X。t。This guy。This guy won。Then I'm going to draw same thing。

 but with a added why so I'm going to do。At V2 Y， I don't know if you have that。Well。

 I was just happy to he。Let's do six。ok。😊，Then，We try to beat you。Bye。Ms区。



![](img/1850b42de83cdf80b178739039962045_1057.png)

2， eye。安器。Okay， zero and one。So this is wrong right off the bat。



![](img/1850b42de83cdf80b178739039962045_1059.png)

Going to。Change。

![](img/1850b42de83cdf80b178739039962045_1061.png)

but I'm just going to see the behavior again， like it should be even worse， yeah。Worse。

And this is still pretty。🎼So。For some reason， I still are chaos。Let's see。 our mouse， D P 0 and one。

 because our mouse pointer。this guy in our screen center。嗯。Let see。 The rock。It's。50，6，3，78。

And then we change the why。哦。We're not doing the。

![](img/1850b42de83cdf80b178739039962045_1063.png)

That's weird。 We're not doing the。嗯。Client direct thing。Why are we not doing that？That's， oh。

 I suppose we don't care about that anymore。Because we were getting the relative。

Position to the center。That looks really error prone。AndI'm not sure I' big yeah， this is just wrong。

So。

![](img/1850b42de83cdf80b178739039962045_1065.png)

C。

![](img/1850b42de83cdf80b178739039962045_1067.png)

![](img/1850b42de83cdf80b178739039962045_1068.png)

![](img/1850b42de83cdf80b178739039962045_1069.png)

Were numbers。 Were number， please。Let's just add like 10。



![](img/1850b42de83cdf80b178739039962045_1071.png)

🎼Oh。

![](img/1850b42de83cdf80b178739039962045_1073.png)

We are setting the cursage to the center。Why。And we're subtracting that to the central Ryan。

And the center。Yes。Center up the rectangle。So I suppose the correct calculation here will be erect central Y。

Mus this。

![](img/1850b42de83cdf80b178739039962045_1075.png)

Well， I suppose it's the same thing as the buffer pin。These numbers look pretty decent at same game。

Same thing， but we've got a lot more。If something tells me the problem is not weak， which is。

🎼I really， I suppose。

![](img/1850b42de83cdf80b178739039962045_1077.png)

Let's go back to where we were doing。 I mean， it's not perfect， but it's。



![](img/1850b42de83cdf80b178739039962045_1079.png)

First。

![](img/1850b42de83cdf80b178739039962045_1081.png)

YeahAnd that's started debuging the play movement。

![](img/1850b42de83cdf80b178739039962045_1083.png)

Let's draw the player。Yeah， the target fee is wrong。



![](img/1850b42de83cdf80b178739039962045_1085.png)

So I suppose that's a little bit better， so the target。P。Iose this might be wrong。

Why am I dividing by the DT， the DT is how much you moved last frame？



![](img/1850b42de83cdf80b178739039962045_1087.png)

That's super wrong。

![](img/1850b42de83cdf80b178739039962045_1089.png)

Yes。

![](img/1850b42de83cdf80b178739039962045_1091.png)

I don't get it。I don't get it， do you guys get it？🎼The player， D T。



![](img/1850b42de83cdf80b178739039962045_1093.png)

That's。Thats the whole thing like。We got the mouse world。Which is a speed multiplier。Right。

Times clamp old because it's clamped。That's fine。

![](img/1850b42de83cdf80b178739039962045_1095.png)

So at low frame rates。🎼Okay。Okay， we wereclaimed before we were correct。I mean。

Not correct in terms of size and sound。Let's suppose the sound and the size。



![](img/1850b42de83cdf80b178739039962045_1097.png)

🎼I'm not going to be 10% correct， anyways。Because they use。They slowly move towards the goal。

Although， we do consider the DT。But yeah， he we can take out this guy。Pretty confidently so。Progress。

 so in the mouse world。里皮。It's inverted， we inverted。

 then we set the desired fee to be the target plus so to target the old one。

And the desire isn't the work。Do test collision。That's pretty much everything out spring is a bit problematic。



![](img/1850b42de83cdf80b178739039962045_1099.png)

Yeah。

![](img/1850b42de83cdf80b178739039962045_1101.png)

🎼I am really。I'm really shocked at how low。They transparent the rectangles are。

It's like almost like I want to do a little bit of investigatingigating like。

If I if I sort this is low part。Presumably。Yeah， we do like dog product and subtraction stuff。



![](img/1850b42de83cdf80b178739039962045_1103.png)

Like， if we don't do the alert。I see what influence it？Fil alert。Yeah， I go to like 21。You were like。



![](img/1850b42de83cdf80b178739039962045_1105.png)

🎼22。🎼穿一下。Yeah， we got one meise second。And doing this looks or yeah。Speaking。

But I suppose the biggest problem is here， let's see if we can optimize that。

This we just do casts and we these got。Then we subtract this guy。

From all these guys do three relative of guys。And we dot product。Yeah。Yeah。

 we're going to have to speed that up。A lot。Not sure what we should do in the meantime。



![](img/1850b42de83cdf80b178739039962045_1107.png)

Maybe we should just take them out。阿是。😊，And we are still really slow because of the overdry supposes。



![](img/1850b42de83cdf80b178739039962045_1109.png)

Alway it's because of the text text， but this is like acceptance speed and we are not。

And we are not up。Ms that？

![](img/1850b42de83cdf80b178739039962045_1111.png)

![](img/1850b42de83cdf80b178739039962045_1112.png)

Yeah， well。6 seconds。 Oh， we're doing。

![](img/1850b42de83cdf80b178739039962045_1114.png)

Point2。So two。This is， this is nice。If we don't like do anything。6 is what we got， what we have。

If we draw the big large rectangle。Go to 。7。But it's okay， I suppose。

 but these two guys do they are crazy slow。I may have to change priorities。



![](img/1850b42de83cdf80b178739039962045_1116.png)

![](img/1850b42de83cdf80b178739039962045_1117.png)

Like each one of them。Each one of them is like8 milliseconds。



![](img/1850b42de83cdf80b178739039962045_1119.png)

Just draw the at。I don't know。I don't know。We do like four dot products。



![](img/1850b42de83cdf80b178739039962045_1121.png)

And that's not that many pixels， I think。

![](img/1850b42de83cdf80b178739039962045_1123.png)

![](img/1850b42de83cdf80b178739039962045_1124.png)

Yeah， I suppose we're going to have to do that next time， but I don't know is that that ugly？

Should we up to mind just for this case？We could make that a dead map。🎼Which would they。



![](img/1850b42de83cdf80b178739039962045_1126.png)

Just for the sake of comparison。

![](img/1850b42de83cdf80b178739039962045_1128.png)

Let's try making that a bit map。

![](img/1850b42de83cdf80b178739039962045_1130.png)

Let's do a 64 by 64 with man。

![](img/1850b42de83cdf80b178739039962045_1132.png)

And let's do， well， that's not going to be very precise。行。Let's see what we have now， breakout data。



![](img/1850b42de83cdf80b178739039962045_1134.png)

Correct。Then， in the studio hold。

![](img/1850b42de83cdf80b178739039962045_1136.png)

哎知得好。Sa。来下。It's called that green。Then I'm going to do。没有。Green。Half racked。

sThat really what I called it。Okay， now still doing this。Going to draw。Same position， same。

 same things。But I'm going to draw a bit map。いたってね。And I'm not sure。It takes。To main parameters。

 So take。Position a F size。Athle takes a collar。

![](img/1850b42de83cdf80b178739039962045_1138.png)

爱奇。😊，And it's still pretty slow and it looks pretty bad。Because of the way we sample。

We don't do biline。I don't know， man。I don't know。 I think I'm gonna。

Make these guy like this and our。I'm going to change priorities， yeah， like I said， or try to save。

And we're going to make these guys and next time we're going to do。



![](img/1850b42de83cdf80b178739039962045_1140.png)

We'll go optimize record。Thatll be a correct exercise。Let's look for a color。Just try this color。



![](img/1850b42de83cdf80b178739039962045_1142.png)

that green was wayous strong。

![](img/1850b42de83cdf80b178739039962045_1144.png)

![](img/1850b42de83cdf80b178739039962045_1145.png)

Its a bit better。Let's。Theけ。I stake out the player。



![](img/1850b42de83cdf80b178739039962045_1147.png)

Rectangle。Stick out the green thing。Okay， I see the green thing from here as well。O。😊，Let's see。

 yeah。

![](img/1850b42de83cdf80b178739039962045_1149.png)

So pretty slow。Let's just just so we don't lose the。



![](img/1850b42de83cdf80b178739039962045_1151.png)

Let's try give an optimizeimized build， let's see。

![](img/1850b42de83cdf80b178739039962045_1153.png)

well。

![](img/1850b42de83cdf80b178739039962045_1155.png)

11。My Charlie bed。

![](img/1850b42de83cdf80b178739039962045_1157.png)

， I think we can get like。We're going to do Cindy and parallel programming on on that guy。

 Let's try building a non developer building。

![](img/1850b42de83cdf80b178739039962045_1159.png)

![](img/1850b42de83cdf80b178739039962045_1160.png)

Does our council。

![](img/1850b42de83cdf80b178739039962045_1162.png)

Yeah。This is really wrong I suppose。I am enjoying the way it's turning out。🎼会手。

Why did that go so slowly？

![](img/1850b42de83cdf80b178739039962045_1164.png)

🎼C哦。Okay， we changed。Okay， so does low ball。Let's fix that。Well， we're fixed。The player。P。

 S low frame rates。And then呢。Now this is less important， so I'm going to do just go back。To it here。

The weird slow ball， I think we can solve that now because I think the problem was we changed。

The fixed ball p thing。 And I think we wonder if we copy that wrong。 So for next time。

 I think we're going to do like optimization， so。周哥呢。Yeah， we're not going to。

 we're going to do a full screen just to see how really this lower program is。A profiler。

I think we can do a small profiler， but。Yeah， we're going to do the engine optimizations。

AFloating point color is going to make it faster also。

So that would be for next time optimizing the render， that'll be cool， I think。

And then the A called G G reader， we can do that next。Sa and quit。Yeah。

 I'm going to focus on the game a because if we can't have consistent。

Frame rate they'll be hard another thing that we should do before we do like the better levels is this guy。

 which is kind of a kind of。very interesting， but。But we do have to fix that so。

I'm going to do this later on。Just a player。 Make the player size。Have a D like redo player。

It can have a D， maybe。Takeigs that of absolute frame rates。Okay， now let's。

I think the best way to solve that bug。Is to go and see the diff in our。Let's see。 we have。Have a。

Levels， and let's just if that， let's see what changed since we。



![](img/1850b42de83cdf80b178739039962045_1166.png)

Mess around it。Yeah， so we took the arrivals， that was the problem， I suppose。Yeah。

 it took all the way those flags， we took the collision test flag。Okay， if the balls reverse。

 if the ball speed is fixed。Do that。Yeah， see， that was wrong， We're supposed to do this。



![](img/1850b42de83cdf80b178739039962045_1168.png)

We said in a verse， yeah。Reset。

![](img/1850b42de83cdf80b178739039962045_1170.png)

And reverse， got the wrong branch。 Okay， branch of the if。If the ball is fixed。

So we're not going to do this process。

![](img/1850b42de83cdf80b178739039962045_1172.png)

ball wouldn deep be down。And then， we can calculate that。Remove the calculate。



![](img/1850b42de83cdf80b178739039962045_1174.png)

Let's see what else。So now。We've got this part of the branch because the ball speed was not fixed。

 that is correct。Deileated this guy， removed this guy because boss beat's not fixed。Yeah。

 this I think we don't really care。Okay。😊，I liked that。Let's see now， rivalry， okay。Yeah。Oh。谢大家。



![](img/1850b42de83cdf80b178739039962045_1176.png)

Stadium， okay， now。Okay， now let's play and C， I think we fixed it the rear slowball bug。



![](img/1850b42de83cdf80b178739039962045_1178.png)

It' would been nice to optimize that and it'll be hard too。Optimizing is hard。

But a good learning exercise。I's way back。

![](img/1850b42de83cdf80b178739039962045_1180.png)

W。Let's go back to the。Development mode。

![](img/1850b42de83cdf80b178739039962045_1182.png)

Be bit optimistic。い。Yeah。

![](img/1850b42de83cdf80b178739039962045_1184.png)

Dude。Another collision problem， Ire kidding。

![](img/1850b42de83cdf80b178739039962045_1186.png)

I thought so I suppose we didn't solve the prediction problem， dude。Oh， that's not fun。Oh。

 collision problem。Was that maybe it's because it's been quite a lot。

 a long time group've been streaming。

![](img/1850b42de83cdf80b178739039962045_1188.png)

So we're going to have to take a look at that， it looked pretty much the same collision problem we had before。

う。So I suppose that didn't work。 I not sure now if we should keep。

When we did try to solve the collision problem or not。But the game is turning out pretty quick。Nice。

🎼なし。Go back to the menu now。🎼Okay。Oh， today was a good day， a lot of people stuff。

Just because of the very amt， we had a collision problem back，That's always not fun。哦，那我查一。🎼Yeah。

But it is pretty cool。🎼Yeah。It's still pretty hard to get the ball behind it。

And that has to be one of the major goals this ever need because that's fun。

That's the interesting thing about this level Yeah， I like this， see。啊。Right。Yeah。That was great。🎼メス？

A lot， hard。没。🎼Yeah。来不事。'sHard， not that interesting。But it's interesting because。It's like。

The first。Taste。I was comments release。大好ス。Spsy dinners are like just crazy white。

Theres a small problem。That if you don't， if you let the ball。F the ball kick off the ground。

The score multiplier doesn't reset。As suppose that's a mistake。



![](img/1850b42de83cdf80b178739039962045_1190.png)

I'm going to change that。That was pretty cool so pretty quickly and then I suppose we're going to call that and end up today screen just going to try to fix that so。

That's about collision。No。あ。update包。I balls， the ball hit like the bottom。In the arena。

If we do have invincibility。We should actually do the same thing as if the ball had hit the player。

And， let's say。Which is。So。Search those button。Okay。



![](img/1850b42de83cdf80b178739039962045_1192.png)

Let's just make a quick test。嗯。That's pretty cool。seeIt's hard to see for you。

We could make like stronger tests whether or not we。Weet it。I think we can trust that particle。

heard that before， right？Yeah， I'm not going to replaylay that to。Well， let's see。

I think you've got a nice brother today， look at that。I say that every stream。

 but it's starting to look like a game。😊，オケー。

![](img/1850b42de83cdf80b178739039962045_1194.png)

Yeah。😊，So next stream， we are going to fix a couple of problems， probably。And then work on。

 let's do like the full screen， the profiler。40 point colors。And then like。Optimize。

I should like1 print colors。I think。性别。Those are the three things we're probably going to do。Okay。

 so I hope you have enjoyed this stream as much as I did。We are coming to and then， I mean。

 not in terms like an immediate end。

![](img/1850b42de83cdf80b178739039962045_1196.png)

But it is coming along nicely and I wanted to make a cool game。

 and I think this turned out to be a cool game。

![](img/1850b42de83cdf80b178739039962045_1198.png)

I think so if you want to download the game and the source code for free， you can go to my Ho。

 which is Danzadan dot h。tio。

![](img/1850b42de83cdf80b178739039962045_1200.png)

If then you can download the the game， you you just click here and you can download the game and the。



![](img/1850b42de83cdf80b178739039962045_1202.png)

In the source code for free， you can download the source code， play around with it， increment it。

 learn from it， whatever you want to do。

![](img/1850b42de83cdf80b178739039962045_1204.png)

And you can also watch the whole thing on YouTube。 So if you go to my YouTube。

 which is user dot com slash damn， say Dan。Well， dance they dance。

You can watch the whole process from the very first line of code all the way to where we are now。

 which is it was a lot of cool stuff we did a lot of cool stuff。Of of。Features see。

 this is how the menu look like two episode。And I think we are coming to a nice conclusion of the series。

 I mean， itll still be like 10 episode those left， I think。But which is like 40%。But30%， yeah。

Pretty cool， so。

![](img/1850b42de83cdf80b178739039962045_1206.png)

I'll see you next time， I suppose and have fun programming to them。 See you later。😊。



![](img/1850b42de83cdf80b178739039962045_1208.png)