# 哈佛大学《2D游戏开发｜CS50 Introduction to 2D Game Development 2025 Fall》中英字幕 p03 CS50 2D - Lecture 2 - Breakout .cut.zh_en -BV15xsPzEETf_p3-

Hello world。 My name is David Main， I'm Colton Agga。

 and we're here for the third live stream of CS52D。

 which is CS50's new and improved introduction to 2D game development。

 a successor to CS50G which covered both 2D and 3D more on the 3D part before long Today will be a live lecture in the sense that we might start and stop and fix things so please forgive if we make any mistakes I'll be keeping an eye on the chat if you have any questions and I'll raise my hand as needed to verbalize any to Colton this course won't be available until later this year onedx along with the assignments。

 but well follow up in the months to come when we are up and ready Colton curious to ask we're in a2 day game class here。

 but what was your favorite game growing up would you say I really like legend of Zelda link to the past for Super Nintendo that was a big one you've played Zelda for old enough to have played the original Zelda That's a good one too That's a good one too I can still remember the sounds like when you use your sword to breakthrough things yeah when you have full H。

Exactly and in fact it's the HP from Zelda that influenced the CS50 ducks use of HP or heart to raw throttle how many questions you can ask per unit of time I forgot about that yeah that's clever it's cute all right well give us just a moment to reset and this will be CS50。

3。2。Hello world， this is CS52D and this is lecture 2 breakakout。

 so breakakout is a fun I just realized I wasn't going to have the clicker in my hand， sorry okay。

 try out more time。Apologize。Off to a not fantastic search。Breakout star。Already， and five。3。2。

Hello world， this is CS502D and this is lecture 2 breakakout and breakout is kind of cool so in lecture0 we did pong and interestingly breakout is kind of an extension of pong in fact it was created by the same company Atari in the 70s and there's a fun story also with breakakout CS50 back in the day did a version of breakout that was also a game and graphical and I remember being involved in that project too this is many years ago but it's super fun。

 the cool thing about breakout is that it allows us to take some of the things that we've learned in pong but also really get fancy with more complicated game mechanics and sort of levels and scoring and is also much more visually interesting which I look forward to showcasing here in this lecture。



![](img/ad5e3f6b767cac035f8979626c48f9fe_1.png)

But this is indeed CS50 actually set the stage for this lecture many years ago。

Our goal is going to be to produce something that looks like this and there's a lot of pieces as you might be able to infer and so I think it might be best to demo the game itself。

 I'm going to go ahead and step over to the computer and let's just do a little demo here of the final example of our code。

 so I'm here in sort of the distro here but if I go to breakout 13。



![](img/ad5e3f6b767cac035f8979626c48f9fe_3.png)

Go down to Ma Da Lua。And then give it a start here。We'll see。

That we start off with some music to begin with， but also we have at the very beginning high scores。

 something to look forward to if I click on that we'll see we got CTO。

 CTO this just happened to be my initials AAA as well。If I go to start the game。

 we have a paddle select so people might be seeing a lot of things in here that look quite new as opposed to the last few lectures。

 but I like the color reds so we'll go with red， I have this set to start at level 32 just to sort of visually typically showcase more interesting bricks and unfortunately it doesn't look like we got some of the higher tiered variants in this instance but I'm going to enter it's going to move the balls moving so it's going to bounce because sound effects we have particle systems some folks might have noticed when the bricks actually hit。

So if I let myself take some damage at the very top right of the screen， you'll see that we have a。

Heart actually， I probably should have had you come up in demo， shouldn't I Oh， it's okay。

 do you want to do that， Yes sure， Yeah okay。

![](img/ad5e3f6b767cac035f8979626c48f9fe_5.png)

That was， I totally just went into my own into the zone I'm I couldn't go back to there and say we should start a demo then or does it make sense to ask for volunteer here you think？

I would just start over at this point， it's faster。



![](img/ad5e3f6b767cac035f8979626c48f9fe_7.png)

Com。We say。Sorry， I got it was used to Pong zero and then we did the you did it yesterday and I was thinking of Pong。

 okay。So I'll start with something like and then。So we've got a lot of things here。

 but rather than talk about that， let's actually do we remember the last thing that I said at the TV？

I would just start from the top honestly， the very top Yeah。

 and how Colton was able to adjust his volume。Hello world。

 this is CS52D and week this lecture we'll be doing breakreakout which is lecture2 and breakakout has an interesting sort of history Well first off it ties into pong very nicely because it was created by Atari back in the 70s and so allow us to extend a couple of the ideas that we saw in pong but also CS50 proper did a version of breakout back in the day many years ago and in fact this was one of the first things that I worked with with CS50 was adding sort of fun lasers that we shot from the paddle back in the day but pong and breakout our very similar in a lot of ways but breakout as you can see even just looking at this example we have a whole lot of bricks instead of just one other paddle at the very top and it is also a single player game which is kind of neat and it allows us to look at a whole bunch of different things like scoring and levels and some nice visuals which will take a look at today so we can get a kind of overall sense just looking at these screenshots of what the example is going to look like but I think it would be better to actually demo it and if I could。

Is anybody up to volunteer to give breakout a proper try？D Cha Mayor， Colton， nice to meet you。

 David， nice to see you again I'm going to go ahead and。Press this here。

🎼The aeros will way to move throughout the menu here。

We a couple of options for free just enter on either one if you would like to。



![](img/ad5e3f6b767cac035f8979626c48f9fe_9.png)

High scores and star both are different states now。So here this is a paddle select。

The color you like。We started level 32。Its eventually gives people some more videos well。

It that's very similar to Pong in a lot of ways。But as we can see when the ball， for example。

 collides with bricks， we get these particle systems， these visual effects。Does any update？

Clearly better at this than fluffy burst。We've got scoring at the top now we didn't have scoring previously。

 oh I do， I guess we did， but now we have much higher numbers in our scores。We have health。

 which we even mentioned briefly， heart heart，topia。And so if you were to in theory。

 not be able to hit this ball， okay？Make it dramatic Oh no barely I just barely got there but you' know it's one of the hearts one of the hearts got detracted so that's another piece of game state so to speak and if we were to restart this sort of and instead of choosing start maybe instead if we were to look at high scores we now the ability to preserve scores which one am I fortunate overall my initials in there I sure to let you finish you would have beaten one of my scores there but know we have preserving of high scores to data actually persistent data on disk so a lot of new features this time around I'll try again thanks thanks thanks for giving a shot。



![](img/ad5e3f6b767cac035f8979626c48f9fe_11.png)

![](img/ad5e3f6b767cac035f8979626c48f9fe_12.png)

![](img/ad5e3f6b767cac035f8979626c48f9fe_13.png)

All right， as you can see there's kind of a lot going on just in this example。

 this initial demo here， but we're going to take a more thorough look at all of these， of course。

 and some of the topics that we're going to see today。



![](img/ad5e3f6b767cac035f8979626c48f9fe_15.png)

And we alluded to some of these at the end of the previous lecture are as some folks might have observed。

 there are a lot of graphics in today's example， a lot of in particular the paddles and the bricks and the background。

 all these different things， a lot of smaller graphics。

 and if we imagine just including all of those as individual images， it would be quite a lot。

 it would be very unwieldy so we' be looking at sprites sheets as a way to solve this problem。

We had and some folks might have noticed through rerunning the game a couple of times。

 but we have actually procedural layouts， meaning that all of our bricks as they're laid out are procedurally done。

 so that allows us to have very dynamic sort of game layouts and every time we play the game it's going to be a little bit different。

 which is kind of fun。State of course is important， the heartsworth state score was state。

 but also we had all these different states that our game could be in the served state play state and we want to be able to carry that data across multiple states as we alluded to at the end of last lecture so we'll be looking at how ways to do that levels of course we start on level 32 but typically start level1 and then you would work your way up and as the level gets higher typically it gets more difficult。

We have health which is another piece of state， particle systems are a very nice way to add just a little bit of visual spice and polish to the game。

 so we'll look at a way to do that， love makes that very easy to do。

A couple of different forms of collision detection which are different than the forms that we looked at previously。

 we'll look at that， both the ball and the paddle， but also now the ball has to collide with all these bricks at the very top of the screen and that's going to require its own type of collision detection and then lastly persistent save data those high scores we want to be able to not just have a high score that shows right now but if somebody else were to load the game up。

 we might want them to see our high scores in the future and also we might want to shoot for our own previous high scores and persist that data so that'll have to live on disk。

Now， breakakout as a game as we saw has a lot of states， a lot of game states。

 This is a topic that we explored at the end of the last lecture and this is a state diagram that maps the entirety of breakout。

 So if we recall pong and also flapybird are quite simple。

 flapybird only had four states in total and this has it looks like eight in total and all of again the relationships between them all the transitional relationships between them are modeled here So we'll just go through it really quickly but we start in the start state。

 this is of like the all roads will lead back to the the start state but we can imagine that from the start state we might want to go to the high score state as we just did because recall at the beginning of the game we go to high score from high score we can really really go back to the start state it said press escape escape to go back to the start state so that's essentially what we can do and then there's another arrow notice that also these are unidirectional arrow so at these flows are all unidirectional So if you go from the start state down to the paddle select state if you recall David selected the pa that he wanted had different colors available to choose once we're in the paddle select state we can then start。

The ball， which means we can move the paddle around sort of like how we did in flappybid we had a countdown state in pong。

 we had a serve state just to allow us to get a little bit of a buffer before we begin the core game loop when we're in the serve state we'll transition over to the play state by pressing enter or the like and the ball will begin to move around we'll be in the play state at which point if we were to let's say take some damage which we illustrate it well we want to give the player an opportunity to pause for a moment and then maybe regain their composure and then go back into the do that back into serve state by going back into the play state after pressing enter。

Once they're also in the play state and let's say they were to clear out all the bricks in the level。

 which we didn't have time to demo， but if we were to actually clear out all the bricks well we need a way to up the difficulty and go to the next level so we'll make a victory state from which we can then go back to the serve state to begin playing again Now if we're in the play state and we actually lose all of our health we're probably going to want to go to a game over state which is going be a different path and from the game over state there are a couple of different ways we can go let's say we did not get unfortunately a high score we'll just go back to the start state so back at the very beginning of our state machine this is essentially the flow that will sort of represent the overall infinite looping nature of our game and then if we're in the game over state and conversely we actually did get a high score we want to go into this new state where maybe we can enter in our initials and actually enter the high score or whatever name we want to place there for posterity and then when we're in enter high score state maybe we want to see where we were in relation to。

All the other scores， so we'll just go right back to the state we already looked at。

 the highest score state， and then as we saw previously that has a one unidirectional relationship transitioned back to the start state。

So a little bit more complicated than prior lectures。

 thankfully most of those states are relatively simple。

 but I think it's important to have an overall bigger picture understanding of where we're going before we look at the minutia。

So let's begin with breakout zero， which is the day zero update。Okay。

 I'm going to get just a drink of water really quick really before I start。

 my mouth already starting to get dry。有机费。Okay， today， were you planning？Al right。

 so if we go into my source code distribution here， which we were just looking at。

 transition over here， so there are all of the same updates are broken out into files just like folders just like we did last time。

 so one thing that we'll notice right out the gate。



![](img/ad5e3f6b767cac035f8979626c48f9fe_17.png)

![](img/ad5e3f6b767cac035f8979626c48f9fe_18.png)

And I might have made a slide about this actually in fact。

 is that previously we've sort of had all of our files in a hodgepodge just kind of all at the surface。

 all in this one layer in our folder and really it's okay if we're doing something like pong or even flappybid where things are a little bit on the simple side but as you can see shown on the slide here there's kind of a difference between there's an illustration between what this would look like if we were to sort of do it the way we've been doing it versus what I think is a more ideal way to do it and this is kind of representative of what you might see typically in a game project for starters we have a source folder now we're not just putting all of our Lua files at the parent level of our folder we have a sounds folder。

 which I believe we did have in the prior lectures at the very least but also a lib folder is interesting Some folks might have seen that in other programming context for our libraries this is a conventional thing and up to taste but ultimately I think some folks prefer to differentiate their own projects code from other projects code like push for example in class those are libraries that we're using So we'll just talk。

to live and then graphics probably should go in its own graphics folder or the like or images can call it whichever you prefer。

 and then fonts as well going into its own folder and especially as projects scale and you have larger and more complicated projects with many different types of graphics and fonts and sounds and things it's just very unwieldy so it's better to try to consolidate things into sort of semantically meaningful folders as we're doing here and as you can already sort of see we have a bunch of graphics and fonts and whatnot that I've already preloaded。

 actually just one font but a lot of graphics， a lot of sounds to if we open up the sounds and these were all sort of precreated ultimately with BFxer and folks can also use chiptone all of these sounds are just freely generated sounds。

 very eight bit inspired ideally。

![](img/ad5e3f6b767cac035f8979626c48f9fe_20.png)

And same thing if folks might have also noticed a music track， same same deal。

 except that was acquired from a public domain source quoted in the source code。

 So if we open up main dot Lua and break out zero here， we're just going to condense that down。

We'll see a lot of the things that we have been seeing previously except now。

 one thing that folks might have noticed previously was that we had sort of all of our requires in one place in our main dot Lua at the very top of the program and that can be okay again for smaller examples almost anything goes people will be able to find their way through your project but it's better often to try to consolidate individual blocks of meaningful code in this case rather than just require everything all of our dependencies meaning classes and the like that we want to use throughout our code it's better to put those all sort of in one central required place in this case we've created a file called source dependencies which we can now see here we have a new file a constantss file because recall we did have a bunch of constants like our window with and whatnot。

 and we have source state machine which in this case is source slash state machine really this is the way that LuA does paths with periods with dots and then we also have a couple of states to start with and this is essentially more or less what we。

off at the end of last week when we were talking about states。

 but you can see that rather than just requiring these in Ma D Lua。

 we can now put these in their own file。

![](img/ad5e3f6b767cac035f8979626c48f9fe_22.png)

I going go back to main。lua so we have all the same things we saw before love。 load。

 we've got a random number generator， we've got a title。

 I'm putting all of our fonts again in those global tables that we can reference anywhere throughout our code and they're given this prefix of G we're setting a font to a small font remember we have 8 a 16 and 32 we've got all the textures that we'll need we've got a window mode being set here setting up push all the things that we needed before a lot of sounds in this example。

And then remember we ended with the state machine。 So what I just talked about in the slides was all of the states that we were going to deal with today。

 and that was sort of where we left off in Flapppybird was the talk of states and state machines and so the main place we're going to begin now just to start off on the title screen and I'm going to run this example so we can see what that looks like is the start state and the start state is just a simple graphic with some text we have our FPS indicator at the very top left showing 24 because I'm running at 24 frames for production purposes。

 but we have a couple of options here just to start and a high scores and notice that I can hit the arrow keys and I can move between them we have essentially white for an unselected thing and I'm choosing this sort of blue teal color to choose which ones highlighted which is just a state variable but all of this is just now encapsulated as we looked at last time in one central state object so let's go ahead and take a look at what that looks like I'm going to open up now this is sort of a convention thing as well and this is ultimately subjective but I've decided because states sort of feel like they could be。



