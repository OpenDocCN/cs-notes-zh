# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p112 112_07_05_碰撞检测演示.zh_en -BV1QrB6BcEWW_p112-

![](img/7e7bb4afb57eed6cf4c51bdfdd8588a6_0.png)

Now that we understand the two parts to the game flow， let's get started building the game。

The project has been partially built。 There is a ghost。

 and the camera is positioned just behind the ghost in setting up the scene。

 we moved the camera to the ghost and then moved the camera up 。75 units and back 1。5 units。

We also decreased the ghost opacity to 0。7 to be able to partially see through the ghost。

The camera's vehicle has been set to be the ghost so that the game player will be able to see what the ghost sees as it moves about the screen。

If we click on the scene。We'll see that an array of bunnies， if we scroll to the bottom。

 there's an array of bunnies， aptly titled bunnies has been created。And finally。

 if we click one bunny。So let's we'll go back to。Here we can click on。Bani。

We'll see that the procedure hop has been created for the bunny。

 This procedure just has the bunny hop up and down in place。

 And we can take a look at this just by clicking on the edit button。

 And we see all that happens is the bunny moves up， and the bunny moves back down。

Let's start with the main driver loop to have the bunnies that have not yet been collided with hopping up and down。

So let's go ahead and click on my first method。Then what we're going to do is we're going to drag in a do in order。

The reason is there's going to be two things。First。

 we'll have a while loop in which case while the bunnies haven't been collided。

 they'll hop up and down。 and eventually the ghost wolfve collided with all of them。

 and so we'll have the ghost issue some sort of essay statement complementing the player after the game has ended。

So let's go ahead and start with the while loop。So we'll drag the while into the do order。

 and we'll initially just select true as a placeholder。Now。

 what we really want is we want to enter the W loop， WO。

 there is at least one bunny that is still visible。

Let's go ahead and write a Boolean function to determine whether there's at least one bunny that is visible。

So we'll go ahead and click on scene and then add scene function。

We'll go ahead the return type because this is going to be a Boolean function。

 We had better return a Boolean true or false， and we'll go ahead and name our function， at least。

One of the bunnies。 I didn't spell that correctly， at least one of the bunnies is。Visible。

It will click going， Ok。We'll drag in a for each in tile， we'll do that right here。

Because we want to iterate through the bunnies， looking for one that is visible。

So our iterator type had better be gallery class。And we'll go ahead and select Bunny。

That sounds okay。We'll go ahead and make the item name。Bunny iterator。

And we'll associate the array to be our bunnies array。Then we can click on， okay。

What do we need to do Well， we need to check each bunny to see if it is visible。

 namely its opacity is greater than zero。To do so is going to be a multi step process。

 we'll start by dragging in an if statement。Again， we select true as a placeholder。

Then what we want to do is we'll drop down because we want to check if the bunny iterator's opacity is bigger than0。

 so we'll choose a relational decimal number since the opacity is a fraction between 0 and 1。

And we'll choose greater than。We'll put originally one in as a placeholder what we really want is we want the bunny iterators opacity and we'll compare it against the number zero。

 so we'll choose custom decimal number。And'll enter in a value of zero。

We'd like to select the iterator's opacity， but again， this is going to be a multi step process。

 So we'll start by changing this to this dot bunny。We'll click on the functions。

And we'll choose this bunny's opacity and check if this bunny's opacity is bigger than zero。

 but we don't want this bunny， but rather if we click on the dropdown。

 we can now select the bunny iterator and we have if this bunny iterator's opacity is bigger than zero。

And in the case the bunny iterator's opacity is bigger than zero。

 we can immediately go ahead and return true because we found a bunny that has an opacity greater than zero。

Lastly， we're going to drag a return statement in after the entire for each loop has ended。

 if we iterate through all of the bunnies and not a single bunny has an opacity bigger than zero。

 Well in that case， none of the bunnies are visible。 and lastly， we will go ahead and return false。

It is important to place this last return statement at the end of the function rather than in the else condition of the if。

Had we placed the return false statement into the else condition of the if statement。

 We'd be indicating that the game is over as soon as the first bunny was no longer visible。

Now that we've written our function， we can return to my first method。

We can change this bunny back to this。 And now we have a boolean condition， which we have written。

 at least one of the bunnies is visible， and we can drag that over top of the true as we want to enter the loops to have the bunny's hop while at least one of the bunnies is visible。

So now， if we enter the while loop， we know that some of the bunnies have not been collided with。

 so they need to hop。Let's go ahead and drag in a for each in together。Tile into the while loop。Here。

 what is the type again， this is going to be our bunnies。

 so we'll specify a type in the gallery and we'll go ahead and click on the bunny。And click， O。Again。

 we can name our bununny iterator。Bni。Iterator。And we can associate that bununny iterator with our bunny's array。

And what we want to do now is we want to check for each bunny if it is visible。

 so let's drag in an if statement。Into our iterator， again。

 we'll follow the exact same process we did when we were writing our function。

 we'll initially select true。And what we really want is if the bunny's opacity is the bunny iterator's opacity is bigger than0。

 So we'll go ahead and check relational because the opacity is going to be a decimal number between0 and1。

 and we'll choose the greater than。Again， we'll use one as a placeholder because we really want the iterator's opacity and we it against we'll compare for the greater than。

 we'll compare one is a placeholder against custom decimal number， which will set to be0。Now。

 just as we had done before， we need to get the bununny iterator's opacity。

 which is a couple step process。We'll go ahead and change to this dot bununny。

And we can drag this bunny's opacity over top of the one。

And now we can change this bununny to Bunny iterator。Perfect。

