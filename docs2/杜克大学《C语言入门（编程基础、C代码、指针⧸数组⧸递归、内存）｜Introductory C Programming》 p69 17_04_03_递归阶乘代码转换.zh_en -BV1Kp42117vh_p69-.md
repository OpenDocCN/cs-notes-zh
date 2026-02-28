# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p69 17_04_03_递归阶乘代码转换.zh_en -BV1Kp42117vh_p69-

![](img/826b6cea974e974ebddd1cea5a091b41_0.png)

In this video， we will translate the algorithm we developed in the previous video into code。

 We've included our algorithm as comments shown in blue。

 and we will turn these steps into C code To begin with。

 we are going to put all of the steps inside of a function factorial factorial takes an integer in and returns an integer that is the factorial of n。



![](img/826b6cea974e974ebddd1cea5a091b41_2.png)

Now， to determine if n is less than or equal to 0， we're going to use an if else statement。

If n is less than or equal to0， we want to answer one， which we can do with a return statement。

Now we want to represent the otherwise case， which is the else part of the F else statement。

To do this more complicated case， we need to create a new variable in minus1 fact。

 and we're going to have to make a function call to perform a complex step and figure out what value to assign to n minus1 fact。

The function we want to call happens to be the one we are writing。

 So we place a call to factorial with the value in -1。Now that we have the value in minus1 fact。

 we want to multiply it by n。That is the result we'd like to return。

 which we can do with a return statement。Now we've completed our function and our remaining steps would be to test and debug it。



![](img/826b6cea974e974ebddd1cea5a091b41_4.png)