![](img/ad5e3f6b767cac035f8979626c48f9fe_24.png)

Their own category of source code， I put them in their own folder called states within source。

 so in source dot states or source slash states thinking about it more traditionally。

 we can open up start state。And see， we're going to want to highlight start or high scores in this case。

 when we press up， we're going to change highlighted to be either one or two。

 we're using that ternary syntax we looked at last week。

 so we're already highlighted or if one is highlighted。

 then we'll set it to two else we'll go back to one so we'll just essentially toggle almost like toggling a bit on and off going between one and two。

We'll also you know set up our loveevenqui handler and so here is where we're sort of saying。

 okay we're gonna to set the font to medium we have a large font to say breakout for the title and then for medium we're going to highlight if one is highlighted we're going to set our color this is how we draw things in different colors and then we're going to print we're going to draw out with print up on the screen。

 the start text and that's because one is currently highlighted same thing down here except we're going to set color to 1111 to refresh in case two isn't highlighted。

 so we'll go to white and then if highlighted it is two we'll set it to teal or it will just be the one that we just set in which case it will be rendered as the off option here So high scores will take whatever the color option is remember anything that you printing anything that you're drawing that's a shape or even a texture is going to use this color this set color to sort of color it if you draw images it will tint them but we saw for example rectangles and fonts those will all be colored by whatever this love dot graphics set color is so all we're doing is。

We're losing a keyboard input and then we're highlighting which of the menu options to select。

 but that does sort of give us this beginning initial way to get into the source code into our project。



![](img/ad5e3f6b767cac035f8979626c48f9fe_26.png)

![](img/ad5e3f6b767cac035f8979626c48f9fe_27.png)

Now probably one of the biggest things that we're going to look at in this lecture besides the collision detection。

 which is a lot is this idea of quads Now we talked previously just about images。

 images are relatively easy to draw， we saw that last time you just do love graphics draw and then whatever texture you want but in this example in this distro we can see here there's just one paddle being rendered and folks might think okay well we'll just include a paddle image but we saw even just at the very beginning well we have a blue pa。

 we have a green pa， we have a purple paddle if we want a bunch of different pas。

 those will have to be their own image， but folks typically in industry find it a little bit easier to work with these things called sprite sheets or texture atlases which will allow you to actually condense all of your artwork into one file rather than have if we were to make individual textures for each and every one of these images this is maybe close to 100 or 5 between 50 and 100 images it would be very unwieldy it would be horrible in code to be okay what's the name of this one This is blue is。

Blue with green stripes， blue with yellow stripes， how do we even name these things so folks have typically found it easier to use quads or UV coordinates。

 texture coordinates to splice up individual images we can just load one texture atlas。

 one sprite sheet and then just think in terms of rectangles。

 think about how to splice that up into pieces that we can then reference we can say okay draw our main texture at this particular rectangles offset at this particular width and height and that will allow us to pretend as if we have maybe 100 images but in truth we're just drawing one image。

 the graphics card is then taking those UV coordinates that quad data and just drawing a tiny little piece of that for us。

To make it seem as if we're drawing just that individual image onto the screen and so the couple of the functions that we need to take a look at in particular are love graphics new quad and love graphics。

new quad is just essentially declaring a rectangle So it's not all that different from love graphics rectangle in terms of how we think about it except it's a piece of data that's going to apply to our texture when we want to draw it with love do graphics draw notice that we can pass in a texture a quad and in x and Y So if we pass in a texture。

 then we pass in the quad rectangle and then the x and the y at xy it will draw our texture but it will only draw the rectangle of that texture that we tell it to So if we just define a bunch of these rectangles for the paddles for the balls for anything any Ui elements that we want and then we just call it in this fashion we'll be able to draw just small pieces of our texture onto the screen anywhere that we want So why don't we take a look at how that actually works in code I'm going to fire up an example here。

I'm going to close out all of these existing files from last time， close this down。

 and then first off， let's just run this example so we see what it looks like。



![](img/ad5e3f6b767cac035f8979626c48f9fe_29.png)

We can see right at the gate it looks identical to last time except if we hit start now。

 we'll see that we do have a paddle and the paddle can move and a paddle in fact is even set already to clamp to the x axis of our screen which is what we had to do with pong but recall it was inverted with pong rather it was 90 degrees shifted in pong where you couldn't go up and below the top and bottom of the screen in this case it's just because we want the bricks to be at the top and this is the way that breakout was designed we're clamping it down to the left and right edges of the screen。

 but this paddle is just being drawn now not with the texture。it is being drawn with a texture。

 but we're not just drawing an image straight onto the screen in its entirety。

 we're using a quad to delimit with UV coordinates， essentially。

 which is just a way to represent fractional bits of an image on graphics cards。

 we're just drawing a piece of that texture and pretending as if we're drawing just the paddle as its own image as its own entity。



![](img/ad5e3f6b767cac035f8979626c48f9fe_31.png)

So if we look at right here in Maine。Much of this should ultimately be the same。

 but we've added a new state now， as we saw， we went from start to play by hitting enter on start at the title screen there。

 so the play state now， if you come into here，Is going to have it in it as usual。

 but notice that we've set self dot paddle equal to a new paddle， so if we open that up。

All of these things we're now thinking in objects which we started getting used to in the last lecture。

 but a paddle ultimately it has a lot of the same things that the pong paddles did。

 it's going to be very similar ultimately to the paddles from pong except now we're going to have for example this skin and size and things like that these will be variables that could influence our appearance and we'll look at how these work in just a moment we also have a Dx instead of a DY because in pong we have the DY we're moving on the Y axis now we're moving on the X axis so it just's a different axis of movement。

Removing all the same exact clamping logic that we saw previously using Matop Mac and MathT Min to make sure we don't go off the left and the right edge of the screen。

And then we are rendering our paddle here and some folks might notice and this is essentially what I just alluded to。

 that we have our G textures main， so in this case this is just our main texture if we look at what that actually looks like。

Here in our graphics folder。Actually， it's going to be called breakout。And we're just naming it main。

 but we can see this is the exact same texture that I just showed in the slides and we're rendering the paddle。

 but we're。We're not rendering this whole image when we draw and that's by virtue of the fact by the second argument we have this G frames paddles so notice that also we have a twodimensional array here。

 which some folks might have seen in other courses or a twodisal table so a table can store keys and values and those values can also be tables so if you index into a table and that also happens to be a table you can then index into that table and that's essentially what we're doing here we're deciding to break up our texture into various named subts into Gframe so we can say okay I want the paddle frame at index x index y that's essentially what we're doing here。

 we're shifting by doing a little bit of math to essentially find our based on our skin and our size if you look at the texture pull that right back up again。

Graphics breakout。We'll see in a second we'll see sort how we're splicing this up。

're we're going to have to do it a little bit manually because you know some folks might already be able to infer that the pa。

 the bricks， for example， at the very top are all a uniform size。

 and if we wanted to create all of the rectangles we could just go through them iteratively one by one and define and hardcoded constants。

 the x， the y， the width and the height and so forth there's a much easier way to sort of dynamically or rather procedurally iterate through a texture based on the size of the units therein but these paddles are different sizes so we're going actually have to do those manually。

 but what we essentially want to do is depending on our skin。

 we're going to shift down by four rectangles to get whatever size rectangle we also want we don't manipulate the size too much in this distrobe but that will be one of the assignments as we'll see towards the end of the course。

 we'll be choosing a paddle based on the size or rather it will be manulating the size maybe based on something like a power up making your paddle either bigger or smaller depending on。

You maybe have a penalty for touching some sort of poison mushroom from Mario analog in this game。

Now we could also sort of cruelly just elect to choose the first paddle here as the paddle we start with。

 but it's a bit harsh to do so and so we've elected to choose this second paddle here， size2。

 and so if we go back to paddle。lua。We'll see that at the very top， our self dot size is two。

 and ultimately what that's just doing is indexing into this。

Aray of quads that we're going to create all these rectangles。

 So the first so if we were just to choose the first rectangle in that array。

 it would be the small one。 the second one would be the larger one。

 the third one would be the even larger one and so forth。And so we're just doing some math here。

 basically multiplying by our skin， self dot skin minus1 so that we can start right off on just blue and1。

2，3，4 will equate to the very first four quads and then we'll just add four to that to offset depending on which skin we've elected to choose now in order to actually create the quads different that's a whole different question in main dot Lua。

 if we look over here。We'll see up at the top。We have。Inop sorry， G textures， G frames here。

I've called it Gframes because in a lot of circumstances in most circumstances when spritesheets are chopped up and iterated on it's for the sake of animation。

 we think of frames， but you call this Gquads， you could call this Grex you could call this Gframes whatever you feel like as we'll see especially in later lectures this idea is applicable to a great many different ideas but in this case we're just going to start with Gframes gets a table that is going to start with a paddles key that has a return or has a value of this function。

 generate quads paddles which takes in G textureexs main so if we go down to if we go over to our u file notice in our dependencies we do have now a require source u this is a common thing as well。

 you want utility functions that often do some work that might not be necessarily directly germane to the gameplay but in this case it is sort of data processing and so it makes sense to have a u function or u set of functions that we can rely on I'm going to go to u。

And we can see here we have a general generate quads function。

 which we'll take a look at in a second。But we also have this generate quads paddles。

 which takes in an Atlas， this atlas is just another term for a sprite sheet。

 some people refer to texture atlases as like the original idea of an atlas being this collection of maps。

 and so a texture or a sprite sheet， a texture atlas is sort of like a collection of other textures。

 a texture that is a collection of textures。And so that's why in industry。

 you might see the term Atlas used frequently。We're essentially going to， in this case。

 just iterate over from one starting at0 to3 and we're starting at zero because we want to take UV coordinates or essentially based off of positional coordinates very similar to how we move things around in the game world so as we're chopping up our image which is what this function is going to do。

 it's going to create those rectangles on top of our texture we want to think in terms of regular coordinates。

 There's a little bit of confusion， sometimes that can come about from Lua being one index with tables and certain types of loops that you'll see but in this case we're essentially going to from one equals zero to three。

 which is the four different paddle colors or skins that we had。

 we're going to create four different sized rectangles based on all of the if we open up the image again just as a visual reference we'll see it here。

We can see that they're all different sizes。 So if we imagine this rectangle is。In this case。

 32 pixels wide， and then maybe 64， 128， 156 or some odd， those numbers might not be exactly correct。

 but they're going to be a little bit larger and ultimately if we envision per the slide that we looked at previously。



![](img/ad5e3f6b767cac035f8979626c48f9fe_33.png)

These rectangles showing here。For the left one here， you can see it has an X and a Y。

 So it's going to have some x and then some y value inside the sprite sheet。

 And it's going to have a width。 and it's going to have a height。

 And that's what the quad is defined by。 So we want this quad。 We want this one， that one。

 and then this one。 And then we're just going to put them all sequentially into one table。

 that G frames。the Gframes paddles， and then individually we can just reference them at one， two，3，4。

 five， six， and so on， and that's how we'll be representing all of the rectangles。



![](img/ad5e3f6b767cac035f8979626c48f9fe_35.png)

So if you go back to the code there for that。Uil Lua。

We can see we're defining we're using that function that we declared or we showed in the slides previously。

 which is love。graphics。newquad， it takes an x and a y so we're starting our x at0。

 and then we're going to start our Y if we look up here start x at0 and then y at 64。

And then that's just down some distance on the spriteshe。

 and then we're going to say it's going to be 32 pixels wide by 16 pixels tall for the first paddle and then Atlas get dimensions in this case。

 which is going to give love。 graphics。newquad， the numbers that it needs in order to actually compute how to generate UV coordinates on that texture so that when it tries to render the texture with the quad later。

 things will just work as they should and in fact， now with newer versions of love。

 you should be able to just swap this in as just Atlas and you don't even need the colon get dimensions for right now。

 but either of those will be just fine。And then we're just going to incrementally just add 32 and 96 and those were the values that I was sort of alluding to previously。

 we're sort of shifting in our code kind of manually like okay the second we know the first one is 32 pixels so the next rectangle is going to be 32 pixels over and then 92 96 pixels over。

 which there's 32 plus the width of the second one in this case that would be 64 pixels and then we go down to the next line and this one is 128 pixels wide。

 the one line below the three that are contiguous and so on and so forth and then what we're doing is we end up putting all of those into our quads table that we're creating here at counter and we're just incrementing going all the way down the line and eventually ultimately we just keep adding 32 pixels down until we're finished with all four skin categories and then we just return our quads table and so in main as we saw。

Generate quads paddles is therefore just going to give us back that table of rectangles。

 those quads or UV rectangles from which we can anytime we call paddle render。

 which if we go back to that。Or any function that draws a texture， we just draw the texture itself。

 which we've named main because it's our main texture。

 you could call it breakout if you wanted to or whatever makes sense for you。

 and then Gframes at paddles at and then the math that whatever our skin is because four every four paddles is a different skin。

And then the size as well will be a sort of incremental index into those four paddles based on that offset。

 and then we are drawing it at x and Y， and that has the result once again。

 if I can show that of rather than drawing the whole texture。

 we're just drawing the one coordinate at size2， which was the flag that we were preserving and we move it around。

 and we can think of it just like it was a rectangle but it is in fact a big texture being drawn through just a window through a frame or a UV rectangle。



![](img/ad5e3f6b767cac035f8979626c48f9fe_37.png)

![](img/ad5e3f6b767cac035f8979626c48f9fe_38.png)

![](img/ad5e3f6b767cac035f8979626c48f9fe_39.png)

Okay。And take a water break。Very briefly。2。😔，Okay so with that out of the way one of the more foundational pieces in today's lecture we can begin to start to add more interactive elements so the first thing that makes sense is well we have the paddle how about we actually get a ball bouncing around and we've sort of looked at a lot of this already and so this is breakout to the bounce update where we'll sort add a ball here to bounce around on the screen I'm going to go ahead and just move us over to looking at breakout to or quick and get rid of all of these examples that we had there are a lot of files and this lecture represents a pretty big leap in terms of complexity I think it's important step for folks to get used to probably working in this kind of an environment because code projects game projects tend to be much bigger even than this but do excuse the number of files as we bump up but I'm going to go ahead and go into not there but in main and let's just run this really quickly just to see what we have that we're working with I'm going to hit start here。



![](img/ad5e3f6b767cac035f8979626c48f9fe_41.png)

![](img/ad5e3f6b767cac035f8979626c48f9fe_42.png)

And then we can see right out the gate， we have the ball moving sort of in a random direction。

 but this is altogether not unlike what we've seen with pong right where we have a ball bouncing off of the paal and then it bounces off the top and the。

