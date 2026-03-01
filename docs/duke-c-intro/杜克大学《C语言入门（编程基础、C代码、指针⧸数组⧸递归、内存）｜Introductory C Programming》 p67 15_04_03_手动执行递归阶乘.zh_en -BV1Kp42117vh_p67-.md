# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p67 15_04_03_手动执行递归阶乘.zh_en -BV1Kp42117vh_p67-

![](img/fe74498979ba1cacc440a96c3b07ff78_0.png)

This video is going to trace through the function factorial， which is recursive。

 Note that there is a call to factorial as part of the function's return statement。We begin in main。

 and the first line declares a variable X and initializes it to factorial of 3。

 We create a frame for factorial， where in has the value 3。

 mark call site 1 and move our execution arrow into the factorial function。

 and is not less than equal to 0。 So we skip the if statement。 We are now at the return statement。

 which has a recursive call to factorial this time with the argument 2。

 I'm also placing a two on the call site marker to indicate that when we finish this call to factorial。

 we need to return to call site 2。 Let's step into the function。😊，N is equal to 2。

 which is not less than or equal to 0。 We'll move down to the final line of the function and place a recursive call to factorial。

 This time with argument 1， but the same call site location 2。 we step into the function。

Move down to the final line of code where we have another recursive call to factorial this time with the argument 0。

We step into the function and this time in is less than or equal to0， so we have a return value of1。

 we're going to send one back to the call site location of the function that called this one and return back to the call site location。

 Now we have some multiplication。One times 1 gives us the value 1。

 and now we're going to return one to the function that called this function。

We return to the call site location， and now we're in the function factorial where n has the value too。

So two times1 gives the value 2， which we will return to the function that called this instance。Now。

 we're in the initial execution of the factorial function， where n has the value 3。

 We're going to create a return value of 6 and send that to the initial call to factorial。 Now。

 we can leave the function and return to main。Finishing this assignment statement。

 giving x the value factorial of 3， which has the value 6。



![](img/fe74498979ba1cacc440a96c3b07ff78_2.png)

![](img/fe74498979ba1cacc440a96c3b07ff78_3.png)