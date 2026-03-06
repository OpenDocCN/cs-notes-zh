# 【从零开始用C语言制作游戏】 p08 Making a game in C from scratch! Ep 08： -Programming a Particle Sys -BV18i421a7DD_p8-

Hello everybody， welcome to my new live stream where we are creating an entire game in C from scratch you guys are seeing everything from the very first line of code through all the gameplay changes。

 all the little animation things we are doing these bass streams all the way to hopefully the game release so I hope you were enjoying it I certainly am and I was rewatching some of the older streams and I was thinking that we came a long way already I mean we have seven streams。

😊，Around two and a half hours each， three hours sometimes and。Yeah。

 the game is starting to get a lot of fun and you can watch everything in YouTube because you missed some of the streams yoube。

com/danay Dan。There's this main playlist here watching making a game see from scratch。

 there's also like little clips that I'm doing like from the best moments。

And that's pretty cool and actually I just took the time to reorganize this playlist on my YouTube channel。

 which was the creation of the my game Elios's Hunt。

And it's pretty cool because you see the very first video I created when I was just by myself making this kind of a quiet idea and I wanted this alien game。



![](img/13f3c34aeca4e45732e15609ba01749b_1.png)

All the way to the PS4 release。Of the game， so yeah。

 that's the game trailer and the P is the PlayStation channel。

So that was pretty cool to organize that and see the whole thing so we can watch all that as well as the live stream that we are creating。



![](img/13f3c34aeca4e45732e15609ba01749b_3.png)

Okay， if you want to download the game and its source code， can go to Ho， which is dayd。h。

o and I click the first game your breakout kick games out。



![](img/13f3c34aeca4e45732e15609ba01749b_5.png)

And you can download the last episode it's executable if you' want to play around with it and the source code。

And if you're want to follow along programming， that'll be pretty cool。

 so let's see where we left off。

![](img/13f3c34aeca4e45732e15609ba01749b_7.png)

![](img/13f3c34aeca4e45732e15609ba01749b_8.png)

We started to add some gameplay polish like we did a ball trail。And we started doing， you know。

 like we did player squash and stretching， we did wall animations。

 and we fixed a lot of gameplay bugs， but you know I was replaying that offstream。

Just to get a little fuel for the game， we added a few bugs last stream as well。

 so we're going to have to fix that to。Wow， this sounds to look pretty cool。Yeah。

 and the main thing that I realized， I actually， I may have to look at my notes here。Because。呃。Yeah。

😊。

![](img/13f3c34aeca4e45732e15609ba01749b_10.png)

The main thing。Was that。Here， okay。Yeah， the first thing that was big bug when we hit the ceiling。

 I don't know if you guys remember last time around when we hit the ceiling。



![](img/13f3c34aeca4e45732e15609ba01749b_12.png)

A lot of balls with a lot of balls， the students are dropping and we didn't realize that at the time。

 but it's pretty clear now what was going on when I rewatched the stream。

Which was when it had more than one ball， the singing went all crazy， so we have to fix that。



![](img/13f3c34aeca4e45732e15609ba01749b_14.png)

I think I'm going to start with that。And then we can do like other problems like I'm going to tell about the other problems we're going to get to them。

's let's just load the load the four color project， Let's start solving。



![](img/13f3c34aeca4e45732e15609ba01749b_16.png)

That weird top getting down， but I don't know that's what I would inscribe it。Okay， so we do the。

Arena。Top wall， yeah。When we add the visual DP。This is problematic。When we do with the three ball。

 so let's create a more controlled scenario for that。I'm going to。

Not on the block block guy orll make out。Yeah， I'm not going to find the black black。And then。

 in the。3 shots。Tle shots。We a number of triple shots， can start with line of 10 triple shots。



![](img/13f3c34aeca4e45732e15609ba01749b_18.png)

![](img/13f3c34aeca4e45732e15609ba01749b_19.png)

So hopefully we're going to get a triple shot and a bug。

 let's see if Ken we those that why didn't we get the triple shot？



![](img/13f3c34aeca4e45732e15609ba01749b_21.png)

I think I think I zero that。Yeah。So。え。Yeah。Reset power。Okay， triple shots。 Let's do 10 triple shots。

 and let's see。

![](img/13f3c34aeca4e45732e15609ba01749b_23.png)

If we can reproduce the bug。

![](img/13f3c34aeca4e45732e15609ba01749b_25.png)

Yeah， and we do reproduce。Recursive chat。Damn， damn， my man's say damn。How are you doing， man？



![](img/13f3c34aeca4e45732e15609ba01749b_27.png)

And just that's the crazy way we have to fix now。And that's going on。



![](img/13f3c34aeca4e45732e15609ba01749b_29.png)

Apparently。When more than one ball hit or maybe yeah， I'm going to guess the trick shot ball。

 not actually destroying。Let's use our print system， I forgot about that。

 let's use it just make sure or you're doing like the arena top。Yeah， let's do a print。



![](img/13f3c34aeca4e45732e15609ba01749b_31.png)

Just to make sure。That's been calling more than once， which is what we suspect see。



![](img/13f3c34aeca4e45732e15609ba01749b_33.png)

It be like every frame for that。 So apparently the ball。Are running that so。Okay。

 I remember now about the problem where we added。

![](img/13f3c34aeca4e45732e15609ba01749b_35.png)

We continue to do this loop even after the ball disappears to continue to see the particle trail。



![](img/13f3c34aeca4e45732e15609ba01749b_37.png)

Yeah。But this thing should be done。Yeah， earlier， as I'm saying here， so yeah。

 if the ball is not active， we continue。But the ball is active， I suppose。If I remember that。

Correctly。Maybe yeah， I no， I think I'm just getting confused。LetLet's see the ball active。

I don't know my brain kind of paged out the programming， so for each ball。

 if it's not active and it's yeah。See so the balls are still active。嗯。Yeah， see。Well。

 not sure this is the best call， though。Let's say。好。Yeah。😊，I think I'm just going to set。

As ball active。Like here。Process fallinging DP down， I know this is kind of weird。

Let me just let me see if you can fix that by just hacking this in and you can think about that a little bit more。



![](img/13f3c34aeca4e45732e15609ba01749b_39.png)

So this is just making the ball not。

![](img/13f3c34aeca4e45732e15609ba01749b_41.png)

Consider that。 So yeah， it still doesn't fix it。

![](img/13f3c34aeca4e45732e15609ba01749b_43.png)

I think I'm going to set a breakpoint here， so we are on the game。Let's go to the game。8。16。It's 16。

Okay， let's play the game bit。Great point。Okay out， that didn't do。Some reason。Crack。

 let's try that one more time。Okay， let's see at where we are at， so the silly is problematic。

So we have。First ball set to active， right？Okay。Let's see the other ball。Well， at this point。

 we only have one ball。

![](img/13f3c34aeca4e45732e15609ba01749b_45.png)

Update。Not sure， well， we can put a breakpoint in the here I suppose。



![](img/13f3c34aeca4e45732e15609ba01749b_47.png)

In here。那し。So yeah supposed to be called it twice， one fridge calls one， two。Okay。

 so being calling an， oh， maybe this is the third ball， yeah， this is the third ball。and again。

So let's see what ball， yeah， it's not that first ball， the other ball is。So it is said to active。

And。It is set the other flag， which is the。Let's just check this out。Just a ball to and why， see。



![](img/13f3c34aeca4e45732e15609ba01749b_49.png)

Which is weird， this is two okay。This is just a typo。It's supposed to be like this。



![](img/13f3c34aeca4e45732e15609ba01749b_51.png)

Okay。

![](img/13f3c34aeca4e45732e15609ba01749b_53.png)

Yeah， typo bugs there。Okay， perfect， they're not fun， but as long as it's simple to resolve。

 I'll take that。😊。

![](img/13f3c34aeca4e45732e15609ba01749b_55.png)

Okay。So we finished that problem， I mean the other ones that I realized was。The code order。

Is causing。The call to collide。With space invaders。But not destroying it。I'm just going to type that。

 I'm going to analyze that later on trying to get a re case。I'm just going to copy actually。

 and appalling enemy guy and space invaders should use， yeah。

 we're going to do this one pretty quickly， visual problem。With running， so we've fixed this problem。

At a fast spring read， yeah。This one pretty bad and the code orders is causing a call to coli with space emit。

 but not destroy trying。Yeah， this one's going to be pretty bad。



![](img/13f3c34aeca4e45732e15609ba01749b_57.png)

This one's pretty easy。

![](img/13f3c34aeca4e45732e15609ba01749b_59.png)

We have like the space invaders let's let's try to do a palm guy， so oh industry also。

You should also not do this， this is really cool now。We should actually。



![](img/13f3c34aeca4e45732e15609ba01749b_61.png)

You know what？And we forgot to remove the triple shot。The esymmetric shot， the used for the buggy。

But that was pretty close， I'm going to note as an idea。Like。A reward。Player。With。Power ups。不杀。

Go school。When。When he gets like X。ScoreI don't know， that was pretty cool fighting along with that。

Poong enemy guy and space invade should use the arena left Yeah。

 you know that's pretty easy to and I'm going to try to show you guys again but。



![](img/13f3c34aeca4e45732e15609ba01749b_63.png)

![](img/13f3c34aeca4e45732e15609ba01749b_64.png)

That was pretty easy。Yeah。啊。I don't know why I he forgetting to compile the code。



![](img/13f3c34aeca4e45732e15609ba01749b_66.png)

It's been happening a lot。Or maybe I'm running too fast to thinking that's the problem。



![](img/13f3c34aeca4e45732e15609ba01749b_68.png)

So let's see the problem is。When the wall move moves， right， when the wall moves。Well。

 I think it's going to be kind of hard to report that。But well。

 she't have to worry too much about that。 When the wall moves， the pondong guy in a simulate level。



![](img/13f3c34aeca4e45732e15609ba01749b_70.png)

And the Space invade want are using the arena。Have size。Yeah， and it's basically bes here in it。Yeah。

 let's do pump first， so the pun guys， yeah， it's specifically that I don't think they matter much。

The punong guys are going to try to collide with the arena， let's say if it's greater than the right。

比如。And if it's less than their left。Usrual， and we can remove that minus。Okay。

 and can move dot access route。

![](img/13f3c34aeca4e45732e15609ba01749b_72.png)

Okay。Now it should be。Good to go again。Well。I don't think that changed much。Oh。

 because we're not actually pushing him， yeah。

![](img/13f3c34aeca4e45732e15609ba01749b_74.png)

Oh， I don't know。Okay， yeah。Here。Yeah did just half the job for the half size。



![](img/13f3c34aeca4e45732e15609ba01749b_76.png)

Okay。Let's try that one more time。

![](img/13f3c34aeca4e45732e15609ba01749b_78.png)

Dude。

![](img/13f3c34aeca4e45732e15609ba01749b_80.png)

Okay啊。Yeah。

![](img/13f3c34aeca4e45732e15609ba01749b_82.png)

Okay， let's do that again well， but I think this starting to come up cool game we're going to do particles today that's for sure particles are。

Really cool。And like maybe I destroy block animation。That would be cool， too。Yeah， look at that。

 That was awesome。 that's right the right side。😊，That was pretty cool。

 everyone's getting pushed by the wall。Yeah。Awesome， okay， now the spacing there。

 let's see where we are in the arena have size again。



![](img/13f3c34aeca4e45732e15609ba01749b_84.png)

