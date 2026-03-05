# 【从零开始用C语言制作游戏】 p05 Making a game in C from scratch! Ep 05： -Programming the Game Desig -BV18i421a7DD_p5-

Hello everybody welcomele to today's live stream I think we have a pretty cool live stream for you today because you're going to start implementing the core game design idea of the game that was like the thing that when when I thought about I was like okay this games worth making Okay I'm not gonna tell you yet we're just going to start programming but if you want to come here to the HIO website you can download the last episodeode source code so you can follow along if you want you have the excecutable in the source code for each episode or you can go to the YouTube page and I watch all of them we have four so far。

😊。

![](img/a8dd2b7c2e064a5802e967ba681ac481_1.png)

And we started out with a blank file， so we we typed everything on the screen on the stream。

 no no libraries， no cheating。 we just you know， we banged our heads against a couple walls。

 a couple of metaphorical walls， but we managed to do a lot of stuff so far。

 So this is what we have in the game。 so far we started out making a breakout clone。



![](img/a8dd2b7c2e064a5802e967ba681ac481_3.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_4.png)

So we did like a softer render。Utilities and things like that。 So we did a。This space set up。Okay。

 then we started implementing some other cool ideas。

 so first of all I started playing around the shape。Of the， of the blocks。 And then we added。

Some power ups， like invincibility。Like， let's see see。 It's invincible。 Now we also added。

Power downs， right， I ink， that's what we decided to call them。Okay， so we crashed。嗯。

I think we crashed because we didn't finish the power downs， Yeah， pretty sure see。

 because I just hit the power down there。And the red square， and I don't think we have all of them。

So啊。We hit an assert。I'm not sure how to go to thisassemb from here。Yeah。

So if you just set the next statement， forget about that assert。I think we can， yeah， I died， well。

 okay。So I had a few ideas based on the other game， but let me show you the other ones， this one。

 which is the one with two balls。And we were kind of thinking about the math of how to make the two ball speed be you know reasonable for the player。

 and I think I came up with a cool idea for that。So the basic idea is。Okay。

 that's all we have for now， oh we also implemented this other one。



![](img/a8dd2b7c2e064a5802e967ba681ac481_6.png)

Yeah。Yeah， so the basic idea is let me get my notes here yeah we have to implement that the player has three chances I'm going to start typing out those ideas in a。



![](img/a8dd2b7c2e064a5802e967ba681ac481_8.png)

Or coder。Yeah， the game， Okay， so we are going to implement the player。Has three chances。

Because it's pretty hard so far to you end the first try。诶。And we also should。Sure， yeah。

 I'm going to just。Review if。We didn't forget。Any power balances without implementation。It's a。没。

Okay。😊，And。Yeah， so the idea of the two ball。Levels。Is that each ball。Tag。Flag， for instance。Flaag。

不有。Say recalculate。It's。Speed。Based on the position。It is。The moment。It changes。Y is the D P， Y。2。

Be down so the basic idea。Okay， so we're going to yeah， calculate speed so that。It will， always。Take。

X seconds to go to the player。Yeah， so the basic idea for that I'm not going to do that today。

 probably， but the idea is。

![](img/a8dd2b7c2e064a5802e967ba681ac481_10.png)

If if the ball like hits this wall。Let's say this is 10 units， okay。

 just for it to be easy to explain if the ball hits here and that we won we won't hit the player in one second。

 it's between be 10 units per second。But if it hits a block like here。

It speed should be five units per second。This way， we can start with a ball like going up and a ball going down from the middle。

 and theyll always hit the player in the same time。Like we're going to， you know。

You're going to keep switching， hey， Marcus。

![](img/a8dd2b7c2e064a5802e967ba681ac481_12.png)

Nice to see you here。Today we're going to implement that cool idea that we discussed。

That are kind of a。I kind of type down and you through more ideas it's about the block movement and this system is going to allow us to make the unique things in the game。

 you know the cool game design core I that I had in mind。To make this game。So。

What I'm going to do quickly， I'm just going to create a new level， right？

It's going to be this level。😊，And I'm going to see how cool will that be。 First of all。

 I'm going to do， let's see level 0。😊，All I'm going to do is to create。嗯。Create。

A couple of actually just one。Go a create one。Block， block。Okay。😊，And。Yeah， maybe no spacing。

 and maybe I can do like。Ex1 by 5。And I don't even remember all those parameters。

 we added a lot of stuff last time we added a lot of mechanics。Okay。Rivy。0。Y offset。

 maybe you can do like a little bit of Y offset X offset spacing。

And'm going to add a little bit of space。Just a little bit。And also we want to change the size。

 and we also have to pass that as a parameter。

![](img/a8dd2b7c2e064a5802e967ba681ac481_14.png)

Okay。

![](img/a8dd2b7c2e064a5802e967ba681ac481_16.png)

Yeah， that's kind of it， but I'm going to make it like really smaller。 So the half size， let's see。

See， this is hard coded。The X have size。 Let's。Framer。来。Have size， okay。And everyone， here's。

Right before the right blue。可以。可以。可。😊。

![](img/a8dd2b7c2e064a5802e967ba681ac481_18.png)

And this one is gonna be。

![](img/a8dd2b7c2e064a5802e967ba681ac481_20.png)

嗯。Not sure I liked that。

![](img/a8dd2b7c2e064a5802e967ba681ac481_22.png)

I'll try， like。

![](img/a8dd2b7c2e064a5802e967ba681ac481_24.png)

Maybe like eight by。Maybe I should make them even smaller。

 how big is the power up just for reference？

![](img/a8dd2b7c2e064a5802e967ba681ac481_26.png)

Power block。It's well。P black。Sizes two by two。

![](img/a8dd2b7c2e064a5802e967ba681ac481_28.png)

Yeah， so I guess it's going to be two by two。 I think that's the smallest we can go， okay。



![](img/a8dd2b7c2e064a5802e967ba681ac481_30.png)

Yeah， okay。 this is kinda， it's kind of okay。 I'm gonna make like。



![](img/a8dd2b7c2e064a5802e967ba681ac481_32.png)

8ight by two。Now you want to start moving this guy， right？



![](img/a8dd2b7c2e064a5802e967ba681ac481_34.png)

Yes。Okay， let's just。

![](img/a8dd2b7c2e064a5802e967ba681ac481_36.png)

It's just。Like-30。

![](img/a8dd2b7c2e064a5802e967ba681ac481_38.png)

ok。Going to start moving him so in order to do that， all we have to do。



![](img/a8dd2b7c2e064a5802e967ba681ac481_40.png)

I think that had two functions。I'm going to add one， right here。In each block。

 I'm going to do like simulate。L for level。I went to pass the block。On the current level。

I'm also going to do the。Cimulate。Okay。Simulate。来不。That takes the current level。那就。Simulate。Block。

For。No。Up here， we had the idea of the game mode state。Right， but we kind of deleted that。

 we' going to add something back in the same。And the same idea， which is the。Game。

 that's a level state。We're going to make that a union。But not。For now。What I'm going to do now。Yeah。

 I am going to do that I'm going to do like level state。你是个能比明年。And it's gonna be a。State。Okay。

 this one I'm going to save。Like the enemy DP。What is a E2。And they're going to save the enemy。Okay。

That's it for now， Pa， on the simulate level， all I'm going to do is I'm going to add the enemy P。

Dot X。That's add 10。You know， this is just or I should also pass like the DT here。This is， you know。

 it's just for。Of course， you get started。And the simulate block for level over to block。嗯。

Yeah we're going to do block。P。Not sure， because the idea is。

This black pin is relative to the enemy P。But if we set that。Yeah， oh that's not do anything。NVP。

 it's going to be game。 It's going to level state。Dot p dot MP。 and that。Is in case。Our level。Is off。

在。Okay。Level。Current level。嗯。😊，And we should also， you know， we just added that level。Stripped。

Just also make that。して。And in the start game。I'm also going to0 that zero。来过。Okay。😊。

Simulate levels are going to pass the DT。Okay。Actually， you shouldn't see anything， right。

 because we're not outside offsetting the block。 Now， what I am going to do is block P。

Maybe I should just I'm not sure I should return like a V2。Like a。The new block key。

Not sure this is the best idea， though。 So the result is going to be the block P plus equals the level state。

ImGo to do the same thing here。Plus let us take pg。enep。x。Actually。You to do a。

So all I want to see now is the blocks moving。As a whole， okay？Itturn out。Result。Es black。



![](img/a8dd2b7c2e064a5802e967ba681ac481_42.png)

Yeah。

![](img/a8dd2b7c2e064a5802e967ba681ac481_44.png)

And' see what we have。Oh yeah， we also have to change that。To see a late liker level。直播。

He equal this guy。

![](img/a8dd2b7c2e064a5802e967ba681ac481_46.png)

Okay。😊，Okay， that was。

![](img/a8dd2b7c2e064a5802e967ba681ac481_48.png)

A lot。

![](img/a8dd2b7c2e064a5802e967ba681ac481_50.png)

Let's just do it like three。

![](img/a8dd2b7c2e064a5802e967ba681ac481_52.png)

Is that correct，Oh。Yeah。Anmy P。Plus， equals。3。Well， this should be like three units per second。



![](img/a8dd2b7c2e064a5802e967ba681ac481_54.png)

Doesn't look like three unitss per second to two。Let's just put a breakpoint there just to see。Okay。

 nice colors。 Yeah， at the end of last stream， we added a quick colors just to create Samsung visual variety。

And。The idea is to make a whole path in the deep field and colors are really important and that already changed a lot of the field just doing some more interesting colors and that was really random if you watched that stream。

That was really， if we didn't think about that a lot， I almost did， but。I didn't， okay。So。

We're here on this guy， simulate platform level。And I'll also put a break point here。Okay， so the p0。

 the D T E there small。 So yeah。Okay。And then when we should add the block P。To the enemy P。Yeah。

 I'm not sure why that was so fast。We just。We're also going to write no proper movement called but for now。

 that's just no。

![](img/a8dd2b7c2e064a5802e967ba681ac481_56.png)

Check out， Yeah， okay， this is a little bit better。Or because they're accelerating。Okay。

 this is gonna be cool。

![](img/a8dd2b7c2e064a5802e967ba681ac481_58.png)

Okay。What we're going to do is going to be like a really stupid AI for now。In case guys haven't， oh。

 I'm not going to say I'm going to let you guys see well if。The ball zero dotp dot x， right？

If it's greater means if it's to the right。Of the enemy P next。We are going to put a DDT here。D d p。

Which is the acceleration。Let's do it like。还。Else。We're going to do the DDP。Dont why。Yeah。

We should probably do it else if just in case we were like。At the exact position。EDP。t X。

Equals minus-。Okay， and now we're going to add the proper equations， which is the。The D P。

It's going to be plus equals the。DDP， right， so have to。To write that full exam。 So going to be。And。

The MEDP。I think I'm going to add like a pointer。To the letter。St。This where you don't have to keep。

I think that all the time。嗯。Okay。Yeah， we bad。Okay。We're going to add the pun。Emy DP with the DDP。

Times， we have multiplied yet。 times the D T。Okay。😊，That's the basic equation for the velocity。

And for the position。We're going to be the same thing here。Right，2 be。

I'm goinging to add the position。To the velocity。Times the DT。Right。

And this is just like the basic equations of motion。So， we can have a。

We can keep the benefits of having an actual acceleration。

 so we can add friction and we can see it continues to move。

 not just a weird setting the velocity hard codely。Okay， and we're also going to add。啲。The D， right。

Times。啊。TheDT。Yeah哦。DP is not a member of pun。地铁。Ovision from V 2。To F 32。Okay。

 we don't have a square function， let's add that here。Okay。😊，Now有。嗯。



![](img/a8dd2b7c2e064a5802e967ba681ac481_60.png)

Let's see what we have so far。

![](img/a8dd2b7c2e064a5802e967ba681ac481_62.png)

Okay， we have nothing。Or maybe it's like okay， we have something。



![](img/a8dd2b7c2e064a5802e967ba681ac481_64.png)

嗯。I suppose that's wrong right if it's to the left of me。

 I'm going to do the other thing and probably way too strong as well。



![](img/a8dd2b7c2e064a5802e967ba681ac481_66.png)

Okay。At least it's move in moves， right？Okay， so let's see。Okay， so this size。

 this size does nothing and now he gets away。

![](img/a8dd2b7c2e064a5802e967ba681ac481_68.png)

If the ball。P X is greater than the enemy P。To X。Yeah we're going to have to。Do that slowly。哦。

So that's one problem。And I suppose that was correct at first time around。



![](img/a8dd2b7c2e064a5802e967ba681ac481_70.png)

行。Okay。

![](img/a8dd2b7c2e064a5802e967ba681ac481_72.png)

嗯。😊，嗯。Just to make sure I'm going to set these guys。Should the level state harm any key so。

We're going to have like just one block to show where everyone is at， so let's see。



![](img/a8dd2b7c2e064a5802e967ba681ac481_74.png)

Yeah， so that thing was wrong， see this is what we expected。

So now it's going to try to change the direction， really it slowly。



![](img/a8dd2b7c2e064a5802e967ba681ac481_76.png)

Okay， so this can be stronger and that was wrong。来吃。Okay， yeah， that's wrong。

Because we are adding every， so that's going to be a little tough。

Maybe we should have like a flag for。Relative。Position。嗯。Okay， so this is what I'm thinking。

 Not sure this is a good idea， though。But。We have the blocks。The block stripped。Yeah。

 we have the block。We should， I think I'm going to add here a pointer to an origin。Right。

And every time I play around the block P。I'm actually going to。You know。Offsive by the logic。

H not sure this is a good idea。Or maybe， you should just add like a relative fee。Yeah。

 I think we'm going to do that。So I'm going to add。82 relative。Okay。When we spawn the blocks。

So luck luck。This is a really bad name， by the way， when we do that。

I'm going to set the bolt relative。皮。Okay， yeah， let's just do that， do this thing again。

Just so we know every time we use the block P， so this one should be the block P。Yeah。This one， yeah。

 this one should be。I think pretty much all of them should be the Black P accept。When respond。Yeah。

Like， yeah， do collision。Simulate block for level。 Yeah have， this one。

 we're going to have to change。Yeah。Yeah， this is this spawn， we're also going to make it relative。

Yeah。And yeah， this is going to remove entirely。Okay， so let's go back。史要你。你来不。Block for level。

No more results。Now I'm going to change directly to the block B here。

 so we're going to have a default case。Whi will be。That block。T。😊，Equals。The block。But in this。Case。

Let's do why。The block P is going to be the relative P。First。This guy。I think that's not。

And then we can actually。Yeah。Its。怕死啊。Have to do the add V2。Okay。😊，If you guys have any questions。

 be sure to drop them in the chat and I'll try to answer them。



![](img/a8dd2b7c2e064a5802e967ba681ac481_78.png)

Let's see。Okay， it's trying to go right。It's trying to change the direction and that's pretty funny。

😊。

![](img/a8dd2b7c2e064a5802e967ba681ac481_80.png)

I'm going to add some friction just because。😊，You know， once it picks up speed。

 it's hard to go the other way， that case， I think it's going to be， oh， it's going to be sweet man。

Okay， so we have the DP I'm going to add。A friction。Friction。

Which for now is just going to be the DP。Like time a constant。say10。Maybe tastes too much。

And then I can just set the DtP to be the friction。Start and here， I'll do the DDP。Dot x。Plus。

 equals。Yes。

![](img/a8dd2b7c2e064a5802e967ba681ac481_82.png)

Okay。😊，s see I think's going to have a hard time to move at all in this case， yeah。

But maybe he can change speed quicker， Yeah， he did Okay all I have to do is to increase this gap。



![](img/a8dd2b7c2e064a5802e967ba681ac481_84.png)

啊，你查一下。

![](img/a8dd2b7c2e064a5802e967ba681ac481_86.png)

Maybe a little bit。I see。

![](img/a8dd2b7c2e064a5802e967ba681ac481_88.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_89.png)

Yeah。Yeah， still too much fri。

![](img/a8dd2b7c2e064a5802e967ba681ac481_91.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_92.png)

Okay， start to be better。Yeah， see that change of of。Yeah， that that was pretty sweet。



![](img/a8dd2b7c2e064a5802e967ba681ac481_94.png)

Even going to add like a lot here。

![](img/a8dd2b7c2e064a5802e967ba681ac481_96.png)

Just see。ま。And we can play around that pretty much。Yeah。ok。😀ふ。😊。

Now it's going to be a little bit hard。Or maybe impossible， really。Oh， not impossible。Okay。

Just inconvenient。And you also have to to block。position。This is pretty funny， okay。切。😊。

He actually thinks he's strand。He actually thinks he's hitting the ball。Yeah。Okay。Po him。Okay。

 so that。Is one of the main ideas I wanted to play around with。To make。Each game， each level。

Like a throwback to an actual game。But all of them are going to play as if we were breakout see so this is Pong。

 then we can do like spa invaders， you can do Teris。You can do all sorts of stuff。



![](img/a8dd2b7c2e064a5802e967ba681ac481_98.png)

You could add the bulk position prediction to the blocks。So they can avoid it。



![](img/a8dd2b7c2e064a5802e967ba681ac481_100.png)

Yeah， certainly we can do like。Yeah， but I'm not sure he wants to avoid。The ball。

 if we wanted to avoid the ball， we could just like change this thing here。



![](img/a8dd2b7c2e064a5802e967ba681ac481_102.png)

Yeah， I don't know if he wants to avoid or actually or maybe it both。Yeah， so。Oh， we also capped him。

 right？