left on the right edges of the screen now if we just let it keep going。

 I do believe it will just go on into infinity at the bottom edge of the screen。

 which is okay because we have to model the loss condition and health and things like that in the future。

 but we'll just quickly look over those pieces and in fact most of all of those folks I've already seen。



![](img/ad5e3f6b767cac035f8979626c48f9fe_44.png)

Probably the part that folks might not have seen previously is we have this new function generate quad's balls。

 so this is going to take instead of paddles we want to actually have as part of our texture we do have all of the different balls and the different colors for them as well so let's take a look at that here if we go to graphics and we go to breakout。

We'll see that they're actually baked into this same texture， the benefit of having an atlas。

 we can just point to any piece of this one image and they're all there and we can visually also see are all of our colors working well together does everything look good and so therere maybe even slightly hard to see but there are these seven that are right here kind of by the hearts as well which will also need at some point in the future spoiler alert。

 but we can choose any of these colors if we want to。

 so very easily also the benefit of this is not only do we have just ease of general at working with code in terms of getting every individual sprite every individual graphic that we want from a large collection。

 but there's just a。I think an impetus to add color and variety and various visual elements to your project because it's relatively trivial to just create a whole bunch of rectangles and then just just choose okay I want this skin or I want this image here for this thing instead of this other one you don't have to load in this new texture and do all this stuff so I'm going to go ahead。

 go back to main Lua。And we do now have in source。A ball Lewis is' going to be largely the same。

 it's going to take a skin as an argument so we can decide to parameterize the ball with a skin if we want to and make it random。

 but in this case we also have a collides function。

 this is the exact same AABB we use with pong and ultimately this assumes that it takes in a target rectangle。

And this will also decide if it bounces off the wall， so here it's the same code with pong again。

 just in this case， also the top of the world as well That's what the self do y less than or equal to zero bit is so that's just the top of the wall if it's the top of the wall we also want it to bounce down if it's the left or the right again we're inverting the Dx and if it's y the top of the ceiling of the game。

 we want to invert the DY and otherwise keep it moving in the same direction。

 play some sounds things that folks should have ultimately already been seeing but these are all largely with the exception of the quads function which again if we take a look at that as well I'm going to go ahead and open up it's in our UT file。

We come down to generate quads balls。Right down here。

 it's ultimately going to be a relatively manual process。 We don't to fix it too much on the details。

 but we're going to essentially figure out creating an x or there are eight pixels wide and tall which are these two parameters here but the X and the Y are going to sort of be manually hard set based on the indices into the sprite sheet that's sort of one of the drawbacks of having a sprites sheet that has multiple different sizes of textures you do have to do some amount of manual work at times you can't just do a loop that'll just iterate through the entirety of your texture the balls recall we're in sort of like a defined small space right directly adjacent to all of the bricks and that's totally fine。

 you'll just sometimes have to do some manual work to programmatically extract them we're to turn them into U coordinates and that's all we're essentially doing with these loops very similar in spirit to what we just looked at folks can look at it if they want to on their own perhaps but it is essentially the same logic just taking an X and a Y adjusting it by some amount and then also adding eight by eight pixels to create those wind。

Those little rectangles themselves in a group and then grabbing four and then grabbing three because recall it was four balls on top of the three in that example。

 and with that we have the ability to then just render whichever ball skin we want to and then render play the game and use it just as it were a pong ball for example。

 and it functions identically， so that's the extent of breakout to。So now。

IfWe transition over to breakout three， this is gonna to be a little bit more of an exciting sort of update so breakakout three is the brick update and so folks might have already noticed that pong is sort of this two playerer game where you have a paddle and versus a paddle they bounce a ball between them and then the goal is to get one ball to go past the other end of the screen in breakout the goal is a little bit different it's to actually break all of the I believe the original theme of the game is you're breaking out of prison or something like that and so your goal is to break through the bricks of the wall in your prison cell and in this case sort of imagine something similar to that but probably more of an abstract idea we have these colored bricks that are just in space and then every time we bounce off of one of them no matter which direction we want it to bounce off and then we want to clear that brick or if it's a higher tiered brick we might want to。

 for example， if it's green or red， maybe the different colors represent the tier or the hardness of that brick and so hitting it once。

Might actually reduce its color back down by one， therefore maybe giving us a high amount of points and then also keeping the brick in play so that we can still hit it again and then eventually when it gets to the lowest color ti then remove it from play but then this gives us sort of difficulty in a sense and also just visual variety as we saw previously having a bunch of different color bricks gives you a bunch of different ways to visually just present ultimately a refreshing and dynamic playing field and we'll look at what's really cool in this lecture is the randomization of what that could look like with a level maker which we'll see pretty shortly within a few examples but to start with as we can see just looking at the slide it's essentially a grid of bricks in this case so why don't we go ahead and open that example up so we can take a look at it。



![](img/ad5e3f6b767cac035f8979626c48f9fe_46.png)

Close all of these， go to breakout three。In the repo and then we'll go ahead and run it so largely still the same and in fact this will always stay looking this way through the rest of the course。

 but if I hit start we'll see that we started with just a single row at the very top of bricks and in fact we also can see that we have collision working and breaking the bricks。

It's not functioning in the way that we might expect it to， and we will take care of that shortly。

 but we do indeed have bricks that are in play and are being taken out of play when the ball collides with them and we still have infinite sort of the ball going below the surface。

 so if that ever happens we're kind of out of luck and we have to restart the game if I restart。

Just rerun this one more time。We'll see that's actually a little bit smaller。

 the ball is moving a little bit faster as well so we're randomizing a few things for this example。

 I'm going to run it one more time I'm to try to get a group of more than more than one row。

 let's see if we can get that this should be generating between1 and 5 so there's two for example。

 two rows and the rows have variable columns with this resolution we can fit 13 columns of these 32 pixel bricks with 16 pixels of padding leftover。

 those are the sort of the restrictions that we have with this virtual resolution recall we are using a virtual resolution in fact the same virtual resolution that we've been using 432 by 243。

But with a little bit of just a few variables， we already sort of have this dynamic play field。

 we have not just one row always although we did get that just one row several times back to back。

 but between one and five or so let's see one more time if we get multiple so here we have four and we just let the ball kind of fascinating about washing the ball just sort of having like sort of having that god mo on and break out or something where your ball just doesn't bounce off of bricks but as you can see they're sort of there they're hovering in space。

 the ones that we're collided with are in play， the ones that rather the ones that we're collided with are out of play。

 the ones that didn't get collided with are still in play。

 and once we finally break every single one， we can start to think about okay well let's go to the next level。

 maybe we'll start to add more color variety， maybe higher tiered bricks so on and so forth。

 So if I go over to breakout three if we look in main。

 the play state ultimately is going to be still the state we're gonna to look at。

 but we did add another frame table。

![](img/ad5e3f6b767cac035f8979626c48f9fe_48.png)

For our bricks， so generate quad's bricks now bricks are relatively deterministically generatorable。

 they're all the same or rather the quads are deterministically generatorable because they're all the same width and height if we look at our texture again which if we pull this up we'll see that the bricks at the very top of the screen or kind of all in these 32 by 16 squares kind of going left to right top to bottom about four rows worth we could just iterate over essentially those four rows and then minus minus the balls the heart and the last sort of key is kind of in a weird spot if we won't use that in this particular lecture but if folks wanted to use that they could define a quad themselves by figuring out okay what's 5 times 32 on the x over and then three times 16 down get 32 by 16 rectangle and get it that way but if we assume that we want these sort of six by three so 18 plus 321 bricks or so we could just iterate throughout the table offsetting down as needed to get our 21 bricks。

And generate quads from that， so let's go ahead and look at that function really quickly and we'll just skim over it folks can read it the implementation if they want to at home。

But if we say。So here we are taking a slice of， in fact。

 this is a helper function that we've written to Lua doesn't have a function to do this by default。

 but we do have this larger generate quads function which takes an atlas and gives us the width we give it the width and height that we want to assume that every sort of image within that texture is and then it will just do the job of automatically splicing the whole thing for us top to bottom in these x by y increments in this case 32 by 16 increments。

 and so if we go ahead and in this case you can see table dot slice is just whatever the result of that is which will be a table I want from index1 until index 21 which I just alluded to 21 different bricks。

 I just want those 21 bricks if we were to just in this case you can look at this table do slice implementation all it does is just create a new table it's not an inplace slice it'll actually return a new slice of the table。

So we will iterate this is Lu's iteration loop syntax。

 which we might not have taken a look at for its actual iteration numerical iteration。

 but if we say that the function takes in a table at first to last and then a step value。

 we can say okay for I gets first or one so in the event that we didn't actually pass it a first value。

 so start I at one or whatever we define us first up until last this comma is or the length of table。

 this is Lu's weight to get the length of a table with this hash sign here。

And then an additional comment here is the step that we should take when we do our iterations。

 we could give whatever step we wanted to， we could give every two， every three。

 we could do negative one if we wanted to to iterate backwards through a table we could say I gets the length of table until zero or until1 do a step of negative1 and then we're just going to say at sliced at the index of slice plus1。

 we're going to just get whatever table at I is and then we're going to return that so slice is essentially that one through 21 or our particular our particular use cases window into that table and then just uses this larger generate quads function which we're defining and including with the repo takes an atlas a width and a height of whatever tile again this is assuming a uniform width and height that you want we're going to decide what's the width and the height。

In this case， this is the number of images in the sheet， so the number of sprites wide by tall。

We just have a number that we're going to start with and then for this is a nested loop here so we're going to on the y axis。

 we're going to iterate in rows， but through each row we're going to take whatever the column is that that index so for x is equal to0 within that loop every time we will then go the width of the sheet over in those blocks because it'll be calculated based on the width and the height and we'll just generate a new quad so for every y we're going to grab a tiles width or in image width all the way until the end of the x axis。

 the size， the number of sprites in that sheet on that axis then we're going to loop back down to the next y value start x again at zero go over again y is now the third one down go over until we've gone all the way down through the sprite sheet and we've grabbed the x and the y's width of the image that we care about in this case we care about the bricks 32 by 16 so we're sort of pretending that the sprite is。

PrOf 32 by 16 bricks if we open the graphic up really quickly。

We're sort of pretending that this whole thing is just bricks， we're splicing it up into quads。

 we'll iterate down the line y all the way down to whatever that would be this tile sheet divided by 16 y。

 and then the tile sheet divided by 32 on the x and then these 21 bricks here and that's how we can divide and this is a common thing that you'll see when you typically have a sprite sheet。

 for example， a texture sheet that you might use in something like Minecraft you might see that floating around on the internet or lots of games where you might have an animation。

 a set of frames that are the same size。For example， a character might not really change its size。

 even though the animation looks like it's changing a lot。

 in that instance you would do what we just showed with a generate quads that takes a uniform。

 assumes a uniform size of everything in your sprites sheet and then just that's your one sprites sheet。

 that's your one sort of table of quads， in this case things are a little bit more dynamic and all pack together so we're pretending。

 but we're just going to slice the first 21 off of that ultimately fully chopped up sprite sheet。

And so if we assume all of that， we have our generate quads， all these utility functions。

 we won't have to look at those anymore throughout the rest of this lecture。

 but for folks who want to create their own and for future animation related things that'll be helpful。

 if we go back to main dotlua。That's where we were just looking at。

 so that's where we create the actual bricks table， we now have all of our bricks。

 we can go over to our play state。And whoops， I didn't mean to press that key。We'll look at。

Here inside of our init function， if we look up here， is where we're going to actually create our。

gririd of tiles or grid of bricks rather。 And this is really important because this will tie into the later examples where we begin to。

 in this particular example， we just have a very plain sort of collection of just one blue。

Varant brick。The actual columns in rows were random， but the texture was the same。

 but let's say we wanted to add variant of the skin or the tearer or we wanted to maybe add gaps or maybe we want pyramids or we want inverted pyramids or whatever you can think of sort of visually Well all of that functionality is best I think encapsulated and sort of an object sort of how we decided last week to encapsulate the behavior of what it means to have a state a game state。

 I think it makes sense to encapsulate the idea of generating a level into this thing that we've created called level maker as we see self-dot bricks right in in it is just getting levelmakerr dot create map and so before we take a look at that we'll just quickly see we have in here。

 again all the same functions we saw previously of update and render we have the paddle and the ball being updated in here with DT and then we have our collision detection。

We have and that's for the ball and the paddle， but then we have the for k brick in pairs recall。

 that's how we iterate over a table self dot bricks。

 which is that group of bricks that we're going to get from level maker。

 if the brick is in play and that our ball collides with that brick。

 we want to call this function hit， which right now all it really does is just essentially disable in play so that it no longer renders。

 which if we see in here， every time we have a well actually it's deferred to the render function。

 the render method on the brick class itself， what we're calling render on every brick。

 and if we look at brick which is a new class that we're defining here a very simple class。

We have selfdot in， which starts off or other， sorry we have selfdot in in the hit method which will turn false if we hit。

 and so the purpose of that is that now we can essentially mask out the bricks that we don't care to look at or collide with。

 we can just essentially do an if statement to ignore that brick for the purpose of collision and for the purpose of rendering。

And sometimes you want to even preserve this if for example， you were to。

 let's say your instinct might be to just completely get rid of the bricks， and that might work fine。

 although you would potentially run into issues， you definitely want to remove it in place when you're doing iterations。

 but let's say potentially if you were to lose or some other。

Condition in the game you wanted to show the same exact map to the user to the player rather than have all of the bricks stay exactly as they were。

 Well， it would be harder to do that if you were getting rid of the bricks。

 it's much easier to just toggle all of them back in play and then restart the level that way So this is an option。

 you certainly could remove the bricks， but we're deciding to do this in case you wanted to consider doing that and just to illustrate it as an option。

And then again we saw this same logic when we rendered the paddle we have our own bricks quad and then we're essentially doing a calculation。

 we're starting at one， we're adding our color times4。

 so the color is essentially which group of bricks it's every four bricks in this case has a essentially that's where the colors are divided up and then we're also going to add our tier so that's an index into sort of that group of four colors and so that's going to allow us to take our tier and our color combine them index into those 21 bricks that we saw or yeah 21 bricks that we saw and then that will give us the exact rectangle that we want to display on the screen and these colors and tiers and whatnot will be a lot more relevant as we start to explore later examples in here。

And so lastly， the last piece of this， again， which I alluded to previously， is the level maker。

 And so the level maker is going to start off slightly simple， but。

We're going to just create a in this case， a static function。

 so this isn't a method of level maker we're just going to create a static function because we don't really need this we don't need a level maker instance per se living anywhere we can just call this function that exists somewhere in this level maker class and sort of encapsulate the idea of it but not worry about creating a level maker object and having it call a method and preserving state we don't need to really worry about too much of that right now and this is a common thing you might see for classes that have this function you might use as a utility or something and you want to keep it around but not create an object of a level maker that exists in memory but essentially here we create a random number of rows and columns。

 which is what we saw previously between five rows and between  seven and 13 columns remember 13 is the max number that we can visibly fit on the screen so we're just going to cap it at that。