So we set that up。Okay。You got the middle point， but that's only for our creation， raw movements。

 yeah， the raw movements。Yeah， no， this is just for drawing that a little UI thing。

So I think that's it， I think the space invaders。Or maybe they're hard coded。Like space。Ss。Evaders。

Is the same level。Yeah， we try to collide with， yeah， it's hard coded。

I think that's okay for now we can prove that from the space invades， but with this pond。

 which was great。😊，Okay。These row prompts are running out of fashion。 Okay。

 so when I go to publish the game the build on HIO， I hearing the build dot that I add a minus02。

Just so it's optimized and yeah， we have this warning I can disable that。



![](img/13f3c34aeca4e45732e15609ba01749b_86.png)

オ。So if you guys see， there are few visual artifacts in the game， the first one。

Is the player size calculation， I think the player pray， the play movement is correct。

But the size is not correct， so that's the first problem。The second problem， which I forgot。



![](img/13f3c34aeca4e45732e15609ba01749b_88.png)

What was the problem？

![](img/13f3c34aeca4e45732e15609ba01749b_90.png)

At running trail， yeah， in the trail， the trail is different。Sureb take a look at that， yeah。



![](img/13f3c34aeca4e45732e15609ba01749b_92.png)

So maybe you can compare the yeah， that's to the player first， so when you calculate the spring。



![](img/13f3c34aeca4e45732e15609ba01749b_94.png)

We also do the size， right， yeah， but have signs。So I think this squeeze factor is not taking into account thelta time。

 I suppose that's the problem。Let's see we' are calculating the squeeze factor。

 so we are adding the squeeze factor。To the half size， every frame。So yeah。

 I'm going to assume that's the problem。And the squeeze factor。Is yes see。

And discretease factor is the delta that we moved times like a。Co efficient。

But we're not considering the DT like we are in the other cases here。So all we should do really。

 is just oh you should like make that in the squeeze factor。Squeeze factor。Yeah。

 pla's IHp minus squeeze factor。Yeah， never put it。



![](img/13f3c34aeca4e45732e15609ba01749b_96.png)

那可以来起。Part are going to be too slow with the squeeze Oh no it's great， yeah， okay。



![](img/13f3c34aeca4e45732e15609ba01749b_98.png)

Okay， I kind of like that。呃。It's kind of twitchy。

![](img/13f3c34aeca4e45732e15609ba01749b_100.png)

When to move sideways。You see the。

![](img/13f3c34aeca4e45732e15609ba01749b_102.png)

Build up that。I不 seen的。Slow build。No opt。Now this one's this one's pretty cool， yeah， so it's not。

It's not working yet。我写的看长时间。We move I think the positions wrong， Yeah， maybe this guy's also wrong。

 yeah。

![](img/13f3c34aeca4e45732e15609ba01749b_104.png)

So I'm going to bake that DT in。So the squeeze factor is going to be this times the DT。



![](img/13f3c34aeca4e45732e15609ba01749b_106.png)

![](img/13f3c34aeca4e45732e15609ba01749b_107.png)

嗯。Oh， this may be problematic。

![](img/13f3c34aeca4e45732e15609ba01749b_109.png)

That me print to the squeeze factor。可以。And screen factor。And they're going to multiply that by。はい。



![](img/13f3c34aeca4e45732e15609ba01749b_111.png)

We should do like a print float pretty soon。嗯。

![](img/13f3c34aeca4e45732e15609ba01749b_113.png)

Well， it says it's 0。

![](img/13f3c34aeca4e45732e15609ba01749b_115.png)

Oh， I think because we're multiplied by the DT so it's pretty small。I don't like that。Not unopized。

Okay， yeah， we are getting a a few values。嗯。

![](img/13f3c34aeca4e45732e15609ba01749b_117.png)

Yeah。That's you like if。Let's just。P the print here。 Were only printing if we。Do we have a squeeze？



![](img/13f3c34aeca4e45732e15609ba01749b_119.png)

So no squeeze factor， and if we move a little bit， oh， we still don't have a squeeze factor。



![](img/13f3c34aeca4e45732e15609ba01749b_121.png)

嗯。Maybe that's the problem。But we still。Okay。So we were looking at the wrong culprit。

 let's put it that way。The squeeze factor， I think， also should be considered the DT。

 but this guy absolutely should be considered for the DT。



![](img/13f3c34aeca4e45732e15609ba01749b_123.png)

And then there's probably you know。嗯。

![](img/13f3c34aeca4e45732e15609ba01749b_125.png)

Yeah。Yeah， maybe that a lot， maybe it made it a lot bigger。



![](img/13f3c34aeca4e45732e15609ba01749b_127.png)

Okay。

![](img/13f3c34aeca4e45732e15609ba01749b_129.png)

Maybe still needs to be bigger。I don't maybe that。Itちで。



![](img/13f3c34aeca4e45732e15609ba01749b_131.png)

Yeah。Of course， the problem is not。Not the D per se。🎼Although。It is problematic。But。

With the code itself。

![](img/13f3c34aeca4e45732e15609ba01749b_133.png)

At least we've got the same result， okay， but now let's try to understand what the problem is。

We are multiplying。T0， which is like the Bays guy。Times the。



![](img/13f3c34aeca4e45732e15609ba01749b_135.png)

The target Dp。And for some reason。

![](img/13f3c34aeca4e45732e15609ba01749b_137.png)

It's like guess。嗯。Let's print that。

![](img/13f3c34aeca4e45732e15609ba01749b_139.png)

Okay。This is not good seat。We're getting zero for a lot of frames。



![](img/13f3c34aeca4e45732e15609ba01749b_141.png)

Let's it targets DP。This is collision， right？Yeah， player a more collision。

Where is that being calculated？Pay target。一皮。It's a very desired P。Mineus the player target Px。

You write it by the DT。That looks kind of right。

![](img/13f3c34aeca4e45732e15609ba01749b_143.png)

![](img/13f3c34aeca4e45732e15609ba01749b_144.png)

That still like。Yeah， well， this looks right， I think。But。Let's try。To print that down there。Yeah。

Okayそ。差解。It's the desired P。Mine is a target。皮。I think for sume purposes。

 this may be wrong this calculation here， we draw the player at the visual P， yeah。And the visual P。

The target P is the desired to P。

![](img/13f3c34aeca4e45732e15609ba01749b_146.png)

So maybe， yeah， all that can just nature sure I think there's going to be the same result。



![](img/13f3c34aeca4e45732e15609ba01749b_148.png)

Yes， same result。I think this is going to be the player usual。



![](img/13f3c34aeca4e45732e15609ba01749b_150.png)

![](img/13f3c34aeca4e45732e15609ba01749b_151.png)

Yeah， I think this is more correct， I mean， the values are really high。And the DP。



![](img/13f3c34aeca4e45732e15609ba01749b_153.png)

Yeah， that's clear around with the values。Let's like， go back to。よ。感よ。



![](img/13f3c34aeca4e45732e15609ba01749b_155.png)

Dude。That is really cool。And because the position gets oh we lost。

The lost our squeeze factor were going to go against the wall。

But the way we move both the position and。They way with both the position and the size。

When we do like quick movements。We get like an awesome follow through effect。Really jelly。



![](img/13f3c34aeca4e45732e15609ba01749b_157.png)

really cool。I liked that。呃。But we lost our squeeze factor when we were against the wall。Maybe yeah。

 things just gets really small， so we're going to apply that let say much。



![](img/13f3c34aeca4e45732e15609ba01749b_159.png)

Because I'm multiplying that by the DT。

![](img/13f3c34aeca4e45732e15609ba01749b_161.png)

Yeah， I think it's trying to move。

![](img/13f3c34aeca4e45732e15609ba01749b_163.png)

Even more。

![](img/13f3c34aeca4e45732e15609ba01749b_165.png)

![](img/13f3c34aeca4e45732e15609ba01749b_166.png)

Yeah。

![](img/13f3c34aeca4e45732e15609ba01749b_168.png)

That was that was too much。Yeah， and I think I'm going to have to review this squeeze factor thing。



![](img/13f3c34aeca4e45732e15609ba01749b_170.png)

ca。It's twitching a lot。Yeah， and we've got that problem， yeah， I think I'm going to do that now。

We should also like at a minimum。

![](img/13f3c34aeca4e45732e15609ba01749b_172.png)

For this guy， like。嗯，sorry。

![](img/13f3c34aeca4e45732e15609ba01749b_174.png)

Just we don't get like。Like this。Okay， this is looking good。

 That's just before we fix the squeeze thing， let's just make sure。

We look good with a lower frame rate。And we do， it's pretty much the same thing。



![](img/13f3c34aeca4e45732e15609ba01749b_176.png)

Except for the squeeze， thing。

![](img/13f3c34aeca4e45732e15609ba01749b_178.png)

Yeah。This ch thing is broken at a lower frame rate。



![](img/13f3c34aeca4e45732e15609ba01749b_180.png)

So let's try to de what the problem is。We're adding the sch factor here。

The discrete factor is the DT。嗯。The squeeze factor。I'm going to add like a sreish factor。

I'm thinking about that in this quez vector。Velocity。Or maybe。Yeah， you know what。

 I'm going to do like this squeeze factor it' going to be like player。Stuff up here。

To do like the players piece venture？Okay。And I're going to keep。Do that。

I don't think I'm going to do a lifetime for DT though。I have to think a little bit more about that。

That's not worry about that。But what we want to do， we want to do like a similar spring thing。

With the squeezease factor。And the thing is， it's going to be some like coefficient。

But want to we have the desired， which is player squeezed， right？But we want to， I'm sorry。

 the desire is zero， you want to get to zero， but right now we are at this guy。Right？So zero minus。

So， we are trying to。Yeah， this is wrong， this is the DP。For the squeeze factor。

 so I think we're going to have to add the squeeze factor DDP。And the Gase Pack DP。

If you are to do that correctly。Or maybe we can just like he。This in one more time。

Let's do this squeeze factor DD。Yeah， okay， so let's say this like 100。You want to get to zero。

And we also going want to get to the zero。Players squeeze factor D。Okay， so that's this。

That's the player's crease factory。リ啲。And we're going to do like the player。It's crazyrey factor D。

So I'm just copying from down here it's going to be like。Yeah， I can do like plus equals。This guy。

Time the DT。嗯。Yeah， and this looks good。 Then I'm going to make this guy plus equals。😊，The this guy。

 the DDT。Times the Dt squared。So。Time have。Plus the D。Time DT。Yeah。

And then I'm going to add the player。Squeeze back。And then here I'm going to add。

Im going to set the player。Squeeze factor D because this。It kind of wrong。

But we're going to actually tune。た。展示一。And。They desired to pe。Well。

 let's not care about that for now， see the effect。

Term does not have any to a function taking 38 arguments， probably not。ふ。Assembly。

 simple plus plus SQl or Python， do you have a job for me， dude？I don't hire， I like a subtle dev。

Sorry。I am a hobbyist game developer that doesn' it because I think it's fun。So I'm not hiring。

 sorry。Which term does not evaluate to a function taking 38 arguments？Yeah you know。

 help me out with this bug dude， I've never seen the compiler complaining about a function taking 38 arguments。

Im creating a variable。😊，Right。And I'm just， yeah。So， I suppose。Literal does not。



![](img/13f3c34aeca4e45732e15609ba01749b_182.png)

Evaluate to a function mode of y， it asks for 38 arguments。



