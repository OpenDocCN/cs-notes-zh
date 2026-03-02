# 哈佛大学《2D游戏开发｜CS50 Introduction to 2D Game Development 2025 Fall》中英字幕 p06 CS50 2D - Lecture 5 - Legend of Zelda .cut.zh_en -BV15xsPzEETf_p6-

Thankque。Hello world。 This is CS S 50， the first of two live streams today。 I am David Malon。

 and I'm here with Colton Ogton。 and today we're gonna be focusing on the legend of Zelda。

 which was one of my favorite games growing up on the original Nintendo entertainment system As always we're gonna be fielding questions via the chat I'll raise my hand to surface any to Colton as well forgive if we start and stop to have to fix things along the way but otherwise we're just about good to go we have a tradition of fun facts here and I didn't think of one in advance。

 So I'm stalling for just a moment so as to think of a really good one and I've come up with this question of all of this Nintendo systems over the years。

 Do you have a favorite console。 I think Nintendo 64 nostalgic was what I played mostly in elementary school but Super Nintendo' they're tied for you for me it was the original Nintendo but I'm thinking to myself N 64 I think I only first played in graduate school you played we quite a bit the we is what got me back into gaming actually because it was so much simpler than。

😊，The traditional controllers of the Xbox and PlayStation， right， but the switch is pretty good too。

 I think I would agree。All right， well， we'll be back in a moment。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_1.png)

![](img/8fc31d00de36a5a615a661d1a3cd4b84_2.png)

Hello world， this is CS52D lecture 5 today we're going to be looking at the legendgend of Zelda which is a favorite franchise of mine amidt Mario。

 I like Mario quite a bit as well， but this was one of the first series that I have memory certainly playing and also we styled it based on the original cartridge for the NES was actually colored gold so was it SequL。

 which I thought was kind of a cool thing。This is what the original Zelda looks like and this is sort of like a famous line that people quote online all the time it gets referenced in various games。

 it's a throwback and sort of this is the very first thing you see when you go into the game you start off you see this cave you go in you grab a sword at its time was one of the only games that sort of had this early idea of an open world that you could go out and explore and it accomplish this via having a bunch of sort of discrete separate screens that you could transition in and across this is a screenshot of a dungeon you would also go and navigate sort of these labyrinth type structures and in today's codeb will be primarily focused on this sort of view of what Zelda looks like looking at a dungeon that gets generated and then we can traverse it and we won't have all the bells and whistles per se but we'll have the sort of famous scrolling and some monsters and the ability to swing your sword and so on and so forth。

This was the first El that I played as a kid， this is linked to the past for the Super Nintendo which took the formula and sort of expanded on it。

 added two different worlds and a bunch of other cool features to it， a lot of different items。

 which is part of the problem that will be how to add， you know not to get to ahead of myself。

 but a item that's a very famous in the franchise being the boomerang which is actually shown here at the top of the screen。

 sort of signify that you can throw this boomerang that will freeze enemies and so on。

And to this day Zelda is still being produced， it's still a very popular very well-selling franchise。

 much like Mario is on the switchitch， this is Teaers of the Kingdom which came out in 2023。

 very good game， which was the sequel to breath of the wild， also a switch game in 2017。

 very famous still to this day， one of the top selling franchises。

And so some of the things that we'll be taking a look at today。

 we've so far when we've looked at 2D games， we've mostly looked at sort of like the side view of what it means to be in the 2D game。

 games like Mario are they are called side scrolling platformers。

 meaning that you scroll from the side and you can jump around and sort of gravity works on the Y axis。

 but in a game like Zelda you're actually taking more of a bird's eye view and actually looking more from the top as if you were literally by the name。

 sort of a bird looking down and it's different than a side scrolling game and that you can actually move across the X and the Y axisxes unlike well you can in a platformer but in this kind of game you actually have full movement across the X and the Y axis。

 your Y axis isn't just a jump determined by gravity， you can add onto that depending on which game。

 even Zelda has done this with very things like the rock feather in various titles。

But today we'll be looking at what this means and it's really not much of an evolution on what we've already looked at。

 but there are some site differences to take into consideration。

 we'll look at dungeon generation how to actually create a dungeon in code。

 which allow us to test that our transitions and would not work。Hit boxes and hurt boxes。

 the difference between them， a hitbox being sort of like when you get hit by something and a hurt box being。

 for example， when you swing a sword， there needs to be a way to differentiate your sword from your character's body and have the sort of semantic difference of your sword inflicting damage onto another rectangle and that's where the difference comes into play between hit boxes and hurt boxes willll look at events briefly screen scrolling is sort of like the。

Classic 2D Zelda aesthetic when you think of it it's where you're moving to the edge of the screen and then the screen pans and that's how you open up and go explore a new area we'll look at how to do that in our dungeon and then lastly we'll take a look at stencling which is a sort of way to mask pixels before they're actually drawn to the screen to achieve certain graphical effects before we look at a little bit of data-driven design and how to representing all of the entities and so forth in our code without having necessarily to upfront define them in code as much as have them in a separate file something that a designer might be able to sort of take on separately from a dedicated programmer and so this is what our goal ultimately looks like you can see things are styled roughly in the vein of Zelda its font and so on and the top right in particular shows what the gameplay at its core looks like but I think in order to really illustrate this we should have a demo as this tradition and if we could get a volunteer from the audience who might be yes Damon I think right？

David。A， great， okay。Nice to see you again。 Nice to see you。

 Thank you for calling on me So this is Le of 50 Okay So if you press enter you'll actually begin and as you can see we have a character in the middle of the screen a space bar will actually。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_4.png)

🎼So it， too。The hitbox is kind of small， but as you alreadydy got it。

 this was a childhood Game of yours because' my favorite。

And maybe one of the two games I think I've played okay， you get getting the trifor。🎼There well。

So you'll notice that there's a switch there on the screen and actually this particular example generated a dungeon that doesn't have any doorways。

 so if we might restart the implementation here really the best I've ever done in these games though it is an outlier so we try this version。

 there's a actual switch and a doorway on the right as we can see here。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_6.png)

Okay so should I exit the room this time so if we hit that you'll see it actually open the doorway and now we can walk through it and if you press M as well。

 by the way， you'll notice that we have a sort of a dungeon layout here we're getting unlucky with these dungeons we only got this one only has two rooms normally they are much larger than this。

But as you can see we've got switches now the open doorways。

 the transition occurred where we're able to actually move back and forth between rooms。

 notice your character sort of on his own will move to the screen。

 the screen will shift and now we' sort of centered everything in this new area。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_8.png)

Oh half a heart left Should we see what happens if Yeah。

 why don't we see what happens we got a game War we're screen stylized thanks for having thank you so much。

Sorry to cut the thing it looks like this， the recorder fell out of this following。

 and I don't know if it accidentally a button changed on it or something。All right。

 so to illustrate this， I think as this tradition， it's best that we take a look at an actual example so if we can get a volunteer from the audience。

 yeah， come on up。

![](img/8fc31d00de36a5a615a661d1a3cd4b84_10.png)

This is a Damon right David okay okay， nice to see you again thanks for calling Okay so we'm gonna to go ahead and start the game here as you can see we've got a title screen you press enter now we've got a as you can see a dungeon layout here some enemies if you press space bar you'll actually have a sword you can swing to deal some damage you also take damage from enemies I see a lot half of heart you got hearts at the top indeed you'll notice that there's a set of doorways。

AndThey're all closed currently， but if one were to take notice of the switch there on the ground。

 they all open up。And then we get the classic Zelda sort of transition。

 there's even a utility built in if you press M， you'll actually be able to see the map sort of laid out there if we assume that we started on the tile below there red being the current position。

 green being other rooms， not doing very well。It's hard the hitbox on this particular sword character is a bit small。

 but you're doing a great job carrying out this room of all the enemies， nonetheless okay。

 one heart left。nailil biting。All right to receive it and then yes。

 ifre you to lose all of you I think so it could have been， but yeah。

 we have the stylized game over text and then we could repeat it thanks so much。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_12.png)

![](img/8fc31d00de36a5a615a661d1a3cd4b84_13.png)

All right， and as we saw there were a lot of pieces in there that we probably seem a little bit familiar but also a little bit different。

 we do have the classic screen scrolling， we haven't quite looked at anything exactly like that。

 but if we sort of think back to previous lectures we can imagine that you know it does look like in interpolation。

 therefore a tween might be occurring that's taking place we do have enemies that are strikeable with the hurt box that we talked about but they're also moving around in a similar way to the snails we're in Mario and all of this can take place again through sort AabB collision detection we have the switch as a game object。

 we've got doorways which are also game objects and we've got the classic sort of game states that were're transitioning to also various animations of the player as they're moving left right top bottom。

 different states that the player also recall last week we' began able to look at states on the actual entities themselves in this case the player has a walking state and idle state。

 a swing sword state and so we have a lot of the same pieces but we're using。

various new techniques to illustrate different ways we can use them to accomplish different goals and so the very first thing we'll take a look at is the day zero update this being sort of classic again per prior lectures much like breakout and otherwise and here we can just see you know what do we have to do to actually get topdown rendering occurring while we need the player and then just to really nail down the fact that we're in Zelda we can add some hearts as well so why don't we take a look at Zelda zero the day zero update in code。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_15.png)

![](img/8fc31d00de36a5a615a661d1a3cd4b84_16.png)

If we transition over here， I'm going to close out the sort of main file for the Zelda demo。

 and then if we just run。

![](img/8fc31d00de36a5a615a661d1a3cd4b84_18.png)

Main zero or for Zelda zero here， we can indeed see that my character is moving across the screen if I just use the arrow keys here。

 there's an animation taking place， so he's got sort of a down facing upward facing left and right facing perspective and then the hearts at the top left which we can't really interact with at the moment there's nothing to really be able to damage us。

 but the core here of just the movement in 2D space from a bird's eye has been already laid out for us。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_20.png)

Now， if we transition back here， a topdown perspective often in games entails。

 it depends on the graphical style that you're going for。

 you can have sort of isometric and then this is a sort of more orthographic sort of style。

 but as you can see we have corner pieces and walls and things of a various highlight of a particular highlight color up here for example。

 different color that is down here which sort of simulates this sort of idea of lighting and perspective。

 we've got all these different tiles across the board that are being drawn similarly to how they were being drawn with Mario except now they're actually the floor upon which we're looking from the top。

 they're not sort of like this side view that we're looking at them and all these tiles all have a different texture and therefore a different index if we were to look at our sprite sheet from the top down。

Now we're gonna to fix it primarily on just the character for right now and as you can see there's a myriad of frames in this texture here that illustrate the different positions that he can walk in and sort of be in you can see even here some that we're not using yet which are sort of like a picking up an object。

 a heavy object as noted by the sort of strained expression on the character's face this is part of the problem set which will be to implement pots that the player can lift up and carry above their head and then throw as a projectile we won't be looking at that just in this lecture example。

 but we will be looking at for example the character walking walking to the right walking up and walking to the left in theory you could just flip these like we looked at last week with the character but this sprite sheet actually gives it to us they're in the sprite so we'll just use it as is we'll just chop up the sprite the texture atlas the sprite sheet and just use the frames directly。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_22.png)

And then you can see here a different sprite sheet where we actually have the character wielding the sword。

 and because the character uses a sword and it sort of extends his sprite。

 the character sprites here are slightly larger， these are actually 32 by 32 blocks instead of what these are actually sort of 16 by 16 blocks。

And this involves also us figuring out okay what should the hit box be。

 what should the hurt box be for the character， how should we offset that from the character and render it。

 well we won't actually render the hurt box but we can for debugging purposes， for example。

 take a look at it， but this is an example again also of a spreadritesheet with varying sizes and sometimes it's more prudent and we've done this in the distro to just chop them up in cases like this。

 for example， you have this entire spreadritesheet of these particular uniform sizes and also uniform semantics。

 this is just walking， this is lifting a pot， this is walking with a pot。

 those sort of sort of different， so we can think of those differently and so it's sometimes prudent and we did this in the problem that to chop these up into separate textures and so that's what we did。

So why don't we take a look at what we're doing here just briefly。

 most of it is going to actually be relatively old code by now。

 but just to illustrate what we're doing。If we bring up the actual main。

 you'll see that there is not a whole lot going on here other than that we have a play state。

 so we're just going to have a play state that just for right now just renders the player。

 a player is an entity， recall entities where this idea we looked at last week of this container of potential behavior and attributes that allows us to sort of think of all movable or interactable。

 interacting creatures or whatnot， things that are sort of sentient or moving about the game space。

 the game world， as an object that can then inherit behavior， if they get subclass。

 for example an entity， could be subclass to a player。

 meaning a player is just a more specific version of an entity。

 you could do the same thing for enemies， you could do the same thing for any creature that you want to that has its own particular behavior and semantics。

 but a general entity is going to have things like its own ability to collide and render itself and update itself and so on and so forth and contain its animations that get defined。

