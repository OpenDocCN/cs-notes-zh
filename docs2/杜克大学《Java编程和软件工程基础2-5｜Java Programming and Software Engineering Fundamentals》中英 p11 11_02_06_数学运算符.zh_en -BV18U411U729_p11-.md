# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p11 11_02_06_数学运算符.zh_en -BV18U411U729_p11-

![](img/317607df4781fda2139449d868c8c316_0.png)

Now that you know a little bit more about expressions， let's see them in action。

 This code example starts with the declaration of an integer or int variable called X。

 which behaves exactly as you've already seen。 Next， we initialize x to 4 plus 3 times 2。

 as you know from math。 times has higher precedence than plus for this expression evaluates to 4 plus 6。

 which is 10。😊，So we put 10 in the box for X。 Next。

 we declare another variable Y of type int and initialize it to x-6， which is 10-6， which is 4。

 So we create a box for Y and put 4 in it。 The last statement says x gets x times Y。

 Sometimes novice programmers Exp statements which looked like this to behave like algebraic equations with an equal sign where you might solve for x。

 However， that's not what happens。 Instead， you follow the rules you've already learned。

 The right hand side evaluates to 10 times 4， which is 40。And you put 40 in the box for x。 Now。

 let's see another example。Before we work through this。

 take a moment to pause the video and see if you can figure out what values X， Y。

 and Z have at the end of this code fragment。Okay， let's step through it first we declare and initialize x。

 Next we evaluate x times 3， which is 6， and initialize y to that value。Next。

 we compute y divided by 2， which is3。And initialize Z to that value。

 The last statement says x gets2 plus z mod2。Since the 2 plus Z is in parentheses。

 we compute that first and get5。Next， we compute5 mod2。

Remember from your reading that5 mod2 means we divide5 by 2， but take the remainder。

 not the quotient， so this expression evaluates to one。So we update the value in X's box to be1。



![](img/317607df4781fda2139449d868c8c316_2.png)

Okay， great。 Now you should be able to evaluate code involving a wide variety of mathematical expressions。

😊。

![](img/317607df4781fda2139449d868c8c316_4.png)