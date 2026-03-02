# 哈佛大学《CS50 Scratch 编程｜CS50’s Introduction to Programming with Scratch 2024》中英字幕 - P8：Abstraction - Lecture 8 - CS50s Introduction to Programming with Scratch.zh_en - GPT中英字幕课程资源 - BV1nx4y1s77C

![](img/357452e78b26a3dd6b24618bb17f43cc_0.png)

Welcome back， everyone， to an introduction to programming with Scratch。 And at this point。

 we've seen many of the major features of scratch。 how we can use loops and variables and conditions to put together some interesting projects。

 So today， let's take a step back。 Think about how we might use these blocks inside of our projects and how we might be able to improve upon the way that we've designed the blocks inside of our scratch projects。

 So let's start with a sample application or project that we might want to create。

 Let's open up scratch。 And let's say I want to make a game that involves the dinosaur and moving the dinosaur around。

 for example。 So to do that， I'll start by getting rid of the cat and adding a new sprite。😊。

I'll go ahead and find the dinosaur。And we'll bring the dinosaur into our scratch project。

And I'd like to be able to control the dinosaur by moving the arrow keys and so to do that I'll need to respond to various different events。

 I can use the when up arrow key is pressed for example。

 and then have the dinosaur respond by changing its y value， the up and down value by 10。

 for example。😡，And then I'll do similar things for the other arrow keys。

 I'll add one for the down arrow key， and when the down arrow key is pressed。

 let's go ahead and change the y value by negative 10 to move the dinosaur down。Let's add one event。

For the right arrow key， when the right arrow key is pressed instead of changing y will instead change x。

 which is the left or right value for the dinosaur。

 And then finally we'll also allow the dinosaur to respond to when the left arrow key is pressed at which point will also change X。

 But instead of positive 10 it's going to be negative 10。 and we've seen blocks like this before。

 and what they allow the dinosaur to do is respond to me pressing keys on the keyboard。

 if I press the right arrow， the dinosaur moves right if I press the left arrow。

 the dinosaur moves left if I press up the dinosaur moves up and if I press down the dinosaur moves down But let's now give this game a way to win some way that we can goal that we can try to accomplish and I'll add a new sprite and let's look through the sprites and see what might make sense here。

 I'm going to go with the star。 So here's a star sprite and I would like the dinosaur to try to chase after the star as by moving around using the arrow keys and maybe once the。

😊，So as touching the star。 We then we'll say that we've won the game。

 And there are multiple ways that I could go about doing this。 But here's one way。

 I could say that every time I move， every time I change Y by some amount or change X by some amount。

 Let's go ahead and check to see if we're touching the star。So， for example。

 when the up arrow is pressed， we'd change y by 10， but we've now moved the dinosaur。

 So we better now check to see if the dinosaur is touching the star。 So what could I do。

I could go into control here and ask a question with if。

 and I'll move these other scripts out of the way for now， just by dragging them around。

And what I'd like to check for is if the dinosaur is touching the star。

 touching that's under sensing， and here's a touching block that'll drag out and change mouse pointer to star。

So now when I press the up arrow， why will change by 10。

 and then the dinosaur will check to see if it's touching the star。 And if it is， let's go ahead and。

Let dear。Dinosaur report how long it took to find the star。 So maybe it's going to say something。

 and it's going to say。The timer， the timer under sensing recall is just how many seconds has it been since we started。

This program。So I'll go ahead and start my project， and I'll press the green flag。

I'll move the dinosaur to the right and then move the dinosaur up and notice that as soon as it's touching the star。

 it reports， okay， it's been 4。82 seconds and that's how long it took the dinosaur to find the star。

😡，Now， this doesn't work perfectly all the time。 I could try this again， for example。

 press the flag this time， if I move up first， move all the way up and now start moving to the right。

