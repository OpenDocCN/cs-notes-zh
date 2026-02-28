# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p81 06_02_02_简单的malloc调用.zh_en -BV1Kp42117vh_p81-

![](img/bdcd8101f21a76d48773414b4c4d5cdc_0.png)

Now， let's see the semantics of Malik。 Here We have a small example of code， which uses Malick。

 It does not really accomplish anything， but will let you see what Malick does。

 Our first statement just declare as an int star P， which is uninitialized。

 The next statement is an assignment statement。 So you will follow the same rules you always do。

 Find the box named by the left hand side。 In this case。

 P and evaluate the right hand side expression to get a new value to put into that box。 In this case。

 that expression is a call to Malik， which will allocate memory。

 Allocating memory means that you are going to draw a new box。 This new box will be in the heap。

 Not in any stack frame。 Unlike variables which reside in stack frames。

 This box that you will create in the heap does not have its own name。😊。



![](img/bdcd8101f21a76d48773414b4c4d5cdc_2.png)

![](img/bdcd8101f21a76d48773414b4c4d5cdc_3.png)

![](img/bdcd8101f21a76d48773414b4c4d5cdc_4.png)

![](img/bdcd8101f21a76d48773414b4c4d5cdc_5.png)

To see what the new box looks like， you need to look at the argument past to Malick。

Here it is six times the size of star P， which means it will be an array of six elements。



![](img/bdcd8101f21a76d48773414b4c4d5cdc_7.png)

As P is an int pointer， those elements will be ins。 So let's draw that box。

Note that each element inside the array is uninitialized。 Whenever you create new boxes。

 they are uninitialized until you explicitly place a value in them。



![](img/bdcd8101f21a76d48773414b4c4d5cdc_9.png)

The return value of Malik is a pointer to this newly allocated memory。

 So now you are ready to finish the assignment statement。😊，Placing the return value of Malik。

 which is the value of the function call into P's box。Now。

 let's look at what happens later when the function returns。

The frame for the current function is in the stack。

 so it will be destroyed automatically when the function returns。

 This behavior is exactly what you are used to from prior lessons。 However。

 the memory that was allocated by Malik is in the heap。

 This memory will not automatically be freed when the function returns。

 So when you execute the return statement， you will destroy the frame。

 but not change anything in the heap。

![](img/bdcd8101f21a76d48773414b4c4d5cdc_11.png)

![](img/bdcd8101f21a76d48773414b4c4d5cdc_12.png)

![](img/bdcd8101f21a76d48773414b4c4d5cdc_13.png)

![](img/bdcd8101f21a76d48773414b4c4d5cdc_14.png)

Anything allocated in the heap will continue to exist until you explicitly free it。

 which allows you to allocate memory inside a function and return a valid pointer to use it in other functions。



![](img/bdcd8101f21a76d48773414b4c4d5cdc_16.png)

![](img/bdcd8101f21a76d48773414b4c4d5cdc_17.png)