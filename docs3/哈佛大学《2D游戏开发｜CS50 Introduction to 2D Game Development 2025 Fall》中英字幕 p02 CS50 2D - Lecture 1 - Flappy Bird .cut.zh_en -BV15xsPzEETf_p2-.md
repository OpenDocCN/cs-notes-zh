# 哈佛大学《2D游戏开发｜CS50 Introduction to 2D Game Development 2025 Fall》中英字幕 p02 CS50 2D - Lecture 1 - Flappy Bird .cut.zh_en -BV15xsPzEETf_p2-

Oh hello world。 Oh hello。 hello world。 indeed。 My name is David Malon。 I'm here with Colton Ogden。

 And this is the second of our live streams on CS52 D。

 which is a new and improved version of what was C S 50 G。 This version being， of course。

 entirely focused on all things 2 today， we'll be starting and stopping a few times as we film this in real time。

 will be edited and then appear onedx later this year as will the assignments in the meantime。

 I'll be field any questions via the chat or raising my hand on your behalf。

 But Colton Woods in store for us today。 So today， last time we didong。

 which is a bit of an older title 70s Atari and per even the aesthetics as maybe folks can see on the slide。

 we're going a little bit more modern with Fly bird。

 which is kind of popular in the 2010 or so And yeah。

 we'll learn a few things and look at a couple things we learned yesterday。

 excellent Well looking forward and we'll begin in just a moment。

 let me just reduce the number of ducks here。😊，Hello world。 This is Cs52D。 Welcome back。

 This is lecture 1 flapapppy birdd。 So we're doing the zero indexexed approach to the course titles。

 Last time we did pong， which was a bit of an older title from the 70s and this week we're going to be exploring something a little bit newer maybe a lot of folks actually got the chance to play it themselves back around 2013 or so called flappy birdird。

 which kind of had a bit of a controversy around it as well。

 related to I believe the pipe graphics had been stolen something to that effect。

 but a lot of people for a brief period of time， we're really enjoying it。

 I got hooked into it as well。 I was playing it for a little while， wasn't very good at the game。

 I don't remember had friends who were very very enthusiastic about it。 but this week， thankfully。

 flapybiird is a simple enough example that it allows us to sort of evolved from pong because last time when we were looking at pong。

 it was just essentially shapes rectangles and just white and an offbl color。

 but this week we want to actually begin looking at a lot more interesting things。😊。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_1.png)

Things that will take us to not just shapes， but rather things that are 2D artwork that move around on the screen。

 namely with what we also alluded to last lecture， which are sprites and so a sprite and an image or kind of interchangeable sprite is essentially typically in image that will move around onscreen and people when they think sprite they'll think of oh a character graphic or maybe a fireball or something versus what might be a background texture or the like but we'll be looking at images and sprites we'll be looking at scrolling so this is a very common device using games and parallax as well and we'll also take a look at this sort of like idea of using illusions in games to affect all kinds of this sort of verizailitude of sort of feeling like we're in a world that's not actually there also procedural generation aspect of the lecture will be tied to the pipes if people recall flappy birdd is a game where these infinite pipes are scrolling through the level and randomization we looked at last week is a very important piece to making sure games are dynamic and that's also something that。

I've always found very interesting procedural generation in particular and this course we'll explore that in various iterations this week is very simple and as far as we're just essentially dynamically altering a y value of pipes that scroll through the screen。

 but we'll get a lot more sophisticated with that even next week when we look at breakout。

State machines are something we talked about briefly last lecture and it was just essentially a flag this sort of game state string variable rather and this week we're going to properly create a construct that lets us model state machines a lot more abstractly and also avoid a lot of these sort of conditional string checks in our code and then lastly for fun at the very end because this was a mobile game to start with last time we only looked at keyboard input but Flpybird and all mobile games essentially use touch input on devices and that we can model with mouse input through love2D it has a couple convenient functions for that a couple of just fun little articles and blog posts and things that I decided to include here actually this top ones of course and this one is kind of a blog slash course page but when I was initially getting used to LuA-based programming and love2D both of these resources were of a lot of help to me and I really like them a lot and encourage people to check them out and particular how to make an RPG as the name applies is about making RPG some of the things we'll look at towards the end of the course like Pokemon。

That will be more applicable to， and they game programming patterns we've used Robert Nesom a couple of his graphics and links in the slides so far。

 but I can't recommend folks taking a look at that enough。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_3.png)

So our goal today is just going to be as I sort of describe verbally this recreation of Flybird。

 not using the original artwork， but rather some open source artwork and all of that's been linked in the source code。

 but you can see here it is essentially the same game。

 It has just a small bird whose goal is to jump up and navigate this sort of randomly generated obstacle course。

 It's also got a ground in a background。 These are going scroll at different rates to give us this parallax sort of artificial look as if we're in a space and rather than I think purely verbalize it。

 I would like to demo an example of that but you last time I demoed it on my own。

 could we perhaps get any volunteers to take a look and demo it Yeah， why don't you come on up。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_5.png)

啊。What's your name， Hi， I'm David Colton， nice to meet Cha to meet you。 Okay。

 so I'm going to go ahead and hit Command L here to start this。

And so why don't you go ahead and give it a shot， All right， hit enter， enter， we'll start it。 Okay。

 and then how do I play。 And then spacebar is going to be to jump and you want to make sure the bird doesn't hit the pipes。

 All right， here we go。 how hard to get this baby。I think it's pretty hard， all right here we go。

O so we have we have a score of zero there so every every pipe pair we call them in the code that you go through you'll get one extra point and so once you as you can see there's a state transition here once you lose it shows you your score and then you can press enter to play again kind of like we saw at the end of pong Okay。

 can I play it again Yeah， please please try here we go，3，2， one。Oh， go when you hit the ground。

 you also as also loose conditioning keep hitting the spacebar。All right， one more time。

 this game was very hard when it came out， it was the reputation， very hard right now。Okay。

 here we go。 one point coming。 minute It's pretty tricky。 Let's see if I can minimal go。

 I don't even know if I can get oneca I'm so rusty， but let's see。🎼Oh。

 I think there's about it's a tweakable， it's a tweakable height differential。

 We could definitely do that for the sake of speed。 Also。

 the frame rate is a little bit adjusted for production。 So for my eyes。

 I think we need to get rid of that pipe。 Yeah， they will get to get rid of all the pipes， yeah。😊。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_7.png)

![](img/5e4c4e34f2136f2f0d887480ad975eeb_8.png)

Let's see if we try one last time and then maybe for fun， we'll lower the difficulty a little bit。Oh。

 I got so close。 Well that' that's essentially the gist of the game。

 I mean people a lot of people when they were playing this game that essentially had a very similar experience to this on the phone version that was sort of a reputation。

 Yeah， a lot of losing。 well， thank you for having me。 Thank you for volunteering。😊。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_10.png)

![](img/5e4c4e34f2136f2f0d887480ad975eeb_11.png)

So I'm going to go ahead and close that。So that is in the final example in the repo and then maybe towards the end of the lecture if we have time。

 I can adjust， essentially there's a velocity value that gets subtracted from the bird's height for folks like me and our kind volunteer who maybe aren't as experienced playing。

 it can be a little bit difficult to start， but just for the sake of demoing and showing the score improving。

 maybe I'll tweak that just a little touch。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_13.png)

So。Let me go ahead and transition to the slide deck one more time。We're going to do things。

 I think a little bit differently to last time where the code。

 especially as we get progressively through the rest of the lectures in the term。

 there's going to be a lot more to cover and per example。

 And so I think I'm just going to illustrate the code and kind of go through it and allow folks to read some of it on their own at home。

 But we're going to do essentially the same thing we did yesterday。

 We're going to start working our way up from essentially scratch just a blank window up to the final implementation that we just saw。

 And a lot of things people probably noticed a lot of things。

 There were one graphics to begin with as we saw。 We have a bird graphic jumping up and down。

 We have these pipes that are moving through the screen。 We have this background。 We have this floor。

 We have sound effects。 we saw last time。 but what we didn't have last time was the music track。

 So we're also showing just a music track playing constantly。

 which can add a lot of immersion to a game。 very important detail。 I love music myself。

 And we saw state transitions。 a lot of the same pieces interestingly from pong are applied here in flappy bird。

 but they're just used to a different effect。 And so。A lot of those ideas as we explore。

 So I'm going to now open up。Rather， I think we have a couple of slides actually。

 first before we do that， maybe one slide here。 So I'm going to just show a function called this is maybe the most important function of the day。

 which is love dot graphics do new image， which takes a path。

 And so what this allows us to do So yesterday recall， we used love dot graphics do rectangle。

 which all that did was draw a rectangle at a particular xy coordinate。

 So love dot graphics do new image， will allow us to load a。😊。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_15.png)

Image file of any kind we want。 It supports most image types。 PNGs are very common。

 but you might also have Gs or Jpegs。 And then with that， we'll store that in memory。

 And then we can draw that onto the screen with love do graphics do draw。

 which is another function that we'll also take a look at。

 So I'm going to come back over here to our first example。Switch over to my source code here。

You'll notice in the distribution， there's a few existing images that I've placed in there。

 I've looked at sort of free public domain images to include。

 but folks could definitely create their own artwork。

 you just have to use something like a spreadite or Photoshop or Gimp。

 or you could download an image and they just have it in your directory where your main dot Lua is。

 and then you can reference it by its file name by its path。 So if you open up main dot Lua。

We'll see in here。 There's quite a lot of comments。

 but most of the things that we see in here are actually going to be almost identical in a lot of ways。

 at least to what we saw last time at the end of pong or even just in the middle of pong。

 we have defining our width for our actual screen， our virtual resolution， we have our love dot load。

 which sets our filter to nearest so that things are pixelated instead of being blurry。

But we do have here a couple of very important things。

 love graphics new image so these are just literally background dopng and ground dopng the only two images that we have in our folder here。

 It's just going to store them in these global variables called background and ground So with those then and all the rest of these are essentially the same thing we saw yesterday just to window setting setting up our screen a resize handler we have our escape to quit the game if we want to but here between our push start and push finish call we have love graphics draw which takes a background which which takes rather our background variable we're going to draw everything remember everything is drawn by its top left coordinate top left corner rather so if we draw the background at00 it's going to draw down to the right to fill our window and then same thing for the ground instead of drawing that at the very top though what we would rather do is we want that to be at the very bottom of the screen so we're going to say love graphics。

 draw ground at0 so starting at the left side of the screen but we're going。

To draw it at the very bottom virtual height-16。 Our texture being 16 pixels tall。 In fact。

 in VS code I can just show you what these look like really quick if I click background do Png you see it's this long sort of scrolling texture。

 which will be very relevant shortly and then ground do PNng is an even longer， much shorter texture。

 which is our ground and that also will scroll throughout the duration of our code。

 So if I go ahead and run main Lua here I'm going hit command L。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_17.png)

We'll see that we do indeed have something that admittedly sort of funnelnily is much more impressive looking than I would say anything that we did yesterday。

 but it's very trivial what we've done。 It's just a background image and a ground image。

 and we sort of already are almost transported somewhere。 Now nothing is moving。

 There's nothing dynamic happening。 it's a rather simple thing。

 I generally like to go by this style of implementing things in games。

 sort of sketch out the aesthetics and then starting to incorporate the dynamism progressively。

 but we already have sort of the background of our world setup and even the ground setup。

 but there are， of course， many pieces that remain to be implemented。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_19.png)

So let's go ahead and chain transition here So the next update that I think is relevant is the parallax update is what I've titled it and so parallax is this idea where and we can see this in the real world if we see like fences and mountains for example。

 back to back or if you're driving down the highway and you look out the side you can see things move at different speeds and so parallax essentially is in illusion that we can use to simulate distance or depth in our game and one of my favorite YouTube channels for exploring illusions in games just generally speaking is she says and he has a series called Bo break。

 this is a link to his channel this is a YouTube example which you can visit the URL to see it and in A enough time which was a game we looked at yesterday there is a shopkeeper in highre castle that you can go visit and if you actually go behind where he's standing you'll see sort of humorously that the developers because you can't actually physically move behind him in the game。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_21.png)

