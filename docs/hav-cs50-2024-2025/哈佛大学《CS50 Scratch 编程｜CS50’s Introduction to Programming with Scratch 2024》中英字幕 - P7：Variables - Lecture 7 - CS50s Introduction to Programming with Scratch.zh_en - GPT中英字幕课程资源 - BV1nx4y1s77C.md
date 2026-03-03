# 哈佛大学《CS50 Scratch 编程｜CS50’s Introduction to Programming with Scratch 2024》中英字幕 - P7：Variables - Lecture 7 - CS50s Introduction to Programming with Scratch.zh_en - GPT中英字幕课程资源 - BV1nx4y1s77C

![](img/75222c9e31d95ac227e35ffef839b688_0.png)

Welcome back， everyone to an introduction to programming with Sc。 And so far in Sc。

 we've seen our Sc programs use a variety of different values。

 values that keep track of what direction a sprite is pointing in or how big or how small the sprite is where it is。

 for example， And these are all pieces of information stored inside of our scratch program that we can use later in our program to make decisions or to make our program behave in different ways。

 But sometimes as our programs get a little bit more complex。

 we will want to store other pieces of information inside of our program as well。

 where we decide what information gets stored in our program and how we use that information later on。

 And we're going to start to call these variables in the world of program。

 And today we'll explore variables in scratch and how it is that we can use them。

 So I'll go ahead and open up scratch here as we have before。

 And there's one tab here that we haven't looked at yet， which is this variables tab。

 And a variable you can think of as just some value。

 some container inside of our scratch program that's。😊，To store some information。

 information that we might be able to use later inside of our program as well。 And so， for example。

 let's imagine I was trying to create a program that kept track of how many times I've clicked on the cat。

 So to do that， I want some piece of information。 Some container inside of my scratch program that's keeping track of how many times I've clicked on the cap。

 And to do that， I'll click on this make a variable button that will let me create a new variable。

 a new piece of information that I would like to store inside of my program。

 And when I create a new variable。 there are two things that I need to decide on。

 One is the name of that variable。 And I'll call this count for example because I'm going to be counting how many times I've clicked on the cap。

 And the second decision I need to make is is this variable for all sprites or for this sprite only。

 So there are two different types of variable。 If I have a variable that's for all sprites。

 that means that any sprite is allowed to use or modify that。😊，We often call this a global variable。

 Everyone can use that variable， or we can have a variable that's for this sprite only that's only for the cat。

 Nobody else is going to get to touch it。 That's what we often call a local variable。

 Other sprites don't have the ability to use it。 For now。

 we'll go ahead and use for all sprites only。 And we'll see why in just a moment。

 And that is the default。 When you normally create a variable in scratch。

 Any sprite is going to have the ability to use it。😊，So I've created a new variable called count。

And you'll notice that by default， it's checked here。

 You see a little check mark on the lefthand side。 And what you might have noticed is that on the stage。

 we see something appear in the upper left portion of the stage that's just reporting to me what the current value of the count is。

 What information is stored inside of that container。 And right now。

 I see that's stored inside of my count variable is the number 0。

 That's what happens to be there to begin with。 If I don't want to see that。 I could uncheck it。

 And then I wouldn't see the count to appear on the stage at all。

 But here is what I want to have happen。Every time the cat is clicked， so when this sprite clicked。

 that's the event that I want。I'm going to go into variables and change the count by one。😡。

Change count by one means take that variable count and add one to whatever number is currently being stored inside of that variable。

😡，And then。Let's not say hello for two seconds， but whenever you create a variable。

 you suddenly get this variable block that appears here that you can drag into your program。

Let's say the count for not two seconds， let's say for one second， for example。

So now when I click on the cat， the cat says one。 I click again， the cat says two。Now it says three。

 every time I click on it， we're updating the value of that count variable。

 and the cat is saying whatever its value is。 And I can check this count checkbox to be able to see。

 Al right now， count happens to be equal to the number 7。 And when I click the count again。

 now you see the count update to be the number 8。😊。

And so these variables give you the ability to keep track of information。

 and you might keep track of information in a number of ways。

 and we'll explore some of those ways today。 But right now， every time I click on the cat。

 the count is going up and up and up。 and there' is no way for me to reset this thing。

 if I keep pressing the count， the count is going to keep going up。 but it's never going back to0。

 So let's add the ability to reset my program。 maybe a button that lets me reset the count back to0。

 And how would that work。 Well， a button is going to be a new sprite。