You can see here the classic collision algorithm for AABB， the player update just defs to entity。

 update if we take a look at entity again， a lot of the same things we've seen， it has a direction。

 it has this function that we haven't really seen called create animations which takes a definition。

 a table that contains information about the animations。

 and this is a sort of as we looked at in the lecture slides。

 an example of datadriven design where we can define as much behavior as much characteristics as possible of whatever it is that we're trying to create。

 have a function that imports them parsees it， actually creates the thing。

 and then allow our designers and programmers and whatnot to sort of work on separate parts of the problem。

 the programmers can focus on implementing functionality。

 the designers can maybe focus on okay the sprites sheet and the animations and maybe if we expose a high enough level API for how to define behavior within we can define a sort of a DSL。

 a domain specific language for our entities or for whatever。We want to model in our world。

 we can allow our designers to become ever more powerful without having data into the weeds with programming an idea we won't explore tremendously deeply in this lecture。

 but we will look at the sort of beginnings of that with the data portion of it。

 but you can see we have all the classical definitions we have a health attribute which is important that's the hearts again an invulnerable attribute。

 which is something unique to the player because if we recall when we get hit by a creature in the game。

 which we didn't fixate on but folks might have noticed that the player actually goes invulnerable。

 meaning that they sort of phase in and out over a period of time in that they look semi transparent and during that space of time。

 they can't actually be affected by another hit and this is deliberate design such that a character can't just be cornered by several monsters at once and then just go from three hearts to zero in the blink of an eye。

 we typically want to give the player some sort of a buffer to allow them the chance to escape or to defeat the monsters that are cornering them and so that's why we have this invulnerability mechanic。

Which is simply phasing in and out and then ensuring they can't take hits during that span of time。

Flashtimer is part of that deal， so this create animations thing which we looked at is essentially the key to getting all entities to be able to load a texture and a set of defined animations that then define how they get drawn without us having to do it really manually in the code if we look at for example。

 entity depths we'll see here。That the player is defined and this is a global sort of constant we declare this as a sort of constant global variable with this uppercasel or uppercase underscore sort of syntax。

 this constant notation for an object that's sort of global constant we're not going to change it it's not going to be manipulated too much it's just static data that we can reference later and so if we define a key player which then has all of the attributes essentially we care about at the time of initializing the player or whatever entity you can see we have here in animations key which has walk left。

 walk right， walk down， walk up they all have these frames that have been defined within there an interval for how fast the animation should occur character walk being the texture title so we can allow people to actually manipulate these pieces of information without having to actually involve any code whatsoever and it's quite bulky if you were to scroll through all of this in terms of there's just a lot of information there's a lot of sprites there's a lot of different character。

and creatures that we can add to our game， but it's a relatively I would say simple if not mundane and tedious process that somebody could just defer to somebody else or a designer to do。

 and then if we again empower the designer to also do more with these tables and give them the ability to define sort of simple functions。

 for example that allow for collision behavior or attributes， for example。

 what kinds of weapons or what kinds of various other qualities of the entities we want。

 the designer can sort of spend a tremendous amount of time building up all this stuff while the programmers are out doing more sort of lowleve implementation so as you can see as I scroll down here we have all of these different creatures。

 if we open up the graphics here。You'll see that I've split out all of these separate sprite sheets。

 character being the base sprite sheetet， but then we have character walk。

And this is partially for ease because remember generate quads it'll actually splice up our sprite sheet based on a uniform size for the actual sprite that we care about in this case this looks like it's about 16 by 32 or 16 by 24 perhaps but they're all the same size and therefore they can be loaded programmatically we don't have to hand define rectangles that then get placed and get fuuzzsy。

 we can just therefore also cleanly just have this indexable Gframes G quads character walk or walk or whatnot and even more simply because we're defining it in the data now with definitions there's an actual piece of code that will just look up the texture by a string and then the frames and then just simplify our whole process and so this is how we can define our animations now without having to really define it in code we do all the heavy lifting programmatically。

And so if you go to the play state。Here。You'll notice again， entity states， game states。

 these are going to be two different areas where the entity states are these state machines we added last time with And Mario with the characters having this sort of if you're called jump states。

 walk states， idle states， doing the what we did with games。

 but with entities now to sort of simplify how we conceive of them。

The player gets defined here with its animations being set to entity depths of player。 animations。

 it walk speed being set to entity depths of player。 walkpeed。

 and so this is how you allow the designers to sort of affect your code。

 or you can do it all yourself as well as if you're just doing all the development and therefore just more。

 I guess isolate and model your data separately， which is a good idea as well。

 but either way you have this flexibility now。Most we have six health。

 we're storing hearts as two health per heart so that we can model half hearts with one health。

We've got the walk state and idle state。Update classic stuff that we've seen before we have this thing that we haven't seen love。

t graphics。 push and what this essentially does is recall last week we looked at love。t graphics。

translate being that function that will actually sort of shift the coordinate space for us so that we can。

We can think about moving a camera through space， even though we're not actually necessarily physically doing that。

 we're sort of mimicking that behavior with an illusion， but we can do that here。

 we can sort of refresh the state of whatever the camera is set at with this push pop operation whereby push will sort of push a new openGL or new graphic state onto this stack that gets maintained in the graphics card and then what this does is any transformations that occur will actually be considered in their own separate space。

 openGL and most graphics APIs or sort of this state of operations you've seen that we can set the color for example the global color white or whatever we want to draw things and render things but that's globally applicable but sometimes you might want something to draw and then for that to change and you might want to go back to that prior state to draw something else in this particular case we might want to draw the player and then we might want to move the player around but then we might want to draw the hearts and have the hearts always stay in the exact。

Same spot and so we accomplish that by treating them as two separate states in this sort of like abstracted over state of the graphics card where we have this one state where okay this is where translations will occur potentially it will eventually be the dungeon rendering with all of its entities right now we're just rendering the player but then once that's finished we might want to create a whole new state with its own reset translation value effectively where we're not translating anymore by any value and then therefore whatever we draw at00 is always going to be at00 at the top left those being the hearts in a fixed position so this is a way to do that it's a way to sort of have things that get statically drawn no matter where you've moved the camera which is applicable in particular for UI elements and so that's what we're doing here。

All that to essentially say and illustrate how we are getting just a very simple set of things drawn to the screen。

 which I'll run again here。

![](img/8fc31d00de36a5a615a661d1a3cd4b84_24.png)

You can see the character moving around。We have state machines which we'll be looking at periodically throughout the rest of the examples。

 but suffice to say it's not all that different from Mario's walk and idle state from last time。

 in as far as we have an idle state where we're just drawing based on whether we have an up or down direction。

 you can see they have different sprites and then a left or right direction。

 and then if we're moving， let's update that animation。

 if we're not moving then there is no animation to update per se。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_26.png)

Okay， that's Mario Ze or Zelda zero， and take a quick little swig。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_28.png)

So we've got a character rendering。 It's quite you know bleak at the moment。

 but the next update is going to take us closer to a more。

I guess close to final aesthetic for our game， which is going to be the tile set update。

 which we're actually going to start rendering the tiles of the dungeon。

 which isn't anything too complicated or something that folks haven't seen yet before。

 particularly since we've done Mario last week， tile rendering is fairly straightforward at this point and in this particular example today none of these tiles actually have collision we know for sure all of the tiles in our game are going to be in this exact orientation。

 this is similar to the original Zelda by design， folks could definitely implement a version where the tiles did have collision。

 but since we know all the rooms are going to be the same size and offset the same way we don't have to actually worry about tilebased collision we can check and set for boundaries so in that sense today's examples are going to be simpler but there are going to be some other aspects we need to take a look at。

The first thing we'll take a look at is just the size of the tile set and it's not uncommon that tile sets in games like this get as complicated as this。

 if not much more complicated， I mean last week when we looked at Mario。

 it was tremendous we had a ton of tiles to look at a lot of them were the same just with a different aesthetic variety and today's example we have a lot that are actually functionally different。

 we're only going to be using a subset of them but as you can see looking at this we can see that there is a sort of general symmetry to the way that things are laid out a general homogeny to the size of things if we actually overlay a grid on top of everything we can really see the 16 by 16 tile sort of delineation here。

 we can see the things like the pots over at the top we can see these sort of corner pieces laid out which are deliberately positioned in a way to sort of lump them all together and see visually how they might organically be able to be composable in a clean way we have the walls laid out together。

 you can see there are variants of the walls。They have these sort of little details slightly different across all of them and many other pieces。

 for example the doorways， which as you can see with the doorways。

 they're actually modeled with four tiles， which is how we draw the doorways we have they're slightly larger than the 16 by 16 so it's not uncommon that you will draw you two。

4，6， whatever the size of the tiles is， and then model the collision of that however you see fit。

I find it really easy in particular to especially when we're getting into big tile sheets like this to have some way to be able to easily because again we're thinking in terms of indices numbers that we have to index into a table to find these tiles and so looking at this is one thing but we want to be able to ideally look at whatever number of that tile is that we care about on the fly for example I want to know that number four here is the top left corner of the dungeon。

 I want to know that 24 is the bottom right corner but it's kind of a pain to be able to sort of go through and hand count each individual one to know recall it just gets sort of added in this linear way。

 left to right， top to bottom。And so there's included in the distro。

 which we won't take too much of a look at a simple Python program that allows you to put in if you just edit the name of the program or name of the PG that you care about splicing up or whatever the image is uses a library called pillow but you could also do this in code in love 2D for example if you wanted to just load the texture。

 render it and then draw the text overlaid I would argue that that's slightly less convenient because now you have the love runtime up if you're debugging another game。

 you're going to run into some issues， it's nice sort of just have an image that you can save。

 and this is included in the repo for folks who want to use the tile set。

 they can actually see all the numbers preaded onto the tile sheet for their convenience as they're implementing the problem set for example。

 the pots at the top and the treasure chest part of the boomerang part of the problem set folks are going to want to know what index that is so this is a convenient little way to sort of add that so let's take a look at the tile set update in code。

If we go over here， I'm going to close out all these other images， most are sorry source files。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_30.png)

And open up Zelda 1。 Now there's not a whole lot in here that's too fancy or complicated， but。

We do now have a dungeon that is rendering。I should say not even a dungeon yet because technically that's the next update。

 a dungeon being a data structure that has to maintain multiple rooms that are contiguous。

 This is just a room for right now。 we can think of it just as as a room as an object which is defined by a set of tiles that render the top left right and bottom it will have doorways it will have switches it will have entities including the player that it manages takes takes care of renders etc but for right now it's just a essentially the same code that we had last time but now we're actually rendering all of these tiles that we care about and those they're all random too there are multiple variants of the floor tiles。

 multiple variants of the top bottom left and right wall tiles and this is not uncommon because if you were to just draw the same tile it would look quite homogenous in a way that feels very unpolished so it's good to use these variants these sort of randomizing these sort of subtable of tiles that you have access to those being your walls left and right top and bottom to effect as sort of。

Better variety， better aesthetic sense for your game。So's take a look at how we do that。

This will be primarily in the room and notice that there is a world folder here so we have the main source files and we have the states and then we have this folder called world。

 This is how I like to model often when I'm making a game separate your main sort of like base logic you animation entity player。

 those sort of higher level code files can live at the top of source for example。

 or they could go in a folder called entity or some other folder that is more like generic or general。

 but I like to also have world that models anything that's in the world because a lot of the world code can kind of be thought of as a separate monolith。

 separate from states separate from utility in general access code。

 You'll notice that we have So if we go over to。Play state just to sort of set the stage a little bit here。

There's a current room that we set in the play state。

 which is going to get rendered and updated and it takes the player as a reference so that it can render the player thereby。

And this room is in world。And what it is is effectively not much more than simply a container of tiles that gets generated。

 you can see there's a function called generate walls and floors， and we have a tiles table。

And a reference to the player。You'll see also like things like these render offsets and an adjacent offset couple of fields later that are going to come into play when we start transitioning from one room to another。

 we're going to need to essentially have both in memory at the same time and rendered and updating but that's sort of getting ahead of ourselves a little bit but you'll see generate walls and floors。

 all it really does and we won't necessarily dive too much into the particulars at a terribly fine level but what it essentially does is it iterates through the entire map。

 Y to X， a 2D crawl just like we've seen many times and it will just do comparisons it'll say okay。

I want to fill this tile map with the IDs that map up to what we saw。

 which is the wall tiles at the top， the or I guess top wall tiles。

 the side wall tiles at the sides and then the bottom wall tiles at the bottom and then we want to randomize there's like four。

 three to four variance per at least with the walls that we can choose from and then a higher number that we can choose from for the center and then you can see all these constants that we're defining。

 might wonder where are the constants all these constants for top left tile top left corner。

 tile bottom left corner all being rendered and simply just in the constants file。

 we've gone ahead and rendered all or we've gone ahead and defined all of those。

Starting here at tileile IDs， you can see 4， 5， 23， 24。

 all things again that I was able to identify because I had written them all out to that texture if we were to go to graphics here and draw。

 you'll see it as tile sheet numbered in the distro。

So you'll see here if I just zoom in a little bit here。We do indeed have tile top left， for example。

 being four， tile top right， being 5， bottom left 23， bottom right 24， all of these floor variants。

 there's a lot of them， 7 through 13 then 26 to 32， so tedious to an extent。

 but sort of a necessary evil。And what we can do therefore is just handp all of those out。

 define them in constants and now when we're in the room generating。

 you'll notice here when we're actually placing the walls left right top bottom。

 we're actually indexing into these arrays that we defined these tables that we defined by the math dot random at the length of those very tables。

 and so we get a random set of tiles。Here we're inserting it， and then we just render it。

 we just do a Yx crawl and we just render all the tiles much like we've done through in Mario and through other examples like match3。

 Love our graphicphics。 drawaw takes texture， takes the tiles with the ID of that tile。

All things that we've largely seen thus far， all pretty much the same。And then。If we go to。

