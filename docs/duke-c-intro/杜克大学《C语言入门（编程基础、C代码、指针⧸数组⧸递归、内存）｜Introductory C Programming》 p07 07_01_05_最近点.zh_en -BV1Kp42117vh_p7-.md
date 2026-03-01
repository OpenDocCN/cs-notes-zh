# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p07 07_01_05_最近点.zh_en -BV1Kp42117vh_p7-

![](img/a585467d9ba27952bc304c3ec8ed0025_0.png)

In this video， we're going to work the problem of finding the closest point out of a set of points to some other given point。

 We'll start by doing an instance of this problem by ourselvesselve To do that。

 I've begun by drawing a Cartesian coordinate grid and choosing a set S of point。

 which you can see here。 another point P， which is one negative1。

 We're going to find the point in s that is closest to P。

The first thing I'm going to do is to draw my points on my Cartesian plane。

 Now I can begin working through this。First， I need some domain knowledge。

 I need the mathematical definition of the distance between two points。

 which if you don't remember is the difference in the x values squared plus the difference in the y values squared。

 and then we take the square root of that。So the way that I would do this is calculate the distance between P and 27。

 and I would come up with 8。06。Then I would compute the distance between P and 105 and come up with 10。

82。The first point was closer。 So I'm going to keep that。This point is 7。07 away。

 So I'm going to keep the new closest point so far。This point is 7。81 away。

 so 8 negative2 is still closer。This point is 5。66 away， so we have a new closest point。

This point is 9。06 away， so negative 3， negative 5 is closer。This point is 9。22 away， so negative 3。

 negative5 is still closer。And there are no more points to test。

 so negative 3 negative5 is my answer to which point is closest to one negative1。

If we visually inspect this picture， that seems pretty reasonable， it looks like the closest。

Now I write down exactly what I just did。 I computed one squared plus 8 squared。

 took the square root and got about 8。06。

![](img/a585467d9ba27952bc304c3ec8ed0025_2.png)

I computed the square root of 9 squared plus 6 squared and got 10。82， and I compared 10。82 to 8。

06 and said 8。06 is smaller。I computed the square root of 7 squared plus negative 1 squared and got 7。

07， and I compared 7。07 to 8。06 and said 7。07 is smaller。 so this is a better choice。

Then I compared the square root of6 squared plus negative5 squared。And got 7。81。I compared 7。

81 with 7。07 and got that 7。07 was smaller and so on and so on and so on。

And then when I got to the end， I gave my answer as negative 3， negative 5。

These seem like reasonable steps， but。We actually glossed over something that we did in the process of writing these steps down。

 It is very important that we write our steps down carefully， because if we're missing steps。

 we're going to miss them when we go to generalize and end up having a problem。

Here's an important clue。Look at this step where we give an answer of negative 3 negative 5。

 When we go to generalize， we're going to ask， why did we use negative 3 negative 5。

 Then we're going to notice we don't see negative 3， negative 5 anywhere else。

The fact that our answer seemingly comes out of nowhere indicates that we're missing something。

 We did some step without consciously thinking about it and writing it down。

 and we need to fix that before we go on。 We may notice this Now。

 we may notice it when we go to generalize， in which case we need to come back and fix it。

Why was it that we picked negative3 negative5 as our answer here？Reviewing our last steps。

 the last remaining dotted line of length 5。66 is what we were keeping track of Our best choice so far。

 we started at 。27， Then we went around and updated it each time we found a shorter distance。

 However， as we wrote our steps， we never mentioned the point that went with the shortest distance so far。

We should go back and fix our steps to include that。 We start with a best choice of 27。

 When we got to 8 negative 2 and decided 7。07 was smaller。

 we updated our closest point to 8 negative 2。 When we got to negative 3 negative 5 and found that 5。

66 was smaller。 We updated our best choice to negative 3 negative 5。 Now。

 this answer the end makes sense。 It is whatever our best choice was last。

Now we're ready to generalize which we'll do in the next video。

