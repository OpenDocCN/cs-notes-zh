# 【从零开始用C语言制作游戏】 p02 Making a game in C from scratch! Ep 02： -Gameplay, Epic Collision F -BV18i421a7DD_p2-

Hello， everyone。 Welcome to my second live stream。😊，If you watched yesterday's live stream。

 we started creating a game in C from scratch。 And I think it was great。 You know。

 the reception was really cool。 I posted on YouTube。 It's been less than a day and already， you know。

 we've seen a lot of。😊。

![](img/2c5915bbf2791187d13c00d769bdde9e_1.png)

A lot of people like over 800 views in less than a day that's a lot。 And yeah。

 if you go to my YouTube page， YouTubebe。com slashd Z damn。

You'll be able to see the previous episodes in case you haven't seen it。



![](img/2c5915bbf2791187d13c00d769bdde9e_3.png)

But I'm going to recap in the beginning of this live stream。Okay。

 so I created a HIO page for the game。Where you can check out the source code for yesterday。

 so if you want to follow along at home or if you want to you know watch and you know play around the source code as the episodes go by。

 you can download it start here， just click download down。

 you're welcome to give a tip or anything like that here， but you can just download the source code。



![](img/2c5915bbf2791187d13c00d769bdde9e_5.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_6.png)

So I'm using no Ad one source code and hopefully by the end of today we're going to make some nice progress and I'm going to post the second episode source code here as well Okay。

 so if you remember last time。

![](img/2c5915bbf2791187d13c00d769bdde9e_8.png)

We created our base platform layer and base engine， if we can call it that that allows us to。

 you know。

![](img/2c5915bbf2791187d13c00d769bdde9e_10.png)

Move to render to get input to play around with the lit square the screen。Okay。😊。

So that was basically it。It was like two and a half hours of work and we got everything we need to start doing the gameplay。

 so that's what we're going to do now we're going to actually build the game and the idea is to start with a breakout clone but slowly deal with more interesting gameplay as we have more ideas than things go fluidly。



![](img/2c5915bbf2791187d13c00d769bdde9e_12.png)

Okay， so I'm going to open fourcodeder， here's the editor that I'm using。

And inside inside the code there's the game code So what we did last time was to create all these nice structures that we can use like draw and pass a position。

 which is our unit here and the half size and the color as well as you know getting the input with these things Now what we want to do now。

 I think the first step to create breakout is to make the mouse cursor control the little square。

 not the keyboard thing is going to be more interesting gameplay。

 but we might change it later on you know maybe do some different game modes and things like that in order to do that I'm going to open the Windows platform。



![](img/2c5915bbf2791187d13c00d769bdde9e_14.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_15.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_16.png)

And before we simulate the game right after input up after the input messages。

 I'm going to call a function called the G cursor。Pause our position if I'm not mistaken。

 let me just。Check it out。

![](img/2c5915bbf2791187d13c00d769bdde9e_18.png)

Okay， so yeah， this is the function we're going to use to get the mouse。



![](img/2c5915bbf2791187d13c00d769bdde9e_20.png)

But it's pretty weird because it returns it turns this point structure and call this seven mouse。

Poiner。And I get to a pointer。That。Okay， and but it returns in coordinates relative to the screen size。

 not exactly our window size。 So what we want to do is to convert these。

 this unit that it get it returns to us to a。

![](img/2c5915bbf2791187d13c00d769bdde9e_22.png)

To a window relative unit， like， like a screen。2 clients。 That's the function we need。And yeah。

 it's pretty， pretty easy we're going to pass the window and we're going to pass the point。

 the pointer to the point。

![](img/2c5915bbf2791187d13c00d769bdde9e_24.png)

And then it's going to convert that to that specific。Window size， okay。Okay， so mouse。Fire。Okay。

 that's it。 Now all I have to do is pass that to the game。

 If you remember last time we created this structure for input。

 and we already created this mouse X and mouse Y。 I think in inside math， I'm going to do。😊。

Eigger vectors。We created floating point vectors for position last time。

 now think I'm going to do invers。You call it like a V2I。

Just so we can make like a more concise type here in the pet。Daa is going to be a D2I mouse。

And for now it's in pixelels。I think the game is going to be responsible to convert。

 we're going to check it out in a second。

![](img/2c5915bbf2791187d13c00d769bdde9e_26.png)

Okay， and if I'm not mistaken， the point structure， you see point。



![](img/2c5915bbf2791187d13c00d769bdde9e_28.png)

It's just the X and y， yes， it's X and y， so we can pretty much use that when to do a input。Y mouse。

I do。X。Right， okay， equals mouse0 God x。先 thing for one。And now we should be good to go。Okay。

 I'm going to debug step into that， just make sure that we didn't do。



![](img/2c5915bbf2791187d13c00d769bdde9e_30.png)

Anything wrong here？Okay， and now the input mouse has。You know， 232 and 500。

 that looks like reasonable numbers。

![](img/2c5915bbf2791187d13c00d769bdde9e_32.png)

Okay， and now all you have to do if you were to go to the game。 you can now use that。

 But this is in pixels right now， I'm going to use the draw。In cases。

And I're going to pass the input。Mles at X， you put miles at y。Pa。Same thing。

 but I'm going to add like 20。Make a little square and then I'm going to do red。Okay。

 let's see what we have。

![](img/2c5915bbf2791187d13c00d769bdde9e_34.png)

Okay， now if you can see， it's pretty weird， right， the ex position is correct。

But the Y position is inverted。Okay。😊，And it's pretty easy to fix that all we have to do here in the platform layer before we。



![](img/2c5915bbf2791187d13c00d769bdde9e_36.png)

I want to process the mouse here。The wine is gonna be。



![](img/2c5915bbf2791187d13c00d769bdde9e_38.png)

You know， the negative of the what you get， but it's going to be offset by a whole screen height。

As you guys can see， right？

![](img/2c5915bbf2791187d13c00d769bdde9e_40.png)

So I'm going to do is to do。Height， so it's render buffer dot height。Yeah。

 mine is I think that's correct， okay。

![](img/2c5915bbf2791187d13c00d769bdde9e_42.png)

Now the red square is sticking to our mouse burn printer and it's pretty， you know pretty precise。

 I think there's like one frame of lag compared to the Windows actual mouse。

 so I think that's pretty pretty good。I think it's our first word， you'm not sure。But yeah。

 this is pretty nice。 if you guys have any questions。

 you can drop them in the comment and in the chat and then and try to answer them。呃。Okay。

 so now what you're going to do is create an actual player and have the the。the user control the。

 but we also have to convert that unit to world units let's call it them that because we're going to use good collision stuff and things like that and and pixel is not a very good unit as we saw last time because if you have like a very small screen see that the green square that we program last time properly know translates to the correct size based on this window but the other one doesn't so we havent going have to change this mouse X and mouse Y。



![](img/2c5915bbf2791187d13c00d769bdde9e_44.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_45.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_46.png)

T pixels from pixels to a world， so I'm going to call it this mouse world。Coornet。

 and maybe I'm going to create a helper function。In the render suppose or math'm not sure because we did the calculations to do the other thing know where we got a word coordinate and transformed that to a pixel coordinate。

 So So all we have to do is the other the other way around so let's do an internal。

That's return of V2， right， eternal of V2。It's called them pixels。To world。

And then I'm going to get a V2I。F those coordinate。Okay。😊。

That looks good and I'm going to create a result here。I all that X and result result dot y。 Okay。

 now let's think a little bit about it。 Let me just。A simple call here， take those。About past input。

你 but。Mouse。可以。😊，And now with this， we can pretty much delete and now we're going to do the same correct。

But using。The mouse world。ま都。Let's see。All right， now let me draw just to get a clear idea to you guys what we going to have to do。



![](img/2c5915bbf2791187d13c00d769bdde9e_48.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_49.png)

What we did。In that other， let me put it inside the here for a comparison on this function。



![](img/2c5915bbf2791187d13c00d769bdde9e_51.png)

Was。Okay， we had a scale， which is a constant value， and then we chose based on the aspect ratio。

If we would use the height or the width。As a multiplier to make it a non pixel dependent。

Okay so if you we have like a very wide screen， we're going to get more sides。

 know if we make it larger， I suppose。We're going to get more screen space。

And it's not going to change the size， however， in this case。

 if you get a little bit of a wider minor。This point is going to get larger。

So that's why we multiply it like this and then I we just offset it by half the width and half the height。

Because we want to center in terms of world unit， at least for now。

 because we don't have a camera later on， we can do a more。



![](img/2c5915bbf2791187d13c00d769bdde9e_53.png)

Can get the this a as a brander and then do it offset。 Okay， so it's pretty much the same thing。

 but the other way around。 So we are in pixels。 So the first thing I'm going to do is to。

know we're already doing that on float， correct？Not sure which point we should convert to to float maybe right off the bat Okay。

 so this guy is going to be。Floload of pixelixs cornnet dox。Minus half。Of the screenprinter。

Ber dot with。Okay。And the same thing。tight here。Okay， thank you， it has no question for the moment。

 but I like our stuff。I like it that you like my stuff。

 hopefully we can learn a or two if you have any questions， be sure to just tell me okay。So。

Exels coordinate。So that's the first step we just offset it to the center now we should probably test it。

L by line， then I'm going to write the whole thing， then I'm going to play around it， okay。

Now we're going to change the aspect multiplier and the scale。The aspect multiplier is only changed。

W per frame。So later we can do like a cleanup of this。啊，红衣。Needs to be done。When size changes。

So maybe we can do that in a platform layer or do like in it render and do this calculation。

But for now。I'm going to just create a function out of it。 so I'm going to create a。Ask。Multipliier。

Calculate。Aspect to multiply。Okay。And。So the same thing I'm going to do here I'm going to。

Get the aspect multiplier。And now I'm going to， we are multiplying by it。

 I'm going to divide by it and the scale。S， we're going to do like hard coded out here just to make sure that we don't。

他是的。Yeah， I'm not sure the best place to put this maybe as a global for now。Okay。Okay， now。

We did first part， now we're going to result dot x and result or y， we're going to divide that。

By the aspect multiplier and the scale。Like multiplliier。Thatsけよ。

Just the opposite of what we did last time。And okay， this is done then。

And in this case we have to do， they have size too， but since we don't have a size here just。

Coordininated position， we don't have to do that， so I think we are done。



![](img/2c5915bbf2791187d13c00d769bdde9e_55.png)

Let me see what happens。Okay， and apparently we are the， and if you notice the difference。

Our world units use the center as the draw our ju here。

 or draw rack it gets the center and the half size， right？



![](img/2c5915bbf2791187d13c00d769bdde9e_57.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_58.png)

So now we are centered in a mouse before we were in the like bottom left corner because that's Windows。

Cornet system， someone asked last time what was the coordinate system we were using。

 we're just copying windows for now bottom left in terms of pixels and our our coordinates like grow upwards in y and to the right in X So yeah now we have pretty much everything we need to start making the game This is what I'm going to do I'm not going to pass I'm going to you know delete this green guy。



![](img/2c5915bbf2791187d13c00d769bdde9e_60.png)

For now。Okay。Okay， and I'm going to do a vector two here and it's going to be the。The mouse roots X。

And a fixed file， let's say zero for now。

![](img/2c5915bbf2791187d13c00d769bdde9e_62.png)

Just so we get the the base idea of the game Okay yeah so this is the idea of the game we're going to be stuck like this。

 then we're going to move sideways maybe I should you know limit。The player position。And then， yeah。

 but not for now， actually。

![](img/2c5915bbf2791187d13c00d769bdde9e_64.png)

Okay， so I'm going to do a little bit of a taller guy， like two and maybe 10。



![](img/2c5915bbf2791187d13c00d769bdde9e_66.png)

Let's see what you have。That the other way around。

![](img/2c5915bbf2791187d13c00d769bdde9e_68.png)

It's10 and X two in line。

![](img/2c5915bbf2791187d13c00d769bdde9e_70.png)

Okay， this is。I'm not sure how good this is， but I think itll work for now and I'm just going to。



![](img/2c5915bbf2791187d13c00d769bdde9e_72.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_73.png)

没回来。Down。Okay， this is， this is。你跟跟冇见。Okay， this is good， yeah， I think in terms of position。

He may be a little bit too big。

![](img/2c5915bbf2791187d13c00d769bdde9e_75.png)

Not sure if it's going to be easier or not。Let's test with that。Okay， so what we need now is a ball。

 al right， so I'm going to create。A ball。包皮。And a ball。デピ？Which stands for the velocity of the ball。

 right？And I'm also going to initialize。The variable， so it's going to be initialized。

 it's going to start as false in the first time。We run our loop。Iitialized。

 we are going to set it to true and then we're going to do everything we need to do to know set up the variables like ball DP。

 let's say equals。DP dot y equals minus。-10。O。Now。嗯。Now what we're going to do。Is a。

You can draw the ball， right？入边个天。Go to make it a D2。Lets say two by two。And let's make it， I know。

 the color they pretty bad。We're going to make like this， okay。

And then I'm going to calculate the ball P based on the ball D P， right。

 The ball P is going to be whatever the ball P was， so。IGoing to make a mockup here。

 It's going to be ball p。Plus。TheAbout DP。Times the DT that we get here， however。

 we have can't do that can' overload plus to work onstructs。

 so we're going to have to do our add V2 and multiply V2。Line V2， add B2。

It's going to got to beat to A and I heat to B。给。😊，And it's going to return。Let say， A X plus。DX。

And be and A Y plus B， Im kid。Yeah， it's easy enough， right， even for for yeah。

Now we're going to do our mold。V2。And。It's going to be a multipied by scar， correct？

Then we can do like other kinds of vector multiplication later on should we need them。Okay。

Look good now studentss going to be add too。And then this is a Mo tube。Hello， Timmy。

How are you doing？

![](img/2c5915bbf2791187d13c00d769bdde9e_77.png)

We are starting to get gameplay stuff。Okay， now this ball is not very interesting， first of all。

 it's huge， right？And it's falling very slowly。

![](img/2c5915bbf2791187d13c00d769bdde9e_79.png)

So let's make it like a lot faster and you can do it like。



![](img/2c5915bbf2791187d13c00d769bdde9e_81.png)

増でしまう。

![](img/2c5915bbf2791187d13c00d769bdde9e_83.png)

Okay， now it's way too fast and way too small。

![](img/2c5915bbf2791187d13c00d769bdde9e_85.png)

See， maybe。

![](img/2c5915bbf2791187d13c00d769bdde9e_87.png)

呃。Yeah。😊，Yeah， maybe that' that's okay， but now let's make it a start off。



![](img/2c5915bbf2791187d13c00d769bdde9e_89.png)

Kind of a deficit direction， Okay， yeah。

![](img/2c5915bbf2791187d13c00d769bdde9e_91.png)

That's due too fast。O。

![](img/2c5915bbf2791187d13c00d769bdde9e_93.png)

Yeah， now it's going to work for now now what we're going to do is collision， right？



![](img/2c5915bbf2791187d13c00d769bdde9e_95.png)

Because the boy is like just going through us。And I should probably instead of mouse world。

 I'm going to do this slide。A your key。来有。呃。Cl可。Yeah。😊，And then okay。

Now what we you're going to do is get a。It's going to test if the ball intersects with the player。

 right， and the basic idea for collisionleg detection in this system is pretty easy。

If you guys want to search more about it， it's called AABB。Versus A ABB。

 which stands for X's aligned bounding box。Basically， we have a square。And a rectangle。

They are aligned。To our coordinate system， so it's not like a rotated rectangle or more complex shape it's very easy。

 so the only thing we have to test in order to see if they intersect or not。

Is whether the biggest guy here。Is smaller。Actually， is larger than the smallest guy here。

And the other way around， right， we have to be inside in both aes。Sure sure you guys what I mean。

 if let's say。Interssect。We can call AABD versus AAB。I'm not sure if this's the best name for now。

 I could player your pee。And also I have to set the player P to minus 40， right？可有。

P dot x equals minus 40。 and this is going to just change the the of P。Okay， so if the player P。

And players have size， right。Collidedes with the ball pe。And the ball half size。啊。Yeah。

 if it does collide， all we're going to do now， just for the sake of testing。

 we're going to redirect the ball D P。 So ball DP dot I。Going to invert the vector。

 so it goes up instead going down。Okay， so that's the basic idea of what we're going to do。

 I don't know if AABB versus ABB is the best name， though okay。X， not a member。 Okay。

 let's go over K X。They would have size and b have size， yeah。Size。系有。Size。I have size going be82。

Of dot 75 dot7。Player have size。It's gonna be 10 and2。You can see the pattern emerging here。

We implement libraries B3， for example， or writer press， well。

 I may use libraries a little bit down the line， especially for like images and bit mapps。😊。

But I'm not going to use like box 2D for a simple collision detection like this。

 and're not going to simulate physics， or anything like that。 It's going to be really， really simple。

 We can write the。This only function， that's the only function we need pretty much ever。

A for collision。And yeah， that should be enough for us to know make a game if we got to the point where we want more advanced stuff and。

We're not going to Wi's library for that， but part of the idea is to learn a lot of stuff。

 so that's one of the goals， so I'm not afraid to you know try to write stuff that will be easier to get a library。

It's total of fun to write for。 Okay， player P。😊，AABB， okay， so now we should。

 I'm not sure if we keep that a math or we create a new collision。Coicition do C file。

 but it's going to be pretty small so we'm going to in a。Bluue 32。Called A， A B， B， versus A， B。

 B takes a P1。A啊。Size one。And then everything。Steth one。时间。😊，And this is what we're going to return。

Let me just draw it a little bit more calm this guy。I'd say does not intersect with this guy。

 How do we know we know that because the largest guy is smaller than this guy。屎。😊，And。

And in this case。We're the largest guy。Lge guy。Is bigger than this guy。

 The smallest guy is smaller than the biggest guy。So it kind of works the other way around see。

 So I may do each point individual individually just for the sake of clarifying and maybe the optimized builds going to be。

Yeah， I think I may do that I'm going to do like。呃。1 x 0。This point。LetSee just。

I'm not sure may not need that， Okay， so P1 dot x。Minus half size1 dot x， so this is this point。

Let's see， if this guy。Is greater。If。这些。Failure if this guy。Is greater？

we add the receptor if this guy is smaller。Then the largest guy， right？2。

And I have to do this work pretty much every year。Every other。Conbin okay。And this guy。Is less than。

です guy。If'm not sure this is correct， we're going to test just in a。We should test just， yeah。

 in X for now， I'm sorry。Which that's just why just to see because the basic idea。

 I think think we're going to do a more secret version。



![](img/2c5915bbf2791187d13c00d769bdde9e_97.png)

Just's get started。If let's say it's a one deco， right？We have a our。Our P1， P1 is the player， right？

The P1 dot Y plus have size 1 dot y。It's this point， let's say they players liked this。Okay。

 so this point is the longer that we're testing。Thisva， which is the。This point of the ball。

 which is the P2 dot line minus f size。Two， don't mind if this guy。Is smaller。Right， it did。

Or it can do it the other way if this guy。Is smaller than this guy， there's no collision right。

 so we have to test if it's greater。Okay， so this is the like the very basic one。

 And I think we can do that。 Okay， all I have to do。Is include。

So probably to include that in the game because it's like engine stuff。



![](img/2c5915bbf2791187d13c00d769bdde9e_99.png)

