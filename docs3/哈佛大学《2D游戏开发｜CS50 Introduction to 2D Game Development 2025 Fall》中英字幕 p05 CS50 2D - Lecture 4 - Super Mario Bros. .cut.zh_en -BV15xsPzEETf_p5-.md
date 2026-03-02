# 哈佛大学《2D游戏开发｜CS50 Introduction to 2D Game Development 2025 Fall》中英字幕 p05 CS50 2D - Lecture 4 - Super Mario Bros. .cut.zh_en -BV15xsPzEETf_p5-

Hello world。 This is C S 50。 My name is David Main， and this is Colton Agden。

 And we're here for the first of two lectures today， The first one from CS 502D。

 the new and improved version of CS50's introduction to 2D game development later today in a few hours after lunchtime。

 Eastern time， I'll be giving a lecture on practicing programming for CS50 B。

 this computer science for business course。 We may start and stop to make some changes and fixes along the way。

 feel free to ask any questions via the chat。 The last thing we have on the agenda， though。

 for today is a fun fact from Colton， And I'm wondering Colton。

 if you remember what the first video game was that you ever played。

 It's probably legend ofelda link to the past， which isn't befitting necessarily of today's lecture will be for next week's or next lecture。

 but probably link to the past for super Nintendo。 interesting， I think mine was。😊。

Maybe donkey Kong on like on a Commodore 64。 Oh， that version of donkey Kong， the like O G version。

 I think it was either that or at least at home。 I feel like maybe the first video game I played with a。

Family member， my cousin was pole position on the Atari 26 the racing game Yeah okay so anyhow hope those were fun facts for you we'll start in a minute。

You。Hello world， this is CS52D and this is lecture4 today we'll be looking at Super Mario Brothers。

 which is a very famous， possibly the most famous it's arguable sort of franchise of games that we'll be looking at through this term and I'm even joined on stage by a very fitting Mario plusy which is very cool and it fits sort of harmoniously with the slide here as well as you can see also by the slide we won't be necessarily using the exact Mario assets today we'll be looking at a really cool sort of creative Commons version of the same platform or tile set。

 but we'll be exploring all the ideas that ultimately make up Mario so this is the OG Mario and also CS50 traditionally has had a history of using Mario in its own materials and I think it's a great illustration for a number of reasons but it's in a lot of ways a great transition to this idea of virtual world in our game as opposed to the sort of。

You knowSo far we've looked at things kind of abstractly， we have pong。

 which is know these rectangles moving through space， flappy birdsrd， we looked at illusions。

 but there is no really a world representation per se。

 and even last week when we looked at match3 and then breakout these are relatively abstract。

 not so much worlds， but today we'll be actually looking at how to model something similar to this with a few differences but you know we see we have enemies here moving around we have a ground point at some part we have Mario jumping。

 which we have looked at jumping through flappyrd so that part will be somewhat of a reminder from flappybird。

 but know we have blocks pipes and we have a background。

 all these things we feel like we're in a space which is super cool。

 So this is the original Mario for NeS then Mario3 came out for the NeS which also is very sensational when it came out an amazing game I grew up playing more so super Mario world for the Super Nintendo which also has a tremendously positive reputation and then nowadays know Mariio is doing all kinds of other stuff in 3D and here he is with a dinosaur for Odyssey also a tremendously fun game。

 very different。Sor of the franchise has changed quite a bit。

 but the core is still there and we'll be taking an initial look at how to sort of start representing these virtual worlds in our games and start to really model things that are。

 I think a lot of fun。Some of the things we'll be looking at today so we looked at tile maps last week with match3。

 we're going to be looking at the same idea this week except instead of having a puzzle board now。

 we can use the same idea of these sort of IDs mapping to these quads that we draw onto the screen as being tiles that then matter in terms of like are they collidable what do they look like so on and so forth 2D animations important Mario when he's jumping he has a different pose than when he's walking and sort of that also when he's walking。

 he's going frame by frame from one sort of stepping motion to another he's not just a sprite moving around we haven't really have this idea of sprites that actually changed how their appearance is frame by frame as they move that'll be new this week has one of the more sort of I think representative procedural level generation focuses where we actually will make all of our levels in code we won't actually handcate our levels so you certainly could do this。

And then we'll talk about how platform or physics differs from AABB and allows us to detect whether our sort of Mario avatar is hitting blocks when he's jumping or moving or so on and so forth。

 a very， very simple version of AI for the sort of moving Gumbba Sque creature we'll have today。

 which will be a snail， and then lastly how to have things like power ups。

 which will tie into the problem set。So our goal is going to be this representation on screen。

 I've taken a sort of range of screenshots to show where we'll be going。

 you see we have the classic initial starting screen。

 but also all the levels here are just randomly generated。

 they've got different backgrounds different tile sets。

 gaps and chasms and sort of like different props in the background and also blocks with power ups and things like that gems that we can activate through jumping and I think it'd be good to actually demonstrate what it looks like so if we could get a volunteer who'd be willing to come on stage somewhere yes yeah I want't you come on up。

Hey it's Dane right， oh David， okay， okay， nice to meet you， nice to meet you， okay。

 so I'm going to go ahead and hit this button here to get this started。



![](img/67713fb931a2f422757f860cc32b6d07_1.png)

And now feel free， okay， press enter， press enter。And you are now controlling Mario be the arrow keys to move。

 you can press spacebar to jump。You hit the snail and cause it so some of the blocks won't have will have gems and then some won't。

 but as you can see by jumping onto a snail， you will hit it the terrain is collidable so you're walking on top of the terrain some block so this block for example doesn't have a gem in it but if you were it's random in terms of how this is implemented which one willt have a gem in it but if you keep moving forward to the level we might get lucky and get a block that does have one inside of it they all have different tiles a different frame chosen for them so that one doesn't either we're getting unlucky。

🎼ど。Oh， that one did， so now can making if you were to jump on top of it。

There you go or close enough to us， it's my best game yet as he's pretty impressive。

 this is I spent a lot of hours playing this as kid。It shows。

And so we sort of have all the pieces here， even the。

 you know you're walking and hitting these sort of pillars in the level， collision on the snails。

 you've got this jump， your frames are changing if you were to theoretically， maybe even，Pretend。

 of course， to fall down what you want me and we do trigger sort of like a sort of death state at the end level。

 but thank you so much yeah。

![](img/67713fb931a2f422757f860cc32b6d07_3.png)

So as we can see there was quite a lot of pieces there。

 a lot of new things and sort of we've taken a step forward in a way that we haven't really done before in that now we are thinking in terms of existing in a world。

 Flpybird was our initial step and it was doing similar sort of philosophically I guess spiritually it was making us feel as if we were somewhere with its illusion that we have this scrolling background。

 we've got these pipes that are moving flappybird is in the center of the screen and not really moving technically but you could jump and you could use gravity to try to avoid the pipes and there was this feeling that we were somewhere in space with Mario we actually feel like we're moving。

 we have a camera sort of tracking Mario， we've got an offset into how we're rendering things we have this tile map and here is this slide sort of illustrates what tile maps are but essentially it's not all that different from what we looked at last week with the grid of tiles with match3 except last week we were using them to render tiles that we could swap and then calculate matches。



![](img/67713fb931a2f422757f860cc32b6d07_5.png)

We'll be actually using them to draw these blocks on the screen that we can walk on。

 we can walk up against a butt in the case of， for example the blocks that we could hit。

 those were technically game objects but theyre similarly functioning in terms that they were just being rendered on the screen as a subset of that texture and they move around in space related to the camera。

And so just with this drawing of these little pieces of this texture and then putting them in a data structure that models some sort of level where maybe if you envision zero being space。

 one being the ground in our example it's slightly different it's five for the space and three for the ground。

 but you can essentially map that to a level that then we just calculate okay at XY coordinate。

 there's a tile there we should collide with it or not render it as a tile or not。

 and then we just sort of feel like we're in a space now all of a sudden magically so in order to illustrate this。

 why don't we go ahead and step into some code with tiles0 where we'll look at some static tiles。

I'm ahead and transition over to the source code here。I'm going to close the Mario example。

 let's open up tile0。

![](img/67713fb931a2f422757f860cc32b6d07_7.png)

And I'm just going to run it so that folks can see what it looks like。But it's very simple。

 it's just a and this is just some very basic art that I've put together here just before we get to the actual nice tile set that we're using in this lecture。

 which is a very impressive tile set and we'll show it。

 but we just have a background color being drawn here and this is just a random color that I'm clearing the screen with we use love。

 graphics do clear in the past that's exactly what we're using here for the sky and we're just not drawing tiles there and then we are drawing tiles where the bricks are and so if we envision just sort of this 2D sort of grid like we did last time we can visualize how we do this in the same way that we did the match3 grid we'll look at the code here。



![](img/67713fb931a2f422757f860cc32b6d07_9.png)

The tile size， we're working with 16 pixel tiles， we've got two IDs that we care about。

 sky and ground。We had a tiles array， this is't all that different from the tiles or sort of the match three tiles table that we used last time。

And then we're just going to splice up our tile sheet。

 which in this case is just a two tile tile sheet， which is going to give us back just two frames that again we can index into and draw with our1 texture。

 it's a very meager modest texture here as you can see in this case this one on the right here is just VS code's way of saying this is transparent。

 there's technical nothing here on the right side of this texture。

 but here on the left is a brick texture that I've sort of created very。

Primitively using a sp or something， and then here we have this empty so that we can still index into it。

 treat it as if it's drawing a tile， but in truth it's just drawing opaque pixels and nothing's getting drawn to the screen。

So we have a background RGB that gets randomly selected here we're just populating again a 2D array。

 a 2D table of tiles which are just going to be in this case IEDs。

 in this case they're constant mapping to sky or ground if we go down to the draw function here。

We have a clear color that's happening and then literally just a twodial loop that's going to iterate over this 2D table structure that we used similar to last week and it's just going to draw it's going grab the tile and it's just going to draw again indexing into our quads table to get the exact offset that rectangle from one to two。

 itll get either the one or the two， and then it's just going to draw it at the XY minus1 to get coordinate space multiplied by tile size as the offset。

 very simple， very similar to what we did last time with the match3 grid， nothing is really new here。



![](img/67713fb931a2f422757f860cc32b6d07_11.png)

So if we go to tiles one， I think the thing that really stands out is that we don't have。