So I go down below and choose a new sprite to add。And let's add this button here。

I'll drag it to the corner。And I want to change what the button says。 So we'll go into costumes。

 and let's add some text。And the text is going to say。Reet。I should change。

The color of that text will make it black text。And let's make it a little larger。

So now I have a button to reset the count。And now， what do I want to have happen？

When this spreadite is clicked on， when the reset button is clicked。

 let's go into variableism and let's set the count to 0。And so because this variable I said。

 should be accessible by all of the sprite。 It's a global variable。

 It means both the cat sprite and the button sprite are allowed to use that variable。

 They can both make reference to that count variable。 And here I'm using set count to0。

 meaning take the number0 and put that inside of the count container that's different from change count by which adds or subtracts a number from one particular variable here I'm just saying whatever value the count has now。

 ignore that and instead put the value 0 inside of the count instead And so now at this point。😡。

I can。Keep clicking on the cat， count goes up to 9 and then to 10。

 but watch what happens when I click the reset button， when I click reset。

You'll notice the count goes back to 0。 And now the next time that I click on the cat。

 now the cat is going to say one and then 2 and then 3。

So these variables now give us the ability to keep track of information。But what can we use that for。

 How is that helpful to us， Well， you might imagine that we could use this inside of a game in many games you might have played。

 for example， on a phone on a computer， you might have had the game keep score for you。

 It's keeping track of how many points you've earned in the game， for example。

 and it goes up and up and up as you earn points。 We can achieve that by using a variable。

 We can have a variable that's keeping track of what score we have in a game。

 And we update that variable as the score changes。 So let's build a game。

 I'm going to delete these sprites for now。😊，And I'm also going to delete the count variable。

 which I can do by control clicking on count and just saying delete the count variable。

Now that goes away。Let's create a game， using。The hedgehog。So here's our hedgehog。

 And I'll do something similar to what I did with the fish last time。

 I'll say when the green flag is clicked， let's have it forever。Point towards the mouse pointer。

And move five steps。We've seen this kind of code before。

 what this is going to do is when I press the green flag。

 the headhog is going to start moving and it's just constantly going to be following the cursor。

 forever it's going to point towards my mouse cursor and then it's going to move five steps towards me。

😡，So that works well， but let's now make this a game。 What is the hedgehog trying to do， Well。

 maybe it's trying to chase after something。 What's it going to chase after。

Let me choose a new sprite。 Let's go ahead and pick。To the star。

We'll have the hedgehog chasing after this star here。

And how is the star going to work Well the star is going to work where if the hedgehog ever is ever touching the star。

 then we're going to increase our score by one we're keeping track of how many points we've earned so to do that I need a new variable I'll go into variables I'll make a new variable that I will call score。

😡。

![](img/75222c9e31d95ac227e35ffef839b688_2.png)

And I'll press OK， so I now have this new variable called score。And for the star， I'm going to say。

When the green flag is clicked， I want the star to forever be checking。

If we're touching the hedgehog。So add an if statement and then under sensing。

 check not if we're touching the mouse pointer。But if we're touching the hedgehog。

So the star is going to constantly check if we're touching the hedgehog and if we are touching the hedgehog。

 then under variables， I'm going to change not my variable。

 which is a variable that's created for you automatically when you first create your Sc program。

 but I want to change the score by one。😡，And after you change the score by one。

 let's go to a random position to keep these interesting。

 the star will just move around after we increase the score by one。

So now we can try playing the game。I'll play the game。

 The hedgehogs following me around and watch what happens when I end up going to the star。😊。

You'll notice that immediately the score went up by one。

And you'll also notice that the star moved to a different random location。 Now。

 when I get to the star again， the score goes up to 2， and the star moves。

And I have a little game here， every time。I move around。 We end up。