And then again another 2D loop， so for y gets1 until the number of rows。

 so we're going to iterate through our rows， and then we're going to do a nested loop to iterate from our x's going left to right。

For the number of columns， we're going to say B gets a new brick， this is the constructor again。

 we're going to say it starts at x minus1。And then it's going to be multiplied by 32。

 remember coordinates， even though LuA is traditionally one index， which is what we're doing here。

 you could start this at zero， but typically in the world of Lua and love programming。

 you start your loops at 1 so we're just conventionally doing that。

 but you' you're going to want to minus that by one before you do multiplication because coordinates are not one index。

 there's zero index， so assuming that we want to start at index0 for our x axis。

 we're going to multily， we're going to subtract x by1。

 multiply by 32 at eight to give us a minimal padding from the left side for all of the bricks and then we're going to add also an offset based on the number of columns。

 the delta between the number of columns and 13 multiply by 16 pixels。Which is again。

 the max number of bricks that we can store on our map on our size are on our screen size。

 and so this just ensures that。Whatever X we're at。

 we're shifted over a certain amount by padding if we don't fill those 13 columns if we have six bricks。

 for example， this would end up being 136， which would be 7 times 16 which would be the amount of padding we would have on the left edge of the screen which would just make sure that everything is centered which it'll put us about halfway between the two edges because the bricks are 32 pixels wide so by dividing by two and having it be 16 that makes sure that we account for the right edge of the padding implicitly by shifting over by 16 pixels instead of 32 pixels and then lastly a y coordinate。

 we're just going straight down in 16。 they're not nothing too fancy。

 they're 16 pixels tall so this just ensures that they are all contiguous and then lastly we're inserting that into our bricks table and then returning that which again is what we were using previously in our play state and then now we have all the bricks in our actual play state。

 we can collide with them set them in play out of play when we do hit and everything。

Works as intended， just one more reminder， just two。



![](img/ad5e3f6b767cac035f8979626c48f9fe_50.png)

Illustrate。You can visualize it again you see the rows and columns。

 you see that we can basically approximately fit， this isn't fully getting this 13 but you can kind of see assume that there are about 13 bricks worth of space。

 we have padding it's centered and that's again accounting for the offset between the number of columns and the number of bricks we actually created in our table looks like one。

 2，34，5，6，7，8，9，10 so if we were to put three more we would have just a little bit of padding on the left and the right。

 but that's how much we can fit and so they're all just being rendered and set in play whenever the ball hits them and that's the extent of essentially the level maker。

 the foundation of all of our future procedural grids throughout the rest of these examples which will be a lot more concise I think。



![](img/ad5e3f6b767cac035f8979626c48f9fe_52.png)

Okay。Water break good。A lot of words。So that was essentially getting breakout in a visual state that is more or less what we expect to see when we look at the game。

 however there's one sort of major thing sticking out and that's the fact that when we were just playing the game。

 the ball was sort of going right through the bricks and not really functioning the way that it's intended to so this will be a larger example in a couple of ways but this is the collision update and so。



![](img/ad5e3f6b767cac035f8979626c48f9fe_54.png)

![](img/ad5e3f6b767cac035f8979626c48f9fe_55.png)

Unlike pong， unlike flappy bird， there needs to be a certain way that the ball behaves depending on which direction。

 for example and how much the ball clips into the bricks because it can bounce into the left and the right edges of the bricks as we probably saw at the top and the bottom pong was very simple in the ball would move left to right and then it would always essentially be checking to see if it bounce against the right edge of the left paddle and left edge of the right paddle and it would just bounce inwards but if it bounces off of for example。

 this edge here and it's going this direction， we want it to bounce out this way。

 but if it hits this brick coming from the bottom， we want it to go this way and so on and so forth throughout all four directions and so collision ends up actually getting a little bit more complicated in this example than it does in pong and also similarly the paddle here we didn't do a whole lot of fancy work with pong's physics when we did pong but in this particular example if we want to and also in real pong and breakout。

IfWe want to give the paddle just a little bit of physical control and have sort of an influence on the angle。

 we need to also take a look at how to collide， how to test for a particular collision on the paddle in a slightly different way than we previously were doing。

And so we'll start by just talking very briefly about the paddle col because this is the simpler aspect of the two。

 the simpler process of the two， and that's essentially that there is an offset that we could look at when we think of the ball coming down and hitting the paddle essentially it's going to hit the paddle anywhere along this top edge and depending on which offset it hits we could sort of if we sort of eyeball howg and breakout worked that sort of closer to the edge it hits sort of faster。

 we think it should bounce and sort of like sharply bounce。

 that's sort of the feeling that one gets when playing pg or breakout And so in order for that to be calculated。

 we have to say， okay well how far from the center of of the paddle did the ball actually collide So if the ball hits and we can call that ball offset for all intents and purposes right here。

 but if the ball were to hit like safe right here， the offset is going to be smaller it's going to be maybe two three pixels。

 but if the ball were to hit somewhere over here， well now we have a much larger offset and also in our example。

Concerned with is the paddle moving left versus right for example， if we move the paddle to the left。

 but the ball just continues to bounce up into the right as it would normally do well that's not exactly what we expect we might expect as we're moving the paddle for that to sort of have an effect on the ball So if we're moving this way。

 we sort of want the ball to go bounce this way， especially if it's right on the edge is's kind of where the sweet spot is and so we can essentially take figure out what the midpoint is of the paddle and the offset of the ball and then just multiply if we're assuming we're moving in this direction and we do that calculation。

 we'll just multiply the delta between the balls the ball and the paddle center and some constant that we can tweak and then change the the dx of the ball to be negative in that case and then vice versa if the ball were to come here for example。

 and we want to make it go sharply to the right based on how far away it is from the center。

 Well we'll take。This offset here again， and then we'll just go ahead and convert it to a positive Dx。

In the same exact way， the farther away the ball is from the center。

And then we'll take a look at brick collision as well， but before we even get into brick collision。

 let's just look at the code and where that is before we make that transition。

 I'm going to go ahead and also take this opportunity to demo this example so we can see visually what I'm talking about when I talk about this。

 I'm going to go ahead and close all of these。Lots of projects open here， okay， breakout four。

 and I'm going to go ahead and run this。

![](img/ad5e3f6b767cac035f8979626c48f9fe_57.png)

So the ball's moving at kind of a relatively shallow angle， but I'm going to go ahead。

 notice that it bounced， it didn't actually just collide through it。

But it's behaving a lot more like we expect the game to behave and so well it's a little bit too sharp on the angle。

 but you saw that I moved the paddle to the left and it kind of right on the edge and it really took a sharper angle turn to the left and allowed me to sort of。

Influence the trajectory， the angle and just the way that I cared about and not only that。

 but we were sort of getting ahead of ourselves a little bit。

 but the ball is actually colliding with the bricks and not just sort of clipping through them as if it had unlimited power or whatnot when I would just run it one more time and see if I can illustrate that bouncing maybe to the right or the like。

I was hoping for also slightly more bricks， but thankfully it's moving just where I want it to so I'm going to move to the right and hit it real hard and then it's going to give a nice sharp angle bouncing to the right let's see if I can get it to the left。

And there I hit it slightly not on the edge， and it was still moving to the left and it still hit it and moved it to the left。

 but it was a little bit less sharp of an angle because it was kind of towards the center and that's sort of like the overall feel that we're going for because that's kind of more or less what pong and breakout were doing with their own physics。



![](img/ad5e3f6b767cac035f8979626c48f9fe_59.png)

If you go ahead and look at the。Play state， which is going to be in source， states， play state。

Now we're going to find we got a lot of collision code in here。

 but essentially the code we just looked at needs to take place of course。

 in the paddle versus the ball collision code like where the ball is colliding with the paddle so we're going to go ahead and again we care about whether the paddle is actually moving to effect this if the paddle is not moving in a particular direction it's just going to kind of preserve its DX and is going to just shift its DY but if we're actually moving left。

 which we can determine by our Dx being less than zero which should be moving to our paddle is moving to the left。

Or moving to the right， we can now use those and then do a check。

So the center is also going to be an important thing here。 recall we need that offset。

 We need to actually have an offset from the center of the paddle to wherever the ball hits the paddle to determine assuming that we're moving either left or right。

 how much we should essentially multiply we should essentially multiply some constant by that amount to add onto our Dx to make it sharper because the more our Dx is relative to our D。

 the sort of sharper the angle is going to be if our dx is relatively shallow， it's not moving a lot。

 we'll have a much more upward trajectory because our y velocity is higher。

 is taking more precedent than our x velocity， but assuming our x is really high。

 it's going to be more like this and it's going be a lot sharper So we're going to go ahead and take a look at some of these other variables here。

 starting bounce， Dx is want our dx to start at like our initial okay 50 is the assumption that we're going to work with and then a multiplier these are tweakable you could make starting bounce Dx higher or lower depending on your。



![](img/ad5e3f6b767cac035f8979626c48f9fe_61.png)

But these are sort of numbers that I've experimented with and found work pretty well for demonstration。

And then you can do some math here if selfballx is less than the center so if we're moving left it's other condition here so if the ball is to the left of center of the paddle and we're moving left so again's we can kind of see that on our slide there it's exact actually kind of example I'm talking about but let's assume that paddle is moving left and the ball is to the left of center well that offset there we can just multiply that by that eight magic number that I've come up with through balancing and then we're going to add that eight times offset to 50 and then we're just going to set that to be our negative dx and so if we look at our code we'll see that happening here so the offset is the center minus the balls X and then we just set that to the negative starting bounce dx and then we do also an additional minus of the angle multiplier of eight times that offset and we do the exact same thing on the right side only it's positive because if we're moving to the right to the right from the camera's perspective。



![](img/ad5e3f6b767cac035f8979626c48f9fe_63.png)

The offset is going to be on the right side of the paddle if we want it to move to the right and then it just needs to be the ball is going to want to bounce to the right in the case that we're moving right。

 and so it needs a positive DX and so we're going to multiply accordingly in the same way。

 just positive instead of negative but taking the same offset sort of taking whatever the ball's X is minus the or minus the center of the paddle and so that's essentially what we can do to give it the sort of feeling of a physical pa。

 it's not exactly modeled in the way that pong or breakout would have modeled there is I believe there was more intricate and it was also electrical wiring or it was an actual electronics that were wired together to perform the logic。

 but ultimately it feels really good， it feels similar to it and it's good enough for our example that's the paddle and the ball giving it sort of I guess English should be the term putting some English on the ball or whatnot whatever folks say。

In that circumstance。So the other bit of code we're going to need to take a look at。



![](img/ad5e3f6b767cac035f8979626c48f9fe_65.png)

Is if I go transition to the slides。The brick collision now this is a bit more complicated。

 but essentially in pong when we were detecting the ball colliding with the paddle and then bouncing back。

 essentially actually what we're doing now with our current paddle。

 there's an AAB collision detection process that takes place and then for the paddles it was sort of hard set okay it bounces from the if your player one and your ball comes down you want it to bounce to the right and then same thing for player2。

 you want it to bounce to the left it's just a simple inversion of your Dx essentially but with breakout if you come in on the top。

 you're going to want it to bounce up， but if you come from here and here as well on this edge on X edge or a Y edge you're going to want it to bounce in a different direction you're going to want to flip whether it's your x or your Y。

Velocity， it's not just as simple。 Always assumed to be change your。

X velocity in the case of pg or y velocity in the case of breakout。

So we can start by thinking of this in terms of midpoint。

 so we've been doing AABB collision detection which just takes a couple of boxes。

 their' XY coordinates at the top left and then just does some simple checks to make sure there's no gaps between them。

 but we're going want to actually figure out at the moment of collision between these two there's going to be a smaller and a larger gap between either axis。

 the X and the Y axis so we'll say that we have these center points。

 CxB and C Y B and we'll use capital B for brick， lowercase B for the ball。

And then I will posit that we can then take an offset called OX that is essentially just the bricks sort of center point on x minus the balls center point on X。

 and this is an illustration just to kind of show what that looks like if we have center points here。

The brick minus the ball， in this case， this will be a positive O X。 And if it were here。

 if the rather on the next slide， if the。Ball were to the right of the brick。

 then it would be a negative O X。 So this is a signed value。

 and this is relevant because this will allow us to correct the ball when it collides。

 which we have to do in order to reset it if the ball were to hit， for example。

 here on this left side， we want to make sure we shift it back out towards the left。

 and if it hits on the right side， we want to shift it back out towards the right and the same idea applies to our y axis we can take an offset of y So how far part of the midpoints between the brick and the ball on the y axis and this can be negative as well and we'll use this negative value to correct for the ball's collision based on whether it hits the top or the bottom。

Now if we pretend that we are calculating a collision that is approximately at these two values。

 but let's say this ball is coming down and it hits this brick at 10，5 and 1017。

 now we can see that there are 12 pixels apart on the y axis， but zero pixels apart on the x axis。

 so there are essentially almost completely aligned。

 but there is a delta between the two on the y and that's where we know that the collision is actually taking place。

 we can intuitively see that it's not occurring on the left or the right side。

 it's occurring on the top side。So we have Ox of 0 O of 12， those are the offsets。

And just as a spoiler alert， essentially， the offset here is almost always just going to be。

 or the access is always going to be the larger of the offsets typically。

But there's some math we're going to have to do excuse me to do to actually shift to actually figure out how much we need to shift the bulb by when we resolve the collision。

 so assuming an O x offset of 0 and a Y offset of 12 here， sorry don't mean touch the TV like that。

There is going to need to be these other values called PX and Py。

 which are the sort of penetration depths of x and y into the brick from the balls perspective。

And we can just calculate that math here。 So there's a couple of these values。

 these numerical values that are essentially half extents or radii。

 but in the case of the paddle doesn't really quite have a radius so much as it has a because it's not symmetrical。

 it's going to have a difference in its width versus its height in terms of sort of the effective analogy for the ball's radius。

 but we essentially need to calculate you know between the two like there's a max there's a minimum distance that they have to be at in order to have a collision。

 or rather a maximum distance they're going to be at in order for a collision to resolve In this case they're literally touching if we assume the ball is8 pixels large。

 theres a four pixel radius and this is a 16 pixel tall brick， then this sort of。

I would call it a half extent sum Hx you could think of it as， but it's essentially this math here。

 This is going be the 12 pixel is it maps up here exactly to 12 pixels。

 but essentially there's going to be 12 pixels at the very least between the two minimally and depending on how big the collision is that delta would be a little bit smaller。

 perhaps but we're essentially going to need to shift backwards。

 that amount on whichever whichever axis got collided on in order to bounce the ball outside of the collision So we'll just resolve this math here。

 we can see that and that's what the aBS of Ox is。 that's going to be just the amount of pixels at which are the delta in these two exists at So there's there are 12 pixels apart here。

 that's the offset y。 we're going to want to essentially take the max distance between them subtract that and then that's going to be the amount that we end up reverting the ball by when we resolve the collision。