You know this genre at Mario is kind of like a scrolling platform or 2D platformer you've got like scrolling shooters other types of genres in similar vein to that in the sense that you have a background Sure but it can't just be static we want to be able to move around and to be able to feel like we're in a world and to do that we have to have some way of shifting this map around on the screen and so we have a handy way that we can start to do that with the function called love graphics do translate。

 and so what this will do is rather than everything being drawn just with an assumption that it's at 00 love dot graphics are translate will take an x and O Y and then everything that you draw thereafter will essentially be offset by that Xy coordinate such that you can essentially mimic a camera if you think that we have x50 here everything will be shifted 50 pixels forward and so you can sort of think of it as an inverse sort of direction of the camera moving So if we were to shift everything 50 pixels to the right we're going feel。



![](img/67713fb931a2f422757f860cc32b6d07_13.png)

As if the camera has moved 50 pixels to the left and so on and so forth for every direction on every axis and through this method we now have a way to sort of envision a camera。

 sort of a couple of variables an X and O Y and particularly will focus on X。

 but you can have an x and a Y value that model more or less how we can think of the world shifting in the way that we would think of a camera moving on our scene which then gives us the ability to track a character as we could sort of anticipate and then move through our 2D world so with that let's go ahead and look at the code for this it's going to be a simple addition。

I'm goingTo close tiles zero， we're going to open up tiles1。

And then I'm going to go ahead and scroll right down here。

 we see a camera scroll speed so we're going to scroll。

 this is a test example where we're going to scroll and actually want we to run it just so we can see what it looks like。

 so it's the same example as last time we have a color in the background that's random so that's why it's pink as of green now but if I hit the arrow keys you'll see that I am indeed scrolling the screen left to right。



![](img/67713fb931a2f422757f860cc32b6d07_15.png)

And all this is really doing is just drawing everything with an offset。

 so rather than drawing everything， if we assume here more or less， everything is at00。

 then it's a very simple sort of way to see that okay four tiles down at x times  zero with the first tile gasron x times 1。

 the next tile size times1 tile size times  zero， tile size times 3 times  two， whatever。

 they all get drawn sort of relative to the top left corner of the screen。

 which is00 in love 2D game space， but by using love Do graphics do translate。



![](img/67713fb931a2f422757f860cc32b6d07_17.png)

If we scroll down here， notice that the camera scroll stays at zero。

 we're going to manipulate this variable using deelta time just here。

 like anything else that we've done， just some variable that's going to change based on input here。

 it's going to be a deelta time multiplication on that constant。

And then if right before we do our actual drawing， we just say， okay。

 I'm going to translate by the negative， in this case we're rounding down with math dot floor just to keep in the event that you don't you have fractional sort of translations。

 you can have artifacting and weird sort of lines， especially using push and other just in other domains you want to keep things rounded down for rendering smoothly。

 but if we go ahead and just translate by our negative camera scroll， we end up。

Actually seeing a shift as if we are moving left and right throughout our scene， if I hit left。

 if I hit the left arrow key， we do indeed move left and if I hit right， we do indeed move right。

 we are we are negating rather the variable because we want to make sure that when we press left we think as if we're moving the camera left but recall we have to move X positive in order to actually get that effect by moving to the camera left because everything gets drawn with Lovedo graphics do translate with that offset。

 so we have togate if we're thinking in terms of left and right in our input we have to negate that in order for that to actually reflect in camera space。



![](img/67713fb931a2f422757f860cc32b6d07_19.png)

![](img/67713fb931a2f422757f860cc32b6d07_20.png)

That's essentially all we have to do， we just negate the camera scroll variable we're keeping track of。

 and now we all don't have to really manage anything in terms of our tiles。

 they will automatically look as if they're drawing in the right spot because we are adjusting the entire coordinate system effectively to account for this translation。



![](img/67713fb931a2f422757f860cc32b6d07_22.png)

So that's love do graphics start translate that takes care of the scrolling so we have one very important one of the most important pieces tackled。

 but now we have to also factor in okay we have a world sure we can do that。

 but we should also be able to have a character on the screen obviously that we can start to move around and we can sort of envision this scrolling these variables following the character。

 you know the character should be in the center of the screen we can do all of that but even get started we need to have some character on the screen to begin with so。



![](img/67713fb931a2f422757f860cc32b6d07_24.png)

What we'll do is I'm going to go ahead and open up character zero， and let's just demo that。

 see what that looks like。

![](img/67713fb931a2f422757f860cc32b6d07_26.png)

So as you can see， very simple， very similar to what we saw last time。

 except now we're using a little Marioessque avatar， a little alien looking guy。

 standing on top of the ground， so positioned just so that his feet are touching the top of the ground。

If I move， I can still move the camera left and right。

 so this isn't quite accomplishing our full intentional goal of having the camera follow the player。

 but we can see that we're one step closer to our end goal so things are moving in a good direction let's go ahead and look at the code for this。



![](img/67713fb931a2f422757f860cc32b6d07_28.png)

So there is a height and width of the character that we should factor in for positioning。

 so in this particular sprite sheet， which if we open that up really quickly。

This is what we'll be using throughout throughout the。Remainder of these examples。

 this is our avatar， his sprite sheet and it's a sort of set of similarly sized sprites all in one texture。

 This is just a single row and they're all 16 by 20 they've got different frames in here you can see there's somewhere he's just standing still he's got looking to the right or whatever this might be this looks kind of like tiptoeing on the right very far right here we have some walking frames We've got jumping frames。

 which are these， we've got like climbing frames， we've got like a ducking one here and then something that looks kind of like he's unhappy right here。

 We'll use a few of these in particular the walking one and the jumping one here in a little bit of time but right now we only care about this very first frame and it's not unlike what we've looked at previously for for match3 and even for this example with tiles We're just slicing up this texture into these frames and then we can just index into this array that we know we'll get back through generate quads for whatever this tiles sheet is and then if we want him to。

Look as if he's moving， we can just set the ID of that frame to whatever this end is here。

 11 or 12 or so， or one will just be standing static。So if we go over to Ma D Lua。

We're still using the constants there for the tiles。

 so we're going to go ahead and chop up the character sheet， we get its own set of quads here。

We're going to set the character X and y， and we're going to offset basically put them right above。

 we're essentially setting it at7 tiles down， right above tile 7。

 we want to set it minus the character height so that he's standing right above where the tiles。

 the solid ground tiles begin in our array， our 2D， our 2D tile map rather。

 which is what's done here。And then if we come down here。We'll see。

That we have a draw call done just at sheet at quads1 at character X character Y。

 which if we look up here again， character X and character Y are just being set so that it's pretty much right in the middle of the screen positioned right above where our tiles are being drawn so that's fine。

 Things are working pretty well for that。

![](img/67713fb931a2f422757f860cc32b6d07_30.png)

Simple example， but clearly we want the character to be able to move and that's kind of one of the important aspects of Mario to win a level in Mario。

 you have to move from the left side of the screen to the right side of the screen and then in the full game there's a flag that you can jump on and pull down and that ends up transitioning to the next level and our example that's part of the problem set is actually implementing that stage of it but in order to even get towards that we have to be able to move so let's start to think about how we can do that and let's look at character one。



![](img/67713fb931a2f422757f860cc32b6d07_32.png)

So I'm going to go ahead to character one。

![](img/67713fb931a2f422757f860cc32b6d07_34.png)

Let's run this， just see what it looks like。So we have kind of the same thing， again。

 these backgrounds are all random。So we can see we indeed do have a character that is moving now it's not moving the camera。

 so there's a couple of pieces here very clearly。 we have one to move the character so that the character in the world is moving。

 but we also have to move the camera along with the character and we have to make sure the camera is sort of statically fastened to the character's position so we'll look at how to do that in a second I's just going to go ahead and open up character one's example so we can see what that looks like I'm going to close all these other examples。



![](img/67713fb931a2f422757f860cc32b6d07_36.png)

It will be down here in our updated function。Where we can see that we're just doing the same thing that we've always done historically。

 we're just changing the x value by delta time through some constant that we've defined as character move speed。

 all of these constants typically are tweakable with the exception of maybe constants that index into your tile sheets and then we do all the same code as before。

 pretty standard， we're not calling we are calling translate ultimately。

 but we've essentially replaced the actual logic that adjusted the camera scroll with the characters's position。

 so now we have to essentially marry these two ideas together。



![](img/67713fb931a2f422757f860cc32b6d07_38.png)

So that brings us to character  two， which would be the track hero。

 which allow us to actually start doing just that， so let's go ahead and close this。

 and then I'm going to go ahead and open up character2。



![](img/67713fb931a2f422757f860cc32b6d07_40.png)

![](img/67713fb931a2f422757f860cc32b6d07_41.png)

And if I move this character。We'll see indeed， somehow the character is remaining completely within the middle of the screen。

 but as we can see by the scrolling of the tiles and the fact that we're reaching the maps sort of endpoints。

 we are indeed moving our character in worldspace， so how are we accomplishing this？



![](img/67713fb931a2f422757f860cc32b6d07_43.png)

I'm going to go ahead and scroll down。We are doing this in the update function。So。

Here we are doing the same thing where we are moving the character's position because the character does need to move in the world。

 That's not something that needs to change。 The difference is that now we need to essentially set the scroll to be equal to what's effectively the offset of the character to its left side effectively so we need to essentially take whatever the character's X position is subtract half the virtual width。

 which will put it approximately in the center of the screen and then add the character's width divided by two because remember everything is drawn or everything in our in our games is relative to its top left corner so we need to shift halfway through the character's width to be properly centered and then now the camera's scroll will always just be whatever that half screen width is away from the character meaning that no matter where our character moves。

 the camera's position effectively is going to track the character's position and so here we can see we didn't really have to change anything here。

 the camera scroll is now just managed in addition to the character's own position being set the character's position is now。

Dictating with the offset of half the screen width where the camera gets drawn。



![](img/67713fb931a2f422757f860cc32b6d07_45.png)

So that's great。 We have tracking now Co， There's a few pieces left though。

 things are a little bit static， things feel a little bit weird。

 The fact that we're just kind of moving the static sprite around feels unnatural。

 so the first step is going to be let's animate the character。 we've seen the sprite sheet。

 we've seen that we have this ability to do this。 Let's actually do it。

 let's actually look at what it means to animate something。

 animate a character or any sprite over time。😊，I'm going go back to here。

 thing thing I think I have a slide about this just to illustrate this。

 but we sort of talked about this briefly， but essentially there's a set of tiles that we have。



![](img/67713fb931a2f422757f860cc32b6d07_47.png)

This is the only one we're using。 But if we imagine that over time， this number。

 this quad index into this table of quads that we're generating could change and then maybe loop around to some point。

