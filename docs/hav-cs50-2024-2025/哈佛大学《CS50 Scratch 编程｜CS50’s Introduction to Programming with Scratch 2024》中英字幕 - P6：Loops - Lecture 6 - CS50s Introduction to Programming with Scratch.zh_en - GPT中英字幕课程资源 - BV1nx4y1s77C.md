# 哈佛大学《CS50 Scratch 编程｜CS50’s Introduction to Programming with Scratch 2024》中英字幕 - P6：Loops - Lecture 6 - CS50s Introduction to Programming with Scratch.zh_en - GPT中英字幕课程资源 - BV1nx4y1s77C

![](img/72d623dcd9ec318d9259a0e0473636f7_0.png)

Welcome back everyone to an introduction to programming with Sc。

 and so far we've seen a variety of different types of scratch blocks。

 We've seen functions that perform some sort of task。

 We've seen values that hold information like what direction the sprite is facing or what position it is or how big or how small it is。

 for example， And last time we took a look at conditions。

 the ability for our scratch programs to ask questions and then make decisions based on the answers to those questions。

 but through all of this， every time we run the code。

 every time we press the green flag or press the space bar inside of our scratch program every block of code is just running one time we're running through the code top to bottom one time and if we want to see the program run again。

 we have to press the green flag again or press the spacebar again or make something else to trigger the rest of the blocks to run。

 This time what we're going to take a look at is the ability of scratch programs to loop to repeat some blocks multiple times as computers will do quite often。

 And so let's take a simple example。😊，Right now， we have our usual scratch cat。

 And if I say when the green flag is clicked， let's have the scratch cat move 10 steps。

This program we've seen before， when I press the green flag， the cat moves。

 And if I want the cat to move again， I have to press the green flag again。

And then move again and then move again and then move again。

 And I have to be the one controlling every single time the cat's movement。

 So if I want the cat to keep moving continuously， I have to keep pressing the green flag again and again。

Ideally， I'd like for the cat to be able to do all of this on its own。

 I'll move the cat back to its original position。😊，And I'm going to introduce a new block now。

 It's also under control where we saw the if thens last time。

 And this time the block we're going to use is this block called For。

The forever block looks similar in terms of its shape to the if then block。

 The forever block also has a container inside of it where I could add another stack of blocks inside of the forever。

 but there's no question to ask the forever blocks's roll is just to run the blocks of code that are inside of it。

 And then as this little arrow suggest， go back to the beginning of the forever block and run it all again and then run it all again over and over forever until I stop the program。

😡，This is an example of what in computer science we would call a loop。

 something that allows for multiple blocks to repeat some number of times in this case， forever。

 And so what I'm going to do is I'm going to take the move 10 steps block and drag it inside of the forever block。

😡，And connect that to when the green flag is clicked。

Now the behavior of this program is going to be when I press the green flag。

 we're going to see the cat move 10 steps， but then the loop's going to happen again。

 It's going to move 10 steps again and then move 10 steps again and then again and again。

 and you'll see what happens。 I press the green flag。😡。

And the cat moves until it hits the edge at which point it's stuck。

 And it can't move any further than that。 I can drag it back to the beginning。

 and we can watch it go again。 I'll press the flag。The cat moves。

 and I only had to press the flag once， and the cat went all the way to the edge of the stage。

 It appears to be stopping。 It's not really stopping。

 What's happening is that it's trying to move 10 steps。

 But because it's already at the edge of the stage。 there is nowhere left for the cat to move。

And so I could fix this by adding yet another block， I stopped the program by pressing the stop sign。

 Otherwise， the cat would keep moving。 I'm dragging the cat back out。And。

Under the motion section of blocks。There is this block here， if on edge bounds。

And the idea of if on edge bounce is exactly as than they might suggest if the cat reaches the edge。

 it's going to bounce off the edge。 It's going to turn around and face the other direction。

 So I'll press the green flag now。And now notice what's happening。The cat's moving continuously。

 I only press the green flag once， but we're running this loop where the loop is saying move 10 steps。

 And if it's at the edge of the stage then bounce and go the other way。

 And now you might recall when we were talking about directions that sprites can be facing by default。

 Sprites in scratch have all around rotation， meaning that if you tell it to face the other way。

 it's going to end up upside down as if it had just been rotated to face the other direction。

 there is a fix to that， though， And the fix to that is to change the rotation style of the cat that we've seen a couple of times now。

