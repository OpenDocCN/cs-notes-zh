# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p23 23_03_04_类型转换.zh_en -BV1Kp42117vh_p23-

![](img/a971cffeb6588247b1c9b58166505676_0.png)

Let's take a look at some example code that shows when implicit conversions happen and how you have to be careful about types。

 First， we make an inch called N hours and initialize it to 40。Next。

 we make end days and initialize it to seven。Next， we have a float called average。

 which is initialized to n hours divided by N days。 Both N hours and N days are ins。

 So this is integer division。 We have 40 divided by 7， which for integer division results in 5。 Now。

 since we are assigning an int to a float。 the compiler will implicitly convert that integer result to a floating point number。

 but it does that after the division， So we end up initializing average with a value of 5。0。

Then we print out that 40 hours in seven days is 5。0 hours per day。This is not the right answer。

 so let's fix this code。Here we've made one small change to the code。

 we have explicitly cast end days to afloat before we do the division。

 which is called out with the red underline here。We start the same way。

 N hours is created and initialized to 40 and N days is created and initialized to 7。 However。

 now things go differently。 The divisor of this expression is now 7 cast to a float。

 So we need to evaluate the integer 40 divided by the floating point number 7。0。

Computers divide integers by integers or floating point numbers by floating point numbers。

 So the compiler has to implicitly convert 40 to a floating point number before doing the division。

 Now， we are doing floating point division，40。0 divided by 7。0 equals 5。71。

We now initialize average with this value， which means that when we print out our results。

 we get the correct answer。Now， you have seen both implicit conversions， as well as explicit casts。

 Casting is something you use when you need to。 However。

 you should use it sparingly only when you think through what you are converting between and why。



![](img/a971cffeb6588247b1c9b58166505676_2.png)