The entities， the players， walk state。You'll see。Here is where we're sort of doing more of the actual detection for whether we've gone up or below or left or right at a certain point in our room to actually detect okay are we at the limit of the room because we don't want to go we could I should say。

 decide to do all the collision in room with tile-based collision and that's fine。

 but because we're literally just doing a y and x limit essentially for the character because we know the hard definedfined limits of the room。

 we don't have to do tilebased collision anymore， we can simply determine in this particular example we're using actually entity walk state。

 update we're deferring to that， notice that we're calling entity walkstate do update self DT。

 this is a way for us to use a member function， a method of a class in particular this class is a the player is a subclass of entity but if we want to use for example。

 the behavior defined in entity walk state。The player we can't really call like this update function now the player's update function is its own function it gets sort of overrides the entity walkstate method。

 the update method， but if we wanted to call it because we do actually care about that behavior occurring and then we want to add onto it our own behavior we can manually trigger it using a static invocation here so we're actually using the class itself dot update and then manually passing in self recall that if you were to call an objects sort of if you were to use the colon operator and then therefore just passing N DT this is essentially the equivalent only we're invoking it at the class level because that's how we get access to that function now we can't actually call like player dot update player colon update self Dt and get access to that function。

 we've already overridden it by inheriting it from entity essentially player defining it itself if we were to look up here you can see includes equals entity。

walkalkstate essentially means this walk state overrides this walk state。

 therefore this update overrides that update， but we still care about entity walkstates update。

 so we want to do entitywalkstate。 updatedate。And then manually pass in self。

 which is essentially the same thing as calling a colon version a method which passes in for you。

 but we can't do that if we've inherited and overridden that function。

 if we were to look at the entity walk state， you'll see。It's got various。Pieces of code here。

 for example， it actually will change our animation to walk down。

 assuming that every entity that is an entity has a walkdown animation in its thing。

 This is sort of something that gets automatically taken care of for us for example。

 but update has the code all this code here essentially does boundary checking to make sure it'll flag us as being bumped so we can see okay did we collide with a wall。

 and then if we did this allows us to like do some checking for doorways a bit later in the code which is important。

 but for right now the important code is here， depending on which direction we're moving if we're in the walk state did we go to a certain essentially these offsets。

 we have a set of offsets that are constants that define the left and right edges and top and bottom edges of the screen if we've gone past those offsets in any way。

 depending on our direction， we should essentially reset our x or Y position by just shifting it right at that offset or minus by our width depending on which side we actually。

As you can see here， if we were moving to the right， we want to shift to the right。

 remember everything's top left based in this code base， everything is based on the top left。

And so this is the code we care about that does actual balance checking。

 the player wants to be able to detect that do that same thing but also extend behavior in ways that we'll see later。

 and so we can essentially invoke that same function manually here by calling it on the class but passing in self self-being this player as an object and therefore get that behavior while being able to do some other functionality which isn in here sort of penciled in but we'll be filled in later when we get to the screen transitions。

 we don't want enemies to do screen transitions， we only want the player to do screen transitions that's going to need to occur in the walk state but we care about the entity walk behavior so we want to do that and then extend it with our own sort of behavior。

So。Okay。

![](img/8fc31d00de36a5a615a661d1a3cd4b84_32.png)

Im just going to duck out for one second。So that sets us up with a room。

 so just right now one single room which is not quite what we saw previously。

 which is an entire dungeon， which brings us to the dungeon update。

 which is Zelda2 so this is one of Zelda's more famous mechanics or I guess themes is the idea of going through various dungeons。

 this is a screenshot of one of the dungeons from the original legend of Zelda as you can see it's got quite an interesting it actually it looks like an eagle or a magic lamp or something but you usually start here at the very bottom center and then the idea is you move up throughout the labyrinth and it can go in a bunch of different directions and our dungeon generator that we look at will look very similar to this。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_34.png)

But as you can see there are doorways linking each individual chamber。

 sometimes not always in the actual game， a lot of the time the doors will actually be locked and you'll have to get keys and the keys are placed strategically such that you have to kind of solve puzzles to find what they are。

 and there's hidden chambers， there's walls that are you could bomb them and open them up and do we won't do a lot of those more complicated things we'll just be looking at a simple generator which creates a simple dungeon that kind of largely functions like this and that it sort of organically evolves upwards from the bottom and can take on various shapes randomly。

What's kind of cool is that this idea is even used in a lot of other games， more modern games。

 for example， the binding of Isaac， which is a rogue light。

 which is a very popular type of genre where it sort of behaves very similarly to Zelda but instead of having manually sort of created dungeons that actually create dungeons randomly and then places various items throughout the duon。

 another part of Zelda which is part of the problem set to get people started in that direction。

 but Isaac's primary focus is a lot more on the items and we won't be looking specifically at that。

 but that is a huge part of what makes Zelda Zelda as well， and so just to get us started on this。

I think it's important for us to look at。Actually getting a dungeon in code started。

 we won't look too closely yet at the actual dungeon generation we'll take a closer look at that in a few more examples。

 but this example will at least get us set up very lightly looking at everything in terms of not just a room but in terms of an actual dungeon so I'm going to close out these examples and then let's open up Z to two I'll just show it folks will notice that it is the same pretty much because all this really is is a data change essentially we're going model things slightly differently。

So I'm going to open up source and if we go to our play state here。

You'll notice that rather than a room now， we are generating a dungeon。

And right now we're not going to show necessarily the specifics of that。

 but we will look at that in more time down the line in particular because we're not actually yet going to show things like doorways and modeling between rooms so we can't actually show the verification of what the structure looks like and I want to actually go through the generator sort of visually。

 but suffice to say this dungeon maker which we'll look at in a few moments。

 generates us a dungeon structure which is essentially a contiguous assortment of rooms。

 if we were to look at the dungeon itself。You'll notice it has a roomss table and then there will always be a current room that should be updated and this particular instance we get set to this particular room at the very start start X and Start Y are passed in。

 we can set that to whatever we want if we want to start the player in a particular position。

 these are manipulable parameters because you might conceive of generating a dungeon such that。

You've determined the player should start here on the left because everything is puzzlewise positioned towards the right and so that might be index1 x and5 y。

 we start the player ultimately at five5x10 Y which is at the bottom of a 10 by 10 dungeon in the center roughly and this is sort of by design to mimic Zelda but you could approach this in any way that you see fit。

 you could start the player in the center and have sort of crawl out from them in myriad directions there is a lot of genres of games like rogue likes or actual rogue lights or whatever subvariety of that that have randomly generated dungeons that do all kinds of various ways of presenting them and generating them and notice we also have a next room this next room is going to be important because their current room is where the players currently rendering and entities are doing things but if we're transitioning there needs to be a next room so the dungeon maintains not only all of the rooms in the dungeon as the sort of two-diional grid of rooms that get stored also the current。

Room gets rendered and updated。 and then the next room during transitions will get loaded。

 rendered and updated as well， just sort of see things。 But ultimately altogether together。

 all we're really doing is now just，ing updating the rather the player and then rendering the room。

Here， whatever the current room is in the dungeon， which is the typical model going forward。

 the player could be rendered in here， but for the sake of this example we're still rendering the player in the play state。

 which is fine。Here down below or sorry he might be being rendered in the current room， I apologize。

 he's actually being rendered in the room， so if we look down here， we go down to the room。

 player gets updated in room and then room gets rendered as well the room itself and then the player right after the room we'll see more extensions on the room as we get into transitions we're going to look at masking and we'll see the player has to get rendered。

And the doorways all have to get rendered and there's some work there that's going to actually simulate or provide an illusion for the player passing through doorways。

 and so it's important that things get rendered in a particular order through here。

So that's essentially the bulk of the dungeon update， which is a very simple just data update。

 the next update being the hitbox update， which as we've seen hit boxes so far have been the sort of AAB collision detection rectangles that allow us to do simple the classic algorithm classic comparison that test where the two things are colliding with one another so far it's been somewhat of a all or nothing type calculation where if we're colliding with something we want a particular specific action to occur if it's the ball with a paddle。

 we know based on just the way that the game is structured that that means a bounce should occur and there should be a sort of inversion of one particular axis of movement。

 maybe a breakout a p it'll be different or if it's a ceiling or the sides of the game space。

 it'll be different。But there's a difference between a hitbox and a hurtbox and folks might use different names to refer to these。

 they are essentially just rectangles that have different semantic meaning in the case of a hit box as we'll call it。

 it's essentially shown in green here as being anything that can be struck by a hurt box or potentially can be collided with another hit box and all the examples we've used so far have sort of used a hit box and hurt box as one and the same but there are many instances most games where they're actually separate in this game this particular example here which is street fighter as your character is moving and doing a kick for example。

 this part of their body should be open to attack， but if they should collide this part of their rectangle with a green rectangle of their opponent then you actually get a hit on them and you can start to do a combo and start to hit them more and whittttle their health down。

In the case of the example shown down here， this is just an illustration of， in this case， hit boxes。

 which are just。In this case， cubes in the case of Minecraft where the math is a little bit more complicated for 3D collision。

 but essentially when you're looking at things in 3D space。

 everything to collide with it or to pick it up and so on and so forth that's going also have its similar own hit box which you could for example with these things you could collide with them and you could pick them up in particular these items here。

 this is a pig so if you were to strike this with a hurt box which you would get with your sword for example in the same way as this then you would deal damage to the cow or the pig or whatever creature or whatever entity and they have different meaning。

 they have different purpose and in Zelda it's the same way if you're moving around your character in the dungeon and you collide with an enemy。

 enemies are all sort of thought of as almost having a hit box or hurtbox that's always active it being just their physical body it could be。

A subpiece of their body as well， you could have creatures that don't hit you if they directly touch you。

 but maybe if they throw something at you like the skeletons might throw a bone at you。

 and then maybe that has a hurt box on it that affects your character but maybe if you touch them directly。

 it won't hurt you generally if you touch an enemy with your hitbox even if it's their hitbox it will still cause damage to you。

 therefore implying that they are like one and not only a hitbox but also a hurt box or they're both sort of overlapping each other at the same time and doing the same calculation。

 but Zelda has the character's ability which is pertinent to swing a sword and therefore have a separate hitbox from a hurt box the hurt box is smaller in the case of the character because it's quite large and at least in this particular tile set。

 the character's sword is pretty small， but you could extend that you can also change the weapon size of your character depending on the game and so on and so forth it's a very tweakable sort of set of parameters so we're gonna take a quick look at how to implement that。

In Zelda 3。So if we go over here， I'm going to close these all out。And then let's go ahead。

Open up to three and let's just show this。

![](img/8fc31d00de36a5a615a661d1a3cd4b84_36.png)

So I'm just moving around， it's kind of the same as before。

 but if I hit space bar you'll notice that we get a couple of rectangles rendering there。

 and then I can do this and you can see it kind of changes a little bit depending on which direction we're moving。

And this is deliberate。Because the interesting thing about sprite art and depending on perspective and various things is that the rectangle relative to the character will kind of have to be handadjusted。

 which you saw even in the street fighter example， the rectangle that was there on the character's foot was very particularly placed and that's by design and people spend a great deal of time focused on identifying the duration of time that hit boxes and hurt boxes are open as well as their span。

 their size， their frequency， their number， there's a lot of details that go into making a game more or less balanced because of the fairness or lack thereof of that character's hit boxes if they're out for too long for example。

 then that character is considered or perceived as being broken and kind of overpowered because the character has to do less to be able to inflict more damage or if it's too small then that character is perceived as being kind of weak and not very fun to play and so it's something that's very tweakable something that plays a big role in the balance of your game。

 you want to make sure that those rectangles are。Adjusted in tune that they visually line up to because if your rectangles are such that they don't look like they're quite overlapped in the way of the actual graphics in a way that is not beneficial to you the player。

 it will feel very sort of unfair but a lot of games like shooters， for example。

 top-down shooters will actually shrink the hitbox of the player such that you can navigate through a bunch of projectiles that are flying all over the place potentially but you'll feel sort of skillful and able to dodge them because they' hitbox is actually your hitbox is actually smaller than your character looks。

 and the projectiles themselves will often have smaller hitboxes than the projectiles as well therefore giving you just a little bit of leeway and wiggle room that you might not see at first glance but leads to the difference between a game being very hard to play and unfair and punishing in a game being very fun to play and more well balancedd and so this is what's illustrated here we've got debuggged rectangles specifically to illustrate this this is very helpful。

 this is a very difficult thing to visualize if you're ever doing。

self and trying to implement hurt boxes， hit boxes， etca。

 and figuring out balance for your game you want to be able to see them very specifically drawn out so that you can tell okay and ideally also frame by frame maybe go through your game and test to see at what point the collision occurs to see okay things are properly working this's the right size okay no we need to shrink that no we need to move that。

 move it to the left move it down。So on and so forth， it's a balancing act for sure。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_38.png)

So what we do to accomplish this is we add a new state to the player。

 I'm going to go ahead and open up in the sources here in the states， in the entity， in the player。

 from the idle state or the walk state， either one。If we press space bar。

 notice that we go to this new state swing sword， so pretty straightforward there。

We're going to go ahead and load this in here， we'll take a look。

 it takes the player and the dungeon， the reason being that we want to be able to in particular compare this hit box with all of the entities。

 the hurt box rather of the sword， with all of the entities in the dungeon and to do this at the time that we create the actual state itself。

 which is an anonymous function recall or it's passed in， it's instantiated。

 it's constructed within that anonymous function within the state machine that's housed on the entity。

We pass it in the reference to the dungeon， and then therefore anytime this wants to call updated or render or whatever。

 it'll have access to the dungeon and therefore all of the entities therein。

 therefore all of the bounding boxes of all of those entities with which we can then do AABB on that hurt box。

So you can see here we have a obviously we have the direction we care about and then we have hitbox Y width and height。

 those are all of the variables that go into creating that red rectangle。

 we've got the direction depending on the direction。

 we set the width and the height differently because if we're looking to the left or the right。

 recall it's more of an elongated sort of vertical rectangle。

 but if we're looking top or bottom it's more of a horizontal rectangle and then also just based on where we look。

 we want to position the rectangle relative to the player in different places。

