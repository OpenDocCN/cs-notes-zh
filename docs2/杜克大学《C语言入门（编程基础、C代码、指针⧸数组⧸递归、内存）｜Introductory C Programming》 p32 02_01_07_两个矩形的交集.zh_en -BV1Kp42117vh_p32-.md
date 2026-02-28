# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p32 02_01_07_两个矩形的交集.zh_en -BV1Kp42117vh_p32-

![](img/f32d0aabf8425d119c3d7dbfdae24709_0.png)

As an example of the seven steps， let us consider the problem of finding the intersection of two rectangles。

 Well deal with only rectangles whose edges are horizontal and vertical， making things much simpler。

To do this problem， you need a bit of domain knowledge， such as what a rectangle is。

 which you may recall is a four sided shape with adjacent sides at right angles to each other。

 and what it means to find the intersection of two rectangles。

 which is finding the area that is inside both rectangles。

Step one is to do an instance of the problem。 We've started here with a blank Cartesian plane on which we can precisely draw rectangles。

Now I've picked one rectangle from minus41 to 8，6。Next， I've picked another rectangle。

 which goes from 1 minus1 to 4，7。The intersection of these two rectangles is highlighted in green。

Which we can see goes from 1，1 to 4，6。We'd like to write down exactly what we did to figure this out。

 But our inclination might just be to say that we looked at the answer in our drawing。

 This happens frequently。 You just know what you did。

 but you have trouble thinking through it step by step。When this happens。

 a good idea is to work through another instance and try to think about what you are doing。

Here we've taken away the grid lines so that we can't just read the coordinates off our final drawing。

For my first rectangle， I chose minus2，1 and 6，3。Then I chose1 minus1 to 4，4 for my second rectangle。

The intersection here is in green， but what are the coordinates of its corners？

This rectangle goes from minus11 to 43。Now let's write down exactly what we just did。

The first question we should answer here is how did we represent a rectangle as numbers？

The answer is that a rectangle is four integers， left， bottom， right and top。Next。

 we need to think about what steps we took to come up with this answer。First。

 I figured out that the left edge has an x coordinate of -1。Next。

 I figured out that the bottom edge has a Y coordinate of one。

Then I figured out that the right edge has an x coordinate of four。Finally。

 I figured out that the top edge has a Y coordinate of three。My answer was the rectangle minus1，1，24。

3。Okay， now we're ready to generalize these steps to any pair of rectangles。

Why did we pick -1 for the left side of the answer， We might think this was because it's R2s left。

 but will it always be R 2s left， No， it was only R 2's left this time because R 2's left is larger than R 1's left。

More generally， it will be the maximum of R1's left and R2's left。

What if we had not cut the subtlety now， We should catch it later。

 either in step 4 when we test our algorithm by hand or in step 6。

 when we run test cases on our code。 If we catch it later， we would come back to step 3。

 correct the algorithm and redo the later steps。So generally。

 our answers left side will be the maximum of two input rectangles left sides。What about the bottom。

 Why was it one。Again， we might think that it was because it is R1's bottom。

 but this runs into the same pitfall we just discussed。

 It is actually the larger of R1's bottom and R2's bottom。

We then go through similar thinking for the right， but this is the minimum。

 not the maximum of the two input rectangles right sides。Lastly。

 the top is the minimum of the two input rectangles tops。

Let's write that down a little bit more explicitly as directions。 We will make a rectangle。

 which we will call ants with the sides determined by the maximum or minimum of the input rectangles sides。

 as we just discussed。And then the rectangle ants， which we just made， is our answer。Next。

 we should test our algorithm。 It seems pretty straightforward。

 So what could possibly go wrong For one thing， the only inputs that we used to construct it had the same general shape。

 R 1 was wider than R 2 and R 2 was taller than R 1。

 If we had made any of the mistakes we discussed earlier in step 3。

 we would not have caught them yet。A slightly more subtle case exists that we have not yet accounted for。

 It is possible that the rectangles might not intersect。

 What does the algorithm produce for this case。What should it produce for this case。

 It really should produce no such answer。 So we need some way to represent that。



![](img/f32d0aabf8425d119c3d7dbfdae24709_2.png)