![](img/a8dd2b7c2e064a5802e967ba681ac481_104.png)

So。😊，ok。Let's do this is the desired P。If the desired P do x is greater than I don't know but we do have the arena half size。

 yeah。If it's greater then they're to half size。Minus， well， we don't have like a whole block。Size。

That's just hardcode1 now， if it's greater than 10。啊。We're going to set it to this。

And maybe going to do。Like。Desired D P。And then we can do like the desired DP。啊。Equals。

Multiply the desired。D P by minus0。5 looking。This going to。And to try to go as far as you can。Yeah。

 that X。And， but we also have to change here to the。And this one's correct。This one is correct。

 but this one to be the desired。

![](img/a8dd2b7c2e064a5802e967ba681ac481_106.png)

Now， let's see， he's going to try to get away。Yeah好都是。嗯。😊。



![](img/a8dd2b7c2e064a5802e967ba681ac481_108.png)

I was like good dad。And let's see the real thing here。Oh， when we。When we on the blocks。

We have eight blocks， which one is。2 in half size plus a。Yeah， I'm going to save like。Pong。

 let's do like level。 state dot P。Equals， let's do eight times。Well， yeah， eight times。

Two and a half。Plus， this guy， which is the。The spacing。Dot p， dot， let's say， enemy。Size x。Okay。

你 we。か。Oh， yeah。違入って。Okay。Now we can use here the enemy have signs X。enemy。Have size。Yeah呀。

Then I'm going to do。Other collision， if it's less。Then minus this guy plus this guy， maybe you。

This is wrong， it's going to be the arena， it's going to be this whole thing。Yeah。



![](img/a8dd2b7c2e064a5802e967ba681ac481_110.png)

Okay。Yeah， okay。That's a little bit bad， it's not 100%。But we can fix that later。



![](img/a8dd2b7c2e064a5802e967ba681ac481_112.png)

Because the goal is kind of to get to get the ball like behind him so we can get like。

Li bit slower movement here。Maybe a little bit of slower friction。



![](img/a8dd2b7c2e064a5802e967ba681ac481_114.png)

Because we want to get the bulb behind you， you know， that's part of fun， right？

But we want that to be a little bit tricky。Yeah， this is not hard like at all。

So maybe it's going to get boring。Quickly， no one realized the joke。

Maybe you should just add the boat to be really fat， okay， that was pretty cool。Yeah。



![](img/a8dd2b7c2e064a5802e967ba681ac481_116.png)

I think the ball's going to be really fast。So。 I'm going to go through all the blocks。

Do we have like here a block？Yeah， we have the。The speed multiplier here。

Lets do like a base speed multiplier。See， that's the one thing that I really wish that weren't see that。

It exists in C++ is default parameters because this sort of function， you know。

It's not fun to play like a thousand parameters。Yeah， like this。

I don't even read I just added the parameter， I don't even remember remember。What order I added at。

 let's see。It's the last one before the libraryry。So the case comes going to be a one。Yeah。Okay。Okay。



![](img/a8dd2b7c2e064a5802e967ba681ac481_118.png)

But this one， let's do。

![](img/a8dd2b7c2e064a5802e967ba681ac481_120.png)

Let's make it faster。So when you hit the ball， you' going to be like really fast， yeah， okay。

 now it's way better。ok。屎。Yeah， okay。 Yeah， That was cool， yeah。Oh， this may be a little too hard。

 let's see。Or maybe not。嗯。😊，That was nice。

![](img/a8dd2b7c2e064a5802e967ba681ac481_122.png)

And what you can do just for the fun of it。We could add。嗯。Let's do just like a July。

It could add a power down。Everyone here。Don't we have like a？So in the block block guy here。

You block。Powed， power block。 Yeah， power block。Itm to be equal to power。啊。Let's do。Yeah。

 you only have like insecure。I mean， we have strong blocks。



![](img/a8dd2b7c2e064a5802e967ba681ac481_124.png)

Yeah。

![](img/a8dd2b7c2e064a5802e967ba681ac481_126.png)

Okay。Now， now it's getting interesting。Yeah。Okay。呵。啊。HK心。Yeah， I kind of liked that a lot so。



![](img/a8dd2b7c2e064a5802e967ba681ac481_128.png)

Let's start doing more of those。

![](img/a8dd2b7c2e064a5802e967ba681ac481_130.png)

We should we should really add block movement as you like。Space invaders。Tects。

And then we do these guys， player has three chances。Yeah， we did finish。

It's going to call like finish。Her downwns。Two balls， I'm going to try that。嗯。Yeah， that's it。Yeah。

And that's part。I fixed the bug。But weird ball behavior。Pro。At life。Okay。

 so let's do the spacing be one。还可以买。Here。When we create the level。You know what？

I'm just going to prevent the crash。呃。This crash right here。Yeah。Just because。

I don't know kind of suck well have it do nothing。Spimment crash， Okay， so case。L 0，6。Innovavators。

You know what？I think I'm going to add a ver guy just for the fun of it。



![](img/a8dd2b7c2e064a5802e967ba681ac481_132.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_133.png)

Like this guy。So I'm going to add here in the side just so I can use it as reference。



![](img/a8dd2b7c2e064a5802e967ba681ac481_135.png)

Okay。嗯。Yeah， and then we do like block block。I do like。嗯，Create。In favor。Then you can pass。Like。でき？

So I think I'm going to do like a real stupid thing for now。It just is， so it's a little bit easier。

嗯。So we have like。1，2，3，4，5，6，7，8，9，10，11。Then we have one， two， three， four， five， six， seven。

 eight。I don't entirely remember how I do this that this。嗯。Maybe it's just like this。You see， yeah。

Okay， I don't really remember how much chest said。It's like。Can I do like this。No。Yes。

 it's not going to line up perfect。Notly enough。So。呃。It'sLike four guys here。And then we add one。

Like this。Then， we add。The full row like this。And then， we are， like。like this。It the whole line。

Yeah， okay。This is going to be fun。And then。I start out here like two， and then there's the eye。

It just， like 3。And there's the eye， and then there's two。And I hope I do a holding one like this。

It's kind of funny see。Okay， and then I do the en。Which starts out。For the eye。Ens。

It's something like。Like this。Yeah， okay。See now that's an art skill。Yeah。

that was just for reference。Yesさか。Okay， now we have our invadevar guy， now let's pawn some blocks。

Actually， how' is it going to be？Sure， let's just sing thatbuger because I think I may。

 I may want to do an array， really。Yeah。I may actually do an array。



![](img/a8dd2b7c2e064a5802e967ba681ac481_137.png)

Guys。嗯。We just talk creative later。This is a pretty cool control B。

Ps up the new function breakpoint dialog so I can just like control B。

 type the name of the function and name stops。

![](img/a8dd2b7c2e064a5802e967ba681ac481_139.png)

So yeah。Yeah， I think I'm going to have to do an array， so it's going to be an array。Of these guys。

 now I could add the。卡了。Yeah嗯。That looks good。So。😊，For each guy in the array。For each character。

 right。Fer。W哦。At？If at。那里 go toth space。Like Ed。Okay。Yeah。I'm going to make the pay the starting fee。

Just make it easier for us then we can do it like the center calculation shouldn shouldn't be that hard。

Yeah， I'm just call it P。And then well else， if you don't， we if we shouldnt add a block。

I'm still going to add the。The block size here， so the block size may be two， so let's do two。あんとは。

Let's add a guy。 Let's do how they add guys。We do like this。 We should make， this is a function。

 maybe， yeah。Like。We have like a new。Do we have like a。好啊。Yeah。Get next available ball。

 Let's do like， a。嗯。Rock。一点。Next availableva。对吧。That's what。Yeah。S enough。Now， what's gonna be。

Get next the above block。And we should also do that。Let's see。 the block。多啦。嗯。

And then now that we're doing the。So we're going to get the next available block。

And then I should also do like this basic operation line。And not really。So。So the life to one。

Set the block。 half size to。Block size， block size。嗯。And set the reality。

I think we're going to need a lot of blocks for these guys so the relative of P。

It's going to be the P。And then we add this guy。Yeah。And here we add the why。Okay。

Let's see if you need anything else with black color。Let's do full wide for now。

And the balls being multiplier， you can play around with that as well。Let's do you like。1。Plus。He。嗯。

1 plus I。Lets see，1，2，3， Yeah， we。Didded my a。Okay。Make color。Great。And a good to。Invadders。favor。

Okay， let's see what we have。

![](img/a8dd2b7c2e064a5802e967ba681ac481_141.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_142.png)

Okay？Oh。

![](img/a8dd2b7c2e064a5802e967ba681ac481_144.png)

Yeah， we have to do this。

![](img/a8dd2b7c2e064a5802e967ba681ac481_146.png)

Okay。I'll think after that break point。切。Yeah， and we still crashed。So let's do this。Slowly。At。

This guy looks good。 Oh， we should also have to reset the exposition。嗯。Yeah。で。Okay。

 now the at is zero， so we create a block。Okay。😊，12。P here。Okay， now。The at。Oh， yeah。 I forgot the。



![](img/a8dd2b7c2e064a5802e967ba681ac481_148.png)

To diver reference that point。Okay。That's the thing， and we also have to do the。Original X。P x。

And when we go to the new line， we set the original x back。So everyone starts at the same X。



![](img/a8dd2b7c2e064a5802e967ba681ac481_150.png)

Okay， let's see。ふふ。Well。呵。That was not particularly pretty。



![](img/a8dd2b7c2e064a5802e967ba681ac481_152.png)

But I think it's because of the position that we added， this is the half size。So we have to。

Offset by the half size。Tice too。Okay， now see， this is where the fun begins。

 I should say I we start to say， oh， okay。😊。

![](img/a8dd2b7c2e064a5802e967ba681ac481_154.png)

It's upside down， w， it's going to be really cool。It's upside down。And it's also wrong。 something。

 Let me。The print。Screen this guy。And how do I rotate？Okay， so I think we have。1 to me。Guys。嗯。



![](img/a8dd2b7c2e064a5802e967ba681ac481_156.png)

Yeah。😊，This is wrong。One too many in the right side of the eye like this。Correct。



![](img/a8dd2b7c2e064a5802e967ba681ac481_158.png)

嗯。

![](img/a8dd2b7c2e064a5802e967ba681ac481_160.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_161.png)

Actually， I'm not。

![](img/a8dd2b7c2e064a5802e967ba681ac481_163.png)

Let me just put here in the side so I can。是。Okay， so。The eye is always okay， this line here。

Now this line。回埋。I know what to tell you， dude。My name is Dan。



![](img/a8dd2b7c2e064a5802e967ba681ac481_165.png)

And I like to make games。I have released。This。Pretty cool game， I think。For the PS4 and the PC。

 back in 2017， it's called Gilliososis Hunt。

![](img/a8dd2b7c2e064a5802e967ba681ac481_167.png)

That was pretty cool。And the story is I finished the game。AndThen I was like。

I really don't know how to program for real， So I spent like a year or so。

Learning actual programming。And this train is the kind of way to have fun because I'm doing games for a hobby now of。

As a， as a。Work， so I like to have fun making games， so this stream is a way to have fun。And yeah。

Microsoft welcomes you。 Okay， yeah， we are doing this for Windows Microsoft。😊，No， I don't like him。

 though， so。

![](img/a8dd2b7c2e064a5802e967ba681ac481_169.png)

Yeah， you can check out my YouTube channel if you want to see。

The other the videos in the series we started this game from scratch。And yeah， from nothing media。

 you can download the source code on the HIO page。

![](img/a8dd2b7c2e064a5802e967ba681ac481_171.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_172.png)

And now we're doing。Cool gameplay stuff， but for some reason。



![](img/a8dd2b7c2e064a5802e967ba681ac481_174.png)

The drawing didn't turn out to be correct the first time around。

 I think like this should be right and this and this。And this。Yes， that's it。



![](img/a8dd2b7c2e064a5802e967ba681ac481_176.png)

Okay， if anyone has any other question， I can certainly answer it。 Okay， cool。

 now let's make him not upside down。😊。

![](img/a8dd2b7c2e064a5802e967ba681ac481_178.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_179.png)

Isn't that cool， Oh， you're already collididing with that。Yeah， okay。

 that's going to be really cool dude， but it's like it's huge， it's like really big， really big。😊。

You can probably do like 10 times more。 you didn't make a loan， No， I did not make a loan， yeah。



![](img/a8dd2b7c2e064a5802e967ba681ac481_181.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_182.png)

I started out making the game alone。 If you go to my YouTube channel。

 you can see how far I went alone， which was， was pretty funny the way it looked like。😊。



![](img/a8dd2b7c2e064a5802e967ba681ac481_184.png)

I did like this thing。Al by myself， which was like the basic idea for the game。

 so you are this alien guy。And then you yeah， you can jump around， you have weapons。

 so it' the idea is that it's a shooter and platform， I use the unrealre engine。

Right by the time he was releasing for the public the 4。0 version， so yeah。

 I can pick up your weapon and you can shoot guns and then I did like this enemy guy。

And then at this point I realized that it was a lot of work it was a pretty big game， you know。

 I spent three and a half years developing that game。

So yeah it was a lot of work so at this point I started to focus on the alpha version。

 let's call it that so it's I stopped doing the art for the most part I did this monster and things like that but I focus on the gameplay So yeah I did that open my at this point I said okay。

 let's try to get more people on board and since。I was pretty much a student back then， I was like。

 okay， let's look for other students。They are really interested in making this game。

That are not like seasoned professionals or anything， but they know their stuff。诶。

The whole team worked in the game for two years， so I spent like one year before and half a year after on my own。

Or for some reason you get glitchched。呃。But in the middle yeah。

 I had help was like 10 people working on the project at one point。

 I don't know why the YouTube video kind of glitched down I'm going to throw the link in the chat so you guys can check out the steam page if I'm not mistaken yeah。

 it just came out of sale， but it's pretty cheap。

![](img/a8dd2b7c2e064a5802e967ba681ac481_186.png)

I don't know， I think it's like $10。Yeah， you can also buy it on the PS end。



![](img/a8dd2b7c2e064a5802e967ba681ac481_188.png)

So yeah， I did got help， that was pretty cool。But after the game release， I was like， okay。

 I need to take a step back。Yeah， thanks， you said that's cool， happy flower， thanks。

So I took a step back and I was like okay I have to really focus on becoming a better programmer because by the end of development man oh that was like really craziness going on because I had to port for the PS4 version but I didn't actually know C++ that well they't have to integrate with F mod the middleware for audio that we use and the rearrange was all crazy and stuff and have to upgrade the versions really quickly because the SDK would expire and had so much problems that I couldn't actually know how to fix so it was really weird it was like okay I'm going to try to hack these stuff and ask people online and this happens when you use like a lot of tools and you don't actually understand them which I didn't at that time the beginner part there's a lot of people with tutorials and things like that but whent go to the more advanced of like shipping a game with the PS4 there was like a really shortage of tutorials so that's what I found so that was really hard so I decided to take step back and focus on programming and I fell in love with lowlel programming so for this。

I streamers had to do a game。With no no libraries， how many downloads did it again get well commercially was kind of a failure so you can see that we have a 3038 reviews I don't remember off the top of my head how much how many downloads we had。



![](img/a8dd2b7c2e064a5802e967ba681ac481_190.png)

But it was kind of a less than 10，000， maybe 5，000 how much money did I make？Not much。

 the game didn't pay itself， to be honest， because we traveled。

I live in Brazil and we traveled around Brazil's largest advance， like BGS。



![](img/a8dd2b7c2e064a5802e967ba681ac481_192.png)

W is the Brazil PG has。James。The Brazilian Game Brazil Game show。

 that's a pretty big one and we went to Sao Paulo like five times。

 Sao Paulo is like the big city in Brazil where everything happened。And at this point。



![](img/a8dd2b7c2e064a5802e967ba681ac481_194.png)

Where we started going through these events， we spent a lot of money because for the people working on the project。

 you know most of them were students and we kind of a little bit of freelancing work。

 so we spent a little bit of money with that， but the events are really expensive so we didn't actually pay it again back that's why you had to close the company The company closed before I couldn't release the game。



![](img/a8dd2b7c2e064a5802e967ba681ac481_196.png)

Was it worth it then absolutely dude， it was awesome to release a game to the PS4。 You know。

 I learned a lot。 I used to say that if I were to sit down and talk to the person the person I was when I started the game。

 when I finished the game。😊，I like would disagree like 100% because I changed so much my views on everything。

 not only game programming， but also game design and team management， production， running a company。

 making money， you know， talking to people， you know So it was absolutely worth it oh it was great。

 I absolutely loved it and doing a project This size which was three and a half years really taught me a lot about production and scheduling and how can I how can I how can I get things done basically and that's really really important So when we're doing like small size games like we're doing now So it's got to my HIO page ever since I publish that game also did that Vr game。

😊，With this company， but ever since。

![](img/a8dd2b7c2e064a5802e967ba681ac481_198.png)

Ever since I released that game， I worked mostly on small game jam kind of games。

 how big a team we were， I think 10。Max， at that point。Let me see those three audio people。

There was like。Yeah， about 10 or 11， I think 10。Yeah。😊，So people， know from all over the world。

 but mostly local people here students from Brazil。So。Yeah。

 so the money wasn't worth it in terms of like financial success， but it terms of releasing a game。

 a complex game， you know， learning a lot about production， about programming， about game design。

 about， you know， getting things done about business， about financing。

No with Page we talked to a lot of， you know publishers we met a lot of people who got got to be known in Brazil a little bit that was pretty cool。



![](img/a8dd2b7c2e064a5802e967ba681ac481_200.png)