Well， I'm touching the star， but no time was reported。Why not？ Well， if you notice。

 we can take a look at the blocks that I have inside of this project。 My condition。

 this condition here， if we're touching the star， then say the timer for two seconds。

 it appears here when the up arrow key is pressed。 But really。

 I should be checking this all the time whenever I move。

 whether I'm moving to the right or to the left or moving down every time the dinosaur moves。

 I would like for the dinosaur to check to see if the dinosaur is touching the star。

 So what I'm going to need to do to make this project work， is take this same condition。

 If we're touching the star， say the timer say the timer。

 And I'll have to include that in each of the other scripts in my project as well。 That way。

 it's going to check regardless of what key on the keyboard。

 the person playing the game is actually pressing。😊，And so I could add this to the down arrow。

 for example， and the way that I would do that is by adding a condition。And saying。

 if we are touching。The star， then。Go ahead and say。The timer。

For two seconds and that took a fair bit of time so you might also know that you can duplicate some of the blocks instead since these are really just the same blocks I can just copy them again to get them to work for left arrow。

 I'll go ahead and control or right click on the if block and just say duplicate。

 I want to copy this whole section and I'll drag it underneath the left arrow。😡。

And I'll do that one more time for the right arrow。Duplicate， drag it underneath right arrow。

 And now， regardless of which arrow key is pressed， whether it's up or down or left or right。

 we're still going to be able to check if we're touching the star。

And just to make things a little more interesting， let's add some code to the star， too。

 let's say when I press the green flag to start the program。

 let's have the star go to a random position just so that it chooses somewhere on the stage to go to so that the game is a little bit different every time。

😊，Now I press the flag。The program started that you see the star moved a little bit。

 and now I can use the arrows。To try and make my way to the star。And once I get to the star。

 you'll notice that the dinosaur reported to me how long it took。 in this case， it was 9。

70 seconds and 9。70， That's very precise。 Maybe I decide a little bit later。

 I'd like to improve upon this program a little bit。

 And what I'd really like to do is I would like to not say 9。70， just round it to 10 seconds。

 round to the nearest number of seconds。 And we've seen before。

 there's a block under operators called round that can round a number to the nearest whole number。

 And so that might be what I would want to do here。

 And what would I have to change in this project to get that to work。 Well。

 I'd have to add round to this say block and to this say block and to this say block and the one down below too。

 I'd have to add it to all four directions because effectively。

 I've copied myself again and again and again and again。

 And whenever you find yourself copying a lot of code in your project multiple times。

 oftentimes that's an indication that there might be a better way to try to solve that problem。

 And in this case， there is。😊，And what we can do is create an entirely new block of our own instead of repeat all of these。

 this combination of multiple blocks， the if and the touching and the say and the timer and repeating that set of blocks multiple times。

 I'm going to write those set of blocks once and then just refer back to that collection of blocks by a name that I choose and I'll show you exactly what I mean by that right now。

 we're going to look at a new section of the scratch interface。😡，Which is here called My blocks。

 And this is a place where you can create blocks of your own。

 Scratch has blocks that say something that change the y value or the x value by something。

 but we can create a new block if we would like to。😡。

And I can click make a block to make a new block， and I have to give the block a name。

And I'll call the block check if one， because that's what I want the block to do。

 I would like the block to just take care of checking if the dinosaurrs won the game。

 meaning checking if we're touching the star。 And if so， go ahead and report how long it took。

So I've defined this check if one block and what you'll notice here， up at the top of my screen。

 I now have a block that says define check if1。😡，Everything beneath this block now are going to be the blocks that run every time I want to check if one。

 every time I want to check if the dinosaur has won the game。😡，So what should I do， Well。

 I'll take this same condition， if touching star， then say the timer for two seconds。

 And I'm going to put that underneath this definition for check if1。

 What does it mean to check if the dinosaur has won the game， Well， it means check。

 If the dinosaur is touching the star， then say the timer for two seconds。And now。

 underneath this event here， when the up arrow key is pressed。

 rather than change y by 10 and then this complicated condition with multiple blocks that I had to put together。

 I can just change y by 10 and then drag out this new block that I created and I picked a name for called check if1。