So let's go ahead and just shrink that math down to recall it's just essentially the radius and half width and height of the paddle。

 so that ends up amounting to this math here， 16 plus4 minus the absolute value aB of Ox so Ox in this case is0 they're literally aligned on the x coordinate here so that's going to amount to0 here and then 12 here for the y axis because there are 12 pixels apart so we end up with px or a penetration depth of 20 and then a penetration depth of 0 on the y axis Now between the two this one is higher 20 pixels higher and this one is lower0 and we actually want the lower of the two because that's going to be the one that we just triggered the collision on so folks might see the 20 and be like okay well that's higher maybe we should have the collision take place on the higher value but in fact it's higher because from the perspective of the algorithm it is effectively penetrated in 20 pixels because if。

We assumed that this was a collision of some kind here， Then it would actually be 20 pixels in。

 but that's not the collision that happened。 This is the collision that happened。

 And so we could essentially move this ball around， and these values would all change。

As you run these numbers， the lower of these numbers is always going to be the most recent definite trigger point。

 that the actual collision that occurred versus the。

The axes that are closest to part at the time of collision by virtue of just the way that the rectangles are sized and the way that midpoints work。

 so you're going to end up ultimately having a y axis collision with the lower of those two PX and Py values。

 which then we can decide to shift the ball negative based on that the amount that they collided the amount that they were different。

 in this case， it's going to shifted by zero because that's where we actually ended up with here。

Z pixels。 but if were if this were actually clipped in， this would be slightly higher。

 this would be like one pixel or two pixels or the like， but in this case。

 it's going to be zero because they're literally touching for the sake of illustration just so you could see them looking at or be like 0。

1 or 0。2 or something like that。And so if we just run this same math here， it's the exact same thing。

 you have a collision on the right side， in this case it's going to be x is ahead of the paddle。

 so we have 54 there， 34 here， it ends up being about 16 plus4 pixels。

 20 pixels of difference between the two at their max distance。

 max their minimum max distance per collision， so that's what's shown here， OX is negative 20。Y is 0。

 And so we condsed the same math that we did previously。

 and it's the absolute value that we're taking of the offset on the x。 So it's minus-20 here。

We end up with a zero value on the x axis and then a positive value on the y axis。

 even though again they're at the same y level， but the x axis is what they collided on because that's got the less delta on it then or the lower delta on it than the other axis So we have 20 pixels of penetration depth or of delta there effectively。

 but the 12 pixels here is essentially showing what it would think it was triggering if it were coming from the top or the bottom。

 it would think that it was a 12 pixel penetration into the rectangle。

 but it's actually not the collision we're checking for。 we're checking for the lower of the two。

 and so we have a x axis collision and then we shift it negative by px the ball actually and then that's essentially the gist of it。

 it's a little bit convoluted， but we'll take a look at it in the code here。



![](img/ad5e3f6b767cac035f8979626c48f9fe_67.png)

Or it's seemingly convoluted， it's I think intuitive to a certain extent。

 but we just have to essentially think about it in terms of if two things were going to collide together of the two axes that we are looking at。

 which is going to be more likely to be further away from the other and it typically is unless you're at the corners。

 which is where they can be about the same， but if you're on a flat surface relatively toward the center。

 it's always going to be the opposite。Angle， the opposite axis that you're close to。

 that is the colliding axis。 And then depending on whether it's a positive or negative offset。

 which recall， we have the Ox being negative or positive O Y being negative or positive。

 We can use the fact that it's negative or positive to determine， okay。

 we have to actually set the D。 we have to actually shift the pixel by or shift the ball by x pixels and then change its D accordingly。

 So let's go ahead and go into play state。 It's going to be below where we collide with our。



![](img/ad5e3f6b767cac035f8979626c48f9fe_69.png)

Oh sorry， this is actually the code here， I scrolled down in advance。

 but so this was where we collided with the paddle， we checked the paddle collision code。

 we scrolled down a little bit here， we're going to arerate over all of our bricks as we were doing before。

 and then we're going to hear to essentially do all the math that we just showcased visually。

We're going to create our half radius points and our half extent points， our CxB our CxB lowercase。

 and those were the center points for our ball and paddle respectively。

 we calculate the offset just by multiplying those center points or sorry by subtracting the balls center point from the paddle center point。

 we're going to get the offset it will be negative or positive which will be useful when we determine how to resolve collisions。

And then we perform that calculation that I showed on screen， which is the PX。

 we're going to take the absolute value of that offset。

 and then we're going to subtract it from the sort of half point。

 the half extent sum of the two colliding entities， and so we want the lower of the two。

Not the higher of the two， and when we do that， so if px is less than py。

 we can set the dx negatively， so in the case that the penetration depth of x is less than Py。

 that means that we collided on the left or the right side。So we therefore should reverse the Dx。

 whatever that was if it was coming from the right side。

 we want to shift it back to the left and if it's coming from the right side or left side we want to shift it to the right or backwards。

 and then we're going to want to also take the negative Px or Px from our OX or offset so if it was positive or negative。

 we're going to want to shift by whatever that amount was。

 depending on which side of the effectively the brick that we collided on that'll nudge just just out whether if that px was one。

 that means we went in one pixel， we want to shift back out one pixel same thing for the top and bottom and the same logic is just applied here。

 and then the last ingredient to this is that typically with games like this。

 we did this slightly with pong we want to also ensure that things kind of keep moving and escalating in a sense。

 so we're going to just add some multiply to our acceleration on D Y which is sort of the more meaningful axis it could you could do it on Dx as well but Dx because you manipulate。

DX through paddle movement that doesn't feel like a great and then also wrote it also kind of goes back and forth。

 it doesn't feel like a good use of balance to manipulate DX， DY。

We can just multiply that so the top to bottom interactions will be faster which will make other interactions feel faster and then eventually the game should in theory be so hard to play。

 we probably would want to cap this and we do in later examples。

 but it'll be too hard to play through eventually we'll probably lose and then that will be game over so just as a reminder just we just play it one more time that's effectively all of the collision code I'm just going go ahead and do another example here。

 you can see it's come from the bottom it it bounces towards the bottom it got shifted。

 I'll do this maybe we can get a few more bounces this time。



![](img/ad5e3f6b767cac035f8979626c48f9fe_71.png)

If we're lucky， and it'll be fun。in that particular instance。

 it bounced so quick off a whole bunch of them that it just cleared out a whole bunch back to back。

 but essentially that's the gist of what's going on。 And so now we have a way to determine。

 okay something collides from the left or the right or the top of the bottom。

 it's just based on that offset delta between the two axes and we want to essentially assume that the axis with the lesser of the two deltas actually is the or penetration depths is the actual one that collided because the penetration depth of the higher penetration depth。

 it sort of implies whatever is closer on the axis which if you're on the top and you're right in the center。

 it'll be x and if you're on the right and sort of center it'll be y and so on those exact angles you want the lesser of the two penetration depth which on the top example。

 it will be x and if it's on the side itll be rather if you're on the top it'll be y and if you're on the side it's going to be X。



![](img/ad5e3f6b767cac035f8979626c48f9fe_73.png)

Okay， so that was probably the most intricate， complicated part of today's lecture， thankfully。

 think the rest of the examples should all be relatively tame if we take a look at the next one。

 so yeah， indeed the next example is going to be quite a bit simpler。Okay。

So now time to transition to something a little bit more sort of playful。

 we currently have a you know a bunch of bricks but no real way to determine okay。

 what's our lost condition， I mean there's sort of a soft loss condition with the fact that the ball can infinitely go past the bottom of the screen but that's not ultimately what I think is the most ideal way to approach this game so what I'm going to go ahead and do is go over to break out five I'm going to go first and close out all these examples。



![](img/ad5e3f6b767cac035f8979626c48f9fe_75.png)

![](img/ad5e3f6b767cac035f8979626c48f9fe_76.png)

And then if we go ahead down to breakout5， I'll just run it real quick to showcase what we're going to add here。

So same as usual now notice at the very top right， so a couple of things going on here one is that。

Previously when we hit En， we just start going and now we can actually serve the ball。

 notice also fund sort of thing that the ball follows the paddle。

 which is how typically games like this aranoid to breakout or whatnot。 We'll often have this。

 but we have a few hearts at the top right of the screen So hearts are like a very zelda。

 I think people usually think I think of like Zelda or games like that a very sort of video gameie thing。

 We also have a score that we've added there too So I'm going go and press enter to serve。

 It's going to start moving in a random direction。With the collision texture we just added。

And then I just try to add a little bit of extra velocity there so every brick is worth 10 points in this case in this particular tier and as we'll see later。

 future colors will add more sort of different types of score intervals or score amounts per brick。

 but when I took a hit， you notice that I did detract one of my hearts and I have two out of three hearts so I'm want to presenter to serve again if I move around hopefully Ill purposefully just lose for the sake of time here。

But one more time and notice the ball is also randomly being set to different colors just for fun because we have multiple textures。

 multiple skins， but we essentially got all three of our hearts detracted and then now we have our game over state and it says final score 70 so the score was passed from the play state over to our game over state and also the bricks and everything actually really were transported between the play state and the surf state as well so we can take a look at that here in just a second a lot of these things folks have seen before so we won't spend too much time dwelling on particulars but if we go over to the。



![](img/ad5e3f6b767cac035f8979626c48f9fe_78.png)

Serve state， for example。We'll see that we have a ultimately some tracking logic in place here for the X of the ball to follow the paddle and just be raised above it。

 but also every time we call state machine change remember that was how we can essentially do that handshake between states we talked about that at the end of last lecture but every time we call G state machine change recall it will call its own exit function if defined and then we'll call its enter function if also defined and so what that lets us do is bring data from one state into another state because remember every time we create a new state with that state machine in main de Lua it's going to create a brand new copy of that state。

 it just this brand new object and that's often what we want but often also not what we want depending on whether this states should preserve some amount of continuity between them in this case if we're in the serve and the actual play state we can notice if I run it again。



![](img/ad5e3f6b767cac035f8979626c48f9fe_80.png)

This state， the title state or the start state has really no state that's meaningful that we need to preserve。

 but this serve state here has a score。 It has our HP。

 that's another variable it needs to move around it has the bricks because every time we create a brand new play state。

 this is all just right now what you're seeing is it creating everything from scratch。

 but as soon as I go into this play state like it didn't really look like much changed but in fact some stuff。

Did change， we went into a whole new state we're no longer we're in the surf state。

 we are now in the play state and so well now we're in the surf state again。

 but everything is being handed across with that G state machine change and we're taking those values in and essentially taking charge of those as our own new state when we do the enter function of all these for example。

 the enter between between the start state between the surf state and the play state so I'm going to go ahead and close that out。

 we'll take a look at the。

![](img/ad5e3f6b767cac035f8979626c48f9fe_82.png)

Serve state。Change is going to play so we're going to go to the play state right and these are all of the variables we want to pass from our serve state to the play state to say hey you'd now take charge of these variables these will be your variables to handle we are going to essentially get delocated。

 the states going to be lost but before we do that here take these things， take charge of them。

 you need access to this information to preserve that continuity so when we go to the play state。

And if we go up just a little bit here， notice that we're defining this enter function。

 which we saw previously it takes in a Paras table and we're just taking all of those parameterss。

 the table that we just saw， and we're just going to assign them to self dot the same thing so self dot paddle equals Paras do paddle so on and so forth。

 we're inheriting those and we're saving them as if now they're are state which they do become our state and so now。

In the same exact way， if we were to go for example， to the serve state down here。

 if we actually get a。If we actually go below the height of the screen with the ball。

 we can do the same thing here， so if selfhe is zero so we're now storing health and so we're subtracting one from health and that's mapping to our hearts we have 3H to start with one2。

 three you're out of the game if health is zero， we want to change to game over。

 so that's remember we did see that it's a new state or we'll change to the serve state and again we're passing in the things that we care about as being preserved between the two。

 we care about the paddle， we want the paddle it's positioned， it's texture， all those things。

 we want the bricks， we want the health and we want the score everything else there really isn't much else。

 but those are the things that we want to preserved between the two that we communicate back and forth with。

And so if we're in the play state， for example， you'll notice that we have render score and render health as a couple of functions we're defining in Maine。

 so if I go over to here，And we'll all just quickly glance over them we won't talk about them too much。

 but there are a couple of helper functions， the reason that we're defining them in main is because they're going to be drawn in several different places rather than define them in every state and just having them repeat over and over again it sort of makes sense to have them defined here in mainine where you could create a base state that has access to that function and then include do the inheritance thing we should last degree to includes equals that base state you could do that as well here we're just defining a function in main which just takes in a health and we'll just render it onto the screen using love that graphics draw just with the hearts we have this new we have a texture and hearts that we're dividing up and we're giving to we're giving to that function to call and render so essentially we're drawing from one up to our health number of times a red heart and then for the rest we'll draw frames two which is a dark heart and so if I go ahead and open up the hearts。

Texture might have just spliced this out from the。Yeah。

 I think I just splice this out from the full texture， it's a little bit hard to see here。

 but just it's just two sprites， just two like eight by eight ish sprites of a red heart and a unfilled heart and we just if you have three HP。

 draw three red hearts， if you have two HP， draw two red hearts and then one gray heart if you have one HP draw one red heart and then two gray hearts and that's essentially what we're doing here from one to health。

 draw those red hearts and then from one to three minus health do the exact same thing。

And then we have the display FPS and also a display score which takes a score and it's just a couple of very simple function calls that just set the font to small。

 and then we'll just render our score up to the top right。So that was the hearts update， breakout5。

 Now breakreakout6 is kind of fun。 So this is called the pretty colors update just for fun。

 It is just a funny goofy title。 but as you can see。

 currently we've only been dealing with very boring brick layouts in the sense that we just have blue bricks and they're just worth 10 points。

 Nothing really too amazing about that。 but if people are familiar with breakout even as we saw。

 I mean as you can see here， but even as we saw in the example that CS50 originally did C50 proper。

 there's various colored bricks and they all mean different things depending on the game。

 they can be a higher tier can they can take a certain number of times to break。

 they can break and then go down a color and then go down a tier and then be worth more points accordingly and so they essentially act as a way to one very the visual aspect of the game。

 but also two provide difficulty and some dynamism and it's just fun。

 I think it just looks really cool。 So this is all done in level maker which we saw previously so we'll just go ahead and transition over。

Level maker in breakreout six， we won't spend too much time looking at this because it's essentially the same logic。