So yeah， oh man， absolutely worth it。But now I think the point is， in my life， I'd say。

 is to really focus on become a better programmer and designer。

 So when I tackle projects this size again。I can do， I can be more confident because you know。

 there are a lot of flaws in this game， it was my big my first big commercial game after all。

 I worked on games for advertisements before I worked on this game。And that was a whole different。

 you know， whole different game， you know， so to speak， because there were really small games。

 and we didn't really care about the player only about the。The client that paid for the game。And so。

Yeah， I really left there with a sour taste in my mouth and I was， okay。

 I want to I want to make games for entertainment I want to know。

I'm going to be cool games that I think I would love to play and people will like to play so that was the idea behind this game so I spent like three and a half years doing that。

That was really cool I dream about making my own game， dude making games are awesome。

 you know the risk of that I fell into actually that now I like so much making games that I play you know a lot fewer games that I use to do。

 but I think that's a nice progression， right？Because I fell in love with making games。

 it's really cool， man。When I found Ali about real， when it released unrealre engine4。

 when it left the be and stuff， I really liked the way it worked in terms of。

How easy was to get something cool on the screen so I started you know I was an artist before I started programming。

 so I then started know just creating interesting things in unreal real， that was the basic idea。



![](img/a8dd2b7c2e064a5802e967ba681ac481_202.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_203.png)

And then that things start make to become more complex so you can see like the very first prototype of the game。



![](img/a8dd2b7c2e064a5802e967ba681ac481_205.png)

I modeled and animated this guy， and then I programd him moving around。



![](img/a8dd2b7c2e064a5802e967ba681ac481_207.png)

And then jumping， things like that。 Then I did the shooting system。



![](img/a8dd2b7c2e064a5802e967ba681ac481_209.png)

My look kid a huge idea。 I don't like video games， but I like see programming。

 Your project looks cool， cool。 Thanks， thanks， man。😊，Yeah， thing about about video games。

 A lot of people I know don't like。😊，Video games per se， but like making video games。

That's a pretty interesting distinction， I like them both。But I can definitely see the difference。

 So maybe like you will like making video games do it。 I don't know。 You can definitely try。 So yeah。

 using an engine is a nice way to start。 But at this point， I really like doing games from scratch。

 And if you if you watch out if you watch from the very first episode in my YouTube channel。😊。

You can see we started out with nothing。So if you like programming， do do from Rio de Janeiro。

 Di Jane Janere， you can definitely see the progress of doing the C game and maybe。



![](img/a8dd2b7c2e064a5802e967ba681ac481_211.png)

You can try things on your own。So let's go back unless you guys have any more questions。

 drop any questions if you have them since we're doing like this little off topicic chat for a while。

It's good to have more ideas about the game we're doing。Okay， so let's go back。To our evar guy。

 so this is turned out really cool。But what I actually want to do。Is to make him a smaller。

 like a lot smaller。

![](img/a8dd2b7c2e064a5802e967ba681ac481_213.png)

Right， shouldn't be， shouldn't be hard。

![](img/a8dd2b7c2e064a5802e967ba681ac481_215.png)

I think we kind of baked that as a constant here， so maybe if I just do like this。

 it'll be 10 times smaller， maybe。

![](img/a8dd2b7c2e064a5802e967ba681ac481_217.png)

Wow， how cool is that， man？And now renderer really handled that， you know。

 it's not 100% perfect because we don't have like subac pixel rendering。But that。Okay， yeah， wow。

 that was crazy。

![](img/a8dd2b7c2e064a5802e967ba681ac481_219.png)

Oh， and you also have to change the y thing， because the way we structure this code is that the bigger the bigger the row he is。

The faster， the speed multiplier， but actually want the other way around。

Because we want to start pretty slowly， so you're going to do like the max minus this guy。

Time if this guy， okay。I love playing League of legendgends， however。

 many of my changess don't follow my taste， so I'd love to change them the amount game where there's only one thing I'm satisfied with。

 however it's way more difficult said than done。 Yeah， it's difficult。

 it's more difficult said than done， but it's not that hard to get started。

That's the cool thing about making games now。 Hello， Timmy， Nice to see you， man'am。

The thing about getting started at Happy Flowers that。I'm 0。4 done with the same yeah。呃。

But I don't know， maybe you shouldn't start， you should start like with a Sboard game。But。

And you know， the key thing about making games is not giving up， I mean。

 three and a half years to build eosis。

![](img/a8dd2b7c2e064a5802e967ba681ac481_221.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_222.png)

I mean， I always gave up a couple times。Because。

![](img/a8dd2b7c2e064a5802e967ba681ac481_224.png)

It's really， it's really tough man， I mean， you get a little bit sad in the beginning in the middle。

 you're like， oh， there's no wind sight and then you're in the end and like oh， I think this suck。

 oh， I' wan to finish it。You know， oh， everything went wrong and I oh。

 I wanted to be to be a better game。 So the key is not to give up to be really。Really， perseverant。

Perseverance， is that awkward word？Basically not to give up like at all。

 And starting small makes it easier not to give up。This video is you are uploading to YouTube。

 I check the playlist you're name to making a game from scratch。The sca building list。

 sorry for the English。 Yeah， it's okay。 Your English was nice， man。Yes。

 we are uploading it to YouTube， we have this making a gaming from scratch。

 I'm going to throw the link in the chat here。Yeah。

 you can check out all the videos we we're live streaming the whole thing。

 so we started out the blank file we did like a hello program， hello world program。



![](img/a8dd2b7c2e064a5802e967ba681ac481_226.png)

And then we started doing the actual game， you know starting out explain a window know getting graphics done。

 gameplay now we're doing some nice some crazyaz stuff because the idea for the game was to start out with a basic you know breakout clone。

 which we did in a couple last streams。

![](img/a8dd2b7c2e064a5802e967ba681ac481_228.png)

Which is this guy， just the breakout clone， right？Not too much about it。

 but then we started adding cool mechanics like a lot of people in chance like Marcus had a lot of cool ideas about mechanics they wanted to add so we did like this wall pattern and then we added power ups like let's see this power invinscibility。

And we had like another power up， yeah this ones a pretty cool comet that kind of drives through and these are like power downs so yeah yeah I lost。

呃。How do you financely intend people to work Well， in Brazil。

 there's a thing called it's kind of an internship。But it's not really internship。

 it's kind of a junior position。And that's pretty， pretty cheap。 And most of them were students。

 So we had to， you know， that was pretty， pretty cheap。 And my dad also helped me to pay。

What we had to pay for these guys So yeah that's how we finance we live in a country that people don't actually get a lot of money for working。

 which is sad but good if you're trying to get started。And we also looked for students。

 so they didn't charge like much at all at all， really。

 because they wanted to learn just like I learned a lot， everybody learned a lot。So yeah。

 that was basically how we finance his end and it was like two years off a company。

It's not like we had to like get1 thousand100000 right off the bat， you know， in two years。

 you can get a lot of。We can start little by little and by the end we had to close the company because the money ran out basically。

 right？So I had to go back here， apartment， my parents lived and to finish the game on my own that was part of the process。

 but that was cool kind of it was fitting like here's journey right。

 I started out on my own on my bedroom right and then I finished my own on my bedroom that was pretty cool。

But that was a lot sad because I really love the team。 Yeah。

 we can we should like do like a live stream where everybody comes together and play the game。

 things like that that'd be cool。 So yeah， we started playing around with the game against this one's pretty cool。

 but we have to we have to play around with that a lot。

 So we have two balls and you can only destroy the blocks They are' in the same color but it's not really playbo now。

 This is a bit weird。😊，And yeah， this was a variation of that one。Yeah。

So we have to play around with that a lot。But this one are the cool ones that we're implementing。

 so it's breakout， but with old games。So we have like a punk level， which is this one。

That's really cool。And then， yeah， I need time。 Actually。 Oh yeah。

 And then we're doing the space invade once。But why spend time on this pixel game because we're doing this from scratch。

 man， since I'm doing a games for a hobby now and I don't have like。

Money to make another game this size。And I do have like another work and things like that。

I can tackle a three and a half。Pixel。3 and a half pixels I read， P thatet。

 a three and a half year project。Right I can't do that right now so I want to do a simpler game that I can actually finish so that's a cool tip for you that wants to start making games I'll start with with small pixel games man like yeah。

 there are a million others pretty much like this one but there are not a million ones that you created See that's a distinction and team is right it's fun the point of this live stream just to have fun and to learn So we are learning a lot if you see the progress we had a lot of problems and we're coming up with solutions for that for them and it's great to make games dude not only big games but also small games and this game we're actually going to finish and post on HIO and things like that。

😊，It was also from scratch and a real engine。 Yeah， it was from a real engine。

 but since you used like an engine， it's not actually from scratch because the engine does like a lot of the。



![](img/a8dd2b7c2e064a5802e967ba681ac481_230.png)

A lot of the， let's say boilerplate work， like rendering work， collision work， animation work。

 things like that。Aet management streaming， pouring to the platform， like that。



![](img/a8dd2b7c2e064a5802e967ba681ac481_232.png)

So yeah， by using an engine， it's not really from scratch， but。Yeah， I mean。

 I had to create all the assets and all the mechanics that program the gameplay。

 the gameplay was from scratch， if that's your question， but the game as a whole is not。

 the angel really helps in the beginning。And it's really a opinion to as if don't understand that by the end。

 do you think pixelix games can still be nice？I'm learning Open G and I really want to make a pixel game Yeah。

 dude， I really like this kind of game， not only to learn。

 but also to play because you can really get interesting mechanic out of them because when you get like a complex game。

Like it not really a complex game， but it's a more evolved game in terms of graphic and stuff。

 a lot of it getting in the way of making the game design interesting。

 so by making small pixel you know pixel art games you can really focus on first of all。

 understanding the whole program， which is a good point。And the other point is to。

Is to play around the mechanics to make them interesting so in this scenario where everything's more controlled see we just for this guy we just implemented the movement equation by hand and we could really understand the variables in place so we added friction。

 we had acceleration， things like that， so by doing that when you're doing a bigger game like heliosis hunt for instance。



![](img/a8dd2b7c2e064a5802e967ba681ac481_234.png)

You have a lot more understanding， a greater understanding of everything in the game。

 so it definitely helps making these kind of games and they could be really fun yeah。



![](img/a8dd2b7c2e064a5802e967ba681ac481_236.png)

So。0。2 was way too small， let's try 0。5。

![](img/a8dd2b7c2e064a5802e967ba681ac481_238.png)

Yeah， that's more like it， maybe it's still a little bit too small。Yeah。

 once there's like one or two lefts， you're going to be really hard， let's do like 08。



![](img/a8dd2b7c2e064a5802e967ba681ac481_240.png)

Why not use the tools you have right now you don't use your hammer。

 use your hand to punch the needle down the wood？

![](img/a8dd2b7c2e064a5802e967ba681ac481_242.png)

呃。Yeah， the thing about using tools is that I use them for a long time。

And if you don't really understand them， you have a really hard time。

 especially by the end of the development process when you're trying to ship the game。

 we're just prototyping， yeah， whatever do use whatever tools you want。

 But if you want to do like a serious game which I do want to do a serious game know way bigger than eosis。

 but I'm just not going to do them not right if you're doing this kind of game you really need to learn your tools that's essential like and I didn't at the time so I spent a lot of time trying to to hang things together know searching for things that didn't actually understand So taking the time that I'm doing in this months to really understand what a game is made up of so to speak。



![](img/a8dd2b7c2e064a5802e967ba681ac481_244.png)

When I go ahead and use tools or build my own tools for that。

 the understanding is going to be so much bigger the understanding that it's going to be easier to ship。

 it's going to be more robust when I come up with random bugs， I will be able to fix them。

 so there's a lot of value of understanding the whole process。

 even though there are tools available to make you get started quicker。

 but the thing I found out with the O hunt。

![](img/a8dd2b7c2e064a5802e967ba681ac481_246.png)

That by the end of the process。You know if you don't understand the tools， man。

 you're going to have a huge hard time and they don't tell you that when they tell you about the game engine。

 they only tell you about the beginning and the beginning is great。

You start quickly you have a lot of fun， that's great， but by the end。

I'm going to open the window here just because it's really hot。Yeah， Brazil。

 even winter and even when it's like everyone say it's really cold， it's really hot。 I like the。

 I like it， though， yeah。😊。

![](img/a8dd2b7c2e064a5802e967ba681ac481_248.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_249.png)

Okay， let's see 0。8 is enough。Yeah， this one looks a little bit nicer。

 so let's start adding movement to these guys。

![](img/a8dd2b7c2e064a5802e967ba681ac481_251.png)

I'm going to add a whole bunch of them。Like。😊，Ver， cr Vaer， yeah。Hey， Noah。

 I'm going to automate that because I'm a programmer， am I not？Okay， so let's add like five invaders。

Like this。And then there's theres that like。Okay， Car enough， but you can read on real engines。Psets。

 why not use them like presets test when a goes to B。 you gain Ainsburg。 Yeah。

 that's the thing I I already made a game using these presets and。



![](img/a8dd2b7c2e064a5802e967ba681ac481_253.png)

It's nice to understand。

![](img/a8dd2b7c2e064a5802e967ba681ac481_255.png)

What that preset does。So。When you actually go to use them， you' have like a huge hard time。

 but that's not that's not I think the beginning of the process。

 I think for Yohan was great I would not have made Yohan if I hadn't use them real that's for sure especially at that time and now I can't even do that and it would take like a lot a lot longer but I think it's a process you know it's a process of。



![](img/a8dd2b7c2e064a5802e967ba681ac481_257.png)

Of learning so yeah I learned to use tools now I'm going to learn how to make tools so yeah that was really bad let's do have times 10。



![](img/a8dd2b7c2e064a5802e967ba681ac481_259.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_260.png)

Okay。

![](img/a8dd2b7c2e064a5802e967ba681ac481_262.png)

Okay。That。Didn't work。Let's do times 30。 I think that's right， the call thing。Butら。Actually。😊。

It's going to be zero。And then。While that for few minutes is not space。 Yeah， Marcus。

 that's the point， man， that's the thing， you know。😊，That's the cool thing about this game。

 It's breakout with all old arcade games。😊，That's where we're going。With this。

 So we did pong already， right， and we did spacing invades。

 And I think we're going do ts today as well， I hope。😊。



![](img/a8dd2b7c2e064a5802e967ba681ac481_264.png)

呃。

![](img/a8dd2b7c2e064a5802e967ba681ac481_266.png)

Maybe going to do donkey Kong next Yeah， it's going to be fun okay。



![](img/a8dd2b7c2e064a5802e967ba681ac481_268.png)

And。

![](img/a8dd2b7c2e064a5802e967ba681ac481_270.png)

Yeah， that's what I wanted。30 times。系。Yeah， I'm going to do them by hand just because。



![](img/a8dd2b7c2e064a5802e967ba681ac481_272.png)

はい。I see how many。

![](img/a8dd2b7c2e064a5802e967ba681ac481_274.png)

And then also we're going to add like an offset like。M 50。-5，0，25。



![](img/a8dd2b7c2e064a5802e967ba681ac481_276.png)

And 50。LetSee if there'll be enough。

![](img/a8dd2b7c2e064a5802e967ba681ac481_278.png)

Okay。

![](img/a8dd2b7c2e064a5802e967ba681ac481_280.png)

But I also have to center that， I'm going to center that later on'm going to do like to do。To do。

Center this。Well。That's pretty easy thing we're going to do that so the original P。

I'm going to do like P dot x minus equals， we have the block half size。Times。You know。

We just liked one。We are facts accelerate。参与起来。Sorry guys didn't understand why I got 50 T shirts that you don't want when you could get one T shirt that I really want for the same price。

Youude， that's really the wrong analogy。

![](img/a8dd2b7c2e064a5802e967ba681ac481_282.png)

啊。I don't know， everyone has their own interests。It's hard hard to explain if you don't get it。

Maybe should you you know download a game engine like unity or unrealre and start having fun man that's the point just start having fun and maybe you're going to find out that they suit your needs。

 you know this kind of a line of thought that I do have is not common between game developers。

 even people who release games so I'm not going to say that I'm right。But I am going to say that。

The things I am learning， you could not learn by using a tool。That's for sure。So yeah。

 maybe this is a bit too fast。 I don't know。Yeah， it's a bit too fast。



![](img/a8dd2b7c2e064a5802e967ba681ac481_284.png)

Let's do like。Plus75 times that So yeah I think if you download to and sort of playing around it。

 you're going to find your own way and maybe your way is gonna be just use tools and be better at using tools and I'm pretty good It really can tell you that I use like I've been using for five years so I can do games really quickly and of high quality there I mean。



![](img/a8dd2b7c2e064a5802e967ba681ac481_286.png)

As high quality as I was able to do for the release， right？

But I want to trade different interests now and if that's not your thing， that's okay， no problem。

Yeah， so I think the speed looks nice now and I'm going to。



![](img/a8dd2b7c2e064a5802e967ba681ac481_288.png)

And'm going to add。点么点。Do like five guys？And that's due I。Times。20。4 one let us do。

Why why why why why why why。

![](img/a8dd2b7c2e064a5802e967ba681ac481_290.png)

企。😊。

![](img/a8dd2b7c2e064a5802e967ba681ac481_292.png)

That was not right。

![](img/a8dd2b7c2e064a5802e967ba681ac481_294.png)

Dude， let's wrong with this for loops。

![](img/a8dd2b7c2e064a5802e967ba681ac481_296.png)

I'm going to step into them just to understand them。Vder， yeah。

