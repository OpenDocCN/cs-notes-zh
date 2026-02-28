# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p08 08_01_06_泛化最近点问题.zh_en -BV1Kp42117vh_p8-

![](img/1b602fc17e65087040071ed45ee08ef1_0.png)

In the previous video， we carefully wrote down the steps we followed in working a specific case by hand。

 In this video， we generalized the steps to finding the closest point。😊，Looking at our steps。

 some of them are similar， but we need to make them match up。

 Each of these colored boxes contains similar steps。 First， a computation than a comparison。

We also have some steps we only do sometimes， and we need to figure out under what conditions we do them。

We also have some steps we only do at the start and the end。

 and we're going to need to generalize the numbers in those。

So the first thing let's do is make these similar steps match up。

Why are we computing 9 squared plus 6 squared here，7 squared plus negative 1 squared next， and so on。

If we look at our picture， the9 comes from Delta x and the 6 comes from Delta y。

 the difference between the 010，5 instead S and one negative1， the point P。

The same is true for all of these other numbers， the differences in x and y between points S and P。

So we might rewrite all of these steps。To have the points S1， S2， et cetera， up to S6。

We'll call the first point S0 when we get to the starting step。

 programmers often like to start counting from zero。

The first substitution gives us S1s x minus ps x quantity squared。

 plus S1s y minus ps y quantity squared， then the square root of the whole thing。Now。

 the result of this computation won't always be 10。82 or 7。07。

 so we should give these a name such as current distance， but when we do this。

 we're going to have to keep track of each time we use this number and update them too。That is。

 if we change the first occurrence of 10。82 to current distance。

 then we need to make this line compare current distance to 8。06。

But some of these numbers are used in other ways， so these are going to need a different name。

Here we've replaced the value for each computation with current distance。

Notice that the only times we update the best choice are when current distance is smaller。

 that means we must have been keeping track of the best distance so far。

 which we now need to update as well。Now we update the best distance when the current distance is smaller and we can use the value of best distance for comparison with future computations。

Let's look at the first 8。06 we compute。And consider the other places it occurs。

The computation can be achieved like the others using S0， since this is our first computation。

 it might as well be the best so far， then we can replace the other instance with best distance making the steps match。

To continue generalizing， let's look at the points for best choice，2，7，8。

 negative2 and negative 3 negative 5。 Each of these is the particular point we're looking at so we can replace those with S 0。

 S2 and S4。Recall that we only updated the best choice when the current distance was smaller。

 we can make each of these steps the same by including instructions to compare current distance and best distance each time。

 but only update best distance if current distance is smaller。Now。

 we do the same steps for each of the points。 Each colored box is the same as the others。

 except for what point we're looking at S1， S2 through S6。

 That means we can express this as a repetition where we count from1 to the number of points in s exclusive。

 We'll call each number that we count I and we'll compute the distance from the I point in S to P。

 If current distance is smaller than best distance。

 then we'll update best choice to S I and best distance to current distance。

We haven't changed our steps for the start or end， but we should generalize the point we give as our answer。

 The answer is not always going to be negative 3， negative 5。 Why did we say that？ Well。

 the answer was the best choice when we finished counting。 So in general。

 we'll give an answer of best choice。The only other thing we need to do is consider a corner case。

 what if S has zero points in it？In that case， we give an answer of no answer exists。

 This corner case was not revealed by the example we just worked。

 but it would have come up through testing， working an example with zero points。

 we would have had a problem during the first step of our computation。

 so we report no answer exists and skip all of these other steps。So here is our algorithm。

 you can test it yourself， later on， we'll learn how to translate this into code。