In that you have rows and columns of bricks being generated in a table that have their own XY coordinates but the only other difference is now we're deciding okay should we also just change the skin and index into we have the 21 bricks like we'll just do some math index into whatever our skin is and then add an offset for or thatll be for the tier and then that will represent what that brick actually is worth and then there's some logic that we can use to calculate points and whatnot。

 so we'll go over to in this first off， let's test it let's just actually have it run I'm going to close others from here。



![](img/ad5e3f6b767cac035f8979626c48f9fe_84.png)

And then let's go ahead and run this。So right out the gate we can see a lot more visually interesting we've got purples and reds and greens。

 these will all still I think potentially be。Single hits， and they're all still worth 10 points。

 We haven't really done anything to change how they function。

 but they visually are really cool looking。 I'm not even。

Touching the screen I'm still somehow not losing y were still still going but essentially just with a little with just a few patterns here。

 we have some pretty interesting variety。 Now we can see just the very top row for example。

 you've alternating colors you've got red green， red， green， red green。

 So just imagine a bit on off on off for choose two colors and say okay if it is on red if it's off green if it's on red off green。

 just alterating between the two， or you can just choose not to have alternating colors like the second row。

 which is purple， or you can elect to have maybe bricks and then not bricks， bricks。

 not bricks to have gaps in your bricks and then that allows you to do the same logic as for colors except instead of alternating colors now you're alternating whether there's a brick there as we're iterating through our rows and columns in our level maker and then essentially this row right below it is doing the exact same thing。

 it's just inverted。 we start off at a sort of offstate for should we put a brick there and then we turn on。

off， on， off， on off。 accordingly。 And then if we just run this a few times， we'll see variant。

gririidds being generated so here notice also you know it shrinks to fit different sizes that would fit within the screen this one's cool it's got green and blue at the bottom and alterating colors these almost look like they were designed by hand but they're just using very simple procedural generation techniques I would love to even call it that but it is sort of procedurally generated grids and so we see here again almost looks like a human made that it's pretty cool we'll go ahead and just do one more time for fun。



![](img/ad5e3f6b767cac035f8979626c48f9fe_86.png)

![](img/ad5e3f6b767cac035f8979626c48f9fe_87.png)

![](img/ad5e3f6b767cac035f8979626c48f9fe_88.png)

![](img/ad5e3f6b767cac035f8979626c48f9fe_89.png)

And this one's actually fully solid but because we're choosing symmetrical sort of approaches。

 they're always going to and also a symmetrical number of column or an odd number of columns they're always going to be pretty nice looking most of the time。

 especially if we'd keep it relatively simple we keep within a grid。

 we have just alternating colors alternating spaces but you could envision a world where you want to do pyramids or inverse pyramids or squares or maybe a circle or something and the sky is the limit ultimately you just have to write the code。

 the logic that can speak in rows and columns to do that and you're encouraged to experiment with that so I'm going to go ahead now open up level makers so we can take a look at some of the stuff we've added。

 I won't spend a terrible amount of time covering the specifics。

 but if we go up here just a little bit。

![](img/ad5e3f6b767cac035f8979626c48f9fe_91.png)

We're doing all the same things we were doing， just having a set of random rows and columns number so that we just have a variable size of our grid。

The highest tier and the highest color are essentially just a little bit of math that's going to look at our level and determine okay what's the highest based on the level。

 what's the highest tier that they can access if they're at a lower level we shouldn't give them really high tier bricks。

 if they're at a higher level， we should make sure that they can potentially do that up to a certain threshold。

 a certain number， which is that math that meanss first argument， no higher than tier 3。

 no higher than color5， there are no more colors than that or tiers than that。😊。

And so we're going down the line number of rows， we have all these variables for a skip pattern which is just flipping a coin one and two。

 make it true or false， this is the bit flipping on or off， so whether we should have a skip pattern。

 whether we should have an alternate pattern， what our alternate colors are。

 should we choose to be alternate colors， what our alternate tiers are， should we alternate tiers。

 which we can also do， which you'll see if you were at a higher level in the game in the level maker。

And then the skip flag， which is the actual are we on or off when it's generating。

 and then the alternate flag， are we on red or green if it's doing red and green or vice versa to allow you to change sort of how those are generated。

And then lastly， we'll take a look down here and then just notice that we have for if we are generating something。

 we're going to use this syntax that's particular to Lua that doesn't allow us Lua doesn't actually have a continue statement。

 but it does have a form of go to that we can sort of simulate continue with and that's using labels and a go to statement。

 which is from C and it typically go to is frowned on in the C world because it produces very unreadable code。

 but in this particular instance if we just stick to using it like continue。

 we can sort of almost think of it like we're extending the language in a way with our own syntax。

 but effectively we're just saying okay， we're going to go to a label that I've called continue。

And that's if we're skipping and we should be skipping this brick。

 we don't want to actually do all of this stuff of generating a brick。

 we want to just we're iterating， remember we're iterating every row and then every brick on that row so our goal is to skip bricks every brick should be off essentially on let's say the top row well if we' we need a flag that turns on and off every time it generates a brick and so if we're on the if skip flag is true essentially we need to say okay we're just not going to add a brick this iteration but we're still going to keep generating brick so let's let's just essentially skip this loops continue but in the world of C in other languages that means like keep running this overall loop that we're in but let's not do the rest of this loop's body so if we go all the way down here。

We can see this fancy syntax with double colons， which is how Lua does label definitions。

 and these are used specifically for go to expressions。

And so ultimately all the logic in here is to do all of that is to lay bricks and then depending on whether your ultimate flag is set。

 what's the color that we should draw at， should we draw or should we render a brick here or should we add a brick to the table here or not and then through this relatively simple set of procedures even though it looks like it can be kind of a lot it's ultimately just a set of like。

Check marks or flags that we're holding onto that every time we iterate and we're just saying， okay。

 are we in a itated or are we in an alternating sort of row if we are。

 okay well we need an on off flag。 So let's just on off on off on off next， are we alternating。

 No just put all the bricks Next are we alternating Yes， but let's start off。

 Let's start off So we off on off on off on so on and so forth。

 And then that through those simple procedures， you could think of maybe many。

 many ways to extend this， you have very interesting dynamic grid layout。

 So for folks who want to understand the nitty grty about it even more feel free to take a look at levelmakerr Lua。

 but that is the overall sort of summary of how it's working and how we now have these very nice looking grids。



![](img/ad5e3f6b767cac035f8979626c48f9fe_93.png)

But and we'll go ahead and just sort of transition back。

The other aspect that folks might have noticed， we have these really nice looking grids， but。

 you know， they don't really have any meaningful sort of data to associated with them in terms of their score in terms of their tier。

 all these things。 So， you know， let's say we were maybe per at least what the slide is showing。

 Let's say we have green or we have red。Bricks instead of blue。Well， okay if green。

 if a green brick were to get hit， which is what we sort of showcase in this slide there。

 then let's assume that blue goes to green goes to red goes to purple or the like。

 so a green brick when it gets hit should go backwards in tears So we're essentially weakening that brick。

 The green brick is essentially a stronger brick than blue but by hitting it multiple times we do we still get it out of play and we can even maybe make it worth more points as well and then also add tearsers to these bricks so that not only are they colored in different ways。

 but maybe they are colored and gold or colored and silver or bronze so you weaken the gold to get to silver to get to bronze to get to no sort of metallic color and then that's how you can get even higher tiers and higher difficulties and things like that。

 So let's go ahead and I'm going to close all of these。



![](img/ad5e3f6b767cac035f8979626c48f9fe_95.png)

So if we demo that。

![](img/ad5e3f6b767cac035f8979626c48f9fe_97.png)

In breakout seven。I'm to run this。We'll see here we're starting off with green bricks。

 so if I just start serving。Green turned to blue and we got 50 points。Okay。

 another 50 points see if I can hit a blue to compare the point amounts。

mightight be tricky for a moment。But this is a lot more akin to what folks might have expected to see。

 but okay， we got actually missed the point total that it gave， it looked like 25 points。

But there's also a sound effect now playing to folks here at home， but 25 points for blue。

 50 for green， so there's some amount of math that's going to apply 25 times color and then probably times tier as well。

So we say that purple went to red right so kind of this overall idea is just to make the map a little bit more visually interesting more rewarding and more challenging because if you imagine all of these were purple bricks it would take quite a long time to break all of them remember every time we bounce off of the bricks there are y velocity is going to be increasing now we should cap it ideally so that it's not infinitely fast and becomes untenable to play as you can see it's already becoming a little bit difficult for me to play but by essentially see it's getting really difficult even hardly play getting barely there。

 I'm going live there okay and this it gets restarted but you see I have 1300 points from you know breaking all these higher tiered colors。

These higher colored bricks， and that's sort of one of the aspects of this is that make this really cool。

 not only do we have visual variety， but this is going to impact our gameplay。

 So if we go over to our source code here。

![](img/ad5e3f6b767cac035f8979626c48f9fe_99.png)

Oops， I was on the right screen there if you go over to our source code。

So this all should probably happen within the collision part of the function。

 so that's going to be in the play state。So we go over here。

And then we'll notice that now we're also doing a bit of multiplication here so the tier of the brick which we haven't seen quite yet。

 but if you' had a higher tier you'll see gold， silver， bronze， whatnot。

 so whatever the tier is in the case so that it's not any tier besides normal it's just zero so this is going to add zero times 200 which is fine for right now and then whatever the color is times 25 which I alluded to so that's where we're getting the sort of higher level multiplied point total based on the color but also in brick dot hit if we go back to brick。

We'll notice that we have a little bit of logic here， so depending on what our tier is。

Ter is currently going to be zero， so for all intents and purposes we don't have to fix it on that too much。

 but essentially that's just going to shift the ball back or the brick back， a series of colors。

 five colors backwards in the list of point values。

 because every tier is five bricks of color and then here that's if we were to go back in tier。

If we were to look at self。 color here， if it's equal to one， which is blue， it goes blue， green。

 red， purple， I believe blue green， my memory is a little bit fuzzy on the exact colors but essentially if it's one which is blue well then okay that means that that brick needs to be no longer in play but and that's assuming that we're in tier zero which is currently what we're at if we're in a higher tier then we're going to start back at the highest color of the next tier down。

 which will be like purple or whatever color is highest tier。

And then we're going to also if it isn't one， let's say it's green or it's red。

 it's going to be two or three or purple or whatnot， then we're just going to subtract one。

2 or or three or four， which is purple， but essentially here we're just going to subtract the color and so that's going to then impact the score calculations and so on and so forth。

 and that's all we essentially have to do in order to get things working properly with the tier update。

😊。

![](img/ad5e3f6b767cac035f8979626c48f9fe_101.png)

Now。One of the funnest parts of this lecture I think。

 is the idea of particle systems and particle systems are really cool because they're essentially just a way to sort of add this visual flare and they're called a system because the particles that are inside of this sort of like emitter or generator kind of have behavior that you can configure and so as you can see here there's an example of the ball hitting what was a green brick but it's got these these green little blurry pixel things。

 particles that are emitting from that center and they're purposefully colored green because the brick was just green。

 so it's kind of just trying to keep in line with the coloration but right now when we hit bricks。

 they essentially just disappear right away and there's some element of just simplicity to that that's a a little bit drawing or unnerving or maybe just dissatisfactory unsatisfactory but this is I think a away and particle systems in general are all over the place if you're paying attention in games。

 it's a way to add just the little literally。parkle to your game in a way that adds polish and I think is just kind of fun to work with。

 but they're quite complicated and intricate in terms of just the number of tweakable parameters that you can mess with in today's example we care about just a few fields。

 a few functions that we'll take a look at， but to create a particle system it's just love do graphics。

 that new particle system， particles can take a texture。

 they do take a texture which is in this case today we're just using some simple circular texture that you saw some very simple small4 or eight pixel texture。

And it's going to then apply various alpha and colorization functions to those particles。

 emit them in a particular way， fade them out and so forth。

 and then that's how you can get the appearance that you want。

 but if you imagine creating like a diamond shaped you texture that you use instead。

 well now you can give it this sort of sparkly kind of cool glitter effect or you could create like fire。

 a fire- lookinging texture or something which might look kind of hokey now that I'm visualizing it fire usually often is just a collection of particles I think anyway in a lot of games。

 but you can sort of use any texture is the point that you can then apply all these other colorations in various things to and they're explained in more detail on the love 2D wiki so let's take a look at how those look and how we can add those really quick。



![](img/ad5e3f6b767cac035f8979626c48f9fe_103.png)

So if we're in。

![](img/ad5e3f6b767cac035f8979626c48f9fe_105.png)

Breakout eight， which is where we're going to be。I'm going to go ahead and close other here。

Let's just run it so I can show you what it looks like。

So it's going to hit one of these blue bricks and it does indeed destroy it。

 and also it's got like a little blue puff of smoke， which is kind of fun。

See if it can maybe start off a little bit slow， so used to how fast it was last time。

 but let's just give a little bit of speed there。Blue again， see if we can get it to be green be。

 might take a second， which we can。Oh there we go， got a lot of particle systems there so each of these bricks is essentially given its own particle system and a particle system will just be triggered to emit its particles and we're setting it to emit about 64 particles here。

And then。They all have a decay。 they all have a lifetime at which point once that lifetime has gone by。

 they'll all be completely removed and then it will just essentially reuse the particles that it's buffered in its particle system。

 and just with that small change now we have this sort of visually appealing way to give us feedback that we've actually collided with a brick and this is done in the play date。

 just like we were looking at last time。 So if you go to states， play state。



![](img/ad5e3f6b767cac035f8979626c48f9fe_107.png)

In the actually， no， sorry， this might be in the brick hit function rather。

 which is called from the play state。 So for in brick and we look at the brick hit function。

 So first off， I'm going to just point you to the fact that we have a bunch of palettes of colors here。

 So I've gone and handpicked out through color picker or the like colors from all of the。

variarous bricks so that we can match the colors of what the particles will be to those exact bricks。

 so we have approximately the RGB for all of the brick colors here， red， green， purple， gold， blue。

 so on and so forth。And you notice that we are declaring a new as a state variable in every brick。

 it's going to have reference to its own particle system， a new particle system。

 it takes in a texture， we me just give it texture of particle， which if you were to look at it。

 it's this very small sort of it might not even look like anything meaningful if we look at it。

 just a very tiny， it almost looks like something you would see if you were scrolling through metadata or icons in ohops。

 I mean hit' hit that one， it might just look like a little。Go to scrolling a lot to see it。

But it's just these pixels here， these are just what your particles。

 the particles that we're seeing here are made out of。

 it's just a very simple gray scale so that when you do apply color to it， it's very clean。

 doesn't have any preexisting colors or anything like that。

But you could make this literally any texture you want to。

 and it would just spawn a bunch of those instead of this little sort of roughly diamond shaped circular particle。

 so I'm going to go back here so we are creating a P system short for particle system。