With some interval of time， we can imagine just like using delta time to either toggle a couple of sprites back and forth or a couple of frames in this texture back and forth。

 or we could know do any number of things with any number of frames just over some time。

 and we can see at the very end， we've got a couple of frames in particular。

 those last two are going to be sort of like the toggles we could envision for walking if we're looking to the left。

 looking to the right， maybe we flip the texture because this is all you folks might notice this is all just looking in one direction to the right。

 But if we're moving to the left well we want to also reflect that literally and just visually。

 so we need to flip the sprite to look towards the left So we'll do that as well。

 and then you know essentially you can just think of it like a flipbook like if you have a bunch of images if we envision those same images just on top of each other and a flipbook repeated and just flip the pages quickly。

 it'll look like he's walking at varying speeds。 so we can take a look at that。

 So let's go ahead and look at character4。Or character 3。I'm going to go ahead。Closeses this。



![](img/67713fb931a2f422757f860cc32b6d07_49.png)

And let's just show what this looks like。

![](img/67713fb931a2f422757f860cc32b6d07_51.png)

So everything's the same， although slightly harsh with that green color， so that's actually redo it。

 so it looks slightly better。

![](img/67713fb931a2f422757f860cc32b6d07_53.png)

That looks a little bit easier， contrastwise。 so now if I hit left and right you'll notice see's static right now。

 but as soon as I hit left， he looks to the left， he's walking， his legs are moving。

 I let go of the arrow key。 He goes back to this idle state。 He's no longer moving。

 He no longer has an animation if I move to the right。

Same things except now they're looking to the right instead of looking to the left and then back to center。

 so we've done all the things that I've just alluded to。

 we've animating and we're also adjusting the position， so's look and see how we're doing this。



![](img/67713fb931a2f422757f860cc32b6d07_55.png)

You'll notice that I have an animation。lua in here now and this is the backbone of how our animation is gonna work and also how animation is gonna to work in the distro。

 it's the same the same class here。 but essentially it's all the things I just alluded to。

 We're gonna have a set of frames。 you think of an animation as a set of frames that should play over time and then typically you'll just loop back through the beginning of them。

 So if you imagine the walking animation， it's literally just two frames It's one it's the 11 and 12 ideal wise or approximately there if you imagine those sort of flipping back and forth or it's 1112 and then looping back to 11 it's essentially a sort of flipping of two things。

 If your animation was five frames 1112131415， you'd play them in order and then loop back to 11 112131415。

 1112，131415 probably assuming that your animation loops sort of elegantly smoothly。

 which is an ideal characteristic of an animation that is intended to loop。

 it should look smooth in the way that our flappy bird parallax background was smooth and the same backgrounds in this distro are smooth The animation should have an。

And then often it's the case that an interval is the same。

 but you could in theory have intervals that are different and so you you would need to keep track of each interval per frame what that is。

 and then you could set an animation to change sort of differently over time all of our animations for this district will be the same interval and it's usually some very small duration in seconds or half or fractions of seconds in this case the walking animations probably like 0。

25 or 0。5 seconds。And then a timer to manage that and then whatever the current frame is。

 we're going to be get this back whenever we call our animation。

 we're going to need to render the animation at whatever its frame is。

So the key detail which I alluded to is is deelta time here again Delta time is often the solution to these sorts of problems。

 so if there are more than one frame in the animation。

 then we're going to just update our timer and then assuming that we've crossed over that interval so whatever that might be we'll pass that in in terms of a definition here which is what this de parameter is to the constructor we will then set the timer back to the modo of that interval which we wrap it back to0 and start it with whatever the fractional overlap was and then we'll just set it to be no greater than one or rather the higher of one so it can't be below one or in this case we're going to modo if we take our whatever current frame is plus one and then modo the number of frames plus one onto that the reason that we're adding plus one here is so that when we get to the current frame being the end frame in our animation we still want that frame to finish over that interval and if we were to。

Se it to current frame modulo self do frames， it would end up actually just immediately skipping the last frame because that would be the length of the number of frames would be whatever our length of frames is is going to be that last frame so essentially modulating by and adding two one frame past the total number of frames such that it just overlaps。

 loops back to one at that point and then we still get that last frame rendered on its full interval and so as a result frame the first frame will go its interval then frame two will happen and then it'll loop back to1 and then two or if it one。

2，3 it would do all of that no matter how many frames。

 it'll always run the interval and then modulular wrap itself back around to zero for the timer and then ensure that we always go back to one when we mod because modulo goes to zero we want to make sure that we actually modo to1 instead of zero。

Okay， so let's go ahead now。We've done that， we've looked at animations or actually well rather we need to look and see where this is rendered。

 got ahead of myself slightly so here we're going to define two animations in main dot Lua so we have just essentially we can still think of our idle position as an animation。

 just a one frame animation。And it's not going to actually do anything we saw there was an if statement to check for more than one frame。

 so effectively this is just essentially for consistency for our character。

But we do have a moving animation that has 10 and 11 as the two frames into our sprite sheet recall when we looked at the sprite sheet。

 they were kind of at the end， the 1011 indices into our sprite sheet， the interval here we set as 。

2， so every 0。2 seconds the frame will tick and then we'll go to the next frame and then loop back around。

We're going to set to idle animation and then what we're going to do we also want to keep track of the direction for moving left and right。

 we're going to also want to flip our graphic left and right which is an important detail and then let's go ahead and go down to update where we can see that we are indeed updating our animation because it does take DT it does need to know how much time is passed by so it gets an update just like anything else。

Much like timer did last week。And then here if we are for pressing the left or right。

 we want to actually change the direction and if we are in this case moving。

 we want to set that to be the moving animation， rather， no matter what the case is。

 we want to set the current animation to the moving animation。

And then if we are not doing either of those， then we can just set the current animation to the idle animation and then update it。

The result being here， if we come down to love graphic draw after the map gets drawn when we draw our character。

 we're going to instead of drawing quads at just index1， which we were doing previously。

 we're going to whatever our current animation is， we're going to call get current frame。

 which if we look back here， it was literally just an index into self dot frames that current frame so just a glorified getter basically。

And then we're going to essentially set the width and height here by an offset because it's important when we're shifting things in space。

 rather when we're flipping things left or right in either on the X or the y axis。

A flip will if you're basing your origin on the top left of your character。

 which is what we do by default， it will actually flip around that origin point and end up having weird behavior。

 we want him to actually rotate in place and so to do that we have to actually set the origin point of our character right in the center of the sprite instead of the top left corner which doesn't affect our calculations for physics but it does affect where things get drawn which is what we do here。

 we actually this last two arguments to love our graphics draw after sort of all these other arguments that we've been used to seeing。

If we set the origin here to character width divided by two， character height divided by2。

 what we're essentially doing is we're shifting in from the top left corner。

 that origin to be slightly well to be directly in the center of the sprite such that scale operations now happen based off of that origin point and not this top left corner and the scale operation is how we apply a flip。

 if we scale by negative one on the x or the y axis that's effectively what's going to flip the axis around the origin point and it's going to trigger that sort of flipping aesthetic。

 it's a scale technically speaking， and that applies to the origin。

 It's always going to be relative to the origin。 And so we also in order to account for this we have to draw。

Essentialsly shift the characterss X and y by that value because now all drawing operations are going to occur based on the center point of the sprite。

 which is going to result in the sprite looking as if it's shifted up towards where it's00 point was previously at its top left so we're essentially shifting the origin into its center and then we can offset that by drawing inwards by that amount。

 and then we can now flip its axis of rotation or we can flip or along its x axis depending on whether it's moving left or right or whether we have left or right set。

And so ultimately that results in being able to move in place while being able to still have the same collision and things draw just as if they were as they are expected to。

 essentially。

![](img/67713fb931a2f422757f860cc32b6d07_57.png)

And so we have， therefore， all that we need in order to draw a sort of。

Flipable translation or a flipable animation now character that can rotate or not rotate。

 but can flip on any axis y or x axis and look as if it's moving left or right and they animate as well。

 so now they actually look as if they are sort of more lively， interactive character which is great。

 great steps， the last thing to illustrate just the basics of the character before we move on to other topics is the ability to jump。

 which is a very core part of Mario， Mario sort signature thing is jumping up and hitting blocks and so it's only fitting that that's the last thing that we have Mario do in this example and there's again another we saw that already alluded to the sprite that will allow us to do that。



![](img/67713fb931a2f422757f860cc32b6d07_59.png)

And what's cool is we already sort of looked at that in flappybird。

 so let's go ahead and open up character four， I'm going to close these examples。



![](img/67713fb931a2f422757f860cc32b6d07_61.png)

Open character 4。And then we have the same thing as before， it can move the character left right。

 everything works exactly the same now if I hit spacebar。You'll notice that if I'm staying still。

 the character is just kind of jumping up and down in place， if I move right and jump。

 you'll see the animation is slightly different， but they are indeed jumping with their fist raised up。

 which is part of that animation and then left sort of the same thing。

 so I'm essentially setting that stat frame to be whatever that jump frame was probably nine based on my memory of this sprite sheet。

And then if I'm moving left， it'll keep that frame and if it're moving right。

 it'll change to that frame， and that's essentially all we need now to feel like we're using a sort of very analogous Mario character with all the same basic features of at least Mario from the original Super Mario Brothers version。

 we can take a look at that here， it's not a whole lot more that's been added。



![](img/67713fb931a2f422757f860cc32b6d07_63.png)

We've just added a new animation for the jump animation， which is apparently frame3。

 I thought it was frame nine， it looks like it's frame three。And then if we are。

 if we come down here just a little bit down into the love dot key pressed。

 if the key is equal to space， and the DY is0， meaning that we aren't already jumping because remember this is what we did in flappyword。

 we have some gravity amount， the character can jump up to set their negative gravity。

 their negative DY to some value， like negative 300 if we assume like a 980 or 900 gravity on the positive y axis。

 and then gravity will bring them back down。But that's essentially what we need to check for here is are we already negative or are we already statically set on the ground such that we're not either jumping or falling down because we don't want to just allow the character to keep jumping and going up and up and up。

 we did that in Flpybiird， you could just spam spacebar and just keep moving up the screen。

 which is part of the game， but in Mario you only get to jump when you're touching the ground so that's what we do here。

Then we can see here we apply gravity， very similar to what we did with flapapppybiird。

 and then in here we have just a hard sort of like check for are we at where the tiles begin on the map。

 which is about tile7 minus the characterss height so that when its feet touch the top of that tile。

 it won't go any deeper than that。And then we'll just update whatever the current animation is。

 and then keep moving left and right， so on and so forth， the same things should still apply。

 we should still be able to move left and right and then still apply a transformation to whatever we're jumping at with current animation。

 nothing changes， even if we're jumping， it's still going to be the same thing here。

 but now our animation can now just be jumping instead of instead of being static or moving to the left and right。

 depending on whether we press Bbar and we are indeed jumping。