ButFor now， let's just a quick。So we should just kick， right？Yeah， okay。



![](img/2c5915bbf2791187d13c00d769bdde9e_101.png)

For some reason， it started offset， I'm not sure why。Let me just see。 I think we said。Game。

We should accept the。

![](img/2c5915bbf2791187d13c00d769bdde9e_103.png)

PY to minus3。啊。

![](img/2c5915bbf2791187d13c00d769bdde9e_105.png)

DPX of 40， why did we do that？I think I meant the P， Y。



![](img/2c5915bbf2791187d13c00d769bdde9e_107.png)

对。人唔好事。Yeah， this is it So see what we did there， we finished a oh we didn't finish。

 we started a one deco collision。

![](img/2c5915bbf2791187d13c00d769bdde9e_109.png)

So whenever the ball hits this part of the player。

![](img/2c5915bbf2791187d13c00d769bdde9e_111.png)

呃。Yeah， it just reflects。Now， the problem is。

![](img/2c5915bbf2791187d13c00d769bdde9e_113.png)

That。We don't test the x coordinate， right， so we can just move by the side in words。

 see it's easier to do this step by step。

![](img/2c5915bbf2791187d13c00d769bdde9e_115.png)

So。😊，The same idea for the X。Just okay。So， if P X。Plus， half size 1 x。 It's greater than P。

To x minus half size 1 thatt x。Now we're testing。

![](img/2c5915bbf2791187d13c00d769bdde9e_117.png)

If it's in the right side of this guy。 So right here。See if that's true。



![](img/2c5915bbf2791187d13c00d769bdde9e_119.png)

Nicely， but right here it's going to reflect because we're not testing this size yet， okay。

You guys understand， right， the process of making a this thing that was pretty。

When I start typing this color right off the bat， started to get complicated。

 even you know in my head， even drawing a little bit。

 so just did the simplest thing possible and you managed to fix that pretty easily。



![](img/2c5915bbf2791187d13c00d769bdde9e_121.png)

Yeah， let's see like this。Okay。G。Now， let's say this side doesn't work。

Let's do the other side now the question for you guys is what happens？If， you know。

 if the ball is like gone past me， and then I intersect with this like this。

Let me just try a more visual thing。Pretty much every frame right sorry， I didn't get it right。

Every frame you should， yeah， it doesn't， it doesn't show it up。See that it's stuck if you see。

 and manage to get it in the perfect position， if you see very closely。😊。

You can see that it's actually going up and down。Every other frame。



![](img/2c5915bbf2791187d13c00d769bdde9e_123.png)

Yeah， it's pretty， pretty weird right， this will happened we're testing if we are colliding with a bulb。

 change the direction。😊。

![](img/2c5915bbf2791187d13c00d769bdde9e_125.png)

So this is what happens。We are here and the about is here。We're not colliding， we're not colliding。

 let's say like this now we are colliding with a ball， so it was going down now it goes up。

But in the next frame， we are still colliding， so we changed this direction again。See。

 Anna that's basically。That's basically infinite， right？So there are a few ways we can yeah。

 it doesnt make sense， but it's weird right it's kind of counterintuitive a little bit what we want to do is maybe a little bit of a hard hard coded solution。

 right？😊，Is that a。Maybe you should test。If we can test a lot of stuff， we can do like。

If the ball is less than our position。hich means that the first collision happens with just。

Change the position and then we don't test like something like this if。

Thevol P pi is smaller than minus1 smaller than zero with at the collision lesion。See。

 so now we only test if the boats coming toward us。So if the' voice like this。DP is negative。

 we're going to test the collision， and then we test the collision like this， we collide it。

 then all it's going to do is to reverse the direction， but next frame， since it's going up。

 we're not going to test again。

![](img/2c5915bbf2791187d13c00d769bdde9e_127.png)

And let's see if it works。屎。😊，Now I'm not sure if the best， the best call。

To do in terms of game design。I'm not sure how it feels either。

 but for now I'm just going to ignore that。And kind of about work。The way。The way it is right now。

Okay， but it's not a very interesting game if you can't change the direction of the ball， right。

 so that's the very basic thing。

![](img/2c5915bbf2791187d13c00d769bdde9e_129.png)

We could， just to。Get started。If we coli it， we change the direction。

Of the five and we add the direction。We add the X direction， right？To the， to the player。

But we don't have the play speed。So I'm going to assume that we have a player DP。And dot X。Correct。

 yes。

![](img/2c5915bbf2791187d13c00d769bdde9e_131.png)

And。So the idea of this movement， and we're going to iterate that a lot in terms of design。

 if we are going really fast this way。Id say let me draw easy this way。呃。And the boat。Hit us。

Like this，'s say like this， it's going to go this way。But it's already going this way。

All we're going to do is to add our position to it， so it may go straight。

Like like a 10 is effect like the boats really affected and do you get the other effect。

 so it kind of encounters one counters the other one， and then you have the straight movement。Or a。

Yeah， if you go to this site， it's going to be way faster， right？

Where if you go like a very tiny amount， maybe all we can do is remove a little bit of the speed。

 I think it's going to feel nice。

![](img/2c5915bbf2791187d13c00d769bdde9e_133.png)

But we do have to get the player D， which is the player。The player。在拉ly。And are we going to do？

Is to subtract the old position I'm going to call like a。You call this a player。new。X。可以。😊。

Play your new X。べ this。And the player VP， playerdp。x。It's going to be the ODx。This guy。😊。

Minus the new X。没音。😊。

![](img/2c5915bbf2791187d13c00d769bdde9e_135.png)

USX。Okay， hopefully that makes sense。I see if we're going go a little bit like this。

I think we got the。The other way around。Yeah。

![](img/2c5915bbf2791187d13c00d769bdde9e_137.png)

Yeah， we moved to the other side and that was pretty slowly。So this unit。Is the oh。

 the third defeat is in seconds and this guy is in frames， so we do have to multiply this。By the DT。



![](img/2c5915bbf2791187d13c00d769bdde9e_139.png)

Isn't that correct？ウィックあ say。We are at unit 10 and now we are unit 12。I'm sorry。

 the other way around like decrease light in our unit eight。RDB is the new one minus the old one。

Okay， so we fixed that direction problem， so it's going to be minus2， right。

 but this minus2 is minus2 per frame。

![](img/2c5915bbf2791187d13c00d769bdde9e_141.png)

And we want this scale to be per second。

![](img/2c5915bbf2791187d13c00d769bdde9e_143.png)

So how are we going to change this， all we have to do？Yes啊是。Minus two per frame。

And have to do a per second thing so our DT is how many seconds per frame we have。Yeah。

 so if we divide by the DT。Correct。We're going to multiply by this guy。And then I can。



![](img/2c5915bbf2791187d13c00d769bdde9e_145.png)

Yeah。😊，Okay， let's see if that is correct。

![](img/2c5915bbf2791187d13c00d769bdde9e_147.png)

Okay， yeah， now we are talking。哈。think's a little bit too sensitive。I just trying to do it。Yeah。

 look at that bug gold team he says， that's pretty， pretty interesting。😊，Yeah。

 I think it's I think it's。对不起。And just。Yeah I think it's nice。

 maybe it's going to be hard to do like very precise ones and we can make it not exactly like this。



![](img/2c5915bbf2791187d13c00d769bdde9e_149.png)

Maybe you can add a like a loss of energy or R trail here。

 but let's see now what we're going to do to make it very chaotic and it is going to be fun really quickly All I have to do is to make it bounce off the walls that was really。

😊。

![](img/2c5915bbf2791187d13c00d769bdde9e_151.png)

Oh my god， it's to be。

![](img/2c5915bbf2791187d13c00d769bdde9e_153.png)

Funny， yeah。It's going to be really chaotic。 Okay， so the same thing we did for the player。

 this idea here。😊，We can do for the。Vable and just as a final example， I'm going to do the other X。

 other y as well。So this is actually the AABB versus AAB because we're missing one。1。

One axis is here。I think that's correct。In this case， not going to make much difference。

Unless you know the ball is like here and we are went past it。



![](img/2c5915bbf2791187d13c00d769bdde9e_155.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_156.png)

But yeah， just to make it complete。 Now， if the ball collapses with the player， okay， Els。

The ball pe。Dot x is greater than Ed to get like an arena half size。Just for us to。

Have that usually measured and maybe display a little bit of a difference if the ball x is greater than they are in a size of x。

All we have to do and we should probably also cap the ball position。Maybe possibly like。

If the bolt went like this。We should just make it like this and then change the direction。

If you wanted to do like a more precise collision detection。We should make it move just。

Minus the part that it already moved that frame。If that makes sense。But for now。

We can comment this and make like a robustbuness。Comment like。Yeah， subtract。我 the ball。All right。

 I don't think we're going to care about that much。Alright啊。Yeah， I do。

 I am going to comment that can track with the ball already moved。To get。To the colliding。Yeah。

 but I don't think we're going to care about that。And much。All you're going to do is to set it back。

So they are in a size。X。And actually， this is not correct。

 just like here we did that plus have science have to do with that as well。

So we're testing if it's greater than this side of the wall， right？Plus。The ball have size dot x。

 Okay， if that is greater than the are， then the ball X is going to be the are minus。

The ball has hopefully that makes sense。 if you guys have any questions you can ask。

 but that's not very， very difficult。 And we're going to reflect the factor。 So ball。P。Dot X。喂。😊。

Arena， yeah。 and now gonna have to create your size arena。Have size。Yeah。

 I call it area size buildingina。Have size。When we knit that。To， let's say， if the player at -40。

Maybe the arena， that's an X。 Maybe the arena is like。50。Yeah， we have to drive that。Let's see。

Let's say it's 30，50。Actually， 80，50。And I're going to draw a re for the arena。

And then we can optimize that later on because， you。

 I had this problem in the paw game that I showed you guys last time。



![](img/2c5915bbf2791187d13c00d769bdde9e_158.png)

If we have our screen and then we first， we clear it to a color。

 so we're going to go to every pixel and dry it。And after that， we draw arena on top of that。

 let's let's say blue。We're going to waste a lot of work， you know， filling those pixels。

 So what we should have is like a clear。Screen and fill wreck。single function。

 so we could screen where the reactor didn't appear， let's say。



![](img/2c5915bbf2791187d13c00d769bdde9e_160.png)

But for now， let's just do two calls。 So we're going to do a。It going to be sector 200。

You're going to do player， not player arena have signs。We have size， okay。

Now let's see what we have I'm also going to do that。い？In the other direction just。

Does one can properly test if it's less than minus are not half size。Okay。

 the position is going to be Skype plus。Yeah minus half size close skype。

And then we're going to to reflect the access row。

![](img/2c5915bbf2791187d13c00d769bdde9e_162.png)

Let's see。Okay， green was not a very nice color for the arena。



![](img/2c5915bbf2791187d13c00d769bdde9e_164.png)

Let's do it like a slider as it make the little bit darker。And nice made。This color。



![](img/2c5915bbf2791187d13c00d769bdde9e_166.png)

I turn out blue， but that's okay， suppose wow didn' I really miss that。



![](img/2c5915bbf2791187d13c00d769bdde9e_168.png)

嗯行。You've got it wrong， apparently。This guy。Minus half size。Plus， ball have size。



![](img/2c5915bbf2791187d13c00d769bdde9e_170.png)

Oh， it's Dp。Yeah。😊，That was weird。

![](img/2c5915bbf2791187d13c00d769bdde9e_172.png)

Okay， now all we have to do is the same thing for the white。

 but the arena didn't it's not recognize nice。

![](img/2c5915bbf2791187d13c00d769bdde9e_174.png)

I think it's okay in terms of x， maybe a little bit more。



![](img/2c5915bbf2791187d13c00d769bdde9e_176.png)

Maybe we're going to do 90， but we can make it like。



![](img/2c5915bbf2791187d13c00d769bdde9e_178.png)

Shorter like 45。Great。Oh， now we've got a little bit too much here。警さ forた。



![](img/2c5915bbf2791187d13c00d769bdde9e_180.png)

打得起。Okay， yeah。

![](img/2c5915bbf2791187d13c00d769bdde9e_182.png)

Yeah， now we're talking， right？It's going to be really hard to have to really multiply this guy down。

Okay， and then we're going to test safety for the。For the top position。

 but I'm not going to put that in the Elif。

![](img/2c5915bbf2791187d13c00d769bdde9e_184.png)

Because maybe in one frame， it can do like both。Like this。



![](img/2c5915bbf2791187d13c00d769bdde9e_186.png)

So I am going to do a separate it for that if。B key。Dot5 is greater than the arena。Half size dot lie。

I the same thing plus。Ba half size dot by。Well in this case， we're going to do the same thing。

 but for apply。So it's going to be plus this guy minus the guy。



![](img/2c5915bbf2791187d13c00d769bdde9e_188.png)

And' going to reflect the what position。

![](img/2c5915bbf2791187d13c00d769bdde9e_190.png)

Yeah， now now we're starting to have the basic gameplay。Idea， okay， yeah， let's see。Okay。

 let's see if I can try to no。

![](img/2c5915bbf2791187d13c00d769bdde9e_192.png)

So yeah， I'm just， I'm going to put like a random number here。Just because that was really hard。

Let's see this guy， I'm going to。Comment。Yeah。Player。肯定性。Okay， and let's say half of the forests。

Better。

![](img/2c5915bbf2791187d13c00d769bdde9e_194.png)

ok。That was a little bit better。Yeah， see what happened， you saw the bowl inside me。

That because it entered through the side。

![](img/2c5915bbf2791187d13c00d769bdde9e_196.png)

And。Yeah， maybe just gonna test see how， how that feels。 Maybe I'm going to do the ball。

P the x is going to be。The player。Pだ x。Dota why I'm sorry， typing correctly and say it incorrectly。

Plus， the player have size do。

![](img/2c5915bbf2791187d13c00d769bdde9e_198.png)

So now， if we do do that and to the side， it's going to， yeah。

 I think that feels a little bit better。 It's going to automatically go to our。To our position。ok。

Yeah。

![](img/2c5915bbf2791187d13c00d769bdde9e_200.png)

Alright， see you're not running very nicely when to go to full screen。

 that's because it does not optimize。

![](img/2c5915bbf2791187d13c00d769bdde9e_202.png)

And it's because of this as well， so maybe we can do that really quickly。Yes software random。

We're going to do a trial。It clears screen。Clear speed and draw correct。Okay， it' is a。

And the basic idea is it's going to work like a normal raw act。But where there's not a rectangle。

 we're going to get a clear column。所以啊。Re easyゃ。But we already did that。Okay。So yeah， same thing。

 apparently， right？But we're going to draw four more。Rs， where we don't。

Where we we are not in terms of the react position， right， so if we want to draw this react。

 we're going to draw it。That's this first line。Right now you have to draw this。Dsect。

Dis and distract。Okay， oh， you guys didn't see that。



![](img/2c5915bbf2791187d13c00d769bdde9e_204.png)

Have to draw this。Yeah， this guy。And these guys。

![](img/2c5915bbf2791187d13c00d769bdde9e_206.png)

ok。😊，So the first one。It's going to be zero， right， which the first pixelel。And0 to the y。

 And it's going to end in the x 0 and y 0。

![](img/2c5915bbf2791187d13c00d769bdde9e_208.png)

So it's this guy right here。Could you start here？And go all the way to x is zero。And y zero。

 I'm sorry， it's not going to be y0。 it's going to be all the way to the top。



![](img/2c5915bbf2791187d13c00d769bdde9e_210.png)

So's going to be the renderer buffer hi， sees nice to draw sometimes。



![](img/2c5915bbf2791187d13c00d769bdde9e_212.png)

Okay， so that's the first one， the other one is the same thing。

 but instead of starting at zero and ending at x。0， I'm going to start at。啊。Pas。

I'm going to start at X1。And end。Add a rendered buffer list。Okay。So now we got this guy。Started here。

You got all the way to here。Now the other two that are missing， they start the x is x0 and x1。

 and the y is0， y0， y1， the same thing。But instead of going all the way from zero to here。

 we can do just the offset because we're already painted at this part。



![](img/2c5915bbf2791187d13c00d769bdde9e_214.png)

Okay。😊，So， yeah。So it's going to be， it's going to be x zero。



![](img/2c5915bbf2791187d13c00d769bdde9e_216.png)

Next one。And let's see the first one is y zero， let's say the first one is zero。



![](img/2c5915bbf2791187d13c00d769bdde9e_218.png)

Y 0。And the other one it' going to be Y1。And drop buffer dot com。Do， during my last hope， Let's see。

 I stumbled on something。 send me this code。I said they are recruiting。

 they say like 20 things to do。You would have no idea what you're talking about， I'm sorry。Yeah。

 I also have no clue what to do。呃。It's got a random streams of numbers。Yeah， okay， apparently so TV。

Okay， to a few arguments。It's not the draw， it's the rendered buffer。



![](img/2c5915bbf2791187d13c00d769bdde9e_220.png)

Okay。

![](img/2c5915bbf2791187d13c00d769bdde9e_222.png)

Okay。So maybe if you go full screen， we're running， yeah， we're running a little bit better。

Am I not really going to care too much about it for now。



![](img/2c5915bbf2791187d13c00d769bdde9e_224.png)

Okay。And I have this light impression。

![](img/2c5915bbf2791187d13c00d769bdde9e_226.png)

That our screen size doesn't consider this guy。That's why we're not actually。Partperly standard。

I'm not entirely sure。Yeah。 we're not 100% standard。And that's not very nice。

And I have to check that later。

![](img/2c5915bbf2791187d13c00d769bdde9e_228.png)

I think in the conclusion， we're probably probably doing something wrong here in software Ring。呃。

We multiply， we change the scale。Right， and then we change。The width and height。Now。

 that does look right。Yeah， I'm not going to。

![](img/2c5915bbf2791187d13c00d769bdde9e_230.png)

I'mt want to spend too much time with this right now。



![](img/2c5915bbf2791187d13c00d769bdde9e_232.png)

Because all we're going to do is some gameplay。Amen。How are you doing。

 hopefully you can get along pretty well？I know you know all that stuff right and we are the gameplay part so this is going to be the more fun part。

 so this is what we have so far I'm sorry I just lost。啊。

We control this guy with a mouse and there's a ball and we just finished collision。

 the first version of collision。And we can like control this direction off the ball。

And it's not very nice to control yet。Kin of a little bit weird。

 but I'm going to give us a goal in order to make in order to test that。

 So now I'm going to start with the actual。

![](img/2c5915bbf2791187d13c00d769bdde9e_234.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_235.png)

Object of the game， right， which is to destroy the blocks。See this pattern here， we've got the P。

 the D P and half size， this we could probably create astruct and base ski off it like an entity structure。

 something like that。But I'm not going to do that for now。Maybe a little bit later。

Because I think the blocks is more important because there're going to be a lot more blocks。

So what we are going to do is create a search for the blocks， yeah， that makes sense。L。

 and for now it's going to be just a P。And let'd say exist。Or maybe life。Yeah， the's say like。

And what I'm going to do is just going to create a bunch of blocks in the stack here。

I say we'rereating。64 blocks and in initialization。I'm going to display these blocks。Someummer。Okay。

 maybe you should also put a block size here。So。We're going to go through all the blocks。Well。

 not all the， let'， let's say we want four blocks， four by four。So yeah。

 I'm going to do a wide block。A X block。あ。企。😊，Okay。

 and we also going to do a nice trick that says the next block。Which starts out as being zero。

 So all I'm going to do here。Just to get a block。Which is the blocks。First， next， next block。