Not to model him with legs。 So despite the fact that he looks like a real person here greeting you with a rather sort of brusque expression。

 In fact， he is just a torso without any legs。 and this is a common theme and this is typically how you achieve most things in games that feel like you're living somewhere whether you're in an open world game and you're streaming all of those surrounding polygons and textures and things in real time。

 if you were to take a camera outside of your character walking through a world and go far enough away。

 you'll see that the world is typically not rendered and most things if you can avoid it aren't rendered in the background or off the sides of the screen It's called calling as well in 2D and 3D。

 and so this I thing is an excellent example of that highly recommend his channel。

 he explores a lot of interesting sort of illusionbased camera clipping techniques。

 Now in our particular example， we're not doing anything quite that sophisticated。

 but we are sort of using the fact that we want this infinite world but we can't necessarily build an infinitely long。

We do have a long enough texture， and this texture does， if you notice。

 it has a sort of looping look to it。 In fact， here's two images that show the identical part of the screen。

 And This is about 400 somewhat odd pixels in width。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_23.png)

And so。You can sort of imagine this as being， if you were to almost sort of glue it together and form a ring with it and just kind of spin it around。

 it would ultimately look like it was infinitely sort of spinning around。

And we're going to infinitely scrolling rather even as you spin it。

 and so in order to achieve this sort of infinitely scrollable world。

 this world that feels like we could just infinitely keep on flying through。

 assuming we' were good enough at the game to do that。

 then using just a single texture that loops a couple of times。

 well we can just achieve that exact aesthetic。Here's a visual illustration of sort of what this might look like if we envision this is our screen here and the background is currently at x is equal to zero。

 but we decide to set some sort of loop point that we figured out by looking at our texture and deciding。

 okay， this is the pixel at which exact this basically this exact same part is right here。

Then what we can do is we can't really model a ring per se very easily， but what we can do is say。

 okay， once it gets to this loop point， why don't we just set it right back to zero immediately and then if it's scrolling it's going to essentially come back here again。

And then once it does that， it's going to hit zero again。

On and on forever imagine that being sort of animated and you'll see the effect and this is a technique used in infinite scrolling all throughout 2D games and in 3D games for certain effects for texture scrolling。

 and this is how we're going to accomplish this sort of infinite same thing with the ground texture。

 but this is how we're going to accomplish the idea of an infinitely scrolling world so that we can fly through。

So I'm going to go ahead and walk over and let's take a look at bird one。

Which will be our next example。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_25.png)

So if we open that up。Let me go ahead and close these other。Fileles。

So keep we keep our textures imported that we did we're going to use the same textures。

 but we want to first of all scroll them now recall last week when we looked at Pong when we looked at the paddles in the ball。

 they had a sort of delta Y in the case of the paddles but also the ball had a delta x and a delta y and it could move around and we would adjust the x and the y based on this deta x delta y。

 the velocity of the ball and over time if we multiply by DT which was our delta time。

 that ball would just move in whatever that direction is。

 essentially the xy models of vector of direction and the y just models a vector that's just y aligned。

But also notice that we specified as I pointed to in the slides this looping point here at 413。

 Now the looping point is the point that I've looked at the texture to decide。

 okay that is where the texture is identical at 0 and in this case 413。

 so once we hit once we go over 413 pixels assuming we scroll we're going to scroll the texture towards the left because if we scroll the texture to the left we're going to look like we're moving to the right。

So if we just keep doing that progressively and then right， as soon as we hit。

 we've gone 413 pixels to the left。 We'll just set the position back to 0。

 It'll almost look like it did a complete in place movement。 And then we just。

Keep that process going infinitely。 The way that we do that， the way that we can easily do that。

Is through a modular operator。 So you'll notice in love dot update。 we're taking background scroll。

 and then we're going to do essentially the same operation mathematically that we did to everything in Pong that moved last lecture。

 We're going to multiply the scroll speed by Delta time。

 Add it to our whatever our background scroll already is。 And the ground scroll。

 It's the same same idea here。😊，But we're going to modulo by the background looping point and so that's going to once it hits that 413 pixels where it's really the same exact image if you were to copy and paste it over。

 it's going to modular back to0 so this background scroll is going to set back to zero So recall modulo is essentially division it's very similar to division but instead of giving us the actual divided number it'll give us whatever is left over so if we modo by background looping point。

 if we're at 413 and we modo by 413 we'll get back to value of 0 because theres 413 divided by 413 is1 but there's zero remainder that's what modulo operator does in this case because the ground texture is so similar throughout it and much smaller we're doing the same thing but rather than set a looping point。

 we're just going to set it to the virtual width and it looks fine。 It works completely fine。

And here as you can see， we we draw the negative， we draw the actual background by its negative background scroll。

 so it's make a shift to the left and then same thing for the ground scroll so if we run this。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_27.png)

You'll see， indeed， that we have a sort of parallax effect， because recall。

 and I'll take a look at the exact numbers in a second。

 But the background is moving at an actual slower rate than the ground is。

 The ground is because it's closer to us as the viewer in this。Particular shot。

 That's the way we want to frame it。 These mountains are very distant。 The slower the things move。

 the more in the background they're going to be perceived to be。

 So these mountains are perceived as a background element。

 and the ground is perceived front as a closer element to the camera。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_29.png)

And so if we can see that here， if we go up to the scroll， the scroll speed is actually double。

 you can adjust this to whatever you want， essentially the slower the speed。

 the farther away it's going to be， if it's a two pixels， it's going to look like it's really。

 really， really far away， for example， but that's essentially what we're doing we're just doing a double a having on the scroll speed of the ground to achieve the mountains looking as if they're even though they're just literally just textures。

 they're just pixels being drawn on the screen， they look as if they are。

 in fact different depthwise elements。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_31.png)

So that was bird one。Shift here。Okay， might take just a second to get a drink of water。

So we have our background elements now， but I would say probably the most important thing in flappy birdird is that we are missing our actual bird texture now。

 so it's a really trivial thing at this point because we now know how to draw textures onto the screen that we can just draw if we want to just to get started at least let's just draw a bird texture right just an image like anything else I'm going to go ahead and open up bird too。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_33.png)

So let's close out B one。Now you'll notice that we have a bird。

png in this example and again these are just images that I might have even made bird。

png potentially at one point I don't actually it's been a while now but bird。

pNng you could just take a file from the internet you could create your own again it's just a pixel piece of pixel art but it's in here now and there's also a bird。

lua， so if we go over to our。Main at Lua。We're taking this opportunity as well to reintroduce。

 remember classes objectoriented programming so if we know we're going to need a bird。

 if in general we know we're going to need to model some data in some way that we could think of as being real worldor entities or the like I think it's good to start off just already getting the class in place。

 So in this case we've created a class called bird and we're just instantiating it here。

 we're creating a new bird and we'll take a look at that in a moment but we're doing that as a global variable here in a a love dot load function and then if we go down here。

 we're not doing anything really fancy with it yet。

 but you'll notice that now we have bird colon render and so that's just going to draw our bird and our bird is going to we open it up。

Actually handle its own graphics so in this case we're doing self dot image recalls these are just a way to refer to whatever the instantiated entity is and these are just setting fields to it so self dot image it will hold its own image and that's going to point to love。

 graphics new image we could just create new images and all these things anywhere we want to they're available to us anywhere as long as we're running through love。

So we just load up bird。png you'll notice that there is a couple of functions here that are pretty useful。

 so instead of actually hard coding the width and height and having an idea in advance of what that is。

 we're creating it dynamically by actually getting the dimensions of the texture。

 which is something like I think 20 by 12 ish and the benefit of this is that in theory we could just load in whatever texture we want to it could be some larger or some smaller bird。

 whatever we feel like but here if we just do self dot image colon this is a method on an image object。

 one of these new image， whatever this new image function returns it's going to have a method called get width and get height which will be integer values that now will'll set to self dot width self dot height and then we're just going position it right in the middle of the screen。

We're using virtual width and virtual height divided by two。

 we're subtracting half of our width and the heights that is right in the middle of the screen。

 and then we're using love。 graphics。 drawaw on self。image， self。x， self。y。

 quite a bit more readable， I think than having a ton of magic numbers all over the place。

 which in general we want to avoid it will come up periodically， but in general。

 if you can sort of put things into variables or constants or the like。

 things tend to be a little bit more readable。And so that's what this bird colon render function is doing。

 it's just deferring essentially to this render function here。 So if we run main Dtlua in bird 2。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_35.png)

We'll see that it doesn't look very convincing as in terms of the gameplay。

 but it is functioning properly。 We do have our bird。

 It's being rendered perfectly in the middle of the screen。

 and the background is continuing to scroll。 So we do sort of feel like almost where I guess we're flying through through the sky in some strange form。

 but yeah。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_37.png)

Yeah， syntactically， what's the difference between the colon syntax and the dot notation？ Sure。

 So syntactically between the dot and the colon notation。

 a colon means that we're going to pass an implicit self to this function called render。

 So tables can be defined， This is sort of the prototypal method of doing object oriented programming。

 which Lua does in ja also does this。 but essentially the bird class has these functions defined within it called render。

 and then each object， each bird object or each whatever object， whatever class。

 if you wanted to call that render function， and then have it automatically know that it's the bird that we want that render to apply to。

 this colon essentially performs the equivalent of doing this。

 if we were to do bird dot render of self。And so that's with the colon。

 without the colon or with the colon， we no longer need to do that。

 and we can treat every function as just。Essentially。

 not even needing that argument defined in its definition。 As you can see。

 render here just assumes to not take any arguments。 And so it doesn't need to know about self。

 That's something that Lua takes care of for us。 Yeah， we can edit this part out。

 Can you get into the habit of closing the file Explorr because your torso blocks a lot of the code。

 Oh， sure， sure， okay。Take it from。We'll do a Ryan if it's cool， we'll do a clean。

Transition into three。So despite the fact that we now have our bird rendering。

 we do need to I think add a few elements to make sure that the game is believable and also that there's some dynamism at play。

 so what we're going to do I'm going to go ahead and close out these examples here。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_39.png)

And then the next piece that we need to look at is the gravity update。

So gravity in this case is really the element that makes Flybiird a game。

 It is a constant essentially we can think of gravity as this value that's pushing down on things to make them fall down。

 increase their y velocity to make it more positive over time。 It's about 9。

8 meters per second squared is the acceleration rate of gravity and we're going model something kind of like that numerically it doesn't really work quite that way because of the way the pipes are of weird size and who knows how big the bird is in size。

 but essentially we can sort of model things if we think of things in those terms。

 so I'm going to go ahead and open up bird3。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_41.png)

And then if we go to our bird， ultimately， that's going to be the so I didn't need to open the bird PNG。

Our goal is to get our bird instead of just being static on the screen。

 we want it to actually fall down because that's the overall thing we're working towards is remember。

 we want to be able to bounce our bird up and down。

And the thing that's essentially pushing against us is gravity that's where the main thing we're fighting against and so we're going to every time we hit spacebar。

 we're going to move up， but to start with we to move we want to get the bird at least moving down towards the ground。

 so the first thing that we're going to do。Is we have to know how fast we want to move down so gravity is about 9。

8 meters a second squared and we're just going arbitrarily kind of go based off of that。

 So we're going to say we're going to have a constant here of 980 now you'll notice that I defined this variable using this local word which will start to see more of progressively throughout the rest of the term but everything so far that we've seen has just been defined without local just like this and what that means is that anything throughout the entire application can see that variable but there are certain situations where you might not want every variable visible across your entire application if you're using for example。

 somewhat simple names for variables it's higher likelihood that you accidentally reuse or overwrite or the like a particular variable between files so it's generally better practice to avoid globals as much as you can outside of particular circumstances that will take a closer look at throughout the remainder of these examples and throughout the rest of the course but for right now we're just going to keep gravity local here using the local word。

 which means that just whatever is in the scope。It's defined in has access to it。

 this scope in any inner scopes， but nothing in other files or anything of a higher scope。

And if we come down here。You notice that we've set a Dy to start with。

 So our bird is never going to have an X velocity。 It's the only way that we're moving。

 you know quote unquote through this game world is actually an illusion。

 all of it is just the background scrolling and there will be things that move the pipes that we saw will'll move throughout the game space。

 but all of that is simply in illusion。 We're not actually moving through anything。

 The only direction which we're actually going to have a velocity that matters is our y axis。

 And so we're setting it to zero to start with。 So no movement on the X or the Y。

But you'll notice that we defined an update function in here。

 and what we're going to do is defer to this update function from our maint Lua。

 we're going to call bird update and pass N DT。 But what we do is we just take our Delta Y。

And we're going to add gravity times Dt。 So over a second's worth of time。

 will our DY will go from 0 to 980。Which if 100 pixels was a meter， that would be about 9。

