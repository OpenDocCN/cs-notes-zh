# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p06 06_01_04_绘制矩形.zh_en -BV1Kp42117vh_p6-

![](img/8ac58589fce64ac105e35405f33e2bf5_0.png)

In this video， we're going to step through the process of designing an algorithm in the context of the following problem。

 Here we have a 16 by 16 grid， and we're interested in drawing a blue rectangle of particular height and width located at a particular starting X。

 Y location。 So to begin with， we'll just look at a specific instance of this problem。

 Let's suppose that the starting point should have the x and y coordinates 7，9。

 The width of the rectangle should be 8， and the height of the rectangle should be 4。😊，Now。

 to do an instance of the problem， were going to look at our starting point and simply draw that rectangle。

 You can assume that you have some kind of a blue pen。

 and you're just going to draw this rectangle as the problem specified。

Now we need to take a step back and write down what we just did。

The first thing that we did was start at 0。79 and draw a horizontal line， the length of 8。Next。

 we draw another horizontal line of length8， starting at 710。

A third horizontal line that starts1 point higher and finally a fourth horizontal line starting at 712。

Let's step away from the drawing and look at the actual lines we've written out。

 describing what we did。You'll notice that this is a very repetitive process。

 The only difference in these four steps is the Y coordinate。

 The Y coordinate starts at 9 and stops at 12。The reason that we start at 9 is because that's the starting y coordinate of our rectangle。

 The reason we stop at 12 is because we're interested in drawing a rectangle that has height 4。

 So we're going to draw four horizontal lines， stopping at y plus height-1。

Now that we've inspected these four steps。Let's try to write an algorithm that will generalize them。

Recall that we were counting up from y to the value Y plus height。 Now。

 this was actually an exclusive y plus height because we counted 9，10，11，12。

 We did not actually go all the way up to 13， which is y plus height。

 We're going to call this number I。 And then for each of those values。

 we're going to draw a horizontal line of length 8， starting at the coordinate 7 I。

Why are we drawing a line of length 8， That's because it's the width of the rectangle so we can go ahead and call this width。

This way， we will be able to use our algorithm for rectangles of different sizes。

And why are we starting at the Xlocation7？Because that's our beginning X coordinate。

So we can call that X。This way， our algorithm will accommodate all values of x。Now。

 this part seems a little bit complicated。 We're going to draw a horizontal line of length width。

 starting at X I。 It's actually fine for this step to seem a little bit complicated。

 We'll just call that a different programming problem。

 We're going to assume that we either already know how to draw a horizontal line of length width。

 starting at X I。 or we can solve this as its own programming problem beginning with steps 1 through 4 all over again For this exercise。

 We're just going to assume we know how to perform this step。

The last thing we want to do is add a little bit more precision because we wanted the line to be blue。

 So our algorithm needs to specifically say that we are drawing a blue line of length width。

 starting at the location X， I。Test this algorithm for yourself， give yourself a value of X， Y。

 a width， and a height that you want to test out and see whether this works for you。As a final note。

 some values of X， Y， width and height will cause you to draw off the grid。 In this case。

 we're going to assume that nothing special happens and that doing nothing in response to this is the desired behavior。

 Later on， we'll look at ways of handling errors and corner cases in a more sophisticated manner。



![](img/8ac58589fce64ac105e35405f33e2bf5_2.png)