And we can assert we don't have to assert。I doing my homework freak out， no。

 your home's not going to be break out。 It's going to be a more complicated game so。Yeah。

 consider this not your homework。😊，We concerned that the next block is less than the。Well， in fact。

 I'm not going to assert that if the next block is greater or equal to the array count。

 we're going to create that as well。Your rate count。Do you remember how to do the array count。

 tell me in the chat if you do， and then we can do that piece of code。呃。The recount of the blocks。

And okay， then next was will be zero， so we're just going to ignore and start reusing the blocks。Now。

 the array count。Let's just put that on the utilities。I'm going to do a macro。

It's going to get the array and the magnet is going to be pretty simple。

 It's going to get the size of the array。Divided by the size of the array's first element。

Think that's correct。 Okay， so yeah， it's basically gonna give me the size。

 the the the size of the array。 Like， let's say if the array is a 10 elements that is 4 by per element。

 the array size is 40 and the the element is 4。 So if we divide by those guys we have 10， right。😊。



![](img/2c5915bbf2791187d13c00d769bdde9e_237.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_238.png)

That's basically the array size。 It's pretty easy。 Now。

 then we're going do block life equals one for now。And we'm going gonna to do block P。D X。Equals。

 let's say， X。Times。Blocks， I think the block size is going to be a constant here for now。Baxa。

X times the block size X。Plus， let's say plus nothing。 just gonna be this based off。

I the why iss going to be the same thing。For the way。Okay， and then I have to do is to initialize。

The block size。Blolock size going be this guy。Let's say it's。超 by one。



![](img/2c5915bbf2791187d13c00d769bdde9e_240.png)

Okay。

![](img/2c5915bbf2791187d13c00d769bdde9e_242.png)

Yeah， we also have two render den I suppose， right？So this is the oh， we didn't use actually。 I kind。

 So I kind of lied when I said it was faster。 We didn't use the。😊，They clear screen and direct。

So I'm not sure why I felt that was faster， maybe。Maybe I， I don't know。Okay。Okay。

Now I shouldn be a little this。

![](img/2c5915bbf2791187d13c00d769bdde9e_244.png)

And actually not little it like twice as fast， honestly。Yeah， and now it's good。

And the colors change terms of reasons。

![](img/2c5915bbf2791187d13c00d769bdde9e_246.png)

Okay， now we're going to render all the blocks。For。怎啦对吧。Because black。What's not。

Blocks plus a count blocks。Block， just plus。If。There's no lights。感 continue。

What graphics library are you using we're not using any graphics library， forgetful。呃。

It you're forgetting。Past stream， which was the first stream， we created this basic setup。

 we created a window。We created a basic window here， we created a message loop for input。

 and then we created。These functions。To just draw the pixels so we're doing software renderry with no graphics library if want to check that out。

 it's on YouTube。

![](img/2c5915bbf2791187d13c00d769bdde9e_248.png)

The recording。Here， I'm going paste that on chat。Youtube。com/dayan。

And you can watch the first stream like two hours and we do that， it's pretty cool。Okay。



![](img/2c5915bbf2791187d13c00d769bdde9e_250.png)

呃。Just right， so no idea what's going on yeah。It's okay， we were making a game in C from scratch。

 so last stream we started with literally a blank file。And start typing crazy things like crazy。

 not crazy things， just code。And then we did the first part， which was the basic structure we needed。

 which was the window， the input， the software render ring pretty much and now we're doing the gameplay so。



![](img/2c5915bbf2791187d13c00d769bdde9e_252.png)

Yeah， we're kind of slow， but we're getting there so now it kind of moves now we're going to do the block rendering。

 hopefullyre going to see the blocks。

![](img/2c5915bbf2791187d13c00d769bdde9e_254.png)

I'm going to draw the blocks and it's going to be block peak。不啦。Size。And。The colors are really。

 really bad for some reason， let's do green。We already have a agreed。The player。Yeah， oh good。

Do a nice。Color pass。Later on banana。

![](img/2c5915bbf2791187d13c00d769bdde9e_256.png)

black。Okay， let's see if it has some blocks。We do have， not sure this is correct， though。



![](img/2c5915bbf2791187d13c00d769bdde9e_258.png)

But we do have。Some locks。Okay。'Not exactly sure if that's correct， let's do one block。

Should be one block at  zero zero。

![](img/2c5915bbf2791187d13c00d769bdde9e_260.png)

Yeah， I'm sorry， I have to。One block。Yeah， so I guess that was correct。You know what I should do。

 each block should be a little different in terms of color。



![](img/2c5915bbf2791187d13c00d769bdde9e_262.png)

Just to start making it more interesting。Yeah， I'm going to do that。

 I'm going to do a life and a UH color。And here we going to set the black color2。

Let's do a shade of gray。Based on these guys。So I'm going to create。In math， let's do like color。

Heper functions。We're going to do a。没。😊，Color from gray。I'mNot sure this is the best name。

And all we have to do， remember we have a 32 bits of color and we're receiving eight bits a gray color and want to put that on every channel。

 I say the three channels， the three color channels to shift the gray。By nothing， which is the blue。

 right， so we're going ship by nothing。I'm going to add that with some other shifts。m to shift that。

8 bits to get to the。The blue channel is 16 bits to get to the red channel。Okay。

So it's going to be make color from gray。Let's just do X。Plus， white now。And I do more blocks。

 I said like 10 blocks。Maybe x plus y。

![](img/2c5915bbf2791187d13c00d769bdde9e_264.png)

Andre can do some pretty interesting things with this later on。



![](img/2c5915bbf2791187d13c00d769bdde9e_266.png)

Okay， so I do have to use the color though and that position was all messed up。



![](img/2c5915bbf2791187d13c00d769bdde9e_268.png)

Okay， so black。Okay， now this is pretty cool。 Can a guys see that？But it's wrong， it's cool。

 but it's wrong。呃。Yeah。

![](img/2c5915bbf2791187d13c00d769bdde9e_270.png)

I'm not sure what else to say， have to run through the code to see。We're creatingating 10 blocks。

And the x is the x times， well， yeah， because they have block， maybe times two， okay。



![](img/2c5915bbf2791187d13c00d769bdde9e_272.png)

Okay。We are better， but we're still wrong。Because for some reason。Trow。



![](img/2c5915bbf2791187d13c00d769bdde9e_274.png)

It's not being used。Y++ x plus+。嗯。Not sure。Let's do a little bit slower。

 we're going to do one row of 10 guys。

![](img/2c5915bbf2791187d13c00d769bdde9e_276.png)

Okay， that looks correct， one， two， three， four， five， yeah。That's correct， I think。

 and let's do10 rows of one guys of one guy。

![](img/2c5915bbf2791187d13c00d769bdde9e_278.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_279.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_280.png)

Okay， that also looks correct now I'm not sure。Why are am making 10 ruless of 10 guys？



![](img/2c5915bbf2791187d13c00d769bdde9e_282.png)

Its wrong Oh maybe we don't have enough guys， we don't， we have 64 so yeah。

 we decided not to crash and just to reuse the same guy well that's what happens right。



![](img/2c5915bbf2791187d13c00d769bdde9e_284.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_285.png)

I'm going to make it like a 256 guys。Okay， now you're gonna have some fun， right。



![](img/2c5915bbf2791187d13c00d769bdde9e_287.png)

Let's making them a little bit bigger just for the sake of entertainment。Okay。

 let's make it like twice as。

![](img/2c5915bbf2791187d13c00d769bdde9e_289.png)

Okay， nice。And now that's also offset。That position So that of them starting in the。



![](img/2c5915bbf2791187d13c00d769bdde9e_291.png)

Center。Let's do， like， a。平や？Number of why guys， let's say 10。Number of X guys，10。Number why。No X。

Okay， and then we're going to do a。and the X alpha are going to be half， half the size， right？

B have size。Times the number of blocks， the nu x。Dot X and dot。Why。Okay， that's basically it。

 So if we add these guys， we should be all good to go。In house。Yeah。

 but we did it wrong where we had to subtract。

![](img/2c5915bbf2791187d13c00d769bdde9e_293.png)

Oh， that was not good enough。Okay， now it's pretty nice， but the why we shouldn't center that。



![](img/2c5915bbf2791187d13c00d769bdde9e_295.png)

We should probably。I'm going to hard code this for now。



![](img/2c5915bbf2791187d13c00d769bdde9e_297.png)

Yes。Then we can think about that later on。

![](img/2c5915bbf2791187d13c00d769bdde9e_299.png)

I'm sorry， minus。电的老上上。Too much。

![](img/2c5915bbf2791187d13c00d769bdde9e_301.png)

Okay， nice。Yeah， and that's going to be it very nice。



![](img/2c5915bbf2791187d13c00d769bdde9e_303.png)

Okay， let's start colliding with the blocks， then I'm going to focus on making game the fun， right？

But pretty easy， we're going through all the blocks here。Not sure if we should do that twice。

And which points are going to do that， maybe we should do。Yeah， we should probably do here。

 but we already clean the screen and draw the right for now we're going to do inside the rendering。

Look。We're going to simulate any of these guys。And yeah。It's going to be good， I think。

 so we're going to do the AABB versus AABB。That we drew earlier today。If。We are colliding。

So this is going to be the。Block。P。Block have size ballpy。if we do if we do collide。

 we have to know where we collide it from， right？So maybe we should do a block versus ball operation。

Yeah。😊，I think that's going to be better than trying to。Or it could just pass。

What direction we collided？Is see the college。Yeah， I think I'm going to do。 I' going to do a。He。

Let's say do。Bck。Versus ball。Once you receive a block pointer。And the ball。Pea and the ball。太上。

And we're going to separate these two axes here。Because if we are colliding。We have to know。

We have to know where are we' colliding from。If it's up or down。



![](img/2c5915bbf2791187d13c00d769bdde9e_305.png)

I mean，m sorry， if it's this side or this size。Like you have to know if the blocking this way to reflectlect this way or if the block this way to deflect this way。

子。😊。

![](img/2c5915bbf2791187d13c00d769bdde9e_307.png)

So I think the best way to do that。It's just going to be。Yeah， if we do collide。

 we have to check which axis is that so yeah I'm going to do。First。See here the call collide。

Why and applied。So if you collectide them both。Now you can see which one mirror co light， right？

Makes sense。If we callllide x。I'm sorry， this is like why。And then， if you collide。X6。If we do。

 if we do collide X。I also collide white just probably worry about both too。因为 yes。Okay。

 and we're going to do the same thing we do for the arena。I'm just going to change the direction。

But oh， actually， it depends， right？So if we collide， we are going to decrease the block collide。

Now we're going to change direction either way， so yeah， if we're colliding Dx。

 let's just change the direction。I think it's not going to be。

It's not going to work in the same case that we had to work for the player。



![](img/2c5915bbf2791187d13c00d769bdde9e_309.png)

Like this case。Where it's inside the block， anyone wants to leave it in the next frame。



![](img/2c5915bbf2791187d13c00d769bdde9e_311.png)

Couldn't leave。So in this case， that think's going to be just change ice so we have to know exactly if it's this size side so we can move him or this side。



![](img/2c5915bbf2791187d13c00d769bdde9e_313.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_314.png)

嗯。Yeah， so I'm going to split that even further。 Yeah， I'm going to do。Fide wide。

Let's call them left。Which is this guy？Collide whilewi， it's going to be easy to see。

 but it's going to be a little bit repetitive。全名叫 the。What do。Let's see， plus have size。Greater than。

The two minus。And does the F P1 and P2 have to change the block to the name to block？Okay。

 so we're going to change why。ゆ X。Okay。😊，And okay。If collide by。Left， right。And collide。诶喂。Right。

And Colllidex， right left。Collide。That's right。And if we do the x right。

 we're going to now we're we're at the same point， we're going to change。The ball Dp to the other x。

And of all P。Well P is going to be the block key。If you go ahead the right side。Of the block， yeah。

 it's going to be plus。Bck。3。So to get that。Okay。Okay， that does good and now we can test。DY slide。

I'm sorry， the。The why， why is up and down。If it's minus， it's down。Okay。Sorry about that。downown。

If we collide with the right， that's what we do else we're going to see if we collide with the left。

Hello Morphus， let's see you again。

![](img/2c5915bbf2791187d13c00d769bdde9e_316.png)

And me show you what we did so far today。We are starting to look like a game。So you can。

That was our student。We have ball in to control the pedal with the mouse and we can move and it collides with walls and stuff Now were doing the block collision。

Okay。Hey， Marcus， thanks。Just like congratulations for your initiative， thank you very much。

 I hope you guys enjoyed this as well， it's going to be a lot of fun。😊，Yeah。Yeah。

 we're almost done with the prototype and that's the fun thing we're going to do the breakout clone it's going to be the first thing。

 but we are going to start playing around it in terms of game design and make it more complicated and interesting things so I expect to spend some time in the gameplay for now。

 but yeah in terms of the game the base game is almost done。😊。



![](img/2c5915bbf2791187d13c00d769bdde9e_318.png)

It's not， it's not that much work。 You know， see that's the thing people usually think and making game。

 oh， I'm talking about Cbo game， right， making these Cbo games from scratch are like it's like impossible or like is it really hard。

 It's really not it。 It was been like one day。😊，Which was like two and a half hours doing the engine。

 now we're doing the gameplay。And maybe not， not that hard。 So if we collide the upside and our data。

 I'm not sure this isn't already correct。 It's going to turn run through this one more time。P1， Yeah。

 I have them changed P1。啊。P1 can be black。皮。😊，And two is going to be bally。And。Have size one。

It's going to be black。Size。And half size 2。F flag two is going to be。Ba。Have life。Bll have life。

All right actually typed B F5。It's supposed to be ball have size。Okay， so half size 2。这里包。Pa。

Get it was strict。Block。Its black。O，先 text sir。Mising semi callinglon。Where are we a考。Okay， yeah。

 else if。It's weird。 We didn't miss the same。 I can't miss the if。Will you save the videos， Yes。

 I am saving the videos and the first ones already on YouTube。😊。



![](img/2c5915bbf2791187d13c00d769bdde9e_320.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_321.png)

If we go， if you go to this link。which my YouTube page is YouTube。

com/d Z the first one's already there and it answered the other guys's question I remember it was who is how we did the rendering we didn't on the first episode that was pretty easy No problem markets I hope you enjoyed it you have any question about previous day you can also ask me and the source code if you want to play around with that is available on the HIO page so right here。



![](img/2c5915bbf2791187d13c00d769bdde9e_323.png)

Which is you can copy the links damazdm。h。o， there's my game there。

 I'm calling it break arcade Game Ta， it's very bad name。

 but hopefully youll hint of the game badd ideas that I have for the breakout game。

I already put the first days。Well， there's not a game， so the executive is pretty boring。

 but I do have the source code there， all four kilobytes of it， right？

And so you can download this heartS code and follow along or if you want to do your own game。

 that's pretty cool， I'd love to see that。

![](img/2c5915bbf2791187d13c00d769bdde9e_325.png)

And not going to spoil the surprise but hopefully I think we're going have a forum too so yeah just download down if you don't want to if you don' have a if you don't want to tip me you can just click no thanks and then you can download the filess。

 yeah easy as that。

![](img/2c5915bbf2791187d13c00d769bdde9e_327.png)

Okay， let's go back。

![](img/2c5915bbf2791187d13c00d769bdde9e_329.png)

To the yeah， we compiled， hopefully that was it and we can start doing some collision。



![](img/2c5915bbf2791187d13c00d769bdde9e_331.png)

I think oh， we're not calling that。And we spa the ball inside the guys。

 so it's not going to be very good for that。 So all I'm going to do。

I'm going to spawn the ball a little bit to the side the size of the are is 84，85。

 so I'm going to spa like 70 and x。

![](img/2c5915bbf2791187d13c00d769bdde9e_333.png)

For now。Just so you know， we can do that， okay， yeah， it's kind of kind of cool。



![](img/2c5915bbf2791187d13c00d769bdde9e_335.png)

Now， we're going to call。These guys。Instead of calling the A， ABB， I'm going to do the let's say。

 do block。Versus bulk collision。Going to pass。同认识的歌。Block F size。Ball P and ball half size。Okay。

 for a definition of basic different types。嗯。Okay， because we。Yeah， we。I think， in the。

In the witness platform from， the problem is we are first using the function banner Dec and C has this。

And C++2 has this four declaration thing。Which is like from before I was born。And。Yeah。

 I'm going to actually or the collision here。Okay。I see。完咩事。Yeah。

 I actually have to declare the block。

![](img/2c5915bbf2791187d13c00d769bdde9e_337.png)

Okay， now we compiled。Let's see what happens if we try to run。Oh my god。

I don't think I'm going to keep the mouse control。 I'm really， either I'm really bad at this or it's。

 it sucks like， okay。Just reflect off these guys。But it's kind of weird。

I think it just messed up the X and Y。

![](img/2c5915bbf2791187d13c00d769bdde9e_339.png)

If， let's see。The X， yeah， it's the other way around。 if you're if you're testing the y because。



![](img/2c5915bbf2791187d13c00d769bdde9e_341.png)

condition。Just drop with you guys。Let's say this is the block and this is the ball， if this fails。

 so we are inside the x position， we have to kick him off the y position。知。😊。



![](img/2c5915bbf2791187d13c00d769bdde9e_343.png)

So that was the problem。I think， let's see。I think we'm going to just change these guys。I see诶。X。

 yeah。

![](img/2c5915bbf2791187d13c00d769bdde9e_345.png)

Yes， if we are past。Let's see。The y is less than this guy， sorry if were colliding this part。



![](img/2c5915bbf2791187d13c00d769bdde9e_347.png)

Yeah， we might have to review that。For now， let's just see what happens。It's just called this。

Just for to sake of。Seeing the result， and then I have to do some cleanup。



![](img/2c5915bbf2791187d13c00d769bdde9e_349.png)

Yeah， see what。Yeah， it's not right。

![](img/2c5915bbf2791187d13c00d769bdde9e_351.png)

It's funny， it's like nothing changed。But we change the y to be based off the x。Okay。

 I'm going a bit computer now。Yeah， what I'm going to do is switch these guys。Okay。

What is ball P and ball DP， ball P as the ball position？So we initialize that 7540。

 and every frame we calculate the new position based on the opposition。

 so we add the opposition and we multiply the velocity with the delta time。

So these things for I going to be able to pronounce that。



![](img/2c5915bbf2791187d13c00d769bdde9e_353.png)

So there's the integration and that the're derivative。



![](img/2c5915bbf2791187d13c00d769bdde9e_355.png)

thing that's I say， derivative relative。Of the position which is the velocity， so yeah。

I think it's easy than to call it。Baoby。And if you want to do like acceleration， go DDP。



![](img/2c5915bbf2791187d13c00d769bdde9e_357.png)

I think that's。That makes sense， yeah， it's pretty cool。ok。

Now now it changed pretty much the whole thing， yeah， I think it's correct now except well。

 the X was kind of correct。Except。We should have we did deflect。The why， Oh。

 so the problem is we're deflecting both the Y。And the X。Then which only deflect the X。



![](img/2c5915bbf2791187d13c00d769bdde9e_359.png)

Maybe it's because。

![](img/2c5915bbf2791187d13c00d769bdde9e_361.png)