8 meters of distance that we move or we accelerate through every second。

And then not only do we have to do that DY operation。

 we also have to add the DY to our our actual Y value。

 our coordinate inside of the bird object because that's what we use to render the bird and so if that never actually gets updated。

 the bird's DY might change but when actually update visually。

 so we're going to do that we're going to then take that DY and we're going to add it to our Y also multiplying by DT。

And then we're going to draw just the same as we did previously and assuming that main dotlua has the in our update function。

 we'll just go ahead and go straight to there， noticeice that we added B update and we passed in DT so that it would have access to that。

 we can then run this。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_43.png)

And we'll know it's kind of hard to see it's very easy to miss。

 but let me run it one more time if you pay real close attention。

You'll see that it just falls right down through the ground。

 which is the exact intended effect for our game， so we have an initial z or initial zero value of our y velocity that's going to add every160th of a second。

 it's going to not only get faster in terms of how much it moves。

 but it's also going to just keep adding that every second until we just fall straight down through the Earth。

 there's no collision or anything， nothing is testing for these things once it goes out of bounds。

 we don't see it， it is actually technically still increasing and moving。

 but it is for all intent purposes out of sight sort of out of mind。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_45.png)

Okay， they get another water break， if that's okay。

So it is a little bit underwhelming currently that our bird。

 all it does is just essentially fall through the floor， which is not exactly what we want。

 but this gives us the perfect segue into actually being able to correct for that with input。

 meaning that we can press spacebar or tap on the phone of the like to actually make the bird sort of jump up and start to fight against gravity and then we'll have the beginning of our sort of interactive gameplay loop so to speak so I'm going go ahead。

 transition to the slides here。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_47.png)

![](img/5e4c4e34f2136f2f0d887480ad975eeb_48.png)

In order to do that， we want to do or move on to what I call the antigravity update。

 so just kind of cutely naming it， but essentially what this means is the way that flappy birdd works is that this is a sort of complicated graph seemingly for to describe overall I believe this was usually used for a neural net sort of training dynamic thousands of flappy birds moving around the screen and calculating optimal play paths for them。

 but you can see essentially all the elements that we are going to be looking at throughout the game throughout the rest of the game examples are shown here visually we have the size and we have the gravity vector here which is modeled essentially with the 980 pixels that's per second that's applying to our Y our actual y velocity positively。

 but there's another important aspect which is there's a jump velocity and this jump velocity is what we're going to look at with the antigravity update so what we can do essentially even if we have this gravity pulling us down constantly。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_50.png)

If we essentially just sort of say， okay， well we're getting higher and higher in terms of our DY per second。

 but we can just hard set it negative， the opposite of a positive y velocity is going to be going negative which means we'll just go up towards the top of the screen and the effect this is going to have is that we can make essentially rather than just do a continuous updating of our velocity。

 minus by some delta time amount per frame， we can just hard say， hey。

 let's just set it to like a high negative value and it will immediately start going up really fast but because we're always applying gravity per second per frame rather。

 it's going to immediately start to correct for that and that's what's going to give us this appearance of sort of jumping。

 we go up really fast， but really within a very short span of time。

 gravity is already doing its thing again and we're now we're moving back down the screen and tweaking those values。

 tweaking gravity， tweaking the jump velocity so to speak or really what's going to be behind balancing this particular。

Ge specifically in addition to for example， the pipe speed as they move through and also the gap between the pipes。

 those would all be like the balancing variables that you would use if you wanted to tweak how hard or easy your game is right now it might be a little bit too hard we could certainly tweak a couple of these variables and see if that makes it easier to play towards the end of the lecture but you can see as a preview we also have our pipe separation our pipe gap these things are also what we're going to be taking a look at in some examples to follow。

So we're going to go ahead and transition now to。Bird4。So if you go ahead and close these out。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_52.png)

Now if we move over to here， so we have our bird module。

And this is all really going to stay the same。 What we want is in our bird do Lua。

The key is we will take a look back at main Dlu in just a second because there is a very important thing here we need to talk about but the main thing here that's doing the work of this antigravity update。

 so to speak， is again， we press space bar we want that space bar to give us this jump up and to do that rather than have a continuous sort of like decreasing of our velocity which is make us go up really slowly we're going to hard set our velocity really high in the negative direction and then allow gravity to correct for that and so that's where we're doing right here。

 we just set it to a burst at negative 300 which is about within about a third of a second that's going to be brought to0 from gravity because it's going at 980 pixels per second and then it's going to immediately start applying that 9。

8 meters per second squared down in the y positive direction once that has been reset back to zero and so again you can tweak these values a little bit depending on what you want but we're just hard setting the d to negative 300 and then allowing gravity to do its work。

Now you'll notice that I have a function here called love。key。

was presseded and what that function is iss actually not a function that's inside of love。

 this is a function that we have chosen to define ourselves because Lua is dynamic。

 you can essentially add functions to whatever you want to。And the unfortunate thing is that in love。

 most of those callbacks that we all saw should and can only be defined in one place。

 namely your mainlua if you want， for example， when we looked at continuous input for the paddles it was love keyboard is down and recall and we can pass a key in like a or W or up or down and that will just give us a booley in hey are we are we pressing that key actively。

 yes no， but what if we want to just have like an instant click well or an instant key press well the only way that we've known to do that so far has been through our actual love do key pressed callback function in mainlua。

 but we can't just define that in here and check for that what we want to do is we want to say you know you could have ways where you could define something like that。

 but then we're gonna to have to say okay， we're gonna manipulate the birds dy bird do dY equals negative 300 and we're sort of getting our hands dirty with the objects themselves。

 but if we want to encapsulate this behavior and let the bird。

manage its own input handling and let anything manage its own anything。

 We need sort of ways to cleverly get around main Dt Lewis predefined callbacks。

 So if we go to main Dt Lua again，We'll notice that we have a little table here that we've defined called love keyboard。

 keys pressed we're just defining it to an empty table to start with in our this is in our load function so're at the very beginning at love。

t load we're just going to create this and again we're just extending this。

 We are just adding this to the love keyboard namespace。

 the lovet keyboard module we can just add whatever we want to it。

 Love keyboard is a thing but love keys pressed is not a thing so we're just going to say love keyboard。

 keys pressed equals an empty table。And then inside of our callback function。

 notice that we've added， we've added this in here。 This was in here previously。

 but we've gone ahead and we've added love dot keyboard do keys pressed key gets true。

 which is this table that we have just to find up in our love dot load。

 So what that allows us to do is basically keep track per frame。 Okay， I pressed this key。

And then now we can just globally have access， okay which keys got pressed this particular frame。

 if we just look at whatever key is in there， we'll know， okay oh I pressed a this frame， lovekey。

 key is pressed at a is true and everything else will be false assuming that we initialize it to nothing or itll be nil rather。

 and then we can just set it all to be nil later， we can set it to a fresh table。If we go down here。

 we see the definition for that function I alluded to Lovet keyboard dot was pressed key。

 This is our own function。 We're just extending love do keyboard and we're just doing a check on that table。

 If lovet keyboard key is pressed at key， meaning if there's a value in there at all any true the value then return true or return falses and so what that lets us do is we can just call this now anywhere we want to。

 love keyboard lovekey pressed will continue to fire。

 it will populate this table and then anything throughout the entirety of our code can just reference use this function to see oh was it pressed once。

 not lovet keyboard dot is down， are we pressing it continuously but did we just press it once。

The important thing that lets this work per frame and actually apply to individual frame separately is that at the end of update。

 we need to reinitialize keys pressed that table to be an empty table so that everything is essentially emptied out so that there is no memory of whatever we pressed this frame on the next frame everything's a blank slate and then per frame we just populate with whatever we trigger in our key pressed handler so if we look back at the birdlua file well see here love keyboard was pressed。

 that's our own function， lovekey pressed if we press spacebar， itll handle that for us。

 it will put it in that table， it will mark it as yep we pressed it and then we can immediately just check in our update function。

 anything that checks within update which is what this bird bird colon update is being called right here it will check that table with that function and then return true and then we can just process individual keystrokes as if we were essentially doing it in our main dolua。

 but now we can。in any class and any file that we want to。  normally， this would not be possible。

 but we have extended effectively our ability to do that。

 So I'm going to go ahead and run this example。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_54.png)

And we'll see I have to remember to actually start pressing spacebar。But now。

 anytime I press spacebar， you'll notice I am indeed。Going up about at a velocity of negative 300。

 gravity is pushing that down。But if I don't press anything。

 it'll start to accelerate down more and more， but I can just immediately shoot up negative 300 pixels。

 DY gravity will subtract that。And then within about a third of a second。

 it's already sort of zeroed out。 and that's how we have the sort of convincing input loop of flappybid。

 so to speak。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_56.png)

Okay， I was gonna take a， I think a break。 do you have a actual question。 Yeah， it's okay。

 we can weave it in better。 Sorry I was， I was sort of expecting the light。😊，Oh， sorry。

 I that was spontaneous。 let me ask it。 and then I'll ask it for real。

 Love dot keyboard is that is an actual global object。 It seems Yeah。

 keys pressed is that your own field within。 So you just allowed to add arbitrary fields to an object。

right， can I ask this question then for real？Let me get a sip of water and then we'll cut in。呀。

Is love dot keyboard do keys pressed a table that comes with the love API or is that something you added。

 No， this is something that we are choosing to add ourselves。 So everything in Lua is dynamic。

 Tables are all dynamic。 You can just add everything at the end of the day is going to be a table of some kind。

 and so you can just add whatever key you want and put in whatever value you want。 In this case。

 love dot keyboard comes predefined， but it does not have a keys pressed table。

 It also does not have a love dot keyboard was pressed function。

 We are also adding our own function to it as well。Okay， so that is the antigravity updates。

 so now we have essentially a model of how to fight gravity and how to get our input to work properly。

 but now you know it begs the question， how do we actually start to get the obstacles in our code that allows us to have something to dodge with our bird because it's not really right now there's not really much of a game there。

 you can move around， you can jump around but the pipe is kind of the ultimately it's even shown on the slide it's kind of like the missing piece。

 so the next update， the next piece of code is gonna to be called the infinite pipe update rather。

 so why don't we go ahead and open up that example so I'm just going to go ahead and close out these examples。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_58.png)

![](img/5e4c4e34f2136f2f0d887480ad975eeb_59.png)

Open up bird 5， unless we added a couple of things here inside of this example。

 So we have a pipe dot PN G。Again， just an image， it's quite tall image。

 but this allows us to render it even potentially really high up on the screen and it'll still fully show you could in theory。

 loop segments of the inner part and that would function just fine too。

 but we just found a tall graphic that we're going to use。And we also have a pipe dot Lua。

 So in our main dot Lua， let me go ahead and。Kind of come down here， or requiring pipe。

We have a table that we've added， so local pipes gets empty table。

 so this is essentially just going to function as an array for folks familiar and tables can function just like arrays in languages like C or++ or Java。

 the table is Lu's sort of catch all data structure for anything that requires multiple things。

And so we're going to store a bunch of pipes in this table and we're going to scroll them and we're going to move them throughout the screen and so what we're going to do then last time you know up to this point we haven't really had a collection of multiple of the same things。

 we've had two paddles， we've had a ball and then we've have our bird but we haven't had like if we need infinite pipes。

 we need a way to have you know some data structure that can store， I'm not going to define pipe1。

 pipe2 pipe3， pipe4， I'm going to put them in a table or an array of sorts。

So we're going to go down here and just take a look at our update。 You'll notice that we added。

A timer， so this is just a very simple timer。And actually， we might have defined that up here。

At zero。 So what this is going to do is going to add essentially we want what we want to do is we want to spawn a pipe every so often。

 like maybe every second or two in order to account for the fact that we've spawned or that we need to spawn a pipe Well we know from love do update that Dt field that it passes in is just a time it's a fractional time in seconds。

 it'll be some like 0。016 or depending on what frame you're running。

 it might be higher or lower than that。 And so if we just keep adding that fractional value to some variable in this case。

 we started at 0。 but once this gets to one。We'll know that a whole second' worth of time is passed or two we'll know that two seconds worth of time is passed so through using a timer and adding Dt just over time to it and doing a conditional check we'll know okay a seconds passed two seconds passed I want to pipe to spawn every 2。

5 seconds or every 5 seconds。 This is how you do that。

 you just keep adding DT to some value and then do a check on it。 So if we go back down a little bit。

