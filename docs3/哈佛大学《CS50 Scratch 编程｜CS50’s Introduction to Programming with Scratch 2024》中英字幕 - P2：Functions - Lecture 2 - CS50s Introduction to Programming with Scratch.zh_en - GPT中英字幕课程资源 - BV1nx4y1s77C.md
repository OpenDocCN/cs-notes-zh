# 哈佛大学《CS50 Scratch 编程｜CS50’s Introduction to Programming with Scratch 2024》中英字幕 - P2：Functions - Lecture 2 - CS50s Introduction to Programming with Scratch.zh_en - GPT中英字幕课程资源 - BV1nx4y1s77C

![](img/cdffe696599eac69766638fe7d1181ce_0.png)

Welcome back， everyone to an introduction to programming with Sc。

 And last time we introduced the world of scratch， introducing the stage and the sprites that can live on that stage and saw how we could change the way those sprites looked by giving them costumes give them some sounds and also add some backdrops to our stage to make it look a little bit more interesting。

 But everything we were doing last time had to be done manually by ourselves。

 If we wanted to move the sprite， I had to change the X and y values and drag the sprite around into a different position。

 for example， if I wanted to change the costume。 I had to click on a different costume that I wanted to do。

 This time， we're going to start programming our scratch projects。

 adding some code so that we can let that code run and manipulate what happens inside of our scratch projects as well。

 So let's start to take a look at how we might be able to do that by opening up a new blank scratch project。

 And when we do so， we'll see the stage which is pure white by default and the default scratch cat that's here as well。

 Now， remember from last time， if I wanted to move the scratch cat。 I had two ways。😊，Of doing it。

 One was to click and drag on the cat and move it around the stage to wherever I want the scratch cat to be。

 Or secondly， I could use these x and y values down here。 I could change the x value to0。

 and the y value to0， for example， to perfectly center the cat inside of the stage。 But this time。

 we're going to start to introduce these blocks that have been living on this left side of our scratch window for some time now。

 but we haven't really done very much with just yet。

 And each of these blocks is going to perform some task some action that's happening on the stage of our scratch program。

 And we're going to start to call these blocks functions。

 a function in the context of scratch is just some block that performs some task。

 And we might look at this very first block， for example。

 which just says move 10 steps And that is a block， which， as you might guess。

 has the effect of moving the cat10 steps。😊，And so let's give it a try， How could we use that block？

Well， if I want to use a block as part of my project。

 I'm going to start by taking that block and dragging it into the code editor in the center part of the scratch interface。

 So on the left hand side is really just this library where all of the blocks live to begin with。

 But if I want to use a block in my project， I'm going to take the move 10 steps block and drag it out into the main part of the scratch interface and just drop it off。

And so now I've added my first block of code， my first function into my scratch project。

 And to run it， I can just click on it。 So watch what happens when I click on the move 10 steps button。

 notice that right now， the scratch cat is right in the middle of the stage。

 But as soon as I click the button。😊，The cat moves just a little bit。

 You'll notice it moves slightly to the right， and you'll notice， too。

 that the position of the cat changed Orin， it was at 0，0。 Now， x is 10 and y is 0。

 We've moved the scratch cat a little bit。 And if I click it again， I can keep moving that cat。

 And every time I click it， the cat moves10 steps to the right。😊，Notice， too。

 that in this move 10 steps block， theres a bit of an empty gap here where we filled in the number 10。

 This is what we can call an input to a function， functions that are allowed to take inputs。

 information that those functions use in order to decide how it is that they're going to behave and the input that this function takes is a number indicating how many steps we would like to move。

 So in this case， the input is 10， meaningan I would like to move 10 steps， but I could change that。

 I'll drag the cap back out to give it a little more space to move， but I could change this input。

 for example， to 30。😊，And now， when I click on this block， the cat moves further。

 You'll notice every time I click on it， the cat's moving 30 steps instead of 10 steps。

So I can control based on this input how far the cat's going to move， and if I make it negative。

 say negative 20， now， every time I click on the cat， the cat's going to move backwards。

So you can decide based on what number you write here in what direction that cat is going to move。