![](img/67713fb931a2f422757f860cc32b6d07_65.png)

And that ultimately wraps up all of the character examples。

 which now we can begin to start to take a look at another key aspect of this distro。

 which is the level generation。

![](img/67713fb931a2f422757f860cc32b6d07_67.png)

Okay。I'm going to take a water break real quick。Good job。嗯。

So to sort of bridge us to the distro then what we're going to want to take a look at。

 start taking a look at is procedural level generation， which is something that's pretty cool。

 I've always been kind of a fan of it， it can be something that's you know。

overly done and sort of to relied on sometimes but in the case of today's example。

 the benefit is that we can get some really nice looking levels without actually having to by hand create all of them。

 giving us sort this infinite replayability which we've explored this idea in concept。

 at least in terms of breakout for example where we have all of these different types of grids of bricks that can be generated that can be broken and then in match3。

 the grids have to be randomized in a similar but simpler way but in today's example。

 we can sort of start to think about level similarly in that you essentially have a obviously a grid of what we represent as numbers so far that we've looked at and these have some sort of semantic meaning in terms of how they should be placed together for example a ground should be at some baseline level probably so far we've been doing it about six tiles down。

 seven tiles down into the game space and then you can start to think about okay well that's just a flat ground that's infinite in sort of the way that it feels in pretty simple。

and not much of a level， but if you start to say， okay。

 instead of having all tiles throughout that whole space from7 down on the y axis all the way to the end of the x axis。

All of them always being filled， we can start of imagine。

 okay well what if we instead just decide to introduce gaps in there sometimes or we put pillars or we draw pyramids or we do any number of things。

 we start to add new props， new features instead of tiles， maybe there's switches。

 maybe there's blocks， we can jump up and hit， maybe there's sort of decorations like bushes and clouds and various things。

 maybe there's。Coins， any sort of thing you can think of and you start to place these around and you sort of have rules that get more and more elaborate now you've got the system in place that allows you to create these infinite levels and the sky is the limit ultimately for what's possible as long as your logic is such that you never overly put the player into a position that's unwinnable which is difficult in its own way。

 you end up having a pretty robust system for certainly for testing and maybe even for playing games that are fun enough at least to play for some people。

So we'll be looking this week we have a quite nice tile sheet that's Cative Commons。

 an artist named Kenny did the original version of this which then had a sort of 16 by 16 version done by somebody else。

 which is really neat and it has just a plethora of tiles here as we can see and these are all tile sets we'll only use a couple of these throughout today's lecture and particular the empty and the full just square version but you can see there's slopes and rounded versions and all sorts of fun things you can do with that I encourage people to explore with the codebase but in addition to that we not only have tiles but we also have tos for them。

 so this is a way to sort of add these don't really functionally mean anything in terms of gameplay。

 but they do offer a way to differentiate your levels visually in a way that allows us to get the sense that okay we're not just in some random plane maybe we're in like a candy themed place or like this icy area or this foresty place and so this is just a simple change really ultimately it's just drawing a texture on top of another text。

which we'll see， but it does offer a tremendous amount of visual variety that gives your game a lot of pop and makes it fuel just fun to play In addition the spritesheet includes a lot of these other tiles and whatnot that we can use there's some hills and some blocks we'll use these blocks for sure we'll use a we' use there's a flag here for actual distro for folks to use for the problem set。

And then there's some other various examples here， you can see that there's even a couple of creature sheets here we'll be using this。

 this is where we got our character from， but there's also like an enemy here， a snail enemy。

 and a bunch of other things， the gems here for the power ups。

 keys and locks for the actual problem set as well。

Here's the tiles again so you can see what it looks like just isolated。

 I've gone ahead and isolated most of these as well。

 so rather than having them be just in one big texture， which is what this is by default。

You get instead we have this， we can sort of now if everything's symmetrical， recall。

 we can splice it up programmatically a lot more easily。

 we don't have to hard coat offsets and do things that are too crazy to figure out where we are。

 same thing for the toppers， these are now isolated。

 these are now programmatically slicelicable in the same way。

And then with just these visual elements we now have， as you can see。

 I try to take a representative selection of levels。

 but just and I'll do some live illustrations because I have a key bind set up to generate the level textures over and over again。

 but you can see we have not only are the visuals varied in terms of we have the topper here we've got like this green texture on top of this darker texture。

 we've got this white texture here on top of this yellow all of these kind of have a different version of that。

 we not only have that the backgrounds are randomly chosen。

 but there's only three of those but you can see we've got like gaps in the levels here， gaps here。

 we' here we've got a little bush here we've got a little grass looking thing and then we've got these pillars as well that stick up and every sort of thing if we imagine sort of thinking of our level as this set of tiles that we can place in a line going left to right top to bottom。

 you can sort of envision that you maybe we want to say okay on this tile。

 I decide that I don't want any。Tile this particular column and they maybe on the next one it's like。

 okay this one I want to just set the ground at normal will just define some sort of normal ground elevation。

 okay draw ground from the top to bottom draw ground from the top to bottom and then whatever the first tile is put a topper on that tile。

 mark it with a flag to say hey let's have that one be a topper tile because we don't want to draw it on these ones below here itll look like a glitch we do want to draw it on whatever the topmost tile is notice for example looking at here you can see this one has a toppper it's the surface and this one here doesn't where these same elevations are。

 so you can do a lot of these sort of calculations looking as if we have like this marker going across the screen placing tiles in sort of that direction you can think of your game in multiple different ways your level in multiple different ways you can have multiple passes throughout your level to place things after the fact once you've laid your ground for example that's an excellent time to decide okay now I want coins here and like an arc or something or I want to put like a block here that you can jump on to get something and there's multiple ways。

You can conceive of level generation， we'll take a light look at a lot of these ideas。

And we'll start with level  zero。 so let's just get a basic version up。

 This is essentially the same thing that we did previously。

 except we're going to start to use our new graphics here。

Let's go ahead and I'm going to close out character four， we'll go to level0。



![](img/67713fb931a2f422757f860cc32b6d07_69.png)

And then I'm just going to run this， see what it looks like， we do indeed see this is random。

 so whatever it picks is just going to be a random tile with a random topper。

 the background is going to be random color。And then if I press R。

You'll see that I'm shifting through all these different graphics。

 and so we can sort of see lots of really cool combinations here if I do just all of these。

And all it's doing。That looks like sonic all it's doing is essentially just taking。

The tiles that we're rendering and so now we're instead of drawing this very primitive brick texture with the transparency layer for the sky that it was doing before。

 it's now deciding to randomly take we're going to splice up all of our graphics from the from the tile set。

 we're going to splice up all of our toppers and then we're just going to pick a random number between the number of tiles sets and the number of toppers。

 grab that block of tiles or tos and then just index into it at whatever that ID is for the tile and then just put the same topper on top of it。



![](img/67713fb931a2f422757f860cc32b6d07_71.png)

So let's go ahead and into our source code here。We'll see in we've got a bunch of constants here。

 these are just the number of tile sets wide and tall， all of our topers and tiles are。

 there were more topers than there were tile sets， we won't spend too much time looking at necessarily all of the code for chopping it up。

 it's essentially just a calculating a set of offsets into our tile set so in the case of our we're going to chop up all of our tile sets based on generate quads but then we're going to pass that into here。

 we're going to then just essentially divide up that whole 1D array into a set of into a 2D array which is going to have each block of tiles within that particular tile set if we look at for example。

The tiles here。You can see that we have a block of tiles here that are all going to be one array。

 a block of tiles here， there are going to be one array， block of tiles here。

 and if we zoom in a little bit，If we look at for example， we'll look at this one as an example。

 you can see if we count in 16 blocks of tiles it's a little bit blurry so you can get a little bit crisper but you can see in factor if we figure each of these sort of blocks here as VS code is rendering it as these four tiles together is one tile one 16 pixel by 16 pixel tile this would be tile 1。

 this would be tile2， this would be tile3 then for and then five and so we can see just looking at this that for example tile 3 here is our solid tile that we're going to use for all generation and then tile 5 is just our empty tile it's just transparent。

 there's no pixels being rendered there if folks wanted to they could choose to use some of these tiles here for sort of slopes。

 if they wanted to implement slopes and offsets vertical offsets for walking up slopes or if you wanted rounded corners you could choose to use these for the bottoms of certain things a lot of these other tiles are the same tile essentially。

It has this solid tile but put together in a way that makes it easy to visualize sort of what the tile set looks like in a representative example of what the terrain ought to look like。

So it's really neat and we can essentially just index into this with some ID3 and5，3 being solid。

5 being sky， essentially a ground and sky， and we can do the same thing for topperpers。

 which have called tile tops， which is laid out in the exact same way by design。



![](img/67713fb931a2f422757f860cc32b6d07_73.png)

And if we just zoom in a little bit。We'll see that they align such that。Whoops。



![](img/67713fb931a2f422757f860cc32b6d07_75.png)

If we go to where the purple begins here。We can see we have one， two， three。

 the topper would perfectly align with that tile，4 and then five for transparency。

 so things line up perfectly between the tile sets， and then it's a matter of just deciding， okay。

 if I have a tile set and a topper set， we call them topper sets。

I can just draw the tile and then if I have a flag on that tile that says okay you should have a topper just draw a topper as well right afterwards on top of that tile and now we get this sort of layered effect of this top of the tile having this element on top of it so if we look down here we're just going to go and scroll down just a little bit here we can we have we're going to choose a random tile set and topper set which we can index into。

 I'm going to come down to draw function here， which is going to be where we have our 2D iteration over all of our tiles。

 and so when we get our tile we're going to do our usual draw。

 which has been previously what we did essentially which is just draw whatever that index into the tile set is we were just using the two tile set before。

 what we're going to actually have whatever the tile set that we randomly choose。

 these are just going to be two random numbers。

![](img/67713fb931a2f422757f860cc32b6d07_77.png)

And then whatever the ID is at that tile， we're going store the ID just on the tile now。

 instead of it being a number， we'll store the tile ID because we want to flag whether it has a topper。

 which is what this does right here。 So topper is just a flag it's just a boy and this's basically going to be okay is this tile like essentially touching is this the top surface of the ground essentially we do our when we create our level and if it's true。

 then we should draw the topper else that means it's going to be below somewhere somewhere under the ground under that first tile that gets done in our when we actually generate the level。