Yeah， this calculation is not correct， we're going to have to do this a little bit more slowly。

So this is what we're trying to do， the block。And the ball。We already have the the AABB versus ABB。

 which test collisions with two a's aligned bounding boxes， in this case it works perfectly。But。

We need to know。If the collision was done。In this side like this or this side or like a corner here。

And either way， what we are testing。We are testing if one is inside the other one， right， okay？



![](img/2c5915bbf2791187d13c00d769bdde9e_363.png)

All you have to do is yeah， we can do like a cheat。And say， yeah。think I'm going to do that。

It's going to be cleaner。Yeah， the cheap is if we collide， I'm going to do the A V B versus A B。垃啲。

Have size， block half size。毛皮。We all have signs。Okay， yeah， if we life。



![](img/2c5915bbf2791187d13c00d769bdde9e_365.png)

We are I1 not， and I can pretty much。Test， well， if R P。It's less than therapy。 I I mean， the ballpy。

 the ballpy。

![](img/2c5915bbf2791187d13c00d769bdde9e_367.png)

X， I'm sorry， Y is less than。

![](img/2c5915bbf2791187d13c00d769bdde9e_369.png)

The block。TY。That means we should reflect downwards。Well， not， not really。

Because in the case that we kick off this side。Yeah， I should probably studied collision more deeply。

 so yeah。So now it's where the learning thing comes in because clearly。

There's a quicker solution to that that I'm thinking and that box to the guy in the beginning of the stream。

 I guess he was right， I can kind of accept that， not that we should use。A library for that。

 just because we we want to learn the point is we should learn it more thoroughly in terms of collision The idea of question is really simple。

If we are inside this guy。All these things are true。So that first thing was really。

 really wrong in terms of the collision party。Now， the point is， we own't say。😡，How do we know？

If we should reflect this vector， this vector， this vector or this vector。

We could hack something together like， oh， if we are really close here。

 but if the ball's really fast。And it kind of collects like this it should reflect really downwards。

 So yeah， I guess the point is we should just change the。



![](img/2c5915bbf2791187d13c00d769bdde9e_371.png)

Based on the ball speed like we did here。In the player for guys who weren't here in the beginning of the stream。

We test if the buzz is going downwards， then we test the player。Yeah。

 I'm going to remove that commentary just because I want to care for now。



![](img/2c5915bbf2791187d13c00d769bdde9e_373.png)

Yeah。😊，Yeah， that kind of makes sense if the ball is going。Upwards。

Reflectexs it downwards and if it's going right。I guess we just do both axes。All the time。



![](img/2c5915bbf2791187d13c00d769bdde9e_375.png)

嗯。😊，Maybe let's see what happens。

![](img/2c5915bbf2791187d13c00d769bdde9e_377.png)

Not sure， though， I see。If you hit the bottom of a block， you just refer to Y， yeah。



![](img/2c5915bbf2791187d13c00d769bdde9e_379.png)

Yes， that's the point。 Yeah， we can do that because if we do， if we are in the bottom。

 we are not going to rever the。

![](img/2c5915bbf2791187d13c00d769bdde9e_381.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_382.png)

The other one， you're correct， but the problem is， how do we know if we hit the bottom of the block？

See， because our collision tests if we are inside the block， right？True or false。

 that's what your insurance is。So the question is， we are inside about the。the block， right？We can。

 can get the position， but the the direction。 Yeah， but the direction is not going to give us much。

 In this case， we only want to reflect the y not the X。

 So if want to really hack this just just for the。Just for the sake of。

Seeing the correct result even。

![](img/2c5915bbf2791187d13c00d769bdde9e_384.png)

Not for all the cases， this is what we expect， just like you said。

 we're just going to revert the why。See， now this is correct。Now， the problem is。If we do like this。

屎。If we hit this part of the block。

![](img/2c5915bbf2791187d13c00d769bdde9e_386.png)

We should refer to the X。questionestion is， how do we know？Where we are inside the block。

 it should probably be like a linear algebra。Solution to that。That I don't know。

 off the top of my head。But。Yeah， we can test if we are like on this。Geez， I may have to search that。

And it may not be fun。To go through all that stuff。



![](img/2c5915bbf2791187d13c00d769bdde9e_388.png)

Let's see。Yeah。Yeah， that's what happens when I go just do one axis。



![](img/2c5915bbf2791187d13c00d769bdde9e_390.png)

Okay。What happens？depends on the frame rate and ball speed。Yeah， but if I use the ball speed。

To determine where I'm going to keep off of。I don't know。Maybe yeah， I probably didn subtract it。

I think that's the point I helps attract the two factors。 this this is the problem if I use。

Let's say the ball speed is going like this way， just， okay， it's going this way。

The bulk appearserce the block through his look， that's true。

But we're not going to have such small blocks that yeah， I also agree that's unlikely to happen。Yeah。

 it's called Tly， what you mean and we can probably fix that by kind of a sweeping。

It's the collision turn sweep these positions。And that's probably what we should do anyways。

What the problem is in terms of the DP is that that DP could be the same here， right。

 so it doesn't really matter。What we do want to test like if we are。Oh。If we are inside。Oh。

 because this we are inside all the pointsac。Yeah， what you can do though， is subtract。I to get the。

 you know what I think I'm going to have to search that and play around with this and more。

Because I'm not entirely sure。Of the formula。There is issues in this case。



![](img/2c5915bbf2791187d13c00d769bdde9e_392.png)

Like。Yeah， I'm going to do like a quick search here with you guys， but if I fail。

 I may search offstream。

![](img/2c5915bbf2791187d13c00d769bdde9e_394.png)

Let's see。As you AABB versus ABB。

![](img/2c5915bbf2791187d13c00d769bdde9e_396.png)

Let's see what people say about that if the ball is completely inside a block and have no way to know the ball direction。

 I do know the ball direction。But the ball direction， as I wrote that， as I drew that on as a。

Red arrow here， the body actually can be the same。But I'm going to interpret that differently。

 so in this case， I'm going to revert。Just the， just the X and keep going up。 This case。

 I'm going to keep going to the left。 but I'm going to revert the y。So yeah。

 I do know the bold direction， but I don't know how to use that。To give me the answer。

 because in all three cases， the direction is the same。

And we can't do like a very hardcon thing of knowing if we are in know to decide。Are down here。

Because we may reflect like this。In this case， we should only reflect。Upwards。

You know what we can do？呃。If。Yeah， I think that's going to be a reasonable solution。

You're going to look in the old position。

![](img/2c5915bbf2791187d13c00d769bdde9e_398.png)

Do we have the position？Of the ball。

![](img/2c5915bbf2791187d13c00d769bdde9e_400.png)

Yeah， we can get the position， okay， so we try to go here with a ball。



![](img/2c5915bbf2791187d13c00d769bdde9e_402.png)

If we can't。We test。If which if we kind of a。If this guy， if this why， let's talk about why here。

 if this why。It's less than this guy。And if this guy。It's more， let's call this old， old Y。

It's less than this guy and if。Why is greater than。The other guy。Then we can deflect why。

Does that make sense to you guys？I'm trying to open the window here just。a little bit more winning。

Okay。Yeah， you know what， I'm going to do that。Going to get the ball the old ball P。

And then play around with that， it's going to be kind of a hackck。At first， not really。Okay。

 so let let's try this one more time to see if it's going to work。

So we have the block and we have the ball。Then you would need to reflect x E exactly， in this case。

 we would reflect no。If we would reflect why this case。So in this case， I mean。

 I pointed with my finger， I have to point them out in this case， we should reflect a why。

Because it's going to keep going to the left in terms of X。Velloc。

 but the y is going to change you' going to go downward instead of upward。

So I'm going to do is when I collide。Like I'm glad I'm excited somewhere like this。

What I'm going to test is， well， I can do that with the DP so I don't need to。Yeah， I don't need to。

To save the old fee。No， I'm sorry， yeah， I could do that and it didn go backwards。

But I think I'm going to say the okay anyway， so we have， let's say， this is the old position。Od P。

And this is the new P。要 p ok。We can kind of a hard codely test。

 hard codeedly nice test if in the x and or y and all all the x's。

If this guy is is the one side of the X guy。And this guy， I'm sorry， up the white wall。

 let's call you that。And this guy is on the other side of the wide wall。Correct。I think so。

Or maybe we can simplifyify that。Maybe we can seem to have this guy too。

If we test the wall individually。We just like。If。Let's say the new P P do't。hyhy。If why。Yeah。

 this is the sweep we were talking about earlier when you asked about。Tunly。

That's kind of the way we're going to do sweep with the direction。

So we're kind of doing a fixed sweep for now。Just because it's not very clear to me how to do a more robust thing。

呃。不 yeah。I think we're going to hack that now and then we can clean it up as we see it working。



![](img/2c5915bbf2791187d13c00d769bdde9e_404.png)

Okay， so I going to have the old ball pe。Okay， so let's do old ball feet。Eals love。

Here I'm going to pass the old ball P2。我的毛。包包笔。Now， if we are inside the block。



![](img/2c5915bbf2791187d13c00d769bdde9e_406.png)

I'm going to test for now I'm just going to test this guy and then we can test these guys later on。啊。



![](img/2c5915bbf2791187d13c00d769bdde9e_408.png)

Okay。And that's assuming the blocks are static。

![](img/2c5915bbf2791187d13c00d769bdde9e_410.png)

Wish they may not be。O。If the x is less than。

![](img/2c5915bbf2791187d13c00d769bdde9e_412.png)

The the Ox。Old， I'm sorry， old。包屁的外。The y is less than， let's say。The block。PY minus。The hand。

Block have size， by。

![](img/2c5915bbf2791187d13c00d769bdde9e_414.png)

So if this guy was in here， we already know。

![](img/2c5915bbf2791187d13c00d769bdde9e_416.png)

For a fact。

![](img/2c5915bbf2791187d13c00d769bdde9e_418.png)

That。We can reflect a why。Because it entered this， you may have entered。Like this， in this case。

 we should reflect both。

![](img/2c5915bbf2791187d13c00d769bdde9e_420.png)

But in this case， we can pretty safely。Reflect it。So yes， there's going to be。

Since this is a global for now， we can just use it， but later then I do it more。I like， yeah。

 these problems are pretty interesting， that's why I don't like to like search a tutorial and pretty much copy that。



![](img/2c5915bbf2791187d13c00d769bdde9e_422.png)

Because you do have to think about all these cases。And it's very iterative。

 so we're going to try this first version。And then start doing building on top of that they do all of for us they seem seem by first。

 but then they are way much tricky yes and。People usually like say， okay。

 just use a library for that and they kind of miss the point， I think。

The point is to kind of develop the skill to solve these kinds of problems and they are everywhere。

 even though they may not as be as math headty as this one is and in terms of hacking a solution together。



![](img/2c5915bbf2791187d13c00d769bdde9e_424.png)

But the development that you think about these problems are exactly how how to get smarter。 I think。

 Yeah， so let's totally do that。 So I'm going to。😊。



![](img/2c5915bbf2791187d13c00d769bdde9e_426.png)

If if we collide， we're going to revert the DPY。

![](img/2c5915bbf2791187d13c00d769bdde9e_428.png)

Okay， so let's see if this is true。

![](img/2c5915bbf2791187d13c00d769bdde9e_430.png)

ok。Okay， so we got what we needed。呃。And yeah， that's pretty cool。 Okay。

 now let's see if we enter from the side。Okay， now it should be wrong， yes， it's wrong。



![](img/2c5915bbf2791187d13c00d769bdde9e_432.png)

But now we can test the other guys。Right。If。

![](img/2c5915bbf2791187d13c00d769bdde9e_434.png)

The old ball key。Okay， let me draw。 Okay， yeah， this case， if the old。If you O P。



![](img/2c5915bbf2791187d13c00d769bdde9e_436.png)

X was less than this guy。See if the old is less than this guy， I described revert。If the old。Ball P。

 X， it was greater。

![](img/2c5915bbf2791187d13c00d769bdde9e_438.png)

Then this guy， we just。This guy。

![](img/2c5915bbf2791187d13c00d769bdde9e_440.png)

Also revert。The the X。Correct。And I've going to do the same thing for a while。So yeah。

 this is kind of a fake sweep。We should probably learn more about Fi all do that and maybe in the next stream we can clean this up。

 I'm going to comment that， but I think we are going to be able to progress at least。

Which is always good， that's the whole point。

![](img/2c5915bbf2791187d13c00d769bdde9e_442.png)

O。Let's see what we have。ok。That was correct。 Okay， that was nice。LetSee， I think we are 100%。

In terms of a basic collision detection， okay， we're not 100%。Wow。That was pretty bad。

And know what I think happened。It collided with more than one block wow Wow， yeah。

 that was pretty bad。

![](img/2c5915bbf2791187d13c00d769bdde9e_444.png)

Yeah。😊，If the ball X was greater than a block because it happened at the bottom of the block。

 I don't think so。Let me draw and see if。If the ball X was greater than the block X。



![](img/2c5915bbf2791187d13c00d769bdde9e_446.png)

In this case， it's the block X plus the half block X， right， Yeah， so if the old block X was greater。



![](img/2c5915bbf2791187d13c00d769bdde9e_448.png)

Then this guy。 So in this case。He was here in the beginning of the frame somewhere here。

So you indicate， even if you did that。Well， I'm not sure in this case， maybe yeah。

 he should just reflect on why。Yeah， when you get from the bottom right now like this。😊，Yes。

 in this case， it would be wrong。You are correct， Morfius。呃。But。In this case。

 should he always reflect like this？And can we get the same problem like this。

 we can probably do that like this， right？Yeah， I think we we're going to have to do some vector May stuff。

Like。We can probably know。Like this， well we like we have these we can have this vector。Right。

But that doesn't tell as much。Or design it？嗯。You will need to draw a line between the old。Yeah。

 we could do that。And then check where your list about yeah。

 okay so that's the full sweep you're talking about so yeah。

 I think we're going to have to do the full sweep。And that's going to be cool because you're going to learn more。

 I guess， and it's going to be a little bit tricky。But I think you are correct。

 We are going to do a full sweep， So let me just explain。What I mean by that。So。If we have this guy。

And expect and then check right in yeah exactly， so morphphus， you got the point。

 the point is we do have to draw this line。From the old and。And we're going to check this guide。

And then this guy， we can't actually stop him。And then reflect。

The position based off the rest of this guy。Because。We'll know at this point。Correct。

 so the idea is kind of make a lu。Lv is a linear interpolate。啊。Okay， so the lor is。

 let's say we have this guy at the beginning， that's called it A and this guy at the end。

 let's called it B。Lb takes A B and a T， which where do you want to go if we go zero。

 we start at the A if we go1， we go to the B， okay？Okay。But what we want is the other way around。

 we don't have the tea。

![](img/2c5915bbf2791187d13c00d769bdde9e_450.png)

Correct， and we want to find that out。Okay， so this is turning。

We're starting to get a light at the end of the tunnel， right so the lub。Function。Is1 minus T8？

Plus B plus T B， right， So the idea is if we pass 0， we're gonna be 1 minus01，1， a plus 0 times B 0。

 So it're going get a。 If we pass one is's going to be 1 minus10， we're going to get4 B So this the。



![](img/2c5915bbf2791187d13c00d769bdde9e_452.png)

But we want to do the opposite of the lurk， you know。

 to get the sweep because we want to know this guy anyway。We should。 we should have the。The target。

 let's say equals C。

![](img/2c5915bbf2791187d13c00d769bdde9e_454.png)

Right。Okay， what we want to do， what we want to do we have this guy， we have these guys。



![](img/2c5915bbf2791187d13c00d769bdde9e_456.png)

Do we have this guy？We do， right？I'm not sure。

![](img/2c5915bbf2791187d13c00d769bdde9e_458.png)

Let's just try to isolate T。嗯。Let's do that。Okay， so。It's going to be a。Oh my God。

 I didn't think I to remember how to do that。1。us8 times a is going to be a。Minus T。

I think that's correct。Plus T TV， let's just check if it's 0。We should have a minus0 a， so yeah。

If we have one should a mass be spread？Well， see my high school math not actually like even before high school。

 I'm not sure。Okay， so this is。It's correct。And then if you isolate the。Look me minus T A plus T B。

Equals a minus a。RightAnd then we can take that。You can write it like this looking like TB。Mineus D。

Because minus a。You can do。子。Times。你名死。Correct。😊，な。T。😊，Equals。唔 minus四。Divided by。D message。

That looks a bit's weird。I think， yeah， we should really use the C。 It's going to be C minus A。Cma a。

Okay， now it looks kind of a little bit more correct。嗯。So the idea is。



![](img/2c5915bbf2791187d13c00d769bdde9e_460.png)

Given A a the and a C， which I'm not sure we're going to easily get。

We will be able to get the T and the T is how much we should move in this direction。

how much to we remove from this reaction？To reach this guy。嗯。At this point。

 I'm thinking about cheating and kind of a searching because we've got to this point。

Wwhich is a lot of progress and I could cheat my code base or I could cheat on Google。

 I don't know which one's worse for our learning experience or I could just keep doing that because I think we got to an interesting point。

But I think we're missing something。 I'm not sure， I mean， in the C， how how would you get the C？



![](img/2c5915bbf2791187d13c00d769bdde9e_462.png)

Yeah， I'm going to cheat。In my codeb for now。I see。 I have this game。And see， we have。

All these crazy collision detections。Line tray， Yeah， it's called line trace。呃。

Line trace versus AABB。So we have start and the end。



![](img/2c5915bbf2791187d13c00d769bdde9e_464.png)

Start at the end， So no see。And we have the average P in the object size。Okay。



![](img/2c5915bbf2791187d13c00d769bdde9e_466.png)

C。

![](img/2c5915bbf2791187d13c00d769bdde9e_468.png)

A point or the entire line。 Yeah， the C， we're going to get C， which is this point。

When we solve this function， right， so that's the thing。



![](img/2c5915bbf2791187d13c00d769bdde9e_470.png)

If we get the T， which is what we need。

![](img/2c5915bbf2791187d13c00d769bdde9e_472.png)

We will be able to find in what point he's intersecting。And at that point。

 we'll be able to know if it's this guy or the other way。

 so see in this case make it pretty clear so。

![](img/2c5915bbf2791187d13c00d769bdde9e_474.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_475.png)

The delta here is the line okay， so first thing I'm going to draw that code example。

Because I already research that and it's not very funny。

 it apparently didn't stick my head in terms of a math stuff。But yeah。

 I do have to flex those mathth muscles a little bit more。So we have this guy， object B。

The numberumb size。And we have a。And B。And in this case。

 we might as well draw B out here because it'll work， that's great。

That was a point that we were talking later， so we can do the ball really。

 really fast and very small blocks and that could be fun。They're small blocks or not。

 because they're going to kick all over the place， so notes。Okay。😊，So we first find out the deelta。

 which is this line。Okay， I'm going to call that deep。呃。Okay， in this case， it separates。Yeah。😊。

Because the object might be going exactly sideways or exactly upwards and downwards， in this case。

 we can divide by zero。We have to change that and the Tx and TY。Which is what we find here。

 Tx and TY。Is going to be。Object Px。This guy。Ninus StarX。Okay， let me find out this guy。

Divided by deelta x。So c。Oject， yeah， we almost got it right。We almost got it right。

 so this is the function that we wrote here on the stream and the divided by B minus a is correct。