So the first invader gets's call it position， let's see。us 50， that's right。

 so we should see him at least。Right。So I'm not sure why we don't。はい。



![](img/a8dd2b7c2e064a5802e967ba681ac481_298.png)

We really don't。But if it passes zero to this guy。We see one guy。Oh。Oh no， I sorry。

 I thought I didn't， I wasn't doing like a T2。So I have no idea why this is wrong。

But I don't really want to think about it。At this point。Because。I know。

We're probably going to do like a better thing later on。

So I'm just going to copy and paste like four times。And they do like。-25， minus-50。And。



![](img/a8dd2b7c2e064a5802e967ba681ac481_300.png)

不及。😊。

![](img/a8dd2b7c2e064a5802e967ba681ac481_302.png)

Yeah， so the problem is we're using the position wrong， I suppose。That's really。 Oh， I think we have。

 yeah。No， it's actually because we have a limit on the block size。



![](img/a8dd2b7c2e064a5802e967ba681ac481_304.png)

Another the black count。Yeah， I see five guys are okay if I do like start doing more of them。



![](img/a8dd2b7c2e064a5802e967ba681ac481_306.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_307.png)

Life， I do like two more。We're going to run out of blocks。

 then we're going to have to reuse the blocks。屎。😊，嗯。😊。



![](img/a8dd2b7c2e064a5802e967ba681ac481_309.png)

So so。Yeah， I can really go back now。Yeah。Like this。😊，Then we can do like blocks。

And they had like a lot more blocks。We already have 256 blocks。How many blocks？



![](img/a8dd2b7c2e064a5802e967ba681ac481_311.png)

Doesn't fade。Take。嗯。Let's see next block。As he call it again？Noumb blocks。So zero。

 and when we finish the first invader。if there's the first invade here。46。

So we have going to need a lot more blocks。

![](img/a8dd2b7c2e064a5802e967ba681ac481_313.png)

That's do。

![](img/a8dd2b7c2e064a5802e967ba681ac481_315.png)

As to these。thousandhousand0 blocks。Okay。Yeah， starting to look better。

 I think I'm going to do like just three roles of them。



![](img/a8dd2b7c2e064a5802e967ba681ac481_317.png)

Three rows。

![](img/a8dd2b7c2e064a5802e967ba681ac481_319.png)

Okay。😊，And I think。Yeah， that's really perfect， actually， right。So let's start moving them， right？



![](img/a8dd2b7c2e064a5802e967ba681ac481_321.png)

Okay， finally， we took a long time to make them draw， but they look good。

Marcus could just have that surprise moment when he rejoined the stream， that was cool， Okay。

 so we have the p simulation， right？😊，Which is this now we're going to do。

We're going to do the spacings one。Oh six invaders。And then I'm going to create theva state。

And we're going to have the enemy P。Yeah， it's going to be the same thing。So state。

But we're not going to have the DP。We are going to have a timer， though。Yeah。😊。

Timer and let's say account。Let's just say a movement。Timer。And movement count。O。Yeah。

 that looks right。So。Let's do now the simulation。For the Space invades game。All right。

We're going to get the level。 I don't see level。St。嗯。です。你给。嗯 levell。You better state。Inva。

 I should really call invaders。see。Yeah， okay， so we have it。

And we're going to just decrease the movement heat or increase it。Yeah， that's increased movement。提。

😊，With an A， right， invaders？And I're going to increase that by the Dt。And if and that's also due a。

Movement。Target。And then when we start the game mode。えるす。They're going to set。啊Yeah。We're to set。

The game。When I lead to programming with Python。I didn' understand what you need， man。

Oh okay yeah sorry I didn't see the first message this is the first video I'm watching why you're programming on two IDs forcode and research Studio the forcodeder project looks nice like Vim do you recommend I use Vm to programming with Python when I'm programming with Python yeah I use two because the forcoder is not a debugger so I can only type here know I can also run the compiler so if I press al M。

I run this。This build file here。It actually hos Vi Studio and then it shows me the errors right so this is pretty much like。

Which could almost say it's an ID because it comped， but it doesn't have a deder， right？

Visual Studio， however， does have a debuger， so I can play the game from here。



![](img/a8dd2b7c2e064a5802e967ba681ac481_323.png)

And then when I hit that particular point。

![](img/a8dd2b7c2e064a5802e967ba681ac481_325.png)

I can you know。See， the variables and analyze the game and whatever。

The reason I don't edit individual Studio because I like Forcodeder way better than Vi Studio as a text editor。



![](img/a8dd2b7c2e064a5802e967ba681ac481_327.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_328.png)

So。Yeah， I use these tool the these two ways of of。



![](img/a8dd2b7c2e064a5802e967ba681ac481_330.png)

ProgramSo I don't actually change the code here， I just change it here。

And I run the game here because I can't like pause and analyze the variables and stuff。呃。

I don't know I don't know if you recommend if I would recommend forcoder instead of them。

 it's a lot of a personal preference thing， I really like forcoder。

 I think know it's auto indent thing， see if I start typing with a parenthees， then if I do like a。😊。

curly grace here， it also in dance things really quickly and it's like a ghost in dancer I don't have to like if I press space。

 nothing happens， I'm press in space right now and doesn't in because indentation is virtual。

And it's， I really like it， it's for free， you can download it on eachI。



![](img/a8dd2b7c2e064a5802e967ba681ac481_332.png)

The free version of it， there's also a paid version， which like $10 or $12。



![](img/a8dd2b7c2e064a5802e967ba681ac481_334.png)

Then you can like customize。Yeah， so there's a 12 version。

 but you can also download the free version here， and I use the free version dude and it's like perfect。

 I really like it。

![](img/a8dd2b7c2e064a5802e967ba681ac481_336.png)

Yeah， I'm not sure if I recommend to switch though because you should programming whatever you are more comfortable with right。

 but if you want to give it a try it's for free man。I really like it。Yeah， so we had the Mo to。

The Va movement T。Yes。Greater 2 or equal than greater。Where then are equal to invadevars， a movement。

呃。Target。I I'm going to decrease that by the movement target。

 and I actually I didn't think I set the。The default。Let's see。E。两点。I was going to do like a level。

State that invaders。Dot。嗯。Mo门。Target， yeah。Equals two one， let's say every second。呃。

Every second I'm going to do what I'm going to just change the position。Invaders。

You we also know which side we're doing it， but for now let's do one step at a time invaders。NP。N。

t x plus equals， that's there to go 10 units at a time。Level invader state， yes。Invaders。State。

Unitialized。Yeah， level state do invaders。The address of that。Okay。



![](img/a8dd2b7c2e064a5802e967ba681ac481_338.png)

Okay， let's go back。

![](img/a8dd2b7c2e064a5802e967ba681ac481_340.png)

オケ。是。I'm not sure what to say about that。That is wrong in so many levels。



![](img/a8dd2b7c2e064a5802e967ba681ac481_342.png)

First of all。Actually， maybe just。Maybe just like one level。But why。Did that move that fast？

That makes no sense， we had the same problem。嗯。Yeah， no， I don't know， let's get a break point there。

 but。

![](img/a8dd2b7c2e064a5802e967ba681ac481_344.png)

Come on， man。That's been a break point when we do hit。So。If it's greater than target。

 the target is zero。

![](img/a8dd2b7c2e064a5802e967ba681ac481_346.png)

I thought I had just initialized that。Oh， I initialize that。

How is that not a compr error to put an expression here？This is like between the cases。

Because I guess technically you can do that， right you don't need to。



![](img/a8dd2b7c2e064a5802e967ba681ac481_348.png)

That was a stupid mistake。

![](img/a8dd2b7c2e064a5802e967ba681ac481_350.png)

So we're doing that every frame， now let's do this。Every one second。 Let's see。 Okay， yeah。Okay。

 now this is threatening。

![](img/a8dd2b7c2e064a5802e967ba681ac481_352.png)

I can fill the threat。Yeah。😊，And that's also change that。连了没？PX。



![](img/a8dd2b7c2e064a5802e967ba681ac481_354.png)

To be minus 25。で的に。

![](img/a8dd2b7c2e064a5802e967ba681ac481_356.png)

Yes。Dude， this is awesome。See。That's really， really cool。Okay。



![](img/a8dd2b7c2e064a5802e967ba681ac481_358.png)

Now。Instead of doing account。Movement count， when do you like movement direction or like a is。毛巾。

Right。And the default thing。T。Oh， I mean。Oh I miss Bel target。呃。Target， okay。And I to set。

The is moving。Right。😊，Too true。Okay。😊，And then I should also， you change it。The type hope target。



![](img/a8dd2b7c2e064a5802e967ba681ac481_360.png)

All right， well。We're still want to hit the wall， right？



![](img/a8dd2b7c2e064a5802e967ba681ac481_362.png)

Simulate lab， okay。If。Invadders is moving right。We should move right。And test， if we reached。So， if。

This guy。Got X， is's greater than。Let's see if it's greater than。40。Oh， actually。

 he's going to be like。We started out at minus24 when we hit。Yeah， this is going to be 25， yeah。

 because bigger than 25。Right now， I'm just going to change the direction。

Its moving right later you can do like them go down。The cooking thing。Okay。

 now all I'm going to do here is the other way around minus10， if it's less minus25 moving right。



![](img/a8dd2b7c2e064a5802e967ba681ac481_364.png)

ok。😊，Let's see what we have。So we should move right。To， that was pretty cool， man。Yeah。是。

As's not working。嗯。Why is it not working？I see。Let's。Stop at the moving right part。Okay。

 this is minus 15。This is minus5。

![](img/a8dd2b7c2e064a5802e967ba681ac481_366.png)

Oh， because we did the other way around。This one's false。

And we should actually just change the value。That sounds。That sounds less errorprone。



![](img/a8dd2b7c2e064a5802e967ba681ac481_368.png)

Now they should you paintpon back and forth in terms of direction。This is really a hard game。诶。Yeah。

 maybe I don't know， so far you only have like one shot， you have one life right。

 so it is pretty hard， but when we had like three lives for the player， maybe won't be that hard。

Yeah， 25 was too much。

![](img/a8dd2b7c2e064a5802e967ba681ac481_370.png)

Yeah， if you do like。We're going 10 by 10 so we should like 15。



![](img/a8dd2b7c2e064a5802e967ba681ac481_372.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_373.png)

I mean， it starts out like this， right， Eric， that's the normal first level。Okay。

 so you start out you play around the breakout， you know？And then you do like this level。

 and then you have more complicated stuff like。Okay， maybe there'll be par ups。

Right and then well let me get out the power up here， it's not random， by either the way， guys。

 we didn't comment random yet。呃。We are question okay so。I've got a power up。Which you know， make。

Yeah， like this。They implement another power up， which' is going to shoot more balls。

 things like that。This one's pretty hard， but this one。

I don't know if you're going to keep that or if you're just going to improve on that at the very least。

Which you have two balls and have to hit。But I think that's cool， I don't know。

That's pretty interesting。But you have to definitely change the ball speed。

This one' just a crazy idea。Uses the other mechanics。And these guys at the top。Yeah。

And this one that very starting to get interesting， this is Pong。Right。Wob， this is going to be hard。

 okaytie， let's see。哎呀。And now this is behaviors， now this may be hard。

Especially because we're going to increase their speed， right， with time。Yes是。嗯。

I didn't actually see if that was the right， okay， so that was the right position。



![](img/a8dd2b7c2e064a5802e967ba681ac481_375.png)

So we're going to make them go down， but only slightly。So instead of just moving the direction。

 we're going to do like。呃。冇羊。That's great， I love it thanks Matt clone style， thanks。😊。

And you can actually。You'll be able to download the game and the source code for free on HIO。

So right now， the game that I put， which is last streams executable， now very interesting。

This one's going to be pretty cool， know there's also going to be label and stuff。



![](img/a8dd2b7c2e064a5802e967ba681ac481_377.png)

And you can also download the source code if you've been watching the stream on YouTube。

 you can watch like the whole thing。

![](img/a8dd2b7c2e064a5802e967ba681ac481_379.png)

We started out with like a blank file and did everything everything from scratch on stream。



![](img/a8dd2b7c2e064a5802e967ba681ac481_381.png)

You can watch the whole thing and then with the source code。

 you can play around and maybe at your own levels and gamemos and who knows？That's pretty cool， Okay。

 so move down。And we're also going to set the move down to true。Right。Okay， and I。This should。

Be like， yeah。Move down。Okay， and if we are supposed to move down。Oh， I'm sorry。

 this movedown is already here。Like this。Okay， so if we are supposed to move down。系。

What we're going to do？Is just。We go。Let's do like It know three in this part。And and a half units。

Everero so slightly。Cool， I'm a first time watcher and also up to your YouTube channel what are you using for Raing open GL right now we wrote the Raer from scratch that was the first day so in the first day。



![](img/a8dd2b7c2e064a5802e967ba681ac481_383.png)

Wwhich you can watch like like here the YouTube's like Dan Z Dan yeah in the first day we wrote the platform layer so we opened like the Windows window and things like that and then we did the rendering with no libraries whatsoever so we did everything from scratch。



![](img/a8dd2b7c2e064a5802e967ba681ac481_385.png)

And thats pretty cool the renderer is。

![](img/a8dd2b7c2e064a5802e967ba681ac481_387.png)

It's pretty nice it's actually a pixel independent so we can do like a very small screen。

 can do super wide screen， for tall screen。😊，And I you'll be able to see the whole thing。



![](img/a8dd2b7c2e064a5802e967ba681ac481_389.png)

So yeah， that's pretty cool and you can actually even pay on full screen。

And the performance it's very nice because we're not like we don't have bitnas yet and rotd stuff。

 we're going to add like more stuff to the Ra later on， but yeah， dude no libraries。

 we may in the Po pass do an openGL version I'm not promising just because I don't really like OpenGL and this is simple game we don't need it。



![](img/a8dd2b7c2e064a5802e967ba681ac481_391.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_392.png)

So yeah， that's kind of what I've been working on for a long time now。

 well I a leverage from scratch for me， dude， that's great I mean。Having your own libraries。

Not only is it a great way to learn。😊，And also really fun。

You can really can really be useful because it's gonna be more and more complex dude that's that's great。

 Everything from the otherator to the list search trees， Yeah， well that's the idea of this stream。

 this stream we sort out with nothing and we're going to do this game and when you finish this game we're going to publish that on eachI the final version and I hope it's going to be pretty cool right and then you're going to improve on that engine so we're going to add open GL support and animation and I don't know crazy stuff we are going to add audio threading。

😊，And maybe bidmas for this game。And there's going to be more and more complex currently I'm working to my own scripting language to use game libraries that's really cool。

 I did。😊，A language like I played around with it for a while and it's great because learned like so much about data structures that I had no idea in terms of like know the tree stuff and going down the tree and changing the nodes。

 things like that that was a great learning exercises and it's also a lot of fun because you can really get the way I learned I structured the learning process was I was supposed to do like a calculator but I would type and expression and then I would partse that expression and solve that and give the result and that wasn't too hard so after that I started doing like variables and things like that。

 the language compiled to C。😊，Honestly， I had the most fun writing compilers， yeah。

 they are a lot of fun and honestly I start doing that。😊。

Because I was super inspired by Jonathan's blow。

![](img/a8dd2b7c2e064a5802e967ba681ac481_394.png)

Jonathan blows J， I don't know if you know that， but Jonathan blows like a big shot in the the。

The indie game community right， he's like an awesome programmer and he also also does live streams from time to time and he's been doing a programming language for like four years now。

I was going to make almost five years。And he has like a full playlist。

 they a compiler programming live streams， he has like 70 live streams of companion programmer and like 55 of like demos and if you watch the very first demo。

At the very first on top， he's so excited。Yeah， I've been watching him for。 Yeah。

 dude he is so excited about doing the programming language that you can't help it but you want to do one yourself。

 So that's what I did。 It turned it was just you know。

 I didn't actually finish it or anything which just like a learning thing。😊。

But it was great and the excitement was you know I don't know when when you watch someone exciting do something that he loves like Jonathan B and things like that。

 the energy really passes through that's one thing I want to do here I want to really show you guys。

😊。

![](img/a8dd2b7c2e064a5802e967ba681ac481_396.png)

How cool is it？😡，To make games from scratch and the learning process too。

 I recommend a big squid channel on YouTube。 that's a nice recommendation man。

 I'm going to show it here for the people later on YouTube。



![](img/a8dd2b7c2e064a5802e967ba681ac481_398.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_399.png)

Do do from Hugh generator is recommending Biquid。I would also recommend bitwise。

 I don't know if you guys know， can they bitwise。

![](img/a8dd2b7c2e064a5802e967ba681ac481_401.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_402.png)

Bit twice is great， that's where I actually learned to program compilers。呃。

It's a little bit tough if you're not like familiar with programming。

But as you go to like the twiceice do hemade dot network， there's like a ton of vessel。

 and the main thing about about the compilers is like。

It'sLike this the first like first 10 episodes or like 12。Yeah， so that was great。

 it's good selling a great channel， yeah。It made go back into a few years。



![](img/a8dd2b7c2e064a5802e967ba681ac481_404.png)

Okay。So yeah， these kind of projects， the ones that。

 you know you're just doing it because you're interested and wants to learn more。

Is the ones that usually you learn the most and have the most fun and you take when you go like when you remember the project that you did？

That you did， those are the ones that。You learn the most like in terms of data structures and things that you really were excited about can talk but I mean Biscrit is great。

 logical tough， okay？

![](img/a8dd2b7c2e064a5802e967ba681ac481_406.png)

Okay， so I don't remember， oh yeah， we did the move down， so let's see if we're going to move down。