So this is just one block， one function that we can use inside of our scratch project。

 But there are others as well。 Here's one that is says turn 15 degrees to the right。

 turn to the right or clockwise of 15 degrees。 So if I want to use that one。

 let me try dragging that out into my block editor。 I now have two blocks。

 the move 30 steps 1 and the turn 15 degrees to the right one。And if I click this one。

 the turn block， you'll notice the scratch cat turns Every time I click on it， it rotates。

 changes direction by 15 degrees。 and I can keep clicking on it。

 turning it little by little until we get back to。The original，90 degrees。

So now I have two different blocks， one block that causes the cat to move。

 and one block that causes the cat to rotate。And it turns out I can combine these blocks together。

 often when you're writing programs， it's not just going to be one instruction that you want your program to follow。

 but it's going to be some sequence of instructions that you want your code to follow。

 And so these blocks can snap together。 Watch what happens if I take this turn 15 block and I drag it close to the move 30 steps block。

 you'll notice that it starts to highlight。 And then when I release my cursor。😊。

The block just snaps into place。 These two blocks are now connected to each other inside of a stack。

 which we can call a script。 And now these two blocks together。

 will run together when we run this stack of blocks， it's going to run from top to bottom。

 running the first block， which is move 30 steps。 and then the second block。

 which is turned to the right，15 degrees。 So when I click on it， watch what happens。

 The cat moves 30 steps。 But it also turns by 15 degrees。 and I can click it again。

 and that'll happen again。 And if I keep clicking it now you'll see we've got this cat moving in a nice circle。

 It's moving forward and it's rotating every time。 And I'm doing so by every time I click on this stack。

 running both of these blocks of our code。😊，And so by combining together these various different blocks。

 we have the ability to create more interesting programs just by deciding in what sequence top to bottom we would like for these blocks to ultimately run in。

 and there are all sorts of other different motion blocks that we can use noticeice that the scratch blocks are all organized into categories and those categories are color coded and all of these first set of blue blocks they're all related to motion。

 the movement of the cat。😡，So there's one block called go to random position， that one looks fun。

 I'll try it。 and know every time I click on this block。

The cat just moves to a different random position every time。And maybe that's interesting。

 but maybe I don't really want the go to random position block as part of my program。

 So if ever you decide， you know what， I have a block， and I really don't want it。

 there are a couple of ways to delete a block in scratch。 One way is you can control。

 click or right click on the block。 and you can just click delete。 That's one way。

The other ways is I can take the block and just drag it off to the left。

 put it back into the library。 And then when I release， the block goes away there as well。

So using this ability， this ability to now move our sprites around just by writing a little bit of code by putting some blocks together。

 let's now try and create a program that does something。 I'm going to use a different sprite。

 Let's not use the cat。 I'll go ahead and delete the cat by pressing the trash can icon next to the cat。

 but I'll choose a new sprite。 Let's go to animals。 So I have a few different options。

 And I think I like the hedgehog。 We'll go ahead and use the hedgehog。

 And what I want for the hedgehog to do is just walk around the entire stage to walk in a rectangle effectively。

 And so let's assemble together some blocks to let the hedgehog do just that。😊。

I want the hedgehog to start in the upper left portion of the stage。

 And so that's about this x value and about that y value。 And I can be even more precise。

 You'll notice that the go to block， which is a block that just goes to a particular position。

 will by default include the values for wherever the sprite is currently。 So right now。

 it's negative 168 and 120。 I'm going change this slightly a negative 180。

 just to make the number a little cleaner。 But now this block。😊。

We'll move this hedgehog to the upper left portion of the stage。 And now。

 if I wanted to go to the upper right portion of the stage。

 I'll use the go to block again and remember that to control the left or right position of any given sprite。

 I can change the x value。 The X value controls whether it's to the left or to the right。

 Neative means to the left。 Pos will mean to the right。

 So I'll go ahead and change it to positive 180 and then y equals 120。

 So it starts at the upper left and then goes to the upper right。And I'll add one more after that。

 And I want to move it now to the lower right。 I want to sort of make a rectangle all around the stage。

 And the lower right， Well， that's gonna be a positive x value。 So I'll do positive 180。

 But now a negative y value。 Y controls how far up or down。😊，The headho is going to move。

 and I'll do one more。With negative for both negative 180， negative 1，20。

 that's gonna be the bottom left because the x is very negative and the y is very negative。

 And so what I hope this will do is cause the hedgehog to just move in a rectangle。

 Go to all four corners of the stage。 So I'll try it。

