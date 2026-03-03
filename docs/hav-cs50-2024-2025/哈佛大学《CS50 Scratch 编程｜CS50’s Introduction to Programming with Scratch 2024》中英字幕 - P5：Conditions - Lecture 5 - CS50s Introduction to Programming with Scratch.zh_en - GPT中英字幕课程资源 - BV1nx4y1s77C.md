# 哈佛大学《CS50 Scratch 编程｜CS50’s Introduction to Programming with Scratch 2024》中英字幕 - P5：Conditions - Lecture 5 - CS50s Introduction to Programming with Scratch.zh_en - GPT中英字幕课程资源 - BV1nx4y1s77C

![](img/bc7693b7d0e89d9c107d32bfc117c7d0_0.png)

Welcome back， everyone to an introduction to programming with Sc。

 And last time we took a look at values， pieces of information that are stored inside of our scratch programs that we could use inside of those programs。

 Today， we'll take that idea one step further， and take a look at how we can use information inside of our scratch programs to make decisions by asking questions and then deciding what to do based on the answer to those questions。

 And people do this type of thing all the time， asking a question and then making a decision when you're deciding when you're trying to leave the home you might look outside and ask。

 is it cold outside， And if it's cold outside， you might wear a jacket or you might ask。

 is it raining today。 And if it's raining， then you're going to take the action of bringing an umbrella with you。

 for example， And you can think of this type of logic as having two parts。

 there's a question that you're asking， iss it raining outside， I it cold outside。

 And then there's the logic， The decision that you make based on the answer to that question。

 And computers do the same thing， Comps ask questions like I the computer low on battery is the。😊。

connected to the Internet and based on the answers to those questions， the computer makes a decision。

 And today， we'll try to do exactly that sort of thing inside of our scratch programs as well。

 Ask a question and then making a decision based on the answer to that question。

So let's go ahead and open up Sc and we see the familiar Scca here。

 And let's make something happen whenever the space key is pressed。 That's one of our events。

 So I'll drag that when space key press event out into my code editor。😊。

And when the space key is pressed， let's play a sounder and we'll play the Miow sound。

So now every time I press the space key。You'll hear the cat me out。

But now to make this a little bit more interesting， let's introduce a new block。

 which you can find under the control section of the blocks。And that's this if block。

And what you'll notice in this if block is that there are two places where we can add additional blocks into this if block。

 you'll notice that next to the word if is a little hexagonal shaped region or I could drop a block in there and we'll do that in just a moment and this hexagon is going to represent the question that we're asking。

 We're going to ask a question inside of our scratch program it's going to be a yes。

 no question is the answer to this question， Yes or no or equivalently is this question true or false and based on the answer to that question we might run some additional blocks that are contained inside of this if block here。

 You see this block kind of has a top and a bottom and what that's going to allow us to do is enclose other blocks inside of this if block right here。

😡，So let's take a look at an example of that and see how we can fill in those two different parts of the if block The first thing we need is a question and for that we can go down into the sensing section of blocks and you'll notice there are a couple of blocks that have this hexagon shape these are questions that we can ask in computer science we often call these questions Boolean expressions a boolean expression is a fancy way of saying anything that is either true meaning yes or false meaning no。

😡，And the very first one here in the Sunsing category is a Boolean expression called touchuching mouse pointer。

So I'll go ahead and drag that into the hexagon here in the if statement。

 and you'll notice that it snaps into place， it fits right inside of that if statement which grows to fit the size of the hexagon block。

😡，And then I'll take the play on Miow until done block and drag it inside of the if statement。

And connect all of that to the event when the space key is pressed。

So now the logic is this when I press the space key， the if block is going to ask that question。

 is the cat touching the mouse pointer， the cursor on the screen， and if the answer is yes。

 then we're going to play the sound meow until done。

 but that's only going to happen if this condition is true if we are actually touching the mouse pointer so if I put my mouse pointer somewhere other than the cat and I press the space bar。

😡，You'll notice that I don't hear anything。But if I move my cursor over the cat and now press the spacebar。

Now， every time Im press the spacebarb， you do in fact hear the cat meow so our programs using these conditions now have the ability to make decisions。

 to ask a question and then make a decision based on the answer and this touching mouse pointer block can be used to check if the sprite is touching the mouse pointer。

 but also if it's touching another sprite for example。

 let's say the cat is playing with a balloon I can drag a balloon out so we've got the cat and the balloon and I'll say for the cat。

 now if you're touching the balloon。😡，Then play the Miowa sound。 So right now， I press the space bar。

And nothing happens。But if I move the cat so that it's touching the balloon。Well， now。