We'll see every update we're going to just by default。

 we' going to start by just adding Dt no matter what。

 and then we're going to do a check here so in this case， if spawn timer is greater than two。

 meaning at least two seconds have passed or more than two seconds have passedll notice we're using this function called table do insert this is a function that's in Lua this isn't a love thing this is how in Luua you add to a table you say okay table do insert is table isn't a variable in this case。

 it's actually a keyword table do insert into pipes。

 pipes is the name of our table that we defined way up at the top recall and then we're going to just instantiate an empty pipe here。

 which is what this constructor is doing here recall this is the class constructor syntax from our last week or last lectures example and even up above with the way that bird is defined so we're going to create a new pipe。

 no parameters， we'll take a look at the pipe class in just a moment and then we also reset spawn timer back to zero so that。

Now we'll begin re testing or we'll begin to reacru that two seconds worth of time before the next pipe gets spawned。

 Now， another important detail。Is that， okay， well， we can populate that。

Table all we want to but of course those pipes are going to have to move and moving as we know requires updating。

 it requires some operation on DT deelta time， and we can do that inside this iteration here so this is using a four loop in Lua this is how you do four loops。

So there are a few different ways to do for loops。 this is doing an iterative it's using an iterator So what it's doing is it's saying for k colon pipe and these are variables that we're choosing so you can say for something comma something。

 meaning for every key value pair in this table so everything in a table is a key value pair by default if you use a table as you can see here we're just doing an insert so we're just saying okay sequentially into the table。

 it's just add an element， add an element add an element it's going to treat it much like an array in C or c plus plus or Java where at index1 as we'll find out not zero they'll list one of the  one of the quirks of Lu is that it is not zero index which folks who have taken another course might have know that arrays are typically zero index in Lua tables are one index so we'll start at index1。

 there will be a pipe that an index2， there will be a pipe then an index3。

 there will be a pipe if we just do this over and over and over again。

So when we call this iterator here for K pipe， this just means for one pipe。

 for two pipe for three pipe， it's key value pairs。

 so the key is the index and in the value is going to be what's actually stored in that table at that index So at index1 it's going to be a new pipe at index 2 it's going to be a new pipe at index 3 it's going to be a new pipe。

 but Lua。In addition to storing numerical indices allows us to store strings and have those BR keys。

 And so we can say， you know for example， as we'll see coming up pretty soon。

 if we want to have a bunch of sounds， which we even saw last lecture and we want add the particular sound for like a crash you can say at index crash。

 store this audio source。 well that's going to be not a numerical index anymore now that's going to be a string index So if we were to do that same thing it would be4 k pipe would be or 4K sound rather it would be4 crash would be the key and then pipe would be the sound or sound would be the sound。

 So this is just a way of iterating over a table to get the keys and the values we don't really care about the keys necessarily well actually we du because we want to remove them and that's how you remove elements from tables。

 but in particular often you'll want to just use pipe we'll just want to often use the values if you want to perform some operation off of those values in your table So this is how we iterate over an entire。

T and get back each individual pipe and then from there we can then now call pipe colon update on DT and you'll notice that the other key piece to this iteration is that there's this pairs function and that's a function that's in Lua so pairs is essentially just what gives us this ability to iterate with key value pairs literally the name is pairs in the function to give us that ability so for every K pipe in the pairs of pipes。

 we're going to update pipe with DT。And then we're going to do the check here if the pipe do X so this is where we're going to be able to actually remove。

 we could just do this and let this run forever， we could just keep adding pipes every two seconds and just like store it and it's fine and let it run but if we did that every two seconds we're adding a pipe to this data structure and memory and it's just going to keep getting bigger and bigger and bigger and it's also going to mean that this iteration is going to take longer and longer and be more processing。

 so if the pipe gets past the edge of the screen if it's less than the。Pippe dot width。

 we're going to actually remove the。I think this needs to be if pipe dot X is less than sorry this might be a typo。

 if pipe dot x is less than 0 then we're going to table dot remove， this is another function。

 so table dot remove is a function that will actually again just like up here where we had table dot insert。

 this is another Luo function to remove from a table we say table dot remove at pipes will remove K。

And so what that's going to do is again， K pipe。 so remove requires that you give it the key that it wants to remove。

 So it's going to take a look at the collection that you give it， the table that you give it。

 it's going to say， okay what key do you want me to remove from the table。 So the table is pipes。

 the key is K， which why we call it K And then so if pipe do x is less than zero or less than or equal actually no。

 it needs to be less than okay I realize now why it it was set to that because it has to be because it's drawing on based on itss x axis it's x coordinate rather once that gets to0。

 it's still going to be visible on the left edge of the screen so we want it to actually be equal to the negative size of the pipe。

 thatll be the moment that it just goes past the edge if it's like if the pipe's 30 pixels wide and it goes to the past the left edge of the screen。

 30 pixels， it'll just be at the point where we no longer see it And so that is why we want to be less than pipe width。

And so if it's at that point just off screen， we're going to remove it from pipes。

 we're going to remove that key from pipes， and then that way。

 no matter how many pipes we add to this collection over time。

We're not going to be just getting this bigger and bigger structure。

 we're adding pipes and we'll maybe get like five or six on the screen or so， they'll be moving。

 but then eventually once they get just off screen， the first one。

 the earliest one in the collection will disappear and so then we'll have four and then maybe the fifth one't get added but then the next one will have moved over here and now it just gets removed。

And so we'll see the actual operation of moving if we go into pipe here。Ohm sorry。

 thats thought that was the Lua file。 We'll go into pipe。lua。

 which this is going to be quite a simple。Definition here。

 you can see we have a constant defining the image， the actual image here， we have its scroll speed。

 we're just defining negative 60。Pixels per second， approximately， but you can see that。

We want to set start with the X actually， all the way off screen。

 We're going start we're going start with the pipe being off screen。 Remember。

 they're going scroll in from the right hand side。 And so we're going start it just off screen by setting it to virtual width。

 and then in update， we're just going to do a very simple。

 we've seen this a bunch of times already Time the pipe scroll by deelta time。 And then over time。

 this is going to essentially set the it's going to keep it scrolling until just eventually again。

 once it hits negative， it's width off screen。 It's going to just be you know the cleanup function is going to call in main。

 it's going to disappear。 But also for fun， part of the procedural generation aspect of things in the sort of variability of。

😊，The way the game plays and also looks， we want to randomize the Y axis recall that we did this last lecture where we set maththtrandomsed with OS dot time and in the love dot load so that gives math dot random this always fresh way of randomizing and we're just going to decide to draw its y value between the middle and the bottom of the screen ish approximately a little bit above the bottom of the screen。

 virtual height minus 10 but you can see here we say arrange between virtual height divided by two middle of the screen and then virtual height minus 10 so every pipe will randomly be tall a certain amount and then but they'll always be moving and eventually getting off screen and they'll always start at the right edge of the screen。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_61.png)

So that was a long explanation。 Let me go ahead and just run this example so we can see it。

 I can even， I think press spacebar。 and barely you'll see that there are a little。

 these couple are a little bit low but they all are random。

 So we have some that are just spawning even slightly off screen there。

 You got one that's actually almost made it halfway。But you can see on the right edge of the screen。

 we have they're actually starting。 they're spawning and then every frame that scroll speed。

 which is negative 60。 So about 60 pixels per second， they're just moving right to left。

 Once the oldest one hits the there might be a missing maybe there's a gap there actually。

 either that or they're just slightly rendering off screen。 but the actual。

The actual pipe will be taken out of the table， table do remove at that index。

 And so we just have this infinitely drawn landscape now of pipes。

 So we sort of are achieving the aesthetic of what we're going for。 Now there's things missing。

 obviously the one thing is that we're just you know I can just bounce these can I can just float through these pipes and it's fine we're not actually doing any collision detection a slightly subtle thing that people might be noticing is that the pipes are actually slightly shifting to the last pipe or the first pipe is shifting slightly to the right on every time that the pipe to its left goes off screen。

 and that's because when you remove something in the middle of an iteration。

 the table is going to essentially skip the next index so we're gonna to fix that。

And we'll take a closer look at that in a second so that's a bug and also there isn't a pipe above this pipe on each of these pipes and so we need to model a pipe pair is what we're going to call it and then so we need to model collision first off。

 we need to fix the way that we're moving table or we're removing pipes from our table and then we need to also add this second pipe on top of all of these and then once we have those pieces in place really that's essentially the core of the game。

Yeah， when you call table dot remove to remove a pipe once it's off screen。

 does Lua then also garbage collect the memory so to speak so that you're not just accumulating more and more objects somewhere in memory Yes。

 so anytime that you set a key to nil or you remove key from a table。

 Lua's garbage collector will eventually clean up that memory。

 it is a garbage collected runtime so it's not something that you have direct control over。

 but just like JavaScript or Python and any of these other scripted languages。

 it'll do garbage collection behind the scenes when things are no longer referenceable or keys and tables are removed。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_63.png)

Okay， that was a long one I'm going to take a drink。I'm going to rent to the。

So that was infinite pipes in a nutshell and we do have some more work to do to get us to the sort of full flappy bird sort of aesthetic and so that brings us to bird six。

 which is the pipe pair update this might be one of the more interesting and important aspects of this particular repo because that's what ultimately determines the game itself overall the game would be pretty easy to play if all you had to do is jump over pipes probably and so what the designer of the game did was you have pipes that are sort of above and below each other sort of oppositely oriented but with a space between them that's kind of just small enough to get through with practice and so we can look at this is again another sort of example of an illusion where you know in real life you know you might see pipes that are built into the ground in this sort of way and it makes sense but certainly not just floating from the ceiling from the sky and not connected to anything but because they're rendered off screen and they're tall enough we don't ever really see anything to suggest。

They're not part of the world in some way， and so we give people the illusion of these pipe pairs that exist in the world that we're navigating through now every pipe pair sort of has its own new you can think of it as its own new objects So these pipes so far every object that we've dealt with as an X and a Y value we're going think of these pipe pairs as having their own XY at the top and then they're also going to have a gap size in the middle here。

 sort of the size between the pipes they'll also have a gap between them。

 their spawn interval so that the more pipes that you have and the faster sort of the slope of your pipes as they get generated。

 the harder your game might be if you don't have very many pipes that generate and the slope between them is relatively gentle it might not be as hard maybe you have relatively sharper differences between the gaps and they're more frequent and so that's another example of ways that you can balance your game which we saw back a few slides ago。

And then we can look at this area of sort of named them the dead zone in the spawn zone。

 which is kind of ultimately what I talked about in the last slide a little bit as I was looking over the code。

 but this area just means essentially where things get delocated where the table will actually get cleared of pipes as they move past the edge of the screen and then the spawn zone is just where they start and they move in from right to left and this is just a graphic to sort of illustrate that idea so we're going to explore that now with some code。

You can move over to here。I'm going to close out the examples that were up here in B5。

 we'll open up bird 6。And you'll notice that we now have a pipe pair。lua class here。

 so I'm going to open up main dot Lua。We'll come down here just a little bit。So instead of pipes。

 now we have pipe pairs， so the idea of a pipe pair ultimately folks can model a lot of these things however they want to。

 but in my mind because they move together I sort of envision these pipe pairs literally as an entity。

 even though it's comprised of two entities， but that's the benefit of objectoriented programming or just like more I guess modeled programming。

 you can have things that are relatively complicated and intricate。

 have multiple pieces nested within them and hide the details of how they work so that you can just think in terms of these highlel concepts so instead of pipes going have pipe pairs and this will actually hold within it two separate pipes that we can use to do collision detection and move around angle and oriented things of that nature。

We're going to keep a last why or the gap placement so that one of the bigger issues that you could have。

 if you were to go purely random with the way that you organize the generation for these pipes。

 is that they'll just be all over the place， they'll be very staggered and crooked and it'll be pretty much impossible to play the game no matter how good you are so if we keep our record of our last y。

 then we can just simply adjust whatever that value is by just adding or subtracting some small amount to from it。

 and then what that'll do is it'll ensure that we sort of like move in a gradation it'll look like it's smooth and intended。

 which is the way that the original game was implemented。

And so if we go down to a few functions down to our update。