Going to the star and increasing the number of points。So what do I want to add to this？

 What should I change about this？ Well， one thing I should probably change is that when the program begins when I press the green flag for the very first time。

 I probably want to reset the score back to0 in most games you play when you play it again。

 the score goes back to 0 and you have to start earning points from the beginning again。

 So I can say when the green flag is clicked。😡，Before the forever loop happens。

 I want to set the score to 0。 Notice this line should not be inside of the forever loop。 Otherwise。

 it's going to forever be resetting the score back to 0， which is not what I want。

 I want the score to be set to 0 at the very beginning of the program。😡，But after that。

 then I want to go into this forever loop where the hedgehog is going to be following me。

 So now the score goes back to0 when I press the green flag and I can start earning points again。Now。

 how do I win this game Right now， I'm just earning points and nothing's really happening。 Well。

 maybe I win the game once I get to a certain number of points。 That sounds like a condition。

 Once I get to a situation where I have maybe 10 points， we can call that winning the game。

And what happens when I win the game， I have to decide maybe the backdrop changes。

I can take a backdrop， let's add a new backdrop。Well， instead of picking an existing backdrop。

 actually， let me paint a new backdrop。Paint a new backdrop。 We'll go ahead and just create a。Green。

Background by drawing a green rectangle。And we'll add some text。 The text will say， you win。

 I need to change the color of that。make it black。And let's make the text bigger。

So that'll be the backdrop that shows up when we win， I'll give the backdrop a name。I'll call it。

When and the other backdrop is just backdrop 1 for now。 And so what do I need to change here， Well。

 when the program first starts， I want to set the score to 0， but I also want to make sure。

That the backdrop。Is backdrop 1， a default plain white backdrop to begin with。

But now let's add some code。😡，And I would like to say。Maybe when we change the score。

 I want to ask the question， have we won the game yet， I can add another condition。

By going to if here。After we change the score and random position that's going to be outside of this if statement。

 But if。The score is equal to 10， so something is equal to 10 and how do I get the score。

 that's a variable， so I go into variables。If the score is equal to 10。

 well then I want to display this backdrop， the backdrop that says that I've now won the game。😡。

So we'll go into looks。 We'll switch the backdrop to win。 but at this point。

 I also just want to stop the entire game。 I don't want the hedgehog to move anymore。

 I don't want to have the star keep going to random positions。 and it turns out that under control。

 there's one block we haven't used yet， which is just called stop all that has the effect of stopping all of the sprites that are in this program。

😡，So we'll switch the backdrop to win， and then we'll just stop all。 We'll stop everything。

So this program is getting a little more complex， but let's try and understand now what's happening inside the logic for the star。

 We're constantly going to be checking。 Are we touching the hedgehog If we're touching the hedgehog。

 we change the score by one。 And if now the score is 10， well now we've won the game。

 So we switch the backdrop and then we stop all of the sprites。 But otherwise。

 the star just goes to a new random position to let the game keep going。

So we can try the game now and see what happens when I get to 10 points。I'll press the flag。

The score at 0。 The backdrops gone back to this plain white background。And now。

 every time I touch the star， it goes to a new random position。

 And you can watch my score in the upper left increase。 I'm at 6。7 points。😊，8 points，9 points。

 And watch what happens now as I get the 10th star。Yeah。Everything freezes。

 The hedgehogs no longer following me， but we change the backdrop to this green backdrop that now just says that we win。

So one common use of variables is to keep track of your score in a game in something like this。

 for example。Let's take a look at it another use that we might use for variables。

 I'll go ahead and get rid of these sprites for now。

 and I'll get rid of the Uwin backdrop and we'll just go back to the plane white backdrop。

 and I'll also delete that score variable， which I don't want anymore。Let's choose a new backdrop。

 Let's choose blue sky， which is nice。 We've got the sky， and we've got the ground， for example。

 And let's imagine that we wanted a ball， for example， to be bouncing on the stage。😊，Well。

 let's add a sprite。And let's add the ball。Here is the bow。And what do I want the ball to do？ Well。

 if it's in the air， the ball is going to start falling until it hits the ground。

 So how do I achieve that idea， The ball is going to keep falling until it hits the ground。Well。

 when the green flag is clicked。I would like to， forever， keep repeating something。

And what do I want to have happen forever？ Well I want for to have happen for motion。

To change the y value。By。Negative5， negative5 is going to mean the ball is going to move down。

 and we're forever going to keep repeating that process。 So now when I press the flag。The ball falls。

 and eventually， it hits the ground。 And if I bring it back up again。

 it keeps falling because it's inside of a forever loop。