We're able to detect that。 We're able to sense that the cat is touching the balloon。

 And because of that， we're able to make some decisions。

 And these sensing blocks give you the ability to allow your sprites to sense the things around it。

 Figure out how closer， how far away or other sprites or the cursor to figure out what it's touching。

 whether it's touching a particular sprite or even touching a particular color。

 This block here lets you check if the sprite is touching something that is a particular color。

 And you can use that to build some interesting。😊，Interfaces as well。 So let's give that a try。

 get rid of the balloon for now。 And let's add a backdrop for our cat to play around in。

 And I want to try the winter backdrop here。 So we've got a winter backdrop。

 And now the code I'm going to write is this。 We're no longer going to respond to the space key。

 So I'll delete that by dragging it off。😊，But now， when the right arrow key is pressed。

 I'd like the cat to move to the right。 This is something we've seen before。

 Moving is controlled by a motion block， and we are going to change the x value by 10。

 Remember that X is how far to the left or to the right is this particular sprite。

 So when the right arrow is pressed， we're going to change the X value by 10。

 But now what I'd like to do is get the cat to detect somehow when it's touching one of the trees。

 There's a tree off to the right， there's a tree off to the left。 if the cat is ever touching a tree。

 I'd like the cat to know So it can report as much。 it can say that it found a tree， for instance。

 How could we do that。Well， the tree is not a sprite。

 It's not one of these sprites that I see down below。 It's just part of the backdrop。

 It's just there。 And so if I want to detect it， I can detect it by looking for a particular color。

So I might say， if。And then， go into sensing。Touching color。

And if I click on this little color well here in this oval。

 I can control what color I'd like to check to see if I'm touching。

 and I could try to come up with a green that looks like the green of the tree。

 but it'll be difficult for me to get it exactly right。 And for that reason。

 there's a great tool down below。 if I click on this eyed droppper button。😊。

That lets me pick a color from the stage。 you'll notice I can drag my cursor over the stage。

 it's picking out individual colors and I can say I want you to detect this color right here。

 this green that my cursor is hovering over now， and you'll notice that when I click there now the colors automatically update now my cat is going to be checking if it's ever touching that green that makes up those trees。

And if it is touching the green that makes up the trees well then let's go ahead and have the cat say something。

 And the cat's going to say。I found a tree。So now the cat can move to the right every time I press the right arrow key。

And it just moves。 It's all it's doing， but it's also checking。 It's asking that question。

 is the cat touching the green。And it's not touching the green。 So nothing's happening just yet。

 Every time I press the arrow Q， we're just changing the x value。 But watch what happens eventually。

And it'll probably happen right there。 The cat touches the green in the tree。

 and the cat says I found a tree。So these sensing blocks allow us to let our sprites be a little more intelligent about what's around it。

 What's in the backdrop， What colors does it happen to be touching and what sprites does it happen to be touching。

 And we can use that to create some interesting programs as well。Well。

 let's now revisit one of the programs that we already made and see if we can make it a little better now。

 I'll go ahead and delete the cat and change the backdrop。

 We'll go back to just the plain white backdrop。And let's bring back the balloon。

 you might remember from when we were working with the balloon a little bit earlier。

 that we were making the balloon bigger every time we blew， for example， into the microphone。

 the balloon was getting bigger and bigger and bigger。 In reality。

 you can't make a balloon bigger forever。 Eventually that balloon is going to pop。

 And so let's get this balloon to eventually pop。 go ahead and center the balloon by changing the X and the y values both to0。

😊，And now。I'll have the balloon respond to me pressing the space key。

 The space key is how I'm going to inflate this balloon。 And when the space key is pressed。

 I would like to。Change the size by 10。 This is similar to what we had before where whatever something happens。

 in this case， I'm pressing the space key， the blue just gets bigger and bigger and bigger。

 And you can see the size down below grow。 It's 1，70。 Now。 Now it's 1，80。 Now it's 1，90。

 Now it's 200， for example。 And this。This maybe feels big enough。 Once it gets the size 200。

 then I w to have the balloon pop， for example。So let's bring the size。Back to 100。

 back to the original size。I can ask a question。I can go to control and bring out an is statement。

 And this time， the question I want to ask is not whether the balloon is touching something。

 It's whether the size is 100 or 200。 And how could I check to see if the size is 200。

 Well down here in operators。 We've seen a couple of operators before we've seen the operators to do math。

 like addition， multiplication， subtraction and division。

 We've seen the operators that picks a random number， and these were all oval shaped operators。

 But now let's take a look at some of these hexagon shaped operators。

 These hexagon shaped operators are all boolean expressions。

 Things that can be either true or false answered， yes or no。

 And one of them here is whether something is equal to something else。😊。