We'll see that rather than spawning a pipe and adding it to our table， we now spawn a pipe pair。

 It takes a y value so that y is going ultimately be determined by this last y and that's where this essentially gets calculated based on the last y plus some random value which will allow it to move sort of gradually throughout our game space and not end up being if it's too random it'll just be impossible to play we want to ensure that we keep it sort of graded and then otherwise it's largely the same。

 we're doing another iteration here for every K pair in pairs of pipe pairs。

 which the syntax we saw last time we're just going to update the pair itself now。

 not the pipes which the pair as we'll see differers to updating the pipes and then we have our remove step actually separate previously if you recall we had the remove step inside the update stage but there's a problem with that because if we actually remove anything from a table while we're iterating over it that can cause issues because we will essentially on the next it。

Of our loop before going sequentially， if we remove index2。

 let's say we're iterating through our table and we remove index2。

 the way that Lua actually deals with removals is that all of those indices get shifted back by one so if you have let's say you have three pipes you delete pipe2 then as soon as you delete pipe2。

 pipe2 becomes what was pipe3 and pipe3 is now nil nil is Lua's way to say nothing and so you effectively would skip over that pipe。

 whatever pipe would have been there if you had five pipes and you delete pipe2 it would essentially become four pipes in width but pipe3 would take two's place。

 pipe 4 would take three's place，5 would take fours place and you would skip over iterating over pipe3 effectively by deleting two and by having three get shifted into two's place so typically anytime you want to do a removal from a table。

 you either want to do it in this way where we are。Updating and then removing afterwards。

And we do that with this flag here， pair dot remove， that's what we trigger that and pair update。

 so we basically say okay， this pair should get removed， then we have a cleanup loop。

 or you could also iterate from the end of your table to the front and then delete things and then because things get shifted end from the later end of the table to the front。

 delets won't actually impact further iterations because your iteration will have gone to you'll be decrementing instead of incrementing。

But we're choosing to do this other approach here， which is going to just kind of also explicitly show us that we are separating the removal from the update and there are certain situations where you might want to keep things alive for a little bit for other things to update and affect things and maybe not do a removal right away in place。

 you might want to flag something so that other things can do something to it before it gets removed right away。

And so also in our pipe pairs or in our draw function， we're iterating over all of our pairs。

 and then we're just pair rendering instead of pipe rendering for every pipe。

 So let's go ahead and open up pipe pair Lua。We'll see here that we're taking an approach and I previously alluded to tables the difference between having tables that are incremental and that they get automatic numbered indices like1。

2，3，4 and again they all start at one in Lua instead of zero in case that ever causes confusion but you can also have tables that are defined with strings and we did this last week or last lecture with sounds and we're going to do that again with sounds in in this lecture example。

 but also we can just do it with anything we want to in this particular case。

 if we think about a pipe pair， we know that we want a pipe on the bottom。

 the exact sort of situation that we already just looked at where every pipe is a sort of bottom pipe in our world。

 but we also want a pipe that's above that pipe and that's creating a gap between the two and so to do that we're just going to say okay a pipe pair has its own self-top pipes table this is just another table which has two keys upper and lower and so pipe we've changed a little bit now so previously remember we just had。

Empty set of parentheses for pipe。 It didn't do anything。

 It didn't have anything that it was just all essentially randomly decided where it lived。

 what what its position was。 but now it takes a string as its first key， top or bottom。

 This will be important when it gets rendered in a second， as we'll see。The top pipes， if you recall。

 visually， the top pipe and the bottom pipe aren't being the exact texture that are being aren't the exact same texture that is being rendered。

 If you switch to the slide here and you can see it。 The pipe on the bottom is properly being。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_65.png)

Just print just drawn to the screen in the way that the actual art is displayed。

 but the top pipe is actually getting flipped upside down and so that's where it gives it that sort of nice symmetry but in order for that to actually get rendered properly or to be accounted for we need some piece of data that's capable of representing that and so we're going to pass in this string for our upper pipe is going to have this string pass to pipe called top and then the bottoms the lower one you could also maybe put these as top and bottom if you want to for consistency but in this case we're just deciding to say the upper pipe and the lower pipe has a toporiented pipe and a bottom oriented pipe and then you'll notice that they also take in a y parameter and that's the only really important thing that needs to be explicitly placed because recall x is decided for us they're just going to move rather right to left and that's going to be taken care of for us。

 We don't need to manage X at all。 we don't need to set it it just always starts at the right edge of the screen moves all the way to the zero or it's actually zero minus。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_67.png)

Pippe width， and then it gets garbage collected effectively。

But we do want to set the y value for these because remember we are setting the y， we're deciding。

 okay， I want the y to always be such that the gap never is too far apart from the last gap we're going to keep track of whatever the last y was that we set for that and we're just going to shift the position by 20 pixels or so。

And so that's why we're passing these values into here。 And here is the remove flag that we set。

 We set the X already automatically to a little bit past the edge of the screen， Virt width plus 32。

 we can also set this to virtual width， and that would probably work as well。

 but I'd like to just put it slightly past the edge of the screen。

 You can also tweak this to your liking。And that would effectively influence maybe the gap between your pipes。

 which we'll take a look at later。But then you have the update function here and so now notice that we are deferring the updating of those pipes to this function。

 this function will actually rather it will actually take care of passing a call to both those pipes to render them so that we don't have to think of them from the main dotlua main dotlua just calls update and render here and this manages it sort of wraps over the data of both pipes and so we just call self dot pipes at index lower do x equals self do x well first off we do just the classiclta delta time multiplication onto pipe speed and then we subtract that from self。

 X so were always moving right to left by sort of that pipe speed by delta time and then we're just going to take this pipe pair has its own Xy value and we're going to pass the x value in particular to the pipes so that they move so that when they draw they'll always be moving but they're being managed and they're being sort of held。

In this container of information。And so if our x is still greater than negative pipe width。

 which would be past the right edge of the screen， then we'll do that。

 but if it's gotten past that point， just like with the other pipes。

 we're going to set our remove flag to true and recall that's we did that's what we checked in main to actually do the removal right here。

 if pair dot remove， then just remove pipe pairs from our sort of global set of data in main。

And so let's take a look then real quickly at pipepe， which has a couple of changes。

So most of these are all the same。Except we do have this orientation field now and that was the first string field that we passed into the pipe constructor when we were looking at it in here this top and bottom so this orientation is going to essentially flag this pipe and say。

 okay am I a normally rendered pipe， am I just going to draw the texture as is or do I need to flip the texture for this pipe and so if it's a top pipe it needs to flip but if it's bottom it just needs to render as is and so we take that in notice here it's the first argument to the constructor again。

 the constructor is the in knit function with the class library that we're using？

And then it takes in a Y。 And so self do Y gets y。 it just gets set here。

 Self do X is equal to virtual width。 That's fine。And then if we're not doing any actual updating in pipe anymore。

 but we are rendering pipe still，'re we're essentially using a render function in here that pipe pair can just easily call and defer to oops so the more you can sort of do things like that and sort of reduce your syntax。

 look how you look how clean and elegant sort of this looks at a high level if you're looking at pipe pair and just want to figure out how pipe pair works you can sort of bury the messier details deeper into your data so that you can think more high level but we're essentially just drawing the image for the pipe。

 we're drawing it at X always， but the interesting thing here is that we're going to do a check on our orientation to determine the way that we flip whether we should flip our pipe and the way that we do that interestingly in love 2D and a lot of graphics context is we're going to apply a negative scale factor and so this might look like a lot of details here。

 I'll go ahead and just。Individually new line these maybe for illustration。But essentially。

 what this is。Is。Ted to put this here， so these are all on their own line。

We have our and all of this is nicely documented to on the love 2D wiki where they go into detail in all these parameters。

 but you have the image， the X， so this is the Y， so if it's a top。

 then we're going to essentially remember we're in our pipe pairs。

 we're rendering both of the we're rendering both pipes。So what we want to do is。

The interesting thing about scale factors is that they will flip something based on the Xy coordinate of whatever is being flipped or scaled。

 so by default， everything that has a normal scale factor of one is going to just render down into the right so if you're rendering the bottom texture for example。

 it's going to render just fine， it's going to render based on its top it top left coordinate。

 which is going to it might be visible for that perspective or left camera is flipping my thinking but you're going to render from the top left and then you're going to render down to the bottom right。

 but if we want to set a negative scale factor， the weird thing about that is that essentially we're going if we by default just assume the same orientation of top left。

 then a negative scale factor on the y axis means that this upper pipe is going to look as if it is drawing upwards。

ing to flip， it's going to mirror its y axis starting at its top。

 and that's going to not be what we want。 That's going to essentially greatly magnify the pipe gap distance。

 So what we want to do is when even though we're going to do this flip operation。

 So imagine this is our pipe normally if we were to negative scale factor。

 it's going to flip it vertically and we don't want that we want it to essentially do a flip。

 but we want it to stay in place And so to do that we're doing this sort of essentially adding our height to the y value when we draw it and so the result of that is that and this is just when we're drawing it。

 we're not actually changing its data Y value or anything。 so collision will still work just fine。

 but we're essentially offsetting such that we draw the Y。

Down a pipe's height worth so even though we're flipping even though we flip the pipe vertically。

 we end up actually shifting it down by that exact same amount and it has the intended effect of just in place vertically flipping whereas previously we would have essentially looked as if we mirrored the pipe directly on top of the existing where the existing pipe would have drawn and created a tremendous gap and so that's what this is ultimately doing。

 we're using that ternary syntax that we talked about last time if we're in top orientation then we're going to draw at our self。

 y plus pipe height or just our regular y value and then this is a rotation value here which we're just going to set the zero we don't want to rotate。

A one for our x scale factor。 we're not。 we don't want any flipping。

 We don't want any scaling on the x axis。 So just a one scale factor。

 which will do nothing on the x axis。 But again， another turnernary here， if our orientation is top。

 then we want to set a negative one scale factor， which will flip it vertically or just one which will keep it drawing top to bottom。

 So I'm going to undo some of these little changes here。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_69.png)

And then save that。And then if we render if we run that really quickly。

We will see that we do indeed have pipes that are drawing correctly。

 so even though we are flipping those top pipes， there's a gap of whatever this is that the bird is going through right now。

 looks like maybe 60 or 50 pixels or so， maybe a little bit more。

The pipe is being drawn above that and if we were flipping if we were to flip the axis without shifting its height。

 it will just completely be invisible I mean we can see that if we were to go here and instead of adding if we were into the pipe。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_71.png)

If it's a top orientation， let's just do self dot Y here as normal。We'll see we will。

 we will not see the top pipe because it's going to be rendered really high up and flipped vertically。

 So let's go ahead and just do this。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_73.png)

Once the pipes are coming through。You'll see we see we see no pipes， even though they're there。

 the pipes are there， but the way that the rendering is flipping them vertically。

 even though the rectangles， sort of the collision boxes you can still envision are there。

 the actual graphic is flipped at the top where it's X Y is at0， which is really high up。

 And so we want to offset that。 That's why we go ahead and we。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_75.png)

If I go back into pipe。Add that height back。To essentially like sort of spoof as if we aren't doing a rotation based off of the X Y。

 We're just doing it based off of the we're essentially emulating a center rotation about its midpoint。

 And so that's what we get here。 Run it real more time。 We'll see the pipes properly。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_77.png)

Rendering so anytime you do a rotation if you want to not a rotation， but a scale。

 a negative scale in one direction， you're going to want to offset things visually if you want it to render in place。

 a rotation in place， rather a flip in place。Or you can optionally set the origin point to the center。

 but that adds a lot more complication with actually setting up and rendering things and just also calculating collision in other ways。

 so we elect instead of doing a center origin point for everything。

 we just instead set the we keep everything based on the XY coordinate。

 but we just offset the visual it also helps that we're only doing a Y flip。

 we're not doing an X flip， which would be more complicated。

 but since we're just really flipping in place or just flipping the thing vertically。

 we can just shift it down and it functions completely normal as we want it to。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_79.png)

Okay。I would just be mindful of。So with that we've tackled what might be the most tricky part of the code。

 certainly a lot of things in there， a lot of tables which are sort of a new way of looking at things and their functions that are built into those and the pipe pair itself is a little bit of an odd data structure on its surface and it has sort of multiple objects that it's managing now but thankfully the rest of the topics we look at should be a little bit less intense and the next thing that we're going to look at is actually sort of a callback to last lecture which is this is the collision update and so remember last week or last lecture I had alluded to the fact that AABB is quite。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_81.png)

A prevalent theme throughout the rest of this course and in 2D games it's a very common algorithm for doing collision detection and thankfully everything that we're dealing with today is all rectangular。

 even the bird sort of even though it doesn't look quite rectangular。

 we can think of it rectangularly， so I'm going to go ahead and transition over to B7 here。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_83.png)