Whenever。We， yeah， we did。 but we also moved。 Yeah， Okay， so that was totally wrong， honestly。

 so but we didn't finish。 So the move down， we're going to set that to false。



![](img/a8dd2b7c2e064a5802e967ba681ac481_408.png)

And this is going to be an else。

![](img/a8dd2b7c2e064a5802e967ba681ac481_410.png)

See how fast that was in terms of。Code editing。 That's what far codeder says， knowing the。

In the unknown statement， if you can call that， it says， we're going to make like not a text editor。

 but a code editor， See how fast that was change that piece of code。Okay。So that's pretty cool。

I'm not sure what we're going to do when they reach you maybe。

Maybe you should coll line with a block。There'll be game over or maybe if we can just hard code the position。

 I'm going to do that。Just hard code position。And if you reach like a certain position， ski over。

I haven't still tried for codeder， even though I see everyone using it。

 I't know if I came up with Yeah， the thing about tax editorers。

Is you have to use the one you're most comfortable with， right？

I was lucky enough not to be comfortable with anyone with any text editor before I use farcodeder。

But if I actually was using like vim for a long time and was really used to it and really liked it。

There's no point switching really， unless you don't like it unless you use it but are're like， oh。

 maybe I'll try a better one and things like that or a different one and I'll see if I like it。Yeah。

 so there's that。So I don't know。But I really like it。 still baffles me how I learn film。 Yeah。

 That's the thing I was like， oh man。😊，Can I do like a easierier step to write code fast。

 and I think I write pretty fast， not the fastest。But fast enough， I think。Okay。

 so this is pretty cool。I think this is really， really hard， I suppose。Really， yeah。

 someone said that that's hard now I'm starting to think this is really hard because there is a lot of guys right if I drop like a random power up。

That may start getting easier on you。I think I'm going to do that。

 I'm not need to customize my editor so I go see the subli。Yeah， you know what。

 the thing about customizing the editors I really don't like it either things are really pain the but for coder has a whole open customization layer that you're right on C++ or C and don't remember and you can do like whatever you want。

 you can turn that into any kind of editor right you can do like a model editor。

 you can do whatever you want pretty much。😊，Everything from simple things like changing the。

The key binding， two more complex stuff。But I just use the default version because I don't know。

I don't like to spend time on that stuff， tools。Yeah， so this is impossible。If truth be tolded。

 you can't win this game， right？Adam is nice to， yeah， a lot of people says a nice thing about Adam。

But I haven't tried it myself， okay， so at this point we should have died right。

 but we could have we actually so。Not sure。

![](img/a8dd2b7c2e064a5802e967ba681ac481_412.png)

Maybe if you just add a ton of power ups， that will be solved。

Let's add random to our ancient so we could add just a disclaimer。

So you guys don't be like oh crazy on me。

![](img/a8dd2b7c2e064a5802e967ba681ac481_414.png)

We could add just use the actual end。Random。

![](img/a8dd2b7c2e064a5802e967ba681ac481_416.png)

D and see。We could use that。Pretty much like this， we set the seed。And then we do the ran。But。

In order to learn， we're going to implement our our random stuff。Let's do a counter。

 let's see how much time it takes for us to write that， we're going to do an Xor shift。Algorithm。

 right？For a number generator， and the idea is super simple， man， and we have like this state。

Which is like a Nin。Right。And whatever you want a random to do。We just do this。That's really it。Yeah。

 that's the theme， man we I start studying that。What actually takes， it's really simple。 I mean。

 of course， you can do like way better and you like Cdy and。😊，More or distribution and do likeo。

True or random algorithm， things like that are more random than this random。

But it's great just to know what actually goes on inside the random algorithm function。

 so this algorithm is a very simple one that we can just。



![](img/a8dd2b7c2e064a5802e967ba681ac481_418.png)

Start using really， it's really easy。呃。We have the math。c， so we're going to do like a random。

And'm going to do like。Next， random。And we are going to have like a global see for now。呃。

Or maybe you should just call like random U 32。Yeah。😊，Random U 32。It's going to be an in line U 32。

And the state is going to be global for now。Like random state。

And we're going to start with a random seed。呃。Or if I haven't done my own preNe function yet。

 bring that one off。Really， that's pretty cool， man， because printf。

You can really do like cool of printf in terms of like the types， right？And like zero2 d。

That's pretty cool， and。That's a great learning exercise， I think。Yeah。

 but I don't know rare arts are really weird in sea。

So I don't know if I wanted to do legends just because of the。

 I also want to do the floating point stuff， yeah， the floating point。I don't know， I'm not a like a。

Expert in floating point stuff， but from what I've played around with。

 whenever I want to do like a text to floating point or the other way around。

 I just use the C library because。Yeah， that's a little bit more complicated。Yeah。

 depending on the robustness you want， like you can do like a very。Dirty， quick and dirty function。

Same I have a decent understanding， yeah， we could do like a decent thing。But。

The thing about precision， that's the complication。Mfias with pre neos。

 I have to think about birthing， right？What exactly do mean by buffer mean text buffery？

I'm not sure I haven't done it， so I can't like do。I can't comment in too much。I， I still like。嗯。

Result。It calls random state。And let's change X。For results。

And then random state is going to be resolved。And then we add the return。So， let us see。

If by just doing that。We have random numbers。Right？So。Have a start game， let's just do some。St here。

Random。You 32。Let's do like10。Or so。FG。

![](img/a8dd2b7c2e064a5802e967ba681ac481_420.png)

Okay。And the math behind doing all those shifts。I'm not going to pretend I understand right so we are one level deeper in understanding the random we got as far as to understand the code。

But not to understand the math。If that's our thing。



![](img/a8dd2b7c2e064a5802e967ba681ac481_422.png)

Maybe you can go like， you can do like a home。Crezy is thinking about。给你的。The mathth right， yeah。

 reading all these articles。

![](img/a8dd2b7c2e064a5802e967ba681ac481_424.png)

That's not really my thing，Isn't the output b？Yeah， so you do mean the tax output well。

You don't know the size， so you're going to have to allocate one way or the other， right？

Have no clue， I haven't looked into it much than a few examples。Yeah。Yeah。

 I think you can pretty much expect。To not know。The buffer size didnt have to do it like by hand。

The allocation。Bad enough either。If you get we're going to do like a console for the game or a print helper。

 we're going to do that like to print numbers and stuff。We are probably going to use the sprint half。

To change like from sorting point to text because。Yeah。😊，That's kind of I don't know。

 a deep hold or not， maybe clone style will be able to。Do his own thing， and then he can livestream。

Showing what he did， then we can implement that on this game。嗯。Isn't that a cool project， man？

I like to see that。 So first number looks random enough。Let's see， A，B， C， D，E， F。G， okay。

 let's see them all in text。So second one。Isn't that great？Do that， that's pretty random to me。

 and then we can do all sorts of crazy stuff with these numbers。



![](img/a8dd2b7c2e064a5802e967ba681ac481_426.png)

So yeah。Done pretty much， right？看。呃。And of course， we are going to have to change the seed。

But we're not going to do that for now。Like to do。Change the seed。To be unique。Her。

We are going to do that。But for now， all we have to do is now do like helper functions。

Like we can do like a random pool。And then we can just like return。If。The random U 32。呃。Yeah。

 I think that's going to be random enough， let's test。



![](img/a8dd2b7c2e064a5802e967ba681ac481_428.png)

Let let's change U 32 to B32。AndThen let's see if we got random balls。Yeah。1，1，0，0，0，1，1。Ptリ easyね。

I pretty cool too。呃。

![](img/a8dd2b7c2e064a5802e967ba681ac481_430.png)

Yeah， somorph fifth gave us a link about。The buffer you printf。In terms of floating points。

 that can be cool when you save that for later just a second。

I can learn a little bit more about that。The three types are buffering variabless。Yeah。

 so I don't really understand much about it so I can have to。Ltex programming manual， yeah。Yeah。

 that could be cool to understand， oh， has nothing to do with Greenf。What has to be foing point。

 though， no， no。So I kind of lost it。De line of thought of you guys in chat， I kind of lost it。

 it's okay。Let's just finished what we' were doing in terms of the power ups。So。Oh。

 we should also do like random in range。Like。Random int。And range。It has the men。And a max。

Can we do like。Enclo。Yeah， okay。We actually like random choice。 That's a nice one。

 that's basically this。It's basically a random blue， but you can change this parameter here。But yeah。

So thet random int in range。So we have this number goes from zero。Other way too， you know。です。

So all you have to do。Well， you know what， I don't think I'm going to go that rabbit hole now。

 I think I'm just going to do like the。Branom choice。Which is like this。Yeah。

 we can do like more randoms the later， but for now， you open a normal fire。

It's block buffer means the content I some the fire and buffer is full Yeah。

 I suppose you mean you mean like in the normal then the Linux library。

 I think that was what the link was about。Yeah， not sure， though。Okay， now when we initiate invaders。

But streams for SDD LDR are line buffer so。They get output when a new line is detected okay。Yeah。

 when I played around with that， you know， getting like Windows pipes to get the centered out and centered everything。

I had the hardest time because I found that was like a huge mess。Right。In later。

So I end up not going too deep。You understanding that。Because I wanted to do like。

Future some sorts of output of the program。I don't entirely remember。

I remember that was really crazy。Okay， so if。Rrandom choice， let's see if there's a chance in five。

If there's a chance to fight of doing this。We are going to set the block。The block。Okay。

 have implementation of LibpsC to reduce the rights in cause， okay， that's pretty cool， Okay。

 now I got it。Yeah， I got the context。Power block。See， now we should really do the random things。Now。

 because I have to think math。A little bit more messed up。就。Power。Yeah， I'm going to do the random。

Kt。In range。To me one。All the way to power count minus one。Okay， now let's program that。

I think you guys going to have to help me because this is the kind of code。

Then I really get wrong all the time。We're usually all the time with， right。

 randomand int in range takes a min。😊，Take a max。They're going to be included what is the random 32 random U 32 returns a random unsigned integer of 32 bits。

 so this one's our actual random， it returns everything from zero。To a。This number， right。

So this is what we can use for， so we have to use that。

And we also used that to do like the random a bow and random a bow with chance。

Eals zero should be the right。一科是。And then we should do the。没没听见 in。What do you mean what？



![](img/a8dd2b7c2e064a5802e967ba681ac481_432.png)

That's what we did for the past like five minutes， we came here to pi and got a random algorithm。

That's the XR shift algorithm。Because I said， okay， we could use。the CRT implementation of random。

 but that wasn't fun enough， we wanted to know what kind of code we have to do to generate a another algorithm right so we got this one which is pretty simple。

All I have to do is start with the seed right right now we are hard coding this seed and then we can change that later on。



![](img/a8dd2b7c2e064a5802e967ba681ac481_434.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_435.png)

Yeah， and then it shifts by these prime numbers here。

And I don't understand the math around it so I can't actually explain why it works the way it does。

See， but yeah， if you probably read all sorts of stuff about it right。

 and people build algorithms on top of that。To be more random， but this is random enough I think。



![](img/a8dd2b7c2e064a5802e967ba681ac481_437.png)

Yeah， so this is our random logo there so we got this guy returns from zero to max int at Max U 32 such hackcky stuff it's not hacky dude that's like math ma。

嗯。But I also like it， I like this kind of weird stuff to get interesting results and we tested it and it was great。

 it worked pretty much randomly I think。😊，But now we have to change this number。

 which goes from zero to this guy to be our number， so we have a range， right？

And the range is max minus min。So we're going to do into result equals random U 32。Modullo range。

Right？I think that's right。And then we're going to do results。Plus equals man。Bigturn result。

You know， I'm not sure this is correct， La brand has a type， okay， so right。靠 that。

Not sure this is entirely correct。But let's play around with it a bit。So here in the invader。

Let's do some tests， Okay， so we。We already test the random， but let's test the random choice。

That's like a random choice。嗯。Let's do like four。So it should only be true for like。

Every four times privately。And then let's do the random int in range。Random into range。

 that's like 0，10。Let's do a few zero chances。Then let's do like a minus11。Yeah。

 that should be helpful。Okay， isn't max exactly see， I always said I got。

 I got this wrong all the time， so max minus min plus one。You are correct。

 we were going to exclude the X。Nice calledmorpheus。



![](img/a8dd2b7c2e064a5802e967ba681ac481_439.png)

So when we do the。Create in。Let's see。All these guys so。Yeah， I think that was correct， we got one。

Out of。Six， out of seven， which sounds about 14， right？Okay， now let's test the random in in range。

 so we had， let's change it back to Desimal。We had five，1， eight， five， eight， zero， one。One， zero。

 minus one。That looks perfect to me。 What do you guys think now let's start using these numbers right。

 because we wrote that to use it Okay， so you already。



![](img/a8dd2b7c2e064a5802e967ba681ac481_441.png)

Have this system， so every five blocks， one's going to respond a random power up。

 may be a power up or a power down as we were calling it。



![](img/a8dd2b7c2e064a5802e967ba681ac481_443.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_444.png)

So yeah， let's see， okay， this is chaotic。Dude。If we thought it was hard before。

 now it was like super hard。

![](img/a8dd2b7c2e064a5802e967ba681ac481_446.png)

I don't think I'm going to spoil power downs。Like。😊，Do we have like the last， yeah。

 we have part of last。We're good to do like。Just the part up。



![](img/a8dd2b7c2e064a5802e967ba681ac481_448.png)

Because wow， that was crazy。Maybe we should do like。Yeah， not sure， let's see。Oh， that three， yes。

 it's going to be a art festival， yeah。We have to fix them。

 I think we're going to do that next stream。We're going to fix all the problems with the。

The power up like the comment was problematic， see sometimes it works sometimes it don'。He doesn't。

And。Now got way too many powers。And。Yeah， and I was like way too easy。

 but it's not interesting enough。Maybe I'm going to add like fewer invaders。What are those invaders。

 some kind of Easter， No man， that game is going be like。The game is breakout。

Applied to different games。That's the game idea。See。

 so start out with a normal breakout and then do like a little bit of breakout， fun， you know？

So we test。You， breakout， you know in different with power ups， things like that。

And then we do this game mode， which is pretty bad so far， but it's going to be good。

 I think in the end， which is like two balls and you have to each ball can only can only destroy the opposite color or the same color。

Yeah。Okay， this is chaotic for now。 And then we do pong， right。

 So this is our version of Pong applied。😊，In the。系事啦。Applied in a。And breakout， so this is P。

The collision is not 100% accurate。I have to change that later on， okay so。Yeah。

 so we got P or we almost got the hi。And yeah。I think Pongga are， pretty nice。

Pnoice average of difficulty and interestingness。And then space invaders。Right now it's really hard。

Maybe， maybe if I， if I。Maybe one ball should be able to destroy more than one block。

Like if you make them super small。Do you make some power ups like plus speed and plus size the ball。

 Yeah， we do have power ups， but。For now， we only implement like invincibility。

If I minute one that's kind of buggy， I call it comet。That one's supposed to go through the。

 the enemies。 Let's see this game all easier to see。 It's supposed to go through the blocks。

 That's pretty cool。 So that in a。😊，In the context of a。屎。😊，That was pretty cool， right。

 but it's not 100% yet， I don't know。It's kind of glitchy and we have like three of balls see。

 that's pretty cool。As well。

![](img/a8dd2b7c2e064a5802e967ba681ac481_450.png)

Like， yeah， we could do like plus size of ball。That's a good idea， so par ups。Let's do like。Power up。

Maybe you should just like this。他们。Increase ball sides。And the thing is， we got it wrong。

 the triple shot is the last， the power uplast。So we don't need to subtract one。

Was the trigger right now each block gets assigned whether or not it gets a power up。

 so when we start the level like this level， there's no power up right it's supposed to be like good old breakout。



![](img/a8dd2b7c2e064a5802e967ba681ac481_452.png)

This level， since we didn't have a random when we did it。

 we kind of made for every six blocks in the first two and the last two rows they're going to be spawning par ups I can cheat because I have like invisibility here and super fast speed here just see。

We can achieve and do like a yeah。Let's start destroying the wall like this。Okay。

 then the ball should be back here some time， yeah， okay。And。So if we destroy like the guys on top。

 they should give like power downs and they have like Easter death and。Strong blogs。

 and they have things like that。See， the red ones which we don't want to hit light。

And the power ups you have， but see， that was a glitch， the balls were supposed to go back。

 this was just to hit the enemies and be destroyed。So we do have some debugging time ahead of us。Yes。

 the yellow blocks are the powerups and the red blocks are the non friendly powerups or the power downs。

 as we were calling them。So yeah， that kind of introduces the idea。

 but we also want to do like a bitnap here later on， right？

Then was dead and this is the other mechanic implementeder last time。

 which was the two balls and each ball only the sts。That kind of a block。

This is like really bad for now， but I think we can improve on that a little bit。Okay， yeah。

 this is pretty much the same thing， just level of variation。

This is what we do today the Pong and his facing invaders。But I want to play around that。Because。

This is really chaotic， this is not interesting at all。



![](img/a8dd2b7c2e064a5802e967ba681ac481_454.png)

But if we get the eters really small。If you manage to hit like destroy more blocks with one。



![](img/a8dd2b7c2e064a5802e967ba681ac481_456.png)

B， that could be cool。I think that's what I'm going to aim for like if we hit invader to see how we only destroy one block。

Maybe we should destroy more than one block at this point。



![](img/a8dd2b7c2e064a5802e967ba681ac481_458.png)

Yeah， we are only destroying one block。

![](img/a8dd2b7c2e064a5802e967ba681ac481_460.png)