So if I have two values and I want to know， are they equal to each other， I can use this check here。

 this hexagon shaped block to check to see if those two values are equal to each other。

 And that's what I want to do here。 I want to take my sprite。

 the balloon and check to see if the size of is equal to 200。So I'll take this block。

 drag it into the hexagon area next to the F statement。And let me grab the size value。

Which is under the looks category。Here is my size value。

And I want to check if the size is equal to 200。And if the size is equal to 200。

 what do I want to do？ Well， the first thing I'll have this program do is hide。

 The balloons going to hide。And then just for fun， let's go into sound and have the balloon play the sound pop until it's done。

So now what is the logic of the program， Well， every time I press the space key。

 we're going to run this line， change the size by 10， but we're also going to ask that question。

 check if the size is equal to 200。 And only if the answer to that question is yes。

 then we hide the balloon， and then we play the sound pop until it's done。😡。

So let's give the program a try and see what happens once I start to inflate this balloon。

 It's at size 100 right now。 And remember， you can check that just by looking down below here at the size。

And let's press the space。 It inflates a little。 It size is 1，10， 1，20，130，1，40，150。

 And now it's at 1，90， and watch what happens the next time I try and inflate the balloon one more time as by pressing the space key。

It goes ahead and it hides。And I can try that again。We'll go ahead and show the balloon again。

 And I can do that by using this show block here。 I'll just click on show。

 and that will show the balloon。And。The balloon inflates。Yeah。And then it disappears with a pop。

So that's how we can use conditions to check if two things are equal to each other。

 But you probably notice down in operators that we don't just have the ability to check if two things are equal to each other。

 We can check if one number is less than another number or greater than another number， for example。

 And let's give that a try。 instead of using the balloon。 I'll bring out another sprite。

 Let's choose the。Let's choose the duck this time。I'll center the duck by moving it to0 for x and 0 for y。

And when I pressed the green flag to start this program， the duck is going to ask a question。😡。

And the question might be。Type a number。 So it's asking me to type in a number。

 So now when I press the green flag， the duck asks me to type in a number。

 and I could type in a number。 I could type in the number one， for example， and press return。

So the duck now has a number， and now we could ask questions about that number。

 So if I want to check to see if that number is positive or negative， for example。

 I could add a condition。I could say， if。And then take the greater than blockout。

 which is under operators。 And now I want to say if the answer， which is in the sensing category。

 if the answer is greater than 0， well then whatever number the user typed in。

 that's a positive number。😊，And so we'll go into the look section and let's go ahead and say。

Positive for two seconds。So we ask the user for a number。 And if the user types in a positive number。

 something like the number two。Well， the duck says positive。Great， and then instead。

 if we typed in a negative number， let's say negative2。The duck doesn't say anything at all。

 So we're able to check to see if their answer is positive and if what the user typed in was positive。

 if that's true， then we're going to say positive for two seconds。

 But oftentimes we want to be able to make a decision based on either answer to the question so far with our if blocks。

 we've been asking a question is the answer to this question。 Yes， is it true And if so。

 then we're going to run some code， there's one block of code that we're running。

 if it's the case that the answer to the question is yes。

 but sometimes we want to handle both situations。 If the answer to a question is yes。

 we want to do one thing， and if the answer to a question is no， then we want to do something else。😡。

And so let's give that a try。Turns out there's another block that we can use。

 not just the if then block， but another block under control called if then else。😡。

And the if then else block is structured differently than the other blocks we've seen so far。

 the top part looks very much like the if block we were working with before。

 there's a hexagon shaped space for a question， and then an area beneath it where we could add a stack of blocks for what should happen if the answer to that question is yes。

😡，But this block now has another section called else。

 which has what appears to be an area for yet another stack of blocks。

 So inside of this block can be two separate stacks of blocks。

 One stack of blocks that run if the answer to the question is yes。

 and another stack of blocks that run， if the answer to the question is no。

 So regardless of the answer to the question we're going to make a decision about which of these two blocks we're ultimately going to run。

 And we can use that now to handle both possibilities。

 either the number is greater than0 or it's not。😡，And so here I'll take this answer greater than0 block。

 drag it into this condition。 And in that case， we're going to say positive。

 I'll get rid of this if statement because I no longer need it。

 Now I'm going to replace it with this if else。 If the answer is greater than0。

 we're going to say positive for two seconds。 Otherwise， let's go into looks。😊，Let's say。