I've commented this out a little bit， but there's a few functions here。

 we have a lifetime that we're setting on the particles。

 all of these are documented in the love 2D Wiiki so between 0。5 and1 seconds of lifetime。

 that's how long the particle， each individual particle will live。

 a linear acceleration from an x1 and a y1 to an x2 and a y2 and it'll be variable between those。

 so it'll be some x between negative 15 and 15 that it moves。

 it's going to have a linear acceleration in a particular direction while it's fading。

 while it's fading away。And then it will only ever be between 0 and 80 on the y axis recall the particles are kind of falling down sort of like glittering down almost like there's this artificial gravity that's applying weight to the particles and so we accomplish that with a linear acceleration that can only be positive on the Y axis through this and then also the emission area which is sort of like the radius around the center of the particle system where it can actually be where it can spawn particles so roughly 10 by 10 pixels in this case and then the standard deviation will be 10 pixels away X and Y so within that radius roughly and then what that's going to do is essentially we've preconfigured the particle system it just has to actually call it now also to set the colors there's a set colors function here which we're just passing in the RGB between the color that we want to start at and end at as two pairs of four color component so RGBA RGBA we want to eventually fade out to。

To completely alpha transparent， so we're just doing that here with by setting this alpha to0 for the second color。

 it's going to be the same color but it' just faded to alpha transparent。

 but you could in theory have you could choose one color and have it fade into some other random color if you want to。

Particle systems are very flexible in the sort of ways that you can use them。

 but we're essentially going to multiply by our tier so that we're like more saturated on higher tiers with our particles for our alpha component for the first color that it starts at and then we're going to fade towards essentially transparent and then P system colon and emit of 64 is just going to actually shoot out it's going to actually admit those 64 particles that we've preallocated and trigger the actual operation of the particle system working and that's all you have to do in order to get a particle system to work that very intricate。

 complicated， they can be very dynamic and have a lot of cool behavior but for this example we're just doing a sort of like little glittery sort of puff of particles and those are some of the functions that you can use to accomplish that。

Okay， I'm going to take a brief water break。So with that we've added some visual polish to the game。

 but there are a few missing states still in our game。

 if we recall looking at the very beginning of the lecture we had this large state diagram。

 we had a few states still that we have to talk about and so one of those is the sort of level or victory state rather so whenever we finish a level we want to display a sort of level X complete or the like hence the the little illustration there with those few slides and this also represents progression because with every sort of victory in your game you can have a new grid of bricks that you make progressively more and more difficult which we've been alluding to in talking about but this is really important because now we can sort of have something to aspire to I made it past level5 or I got to level 10 and it's random here every time so you could play this a lot and kind of always see a different game you might get something very easy even shown in the level two there is actually easier looking than level 1 but I mean if you look and see level two does have purple bricks where S level 1 only has。

Blue and green， so in some sense it's kind of you know relatively equal， I suppose。

 but why don't we go ahead and take a look at breakout nine？And we transition to that。

I'm going to close all of these。

![](img/ad5e3f6b767cac035f8979626c48f9fe_109.png)

And then close this， breakout nine， now to test this， we might have to clear a level。



![](img/ad5e3f6b767cac035f8979626c48f9fe_111.png)

That might be too long of a level， I'll try and maybe get a shorter one， we'll see how our luck is。



![](img/ad5e3f6b767cac035f8979626c48f9fe_113.png)

![](img/ad5e3f6b767cac035f8979626c48f9fe_114.png)

More doable， let's see if I can get a single line， I'll just do one or two more iterations。Okay。

 that's much better， Okay， maybe we'll see。But these are purple。

 so they'll be a slightly longer have to hit them a few times。

 but we're going to have a score so I'm going to get the velocity going really high。

 hopefully I don't lose， this would be embarrassing。But essentially。

 what we want to do is we want to have the the。Score go into the victory state just like any other state did。

And then we want to have the。Maybe I'll just actually， I want to see just get a full blue one。

 give me a full， give me a full blue。ItThe one downside of having completely randomly generated levels is if you want to hard detect something it can be slightly oh yeah。

 definitely not that one we can have some fun looking at random levels I guess。

 oh oh boy that one is actually kind of cool that look like a castle actually okay one more time okay much better okay should be this should be reasonably fast。

So we'll just keep doing this and then we'll try to get a victory。But essentially。

What we want is not only do we want the。Li。State to transition right to create a new level。

 which we're going to do， but also that level， the actual tier of all the bricks。

 the max tier and everything and so on Oh there we go。 There we go， Yeah， there we go。

 That's what I'm talking about。Oh but and then I lost of course。

 let's see if that was convenient there， well we want the game to get harder with time too because that's part of what progression means it ultimately means not only do we okay。

 come on， please。This sort of oh oh god， this would be so embarrassing if I lost。Okay。Okay。

 just one more。Okay， this fingers crossed， is this going to be a victory？好。Yeah。

 okay that was a very lucky shot at the very end there。

 but as you can see we have a sound effect by the skin of our teeth we survived somehow on level1。

 which is embarrassing， but we have 650 points， Level1 is complete and we can press enter to serve against so now this is sort of like the illustration of what it means to have progression Now if we were to press enter now the game is going to store the fact that we're in level2 and not in level one So if we' press enter。

😊，Now we're in level two。 notice that so we're in the serve state again。

 a much bigger play field in this instance， but this is sort of how we do progression in games if you have levels and we'll look at something like this in Mario even though in the Mario examples you might not use levels you could apply the same idea and be part of the Mario problem set but you could take the same idea and then just in some way make your game state your world state slightly more difficult some variable or set of variables that will lead to this feeling that okay I am progressing。

 I am going further into something more difficult and it's one of the most important things that you need I feel like in a game to be engaging in fun and something for me。

 I definitely need something to aspire to in the game and so this idea of oh I beat level 5 or I got to level two or three or four or whatever can be very valuable so let's take a look at the code of where we're doing this this is ultimately a pretty simple thing so if we're in the play state recall the transition is from the play state to。



![](img/ad5e3f6b767cac035f8979626c48f9fe_116.png)

This victory state。So if we go to play state here。And if we have cleared out all of the bricks。

 so let's go up here。So we have this function called check victory。

 we're defining it as a method on self on the play state。

 so check victory is going to do what it needs to do to determine oh did are we ready to transition which is just going to be are there no bricks left or all the bricks not in play and then we can change to victory passing in our level。

 we need the level because we're in level one， we need to pass it in to say okay the victory state knows we're in level one。

 let's increment that to two and pass that to the play state so that the level maker can now get past that variable and then progressively more difficult levels and then keep passing in the other details as needed so if we scroll down just a bit we'll see the check victory。

Which is a very simple function， which is just for all the bricks in selfdot bricks。

 like if any of them are in play， return false because that means we know for sure we aren't ready to transition to victory if we solve have a brick in play。

 but if we've gone through all of those and none of them were still in play well。

 then we can return true， we have indeed reached our victory state。

And so if we look at our victory state itself。We'll see that it's relatively simple。

But it takes in all of those data pieces of data that we just passed in， we just looked at those。

And then we can still update our paddle， but when we do this is the important part when we press enter to change over to level2。

 we're going to increment selft level plus1 as we pass it from this state into the next state into the serve state。

 Ser state is going to take over this level variable which is incremented here in place and also bricks is right out the gate because we need to see the bricks before we then start playing it's going to be passed in also that self dot level plus1。

 so now the level maker knows okay we're in level2。

Also generate maybe slightly a more sophisticated map and that's essentially all you need right and in addition to of course the rendering here which says okay level x complete where x is self- dot level and so on and so forth。

 but that's essentially all the code that we need and now we have progression we have levels we can keep going and feel like we're actually aiming towards something and getting higher and higher scores and more and more difficult grid layouts so that's the progression update。

The other important piece， the last sort of remaining thing in the whole game is the high scores。

 we saw that at the very beginning， high scores were at the very beginning of the game。

 we didn't really talk too much about them， but we sort of already see that we are pred with all of these different variables。

 this is a screenshot taken from a different time where I had just created a bunch of random scores and it was play testing a bunch of times CCC and CTO just different alternations of my sort of initials。

 but essentially。There are a few important functions that we need to talk about and these are all tied also to the idea of data persistence。

 So if you think of any game that you've ever played on console or whatnot。

 I mean back in a long time ago back in the day you didn't really have persistent data look at like Nintendo or most gamebo games did but if you look like Nintendo for example。

 a lot of games didn't ship with a save file， legend of Zelda was one of the first that did which was a battery that kept a certain amount of memory active so that it preserved your save data but generally nowadays with modern computers。

 we expect these two existing games and essentially what we need to do is think of I need to save a file on my disk that can store something like all of my high scores and with that then I can when I start the game up later I can load this file from disk and then display them as if they were just always there and then this allows us to in the future we can just keep aspiring for higher and higher scores it's a little bit deflating to think。

 okay I'm going work all this put all this time and effort into playing this game and just complete。

Lose my high score and so I think this is a very important thing that we should incorporate into most games。

 this idea of data persistence save files So there's a few important functions we need love file systemst。

et identity is just sort of a way to say okay where at should I assume I have free rein for a folder to put save data in and so by default this is in some folder on your operating system like on Mac it's your user folder。

 library application support and then whatever folder name you put in as your identity on Windows it'll be in your app data。

 local roaming something like that and then on Linux it's in some other directory and this is going to be variable dependent on your operating system you can look there based on this identity key that you've passed in and find the sort of save data that's going to exist there and then there's a few functions that love gives you sort of like basic operating system functions you can check to see if a file exists with love file system exists at path love file system right so you can actually write at a path。

A file， some data， and then love that file system that lines， which just。

It nuerates over the new lines spaced lines of text in a file， which is for our intents and purposes。

 what we're going to need to save of our data， we're just going to think of it in terms of okay。

 for every，Save file or every high score rather in our program。You know， the initials， of course。

 but then the score。 So we can just think of every individual high score as a that initials and then the score。

 sort of like。Blocks of two lines separated and we'll just iterate over that in a loop just you know divide by get all the lines and then just like okay from one to the number of high scores which is 10 grab that line。

 grab the next line， the first line will be the high score initials the next line will be the number and then just go to the next iteration of that loop and then that'll essentially load all of the high scores into memory so when we take a look at how that looks in code just real quick。

 pretty simple ultimately。I'm going to go ahead and open up breakout 10。If you close this out here。

 break out 10。Mainda Lua。So in Ma Dt Lua。We have this function called load high scores。

 and this is going to get called at the beginning of when we run the program。

And so if we come up here。We'll see that when we actually trigger our G state machine to change to the start state。

 we're going to see it initially with all of our high scores and this will be some piece of information that we just can pass back and forth to between all the states so when we get to the victory state or the high score state these will be in memoryory available to us we're going to load them at the beginning of the game we want them here because if we click on high scores we're going to want to be able to see them and when we hit start and then go to the play state and do all of that stuff and then end up getting into a victory or game over state and then losing we're going to want to check okay is the score that I ended with higher than any of the scores in the 10 high score table and if it is okay well。

I know that like I was above person eight， so like I need to replace eight and then。

10 is going to get booted out and then9 is going to get essentially shifted down and then so will 8。

8 will now become 9， so it be we'll take over 8 and then8 and9 will become what we're9 in 10。

 and that's essentially how all sort of score rewriting is going to happen。

 you look for whatever the highest indexes that you exceed the score of shift all of them down by one and then replace whatever was in that spot effectively with your score。

 So if we go back down to load high scores， essentially what we're doing we'll do that in the victory or the game overstate assuming that we actually get a high score but you can see here we're setting our identity to breakout so that means there's a folder that's going to exist called breakout in that file system sort of directory that's operating system dependent。

And then we're going to check， okay， get info on breakout。lst。

 which is just a function that we'll check to see is there a function that exists there？

And then we're going to say， okay， there's a string local of scores。

 and then this is essentially what's going to be all of these scores that we load from memory。

 actually。And then actually sorry in this case， this is going to be we initially seed all of the scores with if no scores exist rather。

 we're looking to see okay， did we actually save a score table before， if we didn't。

 that means that we are loading it for the first time and then so what we're going to do is we're going to generate a list of 10 scores in this case I've preceded it which is my initials here and then just I by 100。

 so we'll start at 10，000， we're iterating backwards for I gets 10。

1 negative one and then we're going to just add new line between not only the initials like I said it'll be initial score。

 initial score， initial score， 20 lines of text in the in the text file。

And then once that's all done， we're going to just write to breakout。 LST。

 we're just using LST as a general sort of extension to represent the fact that this is a high score list。

 this is arbitrary， you could call this whatever you want， you could call it dot TxT。

 you could not call it anything， you could call it dot dot。

 whatever you feel like do LST for dot list of scores。And then。

What we're going to do is we have this in text but we need to actually turn this into code so what we're going to do a table of data that we can actually look at and then shift sort of inmeory and displace depending on how we do with our scores later down the road。

 so we're just going to essentially create a sort of one through 10 indexes and score this table which starts off with name equals Nil score equals Nil then we're going to load that same file that we just either we just created it or existed before。

 and then we're going to just populate that in memory just like this。

 and so eventually that's going to mean that we have just this set of data that we can use to reference in our victory state rather in our game overstate。

And。Compare and shift names and scores based on did we actually beat any of the high scores。

 which is very relevant for being able to actually beat our prior scores so we'll go over to states。

 we'll go take a look at game overstate， which is where this is going to happen。

Or rather this might actually sorry， this might happen in the victory state， not victory state。

 this might happen in the high score state， thought this happened in the shoot， okay let sorry。

 let's redo that got tripped up。I thought this happened indeed。Oh。

 because we don't do it in this example yet， we do this in the next example，Okay。

 let's approximately Julie， do you have a visual on what my editor looked like？

Things are going smoothly for a bit。So with being able to now store all of those in memoryory。

 that's the first step towards being able to have our high scores sort of usable。

 but the other part of it is that typically when we are looking at high scores and being able to add them or change them。

 you do want to way to input your initials and so that takes us to the entry update so we can now write files。

 you at a write files， look at files， store them actual scores in memory。

 but we still need a way to edit the initials for if we want to save our score if we can't actually save our name to anything well we can't actually。



![](img/ad5e3f6b767cac035f8979626c48f9fe_118.png)

Update our high score， so I'm going to open up breakreakout 11 now to show that。



![](img/ad5e3f6b767cac035f8979626c48f9fe_120.png)

So I'm going to close out this。Let's close that， open up breakout 11。

So we looked at the sort of high score loading function and that gets passed to the start state。

Now what we want to do。Let's take a look at the game overstate。 so when we actually get a game over。

 this is where。We can decide， okay， should we go to the there's going to be a new state here because as we saw the sort of this UI for inputting our initials。

 we're going to need a way to do that and show that and that makes itself very ideal for a brand new state so we'll call that like enter high scorere state。