😡，So the logic for that script now， when the up arrow key is pressed is much simpler。

 It's only two blocks。 change y by 10， and then check if one。And what does it mean to check if1。

 Well I define what that means up here。 The definition of the check if1 block。

 What should happen when I run that block is we want to check if we're touching the star。

 then say the timer for two seconds。And now I can do the same thing for all of the other scripts as well。

 replace this complicated condition with four different blocks that I've put together。

 and instead just use a single block， the check if one block。😡。

So I'm going to delete this condition and just replace it with this one check if one block。

 and I'll do the same for the left arrow， getting rid of the condition， adding back check if1。

 and the same for the right arrow， getting rid of the condition adding back check if one and now the logic for these arrow keys is much simpler to read and it's organized more nicely into just this single block check if1。

 and the program will behave the same way I can try again。I can still move the arrow keys around。

 and the dinosaur will still report to me when it's touching the star。

 but I'm not repeating myself as much。 so I'm using fewer blocks and being more efficient about my use of blocks。

And it's also now easier for me to modify the behavior of this program， too。

If instead of saying the timer， I would now like to round the timer， as I talked about wanting to do。

 instead of needing to add round to four different places for four different arrow keys。

 I can just change it in one place。 I can say， okay， let's go to operators。

Let's take this round operator。And let's round the timer for two seconds。

And since I've modified what it means to check if one， now。

 all of these other arrow keys that use the check if one block will be taking advantage of this updated definition of what it means to check if we've won the game。

I'll pressss the green flag。 We'll start the game。 I'll move the dinosaur around。

And once I'm touching the star， you'll see that it now reports a number。

 but it's been rounded to the nearest in。 We now just say 6 seconds instead of like 6。

28 seconds or something like that， for example。So the ability to create your own block opens up a lot of doors for trying to improve the overall design and the overall readability of your project as well。

 and I'll give you another example of that。 let's delete the dinosaur in the star and bring back our familiar balloon that we've been inflating and deflating a couple of times throughout this course。

😡，And so let's try now to inflate and then deflatee the balloon。I'll say。When the flag gets clicked。

What should the balloon do， Well， let's start by giving the balloon a size of 50%。

Started at like half size。 And then what I would like for the balloon to do in order to inflate itself is to repeatedly change its size。

 increase the size by 10， increase the size by 10 again and repeat that a couple of times。

 So here is change size by 10。But if I wanted to repeat that process a number of times。

 then I would go under control and say， repeat 10 times。 Yeah， that seems reasonable。

 Let's repeat 10 times， change size by 10。So now when I press the green flag。

 you'll see the balloon starts at 50% size and then it grows。

 It inflates very quickly up to full size。 And now just for fun， let's go backwards。

 Let's deflate the balloon。 We'll have our balloon wait one second。😊，And then I want to deflate it。

 decrease its size， which I can do by changing its size by negative 1。

And I'll have to repeat that as well。 I'll repeat that 10 times by going into control。

 repeat 10 times， change the size by negative 10。So now watch what happens when I run this balloon。

It inflates， waits a second， and then it deflates。 It goes back down to 50% size。 I'll run it again。

 it inflates， it waits a second， and it deflates。And this works。

 This certainly achieves the effect that I want of increasing the size of the balloon。

 waiting and then deflating it。 But it might be a little bit hard for someone to read。

 if I just showed this code to someone and asked them， what does it do。

 you'd have to pay very careful attention。 We're starting size at 50%。

 We're repeating 10 times changing the size by 10 each time。 So that's 10 times 10。

 We're increasing the size by 100 waiting a second and then doing it in reverse。

 You'd have to do a lot of processing， thinking about what are the numbers， What are the loops doing。

 how many times is everything happening just to get a sense for what the project is doing。

 It's not necessarily wrong， but we might be able to make it a little bit easier to read as by creating some new blocks。

 These blocks right here。  ultimately， the changing size by 10 over and over again。

 What they're doing is they're inflating the balloon。 But of course。

 scratch doesn't have a block called inflate to increase the size of the balloon 10 times But we could create it。

 We could add a new block called inflate that does exactly that。😊，So let's try it。

 I'll go into my blocks。I'll create a new block， and I'll call it inflate。