Here。At the might have put it into a function。Let's go ahead and scroll down just a little bit。

Generate level now instead of just being a tile ID that goes into our table。

 it's going to actually set topper equal to whether y is equal to 7。

 meaning that that's the point at which we begin to draw solid tiles And so we do this turnernary expression in Lua again。

 So if y is7， then it'll be set to true else it'll be false。

 And then through that we can then check that topper flag in the future and determine whether we should draw topper at the time we draw the regular tile。

 and that's essentially how we can draw now varying tile sets and topper sets to give our levels a cool visual variety and you could semantically flag these。

 you could set constants equal to okay this particular topper is icy themed or its fire themed or something and then you could limit sort of what the actual topper set is that you can choose for your level and have there be meaning there。

 We're just running the entire texture in this case and we're just deciding that it doesn't matter。

 none of that matters at all， it's just completely random and so you never know what you're going to end up getting。



![](img/67713fb931a2f422757f860cc32b6d07_79.png)

。So that's level zero， we got flat levels， so we talked about this a little bit in terms of how we can start to vary up the terrain。

 but if we think about the first step being well， instead of just completely flat levels what if we had some of the terrain actually jutting up from the ground in this example we won't do anything more complicated than just a few tiles up but if you sort of imagine okay。

Right now we just essentially do a 2D loop， which just at the time that y is equal to7 in our columns。

 we start to draw tiles。If we instead just decide per column iterating on the x axis through our table。

 we'd say okay， there's a one in whatever chance that instead of starting the terrain at7。

 we'll start it at four and then so that's going to result in tile4 getting to be solid and then all of the tiles below it being ground and then tileu 4 there getting set to the top or equals true instead of seven and then now that's going to stick up and then we just if we make it a certain percentage chance。

 then some of them will have pillars and some of them won't take a look at what that looks like here。



![](img/67713fb931a2f422757f860cc32b6d07_81.png)

I'm going go ahead and close these。And then run， sorry， level one， not level zero。



![](img/67713fb931a2f422757f860cc32b6d07_83.png)

And you can see here we do indeed have our character on the screen， we can move around a little bit。

 we can clip through the walls right now so we're not actually doing any collision at all。

 but we can see that we're sort of essentially just there's a random chance between one and some relatively low number that instead of starting at seven。

 the ground just decides to start at four。And so we have just some visual variety， it's not exciting。

 it's not appealing， you occasionally get these sort of cool two block thick pillars and you could make some code。

 some logic in your code actually decide， okay I'm going to draw this column and the next column and the next column for example at four so that we guarantee a three block or whatever block with pillar。

 but right now we're just essentially relying on pure randomness and as a result。



![](img/67713fb931a2f422757f860cc32b6d07_85.png)

Excuse me， sometimes you will get these。Sort of groupings of these pillars。



![](img/67713fb931a2f422757f860cc32b6d07_87.png)

We'll go into main of level1 here and then we're going to go down to our way down to our generation function here which is where this is all going to take place。

 this all gets moved into levelmakerr。 Lua in our actual Mariio distribution but we can see here。

That what we're going to do is we just create our entire level with sky tiles to start with。

 we just completely populate the whole thing with sky。

 then we're going to start from the left going all the way to the right of the screen。

 vice versa for camera。And what we're going to do is essentially create a one in five chance to spawn a pillar and then if we do have that。

 then we're going to from four to6， go ahead and create that as ground。

 and then we're going to set to or equal to pillar is equal to4。

 and then rather if pillar is equal to 4 we'll set topper to true on that tile。

And then always default or fall back to the ground so that no matter whether we draw a pillar or not。

 we'll always still be drawing the ground below it， and then in the event that we did spawn a pillar。

 we don't want to also set the topper on seven， but if we didn't spawn a pillar we do want to set it to we do want to set the topper to。



![](img/67713fb931a2f422757f860cc32b6d07_89.png)

True if we are at seven。And as a result we now have pillars throughout our level space。

 which is great， things are varying up a little bit， things are different。

 but you know in Mario one of the big perils is falling into chasms and I think that that's also a very similar idea that we could explore so let's go ahead and take a look at what that means in level 2。



![](img/67713fb931a2f422757f860cc32b6d07_91.png)

I'm going to go ahead and open up level two。Close this。Again。

 this is going to be done in our generate function at the very bottom of the program。

 everything is sort of condensed here。And we're going to do the same thing we're going to populate everything with sky first and then we're going to essentially a chasm is just essentially not drawing any tiles at all in that particular part of the level and so really it's as simple as just choosing not to do the whole bit of logic that we just added in there。

 we're just going to do this continue sort of go to way that Lua does continue。

 we're just going to say， okay we're just going to go to continue if matht random7 is equal to one and continue as this label here at the very bottom of this block below where we actually add tiles and so if we just skip the tiles。

 they'll remain prepopulated as sky and so now we just get chasms for free by just simply not generating anything and as a result if we run this。



![](img/67713fb931a2f422757f860cc32b6d07_93.png)

We do indeed have some chasms here。Now it looks like there is a bug with the topers on this particular example。

 which I missed， but as you can see we do have chasms here that are being skipped over by just the pen in our code is essentially saying okay。

 one in seven chance then we're going to show a we're just going not generate those tiles and then you do as we were doing before。

But it's a little ugly looking I would argue and what you could do besides the fact that the texture is glitch。

 it's ugly in the sense that the actual width of the chasms is so narrow。

 typicallyy in a game like this， you might decide， okay， if I want a chasm。

 I probably want it to be at least two or three pixels wide， so you could elect to decide to draw。

To skip over from if you're at x is equal to5， for example， as your chasm。

 you could just skip right to x is equal to8 deliberately and then shift over a whole three or four tiles and then get a larger chasm as part of your design and then just never have single chasmed blocks it's up to you you could certainly do that and I would argue that that's probably good。

 although it's also arguable whether you might like the fact that there's multiple gaps here。

 it's sort of intimidating sometimes to have a bunch of gaps in your level that you just you can sort of psychologically jump across them。

 but you might lose your nerve a little bit so to speak in the process。



![](img/67713fb931a2f422757f860cc32b6d07_95.png)

And so that's ultimately going to be a matter of taste for whether or not you want to how you want to design your levels。



![](img/67713fb931a2f422757f860cc32b6d07_97.png)

![](img/67713fb931a2f422757f860cc32b6d07_98.png)

So that's level  two， so chasm levels and。As folks noticed， you know。

 we had the ability to walk through our level and。The level generated just fine。

 but collision is a little bit weird， it's a little bit different。

 we're not quite colliding with the level at all except for the ground and that's essentially a hack in that we're essentially hard coding where we stop on the ground and actually performing any collision detection so here we'll take a second to start and explore how Mario handles its collision detection。

Okay。Take a drink of water？嗯。So to begin exploring collision detection。

 I think it's important to begin to talk about how it's different with a tile map versus how it might have been done previously。

 at least it can be different for a tile map you could certainly use AABB for a tile map and it works fine enough but there are I think benefits to being able to simplify the collision for something like this。

 given that there are so many tiles in the space of the game and there is complexity involved in actually determining if you were to。

Try to shrink down the tiles that are relevant in terms of figuring out what Mario ought to be testing for a collision with。

 so it's easy actually if we know that we're in a tile map and all the tiles are static in their placement we can essentially just determine at a given pixel what particular tile is there based on Mario's position or a Mario avatar and determine okay that's a ground tile then that means that that is a collidable tile。

 I should shift Mario to be to the right of that or left of that tile or whatever relation。

The character has to that tile and it's moving， we can bump it to the outside edge of that tile versus having to do AABB for maybe every tile in the whole screen let alone the entire map。

 which is just know especially when you have other entities that maybe are trying to collide with things like the snails。

 for example， that we'll be adding， there's benefit to being able to just isolate your checks to wherever you're moving。

 whether you're walking， whatever you're doing， jumping to just the immediately surrounded tiles based on the character's position。

 we can get a lot of shortcuts and a lot of processing advantage by doing that。

So we won't be using AABB， we'll be using a function called point to tile。

 which will add to the tile map， which allows us to just say， okay， at this XY coordinate。

 we're going to divide by the map's sort of tile size。

 and then whatever tile is there at that index in our tile map at Yx。

 we can determine based on whether it's collidable or not。

 that we have actually collided with a tile， a physical tile， a ground tile。

 whatever tile might be that we might use。There's benefits to this for sure。

And when we test for collision in this new model， so we're not no longer now taking rectangles and comparing our rectangle with those。

 we are still doing that for what are called game objects which we'll see in a second。

 things like the bricks that we can jump up and hit or things like the gems that come out of those。

 if you were to add coins if you were to think about also other entities for example。

 we do still do AABB throughout the code but in different circumstances but for our tile map。

 which has hundreds， maybe thousands of tiles， we're only going to essentially use a sort of conversion between our point our characters coordinates to whatever the tiles are in the world and so for example。

 if we're colliding with something that's above our head which is typically only something we're going to do when we're jumping we can say okay at the characters is essentially top left coordinate and top right coordinate。

 we'll check whatever the tiles exist that are there and so that'll accommodate any particular we don't want to just check the top left。

If there's a tile here and we're only checking for top left。

 well we had clip through this right tile essentially。

 so we want to check both edges of our character to ensure because we can be between two tiles。

 we want to essentially ensure that we don't collide with whatever both edges are。

 same thing for below us if we're falling down or if we're walking or doing anything。

 we want to check the bottom left and bottom right of our character's avatar so that we don't just isolate collision checks to this edge。

 and end up actually clipping through， for example， this tile。

 we want to check both sides of the character's bottom。And then here we have on the left side。

 if we're moving to the left， we want to essentially do the exact same thing， characters top left。

 characters bottom left， and then the characters is moving to the right， character top right。

 and then the bottom right， and these will get applied in the walking state and in the falling state and then the jumping state because we can move left and right when you're jumping and falling and walking。

And so with those。Assuming that you detect or you calculate， okay， whatever this Xy is。

 whatever this Xy is， and then divide by the maps tile size。

 you'll arrive at the x and y indices into your table in order to actually calculate actually figure out what the tile is that's there and then you can then say。

 oh， is that ground tile， is it a sky tile， sky tiles aren't collable。

 ground tiles aren't collable and then you're only ever checking pretty much depending on your direction two to four tiles at any one time instead of maybe hundreds or thousands of tiles。

 it's a very sort of like o of one type of operation。

