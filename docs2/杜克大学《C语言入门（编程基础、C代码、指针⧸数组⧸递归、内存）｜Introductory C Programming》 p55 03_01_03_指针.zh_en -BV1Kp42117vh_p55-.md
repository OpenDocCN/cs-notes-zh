# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p55 03_01_03_指针.zh_en -BV1Kp42117vh_p55-

![](img/25372b81911fd61ed27c927a474b5c15_0.png)

In this video we're going to step through some code that uses pointers to show you how to best draw diagrams to understand what is happening in a line by line fashion。

 The first line of code declares a variable X and gives it an initial value of 3。

 The next line of code declares a variable P that is of type integer pointer。

 It does not yet initialize it。 So in the beginning we have a box。

 but we don't yet know what's in the value， but we do know that the box is called P。

The next line of code will initialize the value of P to have the value of the address of x。

 When you see an assignment like this， it's important to begin by looking at the left side first and then look at the right side。

Looking at the left side， we can see that the value is going to be placed into the variable P。

When we look on the right side of the assignment statement。

 we see that the value we're going to place is the address of x。 So when we execute this line。

 we're going to change the variable P to now have an arrow that points to X On the next line On the left side。

 we see the value that P points to， which is actually the variable X。

 We're going to set that to have the value on the right side， which is4。

When we execute this line of code， we're going to go to that which P points to and change that to have the value for。

The next line of code declares a variable Y， and the value it's initialized to is the value P points to in this case。

4。 When we execute this line of code， we're going to create a new box named Y and give it the value 4。

 The next line is going to declare a variable of type integer pointer called Q。

 and we're going to give it an initial value of the address of Y。

That means we're going to create a new box called Q。

 and it's going to have an arrow in it that points to Y。 The next line's a little bit tricky。

 On the left， we're going to be storing the value we create into that which Q points to。

 namely the box for y， and the value that we're going to store there， is that which P points to。

 which is4 plus1。So when we execute this line of code， we're going to take the value P points2。

 which is4， add1 to it， which is5， and store that at the location Q points2， namely the variable y。

The final line of code we have simply gives the value of P to the variable Q。

 Q is the receiving value， and the value it's going to get is the value P has， which has an arrow。

 So when we execute this line of code， we're going to replace the value of Q with an arrow that points to the thing P points to。



![](img/25372b81911fd61ed27c927a474b5c15_2.png)

![](img/25372b81911fd61ed27c927a474b5c15_3.png)