The B minus a is here， the n minus the start， that's delta。So that's correct。And minus a。

 that's also correct。But the C part to I wrong， apparently， is the object P。Minus8。

Does that make sense？The object Px。呃。Okay， we're testing。 We're testing the X。So we want to know。

 yeah， we want to know in x how much we can move in this case， we can move up to here。

 let's say this is 04。0。5。Yeah， looks more like one4。Minus 1。4， right， nots 。啊。So the point4 is。😡。

The object P。Which is this gun， I saved this gun。Mineus the start x， which is going to give us。

This guy， okay， now it makes sense。Okay， now it makes sense。 We are correct saying that C， which is。

啊。Which is this point。Right here。See， this is where we， I'm sorry， is this this point。Yeah。

 we are correct， let's just try to understand that a little bit more。At this point。嗯。

I think I'm going to do that one B just to be clear。Yeah， we're going have a tough timing 2D。

 making them 1 D， we're going to have tough timing 3D， make a 2D。That's kind of how okay。

Let's say we want to go first from here to here。ok。😊，ok。The object P in this case， why？

Let's say this guy's Tam， Tam。This guy， let's say it's eight and this guy let's say it's。Okay。

 what we want to do。Is to know at which point？Do we hit this guy？See， that's the correct question。

At which point to we reach this guy and。Yeah， and this guy。Is the C。In this equation。Yes。

 that's what Hunt correct。 Okay， so after。Thinking about that for some time。

 I don't know how much time， but for some time。I think we got to a understanding of the problem。

We are doing a sweep。Which means that we're going to do we're going to ask at which point。

Do we collide with that line？If， for some reason， the point in this case。Is past the point？

Now we want to go。We don't collide。If。for。You know， some reason。The point is after the point。Like。

 let's say this is 11。

![](img/2c5915bbf2791187d13c00d769bdde9e_477.png)

At this point， we know you collide with this axisxes。

 that's why in this other code example we split the axes。



![](img/2c5915bbf2791187d13c00d769bdde9e_479.png)

So that makes sense。So， yeah， I think。Understanding more about it now。Actually， I'm sure about that。

 but I'm think understand enough。Then I can confident write the code。Okay。

 so what what we're going to get。Is。A。What youre going to get is a value。

That's going to tell us how much we have to move。In this scale， which is A I'm sorry， this scale。

 which is A B。To reach C in this case， you're going to tell is like 0。8， for instance。

 which is this guy。And in the other case， let me just， in this case， it will tell us one point。

I know three。And if it's greater than one means that we passed， we didn't collide if it's negative。

 we didn't collide either because it was on the other side， so I think now we are confident enough。



![](img/2c5915bbf2791187d13c00d769bdde9e_481.png)

To write that。Okay。So let's do this Do you guys understood the basic idea of the sweep we're going to do and how's going to help us？



![](img/2c5915bbf2791187d13c00d769bdde9e_483.png)

と？

![](img/2c5915bbf2791187d13c00d769bdde9e_485.png)

Yeah， okay。Okay， so let's go collision。What I'm going to do here is a。And， I don't know。

 how do I call it， I'm going to try this like a line trace。That's a pretty bad name。

 line trace versuss。Line。

![](img/2c5915bbf2791187d13c00d769bdde9e_487.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_488.png)

Maybe sweep for yeah， sweep。For AABB。That makes sense。So we're gonna have a problem which will fix。

 Yeah， not really， but let's see。 Okay， yeah， we're gonna have a problem， but we'll。呃。

So the suite is going to return an F 32。

![](img/2c5915bbf2791187d13c00d769bdde9e_490.png)

That I'm going to say how much in this line removed okay？



![](img/2c5915bbf2791187d13c00d769bdde9e_492.png)

So let's do this。The V2P。Which is this guy， let's say start， yes， start。Me too。

And then we're going to do like。Object。T。An object。



![](img/2c5915bbf2791187d13c00d769bdde9e_494.png)

Yeah， the problem， as you can see， is that we're only testing a point versus a。



![](img/2c5915bbf2791187d13c00d769bdde9e_496.png)

An object。

![](img/2c5915bbf2791187d13c00d769bdde9e_498.png)

So we're not really testing for the bound of the ball。



![](img/2c5915bbf2791187d13c00d769bdde9e_500.png)

But we can easily do， we can easily fix that， but we're going to do that later on。First of all。

 let's try to do this version。So start end IP， a have size。呃。If first of all， we have the difference。

 the difference is going to be the subtraction。

![](img/2c5915bbf2791187d13c00d769bdde9e_502.png)

Of the end and the start。So this guy gives us this guy， so in this case that we're doing 2D。1D。

 I'm sorry， it's going to give us minus one。Correct。Correct。



![](img/2c5915bbf2791187d13c00d769bdde9e_504.png)

And then we're going to do and the difference is this guy。And you can see here， so the C。

It's going to be the start。Correct。Yeah， so that's new for why。So the start dot why。

Let's to see minus。

![](img/2c5915bbf2791187d13c00d769bdde9e_506.png)

I'm sorry， object D five， objectly， we're talking about the red line。

 the object why which is 10 in this case。My minus。A， which is the start？



![](img/2c5915bbf2791187d13c00d769bdde9e_508.png)

Start that X divided by。A minus B， it's the di。D段。We could make that explicit。



![](img/2c5915bbf2791187d13c00d769bdde9e_510.png)

I think I would do that for now。Okay， so。

![](img/2c5915bbf2791187d13c00d769bdde9e_512.png)

This supposedly gives us。The T for y。

![](img/2c5915bbf2791187d13c00d769bdde9e_514.png)

Okay，Let's see。See， the problem is math， there's a missing formula here。

Peoples more than us have already thought about that for a long time and got to that。

 all I have to do is understand， really understand so we can use that。In our game。

 I think that's more important than try to come up with that。

 although we didn't manage to do that bit by ourselves。Okay， so what you're doing in this case。

 object Y 10， 10。Minus start y seven。Divided by。Eight minus1。In this case。We have three。Yeah。

 that's precisely correct。And three is greater than one so we're not colliding。Perfect， actually。

In this case。Let's say this is tro。The end is 12， so to be three divided by。1来份。No， I'm sorry。

 it's my second。So。Yeah， no， it's 12，12 minus。12l minus7。Which is five。In this case。

 it's going to be。0ero。6。So it's less than one， so we are colliding， that's it。That's it and。

In this case， let's say， in this case， which was the problem with the first version of it did。

We will not have this problem because we would first know that。啊。We collide in X， correct， let's see。

 like this。呃。

![](img/2c5915bbf2791187d13c00d769bdde9e_516.png)

Yeah， this part also comes into play， right？

![](img/2c5915bbf2791187d13c00d769bdde9e_518.png)

First， we have to know we are not in these bounds。

![](img/2c5915bbf2791187d13c00d769bdde9e_520.png)

No， I'm not sure。 Let's try to limit this part only。 Okay， so if T， Y is。

greater two or equal to zero。If this is zero is going to be a problem。

 so let's not try to think about that for now。You're going to try and divide value your and。七。😊。

Y is less than or equal to one？In this case， we do collide。

 so for now all' have to do all I'll do is do a。Return。A truerue means I do collectllide and。Cause。

P if zero these guys all， finally。programming and enough and not thinking would be thinking for too long。

 I like to think that much。啊。So I'm going to do a sweep。For an A A BB and if。We do sweep。

 in this case， the sweep is only this part right telling only the x the partdon the y。

So I'm going to do the block。Luck皮。Bock have size。薄皮。I'm sorry。毛皮衣。Well。

 and we should get a bold desired pe。Desired。Yeah。😊，Okay， if we do that。It's this guy。

Then we can reflect the X。

![](img/2c5915bbf2791187d13c00d769bdde9e_522.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_523.png)

I'm sorry， the why。呃。Okay， now I have to。Get these guys。So。Instead of saving the old ball pee。

 I'm going to do like a ball。Desired P。And the desired key is going to be this。Makes sense。

And I'm going to test the player。Where there's like ball P in this code。We going do ball。

Desired Pete。O。Okay， well no， actually， they don't think it's okay。嗯。Object。

This is the object P object。P的来。More okay。So we don't need the ball half size for now。

All we need is the ballll。Desired。Os Va p。Pa all desired。Okay。

We should probably step into the debugger just to make sure。



![](img/2c5915bbf2791187d13c00d769bdde9e_525.png)

But I just want to see visually what happens。The ball is stuck。



![](img/2c5915bbf2791187d13c00d769bdde9e_527.png)

Oh， because we don't yeah， we have to send that to the desired P。B皮。Equs。Ba decided。



![](img/2c5915bbf2791187d13c00d769bdde9e_529.png)

Yeah， it's not we're just figuring out what to do， I'm sorry， that shouldn't work really。

Now this work。Oh， didn't work。

![](img/2c5915bbf2791187d13c00d769bdde9e_531.png)

Okay。呃。

![](img/2c5915bbf2791187d13c00d769bdde9e_533.png)

Let's try setting break points， it's going to be hard to catch that break point。



![](img/2c5915bbf2791187d13c00d769bdde9e_535.png)

Maybe we should do like。We should really cheat， we should do like， yeah。

I'm going to control the whole player。呃。Player P。Yes。And going do。Player why。

But if you don't mind equals。Well， I'm going to this again because it' just。



![](img/2c5915bbf2791187d13c00d769bdde9e_537.png)

So I can move the player around， okay， and then the ball is going to be static。



![](img/2c5915bbf2791187d13c00d769bdde9e_539.png)

冇的 p外。

![](img/2c5915bbf2791187d13c00d769bdde9e_541.png)

So I can test the lesion。Okay， so what we can do as just a starting point。

 we should have done that earlier， honestly。

![](img/2c5915bbf2791187d13c00d769bdde9e_543.png)

To get the more collision， we're going to do like is colliding。

And we're going to set that to every frame。好审。Yeah。Let me see that this colliding to false。

If we are colliding。Hes colliding to。And I'm going to draw the player in a different color。



![](img/2c5915bbf2791187d13c00d769bdde9e_545.png)

Yes。

![](img/2c5915bbf2791187d13c00d769bdde9e_547.png)

Okay that nothing。Else。

![](img/2c5915bbf2791187d13c00d769bdde9e_549.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_550.png)

student did nothing。It's colliding。Are we a lady？We were not climbing。BDP， yeah。

 this is starting to get really messy。I might have to go step way back。Well。

 just because it said we were almost done。We hit this big wall in the head。

And we probably have to take a couple steps back。To make sure that our collision system is okay。

 And that's the main point。 I think we can take away from this。Epiode。

 the basic gameplay and the collision system， and once we have a good collision system。

 we can pretty much easily do the rest。But so it's worth spending a time some time in this。So。Okay。

Yeah， because we do test if the boys， that's why we're not testing okay so I'm going to remove this guy。

 not the whole guy of this guy。

![](img/2c5915bbf2791187d13c00d769bdde9e_552.png)

Okay， so we weren into testing。

![](img/2c5915bbf2791187d13c00d769bdde9e_554.png)

Okay。That wasn't expected。Okay， let me just remove all these guys。



![](img/2c5915bbf2791187d13c00d769bdde9e_556.png)

Okay， that's the only thing we need。So this collision of tax system is working。Perfect。But。

AJssica I said it was working perfectly。It's not working perfectly。Oh， think Ill be did that。



![](img/2c5915bbf2791187d13c00d769bdde9e_558.png)

There's a problem in our A ABB versus A being in the X。Yes。



![](img/2c5915bbf2791187d13c00d769bdde9e_560.png)

1。😊，Oh， this may have caused so much problems。Okay。Okay。Okay。



![](img/2c5915bbf2791187d13c00d769bdde9e_562.png)

So now we have。The information that we are at least。You know， this may have caused more problems。

In fact。Now that I think about it。有。Forget about it and let's continue doing this week。



![](img/2c5915bbf2791187d13c00d769bdde9e_564.png)

Okay， so that's the first step we do。We know that we areciding。ok。😊，Okay。

 now the other question is if we were not gliding last train。What side did we collide with？Okay。

 which is basically the suite。

![](img/2c5915bbf2791187d13c00d769bdde9e_566.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_567.png)

So how are we going to do that？呃。Yeah。Okay， in this case。The player is moving。



![](img/2c5915bbf2791187d13c00d769bdde9e_569.png)

So we're going to test the player desired to pe。And the ball pe。ok。😊，So。The player has a desired P。

This is getting really mess， but we're going to delete everything later， so we're just experimenting。

 we're learning more less the point。So this player P。I's actually a player designed player。Thisあ。

Okay， I don't remember why we did this in know player acting。I just create that at the Dp。Yeah。

For now， let's just ignore that。Okay， so the player IGP is this guy。可以。😊，O。



![](img/2c5915bbf2791187d13c00d769bdde9e_571.png)

That's the play desired our key， so if we play， nothing going' we won't be able to control the play anymore。



![](img/2c5915bbf2791187d13c00d769bdde9e_573.png)

Okay， the thing is we're going to try to collide with a ball and got a P from that。ok。😊。

So I'm going to do this in line then we can extract a function out of it。

 it's going to be more organized。So V2 start。the yeah， I'm going to calculate basically this。

So the objects P now is the ball。He。That X。The start pe is the play of pe。

 and I want to go to the desired。AP P is。睇晒。Can内にて。Okay， this。If these are equal。

 I'm going to divide by zero， which is not good。I think it's not crash。Vvoid。Now this is。

 I'm going to set this coiding here to true。And if it's not colliding。I'm gonna。

Pigher P equals higher。

![](img/2c5915bbf2791187d13c00d769bdde9e_575.png)

Thisir。Okay。So yeah， I think we are correct，Because we are only testing why， remember that。

So the point is。Yeah。😊，C。😊，Yes， this is working。Okay。

But it's not perfect because we didn't take into account。



![](img/2c5915bbf2791187d13c00d769bdde9e_577.png)

The ball。The ball size here， so it's going to be ball。呃。This。P the ball minus。The ball， why。啊冇。Size。

 why。Minus the player have size y。

![](img/2c5915bbf2791187d13c00d769bdde9e_579.png)

And now I think we're going to have a more interesting result， okay。

Now this is interesting because we know we collided with this part and we can really do like see how we stop immediately the collision。



![](img/2c5915bbf2791187d13c00d769bdde9e_581.png)

We can go all the way。To the。To the edge， we could do like。This is the advantage they desire to pee。

D why。Going to be alert。Lert。Of。Player。P。TY and player desired P。

Let's do a little really quickly here in math， we already discussed that。Camp what I'm doing inline。

F 32。Lb。It's going to take a。直知。で品？And going to return1 minus T。系四。Plus7。Ch。From V yeah， play。

 we're going to do just a y。

![](img/2c5915bbf2791187d13c00d769bdde9e_583.png)

Okay， now we should have the nice effect。Yes。It's pretty cool。Bd we stuck。



![](img/2c5915bbf2791187d13c00d769bdde9e_585.png)

So。Yeah。

![](img/2c5915bbf2791187d13c00d769bdde9e_587.png)

But I hope you saw it even if I was super fast。I didn't get stuck with the mouse over here。



![](img/2c5915bbf2791187d13c00d769bdde9e_589.png)

With us with space in between and we know how much the space is， it's one minus T y so we can easily。

Meg， and let can just turn the light on here starting to get dark。呃。Opening the window。

 we can easily get the difference in that and advance that to the outside that's pretty cool that's one thing we discussed here in the beginning。

Okay以。😊，Okay， so what else？Do we， do we need to do Yeah。

 I'm not sure if we were supposed to get stuck or not。Yeah， I'm going to debug that。

The games not open， so I'm going to。Enter the simulateim game here。しくした。O。And yeah。

 I'm going to put a break point。Here， when I'm stuck， okay， now it's a good ten。

Would that need to be forward。Okay。So the ball。P 40。They have signs。 Okay， the player P。It37。

 the desired P is 2。Does that make sense？I guess that makes sense。Now I'm trying to go down okay。

And the player peak is。诶。Yeah， minus 34。So I think the T is going to be negative， minus zero。Okay。

 that was unexpected， I thought it was going to be negative。See why it was minus0。呃。This whole guy。

Was this， okay， and a player P。Was exactly zero。So yeah， it's going to be zero divided by。Yeah。

 maybe we should ignore zero， I think that's the point yeah。And should we ignore order one as well？

Probably。1 is like。Now one is actually touching， so I'm not going to ignore one。

 I'm going to ignore ignore zero。

![](img/2c5915bbf2791187d13c00d769bdde9e_591.png)

Okay now we don't work at all。If it's greater than zero。And less than or equal to one。

We only changed this。Yeah， we do， we do get a couple of。I've heard read Frank。

 I don't know if you guys could see that。嗯。Yeah， I'm going to put a break point here。Yeah， okay。

 so apparently， let me see。Yes， so we did hit the breakpoint correctly。And the TY is。0。8。

So we move the desired P to 0。8 to the equivalent。Okay。

 that looks good and guys have the be to desired Pete。And the next frame。We don't hit。

Because it's  zero。I'm confused。な。So at this point we're zero。



![](img/2c5915bbf2791187d13c00d769bdde9e_593.png)

I think if this guy is zero， we ignore this all together。Yeah， maybe。

 maybe an interesting point because we can't divide by zero， so this guy， I'm going to call that div。

This guy is 0。But this should only be zero if for not moving。Not sure how that changes anything。Yeah。

 that doesn't really change it。查一下。Yeah。Okay， so this is working nicely， I think。

I think it's going to be hard to make it stop。Like maybe maybe I should just test like this if。

If we are colliding。Yeah， that sounds good if we are colliding。

Okay I'm going to use the desired player desired P。They have signs if we are colliding。We then check。

Where we are colliding to and that， I think makes more sense。



![](img/2c5915bbf2791187d13c00d769bdde9e_595.png)

眼。I think we are getting somewhere， okay， so it says we are colliding。



![](img/2c5915bbf2791187d13c00d769bdde9e_597.png)

If we are colliding players every repeat。

![](img/2c5915bbf2791187d13c00d769bdde9e_599.png)

毛屁。Yeah， this goes。Okay。

![](img/2c5915bbf2791187d13c00d769bdde9e_601.png)

Now。The is colliding part goes out here。

![](img/2c5915bbf2791187d13c00d769bdde9e_603.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_604.png)

Right now we should stop the movement。

![](img/2c5915bbf2791187d13c00d769bdde9e_606.png)

Okay。Yeah， the player P ends up being okay， reasonable。But in the next frame， let's see player P， 73。

75。Every three minus 102 yeah because I over the miles。It'd be hard to describe。ok。

It's funny thing that works on both sides。Oh yeah， yeah。Because。Yeah。

It doesn't really matter if it's positive or negative， that's pretty cool。Yeah。



![](img/2c5915bbf2791187d13c00d769bdde9e_608.png)

No， I'm getting wrong， we changed the color to down here。Okay， so we are getting progress。But。呃。

Not much， though。So if we collide。You're going to see how much we can go， right？

It had the plate desired。If you write to this guy。

![](img/2c5915bbf2791187d13c00d769bdde9e_610.png)

Maybe now we should be like this。Okay。Yes， no I think this is correct。Or more correct， I guess。Yes。

 okay。Okay， so that was the missing ingredient， it doesn't work in the other way yet because yeah。

This works， but this doesn't yet。Nice， oh， this is pretty cool。 This is pretty cool。

 Now I shouldn't be able to go through。