😊，I can do that by going to direction here， changing the rotation from all around。

 which is the first option to just left and right， which is the second option。

And now when I run this program， you'll notice the cat bounces a little bit more nicely。

 going back and forth。Forever， at least until I pressed the red stop sign to stop the program from running。

And now， if you're really paying attention to this， trying to see if it looks at all realistic。

 you'll notice the scratch the scratch cat， its legs aren't moving。

 its legs are just straight and it's effectively gliding along the stage。

 doesn't really look like it's walking or running across the stage， for example。

 and we can fix that with a little bit of animation。

 animation the same way you might see television show or a movie be animated。

 And how does animation work。 Well， animation， when you're watching anything on TV or watching anything on a movie or on your screen。

 It's really just a whole bunch of images， one image after another image and the images are moving so quickly by your eyes that your eyes just process that and think of it as actual movement。

 And that's what we can try and do here。 have couple different images that look very similar to each other。

 but are slightly different and by moving back and forth between them very quickly。

 we can create the illusion of motion， the same way you might do so if you're animating something like a movie。

😊，So if we go into costumes here， you'll notice that the scratch cat does have two costumes。

 It has one costume here， where the legs are straight， and it has a second costume here， Co 2。

 where the cat's legs are bent。 And if we switch back and forth between them。

 you notice it kind of looks like。The cat's walking。And so we can achieve this this way。

 I'll go into looks。And I'll just add a next costume block into the forever loop。

We're going to move 10 steps。 If we're on the edge， we're going to bounce。

 and then we're going to switch the cat to the next costume。

Now watch what happens when I press the green flag。Now。The cat's legs appear to be moving。

 They're moving very quickly because the forever loop is happening very quickly。

 going very quickly through the movement through the bouncing and then through the switching of the costumes。

 But we've animated this cat just by moving it back and forth between these two different costumes。

 Now， its legs are moving rather quickly。 Maybe I want to slow this down a little bit。

 And I can do that just by going into control and waiting a little bit。

 One second is maybe a long time to wait。 Let's wait 0。1 seconds。

 Just a fraction of a second to slow down the cat just a little bit。😊。

And now the cat's walking in a little more of a leisurely pace。

 It's repeating this process over and over， moving 10 steps。 If it's on the edge。

 it's going to bounce， switching to the next costume between whether its legs are straight or bent。

 and then waiting just a fraction of a second so that we can slow the cat down a little bit。

 And you could play around with this value， determining how long you want the cat to wait for to determine how quickly or how slowly the cat's going to move across the screen。

 But using that loop， we now have the ability to create some effect that's happening inside of our program forever。

 that keeps going on and on。 So what's another example of this。 What else could we do with this idea。

😊，Well， let's get rid of the cat for now。 And let's bring back our underwater backdrop。

 Here's underwater 1。 and let's add。The fish。Back into our program， here's that fish。

And let's try something else。 When the green flag is clicked。

 I also want something to happen forever。What do I want to have happen。

 Well let's go to motion and let's have it point in a particular direction。Now。

 if it were always pointing in the same direction， then it wouldn't really matter if it was inside of a looper node。

 It's just always going to face the right， face the right， face the right， face。

 the right again and again。But I could have it point in a particular direction。

 and I'll go ahead and choose。A block like this instead。

 instead of pointing in a direction with a number， let's have the fish point towards something。

 Let's have it point towards the mouse。 It's pointing towards the mouse pointer。

So now watch what happens when I press the flag。You'll notice that immediately when I pressed a flag the fish turned。

 It's now facing my cursor， which is up in the upper left corner of the stage。

 But watch what happens as I move。The cursor。Every time I move the cursor。

You'll notice the fish is moving as well because it's constantly over and over forever following this instruction to point towards the mouse pointer。

 So wherever the cursor goes。The fish is going to be looking in that direction because it's pointing towards the mouse pointer。

 Now， it's looking at the cursor， though it's not really moving yet。

 So let's add one more thing to this program。 In addition to pointing towards the mouse pointer。

 Let's then have the fish。Move five steps。So now what's going to happen is wherever the cursor is。

 the fish is going to look at the cursor and then move a little bit closer to that cursor。

 So using the cursor will effectively be able to control the movement of the fish。

I'll press the green flag again， and you'll notice the fish start to move。After the cursor。

 wherever I move the cursor， the fish is pointing in that direction and then swimming in my direction。