To invoke the bunny iterator's hop procedure， we again have to do this as a two step process。

 so go ahead and click on this bunny's procedures， will'll drag in this bunny's hop into the if statement。

 and now we can simply change this bunny to Bunny iterator。Perfect。Finally。

 after the entire while loop has ended， let's go ahead and have the ghost issue with say instruction。

 complementing the player on their accomplishments so we can change to this ghost。😊。

And now we can simply have this ghost after the while loop is over， simply say something like。

 I don't know， nice job。And we'll go ahead and make the duration of this instruction be a couple of seconds。

Let's go ahead and run the project。And as we see， the bunnies。

 which have not been collided with because we haven't done that part， all hop up and down in unison。

At this point， we are ready to create the events。Let's first create the event for collision detection。

So let's click on the initialized event listeners。And go ahead and we'll go ahead and add an event listener。

And we're going to go ahead and select position orientation， and then go ahead and add a Col。

 start listener。Now， what we need to do is we're going to need to specify what object could be colliding with what object。

So for the first group， we just want that to be the ghost， so we'll specify for set A a custom array。

And then for set B， which is the objects being collided with， we'll specify this dot bunnies。

And for the Collider will create an array which is going to consist only of this ghost。

And we'll go ahead and click on， O。And what gets created is we have two collids。

 a collision between two objects， the first is going to be only the ghost。

 and the second is going to be any of the objects in our bunny array。

As we noted in the introductory presentation， we need to iterate through the bunny array for which bunny collided with the ghost。

 So what we're going to do in here is we're going to drag in a for each in。Tile into the collision。

And we're going to go iterate through our array of bunnies。So the type will be gallery class。

 and then we'll specify Bny。Again， we can name the item name Bunny。Iterator。

And the array will be our array of bunnies。Perfect。Now， as we iterate through our bunny。

 our array of bunnies， we're going want to check is the object from set B。

 the particular bunny that collided with， so what we need is we need an if statement。

Into our iteration and all again， select true as a placeholder。

We then change the true to relational S thing testing for equality to be able to test whether the two objects are equal for the first object。

 we'll test whether it's a bunny iterator。 and we want to see if the bunny iterator is the S thing。

 So what we'll do is we'll first put just this bunny as a placeholder for the second thing。Next。

 we can drag the item from or the S thing from set B over top of this bunny。



![](img/7e7bb4afb57eed6cf4c51bdfdd8588a6_2.png)

And we'll see if the iterator is the thing that collided with。If there is a match。

 what we want is the bunny iterator needs to change its opacity to zero， then move down 10 units。

So let's go ahead and drag in a do in order into the if because we're going to do two things in a row in order。

We can't directly have the bunny iterator do any instructions， so we'll first。

 again as a placeholder to click this bunny。We'll drag in this bunnies set opacity to set the opacity to zero。

Right here。So we'll first set the opacities to be zero。Next， we want to get the bunny out of the way。

 so let's go ahead and move the bunny down 10 units。So we'll move the bunny down。10 units。

And let's go ahead and change the duration of each instruction to be zero。

 so they happen instantaneously。 So we'll just go ahead and make the duration be0。

So once a collision happens， the bunny becomes invisible。And the duration here， again， for the move。

 will again be zero so it immediately gets out of the way。Finally。

 we don't want this bunny to become invisible， but rather the bunny iterator to become invisible and rather again here the bununny iterator has to move down 10 units。

This should complete the handling of the collision event。Lastly。

 we need to add a key pressed event to handle the game player pressing the left right and up arrows。

 so let's again click on add event listener and we'll click on keyboard and add a key pressed listener。

And what we're going to need to do is to handle the code for each of the three arrow keys。

So we're going to need an if statement to check which key was clicked。

 so we'll start by having an if statement right here。

We'll put through here and then we have over here， we have a check to see which key was pressed and we can drag this event dot is key。



![](img/7e7bb4afb57eed6cf4c51bdfdd8588a6_4.png)

On top of the true， and we can check if the left arrow key was pressed。Now。

If the left key was pressed， let's have the ghost turn left point01 revolutions。

So we'll change this dot bunny to this dot ghost。And we can have this ghost。Turn left。

We'll put it right here into the then。We'll turn it left。Cost and decimal number，0。01 revolutions。

And let's have it happen rather quickly， so we'll make the duration be just maybe a  tenth0 of a second。

0。1 seconds。Perfect。In the L's case， let's add another if statement。Again， after we drag it in。

 we'll select true as a placeholder and just as we did test for the left key。

 let's test for if the key pressed was the right arrow key， so again we'll check the is key。

And we'll check， is it the arrow and was it the right arrow？And if the user pressed the right arrow。

 let's have the ghost turn right。So we'll drag this ghost turn， we'll specify right。

 and again we'll do the exact same amount of 0。01 units。And again。

 we'll make this happen rather quickly by making the duration be just a tenth of a second。Again。

 if the left arrow key wasn't pressed and the right arrow key wasn't pressed。

 we need to check if the up arrow key was pressed， so we'll scroll down to the else here。

 We'll drag in one more if statement。Select true as a placeholder。

 and then we'll check again is the key pressed over here， the up arrow key。

And we'll select the up arrow key， and if the upper arrow key was pressed。

 let's have the ghost move forward 。05 units。So we'll again， ask the ghost to move。Forward。0。

05 units。And again， we'll make this happen rather quickly by making the duration just be a1t of a second。

Now， to be able to have the event happen while the arrow key is pressed rather than just running once when the key is pressed。

 we can click on the Add detail button here， we can select the multiple event policy and just say we'd like to combine key press。

Next， I think we're done and ready to click the Run button to try and run our projects。Now。

 let's try and collide with the bunnies。We collided with one。Who， we collided with another one。Wow。

 this is fun。