And just close a few of these。And so。Most of what we need to look at for collision detection in this example is we just have a collides function it takes in a pipe as an argument。

 so what we want to do is we want essentially as the bird is moving throughout this landscape of pipes that we're creating these pairs。

 we just want to check for every pipe pair is it colliding with either the top or the bottom pipe or call each pipe pair it has two pipes。

 two rectangles that we need to check for and so we can do that by essentially even though this looks a little bit more convoluted maybe than last time this is the same algorithm we're just checking to see if there are no gaps at all throughout all four sides of the bird versus the pipes。

 same code as last time， the only difference is that we are checking on a slightly smaller rectangle than the bird's actual box by offsetting based on which edge we're checking or we're just going to either check whether it's the self dot x plus two or the self- dot width minus4 instead of self dot X and self- dot width and the result。

Of this is that effectively we have a two pixelel smaller box around the entire bird that we're checking instead of the bird's actual full collision box and this is a common thing that you'll see game designers doing just to try to overall make their games not feel as unfair because if your game is gives you just a slight amount of leeway in particular and shoot them up games for like old arcade games like scrolling shooters like 1942。

 you want to have just a little bit of wiggle room to navigate projectiles and like if things are actually hard set to your collision box。

 then it can sort of feel like oh wow that shouldn't even though by the literally by the standards of the algorithm it's purely fair。

 the way that sprites are modeled sometimes a slightly transparent pixels and just weird shapes and circular shapes and whatnot。

 it can feel better sometimes to just clamp or to shrink or reduce your box just a little bit against the things that you're colliding against and projectiles and things of that nature。

So that's the main function that does the work， it's essentially the same function that we looked at last week。

 which was split in too， this one is just all in one condition。

We're going to go ahead and look at the in Maine D Lua in our update。We'll notice that。

We're going to do the update step for every pair just like we were doing before。

 except now we're also going to do a nested check for every pair for every pipe rather in that actual pipe pair even though you probably don't need to necessarily do an iteration over the pipes because there's only ever going to be two pipes per pipe pair but this also is a nice opportunity to illustrate nested iteration。

 so you have 4K pair in this outer loop， so we're iterating over every pair but within every pair we're also doing an iteration over both pipes。

 and so what we can do then。Is say for every L pipe and this is just convention KL in V and M just whatever letter makes sense。

 so we could call this maybe P or some other key if we wanted to but for every pipe in the pairs of pair dot pipes we'll just use that function that we just defined and then we're going to pass in the pipe to the bird the collides function in our bird class and then if that's the case。

 just to illustrate that we actually got a collision for right now we're just going to set scrolling to false so if I go ahead and run this。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_85.png)

So previously， we were just kind of clipping through all the pipes。

 but as soon as I hit one of these。You'll notice right there you can even slightly see that it's just like one pixel in on the bird too because remember we set the or I guess it would be two pixels is。

 we set the box to be just a little bit inside the bird。

 so this is kind of a slightly more fair way to do collision detection。

 but indeed we now do have collision detection it can collide with the top pipe we'll do an experiment let's collide with the bottom pipe as well so let's just go ahead run this again。

And then let the random pipes come through and hit this bottom pipe。

And you'll see that both pipes in this case are collable。

 so now the game sort of is at its core functional in the ways that are important。

 at least to get us closer to being able to have a score and a game overstate。

 so I'm going to go ahead and transition back here。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_87.png)

Which brings me to the topic of， whoops， dot mean to do that？



![](img/5e4c4e34f2136f2f0d887480ad975eeb_89.png)

![](img/5e4c4e34f2136f2f0d887480ad975eeb_90.png)

State machines。So we had the opportunity last time to talk about state machines a little bit。

And state machines and we even have this exact slide up。

 but what we want to do is have a more refined way of looking at the transitions in our game。

 so if remember last time we have currently we don't have many states。

 we just have the game goes right into you the bird is falling and we can bounce around and stuff like that if we want to actually have let's say a title menu or an intro or in Pong we had a serve state。

 we we had a game overstate， we have all these different states。

All of these are when you just have a flag or a string variable that you're using to check。

 then your main dotlua gets really big and complex， hard to read。

 it's just hard to gr to say okay what state am I am I in I in the serve state am I in the highcore state。

 if I'm in that state， what do I need to do and I need to x to x2 y， whatever。

 it gets to be a little bit cumbersome， I would say very cumbersome especially at scale。

 but there are better ways to model these sorts of things。

 and so what we were doing is not really much different than a state machine。

 but we actually are going to introduce a much more effective state machine， but just as a reminder。

This is what a state machine looks like conceptually。

 you have states which are modeled by these rectangles here， which have terms， so you have ducking。

 diving， jumping， standing。 So this is sort of modeling a platform or a state machine。

 and then you have the transitions between them。 So in this case this is if you go from ducking to standing by releasing down。

 you can see that relationship modeled there。 So we release down we go from ducking to standing。

 if we're in standing and we press B will jump and then so on and so forth throughout the rest of this diagram which we talked about last time and this is sort of how you can diagram out the overall flow for your entire game。

 and is modeling an entity， a character but you can model anything that changes state and that has state that and that state is important in determining how it should make transitions。

This is what our state machine is going to look like for our game state today。

 and for a while this will be the primary type of state machine we use to overall guide the states of the game。

We start we ought to start in the title screen of some kind。 That's typically what games do。

 if you fire up a game from back in the day。 even now。

 you'll see the logo and like press start to play， something like that。

 So here we can model the relationship here， I've done it through this sort of way of looking at it or this way of presenting it but if you press enter when we're in the titled screen state。

 we go to the countdown state So countdown states I think just to kind of a fair way to allow us to be prepared to start pressing space bar when flappy birdird is running so if we press rather if three seconds pass once countdown state has begun。

 then we should transition to the play state， and then when we're in the play state now we're actually playing with flappy with the bird and we're bouncing and we're doing collision detection we're accumulating points but if we collide with a pipe that should transition us to a different state in this case it transitions us to the score state and the score state is just hey。

 you scored X points know maybe you could do something like show the user they got a bronze silver gold medal for how well they did it or something like that。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_92.png)

And then when we're in the score state is often the case that at the end of getting to game over or score what have you。

 you'll want to allow the user to get back into the game right away so by pressing enter。

 we can denote another transition from score state right back to countdown state again and now we have this sort of infinitely doable loop。

 we never really ever go back to the title screen or you certainly could depending on what your game use cases or what what you prefer and the case of this example。

 we're just going to go back to countdown and then because we already sort don't need to remind people that we're in flappybid countdown state and then people can just essentially get caught in this infinite sort of triangular loop there。

 So don't we go ahead and take a look now at a way to model state machines we'll look through this relatively quickly because there's gonna to be a bit of code here。

 but none of it should be too complex the important thing that folks should look at or be familiar with is that in main dotlua to start with。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_94.png)

![](img/5e4c4e34f2136f2f0d887480ad975eeb_95.png)

Remember last time that we did states， we did it in the form of a string。

 it was just a variable that we were storing game state equals start， game state equals play。

 and that can work for very simple examples， but now that we've introduced object oriented programming it can be more effective to think in terms of objects can we represent and encapsulate the behavior of what it means to be in a play state or a score state or all these different states because now the benefit of that is they're their own files they can have their own objects。

 their own things that they manage， we don't need the bird for example。

 when we're in the title menu because we're not moving a bird around but we do want it in the play state。

 but we don't want it in the score state maybe so now each of the states can maintain their own state。

 their own entities and so forth， keep things a little bit more a little bit more better encapsulated。

 so let's go ahead and scroll down here just a little bit。The important thing。

 the most important thing that we take a look at is this G state machine and this is an introduction also to a trend that we'll be using throughout the rest of the or a convention we'll be using throughout the rest of the course to denote sort of global variables。

 especially global container variables in this case G state machine So this just means that this is a global state machine。

 we're going to need this accessible anywhere in our code because every。

 especially if we're gonna to have individual files that now manage whether we're in the score state。

 whether it's the play state， whatever if they're their own files。

 they need a way to transition to the other states they need the sort of state machine available to them you'll notice that we're creating a state machine here。

 recall this table syntax is just a way to shorthand call a constructor or call any function that just takes a table as an argument state machine is being required which is right here require state machine You'll notice also we're requiring a few different states as well and this dot syntax is how LuA does directory sort of。

We have a directory called states within which is a function or is a LuA file called base state。

 and you do not need the dot Lua that's automatically inferred by LuA， so states。

 basease state just means in the states folder， get the base state file dot Lua require that and then same thing for these other two states and then also state machine which is provided in the distro。

So if you come back down here we have G state machine and so each state has a key so that state machine title is going to maintain a reference to。

 and this is also the interesting bit。 there's an anonymous function we're using anonymous functions so the benefit of using anonymous functions here is that typically when we have states we want them to be fresh every time at least for relatively simple games in particular depending on the game you might want your states to have to preserve certain aspects of themselves when you're transitioning back and forth and we'll look at examples of maybe some of that in Pokemon later towards the end of the course when we look at something more complicated called the state stack for right now we're just going to look at a very simple state machine and we just want a new copy of each of these states every time we perform a change between one state and another state if I'm in the title screen state and I want to transition to the play state I want a fresh play state and so what we're going to do is we're going to say okay I'm going to define a function。

Here anonymously， this is a thing that certain languages like Lua and JavaScript and Python。

 Python has Lambdas， but JavaScript in Lua will let you do a function actually in line like this and assign it to something this is called a first class function or anonymous function in this case。

And so it's actually going to store this function at this key。

 It's a value just like any other piece of data and what this function does is it just returns a brand new state。

 that brand new in this case title screen state or play state you can put whatever you want in here and you can actually you could have these functions be whatever you want there's a particular reason why we're doing why we're returning states in this particular way and we'll see they have a sort of contract they have to fulfill to work properly but the benefit of this is that every time we do a change and we call this title with the function that'll exist here。

 we're going to get a fresh title screen state， we're going to get a fresh play state。

 there's going to be no lingering state anywhere we're just going to have just like a completely blank slate to work with and this is a benefit with the kinds of games that we want to deal with typically Yeah since you're not passing in any arguments。

 could you instead just assign to the title key the title screen state function name itself and same for play and plain state play state。

Could we just assign the name by itself， that would be a name to the actual title for the function or rather that would be the name of so if we were to pass just the name title screen state to this。

 I anticipate this will crash， but we can try it。But the actual title screen state is itself just a class。

Table， which has a bunch of inner methods that in one of them being like in it in particular is what gets deferred to when it tries to instantiate or call that function and so if we do this。

 let's just run this real quick and see what it says。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_97.png)

![](img/5e4c4e34f2136f2f0d887480ad975eeb_98.png)

And then we。R title screen。It looks like in this case it might be working。

 it might be deferring to in it by default， if I'm assuming that I'm looking at this correctly。

 because we start in title， it triggers it。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_100.png)

Yeah， that might actually be。 that might actually be okay and acceptable。

 I'm not seeing a bug so far。 My understanding， and it looks like it is refreshing properly。

 My understanding was that the。If you do， if you just were of call class by itself， then I suppose。

I assumed you would need to pass in the brackets based on the documentation that I had read。

 but it looks like it's accepting it without it， so yeah， that's a good point。

 it looks like for right now we could assume that that works properly if we let me just do it here as well just to see。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_102.png)

![](img/5e4c4e34f2136f2f0d887480ad975eeb_103.png)

That does simplify things quite a bit。Yeah， I think barring any possibilities in the future where we might need。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_105.png)

The functions defined for a particular reason or other this is also acceptable。

 This makes it maybe a little bit more clear what's happening if youre looking at G statement if you're looking at the state machine definition。

 you might not be aware that ultimately they get called instantiated from the state in this case if you were to do this。

This at least is a reminder to us that we are returning or weing a function。

 we're invoking a function that's going to return a new copy of that state。

 but I suppose if you were used to seeing it， I would probably be totally fine with using this as well。

 I think I would personally like this better once I got used to it。

 but there is I think some element of lost information maybe as you're getting into it that's a little bit strange。

But， so that's another way we could certainly look at it。The state machine itself， let me interject。

 I would revert it because I think we can edit out my question。Oh， you want to end out I think so。

 so I would just revert to your way。Okay。Just so the code now is consistent if we do edit it out。