I'll go ahead and click on this block and see what happens。Alright。

 It didn't do exactly what I expected for it to do。

 The hedgehog just jumped immediately to the lower left。

 even though the lower left one is this last instruction here。

 it seems to have skipped these two in the middle that tell it to go to the upper right and then to the lower right。

So what's going on。Well， it turns out that when a program is running。

 the computer can run our program very， very， very quickly。

 So even though our program was going through each of these four lines one at a time。

 it happened so quickly， it went to one location， then a second location， then a third location。

 then a fourth location that we， the human looking at this project。 Only ever saw the final location。

 We missed all three of those locations that were in between。😊。

And so sometimes if I want to be able to see what's actually happening in a project。

 I need to tell scratch to slow down a little bit。 Don't just immediately go to a particular position。

 but take some time in getting there。 And scratch's word for this is to glide。

 And so what you'll notice is that in addition to just the go to block。

 that immediately jumps to a particular location。 I have another motion block called glide。

 And this one takes three different inputs。 This one by default says glide one second to this X value And that y value。

 And I can use that to say， takes some amount of time to go to a particular position。

 And let's try that out。😊，I'll head over back to my block editor。

 and I no longer want these bottom  three blocks。 I would like my starting position。

 but these other three， I'm going to need to change them。 So I'll take them。

 drag them over into the block library to delete them。And let me now bring out a glide block。

 Let's take one second to glide to x equals 1，80。 Y equals 1，20， both positive。

 That's going to be in the upper right portion of my stage。😊。

Let's take one more second to go to positive 180 for x and negative 120 for y。

 that's to the right and down。 So the bottom right portion of the stage。

 and let's take one more second to glide to negative 180 negative 120。

 which as you can see here where the hedgehog is now， that's the lower left corner of the stage。

 And if ever you're confused about what those numbers mean and where you are。

 you can just drag the hedgehog to the location where you want it to be and you'll be able to see what the x and y values for that are actually going to be。

😡，So now let's try to run this script。 I can do that again just by clicking on the script I want to run。

 and it will run them in sequence。 We start in one corner。

And we work our way in a rectangle back to the other corner。

 And if I wanted to end up back at the starting point。

 I can add one more glide and let's glide back to negative 1，80 and positive 1，20。 that's moving up。

 And so now， when I click on the hedgehog， it moves in a rectangle。😊，All around the stage。

And so we've been writing programs now just by putting these blocks in sequence。

 deciding what we want our sprite to do and then clicking on those blocks to run them and to see our project in action。

 And now at this point， our project starting to get a little more complicated。

 And if I come back to this later， I might not remember exactly what I was trying to do with these blocks I might not remember what all these numbers represent And so Scrach gives you the ability to leave comments on your project。

 just little sentences， short descriptions of what it is you were thinking and that's helpful for two reasons。

 It's helpful number one， if you come back to your project a little bit later and might not remember exactly what you were thinking you can use it as a reminder and it's also helpful if someone else is reading your project they're looking at the blocks that you used and they want to understand why did you create the project this way。

 you can use comments to explain as well。I can add a comment just by right clicking or control clicking on my stack。

 And I'll add a comment。 And here in my comment window， I'll just say these blocks move the sprite。😊。

In a rectangle。 This doesn't affect how the program actually runs。

 It's just a little comment that I can collapse that offers a reminder。

 some text that you can read a little bit later to understand what exactly was going on。

So that then is what we can do with motion blocks。 And there are other motion blocks to for changing what direction the sprite happens to be pointing in or moving only in the X or only in the y direction。

 And you can explore some of those options for what you can do with motion blocks。

 But let's now take a look at some of the other categories of blocks that we have access to as well。

 I'll go now to the looks section。 Notice that these are in a different color for a different category。

😊，And here， let me drag out this， say hello block， which looks interesting。 I'll drag it out。

 and I'm not going use these motion blocks anymore。

 So I'll get rid of them just by dragging them away。So now I just have this one， say hello block。😡。