Let's do that。Do ball block collision， we are only trying one block because when we do collide。嗯。

Let's see。We change the ball desire to pee。

![](img/a8dd2b7c2e064a5802e967ba681ac481_462.png)

Right， so what happens is。Let's say we are here。And we go like here and then we hit。

And then we're here to like。There。A lot of blocks like this。Whichever first block。

We say that were hit。That's going to change my position， my desired position to be like this。Well。这是。

Yeah。

![](img/a8dd2b7c2e064a5802e967ba681ac481_464.png)

So the other ones are not going to collide what we should do really。You have like a ball desired pe。

And they or maybe this is going to be too hacky， I'm thinking about having a ball desired peep。

And they borrow collision test。嗯，你啲。That's the collision of test。And then。We are going to test。

With a collision。TB。Right。Creation test group。Yeah。This I。です。

Some of them are going to be the desired piece，1PDP。Okay。对。包。Desirre pe。

 I don't think this is a heck anymore， change my mind about it。And a collision P。Collion test。

Same thing down here。And this is a heck that we're going to change next time it's not even working。

Properably。把，扣进去。Test。Yeah， we should probably not duplicate this guy like 100 times like we're doing。

We're going to clean this up， were not。Player desire to repeat， ball， desire to play， okay。

For each ball， we're going to set the desired P。And。Yeah。

 and then we're going to do like the ball collision。Tsp equals the ball。Desired be。

Going to remainder the ball。Okay， that looks good。We should probably change these to collision。Yeah。

I'm not going to do that for now， maybe like。啊。Do this。合ly。

But then in the do block well block collision test， you are going to set。明です。Oh yeah， more room。

The we're going to。Yeah， this guy would' you change the actual ball desired。Okay。

 so we are going to test against the collision test。But you're going to change。The ball is active。



![](img/a8dd2b7c2e064a5802e967ba681ac481_466.png)

Let's see。How much we broke as you would like the normal game mode first。Okay。

 this looks like it's working properly。do some crazy stuff。Yeah， let's see if you got the ball there。

Why does the ball accelerate okay， yeah， that's a cheat code that I added just so I can quickly you know destroy the wall sometimes。

So yeah， and that's just cheap code。Yeah， I think it's working nicely， though。Yeah， I don't know。

The ball there and see like。Yeah， that's accelerated a little bit。Yeah。

 now let's do the spacing major， that's the interesting one。系。嗯。嗯。



![](img/a8dd2b7c2e064a5802e967ba681ac481_468.png)

Yeah， I think that word。Sure in faders。Ss that put like to a more reasonable size。



![](img/a8dd2b7c2e064a5802e967ba681ac481_470.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_471.png)

嗯。Yeah， I don't know how to make this。Like more winnable。

Despite the problems with the comet and the other guys。Maybe we should work on that for a bit。

Or maybe she just could make them like really slow。Yeah， we could also do that。Yeah。

 but it's not interesting enough， meaning I can do like this shower of。Tarups， right？And。

I click contact the screen。I can't do that。嗯。When we would do the fatty stuff。Well。

Let'd say it's hard to give an estimate because。We're kind of doing gaming and designing things here and it's hard to estimate we're going to be satisfied with a gameplay。

 but after we do like this first pass。

![](img/a8dd2b7c2e064a5802e967ba681ac481_473.png)

Which we this basically bes， we're almost done， we're going to do Titrus。

 maybe we're going to do Titrus next。Space invadevars。

And they were going to fix a little bit of the bugs that that we created last stream with the power ups and things like that。

That should be like one more or two more most。These bugs， things like that。

And then we're going to do like a cleanup on the gameplay。And as small your patch。

 that should be another stream。And then I'm going to do audio。😡，Open GL， not sure about Open GL。

 Open G is not fun。And this game doesn't need it recursive chat， so maybe we'll do an open jail pass。

 but there'll be at the end， I'll be a polished pass。Because here in the engine improvements pass。

 we're going to do like audio， which is going to be like really cool。

And threading to make the audio multi threadreaded。

 that's pretty much the thing we need threading for。Go to rotator racks。

 maybe you're going to do bitmps， particles， maybe I nothing think really an live editor anymore。

We didn't like the space invadevader level Ed， right？We did。Who did this guy。

 that kind of like a lab editor， like a very simple level editor。And。

Then I'm going to go back in gameplay， this I'm not sure how much time we're going to spend。

This gameplay tough to you know， predict and then the polish pass。Yeah， see。

 we're going to do the profiler agresss chat。If the render is really bad。

 we're going to do an open gel pass， so you can pray for it to be a really bad renderer。

 but it's not going to be because the game is pretty simple。

 but we are going to do like rotated rectangles and we are going to do like more interesting stuff。



![](img/a8dd2b7c2e064a5802e967ba681ac481_475.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_476.png)

什没。呃。Yeah， let's keep changing the。

![](img/a8dd2b7c2e064a5802e967ba681ac481_478.png)

呃。好的。Movement target。Yeah， like this。Let's do instead of 10， let's do 2。5。

Maybe you can do like a little bit faster。As you like point。

What would you do with OpenGL that's the thing， man， I don't know。

 I mean I'm pretty happy in terms of laing what we have now， so I wouldn't do anything different。



![](img/a8dd2b7c2e064a5802e967ba681ac481_480.png)

Over meaning in terms of implementation or in terms of gameplay in terms of like。Eines are flight。

Because in terms of。In terms of。What we were willing to do。

 we don't want to do anything too fancy with this game， you know？Shaadeers。

We really shitters for the next game I'll do I'll promise you that after this game。

 we were going to do like a more robust engine that's going to use open GL。

And although it knew a gel stuff like you're going knew like。By knew。

 I mean not oh so going to do like vertex buffer for objects。

Proertectts are raised behind that and there were newti shaders。I mean， why would you use it。 Yeah。

 there's no point， Marfius， That's why I don't want to do this。 How are you readyy is pretty。

 It's a good project。 Thanks， man。 right now， if you go to the。



![](img/a8dd2b7c2e064a5802e967ba681ac481_482.png)

No， that's not my playlist， but if you go to YouTubebe。com s Dananzean。You can see。

The four episodes that we did so far。

![](img/a8dd2b7c2e064a5802e967ba681ac481_484.png)

And the very first one， we started out with no code， no library， no nothing。

 and then we do like the platform layer， which is input and the window and the loop。

And then we do the software layering， so we get a buffer of pixels。



![](img/a8dd2b7c2e064a5802e967ba681ac481_486.png)

And then we just run through them and I feel them。We have we created this like draw at in pixels。

Which literally goes through all the pixel you want to draw， you just fill them with a color。

That was it and then we did a way to change from pixels to world。And the other way around。

 so we have like a pixel independent rangeer。

![](img/a8dd2b7c2e064a5802e967ba681ac481_488.png)

So that was a fun thing to do。So if you have like a very small screen。It adapts itself。

To work perfectly and if you have like a very wide screen。

 it also works in a very tall screen as well。

![](img/a8dd2b7c2e064a5802e967ba681ac481_490.png)

You don't miss anything。W to play this game。And you can do like full screen。

 and this is like the debug build。And it's running pretty smoothly here on a 4K display。So yeah。

 when we run optimized， I don't think we want to do OpenG for this game， we don't want it I mean。

For the next one， I'm going to do it for sure， we're going to do like shaders and I'm going to do cool stuff。

That would be a cool learning exercise， but first of all， let's do the simple things。



![](img/a8dd2b7c2e064a5802e967ba681ac481_492.png)

I thought we were use Nelib， I forgot the name in Linux。



![](img/a8dd2b7c2e064a5802e967ba681ac481_494.png)

I'm not sure which librarian you mean。No library man。

 that was a pretty simple thing to write if you watch that episode。

 you see how quickly we wrote that。No need review。We already reviewed。

It's review of cleanup only needs to be。Yeah， see so it's like 120 lines for the whole renderer so far。

S open GL is's like the goodoey thing for butload scrub， it's not SDL。呃。Yeah。

 starter rendering is pretty cool， I really like it。😊。

You can really understand the whole thing in the whole。Rotated erect we're going to do。

That's in software rendering， so our software radar will have to be able to deal with rotd rectangles and that's going to be an interesting challenge because I think I want the ball to visually be sideways。



![](img/a8dd2b7c2e064a5802e967ba681ac481_496.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_497.png)

And curses。That's the library。I still don't know it， but I will take a look at it later on certain。



![](img/a8dd2b7c2e064a5802e967ba681ac481_499.png)

Okay， now I think it's easier and I think it can really decrease the。The frequency。

Bandom twice as's like one in every， I don't know。好理。I did a mind Superga and Chris says。

 that's pretty cool。

![](img/a8dd2b7c2e064a5802e967ba681ac481_501.png)

Mininecraper is an interesting design。It's a bit weird。

There was a lecture talking about how it was like a post modern game in the sense that it。

It was an activity about it didn't show what it was actually about， it was mostly， you know just。

I had to guess what it was about in terms of the minds， which is a pretty weird statement to say。

But yeah。And I was， thats weird。OkaySo now this is more manageable， I still think。

I still think it's going to be really hard。But it is getting better， maybe I should do like two。



![](img/a8dd2b7c2e064a5802e967ba681ac481_503.png)

two rows。

![](img/a8dd2b7c2e064a5802e967ba681ac481_505.png)

Your code looks so clean thanks and it's actually really， I think it's pretty messy at this point。

Because we are creating all these crazy gameplay ideas。And。Once we finish with this first pass。

 which we were almost done。We are going to do a little bit more cleanup。

 but I think you think it's clean。Because I don't have like a tons of files and classes in going back and forth。

The thing is what the code wants to do it does， that's the base idea and the if you want to do more compact stuff。

 like we are repeating a lot like a ball。Like this code that repeats a lot。

See if this is pretty much asking to become a function。

 they only to make a function out of it and then it becomes cleaner。That was my first bigger CPuch。

 I'll definitely take a look， man。On your。Or my super game。

I want to do more C stuff now C is really fun and I think C is the most fun language you have so far。

 I really like it。😊，There are a few drawbacks， I think the biggest one that I would love to see see was like default arguments。

That's the only thing that I really wish for。But besides that。



![](img/a8dd2b7c2e064a5802e967ba681ac481_507.png)

I really enjoy it， yeah。Okay， let's see。

![](img/a8dd2b7c2e064a5802e967ba681ac481_509.png)

But yeah， I was going to remove one row of the space invaders。Yeah， or maybe。We couldn't make a hack。



![](img/a8dd2b7c2e064a5802e967ba681ac481_511.png)

Not sure which one is going to be more interesting though。Yeah， maybe the he is when we we。

And we destroy a。Guyss， neighbors。Also die。So it would be easier to。Eat through these guys。嗯。

I am kind of inclined。To do that。Just to excrim with that。So we don't have to destroy like 300。

000 blocks to go through this level。But we also have the interesting invader guide。



![](img/a8dd2b7c2e064a5802e967ba681ac481_513.png)

I think I'm going to do that。In this case， I may actually increase a little bit of the size。

 not the movement。Havebs sense。Yeah， this guy。You got to do like。8。Yeah。

 so how am I supposed to do that， so each invader。It's going to have。A。APoer to its neighbors。

Or maybe an array of indices。嗯。Let me think。Yeah， I think I'm going to。

Because I could do like that a number of different ways。

 I could do like the collision thing without I just。Now， okay， let's do the simplest way first。

 then we can clean that up。So。We have blocks。Let's do just four neighbors for now， so we have。He。查。该。

😊，We have a bottom。A left and a right。Okay。😊，Okay， so whenever we create a block。

HLet's just do that in the。Well， let's do that of black block。Okay。

 so whenever I we respond to blocks。嗯。Okay， maybe that's going to be a little too hard coded。

Let's do like。Yeah。呃。Let's see check neighbors， not check neighbors like。嗯。And那。Or this block。

And let's see。Yeah， I think I'm going to cheat that and doing the col thing。 Okay。

 so the a neighbors。What I'm going to do。But the problem is。

I have to do that at the end because I may not have created all the guys。We'm going to do like。

Calculate all。Yeah。So in the end of start game。Let's do that calculateulate all neighbors。Yeah。

It's going to be a little bit messy， just because how the cold was clean。

 it' going to be a good weird。I have this block。I'm going to add。嗯。

Because the quickest way to do that just to do like a。N squared pass through all blocks。

I think I'm going to do that how many blocks we have like 124 blocks。然后就来 one million。Right。

1 million passes。In the beginning of the game mode。I know。We're going to do like。对。Yeah。

Let's do like。Test block。Okay， so。Or， in fact。If we find out a block with no life。

 we can actually just return。Right， because we had them in order， yeah。That's going to be better。

It's going to be a better and square problem。Okay， so for every block。

 I'm going to test their distance。I don't think we have a distance squared， so I'm going to add that。

If。Let's just say， length squared。From the block P minus the test block P O and also。If the。

Task block。Equals the block。T， right。So for now。I'm just going to。Do like four neighbors and I'm。

Yeah， I'm not going to make a distinction。啊个。Neighbors， we want to sleep。

 wish were all a great night。Okay， see Amorphphus， thanks for coming man， it's a lot of fun。呃。

I'm also wrapping up for now， maybe like 150 more minutes。And then Ill also go to sleep。Okay。嗯。撤消。

If the length squared is less than。The block。Half size。Times to。Squareed。If that's the case？

We are going。To add as an neighbor。Yeah， I'm also going to do a stupid thing to add name。

So we're going to do like。Luck。Goです。Equals black。Neighbors。Right。And'm going to do that by I。

I equal 0， and recount。Test block neighbors。啊。滚。Neighbors。Ile plus。We're going to do block。

You can just like block neighbors。My position is going to be task lock。Well， if。This guy。

It's not zero， right？Okay， so。That's a very stupid way to let do a sub too。

That's a very stupid way to calculate the neighbors。But。嗯。I don't know。I guess itll work for now。

 we don't have a half size。It's called lot have size， well should we just have。Do you like rock。

Size will be。Okay。Times the legal for。Yeah， I have to do it mold。Not convert。Yeah。

 that's because we don't have a length square， right， square， not the square one。嗯。If it's less than。

I actually want。I actually want like。I just did like the max。This is kind of hacky。

 but it's not going to be a perfect system and I don't need it to be a perfect system。

But just first to play around with that idea。It turns out to be a good idea and to change that。

You know。Then we implemented a nicer version of this。

Just because it's not nice to lose a lot of time doing。

Things that you don't want to do in the final game， so going to do like a sub。V2。啊ok。

Then I'm going to do。In line at 32 length squared。Thank， okay。And the length squared is just the。

This guy。This guy。Squad。Does this guy swear？Now。What we are going to do is， let's say blog。

Good destroy。When we destroy the block。We are going to go through all its neighbors。

And try to describe them。The block destroyed is not actually， yeah。

 let's do this hard codeed for now。For。Recount。Bck neighbors。Yes。Block neighbors， eye。Break。

Dan we're going to。就是说。Neighbors， I。We should also add the blood destroyed thing。Yeah。The neighbor。呃。

Acctor。😊，No。Their own life。There it gets from life， right？I equalical zero test forming condition。



![](img/a8dd2b7c2e064a5802e967ba681ac481_515.png)

Yeah。Okay， now that still happens。 We wrote a lot of crazy code。



![](img/a8dd2b7c2e064a5802e967ba681ac481_517.png)

Okay， so for some reason， that other block God said is a neighbor。

So we certainly have a problem with our length。

![](img/a8dd2b7c2e064a5802e967ba681ac481_519.png)

4，15。Okay， so。We are at the block，0，0 and the test block。Hes also the？But it's not。Us。

It it wass not us。Oh， they're relative P， yeah。Oh， that's really stupid。



![](img/a8dd2b7c2e064a5802e967ba681ac481_521.png)

Because it's kind of confusing， right？Yeah。Anyways。I'm not sure this is the best。

Long term solution for that。

![](img/a8dd2b7c2e064a5802e967ba681ac481_523.png)

For the system。Let it work for now， we're to be okay。Okay， that one got delete。But only that one。对。😊。

Not a success， but not a failure either。Yeah， let's see when we collide。So this guy。M-us 79。Yeah。

 this guys right I the side。Right。And the enemy。Add this guy the test lot。



![](img/a8dd2b7c2e064a5802e967ba681ac481_525.png)

Oh， we had him four times for some reason。看。Yes you should。



![](img/a8dd2b7c2e064a5802e967ba681ac481_527.png)

So nice time around。Yes次。Okay。I don't know why I didn't get the side neighbors。But yeah。

 this is correct。This is what we expected。But for some reason，'s only getting the top neighbors。Oh。

 because they are closer， I guess。Yeah， but we are getting the。



![](img/a8dd2b7c2e064a5802e967ba681ac481_529.png)

The maximum， right， no not。If the length squared。Is less I should do less than or equal to。



![](img/a8dd2b7c2e064a5802e967ba681ac481_531.png)

I think that's it。

![](img/a8dd2b7c2e064a5802e967ba681ac481_533.png)

No， that's not part。If less than or equal to the square of the maximum。Of the。Sizes。

 which should be the Dx。Should also do like plus one。



![](img/a8dd2b7c2e064a5802e967ba681ac481_535.png)

Just where like a。Oh yeah， the spacing。We have to add the spacing。



![](img/a8dd2b7c2e064a5802e967ba681ac481_537.png)

嗯。嗯。

![](img/a8dd2b7c2e064a5802e967ba681ac481_539.png)

Yeah。No， actually， I think we have a problem with this code。Like。

Let's go we're going through all the neighbors。If there is a neighbor。We just continue。