![](img/13f3c34aeca4e45732e15609ba01749b_184.png)

I have no idea。Let's see。Okay， looking good， looking good。And we so fixed。意事。



![](img/13f3c34aeca4e45732e15609ba01749b_186.png)

Yeah， this is nice， but I do want to add the squeeze factor。But I'm not sure what to add。

 maybe the squeeze factor。Just as player a squeeze factor， I think that's it。

This may be a frame delayed。

![](img/13f3c34aeca4e45732e15609ba01749b_188.png)

So， let's see。I can do a quick game。Yeah， that's also fun， man。But it's also fun doing big games。

 right dude， that was super stuck。On the wall。

![](img/13f3c34aeca4e45732e15609ba01749b_190.png)

Oh， because we're， oh， this gets way， way， way bigger。so诶。



![](img/13f3c34aeca4e45732e15609ba01749b_192.png)

Now it was fun to control like。

![](img/13f3c34aeca4e45732e15609ba01749b_194.png)

Yeah， it's still not 100% smooth， Yeah， see。I have to face that。



![](img/13f3c34aeca4e45732e15609ba01749b_196.png)

But it is getting pretty cool。You going to have to clean this up annually。

Part goal of is to avoid size changes to make the collision feel solid。Yeah， well。嗯。

Maybe I'm just going to。Add the target DP to like。This guy。So you can add like a little bit of a。



![](img/13f3c34aeca4e45732e15609ba01749b_198.png)

We accelerate to the wall， but we don't get like super stuck。



![](img/13f3c34aeca4e45732e15609ba01749b_200.png)

I don't know， I don't like that。Maybe I should just hardcode something like this。Lalayer half size。

 y。Size y。Like 10% of that。And I still want to make the。Oh， I was adding both。



![](img/13f3c34aeca4e45732e15609ba01749b_202.png)

Okay。So I'm not sure how。Yeah， I see， I think this's going to be the best solution。Yeah。



![](img/13f3c34aeca4e45732e15609ba01749b_204.png)

But maybe a little bit more。

![](img/13f3c34aeca4e45732e15609ba01749b_206.png)

Yeah， but yeah， I think it's going to be good because I want to mess around the player speed。

 things like that。

![](img/13f3c34aeca4e45732e15609ba01749b_208.png)

But if we build up this lot。Yeah， we're still getting stuck。



![](img/13f3c34aeca4e45732e15609ba01749b_210.png)

7年。I want to get stuck in this kind of thing。

![](img/13f3c34aeca4e45732e15609ba01749b_212.png)

For too long。So this feels perfect。Except for the position， right。



![](img/13f3c34aeca4e45732e15609ba01749b_214.png)

Maybe you can just not do this。Maybe instead of doing this。We just do the player。

But player your half size X。

![](img/13f3c34aeca4e45732e15609ba01749b_216.png)

Let's see how does that。ok。

![](img/13f3c34aeca4e45732e15609ba01749b_218.png)

That's starting to get wrong。

![](img/13f3c34aeca4e45732e15609ba01749b_220.png)

![](img/13f3c34aeca4e45732e15609ba01749b_221.png)

没于。They they have signs。It's being used。Yes， check the collision。So。I think I'm just going to see。

 I'm going to subtract。The player。Desired pe。Okay， so。I met the wall。

Kind of thinking about that for a while。嗯。We are。 Let me draw that。 We are。 let's see。

This is the player desire of pe， let's say。And then when you set it to the rightmost P。

 let's say like this。Yeah， I think that's the， it's called that di。Pastic， yes。本とです。Okay。Yeah。

But I think I'mre going to end up wanting to do the。

What did you do the scale as also having an acceleration？



![](img/13f3c34aeca4e45732e15609ba01749b_223.png)

But that's not worry about hellello clone style， nice to see you back。 How are you doing？



![](img/13f3c34aeca4e45732e15609ba01749b_225.png)

![](img/13f3c34aeca4e45732e15609ba01749b_226.png)

So the left side was not nice and the right side was upright wrong。Yeah， we should do like。T do。

Oh the ball movement looks great I'm doing how I am doing great too， Yeah。

 last I' around start doing some particle trails。😊。



![](img/13f3c34aeca4e45732e15609ba01749b_228.png)

See， that looks pretty cool as well as some player。Ququaash and stretching animations。

That's also pretty cool， yeah。But we are， we are adding some。Animation。

 when we hit the wall like this， see。so this is。

![](img/13f3c34aeca4e45732e15609ba01749b_230.png)

Yeah， and I think it looks even better。 That's why we will have to fix that in debu mode。



![](img/13f3c34aeca4e45732e15609ba01749b_232.png)

I think this looks even better check this out。Yeah， I think this is like a way better trail。

Because it's more subtle。Yeah。

![](img/13f3c34aeca4e45732e15609ba01749b_234.png)

So for some reason。呃。Adding this to the desired key。

Kind of what makes us go like too much to the right。



![](img/13f3c34aeca4e45732e15609ba01749b_236.png)

![](img/13f3c34aeca4e45732e15609ba01749b_237.png)

Yeah。I think I'm just going to consider the size as the again。



![](img/13f3c34aeca4e45732e15609ba01749b_239.png)

As the offset。 But I have to think about that a little bit more。

Because I actually didn't think about that so it's going to be the player half size。

 but the shorter the player is the more I want to go to the right so the base size， let's say， is 10。

So I'm going to call that base size。They have size， oh， we already have that。

So we're going to use the base。嗯。Yeah， I can remove this stiff kind。So。This。

Just cleaning up some things that we messed up。Okay， this is just some experimentmentation going on。

Okay， now。Let's see， the half size， but I want to see the difference between the player。

The bass player。The base player。Or the guitar player， the bass player。😊，Yeah。

 that's called the base player。These layer half size x。Which is 10。 So if we are smaller than 10。

You should add more yeah。I think it's correct。We go more to the right in this case and we go more to the left。

It you forstruct。Dot X。

![](img/13f3c34aeca4e45732e15609ba01749b_241.png)

K。Pretty good， pretty good now let's see。ok企。

![](img/13f3c34aeca4e45732e15609ba01749b_243.png)

I think we are going to the wrong way。But we're getting somewhere。



![](img/13f3c34aeca4e45732e15609ba01749b_245.png)

I think that is correct， yes。No。We get stuck。Otherwise。



![](img/13f3c34aeca4e45732e15609ba01749b_247.png)

是。😊，The desired P is the right most。Why does this guy keep getting larger and oh。

 it does get smaller， but not that smaller？

![](img/13f3c34aeca4e45732e15609ba01749b_249.png)

Oh man， I think I'm just going to let that。Be kind of not perfect for now。



![](img/13f3c34aeca4e45732e15609ba01749b_251.png)

Yeah， let's just see the difference between。This guy， let's print。请请万。This guy。



![](img/13f3c34aeca4e45732e15609ba01749b_253.png)

So it's 1991， '92， 93。

![](img/13f3c34aeca4e45732e15609ba01749b_255.png)

I don't know why it gets smaller because this。Oh yeah， the size does it gets smaller。I don't know。

 I think I'm just going to leave it like that。

![](img/13f3c34aeca4e45732e15609ba01749b_257.png)

And then we can do like a more robust pass later， it's not like the final look。



![](img/13f3c34aeca4e45732e15609ba01749b_259.png)

Let's see how there is like a limit。Or， maybe we can change the visual。



![](img/13f3c34aeca4e45732e15609ba01749b_261.png)

Not desiredly。 kind of like that。Player 0 P。マイナイコスで使。Yes。

 because they we' not going to keep getting smaller。Okay， I kind of liked that。And。

 let's change this。Lllegal forstruct visual P。x。

![](img/13f3c34aeca4e45732e15609ba01749b_263.png)

O。Okay。

![](img/13f3c34aeca4e45732e15609ba01749b_265.png)

Oh not okay。

![](img/13f3c34aeca4e45732e15609ba01749b_267.png)

I don't know， I'm just。At this point， I'm just kind of desperately hacking things together。



![](img/13f3c34aeca4e45732e15609ba01749b_269.png)

![](img/13f3c34aeca4e45732e15609ba01749b_270.png)

Yeah，' I'm not going to do that for now， I'm going to add Li to do。

We have like a let's see make this squeeze factor also have the spring look。We did that。

So make like a review。The size make kit。可以进き。AD。Yeah， it's not going to be DP for position。

 it's going to be like a derivative， okay。

![](img/13f3c34aeca4e45732e15609ba01749b_272.png)

Yeah。I think I'm going to keep it like that for a while。 So we fix the player in the。



![](img/13f3c34aeca4e45732e15609ba01749b_274.png)

Yeah， we fix the player in the optimized mode。

![](img/13f3c34aeca4e45732e15609ba01749b_276.png)

Oh， but we're not optimized mode。Yeah， but I think we did。Anyways。

We made that frame rate independent where we had to。Yeah。



![](img/13f3c34aeca4e45732e15609ba01749b_278.png)

It's pretty cool。Let's see about the particle life， particle stuff， so visual problems。

5th spring S5 trail so。It may have to do with the trail life。So when we are rendering。We like。

Fridge ball。Or every trail， while it has a life， we draw it。And to subtract to life。Now。

 this looks okay。Let's see when we create a ball trail。Here。Yeah。😊，This is the problem。

When the bone is active。We spawn the trail。Oh， we subtract the time， right in the time we read zero。

 we add。This number， which is probably too small in the debug， so it only spawns once。

So we are planninging a lot of part， so part do I have to do like while。Yeah。

 I think that's the only chance now it's going to look bad in both。



![](img/13f3c34aeca4e45732e15609ba01749b_280.png)

Now， I suppose it still load the same。

![](img/13f3c34aeca4e45732e15609ba01749b_282.png)

On the optimized one， let's do like now the debug one。The non optimize， not the debug。

 the non optimize， which runs a little bit slower， Yeah， so now we got the same particle look。



![](img/13f3c34aeca4e45732e15609ba01749b_284.png)

![](img/13f3c34aeca4e45732e15609ba01749b_285.png)

And now。Let's make it form like a lot fewer particles。Maybe like this， I don't know。



![](img/13f3c34aeca4e45732e15609ba01749b_287.png)

Okay， that was way。

![](img/13f3c34aeca4e45732e15609ba01749b_289.png)

Do few park。

![](img/13f3c34aeca4e45732e15609ba01749b_291.png)

Okay。This is better。Yeah， and the reason the trail looks kind of weird。

 especially when the ball goes。The diagonal。Is because we don't have rotator rectangle。

 we're going to fix that So that was fixed， that was wave gas the first one and we didn't actually fixed the first one 100%。

 that's okay。

![](img/13f3c34aeca4e45732e15609ba01749b_293.png)

Whether color is causing coal to collide with spec measuresters but not the strain。

 it going to be kind of tricky。

![](img/13f3c34aeca4e45732e15609ba01749b_295.png)

ItIt's kind of hard to see。But I think we are moving the space invaders。In one frame。Fanting。

The collision on the next frame。

![](img/13f3c34aeca4e45732e15609ba01749b_297.png)

That's pretty fun， nonetheless。Let me go back to the non optimizeim。

And maybe I can add like a little bit more particlecode actually。0 point one。How much is that？谁ello。

Yeah。怎么感觉。Well， it was， it was like this， was it not？



![](img/13f3c34aeca4e45732e15609ba01749b_299.png)