Inside of a forever loop every time it's going to keep falling until it hits the ground。

 And right now， it's kind of getting past the ground。

 So maybe I want it to stop if it ever hits the ground itself。

 So how can I detect when the ball is touching the ground。 Well。

 you'll notice that the ground is a particular color， It's this brown color here。

 And I can check for that color。By saying。If we're touching that color。Using if in touching color。

 which we've used before， I can check to see if we're touching the ground。

 I'll grab a color from the stage。 Let's grab this brown for the ground。😊。

And if we're touching brown， let's go ahead and。Stop everything。 The ball is going to stop moving。

So now I press the flag， the ball falls， and now as soon as it touches the ground。

 as soon as it just reaches that beginning of that brown section， the ball is going to stop moving。

 and if I wanted to go again， I press the green flag and you notice the ball fall until it hits the ground and then it stops。

And as we're watching this， I can drag the ball out and let it fall over and over again。

 You might notice that it doesn't look very realistic。 And why isn't this falling very realistic？

 Well， I have a ball here with me now。 And what happens if I toss the ball and let it fall。

 How quickly does it fall， Well， you'll notice。As I let that ball fall。

 then it actually starts a little more slowly at the top， it's more slow。

 And then as it falls over time， it gets faster and faster and it falls faster as it gets closer to the ground。

 It's slow， and then it gets faster。😊，And right now， that's not what my ball here is doing。

 Right now， my ball is just moving by five units every time we run through an iteration of this loop。

And so if I really wanted for the ball to be moving realistically。

 it should be moving slower at first and then get faster as it gets closer to the ground。😊。

So how could we achieve that， Well， rather than move by five steps every time。

 we could move by a variable number of steps every time。

 a variable that's keeping track of how many steps should we we be moving。

 And then we can update that variable so that the ball moves faster as it gets closer to the ground。

😊，So how do we achieve that？ Well， the first thing we need is we need a new variable。😡。

So I'm going to go into variables here。

![](img/75222c9e31d95ac227e35ffef839b688_4.png)

And create a new variable。 And I'll just call the variable speed。And now I have a decision to make。

 as I usually do， I this for all sprites or for this sprite only。And for this variable。

 I'm actually going to make it for this sprite only。

 This speed is only going to be a variable that this ball is going to get to use because no other sprite needs to use or access the speed of the ball。

 And that's going to be helpful because maybe later I might want to have a second ball that's bouncing up and down to。

 and then each ball should have its own speed。 I don't want them to be sharing the same speed because one ball might be moving more slowly or more quickly than the other。

 So this variable is going to be a local variable。 Only this ball is going to get to modify this speed variable。

 And you'll notice that now in this reporting block that's telling me what the speed of the ball is。

 It's telling me it's the speed variable that is associated with the ball sprite。

 It's telling me what sprite the variable belongs to。😊。



![](img/75222c9e31d95ac227e35ffef839b688_6.png)

And so now， what do I do here， Well， initially， when I pressed the green flag for the first time。

 let's set the speed to the 0。😊，Then instead of changing y by negative 5， let's change y。

By the speed。Changing it by a variable amount。 And then what do I want to have happen Every time the loop goes through。

 every time time passes I want to move faster down the stage。

 which means I want this value to be more negative。 So I'm going to change the speed。😡，By negative1。

 What does that mean， That means the speed is going to start at 0。

 And the first time we run through the loop， we're gonna to change y by 0。

 We're not changing it at all。 Then we're going to change the speed by negative 1。

 Now the speed is negative 1。 We're going to change y by negative1。

 Then we change the speed by negative 1 again。 Now it's negative2。 And the next time the loop runs。

 we change y by negative 2 and the negative 3。 And every time we run through the loop。

 the ball is going to be moving more and more and more each time effectively moving faster as time goes on until it's touching the ground。

😊，And so let's give that a try now and see what happens。Bring the ball up。And it falls。

 and you'll notice that it does exactly what I want。 At the very beginning。

 it's falling fairly slowly。😊，But then it speeds up near the end。 You notice near the end。

 the ball speed is all the way up to like negative 24。 for example， it's getting faster and faster。

And so that's working pretty well。 It's more realistic now because at the very beginning。

 the ball is moving slowly。 And then over time， it's getting faster and faster。 Of course。

 the thing that it's not doing that a real ball would do is it's not bouncing。Normally。

 when I bounce a ball， it hits the ground， And then it bounces back up to me。 So how could I do that。

 What do I need to change。 Well， this variable speed， that's controlling。😊。