And。The place to do that to make the determination is gonna to be in game over once we hit an actual game over。

 that's like the game's done， whatever our score was， that's the time to decide。

 okay should we actually go to the enter high score state because remember when we talked about the state machine at the very beginning of the lecture if we aren't a valid high score if we haven't eclipsed any of those scores。

 we probably just want to go back to the start state and then just begin playing again。

 let the users press enter， maybe they can look at the high scores again on their own time if they wish。

 so in the game over state when they press enter that's where we're going to mark an actual transition point towards either or either the high score state or the start state。

And so we just do some math to basically work our way down up through our high score table。

 which are always passing back and forth between all of our states。

 It's just a parameter now that we pass between changes and so we can say okay selft high score is at I do score number 10 from 10 to1 so we're going bottom up lower scores to higher scores if our self-dot score which is another piece of data that's being passed between states is greater than that well okay that's what our high score index is for now and then we're going to set high score to true meaning we got a high score we should go to we should transition to the enter high score state so if high score and we'll just keep doing this this will go all the way up to one so that we because we might we'll be higher than maybe multiple scores if we start at the bottom and maybe we got 5000 in the pre-existing version that would put us at about position5 and so we want to go down to here。

 we want to let that process， keep track what the highest score is that we were and then。

What we're going to do is we're going to say if high score， let's go to the enter high score state。

 so let's go ahead and open that up。So enter high score state。Now this is a relatively light。

Somewhat simple state All it does is it takes in those values that it cares about high scores， score。

 score index， and one it needs to know at what point was this score higher than any of the other scores and then also what were the scores of course so that it can shift them and it's going to resave them to disk so it's going to end up actually the UI as we saw is some sort of like letters that we can move up and down and in fact we might be able to quickly demo this and see we can actually lose this deliberately but this has been preceded to be more generous than normal so we should be able to。



![](img/ad5e3f6b767cac035f8979626c48f9fe_122.png)

we should be able to quickly get a high score， so look at our high scores， our high scores at 10。

000 to 2000。So I'm going to go ahead and start。And then we're already at 3000 actually。

 I've gone ahead and preceded it， so I'm just going to deliberately lose a few times if I can。

 at that time it got on the edge and it clipped up， let's see if I can。

Lose a couple times really quickly。So I can show you what this UI looks like visually。

sIt's going to use similar logic to actually what we use the title screen。

 which is this sort of up and down sort of can highlight appearance。

 but see now we got 3175 recall we started about 1000 going up to 10，000， so I press enter here。

We got like a sound effect that plays to show that we're in a victory I can press left to right and that will allow us to sort of move through these letters。

 We've got a sound effect that's playing when that happens if I press up you can see that we are actually rotating through letters and these letters are being represented numerically so we're using ASI for this so 65 represents a capital A so what we're doing is we're going just press up and down to move to increment through these ASI values we've got three numbers that are being stored that are being converted to strings so we'll just say C。

I guess enter actually saves I was thinking move left or right with En。

 but in this case you can see that we are just above position 10。

 which was at 3000 and we've gone ahead and our new initials are there a CAA， so it went back up。

 it iterated through the loop through or rather through the table where all of our scores were。

And then it ended up just putting me right where 9 was。

 which was the number below that which was 3000， which was the CTO there that got bumped down to 10 and so now we're actually in our high score table at 3175 which was the score that we ended with and so if we in fact restart it we should see the same number the same high scores there。

 this is being saved in that dot LST file right at the time that we saved that if we go ahead and。



![](img/ad5e3f6b767cac035f8979626c48f9fe_124.png)

It looks like it is。

![](img/ad5e3f6b767cac035f8979626c48f9fe_126.png)

Stalling for a second there， we'll go ahead and transition to this here。I'm going to go ahead and。

Load up the that will be in the enter high score state。

So when we press enter so also visually I just want to show this here too this is where we're actually changing the color of our sort of our pen for which letter is blue versus white so if highlighted care is one so there's gonna be a highlighted care in this case it's a piece of state highlighted care is just okay first second or third character which one are we editing which one are we changing the initials of this is a very sort of common presentation for our arcade games and games of that nature so we start with obviously just the first character which is the character most on the left and AAa it's this first A that's here and then if we press left or right we'll shift through that so that'll turn highlighted care sort of increment it be one of these conditions in here so right here if keyboard was pressed left or right we'll go ahead and we'll just increment highlighted care minus one and also're making sure to clamp that so if highlighted care is greater than one we only do that if it's not then we're not going to do that we're going to keep it linked or keep it limited to the left and right space。

GoLes than one， we can't go higher than three。And then up and down does a different thing here here it actually will increment numbers that we're storing at this chairs or carss table that we have or cares table at highlight care。

 so 1，2，3， it's going to store a number so that number is going to be between 65 and 90。

 65 being the letter or the number that represents a 90 being the number that represents Z and so we can't go any higher than Z。

 we can't go any lower than a， so that's essentially up and down will'll also be clamping here。

 the values that can be represented by those letters。And so if you render those。

 we'll see that Lua gives us the string。char string。

 care function which will just take in a number and it will give us back the string for the character that is represented by that number just by calling that function so that's a function that Lua gives us as part of its string namespace globally that we can use and so once we press enter。

 it will finally trigger this code which will finally actually take the name by concatenating all three of those cars1 cars2 cars3 it's getting the string cha from those using the dot do string concatenate them to make a name。

 it's going to then ultimately put that into wherever in our scores table was the index that we determined we were higher or equal to it's going to put that in there with our score and then ultimately it's going to save that to our file it's going to just create a string which's what we're doing here we're just going to keep adding to a string from one to10 all of our table entries just。

initial score initial score， a brand new do LST file it's going to save that and then once we've finished that process it's been saved。

 we can then change over to high scores the other state which we looked at previously which is just a very simple iteration of our high scores table as you can see here from one to 10 just go ahead and display all of the in in a formatted table sort of visually using printDe in a way that looks somewhat sort of structured will display all 10 of our high scores and that's all you need to display high scores at that point you are completely ready to go。

The last sort of example that I think is fun。 besides sort of music， which we'll add at the end。

 which is trivial， is this idea of。😊。

![](img/ad5e3f6b767cac035f8979626c48f9fe_128.png)

Paddle select so thiss kind of a fun thing just toate just to get us a little bit more UI we won't spend too much time looking at this。

 just to polish things off we can we have all these bricks。

 we have the balls of different colors but let's just actually maybe allow us to have a different colored paddle too why not we have the textures there we'll support it so I'll just show what it looks like I'll go ahead and run this make sure that this prior one closed which it did so we'll go ahead and just run mainda Lua and Bout 11。

Oh sorry， breakakout 12 is the one that I meant to grab。

 11 is the one that allows us to enter our scores， breakakout 12， I'll go in open。

 I'm going to close all of these to start with。And then Mada Lua。

When I start this we'll now have this sort of UI we've got these buttons here on the left and right it's sort of like okay if we're at index you know sort of almost think of it like the letters we just looked at。

 we can't go higher or lower than a certain index for colors for our paddles there's only a few different colors there's blue。

 green， red and purple so for different indexes four different colors if we're at index4 we can't go further to the right so let's gray out that image if we're on the left we can't go for index1。

 we can't go any further to the left， we can let's just gray that one out too so let's just choose red。

That piece of data is like the skin variable that's now on on our paddle and it will carry over throughout all the rest as we're playing。

 and it's just sort of like a fun thing。 It just sort of allows you to feel。

 I guess more personal about your game。 I mean every game on the planet nowadays has just a million skins and just various fun things to do So there's some personalization in there it can be kind of fun if we just take a quick look at the state what the state looks like relatively not a whole lot of things we haven't seen yet already。

 So we won't spend too much time on it， but it's a new state paddle select state which will now precede the actual start state。

 So if we go over to the main Dlua， we'll see when we do a transition here。



![](img/ad5e3f6b767cac035f8979626c48f9fe_130.png)

Rather。Start， actually， I should say， goes to the。Paedal select state。 So for instance start。

Start is the menu， this needs to happen after the menu， so you'll start state， then pedddle select。

 then serve， so if we're in start state and we press enter。Which will be here。

So if we're highlighted on one， now we go to paddle Select， we no longer go just straight to serve。

 so if we open up paddle Select， we'll see it's pretty simple。

 it's ultimately just we remember we're keeping around the high scores get passed back and forth between all states。

 but paddle gets one， current paddle is one and then depending on what we choose。

 that's a piece of information that will eventually be passed in to when we do a actual transition to the serve state from here on out because that piece of data needs to move between the states。

We'll just go ahead and we will instantiate our paddle right off the gate here and we'll call self。

 currentren paddle passed in as the parameter for paddle。

 which ultimately if we look at paddle again， the first parameter is the skin。

And then we'll just save that as a variable here so that whenever we draw paddle。

 we're just going to index， we're going to offset our drawing index again with a quad instead of drawing blue。

 which is the first index， we'll draw if we choose red it'll be whatever three down is and we're going multiply by four rectangles that way so we skip all of the different versions of blue to go to green to go to red to go to purple so sort of like using skin as a multiplier on indexing into the quads table that we looked at previously。

 which if we were to go down to render would see that happen here so self- dot size plus four which is the sort of like ultimately the rather sorry self do size plus four times the skin minus1 so that's going to end up being like your size is your index into the four sizes per color we started with size2 so we'll always pick the second of the four。

 but then we want to also multiply that by whatever the skin was。a minus1。

 so it'll be0 but then if we're on blue， but then if we're on red or green。

 it will just end up actually shifting the overall index that we're in。

 whether it's two or if we wanted to play with a larger or smaller paddle。

 it will essentially add multiples of4 or subtract multiples of4 from that to give us the correctly colored paddle in our image if we just pull that up for memory's sake here and we look at breakout that PNG。

You'll see that there's four going to be four rectangles， four paddles。

 and so that's what the skin essentially does is it acts as a multiplier， you add you do one。

 two for size， and then depending on which skin you choose。

 itll be it'll be that plus be your skin times4 added on top of that。

 so zero for blue and then one for green。wo for red， three for purple。

 moving four rectangles into that list of rectangles that we generated earlier on。

 And so that's how you can create a state that allows you to choose your rectangle skin and then the very last update just to round things off the music update which is going to be we didn't have the slide things set up here but so the music update is very trivial。

 very simple we're just going to go ahead and for the sake of rounding things off we won't even need to dwelllt too much on the specific details of that but I'm just going to go ahead and run main Lua。



![](img/ad5e3f6b767cac035f8979626c48f9fe_132.png)

![](img/ad5e3f6b767cac035f8979626c48f9fe_133.png)

![](img/ad5e3f6b767cac035f8979626c48f9fe_134.png)

I liked the music track that we found for this， but oh， sorry， I need to click on that。

So just for some atmosphere， we'll play just to go around a little bit。

 just play with a green paddle。I trying to level 32 just for fun as well。

 typically like to just to see what it generates and not a whole lot of deltas just bor like that a little bit。

Oh yeah， there we go clipping up。All the corners， there we go， yeah， there go， give it to me。Yeah。

 that's good。🎼O。And so fast that even I can't even handle it。

 but yeah that we have 4475 points that way， so ultimately we have a very exciting you know。

Final product， final thing that we've created。 It's very colorful is's very musical。

 but ultimately that wraps up breakout and its's sample code。

 And so some of the things that we'll look at next time so this time was a lot of stuff So very few lectures I think will have quite as many details and a lot of things to take in all at once but breakout is probably the biggest hurdle stepwise and difficulty I would say maybe throughout the term there will be other things we look at certainly and Mario and Zelda have their own difficulties。

 all of them have their own things to look at but breakout is probably the biggest like jump up to feeling like we made a full game rather than Pong which is kind of simple and twoplay and then Flpybird is single player but also very simple breakouts got a lot of pieces to it to make it a good implementation So next week we'll look at we already looked a little bit at anonymous functions。

 but they'll come in handy particularly next week。😊。



![](img/ad5e3f6b767cac035f8979626c48f9fe_136.png)

Tweing and timers are very important things you've noticed probably that all the things we've done so far have been very like physically modeled in that we've got a ball and maybe some paddles and things like that。

 it's bouncing off of things， we've got velocity but you know if we want to say okay move this thing over here over a second or over two seconds we don't really have a very easy way to do that right now。

 but there are ways to do it with convenient features to say。

 okay let's take some x value and sort of interpolate it for example。

 over time to go from this position over to this position and now we can say。

 okay over one second worth of time why don't we move this thing over and now we can start to model all kinds of cool visual things that we can't do so far with just physics we'll have to look at discrete sort of problem solving in a context of a puzzle game because spoiler alert next week's lecture is on match3 a candy crush or bejeweled which is something that I think a lot of folks probably have familiar with。

 especially similar to flappy bird。Folks that are playing on mobile。

We'll look at more ways to doing sort of baked into those games as this idea of this randomly choosing shapes to fill in and how to make a procedurally generated so to speak game grid of tiles like be it candy or gems or whatever next week it will be sort of these tiles that almost look like vitamins but they look pretty nice and then we'll also take a look at sort of sprite art at palace and the influence that those have on games and so assignment two is going to be kind of about extending things most assignments are about extending things and sort of ways that I think are intuitive and make sense right now as in a lot of arcenoid or breakout instances。

 right now we don't have anything that changes the player's paddle size。

 even though we saw paddle sizes and whatnot， we don't have things that influence for example we saw by default the ball was sort of going through bricks just on its own or fully without colliding with anything and that might be some sort of like special power or god mode of the life that you could activate through a power up and so we might want to add something like that。

The case of this problem said， it's going to actually be spawning multiple balls。

 sort of like a pinball inspired mechanic where instead of just one， now you have two。

 and if like one you lose， that's okay as long as you have one ball in play。

 you're still technically okay and you can clear the screen sort of like twice as fast that way。

And also we should have a way to grow and shrink the paddle based on if you've gained enough points and there's already an implementation to like recover health built into the problem set if you've gained a certain amount of points and that amount will keep going up but if you gain enough points and maybe you can just like grow your paddle for a bit you' like deserved a sort of boost to your strength for not taking damage for a certain period of time and then lastly and we sort of looked at that in the spriteshe adding a lock block and then like a key will maybe like fall down from the ceiling and if you grab the key you can then like now hit that block with the ball and if you try to hit it otherwise it just won't unlock but that was essentially break out it was I think again probably the biggest jump in the course in terms of overall complexity and difficulty but I think the things that we looked at today in particular spriteheets will help simplify projects tremendously going forward and they'll also segue us nicely one into next week for match3 which has bricks that are also all in a sprite sheet but also for animations which spoiler。

We'll be looking at a lot with Mariio and Zelda and other problem sets。

 so that was breakout this is CS50 we'll see you next week。



![](img/ad5e3f6b767cac035f8979626c48f9fe_138.png)

![](img/ad5e3f6b767cac035f8979626c48f9fe_139.png)