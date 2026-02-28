# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p11 11_02_06_表达式示例.zh_en -BV1Kp42117vh_p11-

![](img/93ae1d8ee1ce0c43b8ea1788a0370f20_0.png)

Now that you know a little bit more about expressions， let's see them in action。

 This code example starts with a declaration of an integer variable called X。

 which behaves exactly as you already have seen。

![](img/93ae1d8ee1ce0c43b8ea1788a0370f20_2.png)

Next， we initialize x to 4 plus 3 times 2。 As you know from math。

 times has higher precedence than plus， so this expression evaluates to 4 plus 6， which is 10。

So we put 10 in the box for x。Next， we declare another variable y of type int and initialize it to x minus 6。

 which is 10 minus6， which is 4。So we create a box for y and put four in it。

The last statement says x equals x times Y。 Sometimes novice programmers expect statements which look like this to behave like algebraic equations where you might solve for x。

 However， that is not what happens。 Instead， you follow the rules you have already learned。

 The right hand side evaluates to 10 times 4。 which is 40， and you put 40 in the box for x。



![](img/93ae1d8ee1ce0c43b8ea1788a0370f20_4.png)

![](img/93ae1d8ee1ce0c43b8ea1788a0370f20_5.png)

Now let's see another example， before we work through this。

 take a moment to see if you can figure out what the values X， Y。

 and z have at the end of this code fragment。

![](img/93ae1d8ee1ce0c43b8ea1788a0370f20_7.png)

![](img/93ae1d8ee1ce0c43b8ea1788a0370f20_8.png)

Okay， let's step through it。 First， we declare an initialized x。 Next， we evaluate x times 3。

 which is 6 and initialize y to that value。

![](img/93ae1d8ee1ce0c43b8ea1788a0370f20_10.png)

![](img/93ae1d8ee1ce0c43b8ea1788a0370f20_11.png)

Next， we compute y divided by 2， which is 3， and initialize z to that value。



![](img/93ae1d8ee1ce0c43b8ea1788a0370f20_13.png)

The last statement says x equals 2 plus z mod 2。Since the two plus Z is in parentheses。

 we compute that first and get 5。 Next， we compute 5 mod 2。

 Remember from your reading that5 mod 2 means that we divide 5 by 2， but take the remainder。

 not the quotient。 So this expression evaluates to one。So we update the value in X's box to be one。

Okay， great。 Now you should be able to evaluate code involving a wide variety of mathematical expressions。

😊。

![](img/93ae1d8ee1ce0c43b8ea1788a0370f20_15.png)