![](img/2c5915bbf2791187d13c00d769bdde9e_612.png)

Correct。I shouldn't be able。If it's more than zero。AndThat when we are colliding。



![](img/2c5915bbf2791187d13c00d769bdde9e_614.png)

I don't think this is correct because right here， it's like way more。



![](img/2c5915bbf2791187d13c00d769bdde9e_616.png)

Then 0， like。see。😊。

![](img/2c5915bbf2791187d13c00d769bdde9e_618.png)

Let's draw more stuff Oh， I think we are getting there slowly， but we are。Okay。

Let's say we were here and now we are here。Oh， because we failed this。



![](img/2c5915bbf2791187d13c00d769bdde9e_620.png)

Yeah， I really don't like the idea of having to test this first。

But then it can't be zero here for some reason， I have to understand that。



![](img/2c5915bbf2791187d13c00d769bdde9e_622.png)

Yeah， oh， yeah， we can't go back。Because we are colliding， but we want to go down。Like can't go down？

Oh， because these guy， yeah， I company like this guy is going to sum up to zero。

It's going to be zero divided by whatever。Now I want to find out by myself。



![](img/2c5915bbf2791187d13c00d769bdde9e_624.png)

嗯。This， if this guy is zero。What does that mean， that means that we are exactly on the point？

And if we aren't， well， this shouldn't be equal to zero。And this shouldn be go to one。



![](img/2c5915bbf2791187d13c00d769bdde9e_626.png)

If we are on the point we're not colliding。

![](img/2c5915bbf2791187d13c00d769bdde9e_628.png)

嗯。Yeah， well， now I'm stuck again。

![](img/2c5915bbf2791187d13c00d769bdde9e_630.png)

Now， I think this is the more correct behavior。Yeah， I might have I might。

I might go and learn about it， yeah， let's do a little bit of learning。



![](img/2c5915bbf2791187d13c00d769bdde9e_632.png)

y。I'm going to go to the master。I don't remember what this is called as say intersection。

Line intersection collisions。Approachs problems rain intersections， raid plane intersection。

 combining the intersectional a point。Our reflect yeah， that's pretty much it。

Interssecting array with a rectangle。

![](img/2c5915bbf2791187d13c00d769bdde9e_634.png)

This is it。Let me see if you guys can hear that。I can't hear that。So here was our equation。

 our T result meaning the T along that the percentage along the player delta vector。

 that we would have to go to intersect a particular wall ex coordinate at an next coordinate。

So a wall in an ex coordinate， remember， is a vertical wall， right？

I think that's what we've got wrong This is the。No， no player repeat。



![](img/2c5915bbf2791187d13c00d769bdde9e_636.png)

Yeah。I think I already saw the problem。This guy is the desired。This guy。



![](img/2c5915bbf2791187d13c00d769bdde9e_638.png)

And not。第压的 one字。I'm sorry。Actually， I was wrong。How was that。



![](img/2c5915bbf2791187d13c00d769bdde9e_640.png)

Yeah， no， we do have to read things， so we set the desire to deliver。Yeah， let's continue， but yeah。



![](img/2c5915bbf2791187d13c00d769bdde9e_642.png)

So at the X coordinate of the wall we care about right we want to subtract whatever the player's ex coordinate is and then we want to divide by whatever the delta X coordinate is。

 so the X offset that will give us the T at which we would arrive there we then want to check the back。

😡，Of that thing and in order to check the bounds of that thing we then have to figure out where the other component would be right so where would the y be right well we know where the y would be the y is just going to be that on that background so Whitney would have done you know one where started from it all did that somebody has been into the code there。

😡，I'm sure obviously it could not have how dare they those people will。All right。是。

So if it's in there， then this is actually valid and if it's valid。

 then what we want to do is check that team in， so we want to say if T is a closer collision。

 all we need to do， but there is a catchup。😡，If team Min is more than2 result。

Is greater than T result。Yeah， the team in his testing。The team I'm sorry， the team men。It's one。



![](img/2c5915bbf2791187d13c00d769bdde9e_644.png)

So if it's less than one， yeah。If it's less than one， maybe we don't need to test this。



![](img/2c5915bbf2791187d13c00d769bdde9e_646.png)

あ。Okay哦。Now that's weird。Okay。What。😮，Yeah， I think I can only go forward， yeah。ていました。See。Go forward。

No。I should probably have a way to print。Camel case， yeah。Yeah， I don't like it either。

 but I talked about it on the last stream， don't know if you remember what's missing here。

Does anyone remember what's missing？Okay， so we're not in good shape， it's true。

Just so we were all clear on it， so you'll notice that he is able to interpenetrate the wall now and that's because we're only checking his one base point right this is up and the moto works so you can see that we're going to do areas we can so we can either you fix all the rest of this stuff。

Okay， so this is the correct code。嗯。Tam men。Yeah， so the team means how much he wants to move。

 he wants to move by one。Right。And。If he can't move by one。He will move by whatever he can。

This test we don't care for now。Because were going to ignore so this is the test that we are doing。

 which is greater greater or equal to zero。And。In this case， one， yeah。

 one if one is greater to yeah， so in this case， it's doing less than or equal to one。

Same thing you are doing。Yeah， I think the problem is。No。I don't know what the problem is because。

The desired P guess this guy。So， even。Even if the game。Back to。I'm all to date。Yeah。

 I also have to to think。I think I'll stream tomorrow。Morning here。呃。About， I don't know。

 14 hours from now， 14， 15。16 hours from now， that's about it so you can calculate whatever time it is there。

And I had like 16。16een sounds like a decent time， yeah。For tomorrow， hopefully that's the plan。

 hopefully。啊。This will be working the collision detection。

So we can focus entirely on a gameplay and as you saw， the gameplay is not that difficult。

The problem are understanding the basic ancient materials。 So yeah thats。

What I hope to do in this next few hours， so maybe' is going to be like a failed and tried attempt of doing that。

 but yeah。Yes that's it， so thanks for coming， but hopefully for the guys who are still watching。

 we'll be able to understand this together we are getting close。



![](img/2c5915bbf2791187d13c00d769bdde9e_648.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_649.png)

Because。You know we came from like a no understanding at all to a pretty close understanding。

 the point is this is the old， this is the new， let's just imagine in one， this is the new。

 this is the desired， let's put it that way and then we have a problem here， a block here。可以。

We are trying to go。From this。To this， the question is， where should we stop？Correct。

As far as we calculated， everything was correct。

![](img/2c5915bbf2791187d13c00d769bdde9e_651.png)

So啊。At one point， we did get pretty close， right？So T， yeah， I think I me go back a little bit。



![](img/2c5915bbf2791187d13c00d769bdde9e_653.png)

Yeah。Go' going to go back to this point。Lrk。Yeah， done。



![](img/2c5915bbf2791187d13c00d769bdde9e_655.png)

O。So at this point， this is what we had， this is what we wanted， but it couldn't go back。So this is。

Almost correct。Almost。

![](img/2c5915bbf2791187d13c00d769bdde9e_657.png)

Why can't you go banks because of this zero？That's what we realized is because。呃We are。Yeah。😊。

Let's say that we are， this is the ball。This is our point。 We are exactly here。

You're trying to go out。And this zero means if we aren't exactly here。We are collide。Okay。



![](img/2c5915bbf2791187d13c00d769bdde9e_659.png)

But if we don't test this zero。We go straight through。Because see， we do have one collision。

 so I put a break point。If I put a breakpoint here， we will stop the breakpoint， but next frame。

I don't know if I'll be able to。do that in for a bit。



![](img/2c5915bbf2791187d13c00d769bdde9e_661.png)

Next frame。 Let's see。 I see。I'm still colliding。

![](img/2c5915bbf2791187d13c00d769bdde9e_663.png)

But。I think this is going to be yeah， this was zero。 Let's see why the desired P。Desirre P。Was 49。

 that's where I want to go。I am。At the 37。So the numbers look good， why， but why is this guy zero。

 so it's going to be 40 minus all that stuff minus 37？This， these guys。It're going to be 12。

So I think we have a problem with our operations， I suppose。So these guys are zero。Ball PO。

 because the same problem， we are exactly where the ball is。Yeah， so it's the same problem。

But since it's not zero or I'm sorry， since it is zero， we're going straight through。 So yeah。

 it doesn't solve the problem。 The problem is。

![](img/2c5915bbf2791187d13c00d769bdde9e_665.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_666.png)

呃。In this case。Where we are colliding and we want to go out。We shouldn't really。Test this guy。

 We could hard code it。

![](img/2c5915bbf2791187d13c00d769bdde9e_668.png)

Like。If well， let's calculate this guy， it's called it。呃，对见。If di is negative。Means that we are。

 yeah。Eith we are going the other way， we shouldn't。



![](img/2c5915bbf2791187d13c00d769bdde9e_670.png)

Really。呃。Block。Okay， I think we did the other way around。



![](img/2c5915bbf2791187d13c00d769bdde9e_672.png)

If。It's。Yeah， it's possible。 We're going upwards。 So if you are going upwards， we block， okay。😊。



![](img/2c5915bbf2791187d13c00d769bdde9e_674.png)

Yes。I think we finally understood it。This is， this is beautiful。All right。Yeah， this is pretty cool。

Yeah， and you have to test for the audit they make to the graph。Okay， and it's a perfect slide。Okay。

 this is what we want。But if we didn't want to block and we just wanted to check col。

We could just do this。And we had a overlap event， actually， we don't。Once that， I said。

 is calledll to true。

![](img/2c5915bbf2791187d13c00d769bdde9e_676.png)

嗯。哎呀。😊，I don't know， but in this case we're going to test this is what we want， we want to block。

 okay， yeah， we want to block。

![](img/2c5915bbf2791187d13c00d769bdde9e_678.png)

Oops we didn't block at that time， what did I do to not block？Maybe I started， yeah， maybe I started。

Peter， that's strist for。Yeah， I started hereing。Right。Okay， so I hope you guys。



![](img/2c5915bbf2791187d13c00d769bdde9e_680.png)

呃。You know， got something out of that because it took a while。But now we are at the heart of it。

So we have at the collision。Let me just。Have aulation。ABB versus ABB。Overlappping。

 let's put it that way， but we're not going to use that。😡，Its to say， overlap。

What we are going to do is a。A block。

![](img/2c5915bbf2791187d13c00d769bdde9e_682.png)

A block。And what do we want from the block？

![](img/2c5915bbf2791187d13c00d769bdde9e_684.png)

Well， let's go back to the original problem that we're trying to face， we have a block。

And we have the ball if the ball hit wants to go here。We want to put the ball here。And well。

 we can pretty much just deflect the ball。Yeah， I think can do that。



![](img/2c5915bbf2791187d13c00d769bdde9e_686.png)

Okay。So。Now we're going to do some serious cleanup guys。

 prepare for some serious compression of the code， you know。

 I actually going to go to the bathroom and get some more water。So I'll be back in a。

In like two minutes。Okay， I'll be back in two minutes with water code， not code。

 we're going to go after。We're going to clean this thing and now that we got the heart of it。

 which is this part。We will finally be able to create our easily use collision detection system。Okay。

 two minutes。こラと。他死。So the thing is。It takes a while to you know get the first time running。

 but once we have a good solid function， our next games will be a lot easier。

 I mean I could be cheating from the other game like I did a short amount of time there。呃。Yeah。😊，So。

😊，We work a lot once， so that's good about programming。呃。What I want to do。Now， actually。

Is to stuff out how I want to call。The things I want to call。

So I'm going to probably break the game completely。Just to。Just to get it working。

In terms of a structure， so this is what I want to do now we are capable of doing this and I'm going to copy this guy。

Which is what we managed to get to work。To get working over here。

And then we can start cleaning the leg gico okay。So the initialization is working great。😊。

The player for now， I don't know if you need a desire to pe。Yeah， I I think well do reside me。

For the player。And for the bulk。Okay， yeah。Now I think I can keep this for now。And maybe。

Maybe do more complete stuff later。给。😊，Because this was working pretty nicely， the problem was the。



![](img/2c5915bbf2791187d13c00d769bdde9e_688.png)

Because we always know that if we hit the ball， we're going to off the X axis we're going to bounce off the y axis。

 and we're going to add our x velocity to the balls。



![](img/2c5915bbf2791187d13c00d769bdde9e_690.png)

So。That's easy， the problem is the blocks。呃。Okay， its fine false。So this was working nicely。

Their' screen， okay， yes， this is what we're interested。So I can just go back to。



![](img/2c5915bbf2791187d13c00d769bdde9e_692.png)

To running， just make sure。

![](img/2c5915bbf2791187d13c00d769bdde9e_694.png)

Or not working。Because we also have to do player。P。😊，Equals desired。And for now， we're not colliding。

あ。I pleasure and desire。

![](img/2c5915bbf2791187d13c00d769bdde9e_696.png)

We're not colliding with the player， but later we can do a oh I have to do on for the。



![](img/2c5915bbf2791187d13c00d769bdde9e_698.png)

佢s在 here。一あ。Yeah do配 is I。Y X。He goes the sky。And player desired Pt my equal goes player Pt。Yeah。

 later you can block him in the wall and do some pretty pretty cool stuff。Compile。嗯。



![](img/2c5915bbf2791187d13c00d769bdde9e_700.png)

叫。Okay， so we're back to the point we were and now let's just make the ball fall。O。



![](img/2c5915bbf2791187d13c00d769bdde9e_702.png)

Now we want to collide with these guys。And we may change the ball position。Right。

 so this code that we。Took a while but got to create the collision code for this guy。1。😊。

I can just put a commentt here。 giantant comet this。Is the。宝。AB。We can remove。

 I think we can delete this function， this was like really bad。Yeah。😊，Okay。And this one。

 we just copy that sweep。Nice。We can detect like is colliding。It's better name。This client is true。

 A ABB。My call is flight。Okay。Okay， it's starting to get cleaner so we're going to do for the y。

 then the x and then what we didn't do， but it's pretty easy is that if we are colliding。

 we have to test the other bounds like we have to test。



![](img/2c5915bbf2791187d13c00d769bdde9e_704.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_705.png)

He isn't here。And this test is pretty much the same as this test。Okay， so if this and。です。

We should be good to go。But I have to rename all the that right， so this is not Ts IP。

 this is ball of this I。And its not K of， this is block。Okay， if。This is going to get confusing。Yeah。

The ball pe。Yeah， the ball is the block。Whatever I see ball， I'm going to change the block。

And then I'm going to do like this。Block have size。Okay。Yeah， and this guy。It's the。Are the block P。

Lock P， X。The blood cap signss。This is the。不は。Desired。This is the ball desire to pe。

Is it the desired？Well有。I think it doesn't matter really， because if we are like here， yeah。

 it's the desired。And if you do like a huge sweet no。This。Actually， this is problematic。

Because if you do like this sweep。呃。This guy。Yeah， this is going to enter here。

Let's imagining why so it's going to hit and say， okay， this is a problem。Okay， now I'm sorry。

 we are going to test where。If in this position， if it's quite， okay， now it makes sense。

So I'm going to get the。The desire， the target。X。Target X is going to be。Alert。Of the。Player。

 I'm sorry， we're doing the。薄皮。Yeah。Yeah， the ball pe。Dot X。This is the TY。Okay。

98 hands and the ball pe。包。Desired。P。Okay， very good。And that's the target X。The target X。

The target X just to make sure at this point， right？So I'm going to contact that in a way。I closed。

 This is。If。😊，The target X。X。Plus。The ball。Have size。Dt X， it's greater than。The block。

Block have size。Sorry， black。P dot X。And this is the block。P do x。This is the blood。Sence， okay。

Think we're getting somewhere。ううんうん playerピ啊。Yeah， now is that of a player？

We have block on sorry ball。Ball camera search。申请楚槽。Okay target X， we're going to create that there。

If you guys have any question about what were doing， be free to ask them。



![](img/2c5915bbf2791187d13c00d769bdde9e_707.png)

But we're making a breakout game like this。And what we were trying to do。

 we've been trying for the past hour or a half or so。Is。Make a collision with these guys。



![](img/2c5915bbf2791187d13c00d769bdde9e_709.png)

In a proper way， I think I commented out。I didn't。Oh。

 I don't automaticallyulate the player Dp anymore， okay， player。D皮。Maybe payer desired D。

Our last frames D DP。Maybe less frame D DT， so I'm going to do like player。DP equals。Player。皮。Right？

And do just the， just the X。It's going to be the player Px。不 desire。So now we should be able to put。



![](img/2c5915bbf2791187d13c00d769bdde9e_711.png)

Gett the ball moving in the X axis。I don't think we did。It。



![](img/2c5915bbf2791187d13c00d769bdde9e_713.png)

Oh， didn't。KP。W does that repeat p minus8 P， oh my god。This is just a small thing。

 we already did that just because。We're trying to solve the other problem。

But comment out so much stuff that we broke this， that's tick， right？嗯。Let's see。layer， let's see。

 the player moving。Like this， the Dp。Is that。No one minus the old one S， right？They desired。

PX minus pair P D X。Well。Let's see， why isn't that working？Let's see it starts off。Oh right。

 I don't think the pilot maintenance。Yeah。Just the。No， we still didn't work please。Yeah。

 I'm going to hard colddly change the value of like desired P。Just you get some。

Desirre P x then like to0。The player DPX， it's pretty huge。This apparently is correct。

If you go to the next frame。And get the value of player DPX or that year。This is correct。Oh。

 we forgot， yeah。We already talked about， we forgot to divide that by this。



![](img/2c5915bbf2791187d13c00d769bdde9e_715.png)

So that was a very small number， but now it correct。We already talked about that， but yeah， there go。

Okay。I don't think。It's as we expected。ItCertainty isn't working。But let's see。Yeah。

 it's certainly not working。

![](img/2c5915bbf2791187d13c00d769bdde9e_717.png)

It's just see what。Yeah， we can't agree with this guy。



![](img/2c5915bbf2791187d13c00d769bdde9e_719.png)

SeeOkay。Okay， we got some behavior that was weird。I'm not going to complain too much。



![](img/2c5915bbf2791187d13c00d769bdde9e_721.png)

I think we we we。Yeah， okay， no this is correct。But we also have to change the direction of the。

Of the ball Dp。Dot my。

![](img/2c5915bbf2791187d13c00d769bdde9e_723.png)

Okay。Yeah， because it was too， yeah， I think that was expected and correct behavior， honestly。Yeah。

 now it's stuck because it's between two guys。But a。Because we're not testing the X yet， let's see。

 oh， not working yet。And actually didn't。

![](img/2c5915bbf2791187d13c00d769bdde9e_725.png)

Didn't change。啊。你宝DP。

![](img/2c5915bbf2791187d13c00d769bdde9e_727.png)

You put a break point there。I should probably know doing more。A stronger。Okay。Yeah。

 so we collided with a block。And we are going up 30。 Now we're going down。Actually。

 it didn't change anything what？Were still believe。あ。Right， dirty。Why is that？Okay， yeah， sorry。

 I think someone caught that probably。

![](img/2c5915bbf2791187d13c00d769bdde9e_729.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_730.png)

-1。Multiplyed by one doesn't solve our problem。Actually， does nothing。Okay。Okay， now we're talking。

 yes。Okay。Yes。Okay， now I think we're going to work。 Wow， what was that， let's try to win， Oh。

 I did win。Y， I lost。