No， no， this looks very。

![](img/13f3c34aeca4e45732e15609ba01749b_301.png)

Anyways。呃。Yeah， okay。Anyways， the thing is now let us review the simulate level thing。Yeah， so。

We update the balls。And then we simulate the level， and then we upgrade the blocks。

Simulate block for level， we may change the position for the block here。

And then we do the bowel collision test， so it looks correct， let's do， let's see simulate。

Block for level。Invaderrs。Oh， we're not in the sameA block for level。No， okay， so we are in senior。

Cate level。We set the move down the enemy， yeah， we set the enemy piece of it。皮衣。

Why do we change that？In the simulate level， okay。In the simulate block。So just add。



![](img/13f3c34aeca4e45732e15609ba01749b_303.png)

I think it felt wrong。Because the position of the space invaders are。

I may have to watch that on slow motion。Because the position of the space invades。It's not us。

It's not continuous， it's not continuous。So maybe that was right， that it felt wrong。

 maybe it's not wrong actually。There's the code order， which was what I suspected was the problem。

Look， okay。Oh we have to remove that print。Yeah， I don't know。



![](img/13f3c34aeca4e45732e15609ba01749b_305.png)

I don't think I'm going to work with that for now。Okay， now we fix the problems。

 now let's create more problems。Let's do， I don't know。

 we have like particle systems on the list screen shake， increase the ball size， color show timers。

It had a allows of to flash new particle systems。We're going to just。Like make a simple one at first。

 right it's going to be pretty similar in the trail， let's see what we put in the trail。A P a life。

I think that's what we need for our particle。And maybe you're also going to add a DP。Yeah。

So you're probably not going to add the trail to the ball itself， but we're going to add。Here。

Or particle count。Probably everything next， let's just stick the next particle。

Thats do like a lot of particles。Okay。Now好。Trails so we are not going to do thatre there's going to be a lot simpler。

 I think。So we can't just go back。To doing that。And。Yeah， we remove this guide。This year。Yeah。

Is you when to have to aswn the particle？And then we going to render it down here。

 or maybe after the before。Yeah， let's render the particles first because since it's just a visual thing we don't want that in the way of anything。

De balls。Riner balls， yeah。Metter。Articles。So we're going to add the particle collar。Here。

 sos going to be。Cical color。But we also have to add the particle half size。And the article。

Have size。Okay， when we spawn， we're going to like spawn a particle and not do that。

 but let's just keep that。The pattern for now， even though we're going to change that in 10 seconds。

Color equals this。Okay， so。Oh， we have different。Yeah。😊。

We have different color for different particles in this case。

So I don't know if' is going to look bad because。We're going to change just the color of the new tri particles。

But this one we're going to do。 we're going to do like if。We are supposed to destroy it on P。

We do that。Should you like this？Yeah。Okay， this going to look different， not necessarily。Worse。

So let's do a particles。Article。好的P。嗯。Because。哎。He。Life。They're going to draw。PP。With the half size。

The P color with the P life， and I'm going to subtract。The life。And right here。You're going to do。

 like， spa。Articles。One party code。Or maybe you can do like spa particle。Yeah， okay。

 Sp particle and we're going to sp a particle， let's say。That's every we path the position。

We pass the life。That's hardcode that was like 128。Let's see，1，28 times。Let's say，3。I don't know。

So that's particle life and color。Let's try to do that。Okay。😊。

This is what we're going to do in this one particle in a sense。Okay。

Maybe we should start spliting that up to different files。Ls plum particle。就这个P。A life。And a color。

And then家 go。So。article口屁。Articles。Plus， next。Qu go， plus， plus， if。Next particle。

It's greater than a rate count of articles。And we set the next。Parttticicle to0。

 or of P P equals P well。I suppose you can't do that， okay？P life equals life。Color color。历史。Yeah。

C no longer supports default end。You know， maybe。I should do like here P。And。Like a random。你第。😊。

Thinking about that， wellll let's not do that yet when we implement that， we're going to test that。

So。Partticle。Jo just half size， yeah， we also actually。So when we do this small particle。

 we're going to have to pass the half size as well。So pe and a half some。

And then here we pass the ball。Okay。

![](img/13f3c34aeca4e45732e15609ba01749b_307.png)

Okay， it looks good now let's see if you still have the tray， Oh my God。

Traning that the alpha works at the very end， I think we have like a huge alpha。



![](img/13f3c34aeca4e45732e15609ba01749b_309.png)

A huge life。Yeah。

![](img/13f3c34aeca4e45732e15609ba01749b_311.png)

So I think we did our math wrong。Yeah， most certainly we did。



![](img/13f3c34aeca4e45732e15609ba01749b_313.png)

That's like trying。ではと。

![](img/13f3c34aeca4e45732e15609ba01749b_315.png)

Maybe it was 0。3。Not three。That's kind of cool， yeah。Yeah， okay， back to normal。

But now the office is too small， I think。

![](img/13f3c34aeca4e45732e15609ba01749b_317.png)

I don't know。I know can play that for a while， yeah that's a good pe。



![](img/13f3c34aeca4e45732e15609ba01749b_319.png)

Three guys。The。Dude is awesome because like different colors chase the other colors like see。

Then it can do like sorts of crazy stuff。

![](img/13f3c34aeca4e45732e15609ba01749b_321.png)

Okay， let's try 0。4 and then we can play around。

![](img/13f3c34aeca4e45732e15609ba01749b_323.png)

With this mode。Or we can probably reset the particles when we start level。Start game。Yeah。

 let's do that start game。With 0。And set the next， well， we don't need to do that。

 but I don't know set the next article。2。对。关游。Okay。

You could almost do that for some power up of some kind。



![](img/13f3c34aeca4e45732e15609ba01749b_325.png)

You know， I think you are right。I think we should do like the comment with the more extravagant。

Trail。Yeah。And that could be， yeah， I'm still dealing with the print。Yeah。😊，Go to test that。

With a comment， and let's see。Do that's pretty cool。And look at those points。Oh， nice。Yeah。嗯。

The particles。Let me print to see something， okay， next。Oh that was pretty bad frame。



![](img/13f3c34aeca4e45732e15609ba01749b_327.png)

Yeah， that would be cool to make it change based on the power you got， yeah。

 I'm definitely going to write that。😊。

![](img/13f3c34aeca4e45732e15609ba01749b_329.png)

啊。So let me just zoom in really close here。Sa right now。This doesn't look particularly good。

First of all。Because see。Well， first of all， because there are like squares and should be rotated。

 that's the first point， but same point。Which may not be as bad as the first point。they add。Yeah。

 no what， not going to worry about that for now。

![](img/13f3c34aeca4e45732e15609ba01749b_331.png)

Once we had rotator rectangles， we're going to make our work back。But I think 。

4 was not the desk call。2。3。P京。Yeah， okay。Maybe you can add the frequency a little bit more。

I don't know， yeah， let's keep like that and then I'm going to write down。

Make more extra trafficva gts， I don't know how just spell that I of the gt。



![](img/13f3c34aeca4e45732e15609ba01749b_333.png)

Tri。

![](img/13f3c34aeca4e45732e15609ba01749b_335.png)

X， yeah。

![](img/13f3c34aeca4e45732e15609ba01749b_337.png)

Yeah， okay。Or extravagant。Particle。Trayo based on power ups， because now we just change the color。

But we certainly do more than that。You know what？Let's do a little bit of that。

 no sense it just added that idea。Yeah， let's do just a little bit of that。If we are a comet。

Let's change like the life。To like one。And then。And if we are this guy。Yeah， that's good。Yes。

Would you like life equals 0。32。Then I'm going to add life。



![](img/13f3c34aeca4e45732e15609ba01749b_339.png)

Let's see。 How does that look。

![](img/13f3c34aeca4e45732e15609ba01749b_341.png)

Yeah， 0。32 is there？ok。It is better， I suppose。I mean。Looks bad。Who once get to see the。All the。

The non rotator rectangles。Oh， but that was pretty cool。Yeah， that's pretty cool。Oh。

 and they changing color？I like that。Okay。I think we're going to leave it like this for a while。Yeah。

He's definitely better。101010 and 10， do you mind if I ask why youre using C over。

 I don't mind that's try asking that The thing is。😊。



![](img/13f3c34aeca4e45732e15609ba01749b_343.png)

![](img/13f3c34aeca4e45732e15609ba01749b_344.png)

This is more like a fun project， again just for fun。

And I think S++ really add a lot of complexity in terms of like the code， how the code looks。

 and how you're supposed to structure the code。And I think that really adds like a burden to that。So。

Since this project particularly is just for fun just to play around with and learn a little bit more。

 I'm using C because I think that's。

![](img/13f3c34aeca4e45732e15609ba01749b_346.png)

I think that's more fun， this's easier。

![](img/13f3c34aeca4e45732e15609ba01749b_348.png)

So let's try playing spacing invades and see how that looks。

udeI really would' like to add more game loads now。And I think this is going to look pretty cool。

Then we can start doing more stuff like see。That's crazy。

Because now I can see how everything looks in different game modes。啊C。

That was the thing that was weird we moved。Yeah。I don't know about a collision order thing that we discussed earlier today。

Yeah， I think we should add more particles。

![](img/13f3c34aeca4e45732e15609ba01749b_350.png)

When we。When you' are faster。Instead of doing like a fixed number？We're going to do like。

We have like the length squared， yeah。Of the ball。地皮。你必要出好。So we you're trying to ship a game。

Another you're doing here， but you said this is from reach for C++， yeah。

 if this was like a more commercial game I do tend to ship in the sense of like releasing on HIO for free。

I certainly want to do that， but if this was like a bigger game that I was supposed to know have more people involved and maybe have someone port that game over。

 I would probably use C++。

![](img/13f3c34aeca4e45732e15609ba01749b_352.png)

Because that's the industry standard。For， you know。Gam me， okay， so yeah。

 we have certainly changed that。 so let's remove that print。



![](img/13f3c34aeca4e45732e15609ba01749b_354.png)

Let's add another one。啊。Or is that the trails？包的。Yeah。

 but I would use like a very C like C++ I wouldn't do like crazy C++ with know multiple inheritance and templates everywhere and like move semantics and like that。

 I would use very C like C++， but it would compile to C++ it would be a dot C++ file。Yeah。

 so length squared is probably a huge number right let me see what kind of a huge number is this？

So we're going to do like print。Hmt this guy。Print other fines， print can。



![](img/13f3c34aeca4e45732e15609ba01749b_356.png)

Okay， so it's like。

![](img/13f3c34aeca4e45732e15609ba01749b_358.png)

2，502000 and。2500， really。So we should。If you want 0。0。We should multiply that。Actually。

 we won the inverse that yeah， the bigger the speed， the smaller the numbers。

 so we're going to do like one over that。And that maybe should be end up let's。

 let's see how much is one， show you that to calculate one over the number that was we get， okay。

 so that was too much， so not one， I you like。Yeah over。Yeah。Looks about right。Illegal for drugs。

So's the length squared。

![](img/13f3c34aeca4e45732e15609ba01749b_360.png)

判决都会。

![](img/13f3c34aeca4e45732e15609ba01749b_362.png)

O， okay。Now we do have some particles， but not that many。But if oh， this is cool。

How about that clone style？That not's going to be 11 out of 10。Dude， this is awesome。

 adding this little secondary animations kind of stuff。They really add to the whole thing。Yes。12。