😊，And we can use forever for other things， too。 any time I want something to continue to happen during my program。

 a forever loop is often the way that I want to achieve that。 Right now， my backdrop。

 I can click on the backdrop is just showing me this underwater scene。

 But I can add some blocks to the backdrop as well， telling the backdrop what to do。

 And maybe I'll have the backdrop， say when the green flag is clicked。Let's forever。Play a sound。

The default sound is pop， but I can change those sounds。

 Let's find a sound that's appropriate for being underwater。

 And if I scroll down through this long list of sounds， I can try them out。

 but I think there's one called。Let's search for water， maybe。Ocean wave。

 here's ocean wave related to water。I can sample here what that sounds like。 I like that one。

And so let's have the backdrop play this ocean wave sound forever。

 It's going to play this sound until it's done and then play it again。

 And so now when I run the program， notice what you see。😊，And here。

I have the fish following the cursor， and I just stopped the program。

 But because I had multiple forever loops。 I had a loop on the backdrop as well。

 we were just playing this ocean wave sound over and over again。

 And you could use this if you want a sound to play forever。

 you could add music to your programs as well。 if you wanted music to be playing in the background of your scratch program。

 you might have that music sound play until it's done。

 And then the song starts right back up again as soon as the song is over。

 so you can continue to have music in the background of your scratch program going over and over forever。

 So these forever loops can be quite useful for helping to create this sense of continuity。

 this continued presence of sounds or movement that are happening inside of our applications。😊。

And so let's try now to create another program。 I'll get rid of the fish。

 and we'll get rid of the underwater backdrop。Let's go back to this plane backdrop。

 and I'll get rid of this code， too。Let's bring back the cat。

And what I want the cat to do now just for fun is to not let me get too close to the cat。

 If my cursor gets too close to the cat， I would like for the cat to meow or something or otherwise indicate that it doesn't want me to get too close。

 for example。And so how might this work？Well， let's try this。 When the green flag is clicked。

 my instinct might be to say， well， if I want to check to make sure that I'm not too close to the cat。

 that sounds like a condition。 It sounds like an if then， if I'm getting too close to the cat。

 then have the cat me out because it's unhappy， for example。 And so I might add an if then。

And here I can use an operator。 I can use the less than operator because I want to check if the distance between the cat and the mouse pointer is less than some value。

 will'll say 100。And how do I find the distance， That's under the sensing category。

 It turns out there's a block here called distance to mouse pointer。 So I can check。

 is the distance between the cat and the mouse less than 100。And if so。

 let's go ahead and play the Mia sound until it's done。So the idea of this code now。

 what I would like for this code to do is to say。If I'm less than 100 spaces away from the cat。

 then go ahead and play the Miow sound。 And that's what I want the cat to do。

 But watch what happens if I try and run this program or run the program。

 and my cursor starts out pretty far away from the cat。😊，But as I bring the cursor closer。

Nothing seems to be happening。 I'm pretty close to the cat right now。 I'm even touching the cat now。

And yet， still， I'm not hearing the cat Miow。 Why is that what's going on。Well。

 it has to do with the fact that by default when you're running code inside of a program。

 that code is only going to run once。 What happened when I pressed the green flag when I took my cursor and I dragged my cursor over the green flag right there。

 And then I clicked on it。 What was happening inside of the program。 Well， immediately。

 Scratch checks。 It checks this question。 I the distance to the mouse pointer less than 100。 Well。

 no， it's not。 This is more than 100 faces in the world of scratches cord in the system。

 So we didn't play the meow sound。 And at that point， this stack of blocks was over。

 Nothing else happened because we ran through all of these blocks from top to bottom。

And that was the end of the stack of blocks。 What I really wanted to have happen is for this check for this question to be asked not once。

 but for the question to constantly be asked all the time。 I want the cat to be checking。

 is the distance of the mouse pointer less than 100。 And any time it turns out that I get too close。

 than I want for the cat to play the meow sound。 And that's another case where a forever loop is quite helpful。

 I don't just want to ask this question one time。 I want to ask the question forever as long as this program's running。

And so I can go into control， grab a forever block and put it around the condition just like that。

 And now this question， am I am I getting too close to the cat， it's going to be asked not once。

 but over and over again。 Every time we ask the question， we'll then ask it again。

I'll click on the flag。 The program has now started。 We still don't hear anything。

 but now watch what happens is my cursor gets too close to the cat。So it's further away。

 we hear nothing， but when I get too close。Then you start to hear the cat me out and you hear that happen because this condition is now inside of a loop。

 it's repeating over and over again forever， checking to see if the distance is less than 100。