And the definition of inflate will be this loop right here。 repeat 10 times， change the size by 10。

And let me create another new block called Dlatelate。😡，And the definition of deflate。

Will be the opposite。 Repeat 10 times change the size by negative 10。

And now instead of using these repeat and change size of my blocks inside of this script here。

 I'll just drag out my new blocks， my inflate block。😡，And my defflat block。And now， first。

 notice that this program does exactly the same thing。 The balloon increases in size。

 weights a second and then decreases。 But look how much easier to read this code now is。

 especially right underneath this when flag click。 I've simplified the logic by making it easier to read by taking advantage of these custom blocks。

 which we can now call abstracttractions。 abstracttraction is all about taking things that look very different or that are in different parts of your program。

 like I had that if condition in four different places in my program and realizing that they're all just the same idea that I could give a name to。

 And here I can give a name to inflate and deflate。

 and now just refer to those actions by their name。 So when the flag is clicked。

 we're going to set the size to 50%， we're going to inflate the balloon wait one second and deflate the balloon。

 you can just read exactly what it is that this project should do。

 And if in other places inside of my project I later wanted to inflate or deflate the balloon。

 I could do that too。 I could add other blocks and other scripts and。😊。

Use inflate and deflate multiple times rather than need to repeat myself by saying repeat 10 times change size by 10 every time that I wanted to inflate the balloon。

 So these blocks really helped to organize your code。

 helped to reduce repetition and help make it clear to someone reading the code what it is the code is doing。

😡，Now， one thing is true that these blocks are always going to do the same thing every time。

 They're always going to repeat 10 times and change the size by 10。

 which will have the effect of increasing the overall size of the balloon by 10，10 times 10。😡。

But maybe I'd like a little bit more control。 Maybe sometimes I just want to inflate the balloon a little bit。

 and other times I would like to inflate the balloon a little bit more or a little bit less。

So how could I do that。Well， let's go ahead and。Control click or right click on the inflate block and now edit it。

You'll notice that I've named the block and I could change the name of the block now if I wanted to。

 But when you make a block or when you edit a block。

 you also have the ability to add inputs to that block as well。 This block is now a function。

 and we've discussed before that functions can accept inputs。

 information that tells that function how to behave。😡，And so here， for example。

 I could add an input that would just be some number。 I'll call that number n， for example。

 which is just a convention for some number n for number。And let's add a label。

 We're going to inflate n times。 This is just words that will describe what it is the block is now going to do。

 And now I'll press okay， And what you'll notice now is that the inflate block is now changed。

 It's now inflate。 and then a blank value times。 and that blank value looks much like the blank value and change size by or move some number of steps。

 for example， this is now a place where I can provide input into this function to tell it how to behave。

And you'll notice now that under define inflate， it doesn't just say define inflate。

 but then define inflate n times where I have access to this block here called N。😡。

So what I'm going to do is take n and drag it inside of this repeat instead of repeating 10 times every time。

😡，Let's repeat n times every time。 Whatever n is where n is going to be the input to this function。

And they'll do the same thing with Dlate。 I'll edit it， and it will be deflate N。

 and then add a label times。And I'll say okay to that。And now。

 instead of repeating 10 times in Dlate， let's repeat n times as well。

Now these functions have the ability to take some input and you'll notice down below under the inflate block。

 I need to type a number into this space so I could say inflate 10 times and then deflate 10 times and now if I run the project。

 it works the same way it inflates and then it defflats。

 but if I just change these inputs inflate 20 times and deflatelate 20 times。

 well now the project's going to behave differently。😡，Inflate。And deflate。

 It gets much bigger and then much smaller because I'm inflating and deflating it more often。

And then I'll change these back to 10 for now So we go back to the usual behavior inflate and then deflatelate。

 But I could use these blocks in other places， too， I could say， for example。

 that any time I click on the balloon when this sprite clicked。 Well， let's like clicking。

