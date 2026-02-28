# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p74 22_04_05_互递归isodd与iseven执行过程.zh_en -BV1Kp42117vh_p74-

![](img/ece0954663b6ebfc1ebaa168900b98e0_0.png)

In this video， we're going to step through the execution of two mutually recursive functions is odd and is even。

 These functions are also tail recursive so they can have tail recursion elimination applied to them by the compiler such that we will not create a new stack frame for each function call。

We assume a function is called is odd with the argument 4 X has the value 4。

 so we'll pass by the two base cases because x is not equal to 0 or1。 Now。

 we've reached the return statement and want to call is even。

 Instead of creating a new frame for is even， because this is tail recursive。

 we can simply reuse the frame that we have for is even updating X to have the value 3。

Stepping into is even， we're going to pass the two base cases once again。

 and now we want to call is odd with x having the value2。 Once again， we reuse the stack frame。

 updating the value of x to 2。Inside of is odd， we pass the base cases。

 Then we want to call is even one more time。 We'll reuse the stack frame once again for is is even this time。

 updating the value of x to be one。Finally， we've hit the base case since x has the value of1。

 and now we can return the value of 0。 This return value is going to go to the original function that called is odd at the very beginning of this example。

 and the execution arrow will return to the call site 0。



![](img/ece0954663b6ebfc1ebaa168900b98e0_2.png)