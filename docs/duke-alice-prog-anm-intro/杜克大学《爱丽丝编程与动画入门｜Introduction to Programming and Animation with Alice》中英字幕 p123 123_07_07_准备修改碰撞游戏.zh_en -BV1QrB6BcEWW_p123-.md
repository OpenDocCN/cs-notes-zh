# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p123 123_07_07_准备修改碰撞游戏.zh_en -BV1QrB6BcEWW_p123-

![](img/16b739daa0227055e6e88b78dfa79438_0.png)

We need to make several changes to our collision game with obstacles to allow for multiple levels。

 we have already discussed the need to add a scene property to keep track of the level。

We have also described the process of resetting the bunnies， obstacles and ghost。

 We need to have the bunny do a hop when the game player is playing level 1， the lower level。

 If the player succeeds in level 1 and moves on to level 2。

 the bunnienys should do a wander hop instead of an up and down hop。

That makes it harder to collide with the bunny。 A more tricky change is that we need to put an outer while loop around each gameplay。

 while the level is one or two， and the user has yet to lose or win the game play one iteration of the game。

 This needs to be placed around the code in the scene activation event where the obstacles move around randomly。

😊，It also needs to be placed around the main while loop in my first method。

The final change we need to do is to reposition the bunny's obstacles and ghost and reset the score and timer if the player successfully completes a level。

 earning a score of at least 5。 If the player did not successfully complete a level。

 we set the level to 0， indicating that the player is lost。

Will'll need to place this code into my first method after the players tried for 30 seconds to collide with the blue and white bunnies。

Let's get started， modifying the game。

![](img/16b739daa0227055e6e88b78dfa79438_2.png)