Inflate the balloon。Two times。So not 10 a little bit fewer。 So I pressed the flag。

 and it inflates a lot inflates by 10 and then defflates。 But every time I click on the balloon。

 it's just going to inflate by a little， it's going to inflate two times。

 And we were able to achieve all of that just by giving our functions some inputs。

 We defined an inflate block。 gave it an input N。 and then use that n inside of the definition of the block。

 when we run the block， we're going to look at what is the value of n。

 And that's going to tell us how many times to repeat。 such that now when we use that block。

 I can decide how much to inflate the balloon by， just by saying， well， in this case。

 I want to inflate it 10 times but down here， I only want to inflate it two times， for example。

 So you can make your blocks very customizable， very flexible as well。😊。

And these blocks don't just need to take one input。 They could also take multiple inputs as well。

 So let's see an example of that。 Let's go back to。Our bear， which we've had walk around before。

 and you might recall that before we've had it walk in a couple different costumes。

 If you go to costumes you see that we have this costume where the bear is on four legs and I'll go ahead and call that costume4。

And here the bear is on two legs。And I'll rename that costume up in the name section I'll call colored to。

So I have a costume called4 and a costume called two。 and just renamed those two default costumes。

 But now let me make a new block and here's what we'll call this block。 The block will be walk。

Then I'll add an input， which will be a number。And I'm gonna call it M for now。

 So you can call this whatever you want。 This is just a name of an input。And it's going to be walk M。

And then I'll add some text steps。And then I'm going to say on。

 and then I'm going to add a second input， a second input that I'll call N。

And then I'll add some text， feet。So I added two inputs and two additional labels。

 but this block is now called walk M steps on n feet。😡。

So what this is going to do is it's going to control how far the bear is going to walk on a certain number of feet。

 So what do I do about the number of feet。 Well， that's its costume。

 There's a costume for four feet and a costume for2 feet。😡，So let's switch the costume to M or N。

Well， n is the number of feet。 and that's the costume。 So N is going to go here。

 We're going to switch the costume to N representing how many feet should the bear now be walking on。

 And now let's walk M steps， Well， I can walk one step just by saying， move one step。

 And if I want to do that multiple times， I can put that in a repeat block。 So let's go into control。

 and repeat the process of moving one step。 But instead of repeating 10 times every time。

 let's instead。😡，Repeat M times。So this then is our definition of what does it mean for the bear to walk M steps on n feet。

 We first switch the costume to n where n is the number of feet。

 n is either going to be4 or two to determine which costume we should switch to。😡。

And then we're walking M steps。 So let's repeat M times this move one step block。

We've organized the logic for what it means for the bear to walk on a certain number of feet。

 And now I can use that block inside of my project。 I can say that whenever the flag is clicked。

 what should the bear do。Well， let's first have the block or have the bear walk 30 steps on 4 feet。

And then。Walk 30 more steps。On 2 feet。So it's going to start on4 feet， walk for 30 steps。

 then go to 2 feet， walk 30 steps。 and we can watch what happens。 I'll press the flag up。

 It walks on 4 feet。And then on to。 I'll try it again。 And it does the same thing。

 And this code right underneath the when flag clicked is now very easy to read。

 I can very easily see exactly what the bear is going to do。

 and it might have been harder to see that if I was using all of these every single time。

 Scitch costume and repeat this movement process。 And I can use this block now multiple times。

 as I have here to avoid repeating myself as well。 So Scratch offers a number of different blocks that you can use to achieve a variety of different things inside of your project。

 But we now have the ability to add our own blocks。

 if there' is additional behavior that we want our sprites to have inside of our scratch projects。

 We can create our own blocks to define some custom behaviors that we can use inside of our project to make them more complex。

 more interesting and ultimately better organized and more exciting as well。

 That's it for an introduction to programming with scratch for today， We'll see you next time。😊。



![](img/357452e78b26a3dd6b24618bb17f43cc_2.png)