sTry another work。And we find a neighbor， we it to the test block。When we destroy the block？🤢。

Lets's see who are the neighbors？Okay， so。The neighbors are。One guy on。The other three are。



![](img/a8dd2b7c2e064a5802e967ba681ac481_541.png)

Are empty。So it is a problem with this code setting the neighbors。Let's do like good。



![](img/a8dd2b7c2e064a5802e967ba681ac481_543.png)

Just so we can narrow down the yard。Okay， so that worries。



![](img/a8dd2b7c2e064a5802e967ba681ac481_545.png)

Yeah。O。😊，So this is the problem， let's draw that， it usually helps。So。😊，We have two points。

Which is the block relative of P and test block relative of P。You are setting them or just this guy。

And getting the length squared。Let's say it's 10 to length and length square is 100。

We are getting the maximum size。Of the half block like。Let's say it's like this， they're like this。

Regarding're getting the maximum， which in this case should be the x oh because no， yeah。

 should be the x。Times two。Yeah， it should really add that safety margin。Before we square。

So let's do like。

![](img/a8dd2b7c2e064a5802e967ba681ac481_547.png)

Just for reference， let me see what the spacing is。



![](img/a8dd2b7c2e064a5802e967ba681ac481_549.png)

Yeah， I'm not sure I like this it's kind of becoming really hacky。But。I don't know。

 it's just the first version， just for us to check out so the speciess 01。Yeah。Spac is  point1。So 0。

5 should be more than enough。Yeah， let me debug that one more time。



![](img/a8dd2b7c2e064a5802e967ba681ac481_551.png)

啊。T。Okay， so they' out of P。So yeah， we should really break those variables down。 Yeah。

 let's do like。

![](img/a8dd2b7c2e064a5802e967ba681ac481_553.png)

て。Let's do La。And the other one we can do like。さ？

![](img/a8dd2b7c2e064a5802e967ba681ac481_555.png)

Yeah。Okay， so the diff is minus 40。4。4。What is the size， the size is for， right？Yeah。嗯。Yeah。

 anyways so。The sizeize is four， which is the largest one。We're doing four times two， which is eight。

8。5 times 8。5。あ。72。So you the length squared less than 72 or it's away less than 72， right？嗯。Yeah。

Let's put like another。So apparently we found another neighbor。Wse length is 19。Yeah。

 they're only finding one neighbor。It would be easier if we could， like， see。Oh。

 I think they are in order。Okay。Okay， so the block。P is minus， let's say， 44 and2 oh， it's relative。

This guy is minus 44 and6。 so yeah， this one is second on top of each other if I do block。Plus one。

We should have the one that's。You actually decide it。Okay， we do。So。If we subtract。Their positions。

Should have like， a。Should have。A minus。嗯。444 plus 35 cases。Minus9。-9。嗯。Yeah。

 the length of this guy is going to be squared is going to be。Kind of like this。81。Okay， so really。

 it isn't。Okay， so yeah， the math is right， but this guy's wrong。Why。This was 35。



![](img/a8dd2b7c2e064a5802e967ba681ac481_557.png)

I can just check out the black black code。We had x times。Yeah， we do add a lot of spacing。

Two plus the space。Times 2。Oh yeah。O。It the space relative to the block size。That's the problem。

So if the spa is 01。Yeah。This is actually， let's say， point。



![](img/a8dd2b7c2e064a5802e967ba681ac481_559.png)

25 times this guy。Yeah。Okay， nothing like understanding your own code， right？

Now there's no neighbors。Didn't we make it？Eageger。😊。



![](img/a8dd2b7c2e064a5802e967ba681ac481_561.png)

Oh。Sorry about that。😔。

![](img/a8dd2b7c2e064a5802e967ba681ac481_563.png)

Okay。Okay。

![](img/a8dd2b7c2e064a5802e967ba681ac481_565.png)

Okay。Now let's do。Times 2。25。

![](img/a8dd2b7c2e064a5802e967ba681ac481_567.png)

And I think we are correct man at this point， it shouldt be like 2。2， but 0。

5 is just like a error margin。And you know what I think we are also。



![](img/a8dd2b7c2e064a5802e967ba681ac481_569.png)

Maybe you should like individually for the x and the Y。Or maybe we just don't care like we do like2。

2。

![](img/a8dd2b7c2e064a5802e967ba681ac481_571.png)

I see if22 guess the other one。But we're not even going to use on this stage。That's oh。

 because we already。Yeah， well， who cares what I'm interested is on this guy， right？Yeah。です。Yeah。

 see。So this is cool， I think。Yeah。Yeah， okay。嗯。😊，And maybe the ball is getting too fast。Yeah。

 the boss a bit too fast。You see， we couldn't even see the difference。 We did like。

We didn't actually do a full million tests， but we did a lot of。Yeah。

 now it's a little bit more manageable。I'm not sure this is like for winnable yet， though。Actually。

 we don't lose when they get close to us， but we don't win either。You have to make it。

 you have to make it lose like。Amen。おい nextゃった。Hes happy。Yeah。

 I think we're going to decrease the ball speed for a bit。

Maybe decrease the frequency for which they walk for a bit with were like 0。8， I think。



![](img/a8dd2b7c2e064a5802e967ba681ac481_573.png)

Let's do 1。25。And the invaders。Rety later。Here let's change。Or the ball multiplier。That's due light。

2。You do more than 400 lines of code for this well that's a nice question I don't know how many lines of code we did。

But let's find out I have this program that counts the lines of code。

Let's count the light of code for this game， I think it's more than 400 for sure。Yeah。

 this file alone is already more than 400。This program in this computer for some reason is really。

 really slow。Okay， so we have almost 1，000 lines of code。

And if we do include blank lines and comments， we have over1 thousand0 lines of code。We have。

We have almost 1，400 lines of code。And we did that。



![](img/a8dd2b7c2e064a5802e967ba681ac481_575.png)

Let's see， well， it not it's not that impressive， but it's pretty pretty cool， I think。

 while live is stream， that may be impressive。Okay。

 so we did that in these four episodes plus this one。So it had like two， six。8。Let's say，8。11。12。

Plus three， 15 hours。

![](img/a8dd2b7c2e064a5802e967ba681ac481_577.png)

So it's an average of a well considering bank lines in comments。

 it's a little bit less than 100 lines。Per。Hour。Which is decent enough。Considering， you know。

 this is a live stream free time site project。

![](img/a8dd2b7c2e064a5802e967ba681ac481_579.png)

For how long we do it， you can go on YouTube， let me give it a link。

This link I'm throwing that on the chat。And you can watch the whole process。

 it's been like only 15 hours counting with this live stream and you saw。

 you can see the whole process， everything the， the first line of code。

 we tap that on first episode and then we did that for the other episodes as well so you can see the whole thing。

From scratch， so no library is allowed， everything is in the game we wrote。



![](img/a8dd2b7c2e064a5802e967ba681ac481_581.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_582.png)

And。I recorded it。So I think that's a little bit more manageable。

 I think we're going to end for today after we。

![](img/a8dd2b7c2e064a5802e967ba681ac481_584.png)

ya。Yeah I think that's kind of nice， but I do have to make it so that the other game the other levels。

Don't。Said the neighbors？So I think I'm going to individually do that inside that switch。So yeah。

Maybe the bows little too slow now for my taste。And this makes me well a lot。

You wantant to be a programmer， all that work for a simple game。I don't know， man。啊。

15 hours is not a lot of work， to be honest。So， 15 hours。To get like。From scratch。

 this breakout clone， this other iteration with power ups and power downs， wow。

 and now breaking the wall is pretty cool， right？This other weird mechanic that we did the other time。

And at the other level with the punk thing。Yeah， not sure what to say， 15 hourss not a lot of work。呃。



![](img/a8dd2b7c2e064a5802e967ba681ac481_586.png)

Well， if you do want to count the other game that I released。The big one I did。



![](img/a8dd2b7c2e064a5802e967ba681ac481_588.png)

You've been talking a lot about this today， right， this is the big one I did， right。

That's not such a simple game。It's like 3D and lots of animations and lots of levels and particles。

Enemies and AI and pet farming。Upgrade the character， you know， all sorts of stuff。

This game was three and a half years。So if you actually do the math。This game。

s you get a lot more bang for your buck if your buck is time。

Right for 15 hours got that and for three and a half years about that。

 I mean I'm kind of kidding right， but I do got the point in making games and programming a lot of work。



![](img/a8dd2b7c2e064a5802e967ba681ac481_590.png)

But。By a lot of work in three and a half years， I don't mean 15 hours。



![](img/a8dd2b7c2e064a5802e967ba681ac481_592.png)

That's not too much。Yeah， three years， it was a long time。



![](img/a8dd2b7c2e064a5802e967ba681ac481_594.png)

But that project， let me send you the link。That project。Wass pretty cool。呃。

I think it was definitely worth it。

![](img/a8dd2b7c2e064a5802e967ba681ac481_596.png)

The result， okay， so I have to do it quickly just to finish action because I'm kind of getting tired。

What I want to do is let me just see if there's any noticeable performance here。



![](img/a8dd2b7c2e064a5802e967ba681ac481_598.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_599.png)

There isn't。Yeah， it's like perfect。

![](img/a8dd2b7c2e064a5802e967ba681ac481_601.png)

Okay。This makes me appreciate games way more， that's nice to hear。Yeah。😊，嗯。Okay， what I have to do。

 okay， to calculate neighbors， calculate all neighbors also only going to do that in the invaders。



![](img/a8dd2b7c2e064a5802e967ba681ac481_603.png)

So this。

![](img/a8dd2b7c2e064a5802e967ba681ac481_605.png)

This game。There's no neighbor in de， right？But this game there should be， yeah。We had。



![](img/a8dd2b7c2e064a5802e967ba681ac481_607.png)

Yeah， I'm going to add the feedback a little bit， so we did like。You can July like 0。0。欢迎。嗯。No。

 I actually wasn't the create。Maybe， yes。0。2， let's do 0。 I don't remember how much they'll ask。



![](img/a8dd2b7c2e064a5802e967ba681ac481_609.png)

D of 0。5。As is as your question。

![](img/a8dd2b7c2e064a5802e967ba681ac481_611.png)

Okay， let's try the game。Yeah， I think that's。嗯。I should also implement the life system。

That's going to be pretty quick and it's going to change。Gameplay a lot。

I very new to programming only knowing bit of HTML and Python。Making games is as a fun way to learn。

So maybe she did like small games with Python。And if want to do like JavaScript for web things。

That could be a fun too。Yeah， because games theyre fun to make and fun to play。

 so you get to do them both pretty much at the same time。Okay。Yeah。Yeah， it's a little bit better。

just see if I can win this。In terms of a。II'm going to be invincible。

 which is what I want to try is see if I can actually kill them all in a reasonable amount of time。

Not exactly thinking about。If it's going to be hard to lose or not。For this guy， particularly。

Let' see。Yes， you can't waste much time here。Maybe the comet should be activated。Yeah， I'm not sure。

Okay。Yeah， things's going to be really hard in the end。



![](img/a8dd2b7c2e064a5802e967ba681ac481_613.png)

Did I win？

![](img/a8dd2b7c2e064a5802e967ba681ac481_615.png)

嗯。So we have buds。笑了。But at the chances we are doing space space。呃。Make space invades。Loose。

When they。the player。And check。Space invaders。管デシ？Are 2D games easier to make than 3D for scripting？

Well， definitely。😡，If you're using no libraries like this。

That becomes particularly more complicated 3D games。If you do like an engine like unity or unreal。

It is harder to make 3D games than 2D。Programming rise right not talking about the art the art is way more difficult。

 but programming it is a a little bit more difficult because of the math you have to do。

But it's not like。As difficult as it is when you're not using an engine。When you're not。

 the math really piles up。When you are， mostly it gameplay math logic， so it's not that much harder。

 but it is harder yet。But depending on the result。It's worth it， yeah。

So I think we'm going to check the victory condition， then we like this。

I think I'm want to tackle these guys today。

![](img/a8dd2b7c2e064a5802e967ba681ac481_617.png)

Check the space energy condition。Yeah， for some reason。



![](img/a8dd2b7c2e064a5802e967ba681ac481_619.png)

Ficctory call that victory， now we don't。嗯， when。Caine conditionition。Take3。嗯。Yeah， if I destroy， oh。

 okay。I see the problem。I have to see if I have a neighbor。



![](img/a8dd2b7c2e064a5802e967ba681ac481_621.png)

And that neighbor is alive。Because okay， that was easy because like， if I have like this。

And I destroyed this guy。It's going to destroy south in counter point。

 destroys neighbor in counter point。

![](img/a8dd2b7c2e064a5802e967ba681ac481_623.png)

And then you I sort， this guy is going to destroy itself and its neighbor in a kind of point。

We have a living neighbor。That's the strium。And then contemplatepoint。Okay。I think that solved it。

Loose， let's do the loose condition as well。しかに。Easy， so we do simulate level。And if we go down。

Which test like if。Evaers enemy PY。Is less than。I don't know， let's see what。

I might have to test that。

![](img/a8dd2b7c2e064a5802e967ba681ac481_625.png)

Yeah。And put a break on here 477。

![](img/a8dd2b7c2e064a5802e967ba681ac481_627.png)

That's to close the sky。4，77。Okay let's still。Okay。Yeah。

 I think to release the break point for a while。And then when I think it's time。

 I add the breakpoint back here。Yeah know， this is probably already a last condition。Yeah。This guy。

When the player。I see。Yeah， when it's less than minus20。



![](img/a8dd2b7c2e064a5802e967ba681ac481_629.png)

29。Sposed。If this guy is less than  minus29。We are going to how's the game mode。

Be more than game over。Start game。I did a start game。A game current。Start game definition。

We don't have that yet。Oh。Let's just throw that。嗯。Yeah simulate level。そうじ。

She might block for a laugh。そ。就是な。Okay， let's see where we are at if we have a gaming over condition。



![](img/a8dd2b7c2e064a5802e967ba681ac481_631.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_632.png)

And。So space evas。Let's play。Okay。Sly fix that crazy ball bug。

But we're not ready to play at that speed so。Okay， so in this case I'm going to lose， I suppose。Yeah。

 it's going to be a pretty hard game mode， maybe we can oh or I not actually。Cause I don't okay。



![](img/a8dd2b7c2e064a5802e967ba681ac481_634.png)

H I can't test this。It cant test。Just the。The group position。

 I have to see if one guy actually collide with me， so a， okay。So。Whenever we do this guy。

 I'm going to do like invaders。Do Evar player col test。Okay， that's nice I。O。Equals true。Okay。

 so whenever we change the Y position。I'm going to check out here。In the invaders。

If we should do a player recognition test stuff。And then for every block， let's see for block。

This guy。We simulate each block for the level。Okay， then me check out the ball， that to do here。

Let's do， oh， we already have simulate lifeities to simulate。Block for labor。

In case you are invaders。'm going to check out。If we are。If the level state invaders dot。

Do we invade take Asian test？If that's the case。We're going to set that false because we oh。

 we can't accept that false。You can set it。s that at the end。嗯。Yeah。

 I' going to have to think about that， but the point is here。We're going to do is a test， if the。L。P。

 and this the black be dot Y。If that is less than the player dot。Play your pe up black。

Then it's game over， so simulate game。哦，那行。Starting。Start level。Start getting。

Really should be start la。But okay， now we have to remove the Du play equation test。

Whenever we simulate game， I think simulate level I mean。So， it every frame。

I am going to set that to false。 That's kind of redundant。But that's okay， I think。And said。

 that's false。I said that to true， let's see simulate。Lve。

I said thats true here whenever we simulate the block for the level and going to test that that sounds good。

 what do you guys think？

![](img/a8dd2b7c2e064a5802e967ba681ac481_636.png)

Let's see。Let's see if we're going to lose。Okay。It's pretty close now。

I think it's going to be a pretty interesting game mode。I don't think you going to lose this round。

 let's see。Actually， we should have。That's if we to lose next round。 Yeah， we did。 Okay。

 so this is kind of right except。

![](img/a8dd2b7c2e064a5802e967ba681ac481_638.png)

I'mSee you lateclock。Except I'm going to do。If the block。PY。Minus the block。Have size Y。

 It's less than the block。PY， the player PY。Plus。The player have size one， that looks better。

 let's test that。

![](img/a8dd2b7c2e064a5802e967ba681ac481_640.png)

Okay， so in this case， if you manage to destroy this first row here， you get more time。

 which is the point of spacing invade right so I think that comes across nicely。In this game mode。

 I think。It'll be really cool， really， yeah。See， we may actually win this round。

 we're not actually playing， but。Yeah， you know what， I don't think I want to win。I want to lose。

Maybe actually when just because I want to lose。也必须。嗯。Hi man， how are you doing？呃。

Not sure what happened there， you know what I'm going to do， I'm going to do like strong blocks。



![](img/a8dd2b7c2e064a5802e967ba681ac481_642.png)

Whenever we start。Game。Whenever we start。Evaders。I'm going to make it like a ridiculous amount。



![](img/a8dd2b7c2e064a5802e967ba681ac481_644.png)

Just a test。So yeah， we can't destroy invaders。We want to see if we are losing on the correct position and I think。

 yeah， it's this guy minus it's half size if it's less than the player。Pst test size。Why。

So lose right about now。那's。嗯。Yeah， position， the position is a bit weird。

We should go a little bit further to the sides。Yeah， I suppose that's the problem。



![](img/a8dd2b7c2e064a5802e967ba681ac481_646.png)

I think that's why it felt weird the first time。嗯。So in the Culate。来不。Invadderrs。