And then we create a hitbox here which is going to be a rectangle， we store on the player。

 it's a very simple class， hardly even need to really look at it。

 but just so folks know it's literally just a container for a rectangle。

 essentially it's a glorified rectangle。And if we come back here。

 notice that we are changing our sort of sword animation depending on our direction。

 because remember the frames were different in that sprite sheet， we had left looking frames。

 upwards， downwards， rightwards， and so we have this change animation function on our entity which allows us to in the same way that we can change the state machines。

 global state， play state， game over state， etc ceter， we can change the player state。

 and then we can just use string concatenation to programmatically change the state。

 depending on which direction we're looking at to save us a set of four conditionals， for example。

 if player is looking left， if player is looking right， so on and so forth。And then when we enter it。

 well play some sounds， we refresh whatever the animations at because we maintain a consistent reference to the animation we want to make sure that it starts from frame zero。

And then when we update you can see here after we've played the animation once。

 this is how we actually end the animation， there's a counter on the animation which just increments every time it plays every time it loops through and if it's greater than zero well we swing the sword once that's it we don't need to keep the animation looping and playing over and over again。

 which is the default， for example for walking states that's how those states work。

 they'll just loop back to zero once this happens we're just going to change our state to idle and then therefore we'll be able to go back to whatever we're doing and we could also just press space again if we wanted to and then swing or sword a bunch of times。

 we can't really walk and swing consistently we don't have that logic in here。

 we're just assuming that when you swing the sword as as common in these kinds of games。

 you're sort of locked in place and then you go back to idle state and then you can start moving if you hold onto to if you hold onto the arrow keys or WasSD and then here's where we just have our debug rectangle which you could toggle or you could create a flag。

For this if you wanted to， this is common practice。

 you can just have a debug flag that just says if debug on then render these things， if not。

 for the sake of just having the example ready to go。

 it's not set to that but you could absolutely lock this behind a flag or the like and with that now we have the ability to swing swords and then inflict sort of damage。

 we don't have that ability yet because we don't have any entities to inflict damage onto but we have the groundwork laid now the hitbox in question that will allow us to start doing that。

Okay。So now that we do have the ability to use the sword， we do want to start adding the next step。

 the next logical step would be adding entities， things that we saw previously the skeleton spiders。

 so on and so forth， to our actual rooms in the dungeon that will allow us to test that this works properly。

 so to do that we're going to go ahead and transition to Zalda4 which is the monster update I call it。

 which as you can see adds various creatures there and as shown by this half a heart。

 we can collide with them and take damage and inflict damage。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_40.png)

And this theheet， this is a separate spreadritesheet。

 all the spreaditesheets that we've used today were just grabbed off of free sort of public domain。

 Cative Commons assets that are available this a lot of different websites that you can grab things like these from。

 or you could be ambitious and create your own certainly。I'm not a great artist。

 but this is a good enough spreadritesheet for today's purposes and as you can see it's got various different creatures blocked off into these sort of groups of three by four sort of rows and columns and again it gives itself easily or nicely towards a programmatic breaking down using generate quads but it's got different groups of entities and to keep track of okay slime。

 this is the slime you know just looking downwards and looking left， looking right。

 looking backwards so on and so forth， we probably want a way to easily tell which ID maps to which and so similarly to the tiles set I've gone ahead and pre set all of these using the same Python program with an ID and this is just I think a good practice to do but as you can see we have got now a clear way of showing all the individual entities there and we've got the different blocks that they're all grouped up in so we could programmatically look through all of these and see okay the first three for every。

Of the first four rows are the animations down left， right and backwards for this player。

 this player， and then we care primarily about the skeletons and the slims。

 all the actual monsters versus the human humanoid characters。

 but that's essentially how you can think of splitting apart spreadsheets like this and you could still do it programmatically you just have to know what the offsets are。

And so we're going to take a look now at what the。

![](img/8fc31d00de36a5a615a661d1a3cd4b84_42.png)

Process looks like for integrating the character with all these entities and the。

Swing sword state that we just added so we can actually do damage and then we can take damage in turn。

So I'm going to go ahead and close all the examples that are open。

 and then let's go ahead and go to Zalda 4。

![](img/8fc31d00de36a5a615a661d1a3cd4b84_44.png)

Just see what it looks like。So as you can see， we're sort of moving around here。

 if I can still use my sword as usual， all the entities are moving around。

 you can see they're largely just doing pretty simple。😊，igngnoring me type behavior。

 which is by design， we could certainly put pathfinding on these guys and have them come towards me and do so on and so forth。

 similar to what we do with the snail in the last example。

 it's often the case in Zelda games that entities， enemies are pretty sort of just like。

Ambmbling and not doing a whole lot。 So we kind of just took that approach for this。

 There's just two states。 They essentially have a walking and an aislele state。

 much like the player does except these guys will essentially just look for they'll just randomly choose an interval。

Move in a direction if they hit a wall they'll stop moving and then they'll have a chance to either keep moving in a different direction or they'll be idle if I bump into one you'll notice that I take some damage I start phasing in and out that's my invulnerability during that span of time notice I can't take damage and then if I go up to one noticeice I was able to sort of take it out you could in theory if you wanted to。

Designate or illustrate。A slain enemy in this way by maybe having a different sprite sheet or something that's like pile of bones or bat wings or something or slime pile to sort of place there as a game object that might say。

 okay I defeated an enemy there and that's proof that I did that as something that was part of the design of doom。

 for example， back in the day was all the demons and whatnot that you would take care that you would take out they would exist as a sort of they would have their remains around the game space and then you could sort of track back where you've gone through the level sort of like an unintended I mean probably largely intended side effect of that being like good game design for navigation。

 but also just an aesthetic choice that was kind of cool。You could do that here too if you wanted to。

 we didn't make that decision， it wasn't in the sprite sheetet。

 but that's a way that you could sort of verify， oh okay， I defeated X ghosts， x slims。

 X spiders in here， so that shows that the code is working in that way。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_46.png)

We'll go to in this particular instance， most of this is managed in the room itself。

 so if we go over to the also in the swing sword state too， which we'll take a look at。

 but if we go over to the room， sorry it's over in here。You'll notice that we've got a new function。

 generate entities to actually generate them as you have to get placed in the room。

So here they are we've got skeleton， slime， bat， ghost and spider， again。

 all of this sort of creatures that were in this sprite sheet that we looked at。

We're going to generate 10 and then we can sort of grab a random type and then we can do similar to what we did previously with a definition whereby we take the animations。

 the walk speed and then we can grab those from a config or sort of the data file which we looked at previously again that entity def。

lua has all that information so we can keep this part relatively short with all that data we don't have to necessarily dig into the weeds of like okay what's a slime sprite sheet in its indices or what's a skeletons etc ce。

 that's all managed with these keys， these keys are all the same so we therefore don't have to worry about it too much here。

 we do want to give them a random x and a y guarantee that they have a width of 16 and a height of 16 and then a health of one so that when we swing the sword we can deal one unit of damage and then we can check to see for all the entities in the room are any of them less than one health or less than or equal to zero health if they are then we can just remove them from that room and then therefore we have the ability to。

Defeat enemies and remove them from the game state。

So again that gets called and then we have also rendering code here from the actual or sorry this is update code。

 so this is where it actually will do that exact check that I mentioned。

 there is a process AI which is part of the state machine class that we've looked at before。

 and then that's going to get ultimately deferred to an entity state which you can define process AI。

 and then it takes a couple of arguments here， it takes an options table and then deelta time so that it can do whatever you want it to do depending on the entity。

And then here we have the actual code that's going to detect if the player himself collides with any of the entities here。

 and then again we have this function damage of one。

 which is going tick us down half a heart and then go invulnerable for 1。5 seconds。

 which during that span of time essentially sets a flag and the inability to be hit because again here we're saying if not self-top player invulnerable。

 meaning that this won't fire if we're invulnerable。

 so it'll just fail this check and therefore we can't damage ourselves until we are no longer invulnerable。

So if we go to the swing sword state。That we looked at previously。You'll see。In the update function。

This is why we needed to take the reference to a dungeon in the constructor of this state。

 but we are going to iterate over all of the current rooms entities。

And then we can do our classic collision， we can check to see if it collides with our hit box or hitbox again just being a rectangle。

 just a glorified rectangle， willll damage it and then because then it's HP will be zero on the next run through all of the entities in the room。

 it will be taken out of that table， so altogether pretty simple set of code。

 not nothing too complicated a lot of the things we've looked at already just collision and then now we've just got a hit box。

 we've got a few checks for invulnerability and the like。

 but altogether things are coming together quite well in terms of our ability to hit enemies hit entities and then also to be hit by entities。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_48.png)

So the next sort of phase is going to be the trigger update。

 the next major update and a big part of Zelda is besides just being in a room using a sword to attack enemies is's also getting through the dungeon and getting to the end of the dungeon and so far we've been in a closed room but now we'll take a look at actually a doorway or doorways in our dungeon。

 won't be able to move through them just yet， but just to illustrate the idea of opening a door recall in the example that we did the start of the lecture they all start closed which is common in Zelda you usually go into a room you usually have to defeat a certain number of entities or enemies。

 we're not taking that approach although you certainly could you could just do for do a loop over all the entities in the room if it's equal to zero then open the doorways that works fine today we're going to just look at using triggers which is similar to what we did last time when we looked at game objects where we had a game object to represent the block that you could then jump up hit that would trigger a gem。

To spawn if you collided with that gem， you would then get some score。

 youd get an increase to your score and so on and so forth that is essentially the gist of what we're going to do here。

 we're going to define some game object a trigger a switch and then on collision with it it's going to have its own oncollide function that will trigger the opening of the rooms doorways pretty much just that simple so we'll take a look at how it works here in Zelda。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_50.png)

Five， the trigger update。So I'm going to go ahead back to my code here。This goes all these。Here。

When it was all to5， let's just test this and see what it looks like。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_52.png)

So you'll see it's kind of the same as before we do have two doorways in this instantiation。

 this dungeon generator is going to always be random and so again it starts from the sort of bottom of the screen。

 but if I were to besides just hitting creatures， I could certainly do that the doorways are closed notice and right now even in this example even when they're open this won't do anything but this is just how the behavior will normally be if you're going up to the door and it's closed you won't be able to move through it。

 but as soon as I step on this trigger， this switch。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_54.png)

Notice that it plays a sound and it also opens the doors at which point now it isn't implemented in this example because we're going to actually show it's part of the bigger conversation about how to implement scrolling。

 which is one of the most complicated larger features of this particular lecture。

 but we do have the foundation now to trigger those sorts of behaviors in our room。

 so it's similar in spirit to what we looked at last week except we are doing it in a different use case。

So if we go over to Zelda 5， this will be in the room。

Now I want to take a look for a second at doorway because doorways are now going to be a more important aspect of what we look at。

 although the doorway class itself is pretty simple。

 doesn't really have a whole lot going for it other than that recall when we look at the sprite sheet。

 it was four tiles that needed to be rendered to approximate or rather to represent the doorway despite the fact that all of our tiles are 16 by 16 if we were to run this again and pay attention to that fact you'll see that the doorways actually are larger than the walls the walls are 16 by 16 so therefore the doorways represent an object larger than the tile size and so that's totally fine and valid in order to do that in a strictly sort of consistently sized tile set which is common you'll want to just represent it with multiple tiles and so therefore you' have the two bottom tiles being the main parts of the doorway and then that arch the top of that arch is represented with two semitransent tiles on either side that get drawn in conjunction with those tiles。

So if we go back here。Rather， we're already in doorway， we do have it set up here。

You'll notice here that we're going to essentially set our XY width and height based on which direction we set the doorway to。

 it's going to be part of the constructor here， we'll say left right。

 top bottom and then down here in render again we're going to just get a reference to textures and quads。

 we have an offset that we can draw at which is just part of making sure our map is centered in the game world so we just pass in offsets。

And also when we're scrolling rooms together back and forth， those also get an offset added to it。

 which allows the doorways to sort of move as we're transitioning rooms rather the player from one room to another。

As you can see here， if we're looking left， then we're going to want to， if it's open。

 draw a particular set of tiles because recall there were there's four tiles per doorway and we'll open up the doorways here。

Rather， we'll open up the texture。I'll show the numbered version again。

But you can see there are actually actually in this spreadritesheet there are than more than one variant even of doorways。

 they even included gated doorways but as you can see there's a 153。

 154 being like top doorway closed but then if we were to look here 117118 is top doorway open you could use that for either of these the sort of graded or the wooden doorway。

 you could have this semantically be for example， I can envision this being for enemies if you go into a room and there's bunch there's like an arena or sort of like you have to defeat all the enemies to leave the room as sort of hitting a switch。

 you could use this doorway， just sort of visual way to signify the meaning of that room。

 but that's presumably why they incorporated it but it is different these。

Tiles here are different from these tiles， the shading is different in particular， if you notice。

Versus the ones that are sort of like here at the bottom， again， the shading is different。

 so they do have slightly different aesthetics to them。

 even though they are very similar on the surface。And so there are four per and then there are also。

There is essentially four per and then a variant of both sides top left right top bottom that have the door open。

 whether you're using a grate or using a wooden door and so that's why we have to draw things in this way where we have essentially four tiles and you can look through the you can consult through the indices of the attached tile sheet to verify these indices yourself for the sake of just keeping it rather condensed here。

 there's so many of them we' just using the numbers， but you would probably put these as constants。

 but they would get quite bloated here， so just for the sake of illustration and also just to illustrate the fact that we are indeed using the numbers that we can see here on the tile sheet。

They have been included just as the numbers so folks do I encourage folks to look through all of these and see how we're arriving at these 16 by 16 tiles versus when when we're using the direction in conjunction with the open flag on the doorway so that's one detail。