And then we have also a discussion about entities that we'll have to talk about。

 we can briefly look at the collision before we maybe talk about the entities because that's a whole other subject。

 entities being will be， for example， the player and the snail and various other things。

 let's take a look just at what the collision， how the collision is implemented in the code base。😊。

And we'll be overall probably skimming over some details and encouraging folks to read some of this because the codebase is quite large。

 but we'll be looking at some of the important things and I'll point to and explain some of the important aspects here。

The player is essentially in Mario， the gist of the has a lot of the underlying behavior and functions needed for our actual character。

 so you'll see that he inherits from entity which is sort of like a base class that has an X and a Y and just a collision function and it's kind of just the overall representation for something that should move around and interact in your game and some game engines and frameworks might use entity to be just about everything or game object to be just about anything in this particular case we'll think of it as sort of like moving things that can be agents。

And you'll see that there are a set of collision detection functions。 for example。

 we have check left collisions， we have check right collisions， we have check object collisions。

 so they're also game objects in our world again I alluded to this being。

 for example the blocks that you can jump up and hit or the gems that you can collect if you were to hit one of those and they spawn a gem we want the game objects and tiles to be different because the game objects have behavior that is particular to them that is special sort of and you could also therefore put them anywhere you want in your game world and they're not behold into this static coordinate system that you have in your space and also they can be drawn on top of a tile for example。

 you might have a brick in your world that's a game object that you might want to draw on top of sky and that's not really possible unless you have like multiple tile maps which introduces complexity but you can't really have that unless your game objects are kind of separate from your tiles like your tiles if you using this sort。

we're using today and with the advantages that it has with collision and whatnot you are kind of stuck using a static tilebased system and then you have to layer on top of that to achieve some of the effects that you want。

 but essentially we have to check object collision separately from tiles because the objects using AAB collision are sort of like separate entities and you see this collides function here。

 we're sort of using the same AabB that we've used in the past and all of these things have those same functions implemented for them but this left and right collision detection function is important because it has this self dot map the player maintains a reference to the games map in in our codeb and then this point to tile function So what we're doing is we're essentially saying okay I'm going to take whatever our X and y is plus one we're doing that just to sort of shrink our hitbox just a little bit to give us a little bit of a little bit of wiggle room flexibility with how we move around and don't overly I've noticed that if you have it be two firmly set。

To your boundaries in a game like this， the collision is a little bit， it feels too constrained。

 it feels to you hit things and you don't feel like you should。

 it's better to just kind of it feels better to just kind of take a couple pixels off in the form of our X Y and then our width and height。

And so what we can do is essentially say if we're checking for left collisions， we'll say okay。

 what's the tile to the top left and the bottom left of me， which we saw in our diagram before。

 we do that by taking our x and our Y and then our bottom left for the top left and the bottom left is essentially our x and then our y plus height。

And then we can use this operation called point to tile， which if I open up the。Chao。Map。

Is just essentially there's a bound check here， just to ensure that we actually can be within our map。

 we don't want to index outside of our array of tiles。

 but what we essentially do is we just divide y by tile size add one because everything is one indexed in Lua same thing with their x and then we therefore can just directly translate pixel space into tile space into our 2D array or 2D array。

 nothing is really too fancy here， just a width and height in the tiles array much like we saw in our other examples。

 it gets populated。 there's other places where it's going actually get generated in our level maker but as you can see none of what we see here is all that different than what we've done before。

 but now we can essentially just check any particular pixel in our world convert that to whatever the tile is there adding one to account for Lewis tilebased indices and then now is the tile they're solid。

 is it not so we're moving left let's check whatever the tiles are to our left or we're moving to the right let's check whatever they are to the right' moving up。

 check whatever's above。If we're going down， check whatever's below us。

 That's effectively the just behind getting collision detection to work。

 we want to reset our x value if we end up actually colliding with something。

 which is what we do here。And then we're going to do a little trick here to avoid checking for object collisions。

 we're going to actually shift our y position up so that if we're walking and we're moving left and right。

 if we shift our y position up by one pixel just temporarily。

 check for collisions and then move our Y position back to normal。

 we can still walk because if we're walking， we're going to be right above that object and not colliding with it。

 but this allows us to just check for collisions in the event that we are， for example。

 jumping or falling and make sure that we don't actually clip into something。

And then if we actually did end up colliding with something， not in that。

View of that we're walking on top of a block， then we can actually just essentially perform a reset on whatever our walk speed by Delta time was moving left and right。

 which is how we do all of our left right movement here。And so that's check left collisions。

 check right collisions， this will end up getting called， so if I open up the play state。

We have a play state and a start state as normal。 folks might notice we have an entity states folder。

 which we'll get to in a second， and this is important。

 This is where we're going to start to tie in some of the earlier ideas we talked about with animations and the like。

 but。Here we are preserving， we have a level in our play state， which is levelmakerr。

generate 100 to 10， that's the width and the height of the level。

Folks in part of the assignment will be encouraged to increase the level。

 increase the size of the level time the level gets every time that they make it to the end of the level。

 which they have to implement the flag for， they're going to want to increase the size of the level maker。

Increase the size of the level generated by the level maker rather。

 but skipping all these states and whatnot。We can go ahead。

We see that there is an update camera function here， which just has a camera X and a background X。

 which manipulates the， again， this is the overall sort of love graphic translate offset that we saw previously。

 and then same thing for the background X as well。This is just essentially taking whatever the x is divided by 3 modD 256 so that it's going to end up slowly sort of moving to the right the duration of the as they keep moving the camera X throughout the level。

And it's going to lead to that slow sort of like parallax effect that we saw previously。

We spawn all the enemies here， the actual collision takes place in。

All of the actual individual player states， which then get called。 so if we actually go to player。

Walking state， for example。So this is a little bit of a look forward in terms of where things are actually。

 actually， we're going to talk about entities and entity states in just a moment。

 but this is just to kind of illustrate where the collision code is actually taking place。

There's going to be some amount of。left and right collisions is gonna to be checked and certain things are going happen depending on which state we're in。

 but ultimately these defer to the checked left collisions and check right collisions if we're moving left and right because these check left and check right collisions will occur if we're walking if we're jumping if we're falling they kind of are like they transcend any individual entity state or yeah any individual entity state and so here is where they end up getting called or ultimately this walking state gets updated within the play state and then as a result we can sort of like isolate our entity behavior a little bit but have general functions that allow us to do calculations and collisions that are going to occur across multiple states and so that's sort of what's happening here now I'm sort of getting ahead of myself a little bit。

 And so I think now it's a good time to maybe look at for example。

 what an entity state is and what we've been sort of alluding to and what that essentially is we have to sort of。

about what entities are to begin with， and so an entity is just something that has an XY。

 it does behavior， it interacts in your world， people have different definitions of what this is。And。

The benefit of having entities is that they can be sort of like generalizable in a sense that you can isolate certain types of underlying shared behavior and ideas。

 for example， every entity has an X and Y， every entity has a width and a height。

 every entity has some sort of collision detection capability therefore with another entity assuming that everything is access aligned and depending on your game。

 this might be even more behavior than this， but then you can instantiate things that inherit from those behaviors sort of just classical objectoriented inheritance in our model and then have these sort of like more specific types of entities。

 for example a player is an entity that we just happen to be able to steer。

 a snail is an entity that is going to be able to target the player with its own states and what's cool is that we can also think we can build on this idea and think of entities as a container for sort of these behaviors that now we can visualize in the same way that we visualize game states as being these containers for what it means。

To be in a particular part of the game， we can envision the entities as being their own state machines that are engaged in a particular behavior。

 which we actually had seen in previous lectures， we saw the overall diagram of like Mario jumping and doing all these different things and that's essentially what an entity can do is it'll have a maybe an idle state。

 for example， in the case of our character which then if you were to move left or right。

 this is going transition you to walking， you're now walking andre now in that state。

 but if you were to press spacebar you could go from that state to jumping you could go from idle to jumping as well。

 so now you can sort of go to that state through two different mechanisms and then by just letting go of input。

 for example while walking， you go back to idle if you get hit maybe you go into a death animation or something and this is in the same way that game state can be taken from these sort of like convoluted if statements and whatnot as this sort of branching behavior you can just encapsulate these in a state machine and then on your entity。

On your player on whatever entity， just store a state machine that holds all of your states。

 and then all of these states can then be updated one at a time and then rendered and interacted with in the same way that we evolved our implementation of the game state machine。

 we'll do the same thing with entities。And then one other piece that we should look at is game objects real quickly。

 let's look at what the entities look like before we do that。So again， the entity。

 if we transition here。Is just essentially a wrappper class， so I'm going to go ahead。

Close all of these。Game object is also rather a wrappper class。

 but we have an entity folder for states， but if I were to go to just the base folder。

 we have just this entity which takes in a def， you'll see it has a position and a velocity。

 most any entity we've ever interacted with in our games all have an X and a Y and a velocity and a width and a height。

 they'll all have a texture， they'll have a state machine they are going to have a set of states。

 a direction， a reference to the map so that they can actually see other aspects of the map and the tiles and whatnot they want to interact with。

And then the level itself， which is going to have the we're going to have a game level object which contains all of the game objects。

 entities， and the tile map。So through that， we can then see a few functions here。

 we've got to change state function， which is very similar to that state machine that we had previously。

The same type of function actually we're using literally the same state machine class for this。

 except that now we are instead of having our game state objects。

 there are classes that we're implementing with update， render， En， exit and all those things。

 we just do that for every entity we want to model if we want to model a snail。

 a snail' is going to have an update an idle state， a chase state。

 the player gonna to have a jump state， so on and so forth。

You get to have ultimately quite a lot of different states， depending on what your game。

 how many creatures and whatnot you have modeled in your world。

 and so there are ways you might seek to try to reduce the amount of code。

 explicit code for that and use what might be called like data- drivenriven design to do this which might explore a little bit as we get to the Pokemon lecture for example。

 and even Zelda's lecture， but for right now we can model these in code with classes， the snail。

 the player， whatever creature you could imagine adding， and then as a result。

IfWe think of these in terms of states， much like we saw previously with the game states。

We can just create a new folder in this case， just entity so we've separated our states sort of semantically between game states and entity states within the entity states。

 we could have probably put this in a player folder。

 but I just put that in in the base folder because this is sort of like probably the more important for the sake of lecture set of states。

 but we also have a snail folder here to separate the snail states from the player states。

 but you can see the player walking state is going to encapsulate all the behavior of what it means to be walking so if you're holding left and right。

 you're going to want to check your left and right collisions while you're walking and ultimately it's pretty simple the one key thing is that if you're not pressing left and right but you're in walking again we need a way to move between states so we're going to want to change our state here to idle instead of to instead of keeping us in the walking state。

