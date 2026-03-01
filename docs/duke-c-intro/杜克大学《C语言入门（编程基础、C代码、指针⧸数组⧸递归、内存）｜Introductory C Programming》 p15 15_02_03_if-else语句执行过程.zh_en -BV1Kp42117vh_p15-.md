# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p15 15_02_03_if-else语句执行过程.zh_en -BV1Kp42117vh_p15-

![](img/2fa615369e972610b2fbf917e9dfe0d0_0.png)

Now， let's see how to execute code with conditional statements in it。 here we have a function F。

 which has some if and if else statements。 As always。

 our program starts its execution at the beginning of mainine。

The first statement declares a variable A， so we make a box for it。

Even though this statement initializes A， it's going to take us several steps to compute that value。

 so we're going to leave A's value as a question mark until we compute the value of f of 34。

To evaluate the call to F， we make a frame passing the values of the parameters。

We note where to return to and move the execution arrow to the first line of F。

The next line of code is an if statement whose conditional expression is x less than y。

 We evaluate that expression and find that three less than4 is true。

So we move the execution arrow into the then clause of this if statement and continue executing。

The next statement is a call to print F， which you are familiar with。

We write x less than y in our output。 Next， we return Y plus X。

 This follows the same rules you have already learned for return statements。

 We evaluate the expression to get the return value， which is 7。

This is what the function call will evaluate to。 And now we return back to the collar。

 destroying the frame for F。Now we are ready to finish initializing A since we know that the call of F evaluated to7。

So a is now 7。We are now ready for the next line of code in main。 We make a box for B and call F。

 passing in 7 and 5。😊，We once again want to evaluate the condition X less than y。 However。

 now x is 7 and y is 5。 So x less than 5 is false。We find the closed curly brace for this if statement and see that the if statement has an elset clause。

 So we move the execution arrow into the start of the elset clause and continue executing from there。

First， we execute the print statement。And then we reach another if statement。

 This if statement is nested inside of the else， but that does not affect the rules of how we evaluate it。

 We see that the conditional expression is false， so we look for the closed curly brace of the if statement。

There is no else clause， So we move the execution arrow immediately past the closed curly brace and continue execution。

There are no more statements inside the Elts clause。

 so we move the execution arrow outside of the Els clause and keep going。

Now we have a return statement， so we evaluate the expression x minus2 to find that the return value is 5。

 which will get returned to the place that we have noted。

We return back to the main and destroy the frame for F。Then we finish the assignment statement。

Now we are at the return statement for Maine。 we execute that and exit the program。



![](img/2fa615369e972610b2fbf917e9dfe0d0_2.png)