And that open flag is just what's gets set on or off if we were to hit the switch。

 and so this is a good opportunity to again look at， for example， the doorway。

 I'm going to close some of these files here， sorry。

 not the doorway if we were to look at the game object。

The game object is not all that different from last time where it is essentially just a container of fields or flags and it has a reference。

 of course， to its XY width and height and the ability to render itself。

 but again an empty oncollide function is presumed in here so that we can call oncollide of whatever object we want to。

 and then it will just not do anything by default but we can override this through definitions。

 so if we were to go to game objects。 Lua。For example， this isn't where the function is defined。

 but this is where you in theory you could have some sort of way of defining functions here for your designers。

 we're not choosing to do that do so here， but this is where we are again with this theme of like sort of more data-driven design we're going to try and keep as many of the pieces of information that tie to the switch inside this config。

 this sort of definition file as much as possible， it's got to type， a texture。

 you can put whatever data in here that you want as long as your code references these flags and these get preserved then can the sky is the limit。

 you can do whatever you want with these things and then make them as powerful as you wish and give your designers as much。

Flexibility and creativity as you， as you would like。 You can even see here there's a state set of。

A table where we can actually index into depending on our state and get the texture。

 the frame for that object depending on what state it's in。

 which recall from last week when we talked about hitting blocks with Mario。

 this might be how you could do that too， you could have hit and unhit and change the blocks texture accordingly。

 we didn't do that last week though I alluded to as much。

 you could do it accomplishing just this exact sort of approach。

And then so if we go back to our room again。Recall we create the entities and then we also need to create the switch。

 which would be in our game objects if we have a game objects table that'd be the ideal place to do it。

 and indeed we do have a generate objects function here that's been added。

 so we'll just scroll down a little bit here。Past generate entities。

 and we do indeed have a sort of instantiation here where we're creating the game object。

Passing it in the game Object depths of switchitch， which is just what we looked at。

Giving it a random X and Y that we know will be within the bounds of the map。

 bounds of the room rather that we're in。And then we're going to define that on collide function ourself here and say if it's pressed or if it's unpressed。

 then we want to set it to pressed and then set all the doorways open to true and then play a sound that way as soon as our character collides with it。

 it triggers that state， it triggers the sound effect and then all the room's actual doorways which it has a reference to will then get open for us and everything to sort of works nicely in harmony。

And so with that， that's essentially all we have to do in order to have entities and objects that now sort of talk to each other and as much as like our character can now interact with it by iterating over all the game objects and then triggering the oncollide function should we collide with it。

 and then we now have the ability to open doors， press on switches。

 you can now do anything you want with any sort of number of game objects as long as they have a reference to the dungeon or the room or whatever that they need to manipulate so that's that。

Okay。Good。

![](img/8fc31d00de36a5a615a661d1a3cd4b84_56.png)

So this sort of takes us now to。The more， I guess interesting visual and more complicated aspect of the lecture which is the characteristic Zelda scroll between screens。

 which is a very common I think mechanic that when people see it they immediately think oh that's legend of Zelda that's Zelda game and here's an example of this sort of version before we get to the final version where we're seeing a scroll albeit somewhat visually not quite perfect because the character is clipping through the wall right here。

 we don't want that to quite be the case but we are indeed seeing here a transition between two separate rooms so we have whatever the current room was up here and based on the character's direction they're facing down so it's clear that they're moving down the movement in this example is automatic so this is similar to how the original Zelda works and most 2D Z this is as far as I'm aware when you transition screens your character will sort of move automatically towards the next screen and get placed in a particular destination at that particular point in time。

It is ultimately like a little bit of illusion involved here because we have to essentially keep whatever our current room is and then。

There's usually never a next room loaded until we choose a doorway that we then move towards and then at that point both of them being loaded。

 we then perform a transition， a camera transition from one to the other and then we sort of instantly flip our position right back to zero and then that becomes the current room because there needs to be another next room later and so in order to have the sort of current room and next room which are functioning very similar to pointers in a language like C or C++ if you want to think about it that way。

 you have a pointer to a room that can be null and then a pointer to the current room。

 and then we need to essentially swap pointers such that the next room points to nothing so that it can be set to point to something when we do whatever the next doorways transition is and so we get the next room loaded we move towards it。

 it'll be off camera but we're gonna to move the camera position to it and then we're essentially set everything hard to zero and we won't see that happen because it going to happen right at the second。

Right at the moment that we get to that position perfectly where the next room is and so we're essentially almost similar to flappy birds looping where we sort of were moving the texture sort of left to right and then we would hard set the texture back to zero at a certain loop point we're doing a similar idea here just a bit more complicated of a different result but it's similarly captures that idea of making the human belief that they're looking at a movement that is in this sort of larger space but really they're ultimately ever within zero to largely between zero and virtual width virtual height and then they might briefly go up towards negative virtual height down to positive virtual height and then left and right virtual width positive virtual width off camera but they're never going to stay there they're always going to then immediately be sent back to zero zero so that they can do that next room magic to accomplish this we're going to use events and so this is an opportunity to look at what it means to have an event and an event handler but when we touch a doorway we're going to want this sort。

of like actual event to fire， which is， oh it is time to shift bottom left or it's time to shift down left。

 right top in whatever direction that is， and then have the game。

 the camera essentially tween itself up to the next room which is going to live there for a bit and it's going to be in memory and updating and so on and so forth。

We're going to want to actually trigger an event that gets handled by some function that does that behavior and then resets everything for us and then we trigger that event at the time that we touch any open doorway。

 and so to accomplish that we can just use essentially a library knife which is what we've been using。

 but can also you might hear the term dispatch like you dispatch an event or you emitted an event we'll be using a function called event do dispatch in this particular example。

 but there are multiple ways to sort of word these functions in these ideas。

But you essentially just have this string for all intents and purposes that gets listened for which is like shift left。

 shift up， shift down， shift right， and then there's a function that gets associated with that key。

 that string， which just gets fired， it's always listening essentially and then at the time that you call event do dispatch it essentially says okay。

 trigger the function that was there assuming that we pass a string into dispatch。

 like event do dispatch， shift left， it will listen for okay。

it will call whatever function that we said you should listen for that this shift left shift up。

 shift right， shift down event and call this function for we'll see this implemented and these again use anonymous functions which we've looked at in many instances already。

 which is a common theme， especially in dynamic languages like Lua or like JavaScript you'll see this a lot so we'll be looking at event which is another part of the knife library so we had a knife dot we have the timer class so far。

 knife dot timer this will be knife dot event and so we have event do on and then event do dispatch on being this sort of way that we say okay when we hear this string call this callback function。

 so this is where we essentially set up events that are capable of being listened for and then event do dispatch is our way of broadcasting。

 emitting this event and should it be being listened for there will be some function that gets called this callback that will trigger and then that behavior will then issue forth。

At that moment and in this particular instance， this particular repo will be looking at just handling all of the movements。

 the shifting with events just to illustrate how it works。

 Here's a visual that illustrates what screen scrolling looks like in the original Zalda which you can see it's very similar to what we saw previously notice that link is moving from the left to the right and then as soon as hits just the right edge there there's a transition and then he gets placed here。

 He's on the opposite end which is important when you move your character over because remember we are sort of resetting everything to 00 like you can imagine this being 00 and then it there's a camera shift and then this is sort of off screen。

 but then this now becomes 00 again， this happens to be an infinite infinitely repeating terrain so it isn't quite illustrate maybe the fact that you have different screens that get reset to zero0 ideally but it does capture the idea where you have an offscreen target screen。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_58.png)

You're going to move towards it over some period of time and then now we're at 00 again。

 it just get hard reset and then just get like we got tricked into thinking that we moved。

 but in reality we moved， and then everything got renormalized， recentcentered in game space。

So that is the gist behind screen scrolling， we're going to take a look now at the implementation。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_60.png)

And it's going to be a bit of code， we'll look at most of the details。

 but there might be some amount that folks are encouraged to explore on their own。

 but I think the gist of it is going to be relatively digestible here。

 let me just go ahead and close all of these。And then。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_62.png)

Make sure this is closed and then we're just going to run it。And as you can see。

 everything is kind of functioning the same way that was before， in this particular instance。

 there is no dungeon。

![](img/8fc31d00de36a5a615a661d1a3cd4b84_64.png)

Okay rewin that。I think you can say something like。OneOkay。I don' probably not。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_66.png)

So we're just going to go ahead and run it here， so I'm going to go ahead and do this。

And you'll notice that we have everything sort of before we have the switch。

 we have the slims and everything and the enemies， if I hit this switch here。

 we'll do the classic sort of switch opening the doors， but if I move here。

You'll notice that we do indeed now transition from that bottom room up to the room that was above it if I hit this switch here。

A lot of monsters in here。So I hit this switch。And then I move down here。

sameme thing sort of happens。 And essentially all we're doing is we're just moving。

We are loading in the room that we are moving to relative to the current room。

 the current room is always at0 zero， it's always the center of the world。The origin。

 and then we're loading in the next world。Sorry， the next room and then we're going transition to it。

 the camera is gonna to move towards where it is going be offset by some virtual height or width depending on which axis we're moving towards。

 and then that room is going to have everything in it。

 including the player being reset relative to zero0 at which point then we can then do another move to a different adjacent room which will have a different offset will do the same thing that room will get set to zero zero but everything is functioning as intended。

 the only thing that is not currently working properly is when we move through the wall we do indeed just kind of clip through the wall which is an ideal behavior and so we're going to have to fix that that'll be the next example。

 but let's go ahead and take a look at what we're doing here to accomplish this transition。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_68.png)

So if open ups all to six， and then we go to the play state。

Actually we probably don't even need to go to the play state。

 we can take a look at the play date very briefly， everything here in here should be the same largely。

 we are just getting the dungeon maker and so on and so forth。

 the thing that we want to look at is going to be in the room ultimately so if we go to room，😊。

And then。In here。If we。Sorry， it's in the。I think it was in here in Play state。

 right so I could just transition to。Transition right to， it's actually in the entity。

It's in the player walk state is where the transition actually occurs。One second。

All right so let's take a look then how we're going to accomplish that transition。

 so we are only triggering it when we're walking， so we'll actually end up triggering the animation when we're in the walk state of the player。

 the entities can't do this， so we're going to go ahead and look at the walk state here really quickly。

You'll notice that we have this big block of code in player walk state towards the bottom of the update function where after we perform that sort of static dispatch to the entity walk state update function。

 we're going to then sort of say， okay， if self-do bumped。

 which gets flagged if we did collide with a wall， we're going to pretend as if we're colliding backwards in the direction we're moving to test if we're actually walking into a doorway。

 which is because when we get bumped， we end up getting shifted out of the wall so we're going to look to see are we in the doorway。

 and if we are， we're then going to dispatch the event shift and then left， right， up。

 down whichever direction we end up actually walking towards。

And this is going to also need us to make sure that our Y and X get shifted so that our character is directly centered with the doorway because we can。

 in theory， collide with the doorway just a little bit off of it like a couple pixels。

 but if we do this next transition that we're about to do this walking of the player from one spot one part of this room to the next room。

 and he's not directly centered in the doorway in a way that we're going to stencil in on the next example。

 he's going to look as if he's just like fading kind of clipping through the side of the doorway。

 which we don't want， so we're going to force the character's y or X depending on which direction they're moving into the doorway to actually be directly lined up with the doorway。

And so that's going to dispatch the event shift left， which if we go to Dunngeon。Not doorway。

 but dungeon rather， you'll notice that in the constructor we do set these four event do on functions。

 these event sort of like handlers here， they're anonymous functions again。

 but we have this function this deferred call to self begin shifting at negative virtual with zero or virtual with zero or zero negative virtual height and these are like full screen offsets because these model。

 the transition between this room and then a full screens with or height away to a different room。

 and so that's where this begin shifting function will actually allow us to do so if we scroll down we'll see begin shifting here takes in an x and a Y and then we're going to get whatever the next x and y is in the sort of the table structure of the dungeon to determine which room is there because it's going to have entities and we're going to transition towards it。

All of its doorways will be flagged as true to start with when we are moving inside of it。

 it doesn't make sense if we're moving into the next room and as doors are closed。

 but we're clipping through them so they're going to start open and then it has this adjacent offset which gets added to all of its render operations。

Such that when it gets rendered as a room， including all the entities， the doorways， the tiles。

 it gets added this offset， this adjacent offset， it's called adjacent offset because adjacent to main。

 the current room at the time that it has this value。And then what we can do is also figure out。

 okay， when we are rendering that room or at the time or the value we should twinwe the player to specifically。

Ot to end up in the opposite room that he is sort of moving through as we perform the transition so if the player is moving up。

 for example， then the player is going to end up at the lower part of the next room or if you have two rooms player moves up is going to end up here at the bottom of this sort of top room and so that's all this code does it just inverts whichever direction the player is moving it's going to place the players and final X Y at the opposite part of the next room when it finishes there's a tween here。

 this is doing a lot of the heavy lifting for us with the actual movement of not only the camera which is done here。

 recall timer ten takes in these tables or it takes in as a table。

 these sort of values that have these are assumed to be tables and their member sort of fields here。

 have to get actually set to whatever their destination value is that we want a tween and in this case we want a t over one second you could make this however long you want you could make it two seconds。

So faster 0。5 that's going to ultimately affect the speed at which the transition takes place。

 but the player gets their x and y set to whatever that X Y we just look we just talked about is。

 which is going to have been perfectly set by our little shift that I just talked about when we actually collide with the doorway and then the selfca X and camera Y are also going to be between towards whatever the shift x and shift y are。

 which is going to be again it's going to be one value is going to stay the same as is right now is0 and what the other is going to get set to the positive or negative virtual height or width depending on its left or right。

 top or bottom that we're going to move to， we can only move orthogonally in one direction。