And then also， if we press jump， we want to go into the jump state because you can jump while you're walking。

 you don't you're not just limited to jumping while you're idle。If we go into the idle state。

You'll see that if we press left or right， we'll go into walking and then if we press space we'll jump。

 so kind of the same idea。If we're in the falling state。

 so falling just means that gravity is positive and our wipe and we're not like on the ground。

 so if we end up going here， we'll see。If if we're in the falling state and then we actually collided with the ground what this particular thing is checking for。

 we're going to want to immediately go into walking。

 else go to idle so essentially if we're falling and we hit the ground。

 we're going again we check for point to tile below us。

 set our y position up to a little bit so we're statics that are d to zero and then we can just immediately change to whether we're walking or idle depending on whether we're already holding left or right。

 if you don't do it if you're not doing this check here and you jump and you're holding left or right。

 there will be like a frame where your character is in the idle state and it feels weird。

 it's clunky， so you want to just go right into left or right or idle。

And then in this particular instance， too， this is where we actually have the death。

Sort of condition for the game like if you in our particular game， there's really only one way。

 well there's two ways to get killed and that's to fall below the edge of the ground or to let a snail touch you while you're on the ground and so this is one of those instances which is that the G state machine will change to start which again this is for our global state machine is our game state machine。

 we're going to check to see whether our y is greater than virtual height。

 meaning that we're below the map， we've sort of arranged the map such that it's right we're always rendering it above where that virtual height limit is so if we just essentially go below the map falling into a chasm the game will go back to the start state which is at the very beginning of the game that we saw。

And then here we also have some consumable code， so whenever we're falling or we're walking or we're jumping。

 we can collide with consumables in the world， which are game objects。 we've looked at game objects。

 Why don't we transition to that and just have a little brief talk about what game objects are So game objects are you could in theory put these together with entities in a way just mark entities that are non。



![](img/67713fb931a2f422757f860cc32b6d07_100.png)

NoThey're not agents， they're not moving around， they're not doing anything that's sort of representative of some sort of sentient thing。

 but in the case of our game， we're going to say that game objects are this class of item or object that is interactive in the sense that you can collide with it or you can hit it。

 and it will maybe do something for you but it's not an entity， so it doesn't have states。

 it doesn't do all of those things。And so game objects are perfect for things that are relatively static but should have some behavior that triggers when you interact with them or touch them or do whatever。

 and in this case， the gems here are game objects， as are the blocks when you actually jump up and hit those because those have a behavior that behavior being that when you hit the block。

 a gem has a chance to spawn up and come up and then be claimable。

 which is itself a game object so the block can spawn a game object itself It's an game object that can spawn a game object。

 and so we've differentiated between these and you'll see these commonly depending on which environment you're in which engine you're in。

 some engines will use。Game object to be literally anything， including an entity。

 some will separate them， some will just have entities and they will use what's called an entity component system or ECS where literally you just have everything as an entity and then it contains its behavior not through inheriting from some base class and then getting more specific but rather just having some sort of component within it that determines its behavior and then in order for all entities to interact they just iterate through all of their components and then just their behavior is sort of emergent as a combination of all of their interacting components。

 those are called entity component system， unity， the engine is an entity component system。嗯。

As an illustrative example。So。That brings us all I think also to the topic of power up。

 which is essentially just a game object that you could think of as just affecting some sort of state on the player。

 so in this particular example we use a gem but you could decide to implement a power up for example。

 that the gem in our example just improves your score but you could decide to increase the size of your character or to turn your character invincible which will be part of the problem set so this will be relevant for the problem set。

 have a star， have some sort of object that the player can touch maybe it has a chance to spawn from the brick instead of the gem and then particle effect should happen。

 maybe a rainbow effect on your character and then right now when you walk into a snail。

 you will just die if you're not jumping if you're not falling rather but you should ideally if you were invincible。

 be able to just touch the snail at that point which is very similar to what Mario gets to do in the game when he gets a superstar and then defeat the snails that way So let's take a look now at how game objects are implemented。



![](img/67713fb931a2f422757f860cc32b6d07_102.png)

In our code。If we go ahead and transition over here。

I'm going to close out the so actually this is the perfect place to show it。 So in our world。

 we have a game level as sort of this container for。😊，Because we want to have game objects。

 Anaat tile map and entities all together as sort of this trifecta of things that interact together。

 we're going to put those into what's called a game level which is this container for all three。

 so if I open up game level here。You'll see it literally just has entities， objects。

 and then a tile map。And then what this does is we can just say， okay。

 we can just iterate through all the objects if we need to or the entities to see which things collided with each other。

 the tile map again， we're doing point to tile operations for collision。

 so we don't have to worry so much about that， but all the objects can therefore when we do collision code depending on which state we're in with the player。

 we can iterate over each object and determine okay are we colliding with it if we are。

 is it consumable meaning did we give it this flag called consumable and then a function maybe that can trigger an anonymous function as we've seen。

 that will do some behavior that affects the player or the map or so on and so forth。

If we go to game object， we'll just take a look at what that actually looks like a game object is essentially a shell in the same way that an entity is。

 except a game object expects a set of things that will trigger depending on how it's interacted with in our world and we're sort of arbitrarily choosing。

How to differentiate and which things it can have and which flags it can have。

 but this is similar more or less to what you might expect to occur in an engine where you have an oncollide or onconume callback or function that will trigger when your entity or when some entity that is flagged to be capable of consuming those objects indeed does consume those objects for example。

 the snail isn't set up such that it can collide with or consume gems or power ups or whatnot。

 but you can envision a world where maybe you do have enemies that are vying for resources or vying for power ups and then maybe they can also collide or with interact with or consume these items and so we have that ability should we choose to do that through the functions defined on each entity state。

 but as you can see the game object is a very simple function。

 it just has its ability to render itself effectively and collide with another target which is assumed to have an accessalign bounding box and it doesn't even have anything set up an update。

useWe don't have any objects currently that should update or any logic for that。

 but you could very easily extend this to some kind of an uptable thing you could have maybe game objects that animate or game objects that move around and do various things technically a coin for example。

 is going to have some sort of typically in a game it's going to have some sort of like oscillating y position maybe maybe some sort of sinusoidal movement in that way and you could put that in update if you wanted to。

 something like that and maybe that's based on a flag that it has set in the game object well we're mostly concerned about with is it's collidable。

 consumable oncollide and onconsumed flags which。If we go into the level maker。

 this is where all of that is going to end up being created。

 so recall that we showed a very simple version of a level。

 how to create a level previously in our example， so level zero level1 where we just had chasms and whatnot。

 but when we're doing a full proper level here we're going to want to not only maybe add some props。

 which will be game objects that are just not collidable which will just render them wherever we place them。

 but we're going to want， for example， gems that are consumable and collidable for our score we're going to want the blocks so when we jump up and hit them。

 they might spawn a game object or they might spawn the game object that is a gem that then is consumable。

 and so all of those things need to be determined sort of in advance。

 and we do that through a iteration of the level maker class。

 which is sort of in spirit to similar to what we did in breakout we had a sort of like level creator there as well。

You'll notice that in some ways it's going to look very similar to the level maker that we were using in our previous examples and just the test code or sort of the leadup code。

 but we're actually now doing quite a bit more。If we scroll down here。

 we're doing all the usual chance to be empty， chance to lay out space。

 chance to be pillars and whatnot， but when we generate pillars， we can， for example。

Generate a bushha pillar， which will just be， you know we even saw an example of that in the screenshots where we have this objects list。

 this is going to be returned。 We're going to return a game level from this level maker and recall it has the objects。

 the entities the tile map so objects are going to be separate from tiles so we're going have a chance to generate one in eight on top of a pillar just if we did generate a pillar。

The texture， the game object expects a texture so the game object will know to index into whatever the right texture is。

 it'll know which quad therefore we should by quad will be it'll be the frame key here and it'll just be a random this gives just a random bush in this case from the list of possible bushes that are there the spreadritesheet has a ton of different varieties and colors and things so wherever possible we've added some randomization but essentially it will just be offset based on the top of wherever we are in our list of remember it generates that index4 so we want to shift it minus1 so it's on top of that fourth that fourth tile。

But then they have it just has a width and a height， it's going to be able to draw itself。

 it's not collable， it's collable's fall， so our character will just like when it queries all the game objects that it can collide with。

 itll just bypass check and collision on it so it'll just go in front of it。

And then this is just an example of like a static game object that just essentially is a glorified sprite renderer。

 but if we come down， for example， past this other bush example to the jump block example。

 which is the more complicated game object in the distro you'll see in a lot of ways is very similar to everything else。

 it has a texture and X and a Y a width and a height a frame。

 it just can be a random jump block we saw in our example， there were lots of different objects。

 lots of different game lots of different jump block tiles for it to choose but notice that we have collidible is true。

 so it will perform collision detection when we check check object collisions in our player class as the function。

 it its going to have a hit flag that's false so if it's been hit already we don't want it to generate a gem or do its chance to generate a gem for example and you might render this with a different texture in theory we didn't go through the paint to do that in this but could for example in Mario。

 the actual game if you hit a block that's got a coin in it typically what happens is it starts off yellow。

And then it goes into some sort of like faded color after you've hit it to show that you've hit it。

So solid is true， meaning that it actually has collision detection it pushes us outside of it。

 you can be collidable and technically not be solid and still like the collision will trigger。

 but you won't actually get pushed outside of it。On Colllide is the actual function that's going to trigger when we hit it and so what this means is that essentially if we imagine that on Colllide gets called at the moment in this case it's when we jump and we hit it so on Colllide will only trigger in our code we're going to specifically trigger it when we actually jump。

If the object has not been hit， we're going to have a random chance to then spawn notice another game object to actually trigger and this is all also by the way。

 in an anonymous in of function， an anonymous function， it's getting a standarded label on collide。

 I guess it's not completely anonymous， but effectively is anonymous in that we could set this to something else later if we wanted to and swap this out。

 but on collide is essentially this function that's going to trigger later。

 will'll trigger on collide， it's going to 1 in 20 or 20% chance generate a new game object。

 and now it's the gem so it's going to be the gem it's going to end up setting itself up to above the actual block。

which we do here， we actually take the gem itself， we're using timer do tween。

 which we saw last week， over 0。1 seconds， we said it's y to be equal to the block height minus two times tile size。

 which will end up shifting it up above the actual block height。