And let me move the hedgehog to the center just so we can see it a little more easily。

 We'll move it to x equals 0， and y equals 0。If I click on say hello， watch what happens。

 A little speech bubble appears next to the hedgehog， and the hedgehog is saying hello。

If I wanted to say multiple things， I could stack multiple of these blocks together。 Let's say hello。

 and then say。Goodbye， for example， and see what happens。 I'll click on it， now。

I'll click on it again。Notice that， again， we seem to have run into a similar bug， a bug。

 some problem with our program that we're going to need to fix。

 I wanted for my program to first say hello and then say goodbye。 But every time I click on it。

 it's just saying goodbye。 And the reason is exactly the same thing that we saw a moment to go with the hedgehog moving around the stage。

 It's that scratch is running through these block so quickly。

 that we don't get time to see the hello， we just immediately see the goodbye。

 So if we want to see the hello for some time， we're going to need to tell scratch to stay there for some number of seconds before moving on to something else。

 And there's a block fortunately that will do that for us， which is this one here。

 sayy hello for two seconds will have the effect of saying hello。

 but rather than immediately move on to the next block。

 it'll stay there for some amount of time that will give us a chance to read what it is that the hedgehog is actually saying。

😊，So let me delete these blocks， dragging them off into the editor and replace it with。

 say hello for two seconds。And then if I want another one， I'll drag another block out。

 This one will be say goodbye for two seconds。 These are stacked on top of each other。 So now。

 when I click on these blocks。The hedgehog says hello。

 and then the hedgehog says goodbye for two seconds as well。

 So we've been able to fix the bug that we've been able to create here。😊。

So now looks can affect not just what the character is saying。 You can get a speech bubble to appear。

 You can get a thought bubble to appear with the think blocks instead of with the say blocks。

 but looks also have to do with the costume for a sprite。

 Remember that last time we explored costumes and sprites and how we could change the different costumes that a sprite might have。

 we did that before， just by manually clicking on which costume we want the sprite to take on。

 Now we can start to program it using blocks to decide what's going to happen in our project。

 And when our sprites are going to change their costumes。 So let's try a different character。

 I'm going to delete my hedgehog sprite by clicking that trash icon。😊，And let's create a new sprite。

 I'll go into animals and let's choose the bear this time。

And I'm curious as to what costumes the bear has。 so I can click on the bear。

 I'll go into the costumes tab and I see that the bear has two costumes。 There's one called bear A。

 that's just the bear as it is right now。 And there's also bear B。

 where the bear is standing up a little bit。 So we got bear A。😊，And there be。

 And I can toggle between them in the costumes tab to decide what costume the character will take on。

But I can program this as well by assembling some blocks together。

 So let me start with a block called Switch Co 2。😊。

Let's start with costume bare A with the bear normally the way that it is right now。

 And let's give it a starting position。 When I start， I would like for it to go to。

Let's say x equals negative 1，31 one。 Okay， let's go negative 1，20 and negative 50。

 just to use some cleaner numbers。 that's going to be the starting position and the starting costume for the bear。

 Every time we click on this script， it's going to switch to this costume。

 It's going to move to this location。😊，But now what I'd like for it to do is I want the bear to walk across the stage。

 And when it gets to the other side of the stage， the bear is going to stand up。

 That's maybe what I'd like for the bear to do。 And so let's do that in two steps。 First。

 I want the bear to walk across the stage。 and then I want the bear to stand up walking across the stage。

 That sounds like motion。 So it's going to be in the motion section of my blocks。

 And I'll use this block。 We've seen it before。 Let's take two seconds。To glide to x equals 120。

 and y equals negative 50。So it's going to， the Y is not changing。 It's not going up or down。

 The only thing that's changing is the X。 We're moving to the right along the stage。

And after you glide there， after you take two seconds to glide there， now I want it to stand up。

 that's going to be looks， it's what it looks like， what costume it's taking on。😡。

And here let's go ahead and switch the costume to Barby。So we'll try it now。

 I'll click on this script。 and we start on the left， the bear walks across。

 And when it gets to the right side of the stage， it stands up。 and I can click it again。

 Everything will reset because we go back to costume A， we go back to the left。

 and every time I click it， the bear goes to one side。 and then it stands up at the end of that。

