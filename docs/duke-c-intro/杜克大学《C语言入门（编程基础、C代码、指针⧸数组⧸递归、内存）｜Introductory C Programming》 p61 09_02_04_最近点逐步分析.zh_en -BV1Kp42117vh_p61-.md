# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p61 09_02_04_最近点逐步分析.zh_en -BV1Kp42117vh_p61-

![](img/e35403b6272966fb840101ff34ff4994_0.png)

In the previous video， we translated our closest point algorithm to code。 In this video。

 we stepped through this code to make sure it works。

 Let's assume that before this function was called， we had an array of points somewhere in memory。😊。

Here， we take a subset of our previous set S and just test our code on an array of four points。

 each astruct with an x and Y value。 Let us also assume that the calling function has passed in a pointer to this array of points。

 its size and a point P。Therefore， we have S a pointer to the base value of our array of points。

 N with the value 4 and point P with values 1 and negative 1。

 We have our execution arrow at the start of closest point， and we can begin。N has the value 4。

 so we do not return null。Next， we're going to call the function compute distance on the zeroth elements of the array S and point P。

 and we're going to store the result of that in a new variable called best distance。In this case。

 the distance is 8。06。 We're also going to make a note of the fact that this distance corresponds to our best choice。

 which is the zeroth element of the array。So best choice is initialized to be a pointer to S at0。

Now we're going to go into the for loop and continue to look through the rest of set S。

 seeing if we find a point that's closer than that zeroth point in the array。

We go inside the for loop， and we have I with the value 1。

 and we're going to now compute the distance of S at 1， S I。

 which in this case is S at 1 and point P。 We compute this distance。

 and we're going to store that in current distance For this iteration。 current distance is 7。07。

 We want to test whether the current distance of 7。07 is less than the best distance of 8。06。It is。

 So we step into the F clause。 We're going to update our best choice pointer。

From S at 0 to be S at 1， and we're going to update our best distance from 8。06 to 7。07。

We've reached the end of our for loop。 so we iterate。 Now I has the value too。

 So we're computing the distance from S set 2 to point P， which is 7。81。Once again。

 we test whether current distance is less than best distance。 In this case， it is not。

 So we pass by the if clause and iterate one more time where I has the value 3。

In our final computation， we're computing the distance between St 3 and point P。 The distance is 5。

66。 We compare the current distance to the best distance and 5。66 is smaller。

 so we enter the F clause and assign a new best choice of S3。

Our corresponding new best distance is 5。66。We increment I to have the value 4。

 which concludes our for loop。 When we leave the function， we'll be returning best choice。

 which is a pointer to the point closest to point P， which is the point found at Set 3。

Assume we are returning to the calling function。Notice how clean our code is。

 because we're able to use an array to represent set S。

 If we instead we had had to use a variable name for each point in set S。

 It would have gotten really messy， really fast。 Imagine if set S had 1000 points in it。

 It's a good thing we have arrays and that they work so cleanly with four loops where each iteration corresponds to an integer I and that integer can be used to index each element of an array that we're working with at the time。

😊。