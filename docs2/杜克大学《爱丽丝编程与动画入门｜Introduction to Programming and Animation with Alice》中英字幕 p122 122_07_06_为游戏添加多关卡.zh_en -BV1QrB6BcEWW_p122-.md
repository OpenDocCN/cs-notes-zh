# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p122 122_07_06_为游戏添加多关卡.zh_en -BV1QrB6BcEWW_p122-

![](img/22b3a9094b690bfc00d6d1457d1f67a5_0.png)

For this last variation on the collision gain， it might be fun to add multiple levels where the later levels are harder than the earlier levels。

In the example， we're going to build， there are just going to be two levels。

 but you could easily imagine that there could be three or  four。

 even 100 different levels for the later levels， we could require the player to get a higher score than5。

 or maybe we could add more obstacles or faster obstacles。

 or are actually going to do in the harder level is to have the bunnies randomly move as they hop。

It is much easier to collide with a bunny that's hopping in place than one that is moving around as it hops。

There are two conceptually challenging parts to handling multiple levels in a game。

The first is the levels themselves。Every part of the game will need to know what level the player is on。

The easiest way is with a scene property or variable。

 we can simply create a scene property level which can get set to one initially。

 indicating the players at level1。The second challenge is that once a player successfully completes one level。

 everything needs to be set back up。 We'll want to reset the timer and possibly reset the player's score。

What is harder to do is to get all of the objects in the scene back to their original positions。

The ghost needs to be returned to its initial position。

 the bunnies need to be returned to their original positions and turned back to white and have their opacity set back to one。

 and the obstacles need to be returned to their original positions。

To move the bunnies back to their starting positions。

 we're going to use a nifty programming trick as part of scene setup。

 we added an object marker for each bunny。Then we created another array containing each of the object markers。

 If Bny is in location 0 of the bunny's array， we'll make sure to place Bunny marker in location 0 of the bununny starting positions array。

 If Bunny 2 is in location one of the bunny's array。

 we'll make sure to place Bunny2 marker in location  one of the bununny starting positions array。😊。

What we now have is a pair of parallel arrays。 we'll need to look at a new way to iterate through arrays using a Y loop also known as an array indexing loop instead of a for each in or each in together iterator。

😡，The reason we need to use a while loop is that we have to simultaneously access location zero of two arrays。

 and iterators go through one array at a time。We'll use another whole number variable here called index as we set it to zero。

 we can have element0 from the bunnie's array， move and orient to element zero from the bununny starting position array。

And this while loop approach， while not quite as elegant as the iterators。

 will allow us to move all 10 bunnies back to their original positions and set their paint back to white and reset their opacities back to one。

After resetting the bindings back to their original positions in the initial scene and updating the level。

 we should be all set to play again。

![](img/22b3a9094b690bfc00d6d1457d1f67a5_2.png)