Go to hard to code a little bit more space with the guys。Maybe 20。



![](img/a8dd2b7c2e064a5802e967ba681ac481_648.png)

Lets seeOh， just check out when we start， right because we start pretty perfect。



![](img/a8dd2b7c2e064a5802e967ba681ac481_650.png)

Let's see。Ennemy。T。TheX equals 2。-25。So， that's it。And finding some old school stuff。



![](img/a8dd2b7c2e064a5802e967ba681ac481_652.png)

Yeah， it's fun。Both。

![](img/a8dd2b7c2e064a5802e967ba681ac481_654.png)

To learn how the guys did it or。And have some fun to。

Are you using a graphics library like GTK or are you printing it yeah we're doing everything from scratch so no library okay so that was a weird but no libraries If you watch the first live stream here on YouTube you can follow the link in the chat。



![](img/a8dd2b7c2e064a5802e967ba681ac481_656.png)

The very first one we are on the fifth this is the first fifth flag stream。

 so the first one we did the platform layer and our software arranger。



![](img/a8dd2b7c2e064a5802e967ba681ac481_658.png)

So we literally。Go pixel by pixel。And feel its color。So that's what we did in the first day。

 that was pretty easy and it's pretty cool and it runs pretty well too， I mean。

 if I run the game at 4K。

![](img/a8dd2b7c2e064a5802e967ba681ac481_660.png)

It's still works nicely， okay， now it's not 100% nicely。



![](img/a8dd2b7c2e064a5802e967ba681ac481_662.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_663.png)

Okay， this is perfect。Yeah， I mean there's a too much overdraw here， but this one runs smoothly。

 yeah。

![](img/a8dd2b7c2e064a5802e967ba681ac481_665.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_666.png)

But this is a deepbug deal。So if you want to check out how you did that。

 you can watch the video and you can also download the source code。

 source codes available on HIO for free。

![](img/a8dd2b7c2e064a5802e967ba681ac481_668.png)

We can download like the first day where we write the renderer or the last day。

 and after we finished today day， we're going to post that here as well。



![](img/a8dd2b7c2e064a5802e967ba681ac481_670.png)

So。Let's just have the， oh， now it worked for some reason that I forget to compile。



![](img/a8dd2b7c2e064a5802e967ba681ac481_672.png)

啊。😮，Didn't like how that turned out。

![](img/a8dd2b7c2e064a5802e967ba681ac481_674.png)

And it's not centered。嗯。😊，Oh， I'm trying， Oh， that was kind of stupid。

 I was pressing the wrong button。Okay。So yeah， 25 is a bit too much。



![](img/a8dd2b7c2e064a5802e967ba681ac481_676.png)

Maybe it' is going to be like 22 on the right。That's still like。

2 grade and 22 and this one's going to be light。I do some sea cold on my raspberry pie。



![](img/a8dd2b7c2e064a5802e967ba681ac481_678.png)

Aow that's pretty cool I haven't， I haven't done that before programming a Raspberry high。

 I really want to do that at some point。It's pretty interesting how you can go all the way down to the hardware respect。

And。Do so for that Okay so。So 22 was way too much。

![](img/a8dd2b7c2e064a5802e967ba681ac481_680.png)

Mイナ。Yeah， it's weird because this one wasn't that much， but this one was weird。



![](img/a8dd2b7c2e064a5802e967ba681ac481_682.png)

Yeah， press the wrong button， that's fine not。Up and down。Let's see， should do one more almost。

You know a little bit more。

![](img/a8dd2b7c2e064a5802e967ba681ac481_684.png)

Yeah， and a little bit even more on the other of this guy we going to do like this。And this one。



![](img/a8dd2b7c2e064a5802e967ba681ac481_686.png)

Should do like 33。

![](img/a8dd2b7c2e064a5802e967ba681ac481_688.png)

一次。Well， they didn't change anything that 0。5。

![](img/a8dd2b7c2e064a5802e967ba681ac481_690.png)

Yeah， this one's perfect now。This one is perfect。 This one didn't change much。 so we were 25。

And I thought。

![](img/a8dd2b7c2e064a5802e967ba681ac481_692.png)

I thought。That was too much。I think I thought it was too much。Yeah， it is too much。



![](img/a8dd2b7c2e064a5802e967ba681ac481_694.png)

Well。Let's do it for now。I like GC compiler， but we're doing stuff on Linux a bit different。

And Windows applications， yeah。I don't know。 I don't like Windows at all。 I really don't。

 Windows is a。

![](img/a8dd2b7c2e064a5802e967ba681ac481_696.png)

I have so many bad stories of using Windows。

![](img/a8dd2b7c2e064a5802e967ba681ac481_698.png)

But it is where most people play games， right so you have to at least know decently。Windows and。

And it's also where most games run better。So that's why I use Windows。

 but I don't really like it at all，Okay， so。

![](img/a8dd2b7c2e064a5802e967ba681ac481_700.png)

We're fixed。The low condition and the wind condition， I think。Oh， let me just remove this strong guy。

A strong。That's strong hack we did。

![](img/a8dd2b7c2e064a5802e967ba681ac481_702.png)

Okay， so let's just play for a while。

![](img/a8dd2b7c2e064a5802e967ba681ac481_704.png)

And see if we manage to get in America， so the point is we have to destroy these early guys here。

Even though it's easier to destroy the other guys like this， yeah see。F with the bug。

 we're going to fix that next time。So。Ex probably change the behavior of that。To be more predictable。

Okay。Okay。

![](img/a8dd2b7c2e064a5802e967ba681ac481_706.png)

I think that's going to be manageable， you know what before testing。

 I'm going to add the final thing we're going to do today。

 which is the three life for the player so player。Theyre P， theyre D P， player half size player。Li。

ok。😊，So whenever we start the game， start game。Going to set player life。2ose，3。Okay。But。

We are setting we should do like this。确认到。Or lose life。This guy。M minus。If play your life。0。start。

Current lab， let's just see where it's called， right？嗯。Yeah。I have to call that。It's kind sex。

Start game。Oh， we're not getting that compiler error。That sucks。Start game。

 I let's stick with you too。It's forcefulpi error。Yeah。Okay， so simulate block。If yeah。

 we're going to do a， this one is lose life， most of them going are going to be lose life。

Simulate game， if or not， this one start game。If。vol is the end of the arena， like。Insec those life。

Advanced level， Adv level is a target。Yeah， this one start game， this one is start game。Yeah。😊。

Think pretty good to go。Start getting。Yeah， okay。Now， I think we' we'm going to draw。



![](img/a8dd2b7c2e064a5802e967ba681ac481_708.png)

Viual feedback。That we have more lives。

![](img/a8dd2b7c2e064a5802e967ba681ac481_710.png)

LikeIn the tiny corner of the screen， let's do like。包。嗯，我批会有辆这车。Dawect， okay。

So for every life the player has， for every extra language， it's going to be light。Play your life。Or。

I equals player life。死少。Its last their life。Going to draw。I'm going to draw。Let's see。Arena。

 half size X。Mines are going to have size x。Plus。はい。0in plus one。And we're going to do。inus oh。

 this is plus 3 and a half size y。-2。I'mNot sure it's a good size， that's just ball。

Yeah I'm going to hardcode the ball size， I think it's two by2 no one by one。



![](img/a8dd2b7c2e064a5802e967ba681ac481_712.png)

好气。Yeah。

![](img/a8dd2b7c2e064a5802e967ba681ac481_714.png)

We should do like。Plus。4。And minus。And this is going to do like plus I。



![](img/a8dd2b7c2e064a5802e967ba681ac481_716.png)

不行。

![](img/a8dd2b7c2e064a5802e967ba681ac481_718.png)

Okay， so it's going be plus I。Times。2。5。And plus 3。



![](img/a8dd2b7c2e064a5802e967ba681ac481_720.png)

Okay， that looks nice， so we lose a life。Oh that。Loose life。Player livess 3。 Now is2。Still2， right。

Oh， because。

![](img/a8dd2b7c2e064a5802e967ba681ac481_722.png)

Yeah， we do have to reset some stuff。Yeah哼。啊。Okay。So not the level， not the level state。

I am going to zero the balls， the power blocks， but not the blocks。And also the ball。

 so now should be a good time。啊。To do what be。We said we're going to do。And clean up this ball thing。

L life。Okay。Yeah呀。😊，And we can also return at this point。は就年。So zero the balls， zero the block size。

We're going to do like， a internal。Vvoid setup。P it in knit ball。Re see a ball。Yeah。Yeah。

 I wish also set the first button。True。This is going to be per bowl， I think， later on。knit ball。

Walls。Sa飞。一儿。And whatever we have falls zero dot。Ballarrow。And I think， well， let me see start game。

Let me see how different this guy is。50。Yeah， the base speed is different。

And the flags are different。So we're going to keep the base speed like this。😔，Flaex。Okay。现在就不好。

啊 in the包。Balls plus one。Very cascaded but efficient。嗯。Do you mean all the switch statements。

 cascaded， that's what you mean？Yeah， we could do like differently。But I kind of like it the way。

The way it's structured in terms of specifically。Because we search for like。

Things like start game or a simulate ball。Or a simulate level。And then we do， you know， I mean。

 if you had like a thousand levels， maybe that wasn't the best call。But well。So far， so good， and。



![](img/a8dd2b7c2e064a5802e967ba681ac481_724.png)

Yeah。I don't know if you find that confusing， I think I like it a lot so。No that is true。



![](img/a8dd2b7c2e064a5802e967ba681ac481_726.png)

0ro the balls。 Yeah， let's just see if you have anything else。The lose life。

That we should use in the EIS RK， so advanced level zero， the guys in it ball。So the player P arena。

 Isibility。Yeah， I'm also going to do that when you do like reset startups reset。However。

I also have to reset the blocks destroyed。So。Tternal avoid was。PsOh， I do like powered blocks。

I should do reset power。Reset power。We set power and we also have to do the no blocks this short， No。

 we don't have to do that。

![](img/a8dd2b7c2e064a5802e967ba681ac481_728.png)

Okay， we're pretty much good to go。I think。Let's see。Lose a life。We set all these guys。

 reset the power。其次。Y。

![](img/a8dd2b7c2e064a5802e967ba681ac481_730.png)

Looks good， that's your life。Oh I think I have removed as a guy from day。😊，Yeah。Keep in both。

First of all， it true。感是。Okay， I think I'm also going to。Nick these guys let bit。呃。

A little bit taller as well。Like 2。5。And late， yeah， dude I'm tired。

 but I really wanted to finish this thing today this life system。



![](img/a8dd2b7c2e064a5802e967ba681ac481_732.png)

Pretty much done and I'm going to finish the stream， I'm also tired。Did a lot of stuff today， so one。

Two perfect。It's really late here what time is it there， Timmy？呃。Here in Brazil。

 it's pretty much 11 pm， so it's late but not too late。where do you live？

It's like the West Coast in the United States？Or maybe Europe。Netherland。Wow。😮，Yeah。

 so I can't complain about getting late。So see this strategy pretty much sucks at this point in this space it because we have to eliminate these early guys。

 see， yeah。But with a life system。It is getting more interesting。

So I think we almost have an okay game， except for the bugs， right Germany。So yeah。

 I thought at this time I wouldn't get much people from Europe watching。But I guess I was wrong。

 you guys like to stay late。To you know。There some game programming and learn a few things。

And had some fun， too experimenting。 We did a lot today。 Today was great。 We did like Pg。😊。

Pong were like really fun。Yeah。

![](img/a8dd2b7c2e064a5802e967ba681ac481_734.png)

We shouldn't make it that smaller， I think we'm going to do that because it's too easy。螃街。This guy。

 create。Do we pass the size？In a black block。Black， block。

Number offset set offset set half size we do do the half size x only。

So I'm going to do the half size wall as well， so you're going to do。The2。Bock have size。

So it's going to be block half size dot X。And。来。And you think from a set block to the block cap size。

And then two going be the default。 See， this is where default parameters would。

Would be nice because we don't want to change all those calls， I mean， why？Why do that？

That kind of sucks。And this happens a lot in this kind of programming that I like to do just kind of a。

This program kind of a lot of random stuff and then compress it later on。

 so things change a lot I think this。Here， so。2， four， two。Yeah， for the next game。

Then we're going to do like open GL and more advanced shader stuff。I'm pretty sure I'm going to。

USD plus plus。But but a very limited。C plus plus。I'd say features， I should say。But， yeah。

Is it more complicated we get？The nicer those features are。But at this point， I like using C。一。Yes。

 it's faster。It's cleaner to read too。I think that's really important。あま。Okay。Do that。え。给胖没有。

This two。It's going to be。I'd say one， one， and then we double these guys it's going it's 16 by four。



![](img/a8dd2b7c2e064a5802e967ba681ac481_736.png)

I think now it's going to be a lot more interesting， our pond guide。自。

And this size was a bit too much， I think， oh its going to be harder to。Yeah， so。Not like that small。

But definitely smaller。And every one of them drops a。



![](img/a8dd2b7c2e064a5802e967ba681ac481_738.png)

They pray hazard too， so I'm going to yeah。

![](img/a8dd2b7c2e064a5802e967ba681ac481_740.png)

I think you're going to be a little bit larger like one and a half。Then I'm going to do。

 it was eight by two。那3。And 12。And I was going to do。Drop something。And I'm going to do。Oh yeah。

 not every guy's going to drop and not's going to be， yeah because now we have。

To have like the random stuff have random choice。So let's say every three guys。

We are going to create a power block。And the power block， let's see， is going to be power。Let's see。

It's going to do the power up last。 It's going to be a random。In to arrange。Power up last plus one。

Until the power。Count。-1。The problem is we haven't actually programmed all of those guys。



![](img/a8dd2b7c2e064a5802e967ba681ac481_742.png)

So some of them are going to do nothing。Point。Unfortunately okay。

 this size is pretty nice at this resolution we are at 18 128 by 720。Okay。ok。Yeah。

 having life is a nice way to make the game not extremely。不不冇。Yes see， I think I did nothing。Yes。

 we'm going to drop here inside。We should do like as courses than later that。

The more you get like the number of blocks you destroyed times the life you have。

 so the more blocks are destroyed with full life， you're going to get more points for that。

That could be cool。Let's see if you can win。We should do like here。

A better system for these guys later on， but for now。Yeah， okay。Yeah， I think it's pretty winable。

Yes。rop Okay， Oh yeah。That's it。

![](img/a8dd2b7c2e064a5802e967ba681ac481_744.png)

Okay， so that's just we do the you do and then we're going to close everything。呃。Yeah。

 so now it's probably like four o'clock exactly in the morning there in the Netherlands。

What time did in Germany is the same four o'clock in Germany？诶。So review if we didn't forget。Yeah。

 that's what we're going to have to do， we' have to finish this guy， finish power downs。

But I then play around the two ball level。Bugs might happen when the collision。These two buds。Yeah。

 I think we're going to have to do like the comment first。Comments stopped in the middle of the run。

And they bug the leader three ball behavior life a block life。Yeah， so this looking good。

 Maybe you have like。Yeah， at the same time zone， yeah。

So maybe you have like two more streams of gameplay stuff。Before we go back to the engine。

So this is the fifth one， I suppose yeah。So by maybe seven or eight eight or nine。

 we're going to do audio and threading， maybe not in the same one。

 but we're going to start working on that audio threading， rotator X。Yeah。

 I'm going to do a bit nice probably and particles particles are going to be pretty cool。

 who doesn't like particles， right？And yeah， but next time I'm going to do some gameplay debugging。



![](img/a8dd2b7c2e064a5802e967ba681ac481_746.png)

And a polish。Because I think in terms of content。This is okay for the first gameplay pass。

Maybe this one， I'm going to have to play around with this one a bit and this one。

But this one is great。This is the this is the actual the actual idea， right。

 and this one is also great。 This one is this one is was funny， yeah。😊。

We should also make them drop like random。呃。Random。Hazard power downs。Yeah。

 I should do that later on。

![](img/a8dd2b7c2e064a5802e967ba681ac481_748.png)

And also the score system。So yeah， we should probably do like the a print just the first thing。

 it's going to be pretty easy， going to be a hacky print for now， but a print nonetheless。

Add a print number。And。Then I could do Ed score。Based on it's going to be like。

For every destroyed block。Score plus equals life， something like that。

And then we can focus on the bugs， Okay， does that sound good？



![](img/a8dd2b7c2e064a5802e967ba681ac481_750.png)

If you want to download the source code every road today， you can go to the gamess HIO page。



![](img/a8dd2b7c2e064a5802e967ba681ac481_752.png)

And just click at the download now button。You're relevant to give me a tip if you want。

 but if you just want to download， it's okay， take me to the downloads。

 and then you can download the executable and the source code for each episode。



![](img/a8dd2b7c2e064a5802e967ba681ac481_754.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_755.png)

And in case you want to see how we built this game from scratch， using no libraries。



![](img/a8dd2b7c2e064a5802e967ba681ac481_757.png)

We can go to the YouTube page where I'm starting all the episodes。

So from the very first line of code that we wrote。

![](img/a8dd2b7c2e064a5802e967ba681ac481_759.png)

All the way through the gameplay stuff that we're doing now。Its cool stuff。

Everything is documented there and you can watch。And play around with it by download the source code understanding。

 and if you have any questions， be sure to drop them in the comments or the chat， wherever you feel。

More comfortable than I'm going to try to answer them and that's it。 I'll see you guys next time。

 Thank you for watching。 That was fun yeah。😊。

![](img/a8dd2b7c2e064a5802e967ba681ac481_761.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_762.png)

Okay。