So we can combine motion and looks blocks to start to create stories just by using these sprites and changing where they are and what costumes they're taking on。

 And we can make our stories more interesting by adding some backdrops to our stage as well。

 So let's add a couple of backdrops where we might want for our bear to be walking through。

 for example。 So I'll go ahead and choose a new backdrop。😊，And I think I'll choose the forest。

 I'll have the， I'll have the bear walking through the forest。

 So that's one possible backdrop that the bear could be in。 I wantan to pick another one， though。

 Just have a couple of options that I can work with。 So I'll go back to the bottom right。

 chooseose a new backdrop。 And this time I would like， I'll scroll down near to the bottom。

 There is this one， which is called woods and bench， which Ill go ahead and click on as well。

 And so now I have the bear in the woods where there's a bench as well。😊。

So I've got these various different backdrops that I now have as part of my project。

 And now I'd like to construct a story that involves the bear moving through these various different backdrops。

 And so let's try and build this story one piece at a time。 I want the story to start in the forest。

 So I'll get rid of these blocks for now。 We can add them back later。😊。

But there's a block here called switchitch Backrop 2。😡。

And switchitch backdrop to will let me choose what backdrop I want the story to have。

So let's start in the forest。 I'm going to choose the backdrop called forest。

 That's where I want the story to begin。 And I want the bear to begin off to the left。

 so I can move it to where I want。 and I can look at the x and y values to see about what the X and y values should be。

 And I'm going to have it go to let's say negative 1，20 and negative 50 again。

So just a choice of x and y value， now when I click on this block。

 the bear goes to the forest and it goes to a particular location。

And I want for it to also not be standing up。 And so that's its costume。

 So we're going to switch its costume to。Bear A。 And these all happen so quickly that it doesn't really matter what order these three blocks are in。

 but it is still going to run one at a time。 It just happens so quickly that it looks like everything's just happening all at once。

 where we go to the forest。 We go to a particular location。 We switch the costume to bear A。😊。

And now what I want is for the bear to walk off the stage in this forest and enter the other backdrop that we had。

 the woods with the bench there as well， and so I wanted to walk to do that I can use the glide block that we saw before。

😡，So let me have the bear take maybe three seconds to glide。 I don't want the y value to change。

 It's just gonna to walk left and right， but the X value， I wanted to like walk off the stage。

 So I'm going to make this a big value， something like 300。

 just try and get it close to the edge of the screen。 And after it walks off stage。

 now I want to switch the backdrop。So I'm going to go back to looks。 Let's switch the backdrop。

 instead of going to the forest。 Let's now go to the woods with the bench。

So switch backdrop to woods and bench。 And now， as I'm thinking about this story。

 I'm going to have the bear move off to the right。 The backdrops going to change。

 And then I want the bear to come out from the left side。

 sort of like it's moving from one scene into another。 So I need to go back to the far left of。😊。

My program， I'll have a go to negative 300 in terms of x， which is really far to the left。

 And then let's take。Maybe3 seconds to glide to the middle。 X equals 0。

 That's gonna to be right at the middle of the stage。 So it's a whole bunch of blocks now。

 but it's telling a story。 We start at start in the forest， start on the left side of the stage。

 Start with costume bear A。 We're going to walk for3 seconds to the right side of the stage。

 then switch the backdrop。Go to the far left again and then walk back out to the middle。

 And you could try this one block at a time to get a sense for how it's going to work。

 But when you run it all together now， I'll go ahead and click on this block。

 You see the bear move off to the right。 And then it sort of shows up in another environment。

We can try it again and pay attention to which block might be happening when we start in the forest on the far left。

 We're gliding 3 seconds to the right。 The seam changes。 We go to the far left。

 and we walk back out to the center。So by putting these blocks together and really by playing around with it。

 you might not have gotten to exactly that on the first tribe， but you could run the project。

 And if you don't like where the sprite ended up， you could tinker with the X and the y values or how long it takes to glide from one place to another。

 But by assembling those blocks together， you have the ability to start to tell a story by creating some interesting blocks。