And then we're going to play a power a power up sound。

 And so is this is a sort of way to tighten in one of the things we saw last week。

 which is this idea of smooth movement。 So when we actually hit it。

 we're going to actually spawn the block with a sort of like interpolated Y movement so that it's like the smooth movement versus just like instantly oh。

 there's the gem noticeice it's got a consumable is true。

 it's got an unconsume function call back here which assumes that it takes a player and an object we'll play a sound here。

 when we do that to show that we've picked it up and then we're going to increase our score by 100 and then in our actual check object collision function is where these sorts of things get handled in our player if we go back to player here。

If we go to check Object collisions。This gets called across various different states。

 across our jump state， our fall state， our walking state， because all of those different states。

 you can consume a gem or whatnot in all of them， you can be jumping， you can be falling。

 you can be moving。Just not idle is typically where you would not be consuming unless you had movable consumables。

 then you would want to add that to your idle state because it could move into your hitbox in theory。

 but as you can see，Every time we call this check object collisions function， we're going to。

Do a check for whether we've collided with it， which is just the AABB collision detection。

If it's solid， we're going to insert it as being a collided object that we've collided with。

 and then if it's consumable， what we're going to instead do is we're going to actually call that on consume function。

 object onconume， we're going to pass our as the first argument， then object itself。

 and then we're going to remove from the actual objects inside of the inside of level dot objects。

 we maintain a reference to self。 levelve dot objects as the player so the player can do these sorts of operations。

We're going to then remove it from the table so that it immediately gets taken out of the world so that we no longer see that anymore when it does the loop to render over all of our game objects。

 it'll no longer be there， it'll be completely gone。And again。

 this occurs throughout all of the various player states that we can and potentially consume a game object or collide with a game object within I think the last thing that I'd like to look at in order to illustrate sort of what some of the stuff we've talked about is the snail states。

 which we haven't looked at， the snail sort of being this entity that exists sort of that gets spawned at the level maker creation time again based on a random chance。

 just like the game objects are spawned。It's going to have an X and a Y。

 it's going to be placed on a particular tile， but these have their own states。

 so notice that it has an idle state。So in the idle state。

 what's kind of cool is that it has its own animation it's just a single frame of it being in the shell。

 which is kind of just a cute thing， and then its behavior is such that essentially it has a weight timer or a weight period where it will decide。

 okay after that weight period I'm going to change my state to be either moving or chasing and chasing is just essentially if the difference between the player's X and the snail's X is five tiles or less it will set to be chasing the player。

 which just means wherever the player's X is go towards that X， which we can see here。

 snail chasing state。These these states， by the way。

 are instantiated and they take references to in the case of the snail。

 the snail needs to have a reference to the player always。

 so when these states get defined initially they all get the player as a reference to them。

 so this is important if you have any operation that you need to take place within your world between your entities or the player often the most expeditious thing to do is to just pass in a reference to the player or the map。

 assuming that you don't have just this gargantuan list of things and to try to have these sort of highlevel relationships between things in an ideal sense you want to limit as don't do too much of this between things that don't need to talk to each other but sometimes the cleanest easiest way to actually get things to talk to each other is to have them passed as references and held and shared between them。

So here we have a chasing state， it just always will be looking to see basically is the difference between R X and the players x5 tiles and if so like keep moving in that direction。

 otherwise there's a chance for it to or keep essentially moving left or right based on where the difference is whether it's left or right or change it to be just moving。

 meaning that the moving state essentially just chooses a random destination。

 so if we go to here to the moving state we'll see。

That the has a moving timer which is just going to be。

 you know here it's just flipping a coin left or right to this initial it's initial moving direction。

 but it'll always be doing that essentially every time we end up deciding that we should choose a new direction。

 it'll be based on just the same kind of timer as the weight timer was where we just decide， okay。

 after X period of time， I've been moving to the right。

 let's move to the left instead or let's keep moving to the right or whatever the coin flip decides。

And then there's a one in four chance for it instead to just go idle for a little bit just to mix up behavior and this is essentially how you can get some interesting sort of like lifelike you know sort of like fake lifelike behavior or some interesting interaction in your game without going too crazy That's the justist behind overall most of the objectives that people will need for the assignment if we transition here essentially assignment for is that we should。



![](img/67713fb931a2f422757f860cc32b6d07_104.png)

First off， I don't think we had a chance to even see that it happened in our testing。

 but right now there isn't really a cap on the player falling or rather there isn't really an assurance that there's going to be solid ground beneath the player when they fall so you're going to want to do that just is an easy initial thing to also get people used to the level maker code。

The key and lock are in the sprites sheetet and these are cool， they're different colors。

 folks will have to choose between one color of the key and the same color of a lock。

 which will open up the end goal， so this is just to get people used to using game objects。

 so the key will basically enable the player to interact with the lock such that it'll unlock the goal existing at the end of the game level。

 meaning that the flag should then spawn。That or folks can choose if they want to to spawn the flag just in a state that is empty or not functional。

 either way the lock has to open the flag has to make it accessible。And then once they do that。

 once the player touches the actual flag at the end of the level。They should generate the next level。

 so right now there isn't really a way to transition between levels but take the level that you're in right now and then just generate a new level and then make sure that it's just a little bit bigger than the level that you're currently in。

Additionally， folks might have noticed on the actual sprite sheet。

 there's a animation for the character to climb up a ladder and there is a ladder as well。

 so the next part would be to generate pillars that are higher than4。Tiles tall。

 so something that the player cannot jump over currently they can just jump over pillars。

 but we're going to make it such that maybe generate it one or two tiles taller so that you can't actually or jump over it and then add a ladder to the side of it so that you climb the ladder instead get to the top of the pillar and then jump down or fall down this implying that you'll need of course a new state。

 a ladder climbing state in order to and therefore model the model the ways that you get out of that state in order to allow this to be possible and therefore allow you to sort of climb on the Y axis sort of more arbitrarily。

And then also the last thing would be， which we alluded to briefly， a power up。

 so right now we just have gems， you can interact with the gem to increase your score。

 but folks should choose like a star or something else that will allow you to become invincible and then therefore interact with a snail if you're just walking for example。

 and have some sort of particle effect folks maybe can even add music if they want to which is what Mario does。

 but add a particle effect of the likes to set when you're walking into a snail then with that new invincibility mode on the superstar mode on you defeat the snail without having to jump on top of it and it does not affect you。

 you are invincible。So that was it for Mario next time we're going to do a few things in like kind of a similar era which is Zelda。

 which is one of the first game that I remember playing which is the Super Nintendo legendgen Zelda linknk to the past in this case we'll do a simple example even included the hearts in there but so far we haven't really done a top-down perspective type game so we'll explore how to do that movement into axes therefore left and right。

 a little bit different than platformsers with gravity but in some ways simpler and we'll be looking at a few other cool tricks like stencling triggers and events will be important as folks might be able to see there is a switch on the ground there。

 a bunch of enemies also all moving around and interacting we'll taking a look at that sort of basic AI type stuff which is kind of an extension of what we did today。

But there's a sort of set of doors around the side of the level there folks can hit the switch that will trigger an event which will then open the doors。

 those will be listening to an event。That gets fired that then will get handled through a function that will open the doors and then folks can then move through the dungeon and then go to another randomly generated room with switches and doors and then also really key folks will be able to actually swing a sword and inflict damage and that's going to require the use of a hurt box and then lastly in particular in relation to the problem set we'll be exploring the idea of inventory and how to model that in order to show how to for example。

 acquire and use a boomerang to attack enemies from a distance So that was Mario it was probably one of my at least more favorite lectures in terms of I really like the idea of these virtual worlds that we get to explore and use tile maps to represent that there's a lot of things we just introduced game objects and entities and all these things but I think it sets the stage for a lot of really cool things coming forward。

 so we look forward to that next time This is CS52D Super Mario we'll see you next time。



![](img/67713fb931a2f422757f860cc32b6d07_106.png)

![](img/67713fb931a2f422757f860cc32b6d07_107.png)

Hello world for those folks still tuned in this is just going to be essentially a fix for the first week where I blundered and did not properly put a couple of slides on the first lecture so I'm going to be transitioning back to Pong for a little bit just doing a little bit of a closeout for that so in case folks see that and are' like oh that doesn't make Mario why do they get rid of Mario that's the reason why so should just be just a couple of minutes fingers crossed but yeah thanks for tuning in。

Yeah。So with that we've covered a lot of ground， but that brings us ultimately to our very first assignment in the course which is going to be you so far we've used just the paddle on the left and the right。

 they're both manipulable by their arrow keys in WasSD so one player gets to control both of them ultimately that's not quite conducive to an ideal implementation of Pong so the problem set for the very first example。

 it's somewhat well containedtained I think for just a starter problem set。

 but it's going to essentially be adding a very basic version of AI such that the paddle on the right side moves on its own in order to play against player1。

 so player one will retain its ability to move up and down but player two will now be controlled by the AI through some sort of update process up to the implementer's discretion but ultimately how balanced or not you want to make it up to you as long as it behaves and plays in a manner such that it suggests an actual AI is responsible。

So next time we're going to transition away from the world of just shapes and simple colors and whatnot and take a look at our very first images。

 so as a spoiler this is next week is going to be flappy birdsd are' also going to go a little bit into the future so we're going to look at images we're going to look at the idea that transcends just this particular next lecture but applies to kind of the whole course which is that games are illusions sort of in various ways and we'll look at how that applies to this sort of fake world or fake scrolling we'll be seeing with flappy birdir。

Which is part of the problem as well， part of the lecture as well。

 which is this infinite scrolling we'll be doing。We'll be looking at a very basic initial teaser about procedural generation。

 This is really ultimately just kind of a randomization of these infinitely spawning pipes that are going to be moving through the game as we'll see。

 which is the ultimate obstacles shown by the image here that you're supposed to dodge in the game but importantly we'll be looking at state machines as well and a way to clean up what we did in this lecture which is just that we had essentially the conditionals in a string variable with game state that was just going to determine what we could do or could not do at any one given time。

 but we're going to find a way to abstract over this in a lot more elegant of a way that lets us decouple our state separately from each other and then finally because it is a mobile game I think it's fitting that we look at a little bit of mouse input to sort of tie things together at the very end so this was CS22D lecture 0 pong which we did cover a lot of ground there's a lot of very fundamental important things that we looked at today even just the basis of drawing shape sets us up for next week but we'll see you next week with lecture1 into more of a modern era with flappybiird。



![](img/67713fb931a2f422757f860cc32b6d07_109.png)

Next time。

![](img/67713fb931a2f422757f860cc32b6d07_111.png)