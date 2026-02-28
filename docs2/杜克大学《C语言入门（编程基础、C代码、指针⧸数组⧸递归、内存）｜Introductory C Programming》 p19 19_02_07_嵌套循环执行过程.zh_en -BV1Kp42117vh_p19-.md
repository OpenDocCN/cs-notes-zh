# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p19 19_02_07_嵌套循环执行过程.zh_en -BV1Kp42117vh_p19-

![](img/f331aa9b9e924890b57fe2c79cdead88_0.png)

In this video， we have an example of nesting。 In function F， we have a while loop。

With an if statement inside of it， and inside of the if statement， there's a for loop。

The important thing to remember with nesting is that there's really nothing special about it。

 We follow the same rules we've always seen。We begin with our executionarrow at the start of Maine。

 and the first thing we're going to do is call F。Passing 3 for a and 8 for B。

 We create a frame as always。 And we're going to remember where we're going to return and begin executing code inside of F。

Since a less than B is true， we're going to go inside the body of the while loop。We print a equals 3。

 B equals 8， and then we reach an if statement that checks if a mod 2 is0。

Remember that percent is the mod operator， which computes the remainder when you do division。

3 divided by2 has a remainder of1， so3 mod2 is1。A mod 2 is not zero。

 so this conditional expression is false， and we skip over the if statement。

A plus plus increments a to 4， and B minus minus decrements B to 7。

Now we've reached the end of the while loop。So we jump back to the beginning and test its condition again。

A less than b is true， so we enter the body and print a equals 4， b equals 7。

Now when we look at a mod2，4 mod 2 is0，0 equals0 is true。So we enter the if statement。

Now we have a for loop is going to declare an int I and initialize it to the value of a。

 So we make a box for I and set it equal to 4。 We then test the condition of the for loop 4 less than 7 is true。

 So we enter the body of the for loop。 We print I equals 4。Then we perform the increment statement。

 assigning 5 to I and return to the beginning of the loop。 We check the condition again。

5 less than 7 is true。 So we enter the four loop again。 We print I equals 5。

Then we increment I to6 and return to the beginning of the loop。We repeat this process，6 less than 7。

 print I equals 6。Increment I to 7 and return to the beginning。This time，7 less than 7 is false。

 So we skip past the fore loop， leaving the scope of I and continue executing。

 We're now at the end of the if statement's body。 So we resume executing right after it。

 We increment a to 5 and decrement B to 6。 and now we're at the end of the while loop。

 So we jump back to the top。 A less than B is still true。 So we enter the body。 We print a equals 5。

 B equals 6， We check a mod 2，5 mod 2 is1，1 equals 0 is false。 So we skip the if statement。

 We increment A to 6， and decrement B to 5。 and return to the top of the while loop。

6 less than 5 is false。 So we skip over the body of the while loop， reaching the end of the function。

😊，This causes us to return to Maine。 The only thing left in Maine is the return statement。

 so we return zero and exit the program。

![](img/f331aa9b9e924890b57fe2c79cdead88_2.png)

![](img/f331aa9b9e924890b57fe2c79cdead88_3.png)