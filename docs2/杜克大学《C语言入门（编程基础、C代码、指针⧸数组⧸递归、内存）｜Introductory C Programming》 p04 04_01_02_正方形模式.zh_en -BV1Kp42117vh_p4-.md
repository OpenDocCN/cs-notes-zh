# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p04 04_01_02_正方形模式.zh_en -BV1Kp42117vh_p4-

![](img/39cf18a2d32ef7d10e631b299091bf93_0.png)

In this video， we will develop an algorithm for a particular pattern of blue and red squares on a grid。

 We're going to start with step 1， doing an instance of the problem。 And in this instance。

 I picked n equals 3。 So the first thing I'm going to do is work the problem by hand without really thinking through exactly what I'm doing。

 That is， I'm going to do it right。 But I'm not going to try to write down what I did。😊。

Once I've done that， I'm going to do step 2， where I write down exactly what I did in a step by step fashion。

The first thing I did was put a blue square at 0，0。 Then I put a red square at 0，1。

 another red square at 0，2， a blue square at 0，3， a red square at 1，1， blue at 1，2， red at 1，3。

 red at 2，2， red at 2，3， and finally a blue at 3，3。😊。



![](img/39cf18a2d32ef7d10e631b299091bf93_2.png)

Now I'd like to generalize these steps， step three of the programming process。

 and if we look at the steps， we can see there's some repetition in counting behavior。

 which is going to help us generalize these steps into an algorithm。

These first four steps have x equals 0。 Then we have a group of three steps for x equals 1。

 a group of two steps for x equals 2。 And finally， a single step for x equals 3。

 So we're repeating somewhat similar steps as we count x going from 0 to 3。

 But exactly what we do varies。 We color the squares， blue， red， red， blue for x equals 0 or red。

 blue， red for x equals 1。 So the color patterns， something we still have to figure out。 Also。

 how many steps and the y coordinate of each variesr。 Let's look at the y coordinates first。

 coming back to the colors in a minute。😊，If we look at this first group of steps。

 we see that the y coordinates go from 0 to3。 If we look at the second group of steps。

 we see that the y coordinates go from 1 to 3。 and in this third group 2 to 3。

 So it looks like in general， we're counting from x to 3。If we ignore the colors for a moment。

 we can take this group of steps and say we count from 0 to 3， calling the number that we count Y。

 then put a square of some color we'll figure out later at 0 y。

 and we can write similar steps for each of these other groups。

 And now we can use patterns in these steps to generalize our algorithm further。

Each set of steps is the same， except for the X coordinate shown in bold。

 and these vary in a nice counting pattern。That is， we can say count from0 to 3。

 call each number that we count x， and for each of those numbers we'll count from x to3 and call that Y。

 and we'll put some color square at X Y。But this is only true for n equals 3。

 A clue that we have not finished Generalizing is that the steps do not depend on n at all。

 We know that the pattern will be different for different N。

 but this is not reflected in the algorithm we wrote。 We need to make it more general。

 How could we do this， we might just realize it， but if we don't。

 we can go back and repeat steps 1 and 2。 If the pattern is hard to figure out we may have to do steps 1 and 2 many times。

So， for example， if we went back and performed step  one for n equals1， we end up with this pattern。

And when we do step 2。We write down these steps。If we go through the generalization process again。

 we see that we come up with these steps。 count from 0 to 1， call it x， count from x to 1， call it Y。

 then put a square of some color at X， Y， which is very similar to n equals 3。

 except this number has changed。 For any N， we count from 0 to n based on the pattern from our examples。

 Now， we have a more generalized algorithm。Of course。

 we need to figure out what the question marks are for the colors。



![](img/39cf18a2d32ef7d10e631b299091bf93_4.png)

To do that， we can go back to the colors from our n equals 3 example。

 We had mostly red squares with some blue squares， so we should figure out the pattern for when a square is blue。

😊，I've thrown away the red ones so we can just look at blue for a pattern。

This pattern may be a bit subtle to see with only four pieces of information。

 You may have figured it out， but if not， what could you do。Well。

 it might be easier to see with more information。Looking at n equals 5。

 we have more blue squares to consider。Now you look at the pattern and see what you come up with。

 And this is mostly your ability to look at numbers and find patterns。

If we add the X and Y coordinates together， we see that they are 0，3，3，6，6，6， and 9。

 So the pattern here is we draw a blue square。 if and only if x plus y is a multiple of three。

 Now we can go back to our algorithm and specify if x plus Y is a multiple of three。

 we put a blue square at X， Y。 Otherwise， we put a red square at X， Y。

 This algorithm looks pretty good， but we will want to do step 4 and test it shown in the next video。

😊。

![](img/39cf18a2d32ef7d10e631b299091bf93_6.png)

![](img/39cf18a2d32ef7d10e631b299091bf93_7.png)

![](img/39cf18a2d32ef7d10e631b299091bf93_8.png)