Negative for two seconds。So now we're making a decision running some block of code either time。

 but making a decision about which block of code we would like to run。 I'll start the program。

 It's asking me for a number。 I'll type in a positive number， like the number two。

 and the duck says positive。We'll try it again， asking you for a number。

 I'll type in a negative number negative to。 and the duck says negative。

 So if the answer to the question is yes， we run one block， otherwise， we run another block。

AndNow there's a slight bug in this program。 You might have noticed that it does well for positive numbers and it does well for negative numbers。

 But theres one number that's not really positive， and it's not really negative and that's 0。

 If I type in 0 and press return， the duck says negative。Now， why is that， Well， it's asking。

 is the answer greater than0 is0 greater than 0， Well， no，0 is not greater than0。

 So instead of running the if block， we instead run this else block where we just say negative every time。

😡，And that's maybe not quite what we want。 What I probably want is to ask yet another question to ask again。

 is the answer less than 0。 If so， then it's negative。 And otherwise。

 if it's not more than 0 and it's not less than 0， then it must just be 0。😡，And to do that。

 I could add yet another condition inside of this stack here。

 I can add an if else inside of another if else。And to do that， I'll take another if else。

 drag it here underneath the else。😡，And so now if the number is not positive。

 I can ask a second question， ask yet another question。😡，Now， the question I want to ask is。

Is my answer， the answer is in the sensing category。Is the answer less than 0。

If the answer is less than 0， then I want to say negative for two seconds。 but otherwise。

 it's going into looks。I'm just going to say。0。So this is starting to get more complex。

 I have blocks inside of blocks inside of other blocks。

 And the way to read this now is what happens if the user types in the number 0。

 Well we start by asking this question here is the answer0 greater than0。 No，0 is not greater than 0。

 So we ignore the if block。 And we just look to the L section。 And now we ask another question。

 I the answer0 less than 0。 Well， no， that's not true either， so we don't run this block。

 and we instead go to the L， and we run this block， which says say 0 for two seconds。

 And that's exactly the behavior we want for the duck。

 so we can verify now that it works by pressing the green flag And if I type in 0。😡。

The duck reports that I did in fact， type in the number 0 if I instead typed a positive number。

The duck is going to say positive， and if I typed a negative number。Well。

 then the duck is going to say negative instead。And so using that。

 I have the ability to ask multiple questions and make decisions based on the answers to those questions。

 So let's use this ability now to build some interesting games that use our ability to ask questions and make decisions。

 And for that， I'll bring back one of our animals。 We'll go to animalsism and let's bring back the hedgehog And what I'd like for the hedgehog to do is to race across the stage to start at one point in the stage。

 try and get all the way to the right edge of the stage and see how quickly we can do that。

 So how would I go about creating this game。😊，Well， when the green flag is clicked。

 when I start the program， I would like the hedgehog to move to the left side of the stage as a place to begin this particular race。

So I'll have it go to a particular location。 And this is about right， Maybe I'll say negative 1。

50 and negative 25 for y。 And I could play around with that to figure out exactly what I want。

 But I'm just choosing nice looking numbers for now。And then every time not the space key。

 but maybe the right arrow key is pressed， I would like for the hedgehog to move a little bit closer towards the edge of the stage so I could have the hedgehog move 10 steps。

 for example。😡，And what I would like for the hedgehog to do is once it reaches the edge of the stage。

 it should report back to me how long did it take， How many seconds did it take for the hedgehog to get from one side of the stage to the other。

😡，And so for that， I can ask a question。We'll go into control。 I'll drag an if block out。

 and the question I want to ask which will be located under sensing。

 is not whether the hedgehog is touching the mouse pointer， but if the hedgehog is touching the edge。

 meaning the edge of the stage and if the hedgehog is touching the edge of the stage。

 what would I like for the hedgehog to do， Well， I want the hedgehog to say something。😡。

And what do I want it to say， Will I want the hedgehog to say whatever this timer value is。

 Remember that timer is a value that keeps track of how many seconds have passed since the beginning of my program。

😡，And I could have it say just the timer， but I'm actually going to use an operator first。

 I'm going to have us first round the timer and then say that result。 Why am I doing that， Well。

 the timer normally has something after the decimal point， maybe like 5。

28 seconds have passed or something like that。 And I don't really care about what's after the decimal point。

 I just want to know， has it been 5 seconds or 6 or 7 seconds， for example。😡。

So now we're going to move the hedgehog every time I press the right arrow key。

 and if we're touching the edge， we're going to say whatever the value of the timer is for two seconds。

😡，So let's give that a try。😊，We'll start the program。 And every time I press the right arrow。

 the hedgehog moves a little bit。And when it reaches the edge。