And so that then is a forever loop， a loop that's going to run some code over and over again forever until the end of the program。

 And you'll often hear this also called an infinite loop。

 a loop that repeats infinitely again and again。But when we repeat code inside of our programs。

 we don't necessarily always want for it to happen infinitely。

 We don't always want for code to run forever。 Sometimes we do want the code to repeat。

 but not infinitely many times just five times or 10 times or 20 times， for example。

 And so how could we do that instead。 Well， for that， we're going to need another block。

 not the forever block， which I'll get rid of now。😡，But this block here。😡。

This block is repeat and then 10， and this is also a loop。

 It's going to take some code and repeat it multiple times。

 which is implied by this arrow here at the bottom right。

 but we get to specify by typing in here how many times I would like for that code to repeat。😡。

And so when can this be useful， When might I want to use a repeat block？ Well。

 imagine I wanted the cat to meow three times， for example。

 I could go to sounds and just place on meow until done and then place on meow until done。

 and then place on meow until done。 And now， when I press the flag。I do hear three mes。

But this is repetitive code。 I find myself repeating the same blocks again and again and again。

 and I could arguably improve the design of my program by using a loop instead。

 instead of repeating myself again and again， I'll just have a loop， not repeat 10， but repeat 3。😡。

And what am I repeating three times？Let's play the sound meow until done。 Now， I press the flag。

And it's still meow three times。 but this is better than the program I had before。

 It's better And for a couple of reasons。 One， I'm being more efficient with my use of blocks before I needed three blocks to say meow three times。

 Now I just have one block that says meow plus one block that's handling the repeating。

 So I'm being more efficient with my use of blocks。 And also。

 it's going to be easier or later for me to modify this program。

 If I want to change the way it behaves。 say that I later wanted this to say meow not three times but 30 times in my old version。

 I would have to just drag out an additional 27 additional play meow blocks until we were able to get to that point。

 Now I just change the number that appears inside of that oval。 and by changing that value。

 I change the number of times that the cat is going to meow。😊。

And this doesn't just have to be a number that I type in。

 I can drag in any value into that oval as well， which means I could do something like ask the user how many times the user wants something to happen。

 So let's give that a try。 I can go into the sensing category of blocks and ask a question。

The question I'll ask is type in a number。And then instead of repeating three times。

 let's repeat answer times。 Whatever the answer is， that's how many times I want the cat to meow。

 I press the flag， and I type 3， for example， and then you'll hear。3 me。

 But if I press the flag and this time， try5， for example。Then you hear it five times。

 so the user controls how many times this happens because the answer block I've plugged into that open space inside of the repeat block。

And so the repeat block is helpful now， any time I want something not to happen forever。

 but still to happen multiple times。 What's another example of that。 Well。

 way back when we first introduced motion， I showed you how you can get the cat to move in a circle。

 I said you could do something like move， let's say 30 steps and then turn 15 degrees。

 just turn a little bit， and that had the effect if I bring the cat up to the top where whenever I pressed the flag。

😡，You'll see the cat move and rotate a little bit。And the cat moves in a circle。

 But in order for that to work， I had to keep pressing the green flag every time I want the cat to move。

And every time it moved 30 steps and then turned 15 degrees。

 this is a great opportunity to use a loop so that I don't have to keep doing all the clicking。

 The loop will just take care of repeating this process again and again and again。

 so I can go to control， repeat a certain number of times and I counted to get all the way around。

 I had to click 24 times。 So go ahead and repeat this code 24 times where now when I press the green flag。

😊，You'll see the cat move all the way around in a circle。 very quickly。

 it's moving all the way around in a circle every time I click on the flag。

 And the reason for that is it's because it's taking every small movement。

 that movement of just moving 30 steps and then rotating。

 and it's repeating that again and again and again very quickly faster than I could ever click on buttons on the scratch interface。

 and the effect of that is that you're able to see this cat now move in a circle as well。😊。

And so with that in mind， let's revisit one final program that we've seen before。

 And that's the balloon program we've seen a couple of times now。 where before。

 last time we saw the balloon， I was pressing the space bar to try and inflate the balloon until eventually it popped。

 But now that we have these loops to repeat something again and again。

 I can have the balloon inflate itself without me having to press buttons again and again to get the balloon to inflate。

 I'll center the balloon。And let's try this。When the flag is clicked。

