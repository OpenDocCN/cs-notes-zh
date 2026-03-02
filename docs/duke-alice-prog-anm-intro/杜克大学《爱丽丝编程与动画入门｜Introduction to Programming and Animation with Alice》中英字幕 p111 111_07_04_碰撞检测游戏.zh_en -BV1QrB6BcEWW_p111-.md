# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p111 111_07_04_碰撞检测游戏.zh_en -BV1QrB6BcEWW_p111-

![](img/67103cee7a388c628118d8c9c64ca707_0.png)

The idea of this game is for a player of the game to steer a ghost into colliding with several bunnies。

Before building this project， it's very important to understand the game flow In many games。

 the game flow becomes quite complicated and we'll be spending some time explaining how the game should work。

As in nearly every game， there are two parts to the gameplay。

 The first part is what we call the main driver loop。This is generally the code in my first method。

 the code that runs when we start the project。And the second part is the events。

 That is the handling of the interactions between the player and the game。

 What should happen when the ghost collides with a bunny。

 What should happen when the player clicks on a key。 Let's start with the main driver loop。

There will be two parts。First， there's a while the game has not ended Lo。

 followed by a congratulatory message to the player。What does it mean for the game not to have ended。

 Well， the game hasn't ended as long as at least one of the bunnies hasn't been collided with。

As long as a game should continue， we simultaneously iterate through the array of bunnies for each bunny in the array。

 if that bunny hasn't yet been collided with， we can have that bunny jump up and down。Now。

 let's look at the events。There' are going to be two events。

 the first event will be when the ghost collides with a bunny。

And the second event will be when the game player presses a key to try and steer the ghost。

For the collision event， Alice provides the S thing that the ghost collided with。

We know that the ghost must have collided with a bunny。

 We need to iterate through all of the bunnies in our array。 And when we find the match。

 we make that bunny invisible and move it below the ground。The last event is the key pressed event。

 If the game player presses the left key， we should ask the ghost to turn a little bit to its left。

 If the player presses the right arrow key， we should ask the ghost to turn to its right。And finally。

 if the player presses the up arrow key， we should ask the ghost to move forward。

This completes the three aspects of the game。 The bass driver loop。

 which has the bunnies hop up and down while they haven't yet been collided with and the two events。

 one to handle the collision between the ghost and a bunny。

 and the second to move the ghost in response to the player， clicking on the directional arrow keys。

Now let's code it。

![](img/67103cee7a388c628118d8c9c64ca707_2.png)