It's going to report how many seconds it took。 In this case。

 it took 9 seconds for the hedgehog to get all the way to the rightmost edge of the stage。

But we can keep asking more questions here， adding more blocks to the program to make it a little more interesting。

 I'll get rid of this safer now and instead replace it with an if else。

 an opportunity to ask another question。😡，And this time the question I want to ask is this。

Under operators， I'm going to take the less than blockout， and I want to ask。

 is the timer less than5？Remember， this question is only asked once I'm at the edge。

 once the hedgehog has reached the edge of the stage， we're going to ask。

 has it been fewer than5 seconds， and if so， that was pretty fast。

 So let's go ahead and have the hedgehog say。😡，Fast for two seconds。And otherwise。

 if the timer was not less than 5， then。We were going kind of slowly。

 so I'll have the hedgehog say slow for two seconds instead。

So now if I press the green flag and move quickly， very quickly try and move the hedgehog across the stage。

 well then the hedgehog says fast， I managed to make it across in fewer than five seconds。😡。

But if I'm going more slowly， I'll try it again。And more slowly press the right arrow key。Well。

 then it's going to take a little bit longer。 And at the end。

 the hedgehog does report that I was slow that I was not very fast at moving across。

 So that's one possible game you could try to build by asking questions。

 Questions about whether we're touching the edge questions about whether the timer is a particular value less than a particular value。

 for example， and let's try one more example of a game we could build with the hedgehog go ahead and get rid of these blocks for now。

 Let's try and build a maze for the hedgehog to try and navigate around where you're not supposed to hit any of the walls of the maze。

 for example， and I could do that by changing the backdrop。

 Let's use the backdrop to build a maze for our hedgehog。 I want the walls to be red， maybe。

And I'll go ahead and click on this line tool that's going to let me draw lines。On。The stage， oh。

 and I should you really be changing the outline to make the outline red。

So let me delete this line for now and try it again。 I want the outline of this。To be red。

 that's going to give me some red lines。And I'll go ahead and just try and build。A little maze。

For our hedgehog， the try to navigate around。And that looks all right。I'll go back to the code。

 Here's our hedgehog。 It's a little bit big for this maze right now。

 So I want to make it a little bit smaller。 I can go into size here， change the size to let's try 40。

 Yeah， that's probably a good size for our hedgehog。 And now how do I want this maze to work。 Well。

 I'll have it move via the arrow keys。 So whenever the right arrow key is pressed our hedgehog is going to change its X position by let's say5。

10 is maybe a lot for this。 So it's going to move five spaces to the right。😊。

And what do I want to do， I want to check now is the hedgehog touching a wall。

 Because if it ends up touching a wall， that's no good。So， I'll ask if。

The hedgehog is touching a color。Because the walls are all red。

So I'll grab a color using this eyedropper tool， grabbing it from the stage。

 Let's grab this red right here。So if the hedgehog is touching the color red。

 well then I want the hedgehog to just for now， let's say go to a random position on the stage。

 it's going to somehow magically disappear and reappear somewhere else。

 we'll have it go to a random position。😡，And that's what happens when I press the right arrow。

 I'm going to duplicate this whole thing by control clicking and pressing duplicate。

And do the same thing for the left arrow。But this time， we're going to change x by negative5。

And I also want the up and down arrows to work too。 So I'll duplicate once。

 Let's do this for the up arrow。 When the up arrow happens。

 I want to not change the x value by something， but change。



![](img/bc7693b7d0e89d9c107d32bfc117c7d0_2.png)

The y value。By negative 5。And one more arrow key。 Let's duplicate this one more time and use the same code for the down arrow。

This time， changing the y by actually here， it should be negative 5 and for up。

 it should be 5 because when we're going up， the y value is increasing， when we're going down。

 the y value is decreasing。 And I could test that out by pressing the up arrow and the hedgehog moves up。

 I press the down arrow， the hedgehog moves down， I press the left， it goes to the left。

 I press right， it goes to the right。 But if ever I hit， watch what happens if I hit a red wall。

The hedgehog sort of magically vanishes from where it was， and it reappears somewhere else。

 And you could decide on your own what happens when the hedgehog hits a wall。

 maybe it plays a sound effect。 maybe it does something else。

 but you could make this game however you like it。 And here I just have a hedgehog that can navigate through the mam。

 And whenever it hits a wall， it reappears somewhere else。😊。

And so these conditions give you a lot of power， the ability to ask questions and make decisions inside of your programs based on the answers to those questions。

 That's it for today for an introduction to programming with Sc。 Next time。

 we'll pick up where we left off and see what else we can do in the world of putting together these scratch blocks。

 We'll see you then。😊。