![](img/13f3c34aeca4e45732e15609ba01749b_364.png)

。5 out of 10。Okay， but I think I'm going to add a minimum。Yeah， so and we'll get the max。

Out of point。0。I don't know。How much are we getting。那。啊。Print。But no， all joking aside。

That is how you do like cool game field kind of stuff。 you add little variations to everything。

 to every single thing。😊。

![](img/13f3c34aeca4e45732e15609ba01749b_366.png)

![](img/13f3c34aeca4e45732e15609ba01749b_367.png)

So I'm going to see the value， not multi by cancel。



![](img/13f3c34aeca4e45732e15609ba01749b_369.png)

Yes， still zero。

![](img/13f3c34aeca4e45732e15609ba01749b_371.png)

Okay， I think I actually gonna to do the other way like。



![](img/13f3c34aeca4e45732e15609ba01749b_373.png)

If you got four。Which is like too little。Yeah。

![](img/13f3c34aeca4e45732e15609ba01749b_375.png)

So for， let's strike doing like。デフティーディバイルバイですか。

![](img/13f3c34aeca4e45732e15609ba01749b_377.png)

ok。Now， this is pretty cool， yeah。This is very， very cool。Yeah， see， it's like just an normal trail。

This like a supertra of oh didn't get that right。Yeah see。

Now let's see how that looks like in space invades。You they think have like three triple shots。啊啊啊。

That sucked。And res change the color。

![](img/13f3c34aeca4e45732e15609ba01749b_379.png)

Based on the speed。

![](img/13f3c34aeca4e45732e15609ba01749b_381.png)

You know， since we are doing this， let's do like full on。はい。We have like a make color。

We have a alert color as well。Yes。Yeah， so maybe should you like a darker blue in a very light blue？

So。So the length squared。I think we should like do a map inter range of this guy so we have like。A。

like speed range。Yeah。And the speed range。This is like four， right？I know。

Think we have to print everything again。Yeah， I think I'm going to do that。 So let's just see the。

The left length squared to one over length squared。



![](img/13f3c34aeca4e45732e15609ba01749b_383.png)

Just to see some values。

![](img/13f3c34aeca4e45732e15609ba01749b_385.png)

Okay， so。Okay，Or imagine if you do like a color based on the XY velocity。

You mean different based on the x and different based on the y or just change the color based on the x y velocity because that's what we're going to do right now。



![](img/13f3c34aeca4e45732e15609ba01749b_387.png)

![](img/13f3c34aeca4e45732e15609ba01749b_388.png)

In fact。啊。

![](img/13f3c34aeca4e45732e15609ba01749b_390.png)

Oh， I think I mean， like this should be a one color and the Y velocity be on the color should alert that individually。



![](img/13f3c34aeca4e45732e15609ba01749b_392.png)

And maybe we should do that。

![](img/13f3c34aeca4e45732e15609ba01749b_394.png)

So we can definitely play around that for a long time， case of four， three。

Like four is like the base guy。

![](img/13f3c34aeca4e45732e15609ba01749b_396.png)

And then it got ways smaller than four。I know。They they， yeah。

 they do something interesting to play with。啊。

![](img/13f3c34aeca4e45732e15609ba01749b_398.png)

I don't think I'm going to like doing the first， I'm just going to do the normal guy。

 but this is 250。

![](img/13f3c34aeca4e45732e15609ba01749b_400.png)

And let's do like a nice velocity。

![](img/13f3c34aeca4e45732e15609ba01749b_402.png)

Let's say it's like， yeah， we don't， oh， in fact we don't even see if that's too gift or not。

Because our council。Our council。

![](img/13f3c34aeca4e45732e15609ba01749b_404.png)

Should be like。

![](img/13f3c34aeca4e45732e15609ba01749b_406.png)

Yeah， it is 250。Then we can easily get。like 600， maybe should you like。seven。Let's try like。



![](img/13f3c34aeca4e45732e15609ba01749b_408.png)

Okay。That was way too much。Let's right 200，000 so we're going to do。A。哎呀。スpeed？第。😊，Which is in math。

We have， I don't think have met due two range。Normalized。Let's say 2500。The ball length squared。

 right？T。And then let's do like。I like this。Okay， now we have to do like the math inter range thing。

So we take like a min。Take a vow and a take。

![](img/13f3c34aeca4e45732e15609ba01749b_410.png)

Nextax， so all we want to do。Yes， let me just。Sure this guy。 So if you're like。

We want to go like from like， say， 10 to 20。In 15， so we expect 0。5。



![](img/13f3c34aeca4e45732e15609ba01749b_412.png)

So we're going to do the max minus the min， so this is like the ray。Max minus min。



![](img/13f3c34aeca4e45732e15609ba01749b_414.png)

So this is Stan。This is going to be this guy divided by10。



![](img/13f3c34aeca4e45732e15609ba01749b_416.png)

Minus one。ok。

![](img/13f3c34aeca4e45732e15609ba01749b_418.png)

IThink that's it。Close the sky。Let's see。 how does that look。



![](img/13f3c34aeca4e45732e15609ba01749b_420.png)

0。

![](img/13f3c34aeca4e45732e15609ba01749b_422.png)

Z okay yeah， we should probably multiply that by 10 since we are normalized。



![](img/13f3c34aeca4e45732e15609ba01749b_424.png)

买反。

![](img/13f3c34aeca4e45732e15609ba01749b_426.png)

Okay， minus 98。Mus 84， so this is pretty wrong。

![](img/13f3c34aeca4e45732e15609ba01749b_428.png)

At that great point are we on the？

![](img/13f3c34aeca4e45732e15609ba01749b_430.png)

Let's see if you're an opt， you're not。 So map into。Range， normalized。So minimum this guy maximumim。

This guy and the value， so it should be zero。Okay， so it's not minus1。



![](img/13f3c34aeca4e45732e15609ba01749b_432.png)

That was wrong。It's a。It's v minus min divided。

![](img/13f3c34aeca4e45732e15609ba01749b_434.png)

Okay。Let's just see， range。Yeah， this。Yeah，0。It go 17。Oh yeah。😊，Okay。1。28。



![](img/13f3c34aeca4e45732e15609ba01749b_436.png)

Yeah， I think that's a bit too much。Let's try doing like 100，000。Okay， now that we do have this。

We can play around with this in different scenarios like the color。Like。We should do color。Is a make。

Or we have like a dark color rent， yeah。Go to learnb color。Of like。I do a very light。

Guy like this like a slightly darker。Blue， like。Do you like。I know，7，7。CC施。😊，Yeah。

 and this is going to be the speed T。

![](img/13f3c34aeca4e45732e15609ba01749b_438.png)

Okay。

![](img/13f3c34aeca4e45732e15609ba01749b_440.png)

So this a dark blue gets light blue。I do。对 yeah。Yeah， that' was pretty cool thing。



![](img/13f3c34aeca4e45732e15609ba01749b_442.png)

Nice， yeah， I think it was a bit too dark， this guy。You can you like A A。



![](img/13f3c34aeca4e45732e15609ba01749b_444.png)

你不知 b b。We don't want like super dark。

![](img/13f3c34aeca4e45732e15609ba01749b_446.png)

Yeah， it's a bit better yes。Okay， I think we're looking nice。 let's see that on the space。啊。ok。Okay。

 but we actually haven't。Done the particle system， we just converted our trail to the new system。Oh。

 that's it right on time， so what we should do is start adding particles whenever we feel like we should have particles。

We just like all the time。

![](img/13f3c34aeca4e45732e15609ba01749b_448.png)

Yeah， I think this looks pretty good for now。

![](img/13f3c34aeca4e45732e15609ba01749b_450.png)

So remove the print。Oh， we can also I can also do like the trail on based on the speed tee。

So this goes home one。2。Yeah， this goes from one。To zero， so we want。IfIf the speed is very slow。

 we want to spawn like this amount of particles and if it's pretty fast。That's spa like thismon。



![](img/13f3c34aeca4e45732e15609ba01749b_452.png)

Yeah， so it's way we use like the same value for everyone。So。I suppose you are wrong。



![](img/13f3c34aeca4e45732e15609ba01749b_454.png)

![](img/13f3c34aeca4e45732e15609ba01749b_455.png)

No， we were right。

![](img/13f3c34aeca4e45732e15609ba01749b_457.png)

I suppose this has to be a lot more。

![](img/13f3c34aeca4e45732e15609ba01749b_459.png)

嗯。Like this。

![](img/13f3c34aeca4e45732e15609ba01749b_461.png)

I don't know， let's print this alert。And we have to multiply that dial a lot。



![](img/13f3c34aeca4e45732e15609ba01749b_463.png)

![](img/13f3c34aeca4e45732e15609ba01749b_464.png)

4ty。31。34， yes， it's getting smaller。Oh， yeah， we are supposed to get smaller。

It's not got to eat that much smaller。

![](img/13f3c34aeca4e45732e15609ba01749b_466.png)

Let's try to that。40。24。Smaller means more particles， right？Yeah。Dude， what happened did we crash？Oh。

 I think you got so many particles。See the， yeah， we have to limit those guys。😊。

We are supposed to spawn like a lot of particles now。Because this value is super small。Oh。

 but it's negative。Yeah。黐哈。So yeah， billions of particles all in one frame in the same spot。

 so that's pretty bad。

![](img/13f3c34aeca4e45732e15609ba01749b_468.png)

呵。😊，So maybe I'm going to let this guy。How it was for now。All right， you can do like， yeah。



![](img/13f3c34aeca4e45732e15609ba01749b_470.png)

Pro limit that as well。

![](img/13f3c34aeca4e45732e15609ba01749b_472.png)

やらす。That was acceptable， Oh why did we get like green particles？



![](img/13f3c34aeca4e45732e15609ba01749b_474.png)

We probably clamped this guy。I think that's the problem。P you。讨厌白。



![](img/13f3c34aeca4e45732e15609ba01749b_476.png)

So yeah， the color won't go like all crazy and the number of particles won't go like out crazy。ok。

Okay， this is more reasonable。

![](img/13f3c34aeca4e45732e15609ba01749b_478.png)

Yeah。Okay。Maybe， like。Clean up。Use。Speed tea。But now let's start adding more particles。

 Now we have a spa particle。I'm going to do like a spawn particle explosion。

And we're going to do like a V2 B。Hey， let's see like base size。And then we're going to do。

A days life。And base考。Well， as you call it。So the particle explosion， we also do like。

What we should do here in count。Is， that's paw。Partticle。Correct。And the P will be the P。

In a base size。Let's do like。系啊。Size。This is going to be like。The two。Well。What did I do。

 Let's do like。B size to add a little bit variation plus equals， do we have like the random？Blateral。

I don't think we do。They size， Yeah， this size。Random bilateral， which is from minus1 to one。So。

 we should do like。This guy。Yeah， so we're going to add。10% of variation。

This probably also be a framework。And same thing in the base life。So。皮。😊，We're going to do base size。

 base size。Okay， life。B life。😊，Color just going to be the color I'm going to add。えや。

Also going to I like a random speed。D屁。It's going to be， let's say。randomandom。That's a random float。

Random F 32 in range。And let's do like from minus 10 to 10。I't know if that's reasonable or not。

And not going to bother normalizing this guy。The spa particle should return the particle。

The particle D P equals the P。Okay。Yeah， let's start doing like the range stuff。So line randomly。By。

 let's do only a lateral。So this goes from zero to one， so all you have to do is like return。