Let's go ahead and repeat something。Some number of times。

And what I want to do is I want to change the size by 10， which is what we did before。

 And then just to make this happen a little more slowly。 let's wait。 not a full second， but maybe 0。

2 seconds， Just a fraction of a second。So it's going to grow a little， then wait， grow a little。

 and then wait。 And then after we repeat 10 times after we're done with all of that looping。

Let hide the balloon。And we'll play a sound。 We'll play。This pop sound。 So now I'll press the flag。

It gets bigger and bigger。And then it disappears with a pop。Let's try it again。 I' press the flag。

Okay， nothing happened。 The balloon didn't come back， which is a little bit strange。

 But if you pay attention to my code， you'll see why that's happening。

 I've repeated 10 times this process of change the size by 10。 then wait 。2 seconds。

 And then after that repeated， we decided to hide the balloon and play the pop sound。😡。

But because we use this hide block to hide the balloon， the balloons disappeared。

 and then it never really comes back。 So if ever I want something to reset whenever I start the program again。

 I often need to add blocks immediately after the green flag is clicked to say。

 when you press the green flag， let's be sure to show the balloon because otherwise。

 the balloon's going to stay hidden from the last time I hid the balloon when I ran the program。

And so I can use the show block for that， going into looks， dragging out this block that says show。

And because I've been changing the size， I better change the size back to 100%。

So now I see the balloon。 it gets bigger。And then it disappears， and it can press the green flag。

And I see the same thing happen again。 Every time I click the green flaglag。

 we show the balloon again， set its size back to 100%。 Then we let it repeat。

 growing and growing and growing before we hide the balloon and play the sound pop until that sound is done。

😊，And this allows me to repeat the process of growing the balloon and to what size does it grow Well we're changing the size by 10 every time and we're repeating that process 10 times。

 so I could do the math in my head and say， okay， we're going to get up to a size of 200。

 What if I wanted the size to be bigger。 What if I wanted to let the balloon grow up to size of 250。

 for example， Well， I could do the math again and say， all right， we're starting at size 100。

 I want to get up to 250。 and if we're changing the size by 10 every time。

 then I'm going calculate that's like 15 repetitions to get it up there and I can try that。😡。

And yeah， it does seem to get to 250。 but I had to do a lot of math on my own to figure that out to figure out。

 okay，15， that's the number of times。 I would like for this code to repeat。

 There is one other type of loop that I'll introduce finally as one final block for today。

 that can sometimes make our logic a little bit easier。 And that's this block here。 Reat until。

 And this block effectively tries to combine a loop and a condition。😡。

We're going to repeat some blocks， not a fixed number of times， not five times 10 times 20 times。

 but until some question is answered true。 And notice this hexagon shaped opening is the same as the shape that we saw in those if blocks and the if else blocks。

 for example。 So what this is going to do is repeat some code until the answer to some question is true。

 So if I want the balloon to keep growing until it gets to a size of 250。

 Then I don't have to do the math and say， okay， that's going to be 15。 I can just say repeat until。

Drag the equal sign out， and I'm going to repeat until。The size。Is equal to 250。

And now I'll take this code that was in the old loop， bring it into the repeat until block。😡。

Get rid of my old repeat。And this is my new code。 I show the balloon。 set its size to 100%。

 We're going to keep repeating until the size is 250。

 I don't know in advance necessarily how long that's going to take。

 but we're going to just keep repeating the code until that's true。 We're going to change the size。

 Wait 。2 seconds。 And then at the very end， hide our balloon and play that pop sound。😡。

And so I can press the flag。And you see the balloon grow and grow。

 And once it reaches 250 at that point， the balloon disappears。

 So three different types of loops that we've been able to explore today。

 One is the forever loop that takes some blocks and repeats them over and over infinitely until we stop the program。

 One is the repeat block， which repeats a fixed number of times。

 I can say do this five times or 10 times or 20 times。 And then finally。

 the repeat until block that combine some of the ideas that we've been taking a look at today。

 looking at the ability to repeat until a particular question is answered true。

 and using those loops we have the ability to make our programs even more interesting。

 rather than have to click a button multiple times of repeat ourselves with code multiple times。

 we can let the code repeat itself。 just via the use of these loops。

 That's it for an introduction to programming with scratch for today。

 we have a couple more opportunities to take a look at what else we can do with scratch。

 So we'll see you next time。😊。

![](img/72d623dcd9ec318d9259a0e0473636f7_2.png)