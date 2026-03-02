# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p116 116_07_05_随机给兔子着色.zh_en -BV1QrB6BcEWW_p116-

![](img/42aeb60293af4e8826adc869eade8f25_0.png)

In the next variation of our bunny collision game， we'll explore having different point values for differently colored bunnies。

Perhaps colliding with blue bunnies will give the player two points。

 whereas colliding with a red bunny will lead to a loss of one point for the player。😊。

Bunny's painted white can continue to lead to one point for the player。

To make this modification work， we'll need to make four changes to our game。One。

 we need to write a procedure to sometimes change a bunny's paint and call that procedure from bunny。

hop。2， we redefine what it means to win the game。 Now。

 it should be that player score is greater than or equal to5。

Three will add a parameter amount to increase to allow an increase to the player score by amount。

 and four， we need to change the collision detection to pass a value of minus1。

1 or two to increase or decrease based on the pain of the bunny that was collided with。

The challenging one of these tasks is the first。Which is the one we'll cover in this session。

How should we go about sometimes changing a bunny's paint。Certainly。

 we don't want to change the paint color every time the bunny hops as that will be too wild。

Maybe once every four times or so， a bunny hops， it should change its color。How can we do this？Well。

 the most straightforward way is to have Alices generate a random number between0 and3。

Every time Alice generates a0 zero， we can go ahead and change the bunny's paint。

If Alice generates a one， two， or three， we won't change the bunny's paint。

The next challenge is how to actually change the bununny's paint。

A first idea might be to generate a random whole number between 0 and 2。If the number is zero。

 change the bunny's paint to white。If the number is1， change the bunny's paint to red。

 and if the number is 2， change the paint to blue。The problem with this approach is that if a zero is generated and the bunny was already white。

 then this won't lead to the bunny changing its color at all。

What we instead need to do is to repeatedly generate random numbers until a non0 number is obtained。

Then we can change the buddy's color to red if a one is obtained or blue if a two is obtained。

This algorithm can be formally expressed as follows。

 set a variable old paint to be the current paint color of the bunny。

Set another variable new paint to be old paint to enter the while loop。

 while old paint is the same as new paint， generate a random number and update new paint accordingly。

When we exit the while loop， new paint will be different from old paint so we can set the bunny's paint to be new paint effectively changing the bunny's paint。

 Wow， that was a lot of work。 just to sometimes change the bunny's paint， but that should work well。

 And we are now ready to introduce different colors of bunnies into the cane。 Let's do it。😊。



![](img/42aeb60293af4e8826adc869eade8f25_2.png)