A randomom Year 32。And I convert that to float。And divide。By Max。E 32， also in float。是这个这个。

We don't have max U32 that's add that。I don't know what this is called。In the STD int。

Let's just quickly see that。

![](img/13f3c34aeca4e45732e15609ba01749b_480.png)

Nextax。And yeah。Oh， no， this is。Uent and yeah， so it's going to be。



![](img/13f3c34aeca4e45732e15609ba01749b_482.png)

You and 32。あ。Random Unilateto looks correct a loud and has to do with random。Blateral。

So you're going to go from this guy to the max。Yeah， that's just you like。Times  two。Next one。

You probably do like。Okay。And then let's do the random in range。So， in line。F 32。

 random F 32 in range can take。今天。So I'm going to take a random。Unilateral。Times。年。Max。

Minus image which is the range。Plus。正面。And I type mix。Now， let's say that whenever we collide。

 whenever we destroy a block or block。Let's tried。In fact， that's not entirely correct。This。

 let's see， block。De tried。We're callinging tests。L condition。Spawn power block。Sun。

Rer the neighbors。嗯。😊，As you like。This trying neighbors because this may be a recursive function。

And if destroy showing me。です。ok。So when did you block this tried。来。使か？And I go said that。

Maybe this right。ok。And then test form condition。Okay， now we're going to spa particle explosion。

Let's spa。20 particles。I don't remember the the arguments。Count 20 P， block P。Ba size， let's do two。

Base life， let's do one， maybe ones too much， let's do like 0。75。Colllor， let's do right for now。



![](img/13f3c34aeca4e45732e15609ba01749b_484.png)

Is this going to work？Okay， it did work。But looks pretty bad。



![](img/13f3c34aeca4e45732e15609ba01749b_486.png)

ButThe size is huge。And。The life was also huge。And we should also like at a lot of speed。Like here。

差理解。Or' not single in the particles。Yeah， so。When we render the particles。

 we will also simulate them。So。TheP life let's like P P。那 equals p。第一。T产点T啊。是。一？

That's not very clear， I think。Many random letters， legal forstruct。Ad me2。第一。😊，T。



![](img/13f3c34aeca4e45732e15609ba01749b_488.png)

Let's see。Dude。It's like super small， but you guys saw that。



![](img/13f3c34aeca4e45732e15609ba01749b_490.png)

![](img/13f3c34aeca4e45732e15609ba01749b_491.png)

That was really cool。Re cool。好。

![](img/13f3c34aeca4e45732e15609ba01749b_493.png)

That's how the size a little now。

![](img/13f3c34aeca4e45732e15609ba01749b_495.png)

![](img/13f3c34aeca4e45732e15609ba01749b_496.png)

We actually just do that。TheB color。 How about that。



![](img/13f3c34aeca4e45732e15609ba01749b_498.png)

Now it's 13 for 23 in10。How about now did you see the color change？It's even better， yeah。

 I think the office is too low。Doude the room we had sound effects。This is going to get really cool。

You know what？

![](img/13f3c34aeca4e45732e15609ba01749b_500.png)

Maybe you're going to increase the size even a bit more。



![](img/13f3c34aeca4e45732e15609ba01749b_502.png)

And。

![](img/13f3c34aeca4e45732e15609ba01749b_504.png)

![](img/13f3c34aeca4e45732e15609ba01749b_505.png)

See， that's what I think I was thinking about doing， we should add this guy， this DP guy。

Where is that。啊。主皮。This guy。They should maybe add to the trail。Just a tiny bit。

Still much for me to calculate at this point。When we lost the floating point precision is not precisely I should calculate that on double。

Respond particle and then like particle key。Then we do P。一皮。It's going to be just， a little bit。

 Let's do like a random。来ly。

![](img/13f3c34aeca4e45732e15609ba01749b_507.png)

I don't know if you can see。There was a tiny bit of variation。



![](img/13f3c34aeca4e45732e15609ba01749b_509.png)

Let's do a random。Float in range， as do -2。

![](img/13f3c34aeca4e45732e15609ba01749b_511.png)

Yeah， how about that。I think just since we added the block， oh。

 let's also add more particle explosion and things。

 I think I'm going to add that on this on particle。



![](img/13f3c34aeca4e45732e15609ba01749b_513.png)

Swn particle is going to pass， like a。Like 。2。Which is。Particle。Like the DT。TheD啊 theDP。つけよ？Yeah。

 so it may be zero， but it may not be zero， so we're going to do part cool。D梯。People is random。

Bilateral。Times。嗯这。Not convert。Yeah。So in the prior Exp， mouse is going to receive a。啊。D piece。

Ws going to be larger yet。This gonna be。10。Maybe， maybe even more。E12。Okay。😊。

We just need a satisfying brick breaking sound definitely。And now they just said it。

Maybe should like add like a real brick。And like a real brick。

Just for fun because I was thinking about more like game sound of sine waves kind of stuff we could also do that。

 but just put a little brick there just for fun a real brick let's do when we hit the ball。

 hit the wall。So， the wall。It it like ball。Seeing late。S late。Update ball， bulk with player。

Going to add that。Yeah， sounds open another red hole， absolutely， and it's really， really cool。

So we're going to do like the ball desired pe。Here。This one's going to be like。

 let's say fewer particles because we want to attract。



![](img/13f3c34aeca4e45732e15609ba01749b_515.png)

That much attention， what the player called I didn't even remember。



![](img/13f3c34aeca4e45732e15609ba01749b_517.png)

It's green。Well， maybe she do like wine， oh， that' is the ball call yeah。

Which is why it's what who knows。That's add10， let's make it a。8ight。And let's make it like。しまう。

How there's an of both ball。Okay， then let's be like， if purere right。



![](img/13f3c34aeca4e45732e15609ba01749b_519.png)

Oh， you know what， before we test， let's also add。

![](img/13f3c34aeca4e45732e15609ba01749b_521.png)

To the wall。We should do like a double wall color。Yeah， so this is going to be the。

The ball desired P。 Do we have the wall collar， I don't think we do。嗯。No， we don't。嗯。

Is this the color， I don't think so， so。The draw rack。あ？The year。Here yet。We're going do like the。

 oh， I suppose that was the blog collar。So let's do like。A arena color。This guy。And that's。

 let's also do。哎有。Let's also due。 Let's see here。A wall color。哇，好的。Okay。

And this one is going to do the wall column。I'm going to add it。going here。Here and。



![](img/13f3c34aeca4e45732e15609ba01749b_523.png)

唔行。That looks pretty awesome to me。That was pretty cool。I can wait to have rotated racks。

Because the trades going to look so much better。

![](img/13f3c34aeca4e45732e15609ba01749b_525.png)

He know what， know what' going to do。

![](img/13f3c34aeca4e45732e15609ba01749b_527.png)

I'm going to， this is kind of a hack， but a think's going on DI hack， let's do like explosion。

In the destroyed brick。Instead of like。St doing this， we are going to do that。

 but we're also going to do something else。I'm going to respond a single article。At the block P。

I forgot that。Dude， I forgot the arguments， maybe there were bad arguments。N。Yeah， DP scale。

 let's say zero。Havelf size going to be the block。Half size。life。That's 8。5。You color。Black color。



![](img/13f3c34aeca4e45732e15609ba01749b_529.png)

。5 is too much this week。I don't know if you realized what I'm trying to do， let's see。



![](img/13f3c34aeca4e45732e15609ba01749b_531.png)

Okay， so I did nothing。I did nothing。大家。

![](img/13f3c34aeca4e45732e15609ba01749b_533.png)

Okay啊。So， instead of adding。To the block system， which I was going to do， I was going to do that。

Like through another state like disappearing where I render something differently than I have a timer。

 I just。Reused。The， part is for that。

![](img/13f3c34aeca4e45732e15609ba01749b_535.png)

But I realized。That in this article here。I need still like rendered articles。I need， like， a P。

I need， like a E。Lifey， life。So， yeah。When I spawn the particle。

Because some particles know should start out at full life。You know， that doesn't make sense。

I'm trying to think about a better system， I think I'm going to do that for now。Which is like。

A life D。But。I'mNot sure this is the best though。Because I want them to start that full life。

 pretty much all of them， right？Let's do like。Now let's keep this guy have one。And at this， this guy。

 I'm going to do like。5。And。And this one。

![](img/13f3c34aeca4e45732e15609ba01749b_537.png)

就 also want。So now it starts at a full guy， full speed， but then it quickly disappears。



![](img/13f3c34aeca4e45732e15609ba01749b_539.png)

Oh， I think I saw it blue。Yeah。😊，We should probably cap the color at some point。



![](img/13f3c34aeca4e45732e15609ba01749b_541.png)

Maybe at the article draw。Or entered particles。You maybe should do like a comment。

Or maybe she did that yeah， well， I thought I was doing that already。In the renderer。Well， no。

 I don't think so。Alpha。Yeah。Going to do alpha equals。



![](img/13f3c34aeca4e45732e15609ba01749b_543.png)

Okay。I actually。ok。

![](img/13f3c34aeca4e45732e15609ba01749b_545.png)

This is better， I think， maybe it's a bit too slow still。Maybe we should do like1。

And maybe we should add a little bit of speed。Like。W。Arty cool， and we do like。Lock particle， D P。

It's going to be equal to the ball or we don't have the ball， maybe we should have the ball。P。

Minus the block。嗯。Block destroyed。M。其。Block destroyed。Pas the ball。I hope I have the ball here。



![](img/13f3c34aeca4e45732e15609ba01749b_547.png)

I do。Okay。

![](img/13f3c34aeca4e45732e15609ba01749b_549.png)

Now let's see if we do have a little bit of motion should be just a little bit of motion。不要。

I saw no motion。

![](img/13f3c34aeca4e45732e15609ba01749b_551.png)

Let's。Let's make it slower。

![](img/13f3c34aeca4e45732e15609ba01749b_553.png)

Okay， but this is like wrong。

![](img/13f3c34aeca4e45732e15609ba01749b_555.png)

She did the other way around the black be。

![](img/13f3c34aeca4e45732e15609ba01749b_557.png)

Mus宝。

![](img/13f3c34aeca4e45732e15609ba01749b_559.png)

Yeah。Okay。Okay， looking， looking good， looking good， but。



![](img/13f3c34aeca4e45732e15609ba01749b_561.png)

Yeah。Let's see。 If you go back like 8。

![](img/13f3c34aeca4e45732e15609ba01749b_563.png)

Probablys going to be too slow。No。No， that was good， I think。Yeah。Yeah。

Then you can go back and add these particles。

![](img/13f3c34aeca4e45732e15609ba01749b_565.png)

Okay， maybe eight twisted。

![](img/13f3c34aeca4e45732e15609ba01749b_567.png)

Yeah， and I think that's it for the particle system， I think I just like one more thing。Today。Yeah。

Okay， let's see。Other game modes。Dude。Look at that。That's like crazy。Oh， I died。

That was really stupid of me。Okay， so I'm slow now， that was this slow guy。Okay。

 let's see good good making time。I think I may add colors。I don't know。

That's going to be pretty quick and I think it's going to change a lot visually。

And then maybe next time I'm going to do audio。I don't know， it depends on my。I。

I don't think we have much to do in terms of gameplay for now。For now。Let's see this guy， yeah。

 I mean， we do have a lot of stuff to do。Dude， that was the best one yet。