And there are other blocks that you can use to inside of looks。

 I'll go ahead and delete these for now， but in the look section。

 we have the ability to change the size of the sprite if we want to make it bigger or smaller。

 we also have these blocks show and hide。Show and hide， just control this toggle here。

 which is whether or not the sprite is actually visible on the stage if I click on hide。😡。

The bear goes away。 If I click on show。The bear appears。

 So we've taken a look at how we can have the sprite move around。

 We've seen how it can change its looks。 There's a third section here called sound that can play some sound for a sprite as well。

 So， for example， here， theres a block called play sound until done。

 And here if I had multiple sounds， I could choose from those different sounds or I could record a new sound if I wanted to。

 And by clicking on this block， you'll hear a sound。😊，The sound plays。

And so those sound blocks can be useful， too， if you want to play sounds inside of your project and one other block that I'll show now inside of control is this one called weight。

😊，Sometimes in your project， you just want nothing to happen for a little bit of time。

 a little bit of a pause between things that are happening on the project。 And here。

 the wait one second block will wait one second， and I could change the input to change how long it's waiting。

 and then it will move on。So if I put these together with the weight  one second block on top and then the sound。

 well， then what will happen when I click is I won't hear the pop right away。

 but it will be one second。And then you hear the pop after the end of the second。 And so that， too。

 can give you a little bit more control over your project and how it's working。

And so let's try and create a project that uses some of those blocks。I am not going to use the bear。

 so I'll go ahead and delete the bear， and I'll go ahead and change my backdrop if I click on backdrops back to backdrop 1。

 which is just this default white backdrop for now。😡。

But let's add a new sprite just to have a little bit of fun with this。 Let's pick a different animal。

 And this time I will pick the duck。 So we got our duck。 I want to center the duck。

 So I'll move it to x equals 0 and y equals 0 just to move it to the center of the stage。

 But here's what I'm going to。 I'm going combine some of the blocks we've just been using。😊。

I'm going to go to lookss and hide the duck。Then I want to wait one second that's under control。😡。

So controlling the project， I would like it to wait one second。 and then back to looks。Now。

 I want to show。The duck。 And after it shows， let's play a sound let's play the duck sound until it's done。

And so this is going to let our duck play a little bit of hide and seek， it's going to disappear。

 and then it's going to appear。 So when I click on this watch what happens on the stage。😡，It hides。

 It waits one second。 and after one second， it shows up and it plays the duck sound as well。😊。

And so you could have a lot of fun with these sounds。 right now， the duck just has one sound。

 but you could add other sounds to it as one。 You could record new sounds。

 You could upload a sound from your computer if you'd like to。

 And we even have the ability to have other blocks that play sounds in particular musical notes。

 There are extensions to scratch extra blocks that you can add into your block library that give your scratch projects a few extra features。

 And let's try that out now。 go ahead and delete the duck and we'll go back to the usual cat。😊。

So I'll choose a sprite and I'll just go ahead and pick the cat again。

And move the cat back to the center。But notice down here in the bottom left。

 there is this blue block icon with a plus next to it。

 This is where I can get to the extensions for scratch。

 And there are all sorts of different extensions for scratch that we can use。

 We'll take a look at a few of them today。 But we'll start with the music extension。😊。

And the music extension really lets you play music using scratchch box。

 So heres one called play note。😊，And it's saying play note 60 for 0。25 beats， the number of beats。

 that's how long the note's going to be played for 60 is just a number corresponding to what note we're playing。

 And if you don't happen to know what note corresponds to what number。

 that's okay if you click on the 60， what you'll see is a little piano appear here And if you've never played the piano。

 what I'm going to try to do is just play a scale where I'm just playing a whole bunch of notes in sequence that'll sound nice together and I'm going to do that just by clicking on each of these a different keys。

Of the keyboard。 and notice that every time I click on a different key， the note changes。

 Every note has a different number。 And so if I want to play all of them。

Let me drag out 8 of these blocks，1，2，3，4，5。6ix。🎼7 and 8。 And for each one。

 I'll select a different key。 So will be the second white key。 This will be the third one。

This will be the fourth one。This one will be the fifth one。This one will be6。🎼7。And 8。