How many steps the ball is moving every time I run through this loop。

And so when the speed is negative， that means the y value is going to decrease。

 meaning we're going to be moving down on the stage。

 If I instead wanted the ball to start moving up once it reached the bottom。

 then I want the speed to not be negative， but to instead be positive。

 And how do I change the speed from a negative number into a positive number。 Well。

 I can multiply the speed by negative one。 Then the speed will go from being negative。

 moving down quickly to being a positive number， moving up quickly。

And so let's give that a try now as well。 Once I'm touching the ground。

 rather than stopping everything。Let's do something else。Let's set the speed。To a particular value。

 And I wanted to be the speed multiplied by negative one。So we'll go to operations。

 we'll do multiply。And we'll calculate what is speed times negative one。

And let's set the speed to that。So， now。Every time we change the speed， we check。

 are we touching the ground and if we are touching the ground， the speed's going to invert。

 move in the opposite direction and start moving up now instead。

 So if I drag the ball up and let it go， watch what happens， it falls and then it bounces。

And it bounces， and it keeps bouncing。And the reason that's happening is because it's getting negative speed as it goes。

 as it's going down。 And then as soon as it touches the ground， the speed becomes positive。

 and then it goes back up again。😊，Now， the one thing this isn't doing if we really wanted to make this even more realistic。

 just to add one final touch to this program is that when I throw the ball in the ground。

 it doesn't come up to the same place。 it's a little bit lower every time every time the ball bounces。

 it starts high， then it might be a little lower than a little lower than that。

 it loses a little bit of speed。 Every time I bounce the ball。

 but this is the great thing about variables。 I can set this variable to be whatever I want。

 and I can use these operators adding and subtracting and multiplying and dividing to figure out exactly what I want for a variable to be。

 so maybe I want the speed to decrease by a little every time。

 Don't just make the speed positive but subtract one or subtract two from the speed so that now it's moving a little more slowly every time the ball bounces so I can go back into operators and let's subtract2。

😊，From whatever that new speed。Was supposed to be。 We invert the speed。 we subtract to。

 And now it's going to go from a higher bounce to a lower bounce。

 And every time you'll notice that it decreases a little until it kind of gets stuck at the bottom there。

 but we can try it again。It's going lower and lower each time。And eventually。

 it's going to hit the bottom。 And you might have to play around with it a little bit to get it to once it gets to a speed that's slow enough。

 the ball should eventually just stop moving。 But this is approximating that idea of a ball that's bouncing again and again。

 and we're able to use variables to control the speed to make this much more realistic。😊，All right。

 what else can we do with variables， We'll take a look at a couple other final examples。

 one is we can let the user have control over the variable itself， what you'll notice。

 I'll go ahead and get rid of the ball and go back to the plain white backdrop。😡。

Let's go back to the balloon example that we've seen a couple of times now where the balloon was inflating and it was inflating either when we blew at the microphone or press the space bar or we just let it go automatically via a loop。

 Let's let the user now control how big or small the balloon should be。

 Let the user control how much air is inside of the balloon。

Let's create a variable that I'm just going to call error。And now。

 what is this error variable going to do？😡，Well， if I control click on this area here where I can see what the value of a variable is。

 I can change what the readout looks like。 This is a normal readout。

 if I change it to a large readout you just see the number a little bit bigger but I can also change it to a slider and when it's a slider the user of the program can just move the slider to control what the value of the variable is going to be I can change error to be0 all the way up to like 100 for example。

 and that lets the user have some control over the variables in the program and how big was this balloon before。

 well usually it was somewhere between like size 100 and 200 so let me edit the slider range。😡。

Set the minimum value to 100 and the maximum value to 200。

 I did that by control clicking on the slider and then changing the slider range to now range between 100 at a minimum。

And 200 at a maximum。So I can go back and forth between those two values And now what do I want the balloon to do。

