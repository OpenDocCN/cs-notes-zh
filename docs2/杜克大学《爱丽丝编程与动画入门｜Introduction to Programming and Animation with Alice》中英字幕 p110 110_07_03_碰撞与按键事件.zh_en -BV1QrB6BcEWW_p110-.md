# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p110 110_07_03_碰撞与按键事件.zh_en -BV1QrB6BcEWW_p110-

![](img/2ffed3215a1a012e1de8844628145ecb_0.png)

In this week， we are going to be building a new type of game。

 one that builds off with the ability to process collisions。 In particular。

 we are going to be designing and building a game where the player of the game will try to steer a ghost into several bunnies。

😊，When the ghost collides with a bunny， the bunny will disappear。

The goal of the game will be to collide with all of the bunnies To create this game。

 we will need to learn about two new types of events that Alice has。😊。

First is the collision detection event。There are two important parts of a collision。

The colider and the coide， Both of these need to be in an array。

 as there are potentially multiple coliiders and potentially multiple coides。

 Alice lets you build two arrays。 The first array is referred to as set A。

 and the second array is referred to as set B。In this example， we have one collider。

 so we will create an array with just the ghost。Alice refers to this first array as set A。

We have several colliddes， all bunnies。 So all the bunnies will be put into one array。

 the second array listed。This array is originally built as a seen property array。

 so we can just refer to it here。In the collision event， Alice refers to this second array as set B。

When there's a collision， the colider is the colliding object from set A。😊。

Alice refers to the Collider as event。ge S thing from Seday。It will be the ghost。

 as the ghost was the only object in the first array。The second colliding object， the collide E。

 is an object from set B， a bunny from the array of 10 bunnies。

 Alice refers to the collidide E as event dot get S thing from set B。

Suppose we wanted to make the bunny that the ghost collided with move down 10 units below the ground。

Alice has a subtle problem。The Coliders and Colids are considered by Alice to be as things。

And while S things include bipeds， such as bunnies and ghosts。

 they also include things like the ground， which cannot be moved。Thus。

 if we'd like the colled bunny to move down， we need to iterate through the bunnies and once we find which bunny was collided with。

 we can move that bunny down 10 units。The other event we'll use is the Key press event。

With this event， we'll need to add an if statement for each key the game player might have pressed。

In this example， we're processing three keys。 If the player presses the left arrow key。

 we'll have the ghost move to its left one unit。If the player presses the right arrow key。

 we'd like to have the ghost move to its right one unit。And finally。

 if the player presses the up arrow key， we'll have the ghost move forward。

Let's get started learning the details about these events。



![](img/2ffed3215a1a012e1de8844628145ecb_2.png)