Once it's finished， recall that timer Ten can take a callback。

 it can be given a callback of or it can be given a function or invoked to call the function finish which takes a callback function at the time that the Ten finishes。

 which is selffinish shifting， this is the illusion part of what we talked about if we look down here just a little bit。

 finish shifting just sets all everything to zero in the current room。

 it essentially sets the current room to the next room here。

And then it just sets the nextroom to nil and then sets all of the Xy values that we've been interpolating to move with lovedog graphics do translate to whatever the next position is。

 everything gets set to zero， and so we've tricked the player into thinking they've moved some distance into the dungeon when in reality they've gone to that room and then that room gets。

Rendered and set at0，0。And so if we come up here just a little bit。

This is that shift sort of code as well。Wwhich gets reset once we finish once we actually finished。

 we're going to want to set the player based on where they were when we finalize that last shift。

 we're going to actually set their direction to left。

 right up down depending on where they ended up in the map and then we're finally going to close the doors and then reset switches because if you go were to go back to a previous room all the doors close automatically but the switches don't get reset then you can't actually leave the room。

 this was a bug that I actually encountered and I thought it was kind of funny so yeah you want to make sure that you reset all your switches and close all your doors and then you essentially retrigger the puzzle that was there in that last room when you initially when you initially did the transition。

And then as you can see here， if we are shifting， we do perform that love。

 graphics translatelate of that camera X and camera Y， which again get interpolated with timer。

 Tween， which allows us to perform the transition effect。

 and so with that all that logic we then have this ability to detect a doorway collision。

 move towards the opposite point of the adjacent room。Once we've finished that with timer。

 Tween doing the heavy work of actually interpoolating the player's position notice the player was moving during the animation and the dungeon itself was shifting the perspective was because of the camera。

 once it's all been finished with timer。 Tween， the thing we looked at previously in other lectures。

 we can then say， okay， once that's done， set everything to zero。

 normalize it and then prepare our room or our dungeon such that we can then。

Collide with another doorway and set an next room to be some other door or some other room in the dungeon。

 allowing us to repeat this process add intofin item until we just decide you know we're done with the dungeon or we reach the end or whatever。

 but that's the process by which we can implement scrolling So the last sort of。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_70.png)

The last sort of phase that we can look at。In our implementation of Zelda。

 before we also take a second just to look at the dungeon generator is going to be the stencil update。

 which just allows us to effectively accomplish exactly what I pointed to previously notice that in this example in this screenshot。

 I've purposefully taken the screenshot such that the character is transitioning between this room and this room you can sort of see in this little peekcon just a little bit there。

But you can see there's， you know。No overlap with this archway。

He's just being drawn right there as is， and we're effectively this with accomplishing this with a sten。

 what's called the stencil buffer or masking， which is where we're essentially setting some pixels。

Behind the scenes to be the sort of invisible mask that prevents pixels from being drawn。

 should we do a certain set of calculations with that stencil buffer which we'll look at in a second。

 but we can effectively just draw an invisible rectangle that's here that is essentially flipping of the pixels and that buffer。

 sort of pixels quote unquote， these values in this invisible buffer to say， okay。

 if we try to draw on top of any of those flagged pixels。

 don't draw anything therefore if we draw on top of draw first we draw these archways。

 these actual graphics we want to render and then do the stencil operation。

 we can then say we can then ensure that nothing can be drawn on top wherever that rectangle is that we drew。

 therefore trick the user into thinking that we are actually going through this hallway with depth when in reality we are just masking out the pixels that that character is trying to draw onto the screen。

And so this is essentially just an image of what a stencil really is and you can sort of think of the stencil buffer。

 you can use the stencil buffer in many different ways。

 this is just sort of illustrating the concept of what a stencil is。

 which is just some sort of nontransent material through which you can look through， for example。

 and then draw。with a particular bound in this case a circle heart and a rectangle。

 but if you were to try to draw on this white for example。

 I mean this is some sort of non permissible material you would not actually draw pixels and that's effectively what we're doing except they' are just sort of invisible to us we determine how they get drawn and we can show I'll show you a debugging tool to sort of illustrate that。

But another way to look at it too in a more technical terms。

 and this is taken from a useful blog on direct X， but this applies to OpenGL and Vulcan and any other graphics API。

 but you essentially at the time that you're going to try to process pixels by either the pixel shader or the fragment shader。

 which is a stage of the GPU's pipeline where it calculates color value。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_72.png)

There's a step after that before it actually renders it to the screen or to a texture to some device where this thing called the stencil buffer。

 which also has this thing called the depth buffer。

Gets tested and you can test it in various different ways。

 you can test for equality for less than classic boolean type operations。

And you can perform draw operations onto it as well to affect those values so we can set。

 for example， this ring of ones in the stencil buffer if we assume these are pixels。

 this is the same range of pixels but these are the stencil indices over those pixels and we were to set these to one and then set the stencil operation to the comparison function of equals。

 meaning that anything that equals one will allow through pixels， you end up with this result here。

 which is that now you've drawn a ring of pixels to the screen， because those past the function。

 the stencil test as it's called in which love2D has the same API for that we've defined at the time of the intermediate stage between the pixel shader the fragment shader and the render target as it's called in direct X。

Here's another example of how to sort of use this dentalcil buffer for cool effect。

 this is a common effect used in various games。Virtually unlimited ways you can use depth and stencil testing to do certain really cool things。

 but in this case， if you imagine drawing these cubes first and you wanted to draw an outline around the cubes that in this sort of abstract way using this color。

It's normally quite a difficult thing to do， but if you just also at the same time that you draw these cubes。

 also draw to the stencil buffer， which again there's a pixel。

 there's an index on the buffer on top of your screen。

And you were to set these to one and do some sort of comparison of less than， for example， on that。

 than anything that you draw at the next stage。That is going to and set those to one。

 so if it's not less than one effectively it's not going to draw anything at the time that these rectangles or these cubes get drawn。

 you just scale the cube out a little bit you keep the cube where it is scale it a little bit and then draw again with the stencil preventing the prior pixels from being written to because you just don't pass that stencil test but you set the shader to draw the green color now you can get this outline because the stencil buffer is effectively preventing you from drawing where the old cubes previously drew even though normally this green rectangle would be drawing over those if you think about drawing just over whatevers already written to the screen。

Portal uses this to a really cool effect in that through stencil testing。

 they ensure that the current scene doesn't get drawn over wherever this particular texture is here instead there's a stencil operation that then will try to draw another scene such that the stencil buffer will only allow in that scene where the pixels that were previously written to the stencil buffer permit that operation。

 and so therefore you get this sense that you're actually looking through looking at two scenes it wants effectively。

 you have this main scene and then you're rendering another scene again by you're only rendering it through this portal here allowing you this sort of sense that you're defying Euclidean space and able to go through different places。

 which is a really cool effect， they use a combination of stencil and depth testing to achieve this。

And so with love。This is also an interesting time to talk about love 11 versus Love 12。

 they have two different ways of doing this， sort of love most of love 12's changes which is coming out soon are。

Easy to sort of create a version of that permit compatibility with love11 and love12。

 Love12s stencil changes are not backwards compatible with Le 11 so we've included both a love11 and love 12 version of the code in the same files and we're going to be looking at both。

 but essentially they operate very similarly where you have a love。 graphics。 stencil function in 11。

 which takes a function that draws to the buffer， whatever you determine with the operation that you specify。

 and then a set stencil test which then does whatever the test is that you care about to determine。

Do the pixels get to draw to the screen depending on what the sort of state of the stencil buffer is or the operation is in Love 12。

 there is no longer a function that you pass to a lovedo graphics stencil。

 you have a set stencil state which takes it's a bit more of a lower level version of doing it where you specify an action a mode and then a value and optional value and we'll take a look at these examples and then you don't have to use the set stencil test or stencil here。

 you just have the one function， set stencil state。And then you draw whatever you want。

 and then depending on what you've set the stencil state to。

 it'll be either a stencil operation or a regular operation。

But there's also this lovedo graphics that set color mask up。

 which is important because now that we don't have this dedicated drawing function that handled this for us。

 it handled color masking for us， we actually have to prevent drawing to the screen while we're drawing when we're trying to set bits in the stencil buffer。

 such that we don't draw and also set the stencil buffer。

 which will have the effect of drawing for example like white rectangles onto the screen which is not what we want。

 we don't want to draw anything physical to the screen。

 we just want to draw effectively affect the bits in the stencil buffer and then perform an operation that test for that and allows us to draw or sort of preclude us from drawing pixels of our character onto the screen based on those rectangles that we saw。

 which is a lot to essentially just say。That we now have a buffer in memory that we can manipulate to mask colors that we draw onto the screen in other draw operations。

 which we'll take a look at here now with Zelda 7。

![](img/8fc31d00de36a5a615a661d1a3cd4b84_74.png)

So let's go ahead and open this up。Here。I'm going to go ahead and open up Z to7。

 and then we're just going to test it so we can see it in operation。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_76.png)

So we have the usual it's going to take a bunch of damage now I'm going to move through the hallway here to the left and you'll notice as I'm moving through。

 we do indeed sort of have this illusion that we're moving through a corridor because our character is being masked out while he's moving through the corridor so if I do it again and then'll move up。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_78.png)

You'll notice。Just clips。Does not clip through the wall， just actually gets completely not drawn。

 he's still moving， everything is still there and the draw operation is still happening。

 but the stencil buffer is essentially not allowing those pixels to affect the screen。

 the render target。At the final stage of rendering。So if we go over to Zelda7。

 this is going to take place in the room。So if we go to。Room here。

And we're going to scroll down just a little bit here。There is a render function。And so。

You'll notice that we have we've included two different versions of this code that you can see how it works between the two and then as love 12 comes out。

 the love11 versions are technically deprecated， so you will get a notice saying that you're using a deprecated version。

 you're going to want to use the new version in Love12。

 we've deliberately turned off the deprecation error which you can do through this code here， Love。

et deprecation output false， but just for folks that might be using love 12 in the future。

That's something that they might notice， so we've included both versions， the love 12 version。

 I would recommend folks move to that version over the loveve 11 version。

 but just for right now since Love 12 is technically not out just at this moment。

We're going to go ahead and reopen up room， so the level 11 version it takes in a function and then replace is what's going to happen to the stencil buffer and then one is what it's going to replace it with。

 so we're going to replace whatever we draw here in this function。

 which is four rectangles and they're going to be at the doorways between essentially the tops are just the edges of the doorways and the next where the next doorway would be when we do a dungeon transition。

So that's what they're going to be set to， that's these all these functions here。

 all these rectangles rather in this function are going to be performing this replace one operation。

 you can do this with shapes， you can do this with images if you want more fine- tuned。

 specific per pixel image， arch， fancy sort of masking， you can do that with images。

 but we're just doing it with we're just doing it with。

Rectangles kids always effectively need to accomplish the goal。

 and then when we set the stencil test to less than one。

 then that means that anything that passes less than one。

when that character or when whatever gets rendered is being compared against the stencil buffer will go through。

 meaning that because we replaced all of the rectangles with one in the stencil buffer at the doorways。

 it's going to fail the test is going to be equal to one。

 therefore when it tries to draw the player and the player's pixels are on top of those parts of the stencil buffer they're set to one。

 that failure means that essentially skip it won't skip the rendering process but it will skip allowing those pixels through to the final result。

 therefore making it look as if the player is going underneath that sort of dark tile a dark archway。

 and then the love12 version。I'm just going to go ahead and comment out all of this here。

The love 12 version， if we uncomment all of this。Whoops。I' mean to hit that。Meant to hit that。

You'll see that it's pretty similar except we are setting the color mask to all falses because now when you draw things to the stencil buffer。

 you need to actually make sure that you're not also drawing because it does it in one pass now。

 it will draw to the stencil buffer and also draw to the screen during that span of time and so if we want to draw rectangles that are stencil affecting but not like actually drawn to the screen。

 then set false to all four components of RGBA color here means that don't let those through when we try to draw that color it'll just draw completely nothing。

 you can set just red to false meaning that no red will draw which will sort of change how your color gets colors get rendered。

 you can turn off individual channels this way and affect different color effects。

But this is essentially just ensuring that we don't draw anything to the screen when we render things。

 and then this set stencil state is performing the same thing as that stencil function was previously。

 where we're setting replace to always。Of one， so we're going to replace every pixel。

 there's no condition， there's no checking of anything these you can do a lot of various functions to do certain tests and different more complicated ways of affecting the stencil buffer but in this case we're just going to always replace the pixel that's there in the stencil buffer pixel with one and then we're going to draw those rectangles the same rectangles again our mask is on false on all four components of color nothing's getting drawn。

 we're going to set it back on and then we're going to keep whatever and this is the default operation that previously love 11 was doing we're going to keep all pixels that are less than one when we draw hereafter that the stencil buffer is going to see is the value of the stencil buffer less than one if so permit drawing if not。

you know， forbid drawing， therefore when we render the player and we try to draw over those rectangle affected parts of the stencil buffer。

 the character is not going to draw where those pixels interact with the stencil buffer in that way。

And then set scilate here， just resets it to a blank slate effectively。

 so there is no more stencil operation occurring。And that's the difference between 11 and Le 12。

 they function identically and there's even some debug drawing here at the very bottom and so I've added a flag that you can test for if you wanted to see the rectangles actually drawn to the screen and what they look like。

 I believe I said it to D or R， let me just confirm which key I used to draw。😊。