Well， when the flag is clicked， we'll just add a few blocks that say forever I want the balloon to set its size。

 not to 100%。 but to air percent。 whatever the value of the air variable is。

 that is what I want the size of the balloon to be。 I press the flag to start the program。

 And so now this balloon is constantly going to be checking。 what is the value of the air variable。

 And depending upon the value of the air variable， that's how big the balloon is going to be。

 So I can now just drag along this slider。 And as I drag along the slider。

 you'll see the balloon grow and shrink， I'm changing the value of the air variable and constantly forever。

 the balloon is updating its size to be whatever the value of that variable should be。

 And so variables don't just have to be set by these like set variable to or change variable by values you can also just let the user control a variable directly to let them in。

with your scratch project to let them decide how things should behave or what a particular sprite should look like。

 for example。And let's do one final example with variables I this time taking advantage of the pen tool to draw some shapes。

 And so I'll bring back the cat。Here's our cat again。

 And you might recall from before that we could get the cat to move in a circle by doing something like。

When the green flag is clicked， then forever。Have the cat。

Move a certain number of steps and then turn a certain number of degrees。

And that had the effect of moving the cat in a circle over and over。

 just by moving and then turning a little bit every time。And if we wanted to draw that。

 we could use the pen tool to try and draw that。 I'll have the Sc cat start in a particular place when the green flag is clicked。

 let's go ahead and go to 0，0 and be sure you're pointing 90 degrees， meaning to the right。

 And that's going to start the scratch cat off in the same place every time。😊。

So we get a consistent circle。But what I can do is add the pen extension。

 which we've seen before to do a little bit of drawing。😡，We're going to erase everything。

And then put the pen down to let the cat start drawing。

And now what you're noticing is the cat's moving in a circle。 And as it moves in that circle。

 it's drawing。 It's using the pen to draw the circle that it's moving in。

 And if I want to make the cat move a little bit more slowly， I might have the cat wait a little bit。

 Let's just have it wait a fraction of a second， maybe 0。05 seconds。

 And now the cat's moving a little more slowly。 And you can actually see it drawing that circle just by drawing it like that。

😊，But we're not really using any variables here， the reason why variables can be helpful is because we can change the cats behavior。

 maybe not have it moved by 10 steps every time， but have it moved by a different number of steps every time so I'll create a new variable I'll call it steps。

😡。

![](img/75222c9e31d95ac227e35ffef839b688_8.png)

![](img/75222c9e31d95ac227e35ffef839b688_9.png)

And we'll start。By setting steps equal to0。And instead of moving 10 steps， let's move it。Steps。

 steps， whatever the value of that variable is， That's how far I would like to move。

 But then every time you move， we're going to change the number of steps by something like。0。5。

 a small number just to make a very small change。So what's going on now with all of these blocks。

 Well to try and recap at the very beginning， when we first start the program。

 we're doing a little bit of setup。 We're saying have the cat go back to 0。

0 just to the center of the stage， have it point in 90 degrees。

 meaning point to the right and erase everything So if there were already things drawn on the stage just erase them so that we can start fresh and now put the pen down。

 meaning wherever the scratch cat moves， the pen is going to follow and it's going to trace those shapes and we have a variable keeping track of how far the cat's going to move every time。

😊，Right now， it starts at 0。 So we move that number of steps。 But over time。

 we're going to increase the number of steps。 the cat's moving。

 increase it by a little bit and then rotate。 And if we keep increasing how much the cat's moving and then rotating what you're going to see is a more interesting shape。

 It's not going to draw a perfect circle， but it's instead going to draw something like。😊。

This spiral。 notice it's moving by more and more every time。

 And as it moves more and more with the pen down， we're able to see this interesting spiral result from it because it started by moving very little every single time。

 just moving by a few steps。 And over time， it's moving more and more and more every time it rotates。

 and that's creating the shape that you're able to see here。

 And so by taking advantage of the pen and taking advantage of variables and loops。

 you're able to create some really interesting works of art shapes that can be drawn just by sprites on the stage by calculating by modifying some variables and adjusting what those variables should do in order to create more and more interesting programs。

 And you can see up here in the upper left。 this。😊。

Keeping track of how many steps it is that we've taken so far inside of this program。

 So variables add a lot of power to the programs that we can create inside of scratch。

 They give us the ability to keep track of whatever information we want。

 And then to use that information later in on in our programs to create even more exciting games and animations and stories all just through the use of these scratch blocks。

 That's it for an introduction to programming with scratch for today。 We'll see you next time。😊。



![](img/75222c9e31d95ac227e35ffef839b688_11.png)