So I've got eight blocks in sequences， each of which is playing a different note。

 and now when I click on this block。😡，You can hear that sort of scale。

 And there are other blocks too to change the way this sounds。

 I can set the instrument to change it to something else。 if I wanted it to be a guitar playing。

 for example， I can set the instrument to guitar。 and now。

The instrument sounds a bit different if I wanted to go faster or slower。

 that's something called tempo in music， how quickly or slowly the music is going to play。

 I can change it to 80， for example， and try that。Plays a little bit faster。

 I could change it to something smaller， like 40。And then it plays a little bit more slowly。

 So there are a lot of blocks that you can use to change the way your project behaves to add features and interesting activities to what it is that your sprites are doing on the stage。

 And I'll show you one other extension。 That's quite fun。 I'll drag the music away for now。😊。

But let's now try the pen extension。 The pen extension is going to let us draw with our sprite。

And so here's how that's going to work。 I'm going to start the cat over on the left hand side。

And I'm going to use this pen down。😡，Block and the pen up block， which we'll see in a moment。

 And the idea of this now is that I can draw on the stage just by putting a virtual pen down on the stage。

 moving the sprite across the stage and then picking the pen back up at the end of it。

 And so I'm going to put the pen down。Go into the motion section of blocks。 And this time。

 let's try moving some number of steps。 Maybe I'll move 30 steps。And then we'll lift the pen up。

And so let's try this now， I' click on this block。The pen goes down， We move 30 steps and we move。

 and the pen goes back up。 And what you notice is that as I do this。

The cat is still moving 30 steps every time， but it's leaving behind this line that the pen is drawing。

 The pens going down， We're drawing this line。 And then it's picking back up again。

 And the result is that you can draw shapes。 You can create works of art just by drawing using a sprite and moving the sprite around and making sure the pen is down while you're doing so。

 And when the pen is up， then it doesn't matter where you move the sprite。 It's not going to draw。

 You're only going to be drawing when that pen is actually down。

But you don't have to just create straight lines before we。

 when we were first doing motion with the cat， we had the cat move in a circle。 Remember。

 when we were having it move a little bit and then rotate a little bit and then move and rotate ultimately move in a circle。

 So if we wanted to draw a circle on the scratch stage。

 we could do that by combining our code that we used to move the cat in a circle along with the code for bringing the pen up and bringing the pen back down。

 And the way we did that。😊，Is by moving。 But then before the pen goes up， let's also。

Have the cat turn by 15 degrees。And then lift the pen back up。

And I'll have the cat start around the top of the circle。

 And that's probably where I want it to begin。 But before I begin。

 I want to erase what's currently been drawn onto the stage。

 And that's back in the pen section of the blocks。 There's one block just called erase all that's going to erase anything that's been drawn onto the stage。

 So I'll click that that erases the pen。 And you'll notice there other different pen blocks I can use to change what color the pen is drawing in to change the size of the pen。

 the thickness with which I'm drawing。 But I'll just stick with the default for now。

And we'll put the pen down， move 30 steps and rotate， move 30 steps and rotate。

And as I do this over and over again。The cat's moving。And moving。

 And what you see is that we end up drawing a circle on the stage just by putting the pen down。

 And every time we move， we rotate a little bit。 And the effect is that we can use the pen tool to draw out this circle。



![](img/cdffe696599eac69766638fe7d1181ce_2.png)

And so those are just some of the blocks that you can use in scratch。

 We saw blocks in the motion category for moving the sprite around in order to move it left。

 right up or down or rotate it。 for example， the looks section of blocks we can use change the costume of a block of a sprite to make it look a little bit different or to change the backdrop that we see in the stage inside of our scratch program or even to make our sprite speak up by saying something or thinking something inside of a speech or a thought bubble。

 we took a look at some control blocks， the ability to wait some number of seconds。

 the ability to play sounds， the ability to make music and use the pen in order to draw images and create works of art。

 And we can do all of that just by taking these blocks and putting them together in the sequence we want them to be in and ultimately using that。

 you can create some really interesting programs with scratch。

 That's it for an introduction to programming with scratch for today。

 Next time we'll take a look at how we can use these sorts of blocks and take our scratch broad projects even further。

 We'll see you next time。😊。