Some the update function here should be。Which is a S， S for stencil。 that makes a lot more sense。

 So let's go ahead and render this。

![](img/8fc31d00de36a5a615a661d1a3cd4b84_80.png)

And then if I hit S， you'll notice that there are four rectangles that get drawn there。

 those are debug rectangles just so we can visualize where we're affecting the stencil buffer because again we're not trying to draw these to the screen。

 that's why we set the color mask in the love 12 version but if we are not sure exactly where the mask is being set properly and we want to just debug for ourselves and again similar in spirit to the collision rectangles for the sword state and whatnot and for our hit boxes。

 this is a good practice to have the debug way to sort of do this on a keystroke I can just set this global flag。

 this boolean that says you know if some flag then just draw literally draw these transparent red red rectangles and then if I hit the switch here and then we just go up to the top。

 you'll roughly see although it's kind of slow to see but right us soon as we go underneath that rectangle we are indeed not allowing players pixels to draw forth onto the screen。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_82.png)

And so that is how the stencil operation works effectively between Le 11 and Le 12 I recommend folks using love to go to Le 12。

 though Le 11 will still work probably for a while。

 but it is officially deprecated at the time of this lecture。😊，And so the final thing to look at。

 I think， is just we haven't really looked at the dungeon generator too much。

 but that's something I also wanted to spend a couple of minutes just looking at very briefly before a couple of little side topics and so we can do that through I ahead of a separate。

Implementation in here called Dunngeon。And the purpose of dungeon is just to provide a visual way for us to see how the dungeon generator actually works。

 so I'm going to fire this up。

![](img/8fc31d00de36a5a615a661d1a3cd4b84_84.png)

And we'll see that it's a pretty simple UI， but we have a 10 by 10 grid。

And we're using a queue in order to do this。 there are many different ways you can generate mazees and dungeons and whatnot with stacks and cues。

 we're using a queue because it gives us kind of some nice properties that align well with the sort of aesthetic of Zelda。

 but if we look at some of the information around the screen。

 we can see that we're in the start phase。We have our headset to one， we have a Q length of zero。

The head is going to be set to the index that we're always going to be looking at。

 so our queue is essentially just an array of these coordinates that we're going to look at that get randomly decided and we're just going to iterate through them one by one we're not going to do any removing from the queue we're just going to keep adding and then keep incrementing the head and then what that's going to allow us to do is eventually the head if depending on how we want to implement things typically you'll never get to the head reaching the end of the queue in this example sometimes you will。

 but effectively the theory is you want to aim for a certain number of rooms to generate or for so many rooms to eventually generate and then your head to crawl through all of them and test for neighbors to generate。

contiguous rooms that you eventually determine， okay。

 we've reached the end of the queue now we can just consider it the end of our dungeon generation If I press enter。

 we'll see the very first room is going to get placed kind of at the bottom center， which is at 5，10。

And so I have a red cursor there that's just going to illustrate that that's where we're currently looking。

 there is a visited array table at the bottom right。

 which is just going to be a way for us to confirm that we have already generated rooms at a particular index so that two rooms that try to spawn new rooms don't try to both right to the same spot they'll check an array and they'll say。

 okay， we've already visited5，10。We don't need to add a room 2，5。

10 we have a Q length of one right now。Right now what we're going to do and this is what's going to happen every time we iterate through each room is we're going to check all of the orthogonal neighbors。

 top left， right and bottom and unless we're at the edge and we're not going to check bottom here but we can see we're at current 510 we're going to check for example。

410， we're going to check 59 and we're going to check 610 and what this is going to do is if we randomize which of those we decide we want to actually place in the map。

 we could place all of them every time and what that's going to do is just eventually just going to grow in this sort of symmetrical uniform way。

 this dungeon out but that's not ideal behavior because everything's just going to always end up being the exact same。

Sort of layout we want an organic varying aesthetic and distribution of rooms and this sort of feeling like every dungeon is different so there's a weighted chance there's a 40% chance that a direction is skipped。

 meaning a 60% chance that any one direction will be chosen。

Such that there is a randomness to choosing different paths for every room that gets added Now there are some caveats to that approach being that like if it is random purely then you could theoreticaltically just at the very outset。

 not generate any rooms and then have just a single room dungeon and that would be a bug in the implementation and so therefore this particular instance is going to use that implementation but the code will ship with a version that actually is fixed in Zelda 8 whereby we actually do ensure a certain number of rooms get generated and then if we don't have 10 rooms generated by the time that even that runs out then we can just crawl through our structure and add rooms wherever there aren't any rooms that have been generated yet but for right now we're just kind of naively doing an approach where we're going to look at all directions and randomly choose of the four or three for at the edge which one we should choose so if I press enter。

 notice that I'm able to step through this by the way in sequence。

 this operation was happening linearly as just one generation。

Previously right at the outset and we're going to take a look at sort of why that's interesting in a moment。

 but if I press enter。You'll see that we chose left and right， but we did not go up。

 so our dungeon generator has already chosen not to go up with its sort of prospective next rooms。

 these have gotten added to the queue， the queue is actually visible here at the bottom left you'll see we have 610 is where our head's at head's always going to be at the bottom and then 410 is the node that's right above that in the queue so what our code is now going to do is it's going to go to each of those in turn and it's going to create a room there and then it's going to do the same exact operation we're going to say okay up down left right unless there's a room already there and then 40% chance to skip that direction so we're going to go to 610 first that's at the head so that's on the right。

Notice that they're also being numbered based on their order generation just for our ease of being able to see the process。

 so then what we can do is press enter again。Notice that we had two options we could have gone to up and to the right。

 we only chose the right， so okay now we're going to press enter。We went here， okay。

 we got two directions。Okay， left， okay， we're going to do the same thing and we're going to go to the right。

 okay。No directions there， and we're going to go this one。K1。K1。K1。K2。K1。And then so now。

 interestingly， we have sort of this very left word bias dungeon that kind of goes up a little bit and you know if you were looking at this and implementing things a little bit more。

I guess with an eye towards the design of the dungeon itself。

 you could envision a way to sort of gauge distance between the starting node and some of the further nodes and then sort of hourlistically assume that further in points of the dungeon or where you would put treasure or you would put the boss and then you would also lay keys and determine through some sort of like algorithm that can determine that you can get to any particular door assuming that you get the keys in the order that they're generated that the dungeon is traversible。

 you could certainly do that after this point， we're just sort of naively creating all the rooms。

 and then we're going to do a final phase which is called the doorways phase which is going to be right here so you can see the phase got denoted as doorways。

 it's going to do a left to right top to bottom crawl of every door every room and it's going to place doorways for us across all the rooms in the dungeon。

And then once we're in the du phase and we press enter。

 we're going to go into the dungeon that we just generated。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_86.png)

And then I can press M and see that we do indeed have this exact dungeon that we created。

 I can go on the。The switch there and I can move to the right。And if I move to the right。

 you'll see the red cursor move to the right， I'm going to move one more to the right and we'll see we'll get to a dead end。

Because there were no。There's no rooms to the right or to the up top of that so we do indeed have a dead end here and the only way we can now go is backwards to the dungeon that we generated so pretty ultimately straightforward right just a queue we're kind of crawling through it。

 we're saying okay there's random chance， 40% that we won't do a direction but 60% that we will and it largely works。

 it does have bugs if you were to not ensure that a certain number of rooms get created which we've already seen a couple of times and then the fix for that is just ensure that no matter what you do have rooms that get generated。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_88.png)

So we're just going to quickly look through what that looks like and show a couple of cool things about it。

 so the actual dungeon maker， which we haven't looked at too much。Is。

Here we have a couple of different versions of it。 so there's a generate version that is wrapped in what are called corouts。

 and then we have a version that is being run in the actual regular code。

 So in this particular example， this is just one function in the dungeon repo。

 which is just the cor version。 If we were to go back to， for example， the。Let's say Zelda 7。

 and we were to look at the dungeon maker。You'll see。

That we have a couple of versions of that function， we have a generate Gen function。

 which is a generator function， which is another sort of way of thinking of classifying coroutines。

 which we haven't talked about yet， we'll briefly just talk about that。

 but there's a version down here that we've been using throughout all of the implementation otherwise。

 which is the same code， but this version does not have any of the co-routine associations with it。

 and this is just the generate function， but it's essentially just a queue。

 it gets an Xy set of XY pairs that get looked at a room gets instantiated there。

 added to our to our overall rooms， 2D array here， 2D table。

Then we just essentially do some assertions that were less than or equal to the length of the queue and that we haven't gone over or that we are still within the range of the number of max roomss you want to generate。

 you could tweak this number as much as you want to， it's a parameter to the generate function。

We will then essentially just do that verified check， havet visited the room yet。

 generated something there， if not， create a new room right here， player being passed in。

 which is an argument to the generate function， so the room has a reference to the player。

Also order for our generator visited at a string key that maps up to the CX and CY for current X current Y。

 setting that to true so that we can reference that later when we want to see if we've already generated something there。

 and then this is where we essentially do like a little shuffle algorithm that's going to shuffle up down left or right can be one of the four。

We're going to then essentially here's where we are skipping generation for that direction with the 40% thing that go to continue thing。

 we saw that in the Mario example of the distro when generating levels to skip sort of generating tiles in a particular X slice of the world。

IO y slice， but a particular x index y slice in the world。

 and then what we're going to do is essentially just do the same thing here， check if it's not。

Check if it not check if it's within bounds， not visited yet。

 add it to the queue and that Q is just going to keep。

 you know it's going to have all of the floors that we have a 60% chance to add it in this example that our queue is going to then just iterate through in this sort of like bread first manner if you were to use a stack or something similar where you're just adding。

To some sort of stack structure and taking off from the top。

 you'll end up with a very snay generator， for example， a very linear generator。

 there's many different ways that you can use different data structures to accomplish this。

 we're going with a stack with a queue because it accomplishes this sort of like more organic。

 wider sort of building of dungeons versus the snay sort of linear approach that a stack would give us。

And then lastly， we have a generate doorway phase and then the last important thing we'll look at here and something thats really important when I was building the out especially is you know something like a dungeon generator。

 it can be hard to debug especially if it's a very recursive sort of algorithm or uses complicated data structures and to be able to visualize it well is why we've included this tool that allows you to do it in the dungeon example but to do that you're thinking about okay I have this one function that does all these things and how do I split it up so that I can take a snapshot and pause and look at every individual part of it and the way that you can accomplish that is with this thing called a co-routine and so a co-routine is just built into a lot of languages。

 a lot of environments， LuA has its own sort of co-routine。Function， implementation。

With this coroutine namespace， which has a few functions。

 RA being a function that returns a corout that you can then call over and over again in whatever calling context you want to use it in in the case of our particular example。

 folks can look at in the dungeon code， we won't look at it too much here。

 but if you look at the actual Dunngeon test state。

You'll be able to see all of the code that we used to draw， the grid， all the colors。

 and you'll see that if we go to。Any instance of self。t Gen。There anytime you press enter。

You'll be able to。See the next instance of the Q。😡，Such that。Should be in here， used to having the。

Sorry， used to having this particular setup doesn't have easy highlights viewable here。

 but you can see that we have a sort of loop that over the course of time in our update phase once you press enter。

 is going to just call self。gen， which is getting a reference back to the return value of that generate function。

 which is returning a wrapped corout。And so what that means is that so a coroutine is essentially just this function that you can essentially think of as being plausible within a sort of context。

 it exists in the same process as Lua itself， and it's similar to a thread but it operates within Lua's own stack where you can essentially just call this function and then it's going to have a set of pause points or yields within it。

 where it will then return back to you a set of values at whatever point you want while preserving its current sort of state。

 its current call stack， its current existence at that state and time， to allow you to。

 if you were to call it again， it's just going to resume operation wherever it left off on until it's exhausted all of its potentially yields。

 you can run into an infinite scenario where this never happens， so it's something to watch out for。

 but assuming that your co-routine does end eventually you give yourself the ability to sort of manually trigger。

However， much of your function you want to run at once， assuming that you' spaced out these yields。

 so if we were to go back again to the dungeon maker here to the one that is in dungeon。

You'll see that sprinkle throughout all of the implementation of this function are these co-routine yields that return a table of just all the information that we care about and this is at the very end so it's going to return the dungeon itself we can instantiate the dungeon return that as part of the final done phase but throughout in other places you can see for example here this is the doorways phase that's where we can sort of signal to the calling context okay we're yielding。

 this is that doorways at these sort of states in time this is where current is。

 this is the state of the rooms state of visited all the variables that are essentially these complicated things to pay attention to during the generation of your dungeon you can pass them back to a calling context as a co-routine and then step through it piece bypiece such that you could use by keyboard input in the case of love2D to see step by step something that otherwise would be synchronous and really hard to visualize bugs and weird behavior and so this is a practice that I highly recommend people。

ide by or use when they're debugging complicated algorithms or generations of things like dungeons or levels or whatnot。

 co-routines can be your friend and Lua makes it super super easy to use them very handy and folks can explore the dungeon example to see that in practice。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_90.png)

So that brings us to just a few last topics to talk about that are kind of just fun asides more than anything。

 sort of lighter things to look at on the heels of quite a lot of complicated code。

 but we've talked periodically today about game design via data I think this is an important idea that particularly applies very well to large。

 complicated and dynamic games where you have lots of entities that might interact in weird ways an entity component system architectures are also very good for this too。

 and these going to kind of go hand in hand for that which you've alluded to previously。

 but here's an example of what a more fleshed out version of goblin or something and a creature in your game might look like besides just the animation frames。

 the texture， simple things like that， you can imagine being able to specify that they should have certain types of weapons。

 whether they're aggressive， which affects their AI， whether they sleep at night。

 whether they're flammable， you have all these different things that can affect very dynamic game spaces and I think it's very important to try to think in terms of this when your model。