![](img/2c5915bbf2791187d13c00d769bdde9e_732.png)

Okayケ。So this now is way better。So this is trying to move the ball。Yeah。

 we can probably start doing a compression on this。But。What we are going to do is。谁圈进去。Why to this？

Change x to y and change this to x。De red definitionfinition。



![](img/2c5915bbf2791187d13c00d769bdde9e_734.png)

Okay。Let's see， how's that working？是。Wow， I really suck。I would have to fix these controls， okay。

 let's see。Okay。Okay。Let's see what's going to do。Okay， nice collision there。 Let's see this side。

 Okay， this side didn't work。Yeah， I also think top isn't going to work。



![](img/2c5915bbf2791187d13c00d769bdde9e_736.png)

うん。I think this is supposed to work。Oh， definitely if di is greater than zero。😊。

We should just check if if。It's not zero yet。

![](img/2c5915bbf2791187d13c00d769bdde9e_738.png)

Let's see this yeah， our failed。啊。Okay， what's that？Oh， that's not entirely bad。阿 mean。

This is not what we want。Okay， this is entirely bad。



![](img/2c5915bbf2791187d13c00d769bdde9e_740.png)

嗯。O。Yeah。The di means that it's not moving。Oh that axisxes。So in this case，'s not moving up。

She's not moving up。It's no problem with not testing to change the up directionion because it's not moving up。

Maybe it's because of the epsilon。Like it's very close to zero， but not actually zero。I don't know。

 that was weird。If we do like， if it's greater than zero。001。Or if if is less than 0。-0。Points0，0。

one。Yeah， let's try and do that。

![](img/2c5915bbf2791187d13c00d769bdde9e_742.png)

Yeah， it's still weird。Whats it doing？

![](img/2c5915bbf2791187d13c00d769bdde9e_744.png)

It is colliding though。So the problem is not it's that it's too specific。Just不在。These braces。



![](img/2c5915bbf2791187d13c00d769bdde9e_746.png)

Okay。That work， let's see。Yeah。Your mouse is good because of that you can really catch these guys。

 but it's hard to control this。

![](img/2c5915bbf2791187d13c00d769bdde9e_748.png)

呃。So we're failing this case。You know what I should do。

 I should probably go back to the other case right。Where the mouse was controlling。Oh。

 I can do the mass majority the ball。To， yeah。嗯。Yeah。I going to trying to fix that， okay。Diff。Yeah。

 the diff is the problem because that's the thing if it's going this way。

The dip is going to be let's say negative right， yeah，s exactly and we're testing if it's positive。

But I don't know why when a test was different than zero， it glitched out。

Let's just ignore this test and hope it doesn't explode。



![](img/2c5915bbf2791187d13c00d769bdde9e_750.png)

Just to see what。ごいな。Okay。C。😊，And why。We're not getting division division by zero， that's for sure。

Because it's moving like。

![](img/2c5915bbf2791187d13c00d769bdde9e_752.png)

This is really weird。If the di is greater than zero。If you don't test that。We get collision。

Even though we shouldn't。This is wrong。This is the。No， this is correct。Yeah。

 this is I kind of got confused for a moment。Yeah， it's weird sliding。

 even though he wants to go to the other side。Yeah， I should probably go to the do the other 10。

 just spending a long time with this， but I think we。



![](img/2c5915bbf2791187d13c00d769bdde9e_754.png)

I think I'm getting more and more of the problem。So I don't see that as a problem necessarily。Yeah。

 I'm learning a lot。Through all these weird physics stuff。That's just if this side is okay。

 maybe you can hack and do it like。The other side kind of a。Same way， but different。



![](img/2c5915bbf2791187d13c00d769bdde9e_756.png)

Yeah， let's try and do that。This works for one side。We started this。Yeah。

 maybe they'll be the solution。What I'll do is if di is less than zero。Do this。See， this。

 the only difference would be al testing。If this was greater than zero or less than zero。

 which is the same as not zero。So I don't know if this works， I don't know why。

But I don't know why it wouldn't work either。

![](img/2c5915bbf2791187d13c00d769bdde9e_758.png)

We can go step by step。Yeah。Because I think that's the only， I know。Let's see sign depend yeah，Oh。

 because it's doing both of them。I guess。Yeah， maybe it's because it's doing both。

I just want to see if number I think is going to be the same thing。What it was that。



![](img/2c5915bbf2791187d13c00d769bdde9e_760.png)

Okay let's see。Yeah， it went straight through。Didn't work at all。I think I'm going to draw again。

 let's see。Okay， so this is working。This is not working， okay。



![](img/2c5915bbf2791187d13c00d769bdde9e_762.png)

Yeah。Let's see。Why this works first， but we know how it works， but let's just make true。

Let's do some values， Okay， let's say x 10，15。20。Okay， easy enough。The di。This temp。

Which is this minus this。It is where it is zero。Yeah， oh， this is a problem。

 but we're trying to understand that despite that。We're going to do block。This is the block 20。

20 yeah， we do all these minus to get this point， but let's assume。We already got that 20 minus。

Minus。10。We just can't。Divided by 10。This may be wrong。But we did pretty well， we did that correctly。

Hearing the。Sttch， yeah。Yeah， equals C。This is correct。C minus。see， minus a， so C this guy。Minus a。

 So it's 20 minus。I'm sorry， it's 15 minus 1。I know what I was thinking。15 minus10， it's five。

 so five， yeah， it's perfect five divided by 10， 0。5。 So we're going to go with this。

Now let's do the other way around。And we will kind of ignore this guy if we need to。So this is 20。

I'm sorry， it is 10。15，20。呃。The did。😊，Between the desired， which is 10， minus this guy is minus 10。

Oh， I think I'm gonna get the。The absolute value of this guy。Fretty sure。inus10， yeah， let's see。

 minus 10。Because we're actually getting the vector。We're not getting， you know， a， yeah， okay。

 that's see。Let's see， minus 10 is the di。Block， which is 15。15 minus。See。15。-20。Is it correct yet？

15， minus 20 minus5。No， you were direct， minus5 divided by minus 10 is 0。5。啊第什 value。Now。

I shouldn't really do that twice。But。是。Yeah， this thing。Now， let's see why。It doesn't work。



![](img/2c5915bbf2791187d13c00d769bdde9e_764.png)

Maybe we can test with one block， I think I'm going to do that。Yeah， this is really bad。



![](img/2c5915bbf2791187d13c00d769bdde9e_766.png)

It went straight through。Yeah， it was exactly like this case， 10 1520。We got。It a death。嗯。Okay。

 so 10。呃。10， 15， 20， we got minus 10。As the di。Actually， we didn't get minus 10。

I think that was the problem we got 10， didn't be。It's the end。Which is 10。Oh， no， yeah， 10 minus20。

マナテ。Minus10 is the di。This guy's 15，15 minus。20。Okay， so this is five， Yes， so I suppose。

This is the thing。I need the absolute value。Because we're talking about vector size here。

Ist that right or not？I don't think we're getting。Yeah， I don't think expect size per se。But it is。

Yes。In lineine F 32。3。A。If a。Lesson 0。

![](img/2c5915bbf2791187d13c00d769bdde9e_768.png)

感 say。Return a。

![](img/2c5915bbf2791187d13c00d769bdde9e_770.png)

我完了。Oh， this is this。It's not good。I can test this great than you。Who cares？



![](img/2c5915bbf2791187d13c00d769bdde9e_772.png)

Apparently， I think it's running twice。Why is it running twice， guys？No， that was very subtle。See。

As I said， too。Okay。

![](img/2c5915bbf2791187d13c00d769bdde9e_774.png)

嗯。That's a huge failure。Let me try to do one block。Okay， one block。



![](img/2c5915bbf2791187d13c00d769bdde9e_776.png)

I'm going to do one block。And I'm going to center the ball so that it collides directly。



![](img/2c5915bbf2791187d13c00d769bdde9e_778.png)

Okay， let's see。

![](img/2c5915bbf2791187d13c00d769bdde9e_780.png)

W P X。Okay。See， we saw the problem， it's easier not。



![](img/2c5915bbf2791187d13c00d769bdde9e_782.png)

Now， if we check out the。Absolute value。 That's， yeah。Why guy here。



![](img/2c5915bbf2791187d13c00d769bdde9e_784.png)

It's just going to be ignored。Because the dish isary now if we。

If we place ourselves down here so that it goes that nose， it's going to reflect part。



![](img/2c5915bbf2791187d13c00d769bdde9e_786.png)

Why does it work when the values are negative？That's the question。I thought I figured it out。

 but a apparently had it。So the thing is。The diF is going to be， this is the desire。

 it's going to be 10 minus 20。 the di is minus 10。漏两。This guy。Okay， this is Ron。This is wrong。Okay。

 I think't got a problem。We can't subtract。Because if we do objecttract。

 we're going to find this guy。And then it's going to apply twice， okay， no makes sense。お。Good， good。

Okay。See， we should be positive， plus， plus。But if we are on this side， we could heck that。Like。😊。

If we are on the other side。I think that should be the best case， really。



![](img/2c5915bbf2791187d13c00d769bdde9e_788.png)

Yeah， I'm going to do， I'm going to do。め。嗯。And do a collisionation point。Of course this guy。

And maybe you're going to try to do that on factor later on。他内心。Point， well， I don't think。Yeah。

 we about that carries。Let me just get it working first。The block。He。Is greater than。



![](img/2c5915bbf2791187d13c00d769bdde9e_790.png)

Yy。Black Pes， greater than。就。Did the desired pe？Or the target fee。



![](img/2c5915bbf2791187d13c00d769bdde9e_792.png)

I think I'm just going to look at the。The DP。 So this is the ball。第一皮。Theres a bodyaldi P wine。

 if it's going。It's going up， it's working so if this。Greateaer than zero。The collision point。

Look at this else， the collision point。Should be。Plus。Hey， what's up Daninic D？How are you doing？

We're solving some collision problems， you've got to you arrive at a great point， honestly。

Because we are about to solve the collision problem。And we spent a long time on this problem。

 but it's going to be great。

![](img/2c5915bbf2791187d13c00d769bdde9e_794.png)

あ。Well， actually we didn't do anything okay， no， I think we can go back to the to this guy that we were experience Man。

 yes， let's see。

![](img/2c5915bbf2791187d13c00d769bdde9e_796.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_797.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_798.png)

I didn't spell it wrong。yeah， I did， thanks。

![](img/2c5915bbf2791187d13c00d769bdde9e_800.png)

No， but it's nice to be organized in this sense， you know？



![](img/2c5915bbf2791187d13c00d769bdde9e_802.png)

Okay， finally。We finally managed do this。 I think you were rather good luck。

 I think the problem was the commenter was spelled wrong。

 That's the problem because the compiler compiles the comment and it realized。😊。



![](img/2c5915bbf2791187d13c00d769bdde9e_804.png)

That it was wrong。 Yes， it is break C。 we're doing。 let me show you。

Now we can do a lot of cool stuff now that we can have collision working。

 we also have to clean this up because it's a mess。You also have to do that for the explanation。

 I'm going to do this really quickly。呃。I'm going to change y for x。

And this is going to be the collision point。Re your point， okay。



![](img/2c5915bbf2791187d13c00d769bdde9e_806.png)

Yes， we need a lot of things， actually， the game is super boring。

 but I hope Indian is going to very cool， let's see。Let's see if you collide properly， okay， collide。

Okay。I did watch that talk， I couldn't find it after I watched it。

 but I do remember that if you have the link， I'd love to watch that again because that was like super over the top in the good sense of the over the top。

Aspect of it。But I couldn't find it。Yeah， but art of screen shake is about the shooter， is it not？



![](img/2c5915bbf2791187d13c00d769bdde9e_808.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_809.png)

That's。I don't remember。He having breakout here， or you're not talking about breakout？



![](img/2c5915bbf2791187d13c00d769bdde9e_811.png)

And this lecture is about the shooter， right， yes？It's a great lecture。But。There was a breakout one。

 And I couldn't remember who gave that。 I thought it was J。

JW from from the I thought it was the guys from Bmbier。

 but I couldn't fight it after and was it was even more over the top and his tutor。

 started out as a super boring breakout game pretty much like this one were doing。But at the end。

 it was like crazy stuff going on。 There was music and there was a all sorts of lighting effect。

 you know？😊，That was pretty cool， but I couldn't find it again after did。

 but it's on my mind and I want to make this game super cool to play and if you if you check out our let's say the benchmark。

 which was the other game I released。Let me find it。ああエじよ。



![](img/2c5915bbf2791187d13c00d769bdde9e_813.png)

诶哎有。

![](img/2c5915bbf2791187d13c00d769bdde9e_815.png)

Let's see， Dan。He sayd。h。io。

![](img/2c5915bbf2791187d13c00d769bdde9e_817.png)

Yeah， so this pg I created， oh， I think it did fine。八？呃。This poem， that was pretty cool。

 check out the video。I think it's pretty small。Yeah， you should should download the game。

 it's pretty cool it has all sorts of。Yes， that's the breakrickakha lecture。

I can just play it over here。Wow， thanks a lot， I definitely gotten to watch that again。

That was a very fun thing。 And actually， I I I really played。 I tried the game here。 Yes。

 you could play the game。😊，Yeah。😊，So that was over the top。呃。Like a lot over the top。

But you could really learn a lot through that。重字道人ぜ。Yeah， nice one， man， thanks。

so I guess we have a reference for the breakout game No it's not going to be that over the top。

 but it's going to be definitely fun and it's going to be hard to program this kind of stuff。😊。

But Ire certainly going to do our best and this would be great wow。

 thanks man for trying to get do you ever play plasma png before no。

 idea didn't play before they got sued？Was that a super exciting pond like that breakout that you showed？



![](img/2c5915bbf2791187d13c00d769bdde9e_819.png)

Now that's pretty cool Wellow， thanks so but at this point we are super boring right we were like the pretty much the boringest version。

 Yeah， I will I will look up at on YouTube later thanks we're pretty much super boring and actually we're not even winnie。

 but it's pretty easy at this point to make the block disappear。😊。



![](img/2c5915bbf2791187d13c00d769bdde9e_821.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_822.png)

All we have to do is to set the block。activec。Block。Life。😊。

Life minus minus and everyone has one life point in the start。

 so now we should be able to destroy blocks。

![](img/2c5915bbf2791187d13c00d769bdde9e_824.png)

It was pun with fluid dynamics， what？Gotta check this out， okay， so now we can start the blogs。Okay。

Thiss my playlist if you want， yeah， I'm definitely to going to check that out， lots of good stuff。

Im certainly want to check out， okay， now it're starting to have a breakout game。Wow。

 that was worth it， you know， the whole collision problems we had。That。That was problematic， but wow。

 I'm super glad that I would fix it。I think we're going to have a hard time getting the ball。

Behind all these guys。Oh， I almost did。At that time， let's see。Okay， let's see。Okay， yeah。

Now it's starting to become a nice break cloud game。

What we could do now is we could do more like gameplay stuff。In terms of light。

Plaaccing the blocks and the cracks， placing the on that or you can go a little bit of a game field。

Movement since you know， got inspired， you know？And it's pretty easy too。Yeah。I think we should do。

Just the basic animation on the mouse cursor， think that's going to be fun。Okay。

 now or now of talking okay。C。对。I'm just getting the position and adding so I can get really。

 really fast on the X axisxes， okay， now I lost okay。

I make a breakout long time ago and my professor liked it so much。

 she asked if she could use sorry for her into programming， that's awesome， dude。

And I really think each of programming stuff should be games。

 and I love to do an intro programming class sometime。

I'm getting more experience as doing like this is my second ever live stream， so yeah。

 I'm still struggling。I'm live streaming for three and a half hours。And。

And I started a lot to get this working， but I did it， and I think that that's important。So yeah。

 games are a great way to get started programming。So once I get used to the whole streaming thing。

 I think it's going to be a lot of fun if I get to do that。



![](img/2c5915bbf2791187d13c00d769bdde9e_826.png)

Okay， I'm definitely going to save your playlist。Because I think I'm going to enjoy watching that a lot and it's also going to be a lot of reference。

So we can do our oh， your name is Dan， Dan De Mcge， nice， nice to meet you， Dan。呃。

So it's great also to have。😊，Contact with other the breakout games like the one from the lecture。

 if you can get to play it here， I think it's going to be fun， let's see。



![](img/2c5915bbf2791187d13c00d769bdde9e_828.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_829.png)

嗯。I don't I may have closed it。

![](img/2c5915bbf2791187d13c00d769bdde9e_831.png)

Yeah， let me get the link again。Okay。Okay， let's try the game here and yes， they oh I don't。

 I don't think I have a flash player， yeah。

![](img/2c5915bbf2791187d13c00d769bdde9e_833.png)

Maybe I can do that on internet Explorer。That's we games， unfortunately。

Web games have this problem or this spec changes all the time and the games get， okay。

So press tab to set enter enables all effects， okay， let's enable effects。Okay， yeah， loud。

This is great。 You know， this thing about us question and stretching， the guy， that's a great。😊。

Fielel thing to do。And I'm certainly going to do that， I did that in my game。

At the ho on't lose through miss， yeah。😊，It's just about it's a feel good game， right， yeah。

 you don't lose。W， but screen shakeake is really cool， the ball also has a great animation to it。😊。

And the walls， wow， that's super were cool However， I'm not sure how you can control the dude like。

If I don't move， it just reflects， right， yeah。But if I move， can I can actually。

Can actually control it like this， yeah， I can。Yeah， it's hard to， yeah。

 the best game feels invincibility， only if you find out， right？only if you don't find out。

 I should say。So say it's hard to control the。It's kind of stuff with the mouse because I wanted the ball。

 yeah， this case it work， but at that that point， I'd say I wanted to speed up the ball。

 the ball has a max speed， we should probably add that too。But yeah， see。

 I wanted to go that way and I couldn't。It has four or five degrees yeah。It's yeah。

 supposed to be a casual breakout， exactly， but it's hard even though。Even if you know Lou。

 it's going to be sad to compare that with our game now because we're sort in the development。



![](img/2c5915bbf2791187d13c00d769bdde9e_835.png)

But if we do do this freedom stuff。You know， it's hard to get the。



![](img/2c5915bbf2791187d13c00d769bdde9e_837.png)

To get it 100% precise， see， let me just hack it a little bit。Go to make it。



![](img/2c5915bbf2791187d13c00d769bdde9e_839.png)

I'm going to make less fewer columns than y。

![](img/2c5915bbf2791187d13c00d769bdde9e_841.png)

Let's do eight and yeah， let's just see if now it's easier to get the ball to that。



![](img/2c5915bbf2791187d13c00d769bdde9e_843.png)

Point out。And let's just add a little bit of why offset to 35。



![](img/2c5915bbf2791187d13c00d769bdde9e_845.png)

No， I'm sorry， I shouldn't get it to。Okay。Yeah， now it's a little bit too easy， I suppose。Yeah。

But this is kind of interesting wow， see that's a that's an unintended side effect of just adding the speed and you could probably just do that。

And pretty much be invincible。Because they're moving so fast。

That it's pretty much likely that at one frame， you're going to hit the ball。哇ow。Okay。

 that was really weird。See it's hard because it's all about， you know， it's not about physics。

 it's all about， even though the physics is incorrect， I should say， but even if you do correct。

 physics， it's not about physics， it's about what's going to feel nice for they play in terms of expectation。