And unhighlight it because it wasn't highlighted before。Okay。解药。

I made an assumption that they needed the。I mean， I kind of like this way better because it is I I assume this is essentially a constructor。

 and it's a little weird to pass the constructor nay。 It just feels like a bit of apples and oranges。

 whereas the anonymous function kind of。Makes it a little more， I don't know， clean in my mind。Also。

 in theory， if you wanted to parameterize the constructors here。

 when you do changes that's possible versus， I guess it would be。Yeah， it would be。

 oh it's a deferral， it would work the sa well， it expects a particular。When you do， when you do a。

So we have a state machine here with these keys that mapped to these functions that return these new instances of these state classes which we haven't looked at。

 these objects that represent these states。 we've gone from a state being a variable that' a string variable to being an actual object that we can look at as an object a little bit more abstractly。

 but we need to take a little bit more of a look at what these states need to do to implement what it means to be a state already you can see right here right below the state machine。

 we have this method being called on the state machine called change to title so all change does is and we'll take a look at state machine in a second to see in the code what it does。

 but it takes whatever the current state is in state machine and actually might be better to actually have that open while we talk about this。

 but change will take the actual state name that we have currently。And perform a couple of functions。

 it'll perform a sort of cleanup and transitional function called exit。

 and so part of implementing a state means that all of your functions need to have these methods defined as a contract。

So it'll call exit on your state， so title screen， state， exit， whatever that might mean。

That can be cleanup， that could be any sort of thing。

And then it will now change whatever the current state is to whatever the state name value that we pass in is。

 it maintains this its own state， it's this sort of like self dot states。

 which is this table of as many states as we want， we saw that in main dotlua， that's what this is。

 self dot states， it's this table。Then notice that it looks it up by the key。

 and then it will actually call it with these parentheses here。

 so it assumes that a function is going to exist there。 And so that's ultimately what happens。

 And that's why these are also anonymous functions here。 So these get called and then returned。2。

 whoops。Self dot current。 So self do current will then have a reference to this object。

 which is actually a state， in instance of a state that can then be updated and rendered。

 which we'll see here， update Dt， state machine update， Dt will just。Update， it's current。

 self do current， which will be whatever that object is that's returned by one of those anonymous functions。

 same thing with render here， and so now instead of having to do all this stuff and update and render and have all these objects necessarily do all of that。

We can just render the state machine' current and it will just defer all of that to the state object itself。

 and our main will actually become quite a bit more concise， which we'll take a look at in a second。

And then here is just essentially a list of empty starting state starting functions that we can initialize the state machine to if we haven't given it anything it'll have this。

 so if we call it it at least won't crash or anything like that。

 but this will ultimately get ignored， but it's also a useful reminder of what the functions are I suppose that given that any given state should implement in order to be valid within the state machine any state that we create should have a render and update process AI which we'll look at in the future。

 we're not going to use that just yet enter and exit and these enter and exit functions are important which we'll also see in a second for how we can pass data between states if there are these isolated objects。

 the question does become you know if we're taking all of that out of main and now in individual classes。

 individual objects are maintaining their state。How do they talk to each other because if you're in the score state for example or if you're in play state I get a score of five and we're just returning a brand new score state。

 how does it know my score was five if they're separate and that's done through enter and exit if you'll see we'll take a look at that in a second but you'll see when we call self。

 current enter。Enter takes in parameters and those parameters we can pass in。

 we can implement a function called enter on our state。

 which will actually sort of this will be our sort of handshake of sorts between our states to allow us to pass data back and forth between the two。

So if you go over here。And we just open up。 So real quick in Maine。

 we'll notice that we've trimmed things down a little bit in our update。 So in update。

 we still scroll things because this is going to happen no matter what state we're in。

 we want to keep scrolling， but everything else in Maine。

lua in update has been moved to G state machine update and everything has been moved to G state machine render in。

in the draw function， except for the backgrounds because we're keeping those backgrounds。

 anything that you want to apply to all states outside of all states and still happen。

 you can do outside of your G state machine， but now if we call G state machine update。

 it's just going to update whatever it's currently held state is。

G State machine render is going to render whatever its currently held state is。

 and so now let's go ahead and look at。The states， remember we have this folder here。

 we have a base state with just a couple of a few just really empty placeholder functions noticeice that we have in it。

 enter， exit， update and render， we don't have process AI because we're not using that。

 but this is a base state， It's just a class with a bunch of empty functions。And then in play state。

If you scroll up to the very top this is something that the class function or the class library gives us。

 we can say underscore underscore includes equals base state and what that means is that it will already come preload with these functions。

 We don't have to actually implement them ourselves This is a form of inheritance which is another object oriented programming concept where we can have some sort of subclass inherent init from a parent class so the parent class being base state here。

 base state is just like oh this is essentially what a base class ought to look like or what a class or a state that doesn't have any behavior should look like just a bunch of empty functions and then we want to inherit all of those we do that through through this underscore underscore underscore includes it gets base state。

And so in here we have all of the things related to play。

 all of these things that we looked at before is everything that we put in Ma Da Lua has just now been taken out。

 everything that was updated when we should move and set the timer and spawn pipes and all of that stuff we just scroll through it really quickly。

 update the bird。Important thing to note， like we no longer have to keep our bird in main D Lua。

 It's now here in the play state。 the play state's the only place where we need the bird。

 the play state's the only place also where we need the pipe pairs and the timer so the more you can take out of main Lua in a lot of ways the better because now that gives you sort of easier way to see what's happening at a high level。

 look at your states， look at some of your tople loaded data。

 look at your overall flow and then now I don't have to think in terms of my entire game at once when I'm navigating everything。

 especially with pong we have all these conditionals and we're doing stream checking to say see okay are are we in serving are we in the game state。

 the play state， what are we doing right now， now all we have to do is just look at okay all I'm worried about right now is do I have things working properly in the play state and you do we have an init function。

 we have an update function。We have a render function。

 we don't have an exit and an enter function implemented yet。

 which we'll look at later that will be when we get to the score state implementation。

 but if we look at title screen for example， this was something that we didn't have previously。

 but now we have we can just easily create a new title screen again inheriting from base state so it has at least an empty shell of all the methods that it needs so that the state machine will call the method and it won't be missing。

But you can see it has an update and it's just if love。keyboard。

 was pressed the function that we built previously， enter or return。

 then notice again G state machine change into play and then same down here we're just doing more rendering and we're setting fonts to various fonts that we've pres in love。

t load at different sizes。If you go to I'm not sure if we took a look at that previously in Maine Lua。

 but you can see we just created a bunch of fonts here， these are just pre- bakeked in， small medium。

 flappy， huge and then we just set whatever font we want。

 that's what the title screen state is doing。And so in the play state。

 once you transition to the play state， you can see that if we collide at all。

 we then change back to the title state， not typically maybe how you would always want things to be。

 it's a little abrupt， it' a little harsh， but for the sake of the illustration it's going to serve us well。

 so I'm going to go ahead and start maintlua。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_107.png)

If we run this， you'll notice that now we're using a couple of fonts。

 these are just free fonts I found online that look kind of in line with what we want。

 you'll see what it says50 birdd， which is themed after you CS50 and then press enter so a press enter only the state machine right now is loaded just the title screen state and it's calling update and render on that in maint Lua nothing is happening at all with the play state。

 all that code is kind of just almost hidden away effectively we press enter。

 and then we go right into the play state and now a call to the play state has returned that that's being held in that's being held in the state machine and then as soon as we hit a pipe well now right back to the title screen state again we use G state machine change to change to a brand new version。

 brand new instance of the title screen state and if we press enter we'll notice that it's a fresh copy of that state because there's no pipes the pipes are gone because we created。

 remember that anonymous function returns a brand new version of the play state。

And so if we do it again， we'll notice brand new version of the Play state。

So this is desired behavior in many cases where we don't want whatever was left behind in memory whatever could have been left there。

 the last time we were in that state， we just want to essentially get a fresh play field。

 so to speak。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_109.png)

So that is the state machine probably one of the bigger changes to the code base。Okay。How was that。

So that adds probably one of the more useful and more commonly recurring pieces we'll see throughout the rest of the terms I say that a lot because a lot of these pieces are very useful。

 but with this with just the state machine we can start to add a lot of really cool things very quickly and so why don't we go ahead and start transitioning through a couple of more states so for example。

We have the title screen and we have the play state but what if we want scoring to occur well what does scoring even mean in flapy Birds a score is accrued through actually clearing pipes。

 which I've been having a difficult time doing for illustration I might have to tweak balance the numbers a little bit in order to actually properly illustrate it。

 but effectively if the bird， if the bird's X coordinate is to go past the。

Sort of the right edge of any pipe pair which has be that pipe pairs x plus its width while we can increment our score at that point。

 we've effectively cleared that pipe pair as an obstacle and then we just increment by one and so our goal is to effectively keep doing that as many times as possible and then whatever that value is should be presented to us ideally at the end of the game at the end of the run whenever we do finally have a collision so let's go ahead and open up B9 and look at that really quickly The beauty of this is that it's relatively easy now。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_111.png)

Let's say， collapse some of these here。It's relatively easy for us if I open up main Dot Lua。

you'll see that we're importing score state that's going to be our new state and again now we're just modeling states that we just very quickly just add a new state into our repo。

Into our a new object rather into our folder and then we can just load it into our state machine and just like that now we don't have to add a ton of if statements and change strings and spaghetti YR code we just add literally a new key score here to our table and then we set it to return a score state instance and so we'll change the title as usual once we're in it'll be the same thing press enter。

To start the play state and then once we're in the play state。

 now the important thing is we're going to be to start keeping track of our score。

 so let's take a look at play first。So we're in place state。

So we'll see right away if when we're actually updating the bird in our play state。

And we're looking at every collision。Well， since we're already iterating over every pipe pair to do a collision test and every pipe they'rein。

When we're doing that， what we can do is say， okay， if there's a collision。

 let's just transition to the score state， so that'll be the point at which we collide that's our sort of game over。

 we'll transition to that so G state machine change to score。

 you notice we're passing in an object in this particular instance and in the one below here。

This is the same thing except effectively we're just checking if we hit the ground at all。

 but this object here， if we open up the state machine library itself。

You'll notice that change takes in these enter parameterss so this is a very important thing this is about again how to talk have one state talk to another state so the score state or rather the play state needs to talk to the score state because remember these are kind of like separated domain separated areas of play that don't know each other's variables。

 each other's state but the score state needs to know the score that we got during our play state and so to do that we need to allow any state but in particular in this instance the play state to send a message to the score state saying hey。

 this was the score we had at the very end so we can just take a table here called enter parameterss that if we look here at self dot current colon and enter enter parameterss so once we perform the exit function on whatever our current state is so if we're thinking about we're in play and we're transitioning over to score we're going call play exit。

 we're going to set current to now the self dot current at score。

Create a new instance of that and then we're going to call enter on whatever current now is which is the score state passing in the enter parameters that we initially pass into this function。

 so the score state now is going to get those that table those parameters for looking here enter is on the score state is going to get this table so this table is going to get passed into our state machine and it's going to be the sort of like passing overhanding over the keys or what have you to the next oncoming state that we're going to transition to。

And so once we go over here to take a look again up above here。

 so we have quite a bit of code here in our play state。

 but below where we actually are spaing in the new pipe pairs， we have an iteration to see。

If not para dot scored， meaning that we haven't marked that pair is already being scored。

 which is a flag that we need to add to every pipe pair because we could just check every iteration。

 every single one over 60 frames， one over 60 seconds and see or whatever your frame rate is。

 we could check every pair and say hey have we gone past it and any pipe pair that would be to the left of the bird in that instance would still be to the left of the bird for a while before a depawns and so we want to not resco that pipe pair over and over and over again or our score would very quickly get very high。

 so we just flag the pipe pair as being scored if we happen to score on it， so we can just say。

 if not para dot scored then we're just going to say okay if para dot X plus pipe width is less than bird do X。

 meaning is the pipe pair to the left of the bird， if so that we've cleared it the bird's gone to the right of the pipe pair and so we can just increment our self-。

Score， which is a state variable we're keeping in here。

 and then we're just going to say pair do score gets true to store that in the pipe pair and then。

That takes care of not only our score being stored as a piece of state。

 but also prevents like unnecessary rescoring of already scored pipe pairs。

So let's go ahead and take a look then at the score state itself。