In games like that， at least that's in particular a lot of the games that I'm interested in have this sort of philosophy and this sort of requisite。

 I think， games that have a lot of items and enemies and things like that。

 they get complicated and so doing it in data and having sort of emergent behavior。

 emergent gameplay and quickly iterable design or gameplay is a blessing， I think。

We've talked about the last couple of weeks， I think on the heels of that this is kind of a fun thing。

 I've dabbled and a little bit occasionally， I'm not an expert by any stretch。

 but we've looked at love2D throughout the course of this term and it's very high uses Lua。

 it's it's modern， it's not something that takes a tremendous amount to get started with。

 it certainly is very vast and deep set of things to do but it's ultimately relatively high level which is why I like it for teaching an introductory game development class but NeES game development and superintendo and many generations even thereafter where a lot more lowle and difficult and very different and here's a few links that you could go and explore for example with NeES homebrew to see some of that here's an excerpt of what like Super Mario Brothers looks like for the NeES from a disassembly and it's written in assembly code 6502 for the NeES and it's not nearly as readable or easy to understand or Goc because assembly is just a very different world but it is very close to the CPU。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_92.png)

is literally literally using op codes on the CPU which are affecting the hardware on the CPU at that level to affect the behavior that you want in your game and so you have to write a lot more code。

 do a lot less， unfortunately， but this is how it all got done back in the day and the paradigms and ways of looking at those problems we very different and I think it's worth exploring that sometimes and just sort of seeing and respecting how far we've come in this space。

 across all spaces and programming， but in games is the space that I'm the most familiar with。

And that brings us sort to the close of this lecture and then to what we will be looking at for assignment5。

 which is namely extending what the player is capable of doing。

 such that right now the player can move around， swing a sword which we illustrate sort of how to add a state and to be able to affect behavior and do things in the game besides just moving around and even adding new hit boxes。

 so let's extend that idea a little bit and now actually add pots， which is this big part。

 so be able to grab a pot， throw it， have that be a projectile， affect enemies hit the wall。

 so on and so forth we saw pots in the sprite sheet。

 but also right now if folks might have noticed all too well that the game's pretty hard and that when you get hit a certain number of times。

 you're kind of out of luck， because there are no ways to recover HP， but in Zda the game。

 it is very much an expected thing that you have hearts that drop from enemies or from pots or from anything。

 that replenish a full heart which is equivalent to two damage in this game。

That's another big part of the game as well， so hearts， lift pots， pots can be throwable。

 and then damage enemies， and then lastly， sort of another big thing and very important and iconic and we alluded to it previously is in Zelda there are treasure chests and within those treasure chests are any number of things in this problem set。

 the expectation is that the player will find a boomerang。There should only be one per dungeon。

 when the player finds the bummerang they should have an icon to show that they do have it。

 some inventory icon similar to what we saw even in the original Zelda image。

The player should be able to throw that boomerang， the boomer rings behavior should be such that it goes at a certain distance and then will come back and track the player no matter where they are and then they'll be able to throw it again while it's out。

 they should not be able to throw it and then while they throw it it should do damage to enemies or bounce off of walls so a few different things related primarily to projectiles but also just to other big pieces of the Zelda formula at which point really you'd only have maybe a boss and then keys and then you'd kind of almost have the full base game there。

 but that's essentially just behind assignment5。And so next week we're going to look at box 2D and kind of take ourselves out of the NES era and back to the modern era which has been kind of a theme back and forth next we'll be looking at an angry bird's implementation using this sort of sort of public domain tile set and looking at a very different way to do 2D game development with physics compared to anything we've done so far B 2D ships with love。

 it ships with many different environments is' very easily embeddable into almost any engine and as a 2D way to sort of do a lot more interesting types of collision and mechanics and dynamics than what we've seen thus far so that was Zelda that was week five we did a lot in terms of looking at a bunch of code we looked at even some relatively sophisticated dungeon generation and co-routines there at the very end。

 but we've run the gamut largely of what's possible with 2D in terms of side scrolling top down not a whole lot of I guess visual or aesthetic domains left per se。

 even next week we'll be looking at side scrolling。Graphics。

 we could look at isometric at some point perhaps， but that would be one of the few left to really explore otherwise most of the fundamentals I think now have been communicated and so now it's time to explore things like。

Physics and Box 2D， and then eventually with Pokemon we'll be looking at things like turnb systems and GuUI elements。

 graphical user interface elements， but until then this was Le of Zelda and they closed sort of of the NeES era and we'll see you next time。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_94.png)

![](img/8fc31d00de36a5a615a661d1a3cd4b84_95.png)

So for us to be able to accomplish this on our own sort of use the stencil buffer for our own effects。

 we're going to have a couple of functions to look at in particular。

 one doing most of the work for us， which is going to be love。 graphics。s stencilstate。

 which is going to have an action and a mode and then a value that can interact with that both of those prior things。

 the action and the mode。Typically we'll work with one a lot of the time or zero one or the other for simple comparisons。

 but there are you can go all the way up to 255。 there's 8 bits allocated per index in the stencil buffer and then therefore you can do all kinds of things we do additive comparisons and whatnot but for today's example we're going to be using one and we're just going to be doing some pretty simple comparisons but the other thing we're going to need to take a look at is because these draw operations that occur once the stencil state is set have to sort of also draw to the screen by default we want to be able to mask these colors out at the time that we draw and just affect the stencil buffer so when we do anything that is affecting the stencil buffer and we draw it will affect the stencil buffer and also the screen so it's going to turn the screen off using a color mask just setting RGBA to false effectively with set color mask which we will take a look at。

 So it's transition over to some code real quick and see what this looks like to start with I'm going to go ahead and open up。

Sort of main dotlua here。And we'll just run this。And we'll see everything works just as before。

 but I'm going to go ahead and now I've got one doorway， I'm going to go ahead。

Get hit by a spider and then hit that switch。Killll a skeleton and move。

 and you do indeed see that the character moves underneath that sort of archway。

 we have this sort of illusion using the stencil buffer。

That we are moving underneath some terrain that is at a depth closer to the camera than actually is。

 but all we're really doing is essentially just blocking pixels that are being drawn with some comparison operations using the scil buffer and we can do that through any archway as we see there。

What's also kind of cool is we have a debug mode set up here， so if I heard we werere to hit S。

 we see that there are some rectangles that are actually showing on the screen and this is useful for debugging sometimes these sort of invisible as we saw before。

 even with you know the hit boxes on the character's sword and even the characters and enemy's hit boxes themselves or hurt boxes。

It's one thing to think about them and kind of put them in a rough area where you think makes sense and where they belong。

 but it's a bit better I think and more methodical and more precise to have an actual debugging way to do so and so it's not uncommon to have things like rectangles or other shapes or polygons or whatnot rendered in some sort of color that's clearly for debugging purposes because use the transparent shade of red that accomplishes this and this allows us to you know if we are going to draw rectangles during our stencil state operations I want to make sure that they're properly set and so that's what that does right there using a global flag with S so I'm going to go ahead and move back over to here。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_97.png)

And then。Actually， Ryan did I。We was part of that going to be including the talk about we'll use that we can use that as a maybe a transition point I where I just ended on if that's okay。

 but the。When we were coming in we ended up talking about the debug flag and then I actually reran the code。

 do we want to just lump， maybe we keep all that lumped into one thing and we can just end this whole section before the transition to the next slide about the data drivenriven design。

 does that work？I think so are。We just were talking about a peer。Maybe different。Yeah， yeah。

We're missing at them。Yeah， yeah， that is the plan。

 but I'm just wondering now like that I just did that kind of on the fly。

 it kind of felt kind of like a natural point to talk about it there。

 I'm wondering if we can just go through now the rest of the code explanation and then cut at the end of that as we're about to transition to the end of the next essentially the next slide after we。

Or I guess what would be the dungeon generator， which was the last thing we talked about。Okay， cool。

 thanks。Oh， thanks， Appreciate it。No worries。I think for the sake。YouShould try。You said。

Basically if you。Yeah， sure。Basically， right。嗯。In terms of the actual code part， so right now。

Are you saying after we look at the code right now？Yeah。Like so after we look at the code right now。

Okay， so I can do that I can at the end of because we're going to be in Room。lua。

 I can just click to main dot Lua， which will put us here if this is okay enough。I think that's fine。

Rememberm that。Okay， and I can do that。And just closing。All right now。Okay。

I think we ended here on my last thought， are we resuming based off of a cut that was from the old cutter from what we just did？

What you did？Right。W down。Okay， so do all that we just did。

 include the debugging part here in the example， then go to the code explanation of what's happening。

 and then end on main dot Lua and talk about how we're going to the dungeon generator。Okay， yeah。

 I think that makes sense。Can I have Mainet Lua open in advance， do you think is that okay？啊s my。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_99.png)

Okay， yeah， if we can just have it here， I might say， okay。

 now let's open up maindotlu and do a thing maybe to help for a cut or something but。

Is that what you'll be？Yeah， when I come over to do the demo， that's what we'll all be running。

 and then we'll go to Room。lois where the actual stenclink code occurs。

And then I just have to remember once we're done talking about that to go to Maine。

 Lua at the end of that again at line8， and if I just keep it here and I don't scroll。

 this should be perfect because we're at the top of line eight。Okay。

I mentioned explicitly Ze to eight at one point。In the dungeon generator portion。Yeah。

The only other note I have。Okay， okay。I think so， fingers crossed。Yeah。😊。

So that takes us then to how do we actually use stencling in our own game and thankfully love2D abstracts over this really nicely。

 it has a function called love。 graphics。s stencilstate which overall sets the global sort of state where we're editing and testing the stencil buffer in addition to a function called love。

 graphics set color mask which prevents us from also drawing to the screen but say we want to specifically just draw to the stencil buffer and for example write some ones where we want the character to be hidden behind if you were to walk over it and so on and so forth。

 the things that you would write stencil sort of functions for and being able to test for it。

 and so that's what we're able to do here， set stencilstate gives us an action a mode and a value those work together depending essentially set how the stencil buffer is going be compared against certain values at the draw phase to enable or disable certain drawing operations and so we'll go ahead and take a look at how this works in practice with demoing。

I'm going to go ahead and open up main dot Lua here in Zelda 7。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_101.png)

And then if I just run this。We'll see that we indeed have a dungeon as before。

 I'm going to go ahead and just walk around， go to whatever the nearest door is。

 I guess this wasn't the nearest door but it was one of the two。

And then walk through and you can indeed see the character does move as if you were walking underneath the archway there。

 which is pretty cool， I'm going to go ahead and open that and then we'll go upwards as well。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_103.png)

You can sort of see our character getting shifted into position and then sort of。

🎼Walking below the archway even though you know it's literally just tiles that are drawn onto the screen。

 we get this illusion that we're moving through a corridor by the fact that we are essentially rendering some rectangles and if I press S will' even see what those rectangles look like with some debug code I have set up We're actually drawing rectangles during that set stencil state function which we're now added we've added this to room。

lua as we'll see shortly but this essentially sets the stencil buffer to ones here and if we just say only anything less than one can actually be brought through you know at this time that we're testing the stencil buffer only stencil buffer indices that have a value less than one will pass that means that any time we're trying to draw something and the stencil buffer reads a1 well we're no longer passing that condition therefore the character should we try to draw the character won't actually draw its pixels to the screen they will essentially be bypass。

 they will no longer be allowed through because of the stencil buffer and this debugging practice is useful。

🎼this is something again， it can be kind of hard to envision do I have my stencilling exactly setup correctly do I have my hit boxes and hurt boxes exactly balanced in a line correctly sometimes it's best to just set up some debugging code so I just hit S for stencil to sort of debug and display these semi-transent red very clearly debug colored rectangles that now I can verify with my eyes oh yeah everything is set up perfectly and then I can test it in practice that it works properly and so on and so forth and so that's the demo and essentially the final version of Zelda 7 so if you come back here and we go over to room Lua we'll notice that we have some code here in our render function and particularly we start off with this love graphics set color mask which is a false false false false meaning that red green blue and alpha should not be allowed through at the pixel anytime when we draw anything there's gonna to be this mask operation to whatever gets drawn onto the screen just don't let。

Of those components through and if nothing can go through that means nothing gets drawn therefore we can set the stencil state to always essentially replace the stencil buffer's indices with this value one whenever we draw anything here on after so what we'll do is we'll go ahead and we'll say okay I'm going draw four rectangles they're all the same rectangles that we just debug view looked at but in this case these are not going to be drawn because the color mask is set to all false right now we're going set it back to true and then we're going to run another stencil state which is that we're going to keep any pixels that the stencil buffer has less than one of their value there at the time that we draw the character and there's many different compare modes and actions and things。

 the stencil buffer has quite a lot of things you can do with it we're only using just a couple of very basic versions of those functions but this is essentially what allows us to do all of these masking operations we just say okay write some。

Pixels to the stencil buffer and then compare against those pixels at certain draw phases。

 turning off our sort of global pens so to speak with the set color mask and this gives us the ability to draw things the way that we want to Additionally here's where we have the debugging code setup there's just an if statement and a global flag that's mapped to S which then will draw actual rectangles at a particular semitransparent red color which allows us to draw for debugging purposes。

Well， and that's essentially the gist of stencling and that brings us to sort of the last thing we haven't really talked about just yet。

 but we now will at the very close of the program or the game。

 which is how does the dungeon generator actually work？All right。Cool。Thanks。



![](img/8fc31d00de36a5a615a661d1a3cd4b84_105.png)

![](img/8fc31d00de36a5a615a661d1a3cd4b84_106.png)