And in terms of experience。Yeah， but it's hard。To know exactly。

 that's one point I want to get more experience doing these small games。It's hard to get good。

At making it feel good， I suppose， I'm not sure how you feel about that。 You know。

 I don't know if your breakout game was a great field。 I think I got a nice feeling in Pg。😊。

But that was used you controlled with the R case。Let me sure youre the final project。

Because I think it was pretty cool， there was music and there was a nice feel to it。

I change the color based on the。Let me see it leaves us。Yes。🎼你好。



![](img/2c5915bbf2791187d13c00d769bdde9e_847.png)

I have this guy on。

![](img/2c5915bbf2791187d13c00d769bdde9e_849.png)

好下。う。Yeah， that go， I don't remember if your game had sound so see how。😊。

How I apply this question and stretching and also changed the color。

And I think I got the acceleration and decel to a very nice balance。

And I don't know if you're going to here， I'm going to turn the volume up。

Pantation to the sound it makes when I move him。Could you hear that that was like a sound wave that I。

ASine wave that I changed the length of based on polyar speed， the length and the volume。

 so it had this。Kind of sound and thats are not pretty cool and the goal of the poll is that you control both panelddles。

And you can't let that go be scored。And I also like the way I reflected the ball on that game。

But the problem is。Now we're doing it with the mouse， right？自己。And the mouse has different problems。

呃。Because you can't do acceleration acceleration。Because you that's up to the player in terms of what he controls of the hand。

 right？So if you stop， you have to do it like a hard stop and it's also hard to get the correct speed movement like this see。

Yeah。Maybe I should just play with that a little bit before I。I finished organizing the。

The collision things we worked on。And maybe call it a day。Because I'm kind of getting tired。呃。Yeah。

 maybe you should just study some references to like more breakout games。See， because this game。

The way it is right now， it's easier to win by doing this。And getting a lot of points horizontally。

 yeah， like that。😊，Then by the actual strategy of that。Oh， that's's pretty cool。

 thinking what to mean for the first time。Orracley or not， let's see， wow， that's super fast。

And just for the record。It just it only works like that。Because we did our collision。

 I'm probably going to lose now， yeah， the ball so fast that we certainly hits that。

 we certainly hit that every frame。that's really strange， but the point is we managed do that。



![](img/2c5915bbf2791187d13c00d769bdde9e_851.png)

Based on our sweep collision thing that we worked really hard on today。Which the point was。

 we know for a fact if it cos。So we don't suffer for autonity， which most ancients do。

 but were want to do a more。

![](img/2c5915bbf2791187d13c00d769bdde9e_853.png)

A more essay specific thing for it our。So that was it， that was the main collision thing。Okay。

 but yeah， I think I'm going to call it a date。And tomorrow I'm just going to do some small things。

 but tomorrow I'm going to start focusing on making the game play more interesting。

Like I'm going to focus on game field， I'm going to focus on the block position and the。

Going to tweak。Yeah， or maybe later today it's too early， yeah， like 7 pm here。

 maybe I'll do it like in an hour or something like that just need a。To eat something。

He someone has been streaming for three hours and 40 minutes。So。Yeah， I definitely want to do a。

A more gameplay exploration thing where I get the breakout more fun to play and that tweaks。

 you know this thing， which is the multiplier from the X velocity。And things like that。



![](img/2c5915bbf2791187d13c00d769bdde9e_855.png)

Tweaking that and also tweaking the。N I don't know what game。Game win condition and making it not。

 you know， the exploration， the exploitation of the game to do this， although this is kind of fun。

 to be honest。Yeah， I lost， but I don't know why I lost， I was trying to do it as best as I could。

 let's try this one。Yeah， oh yeah。不け。And if you manage to implement that question strategy really quickly。

 I should actually do that just for fun。啊。This would be pretty cool because I would pretty much occupy the host page。

 right， but it also make the game even more exploitable， so I don't know if you want to do that。Okay。

 but that was great if we start out， if we show。😊，In fact。

 I think I'm going to do that we started out today， which was three hours and 40 minutes ago。

 we started out with this， let me show you guys。We started out。

 I'm going to SVN just to revert that executable。We started out with this。That's it。

We only had this when it started out today。And now。We don't have bis we have， we can't pilot it。



![](img/2c5915bbf2791187d13c00d769bdde9e_857.png)

Now we have this。

![](img/2c5915bbf2791187d13c00d769bdde9e_859.png)

Which should I say is a lot better and actually I can I can even。

Just do a quick fun thing I can make the colorsries even more。



![](img/2c5915bbf2791187d13c00d769bdde9e_861.png)

Change even more， maybe a little bit more based upon the position， so we have like a nice year grade。

Yeah， that's the point because I spend a lot of time in the collision thing。

 but when you look at the grand scheme of things， it's really not that long a time。

It was like three hours to get this working。And like two and a half hours to get the other thing working now we do。

 we do need to get the gameplay to a nice stage， that's for sure。



![](img/2c5915bbf2791187d13c00d769bdde9e_863.png)

Maybe I should just add to a little bit of a。It's a bit more of a's sorry not player ball speed。



![](img/2c5915bbf2791187d13c00d769bdde9e_865.png)

This to make it more challenging。Okay， okay， and I think it's going be a lot more fun。Yeah， okay。Now。

 if I probably get a crazy， crazy X movement going on。



![](img/2c5915bbf2791187d13c00d769bdde9e_867.png)

I I probably fail because now the ball is really fast。Let's see。Oh no， I did fail。

 I guess the same thing。And then I compensate a hip in the other side。



![](img/2c5915bbf2791187d13c00d769bdde9e_869.png)

Yeah， let's add more blocks to the X。Maybe a little bit more on the Y to like 20 blocks。



![](img/2c5915bbf2791187d13c00d769bdde9e_871.png)

We should make a nice color palette randomly picking in。 Yeah， I should probably do that actually。



![](img/2c5915bbf2791187d13c00d769bdde9e_873.png)

Okay， so I ended up getting that。We could also fix that bug。We do have a problem with our interview。

 I think。

![](img/2c5915bbf2791187d13c00d769bdde9e_875.png)

In terms of making things center， see how it's not centered。

 but it should be based on our calculations。Yeah， you said about picking a color palette and picking colors definitely。

 I think we're definitely going be。Striving for a nice looking and nice feeling game so yeah。Yeah。

 now it's a more breakout kind of game right， And if I limit。

 I think I'm going to limit just for just for the sake of it if I limit the。😊。

The X velocity of the ball。I think we're already going to have somewhat interesting game。



![](img/2c5915bbf2791187d13c00d769bdde9e_877.png)

T the hold top， yeah， because I moved just a little bit like that。



![](img/2c5915bbf2791187d13c00d769bdde9e_879.png)

Yeah， actually， the less I move， I think the more is going to remove the guys。

 let's try and a little bit just。Now I think I'm moving a little， yeah，'s see。Okay。Okay。

 I'm totally failing on this， yeah。

![](img/2c5915bbf2791187d13c00d769bdde9e_881.png)

Let me see you sent your breakout game。Is that an executable， I can play now just for fun？



![](img/2c5915bbf2791187d13c00d769bdde9e_883.png)

Or do you have to build， oh， there is an execution goal。Okay。呃。Yeah， I'm going to do that。

 download it and say， oh， this is not the source code， this is actually the， oh。

 it is the source code too。Cool。嗯。😊，Okay。Yeah， it's okay。

 you saying it's from a long time ago and it directory is a mess。Yeah。

 the way I'm searching this project is code and build， I like code more than SRC for source。

Because I don't know why I try to type SC all the time。And it's not as intuitive， I think。

Extract files。Let's do this。Break out。Where did that。



![](img/2c5915bbf2791187d13c00d769bdde9e_885.png)

Okay， yeah。Okay。Oh， it's full screen I think I'm going to have to。



![](img/2c5915bbf2791187d13c00d769bdde9e_887.png)

To change the OBS settings here in just a second。Because it's not not。

I don't prepared it for full screen。

![](img/2c5915bbf2791187d13c00d769bdde9e_889.png)

啊。And I。Yeah。😊。

![](img/2c5915bbf2791187d13c00d769bdde9e_891.png)

Let me just wait a second， just make sure to see the fixed。Going to add a display capture。Okay。Okay。

 no， it's not， it's not。It's not even full screen yet。I'm having a hard time setting this up， okay。

Okay， now we're going to do it from screen video。Okay。That was a big failure， I think。

Let's now try to play the game。

![](img/2c5915bbf2791187d13c00d769bdde9e_893.png)

I think a lot， yeah， it's pretty it's best the thing about mouth， you know。

 it's hard let me just change my sensibility here。Oh， I can't， yeah。Let me make it a yeah。Less sense。

嗯。It's hard， you know， it's hard getting the right feel in terms of a responsiveness。

And in terms of like， yeah。You want to want you want to make the player want。

To control the ball all the time， let's see small things like that is hard because maybe it didn't actually collide。

 but you wanted it to。I don't know， that's the hard balance to strike。Okay， yeah。

 I almost got the ball there， okay， yeah。Yeah， your breakdown is pretty， pretty cool， it's pretty。

Similar to the to the。Or breakout， you know， the original one。Yeah， pretty， pretty cool man。

 congrats。There's no life limit is there， I can pretty much die。



![](img/2c5915bbf2791187d13c00d769bdde9e_895.png)

All the time， right？Okay， now I think the fonts a bit too small for me。嗯。嗯。Yeah。

 it's 1800 by 600 Yeah， it's 800 by 600， We to。What， it was 2009。That's pretty cool， man。

 The angle is based on where you're hit on a peedbble。 Yeah， you know， I think that's also a good。😊。

Magic， I like them both， I like making it based upon where you hit on the paedddle and the acceleration。

If that it has constant acceleration， might feel better with this light， we does smooth。

Does it have a cost acceleration？Let me try to。Try to。



![](img/2c5915bbf2791187d13c00d769bdde9e_897.png)

I just felt like， yeah。No， I control pretty much the。Yeah， like I feel like to control like 100%。

Like if I move a little bit， if I move like a lot。Yeah， oh， okay。

 and now I see the point about making it a。And do you know if the original breakout game was only based upon the pal position？

Or if there was actual acceleration involved。Because who knows， maybe you can just do like。

One or the other。Yeah。😊。

![](img/2c5915bbf2791187d13c00d769bdde9e_899.png)

嗯。Because I mean， yeah， infinite definitely， the problem with infinite acceleration is not that it's infinite acceleration。

😊，The problem is that if you add that to the ball， which is what I'm doing right now。

 that becomes problematic and you don't want to do that if there's no acceleration。

 but it's really easy for us to cap that so in fact let's do it here。



![](img/2c5915bbf2791187d13c00d769bdde9e_901.png)

呃。Let's do exactly this guy， but that's plant it。You're going to clamp。Let's say， I don't know。

 minus 100 and 100。

![](img/2c5915bbf2791187d13c00d769bdde9e_903.png)

And let's see how that feels。Yeah， now my mouse is not very much sensitive。Yeah。

 I think that's way better。Yeah。Yes， now I'm talking about， yeah， now it's nice。

No input like nose moving。 Yeah， you definitely don't want smoothing on the mouse That's the problem because on the keyboard。

 it's smooth feels nice right， but mouse also already has like real life smooth。

 I suppose you should call it that。😊。

![](img/2c5915bbf2791187d13c00d769bdde9e_905.png)

Yeah， okay， now it's getting more interesting just by changing just by limiting。That okay。

 that's pretty cool Most games have a bit of smooth especially amount yeah most most triple As do because it usually looks better。

😊，啊，Yeah， okay， I think I'm going to get that。I should get that closer on top， I suppose。

 what I want to do is I want to fix that position problem。Where I'm not actually centered。呃。



![](img/2c5915bbf2791187d13c00d769bdde9e_907.png)

This should not， I know。Since we already spent a lot of time debugging things today。

We might as well do that that's easy to fix yeah， but I'm not sure about that。

 let me show you the code that's driving。Everything is software rendering for now， I go。

 you know each pixel so individually right， this is the draw and pixels。

So if I create a rectangle here， let me just create like a draw。In pixels， if I do a recangle go 50。

 5，1， 51， 50， let's do it like a pinkk。

![](img/2c5915bbf2791187d13c00d769bdde9e_909.png)

This rectangle， it's going to look weird， I think， yeah see。It's not actually correct。I believe。



![](img/2c5915bbf2791187d13c00d769bdde9e_911.png)

And yeah， no， the point is I can just show you what exactly what I mean。



![](img/2c5915bbf2791187d13c00d769bdde9e_913.png)

This， I expect to be。嗯。I expect this rectangle to be somewhat like here。See， I set 5050。

 so I expected the same number of pixels down here as well， so yeah。This is what I expected。



![](img/2c5915bbf2791187d13c00d769bdde9e_915.png)

I think that's the problem。But Hawaiians didoff said， I believe， I strongly believe。

 is because the way we were getting the window size。We are considering this。😡。

So let me just do some print screen things。

![](img/2c5915bbf2791187d13c00d769bdde9e_917.png)

Okay， this is the window， okay， this is the window。If I see the size of the whole thing。Actually。

 if I just see the size of the drawable area， this area。It's 1580 by。Yeah。

 because we are asking for a。You know what？

![](img/2c5915bbf2791187d13c00d769bdde9e_919.png)

I think I'm gonna。Because this I have like。Scaling turn on， you need to yeah。

 but I am getting the client ranked and that's the problem。



![](img/2c5915bbf2791187d13c00d769bdde9e_921.png)

呃。No， I'm getting Windirect， you are correct。Wow， nice call man， yeah client wrecked。



![](img/2c5915bbf2791187d13c00d769bdde9e_923.png)

So yeah， I had my suspicion that that was a problem， So you were right， it's easy to。 Yeah， get it。😊。

え。Dude。That's it。Oh， now。Now it's。Way better in terms of correctness of position。



![](img/2c5915bbf2791187d13c00d769bdde9e_925.png)

So yeah， it's interesting because in the mouse， we did， we did do the right thing at mouse。

 we do we did the。😊，Let's see Mount pointer， yeah， we do the screen direct。Screen to client Yeah。

 so it did screen to client on mouse， but on the screen side we didn't we didnt get Windirect Wow man。

 thanks a lot。Yeah， that was great。You know， in the beginning of the stream。

 I did spend a little time thinking about that。But I quickly like， okay。

 maybe a little bit of a Windows thing and kind of ignore it？But， yeah。Now。

 I certainly gonna keep that in mind。 And I see that problem again， I it peing indeed。

 let me ask you something you are。😊，You were doing this kind of games in 2009。

 What are you doing now， man？Sometimes stuff like that takes eight hours to fix。

 you're totally correct and although what we did today wasn't exactly like that was more of a math exploration thing on the collision。

 so I think it was justified spending a amount of time we did。But。Yeah。

 it's usually you could do usually quicker things， faster things than you do sometimes。But yeah。

 if we were doing like that kind of game in 2008。Dude。

 doesn't8 I was playing like Gt for 10 hours a day。うんうん。你没呢。Yeah。

 I think we got to LA and just remove that。The draw act。See。

 that's why good engine is so cool it it gets better and better so for the next game you're not going to have all these collision problems and gameplay problems and things like that Okay now you're going to start。



![](img/2c5915bbf2791187d13c00d769bdde9e_927.png)

Now it's looking nice。Really nice， man。Yeah。You know what， just for the fun bit。

 I'm going to implement the those condition。And I might as well add the difference in。In the size。

 yeah。ok yeah。ないし。Yeah， no， no， I'm going to let the。I'm not going to do that tomorrow。

It gives interesting。Itives easier things to do in the beginning of the stream tomorrow。Let's see。呃。

Twitch just。Just give me a blank page so I can't see chat anymore。Wow， that was great thanks to it。

But while you're doing some 3D craziness。With collisiongen detection， I can see the mini map here。Oh。

 that's pretty， is that a custom engine， I think it looks like a custom engine to me。

 pretty smooth lines？Things like that looks great。Very beautiful we're going to try to get chat back online for some reason。

Twitch decided to give me just a blank page。

![](img/2c5915bbf2791187d13c00d769bdde9e_929.png)

Which。Okay， now I can see the chat， but I lost the previous chat。Let's see if I can get。Yeah。

 in this browser， I can't open Twitch。The browser。Oh I'm like， okay， yeah。

 open G collision detection。I think now I can go to the channel。Yeah。Creator dashboard life， okay？

But I think I lost the chat dude。 Come on， twitchwitch。Yeah， yeah， and soft shadow。 Okay， lighting。

 Yeah， youre showing。你须。That's pretty cool man， I really want to go more in depth。

On these kind of stuff， too。But， I started with basics just to get really solid foundations。Yeah。

 pretty cool any stuff， man。Yeah， awesome， awesome， awesome。See。

 I got a blank screen from Twitter again， I must be doing something wrong。



![](img/2c5915bbf2791187d13c00d769bdde9e_931.png)

See how all the browser screens are now blank。For some reason。Dude， what is going on？



![](img/2c5915bbf2791187d13c00d769bdde9e_933.png)

Well， maybe a good time to stop since that's going on but。Doude really congrats man。

 you're doing some awesome work and I hope to get to your life in terms of rendering and col and stuff soon。

 I hope。

![](img/2c5915bbf2791187d13c00d769bdde9e_935.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_936.png)

呃。Yeah， I don't think I'll be able to see the chat anymore because I really can't open Twitch。



![](img/2c5915bbf2791187d13c00d769bdde9e_938.png)

Let's see if I can open it again on this browser， yeah， now it works。Yeah。Okay。

 so I think I'm going to close off it was great talking to you guys I had a really fun screen it was a four hour stream where we got a lot done what I am going to do now。

😊。

![](img/2c5915bbf2791187d13c00d769bdde9e_940.png)

If I'm able to show you guys my browsers。Oh my God， what？😮，嗯。Oper， what you expect， come on man。

It's the best browser， but it's not much because you know browsers。

I started in 2016 to low open G out and see。 Yeah， I also started a short time ago， you know。And。

I'm surprised， you know how much you can progress if you really dedicate and I'm really happy。

 I've been doing this kind of a small kinds of gaming and sea for like less than a year。 Honestly。

 what I am going to show you guys is where I'm gonna。😊。

Go' going to publish the source code for today， so if you want to play around with it。

 you can go to HO， you can go to dzean。h。o。And check out this Break Arrcade Gamehouse。

And I'm going to post the episode2 source code， which was today date。

And we managed to do a little bit。 I expected to do more。

 but that's the thing when you' expect to do a lot of stuff， you usually don't。

 so it can have like high expectations in terms of。Programming because in never though。

 maybe gets stuck on a problem for a long time。So yeah。

 if you want to see the recording in case you didn't see the whole live stream or you want to see me you know。

 painfully try to get the collision correct until I finally get to get the collision correct。

 you can go to my YouTube channel， it's WWW。Youtube slashdan Zan。

And I'm going to post the four hour video now it's going to take a while， but yeah。

That's a thank you guys for watching， and I hope you enjoyed it。And tomorrow。

 I think like 12 hours from now。Maybe 12 or 14 hours from now， I'm going to do another live stream。

Where a。We're going to advance the gameplay。 we're going to make it feel nice based on one the great references that da showed and all the references to。

 So yeah， hopefully you're going to tune in for that。😊。



![](img/2c5915bbf2791187d13c00d769bdde9e_942.png)

So I'll see you guys later。Thanks。