We can see here it defines the enter function so you don't have to define enter yourself if you include base state in a state in a state class definition。

 you will get it just an empty one that will work just fine。

 this gets called on every state change so it has to exist but in this particular instance it expects that we will be getting those PRs and it's going to set its score to Params。

 score so remember this is the table that we're sort of transferring over during the state change from play to score in this instance。

 so self。 score gets perms。 score so we're going to store it now in the score state。

And we can now render that if we come down here we'll say your score is colon and then this is the concatenation operator and then self dot score and then we can say hey。

 press enter to play again and now we've added again that press enterter check or return to transition to play once we're in the score state and so all of the activity related to score state thankfully sort of been kept sort of encapsulated in its own block of code so if we go ahead and run this。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_113.png)

Hopefully I can score at least one point， we'll find out。

Might tweak some values just ever so slightly I just have to get one point。Ah， damn it。

 try one more time。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_115.png)

Okay， maybe I'll， maybe I'll tweak the make make it a little bit easier for for the sake of my。

 we'll， we'll say it's for the sake of time。 It's really for my ineptitude that would be in the bird。

Dot Lua will say DY gets negative。250， that might be okay。

 and then we'll just maybe tweak gravity to be something like 900。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_117.png)

Try that out real quick。that looks a little easier， see。Yeah， got one。Got two。Okay。

 that was maybe we should keep it at that， those values， it was actually a little bit more fun。

 but you can see what's cool is that。😊，We got two in the play state that value incremented a couple times and then it was transferred over through the state machines change over to the play state or the score state and it just has it there as a value and then we can just do this add Infinite and this is the process by which you get state that you can transfer between things while keeping them separate logically you don't have to think in terms of like oh these are coupled together really tightly and they have to be nestled and you think about all the code in the way that you would and for example pong's lecture which was purposefully done naively with just a simple variable that we conditionally checked or in any other way we just can think of things more conceptually as objects for state which is kind of maybe useful depending on how you want to think about it and this applies not only just to to game states which is what we're doing it for right now but this could be for entities it was used even in our example that was shown for something like a Mario character for diving and jumping and all these things and we will indeed use that for when we get to Mario and Zelda in particular we will use。

That same idea。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_119.png)

So I'm going to go ahead and close that out。And so。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_121.png)

That brings us then to the idea that， well we have the score state now， which is okay。

 we can score our game is relatively complete in most senses but I mean it's a little bit jarring when it starts off and if we're exploring states and it's just easy to add new states why don't we just add something to sort of give us a better UX or I guess a user experience to get us into the game itself and I'm thinking you know a countdown sort of makes sense it's a little jarring when we just start。

 for example， I'll show it again here， but when we just start and we press enter and we're just already falling。

 it's kind of like oh shoot up maybe I wasn't ready for that that might feel a little bit fast。

 a little sudden so if we just had a simple three21 countdown。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_123.png)

Well it's not the title screen， it's not the play state。

 it's kind of like a lead into the play state， it's kind of between the title screen and the play state。

 so let's just add our own countdown state to the game with this infrastructure that we put in place and represent that so let's go ahead and do that real quick。

We'll close all these out。Go to bird 10。And so B 10， so in the title screen state。

 you'll notice that we go right to countdown when we press enterter， we don't go to the play state。

And then when we're in the countdown state。We have a countdown time， which is 0。75。

 you could tweak this however you want， one second felt a little bit too long。

 but it's about one second it's close to that。We started at the count of three。

 and then we have another timer， essentially the same thing that we did last time。

And then we're just going to basically say if our timer has gone over whatever that interval was。

 decrement whatever our actual number of seconds that we want to look for is which is three so once count gets to zero so at 0。

75 DT accumulated we'll go down to 2 then to 1 then to 0 and then so finally eventually when self。

 count is equal to 0， we can then transition to the play state and so we'll just always render whatever that count is here in the render function and then so we'll visually even be able to see the operation of that state working。

 so let's go ahead and just run this real quick。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_125.png)

So C3，2，1， boom， and once it hit  zero， we do an immediate transition to the play date。

 So kind of a nice little。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_127.png)

Softtening of the process of getting into the game， which I'm a fan of。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_129.png)

So if you go over here， so the last thing that's missing really。

 and we saw most of this last time is there's no sound。 I mean。

 I feel like sound is kind of an important thing to top things off and so why don't we take a look。

 We have just a couple of examples left， but this one in particular is mostly things that we saw last time。

 So I'm going to go over to B 11。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_131.png)

And then I'm going to open up main， you'll see that this has gotten quite packed with files now and one of the things that we will be looking at is okay how can we tidy up our actual project folders because this is just a little unwieldy like we've got a bunch of Lua files in here we have wave files for sounds。

 we have images， we've got now we're gonna have multiple or multiple folders with source code in them like this states folder so we will tidy things up but for right now I'm going to go into main。

lua。This is going to， if I scroll down just a little bit here。

You'll notice I did something like this last week， but we now have a G again using the G to designate it's a global table。

 so we have this G sounds table here。 we've got jump explosion， hurt score。

 and then finally a music track and so the music we're just going to set in particular a couple of interesting functions and might have even shown that no actually I was thinking maybe I had a slide that showed it。

 but I don't but it's just play and then which we saw last week。

 but also set looping is a function that you can use for audio files if your audio typically you wouldn't want this for sound effects。

 I mean I guess you could for certain ambient sound effects and things of that nature。

But you for obnoxious sounds you wouldn't want this 100%， but for music。

 most of the time you absolutely would want it and just like we saw looping textures。

 sometimes you want looping music that is also it's kind of the same logic where the end of your track is immediately the same as what would be the front of your music track so that you don't feel this perceived like either audio gap or harsh sort of like new change in key or change in just overall what this song is doing。

 but here we're doing it so that no matter what happens once our audio plays。

 it's just going to retrigger。And throughout all the code， all the places that we do various things。

 there are a bunch of calls to call these， we won't spend the time to track on every single instance。

 but you know jump only press spacebar， explosion and hurt when we hit a pipe and then score when we actually make it over a pipe pair。

 those will just play sounds in the same way that we did last time and if we run this。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_133.png)

We'll see right out the gate， we have audio that's beginning to play the music。

 which is just much more fun already I press Enter。We'll transition in。

And then we get little spaces here。IThink this is。Pre configured with a much easier setting。It's way。

 way more fun when you， oh I didn't even demo crashing out， I probably should do that。

Because it's way more fun to not be hitting the pipes， I got so fixated on that。

 I'll hit a pipe right away this time。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_135.png)

Yeah， and so also there's a thing that I am doing in that instance too where we have this explosion and hurt sound。

 we have two separate sounds， but sometimes it can work to layer sounds and this is often used in music as well for good effect。

 but sometimes if you don't have quite the right sound。

 it can be easier to just play two sounds at the same time then to try to like synthesize the ideal sound。

 but that's essentially all that's happening in that particular instance。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_137.png)

![](img/5e4c4e34f2136f2f0d887480ad975eeb_138.png)

Now the very last thing that we have is because Flybiird was a mobile game from the outset and we are using it from the perspective of the keyboard。

 but it wasn't designed ultimately to be used that way I thought it was fitting that we might sort of emulate that and so the way that we can do that is love gives us this function called mouseP。

 which is very similar to Keypress it will just trigger any time that you click the mouse and this is essentially also a deferral to touches on iOS or Android and this is often how it's modeled to in the web world。

 but once we click the mouse， it'll essentially fire whatever mouse button we click with so it'll be like a one or a two for left or right click。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_140.png)

So if you open up the source code here for B 12。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_142.png)

We can very quickly look at that， it's very simple because it's essentially just one of the love callbacks。

So we'll go over to Ma D Lua。Scroll down just to touch here。

We'll see below love Key press we have a love mouse pressed， so it also takes an X and a Y。

 which is useful。 this will come in handy when we look at angry birds in particular。

 which uses like actual tracking based on where you clicked and move the mouse or move to the pointer but in this case it doesn't really matter what the X and the Y is we don't care about that if we just click the mouse we essentially just want the bird to bounce up and down instead of hitting spacebar and so all we're doing is we created a very similar construct to what we looked at previously with the keys pressed thing that we added to keyboard but in this case we're adding to love do mouse。

 a buttons pressed table， and we're doing the same thing here。

 you can see love do mouse do buttons pressed and this again。

 just as our reminder allows us to do these checks for single clicks。

 single button presses anywhere in our code we can just think of it as if it was a globally accessible love implementedment function on their global objects but we are implementing it ourselves by extending their namespaces。

And so and also again， just like here's the Love mouse。t was pressed。

 which just takes a look at that table to see is was that button actually pressed and then we reset it in our update function and so if we take a look at for example。

 the bird file，We can see。If lovet keyboard was pressed space or so we're supporting either operation here。

 Love。t mouse was pressed one one being the integer that maps to left click on computers。

 then we do that same behavior， the exact same thing we were doing previously and you can even see here it also references G sounds。

 again the G being a useful identifier for a global sort of table or data structure or what have you。

Globals can be dangerous， you don't want to overuse them。

 but if you're using a sort of data supply of textures or sounds or what have you。

 it can be convenient and often the most elegant way to do things。🎼Let's go ahead and we'll run。

 whoops， that keeps coming down。 We'll go ahead and run this。

 And I'll you might have to take it on faith that I'm doing this。

 but I will just be clicking instead of。

![](img/5e4c4e34f2136f2f0d887480ad975eeb_144.png)

I'm clicking right now instead of hitting space bar。Oly feels even more difficult。

 I think this is because the yeah I think that needs to be they didn't have the balance update in the other source code example。

 but as you can see very trivial ultimately to add a left click support feature in your game especially if you were thinking it maybe exporting it to mobile platforms and the AbiBs example again we'll look into more information on that and using XY sort of。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_146.png)

![](img/5e4c4e34f2136f2f0d887480ad975eeb_147.png)

The positional information as well， which can be useful so we covered a lot of stuff this time next time we'll look at a few other things in particular sprite sheets。

 which will be next week's is breakout。So spritesheets will be very useful the one thing that we did this week which might people might be thinking about is all of our textures are individual and again our actual folder is getting to be very sort of large and dense and full of stuff so we probably want to find a way to as much as possible condsed resources and sprites sheetets are an effective way to do that for graphics so we'll be looking at that procedural layouts for our actual maps so next week is one of the more fun I think procedural quote unquote generation approaches that we'll take throughout the term well have I think what I like our。

What I feel are quite enjoyable layouts for the bricks but that's maybe getting ahead of myself a little bit too much we'll be looking at levels so we haven't had that yet we've sort of just had like pong is a game you play back and forth and the next week we'll do levels health。

 particle systems for more graphic fun stuff， fancier collision detection which is going to be that's one of the things about breakout that based on the direction where you hit the bricks it can be a little bit different and then persistent save data which actually save your score if you want to show off your high scores in the future。

And then for the first assignment there are a few different things we'll want。

 so the pipe gaps right now are like a uniform size and so maybe or not a uniform size or they are a uniform size rather。

 but we want to maybe make them larger or smaller and so that might add or change the difficulty for example。

 if they're smaller， it's going to be borderline impossible if they're larger might be easier。

 and that might be something you would progress through time， for example。

 if you wanted to balance the game slightly differently。

Same thing but the intervals of the pipe itself， they all scroll in and they all come in at the same time right now。

 but we could also randomize that and then maybe they come in staggered or they're slow or they're faster up to you。

And then we've done these sort of new states where we could show for example the score state。

 but what if we want to depending on your score， actually have a Olympic medal or something bronze silver gold though you did a certain you did a certain you got a certain number of points cross a certain threshold and it's a good or less good job and then finally a pause feature which is also a great opportunity to use states。

 but in this case you might want to also keep things on the screen， for example flappy bird。

 so it might be a hint in terms of like maybe this not necessarily a state in the sense that weve just we' showing but some other means by which you can communicate and illustrate state so that was lecture one flappy birdd again was a bit of a more modern take instead of the。

Pong Atari take from last time and we covered a lot of ground。

 we went through and totally revitalized rejuvenated and reorganized our source code rather than having everything be this massive set of conditionals we now have states that are elegant。

 we can model things as estate machines next week we'll dive into breakout。

 which will be a little bit more intricate and visually interesting but this was lecture1 flappy bird and we'll see you next time。



![](img/5e4c4e34f2136f2f0d887480ad975eeb_149.png)

![](img/5e4c4e34f2136f2f0d887480ad975eeb_150.png)