In terms of like the explosion。Well if I do manage to hit it， yeah。That looked pretty cool。

This game looks pretty cool and when I add like a smart enemy， it's going to be way cooler still。

Okay。没有。Okay。Yeah， the explosions look really cool。Yeah， okay， let's just check out spacing pictures。

Dude， that's awesome。They really looked damaged。Oh， it's because the size， the size not dependent。

On the particle size。Which maybe we should do like。I don't know。Dude， this is it's pretty common。

 really awesome。Although I do think I should change。The yeah。Yeah。



![](img/13f3c34aeca4e45732e15609ba01749b_569.png)

I think'm going to change just quickly。The trail， let's see。The trail color here in case。

K we are a comment， that should be the most important color。So yeah， I am going to do the I here。

Yeah， okay。So particle system's done， at least for now。Scr shake， not going to do that now。

 increase particle， increase ball size， maybe I could do that， I'm going to do colors。

Show time is pretty important too。But as I said，Engine improvements is going to be pretty， you know。

Pretty back and forth and I'm also going。To do the rotator reacts pretty quickly。

 maybe even before the audio。Because that'll make the particles work better。



![](img/13f3c34aeca4e45732e15609ba01749b_571.png)

Let me just check out。

![](img/13f3c34aeca4e45732e15609ba01749b_573.png)

These particles here。And I think that's good。

![](img/13f3c34aeca4e45732e15609ba01749b_575.png)

Okay。Those no argument macros are going to byching the ass。Which ones？Meaning these ones？

These are just constants。I don't know what you mean。呃。



![](img/13f3c34aeca4e45732e15609ba01749b_577.png)

Okay， so color， I'm going to add like the get the color wheel。



![](img/13f3c34aeca4e45732e15609ba01749b_579.png)

考er5。

![](img/13f3c34aeca4e45732e15609ba01749b_581.png)

Just so we can， you know， get like a more interesting color， actually。



![](img/13f3c34aeca4e45732e15609ba01749b_583.png)

With a loop ball， yeah。I'm not a big fan of that as well， so we have a four each ball。

That's the only time I do this。But maybe I use it a few enough times that doesn't justify。The macro。

 I use it like just once， just twice。Yeah， you know what？To avoid being bitten in the ass。

 which I am not a fan of。I am going to remove this bag。So thanks for your suggestion。Okay， colors。

 I do like these colors。

![](img/13f3c34aeca4e45732e15609ba01749b_585.png)

So as a start。

![](img/13f3c34aeca4e45732e15609ba01749b_587.png)

You can pass an argument。 Yeah， but I don't know that defeat the purpose that macro didn't do anything at all was just because I was。



![](img/13f3c34aeca4e45732e15609ba01749b_589.png)

Tired of typing this guy and actually I kind of I should have used this as well， but。Yeah。😊。

There's nothing special about that。Okay， so let's see the color pickic on this guy。All right。

Well I don't have the。

![](img/13f3c34aeca4e45732e15609ba01749b_591.png)

I think I going a Photoshop， so I'm only going to take like two days to open Photoshop。

And I can pick a color and then we can choose cool harmonies。



![](img/13f3c34aeca4e45732e15609ba01749b_593.png)

And then this also should be a level dependent。

![](img/13f3c34aeca4e45732e15609ba01749b_595.png)

Like the player color， the background color， maybe even the wall color I'm not sure about the wall color。

 though。

![](img/13f3c34aeca4e45732e15609ba01749b_597.png)

That' see。

![](img/13f3c34aeca4e45732e15609ba01749b_599.png)

Dude Photoshop so slow， yeah。

![](img/13f3c34aeca4e45732e15609ba01749b_601.png)

Okay， let's see these colorsers。That could be the player color， it is the player of color。Yeah。

 let's just look for a nice background color。Maybe we should do like。This orange thing。

 but way more subtle。

![](img/13f3c34aeca4e45732e15609ba01749b_603.png)

Yeah， let's let's try， let's try doing that so we have like a wall。Color， yeah。

The water color could be could be this guy。But then this guy is going to be like a way seller version。

Which is let's say， let's say it's like instead of 40 extent10。Set of FF。I can'tify that life for it。

 let's do。16 divided for eight。So， it's。80。Something like that， not perfect。



![](img/13f3c34aeca4e45732e15609ba01749b_605.png)

We're not aim to make a perfect game。Okay。Is that better？Not really。



![](img/13f3c34aeca4e45732e15609ba01749b_607.png)

I mean， I think it's a little bit better， but this orange is way too strong。

If you can do like this guy。The80 and the 20。

![](img/13f3c34aeca4e45732e15609ba01749b_609.png)

啊。来 see。😊。

![](img/13f3c34aeca4e45732e15609ba01749b_611.png)

Let's see， okay， now we're better， I think。Creby。We also pair around with the both sides now。

And yeah， this guy， we should also change the colors。



![](img/13f3c34aeca4e45732e15609ba01749b_613.png)

Let's do it quickly， so。Yeah， so I can just say what' we're going to do today turns up。



![](img/13f3c34aeca4e45732e15609ba01749b_615.png)

We're going to。Increase the ball size。No screen shake， no show timers， we did that。

Makes your lab animation nothing think I'm going to do that。Pong independent black movement。

That would be cool。think怎快。I don't know。Maybe today I'm going to do like a long stream。

Pong influenced the Bo speed see I'm going to play around with P where I do the whole thing。

 and I do also the space of it。With the size， well， I would try to do that a little bit。

 but it's kind of boring。I。Maybe we should add a size D。そうや。That's what the other one says。So color。



![](img/13f3c34aeca4e45732e15609ba01749b_617.png)

嗯。

![](img/13f3c34aeca4e45732e15609ba01749b_619.png)

Get the。This， I don't know。This orange is kind of ugly。



![](img/13f3c34aeca4e45732e15609ba01749b_621.png)

This pink so much， you know， maybe we should do like this color。



![](img/13f3c34aeca4e45732e15609ba01749b_623.png)

Set up the orange。Let's try to do that。This should be the wall。And let's do like 880。



![](img/13f3c34aeca4e45732e15609ba01749b_625.png)

ok。Kind of like that。But maybe not for the first level。It before the p leg。



![](img/13f3c34aeca4e45732e15609ba01749b_627.png)

Yeah。Okay， this is school for the palm。So let's do astruct。Level info。

And all we have now is an arena color。

![](img/13f3c34aeca4e45732e15609ba01749b_629.png)

And they wall collar her。Maybe also a player color。



![](img/13f3c34aeca4e45732e15609ba01749b_631.png)

Or maybe you should keep the player always green analyze， let's just do these two for now。

So we don't have an array of level info。来部。So。And。Let's do like。Where do you have the levels？

Maybe you would like to lever way up。Yeah。Okay， so these are the levels。

A we're going to play around this。So， normal。Let's do， like，2。不？We don't， we don't have chess。

 I think I'm going to。Remove these guy like。So that's what not the game's about。

 and we also don't have stadium。Yeah， this is like prone to error。But this is just the first version。

Okay， so this。Is the pond。Okay。😊，Now。Let's try， well。

 maybe you're going to use this one for the normal one。



![](img/13f3c34aeca4e45732e15609ba01749b_633.png)

Yeah， let's do it at least for now。

![](img/13f3c34aeca4e45732e15609ba01749b_635.png)

Let's say this is the arena color。

![](img/13f3c34aeca4e45732e15609ba01749b_637.png)

For the normal one。This is the wall call。And for the wall level。



![](img/13f3c34aeca4e45732e15609ba01749b_639.png)

Let me get。

![](img/13f3c34aeca4e45732e15609ba01749b_641.png)

Palette。

![](img/13f3c34aeca4e45732e15609ba01749b_643.png)

Oh， it kind of looked okay。With this。This one。C。Is that it， no， that's not it？Yeah， this is it。



![](img/13f3c34aeca4e45732e15609ba01749b_645.png)

Oh， no just。

![](img/13f3c34aeca4e45732e15609ba01749b_647.png)

Let's try adding these nice R。

![](img/13f3c34aeca4e45732e15609ba01749b_649.png)

Since we didn't do the nice orange color in the other case。And then well do like， yeah。

Sorry for for that。7 so 40。See text are。Yeah， let's do like for the dictators。They are white。Well。

 maybe just do black。Or maybe likely a very dark。Okay， and for the walls。I do a lie agree。Okay。

 missing a lot of。W color。Yeah， so this is like。The level， state to current level。有。

Maybe I should just keep like wall color and had a。AndAnother a macro。Arena color。Okay。

This is an eag forstruct。Well。Level level e。Sorry about that。😔。



![](img/13f3c34aeca4e45732e15609ba01749b_651.png)

Okay， let's see。This is like the normal one， which is not like too strong， oh， this is pretty cool。

I liked like those colors。Dude， this is like maybe。

 we should also change the player color and thinking。Because this green looks pretty bad。

 in this case。Okay。Nice。啊。

![](img/13f3c34aeca4e45732e15609ba01749b_653.png)

Okay， this one and this one， oh， this one looks pretty bad。Oh， I thought about a dark gray。

 I did a light gray。But I kind of liked。The darker edge。It' maybe I'm going to keep it。Anyway。

I still like to。And。

![](img/13f3c34aeca4e45732e15609ba01749b_655.png)

Now I're starting to look like a proper game and think。Yeah， no， maybe I'm going to keep him。

Same color。But maybe not just this screen， I don't know。This one， the green looks pretty good。

As well as this。I don't know， let's keep going。

![](img/13f3c34aeca4e45732e15609ba01749b_657.png)

Okay。So。

![](img/13f3c34aeca4e45732e15609ba01749b_659.png)

Do the colors， let's increase the ball size。We're going to increase the ball size。

Whenever we score a point， just for' fun。Or maybe whenever we collide， yeah。



![](img/13f3c34aeca4e45732e15609ba01749b_661.png)

Whenever we collide， we increase the ball size and that ball size is going to incrementally。Yeah。

 so we have the ball。Do we have the ball half size？Have the ball， no， have the block have signs。

Why do we have the balls？好。Yeah， we do have it at ball have size， so whenever we hit。Something。

 so Paul。嗯。I'm going to do like a small。Call for that。Increase。Ball size。

Just in case we want to play around if that so ball。FSize。

I'm want going to do like a size multiplier。Plus， equals one。Now size multipliers to like as。Well。

 let's just do the half size。As a float。Yeah。😊，So。Itpon triple ball shots。75 well， 0。

 one is going to be way too much。Do ball collision。I the ball half size。All have size。Ill have晒 old。

And。This thing。I'm going to increase both sides。Yeah。う。I think this should be just the first thing。

We do whenever we。Yeah。Because the size is going to change。So。呃。

Increase both sides to a few arguments。Oh yeah， the ball。嗯。Why didn't this one complain？Oh yeah。

 because we didn't get to that yet， okay。Okay， well have signs。Just get smaller。Okay。

All have signs again。And this is assuming me that Bar also always going to be。Yeah。

 I think it may be safe to assume for now。We may regret that later on， but who knows？Okay。你的包。

Update balls is colliding with players， so this one I have to do like。中？All have size one。

Clre colliding with ball。Also going to increase the ball size。And then let's do like。

When whenever you hit the arena。Okay。不是。嗯。just removing this guy。Okay， more stuff to do。

All have side。Size。Okay， respond a particle and。To also pass。Make a fee2 out of that。Direct again。

 a two。I am the V2 here。And V2 here as well。

