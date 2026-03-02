# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p138 138_08_05_综合整合.zh_en -BV1QrB6BcEWW_p138-

![](img/2f63c2e0734ffdbf9826a26663caeb97_0.png)

![](img/2f63c2e0734ffdbf9826a26663caeb97_1.png)

In this last session， we're going to combine the three games together with the scene changing into a single build your own adventure game To build this game。

 we have two problems。 The first is that the game player should only be allowed to steer the dog when the player is in the initial scene and the player has to steer the dog into one of the gates or to the ti。

The player should not be allowed to steer the dog when the player is playing one of the games。

 This is a change from our early adventure game when we were allowed to steer the dog in all of the different scenes。

The second problem is that all three of the games involve clicking with the mouse。

 The memory game requires the game player to click on the bunnies in the order they turn purple。

 The logic game requires the game player to click on the bells to determine the secret code。

 and the matching game requires the game player to click on the cards。

 Alice should only process the clicking of the different objects when the game player is playing that particular game。

😊，Fortunately， one clever solution can solve both problems。

The basic idea is that we have four scenes。 Alice should only process the appropriate events for each scene。

 ignoring the other events for the other scenes for the games the player is not presently playing。

All we need to do is to create one scene level text string variable。

 We can call it game and set it to the string initial。

 If the user steers the dog to collide with the right gate。

 which is where we'll have the game player playing the logic game， we can set the game to be logic。😊。

If the user finishes playing a game and clicks on the return button。

 we can set gain back to be the text string initial again。

 when the game player in the initial scene and steers the dog into the middle gate。

 where the card matching game is， we can set the game variable to the string match。

If the game player in the initial scene and steers the dog into the left gate。

 which is where the memory game is， we can change the game variable to memory。

Then when the game player clicks the mouse， all Alice needs to do is to check which game is being played and process the mouse clicks for that game and using the same technique。

 we only allow the Dalmatian to be steered when in the initial scene。 That is one powerful variable。

 With this in mind， we invite you to play the sample build your own adventure game。

 We have prebuilt this game from the four individual pieces。 The scene changing the memory。

 logic and matching games and added a texturing variable to process game player mouse clicks and a of steering correctly。

😊，Because there is nothing new here， we won't go through the process of building the game from scratch。

Try to win each of the three games and get the Adelaide bust to appear。



![](img/2f63c2e0734ffdbf9826a26663caeb97_3.png)