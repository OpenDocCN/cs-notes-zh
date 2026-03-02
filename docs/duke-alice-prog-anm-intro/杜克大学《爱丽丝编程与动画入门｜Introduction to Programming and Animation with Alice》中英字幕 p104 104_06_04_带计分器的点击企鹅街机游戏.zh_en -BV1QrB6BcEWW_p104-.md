# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p104 104_06_04_带计分器的点击企鹅街机游戏.zh_en -BV1QrB6BcEWW_p104-

![](img/99f77000481bff5855a3fdc5e2a42320_0.png)

Now that we've learned about scores， we can modify our click of penguin game。Remember。

 as the game stands now， the goal of the game is to click on each of the nine penguins。In reality。

 the goal of the game is to click 10 penguins within a set time period in this demonstration we'll build the game that plays until the player successfully clicks10 penguins in a later demonstration we'll add a time element。

Our starting project is where we left off from the last demonstration。

We're going to need to make several changes。The first is to add a score。

Second will be to change the mouse clicked event from turning the clicked penguin red to increasing the score。

Third will be to enter the while loop while the player has yet to win。In other words。

 while the player has yet to successfully click 10 penguins。Let's get started。

The first step is to create a score。To do so， let's click on the setup scene。

We go ahead and click on the Shapes textex tab。We then drag a new text model over the lower right hand side of the screen。

Sadly， Alice does not place a yellow bounding box around the text model as we move it。

The reason is is that Alice does not know yet what we want the text to say。

 so Alice does not know the size of the bounding box。So let's put it right about right there。

Let's go ahead and name our text model， score。😡，Perfect。I choose to set the paint， not from white。

 but to blue， which should be a good contrast on the snowy scene。

Then we're going to head to set the value not to hello， but to custom text string。

 and the string we're going to use is the string0。That looks all set blue， value of zero。

 and we'll go ahead and click on okay。Because in the running of this project。

 we're going to change the camera to provide a view from above。

 we need to issue a one shot to turn the score back a quarter revolution。

So let's go ahead and have the scorer turn。Backward。A quarter revolution。Great。

 that me pull this score， that may pull it a little bit closer to us right over there。

 it should see just so。Finally， we need to add a variable or property to keep track of the player score。

So let's go ahead and click on the editit code。Next， we'll click on the scene tab。And finally。

 we'll click on the text model。Now we can go ahead and add a text model property。

We'll specify the type to be。Well specify， excuse me， the type to be a whole number。

 we make sure that the variable field is checked because we're going to be changing the player score。

We'll name the variable player score。And then we'll initialize it to the value0。Finally。

 we'll click on OK creatingreating our variableable or property。

Let's next write a procedure for increasing the score。So let's click on the yellow hexagon。

And we'll go down to the text model and go ahead and add a text model procedure。

And let's name our procedure increase， as we'll be increasing the score。Okay。

 we'll go ahead by dragging in a do in order tile。As we described。

 we're going to need to do a little bit of double bookkeeping。First。

 we're going to need to increase the player score by one。

So let's go ahead and drag in the set player score into our do order。😡。

And will initially set the player score just to be the value of the player score。

So we can go ahead from here and click on the little drop arrow and invoke math and then say this player score plus a value of one。

Next， we need to go ahead and update the display。We do this by dragging in the text field to do set value。

And we're initially going to set it to be the custom text string of the empty string。

 so we will immediately click on， okay， without typing a thing。

 and we set the value to be the null or empty string。Finally。

 we'll click on the drop down and we'll invoke the plus operation。

 which in the case of a string is to append and we will append the whole number。Player score。

After creating the score， we need to go ahead and update the event。

We start by clicking on the initialized Even listeners tab。Now， currently when the mouse is clicked。

 we set the paint to be red。Instead of painting the clicked penguin red。

 we just wish to call the increased procedure of the score。

So let's start by dragging turning the penguin red instruction to the trash。

And we'll go ahead and change this to this score。And。

We will drag the increased procedure into the mouse clicked event。Finally。

 we need to change the condition of the while loop in my first method。

 so let's go ahead and click on my first method。We don't want the function。

 at least one of the penguins is white。Let's create a new scene function called Game is not over。

So we'll go ahead to the scene and create a new scene function called。Game is not over。And it too。

 will return a booleion。This function is easy to write。If the player score is less than 10。

 we return true。Otherwise， we return false。So let's start by dragging in an if statement。

And we'll just select true as a placeholder。We'll then go ahead and drop down and choose relational whole numbers。

And choose the first number less than the other one。For the first number。

 we'll just store one as a placeholder， and for the second number。

 we'll choose a custom hold number to be 10。Great。Next， we click on this dot score。

Let's scroll down and choose this score。We click on the functionss tab。And we can drag。

The get player score over top of the one。If this score's player score is less than 10。

We should go ahead， and。Return true because the game is not over。Otherwise。

 we should go ahead and return false。

![](img/99f77000481bff5855a3fdc5e2a42320_2.png)

Now， let's go back to my first method。Instead of invoking the Boolean function。

 at least one of the penguins is white。 let's instead change to this and select the function。

 game is not over。And we'll drag that right over top of the boolean condition。Now。

 let's go ahead and play the game。So click on the run。Ah， great。

 able to play the game until we click on 10 penguins。Now， I've noticed a slight error。

 If we see that one of the penguins is coming up right over that 10。

 So let's go ahead back to the beginning and go back to the set up the scene。

 and let's try and drag this0 just a little bit out of the way and maybe a little bit over here so that the。

Penguin is less likely to come up over top of it。Now。

 there are two other slight errors you might wish to think about how to fix。First。

 it is possible if you are really fast to double click on a penguin， increasing the score by two。

Second， it is possible to continue to click on the penguins after you've clicked the ten0 penguins。

Ending the game。How might you correct these minor bugs？