![](img/13f3c34aeca4e45732e15609ba01749b_663.png)

Okay， let's sea。

![](img/13f3c34aeca4e45732e15609ba01749b_665.png)

Oh， we actually don't mut， Oh， we do use it， okay。Okay， this is not entirely bad。

 but it gets pretty impossible to play。Oh， because the particles。

 because our rendering can't handle that。And also the player col。

Not sure why do we lose at that point。Oh maybe because the ball is so big。

Then it collides with the bottom， and I think that's the problem。



![](img/13f3c34aeca4e45732e15609ba01749b_667.png)

Yeah， okay， but it's not going to get that big。Probably。So。Ider balls。We draw the ball。And then。

We are。Do like， if。Ball half size。Is。呃。Greater than。Well， it's less than 0。75。5 signs equal。

And then this is hard coded for now， but it cares。Let's do like。



![](img/13f3c34aeca4e45732e15609ba01749b_669.png)

マ equal。

![](img/13f3c34aeca4e45732e15609ba01749b_671.png)

![](img/13f3c34aeca4e45732e15609ba01749b_672.png)

Yeah， this is cool， but one is way too much， and this is like way too little so。

Sineence plus equals yeah。To。

![](img/13f3c34aeca4e45732e15609ba01749b_674.png)

Just something to read word， thanks， man。Nice to hear that。Okay， so now it's fairly visible， okay。

 no， it's not here， fairly visible。No， I think that's cool because that's a very subtle effect。

But when we do have a lot of collisions。You know， it does adds up to be pretty nice。



![](img/13f3c34aeca4e45732e15609ba01749b_676.png)

I just think。The D T times2 here。我し。Too much。To like one point。



![](img/13f3c34aeca4e45732e15609ba01749b_678.png)

Okay， I think this is getting better。Yeah， okay。We should probably limit。The size， but。

Unless we get a case we got to test space invades。But。Yes， he。



![](img/13f3c34aeca4e45732e15609ba01749b_680.png)

So instead of doing this。I'm going to do like DT times。Let's do like。The max of one。

And the ball have size。

![](img/13f3c34aeca4e45732e15609ba01749b_682.png)

This out there。If you just goide the once， it's going to take like a little bit to。

 yeah to go back to the normal one， it's kind of cool。But if you collide a lot。

 it's going to return to the position quicker。It's going to be just a few moments with a pretty big ball。

Okay， let's play out with the other game modes。Dude。Dude。I didnt。Think about the comment。

That was really cool。But it did get out of control。A little bit。ふ。So yeah。

 so all I'm going to do like add a。

![](img/13f3c34aeca4e45732e15609ba01749b_684.png)

A negative feedback loop， just like we did here。Like the bigger we are。

 the faster you go back to normal。I'm also going to do that。So。The bigger we are。

 the less we're going to grow。We're going to add。Starts out at one point。

 yeah let's see what that looks like so。We are。05。 so if we do like one over that。1 over 0。75。

We're going to increase 1。33， which is a bit too much。And now let's see if we are 1。33。1 over 1。33。

 eventually to add。嗯。Yeah， I don't like that， maybe like half。Let's do like 0。8。



![](img/13f3c34aeca4e45732e15609ba01749b_686.png)

Okay。Yeah， I see that was way too much。Although it is more controlled。



![](img/13f3c34aeca4e45732e15609ba01749b_688.png)

嗯ん。Like， if we do。If we do half over this guy， speed to around just a little bit。



![](img/13f3c34aeca4e45732e15609ba01749b_690.png)

Or maybe my maths wrong。Okay， now this is a bit better。



![](img/13f3c34aeca4e45732e15609ba01749b_692.png)

So we have to test a comment， let's do even less。Oh， but I think I got you wrong。No， I do。 Yeah。

 I got it right， so if we get like。This guy。

![](img/13f3c34aeca4e45732e15609ba01749b_694.png)

Yeah， okay， this is correct。Let's see how this looks here。Okay， this is pretty much perfect。

 I think yeah。Okay。And the comet。Gets just big enough to be awesome。

And small enough to get manageable。So。That looks good， I think。Maybe。



![](img/13f3c34aeca4e45732e15609ba01749b_696.png)

Maybe a little bit less。A little bit less。

![](img/13f3c34aeca4e45732e15609ba01749b_698.png)

Just。So our conscience is。

![](img/13f3c34aeca4e45732e15609ba01749b_700.png)

呃。It's easy。I'm going。Try around with the minus O2。Just to see if he didn't break anything。

I don't know what sorrow。Warning is that。Function not in line， Okay， man， I said in line just for。

It's for reference purposes。

![](img/13f3c34aeca4e45732e15609ba01749b_702.png)

Okay。Yeah。Okay， this one's pretty cool， I think。Dude games getting so。Nice。

Now let's check out this guy。Yeah。This is great。😊，Really。Look at all those comments。

AhI got stuck there a little bit。Not sure if that was me or the game。So。

I really like those particles。They look like。Like fireworks。So maybe we should do it。

 we should do like firework sound effects。That's it part。Yeah。

 we are going to play around as a bit bit of flying out。I do like the contrast in this level。

We should also play this level like black and white。Just so思。D。This is complete nuts。Okay。

It's got better and better， I think， really。It。Almost the point where it。

Interesting enough for I don't know people to start getting interested in on that while dude。

 this is like crazy， okay， manage to control。Yeah。I think each game more than we add like each arcade game。

It's going to get。Really， really cool because。Even the pong and the space invades one that we didn't actually put a lot of time into。

Doing that was really cool。And the controls are really solid too。Yeah， I'm really。

 really enjoying it。What do you guys think？This bill is going to be pretty cool。

 I think it's going to be the first。Actual cool build because it's。I think that's pretty。

 now we got to a oh， lost all those startup。You got to a pretty， I don't know。

 solid point in terms of gameplay。Because you know。

ItKind of it does need to a little bit of a fuel work， you know。

 even though we should really focus like we did at the beginning。On just the。On just the base。

Base mechanics， let's put it that way。When you do add Philly。It starts to becoming a nice game。

basically this one's pretty hard。Oh， we hit the edge， that's why we've got a huge ball。Do that。

 I was super saved there。Okay， I'm not sure I'm going to make it， though。是。So。Yeah， I don't know。

 maybe maybe this sense。Maybe it's a little bit too hard。Although。WhenWhen we get the neighbors。

 we do get nice。好。But the edge guys are pretty hard。次。I don't know， I think it's doable。

 and think's pretty cool。I stopped to look at Chet and I was lost， oh my God。Okay。

God that try I really liked。Adding both the speed。And the normal in position as a modifier to the ball speed。

So you really want to do that calmly， those three guys over there。They are hard。

To hit almost almost hit。7。呃。Okay， I'm going to play that again。



![](img/13f3c34aeca4e45732e15609ba01749b_704.png)

You know what？I think there'll be it for today。We can play around the game modes in the next so I think。

That was a huge success in the first。G paper。So we the size， let's have these guys here。Small呃。

More few。Sttop。Which is screen shakeake。S time is not really it。UI stuff。YouI show timers。And。

Let's do like。終わ？ゲも。Better。呃 levelss。Okay， so it screen shake， and make start lab animation。

And review the science。OkayUI showtimers。That's about it。Better levels。Nice cleanup on the gameplay。

 I don't think we need to do like a bigger cleanup now。It's pretty manageable。It is。

 I think it's like in the border of manageable and not manageable。But I think we can keep。I mean。

 it's a0 line files， not that big。And it's relatively well structured。I mean。

 there are some things we want to clean up like this。

But we don't know what you want to put it here yet， I mean， all this stuff want to put here。So， yeah。

 I mean， the things we could put out out there， let me see。Maybe like the power ups， I don't know。

 I don't want to start split that into functions。Like the play movement。

 you probably do a like player controller file。Yeah。But， I don't know。Not yet。

 this game is pretty small too。The initial gameplay exploration， I would say， is done。I changed done。

So。Let's。More a few stuff， or let's do like better levels。UI lets do UI better levels。

More efficient up， nice cleanup， more gameplay exploration。And apologize。So next time around。

We are going to start doing more engine stuff， so we're going to go back to the engine so today was really productive。

 it's great。We've gotten a lot of stuff in the game。Well， but it was like。

It' was just two and a half hours， not that much。So yeah， we're going to start doing rotd racks。

Maybe float upon colors， but our colorss are pretty well， I think， well。

 yeah because we lup them all the time。I don't know， maybe they'll be the profiler pass。Not sure。

Who did Rex？Audio 3D bitmap， menu and5I0。Thatll be that'll be cool。

 Maybe we do like just rotated racks one because we're going to have to do。Maybe just like。

Maybe just。Or。Partartics。

![](img/13f3c34aeca4e45732e15609ba01749b_706.png)

So this way， we don't have to do collision。But mean。

The rotation part of the code is pretty much just。Colllision， so well get that for free， pretty much。

 although it is point versus yeah。I know。Yeah， we should definitely add。Rotated racks for particles。

Then V maps also maybe she should do that like in a long go。Good maps for power ups。Dude。

Look at those points。So yeah， I think I'm going to do rotateator racks and business next time。Doude。

That was like a perfect one。And maybe the speed is too strong， the speed multiplier。

Kind of thinking that。I don't know but you want to be kind of controlled， right？

Look at that animation。Dity。That's so cool。That's really， really， really cool。

Gaming C I mean of culture I see。 well， thank you。I do appreciate you appreciating。The culture。



![](img/13f3c34aeca4e45732e15609ba01749b_708.png)

Okay。

![](img/13f3c34aeca4e45732e15609ba01749b_710.png)

So。That is it， so we are going to the realator accent and。Oh。

 it doesn't matter that it's just for particles。Roated rackx， Bi next。 That's next time。

 Then we're going to do audio and threading。Then maybe floating point colors， I don't know。

 I don't really care about that。And then menu in5IO and that'll be the engine improvements。

 then we're going to go back to the gameplay。More than。Okay， so thank you for stopping by。

 it's been a pleasure creating the game。And hopefully you enjoyed it as well and maybe learn a few things。

If you want to watch all the live streams， you can go to my YouTube page。



![](img/13f3c34aeca4e45732e15609ba01749b_712.png)

Which is YouTube。com/day Dan。And then you can watch the whole series。

 we started out with a blank file from scratch， no libraries， no nothing。

And then we started no incrementing， know a little bit， you can see all the Alex con linecos。

 thiss for fun。Let's do cloud。I' see。We have。1，400 lines of code。Plus like 400 blank comments。

 so you have total like 1900 lines of code。Not that much but not that little as well。

 so it's starting to get starting to become a nice game as you can see so check out the YouTube channel or you can see all the episodes as well like as clips and things like that。



![](img/13f3c34aeca4e45732e15609ba01749b_714.png)

And you can also download the game for free on HI， which is dZdam。h。

o and you can download the game I'm going to post this executable next time now it's starting to become a fun game right have to change all these screenshots is are pretty old。

And then I'm also going to post the source code for free。

 so if you want download the source code and play around with it。

 maybe learn a few things experiment， maybe do your animations， your feedback improvements， right？

I'd love to see that as well， so that's it， I hope you enjoyed it and I'll see you next time thanks for watching。



![](img/13f3c34aeca4e45732e15609ba01749b_716.png)

![](img/13f3c34aeca4e45732e15609ba01749b_717.png)