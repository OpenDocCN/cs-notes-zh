# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p73 21_04_02_尾递归阶乘实现执行过程.zh_en -BV1Kp42117vh_p73-

![](img/89f8bdf230a585bc2b7413794b26fb69_0.png)

In this video， we're going to trace through the execution of a tail recursive version of factor。

The factorial function has one parameter in， which is the number we're computing the factorial of。

 and it returns an integer that is the factorial of that input。

 The difference between this version and the previous implementation is the helper function named fact helper。

 which has two parameters， an integer in and an integer answer。

N is the number we are computing the factorial of， and answer is a running product that gets computed with each recursive call。

 You can see that when fact helper calls itself it is the last computation it does。

 This is called tail recursion。Let's step through the execution。

 We begin inside a factorial where in has the value of3， and we're going to call fact helper。

 So we need to create a stack frame， and we're going to send in the arguments in equal to3 and answer equal to1。

 We mark the call site location with a1。 so we know where to return when we leave the function。

Inside a fact helper， because in has the value of three。

 we skip over the base case and we're going to call fact helper once again。This time。

 creating a stack frame for the next recursive call where in has the value of 2 and answer has the value of3。

Now， as we step through this code， note that it does not have a compiler optimization that we'll introduce later in this video。

 so this is going through the tail recursive function。

 as you would expect it to happen with nothing fancy or optimized yet。We step into the function。

 Once again， we pass the base case， Then we make another frame for the next called a fact helper。

 where in has the value of one and answer has the value of 6。 We step into that function。

Pass the base case and make another stack frame for this call to fact helper where in has the value of 0 and answer has the value of 6。

This time when we step into the function， in is less than or equal to 0， this is the base case。

 so we return the answer6 all the way up these calls。

Returning from the recursive call to call site location2。

 then repeatedly returning to call site 2 and destroying the stack frame for each recursive call。

 this repeats again。Finally， we return the value 6 to call site location 1 and move our execution arrow back into the function factor。

Now the thing to notice here is that we only needed to return the value6 all the way up these calls as soon as we placed each tail recursive call。

 we didn't actually need the stack frame anymore because there's no value in the frame that we're going to use again。

An optimizing compiler will recognize this。And perform what's called tail recursion elimination。

A stack frame will not be created for each recursive called the fact helper。

Let's step through the optimized version。 We start inside of factorial once again with in having the value of three。

 We create a stack frame for fact helper where in has the value of3 and answer has the value of one。

 We mark the call site location one， and step into fact helper。N is not less than or equal to zero。

 so we're going to place the recursive called the fact helper。 however。

 we're going to reuse the frame。First， we have to evaluate the parameters to two and3 respectively note that we do this before we start changing any of the values in the frame since we want to use the current values。

Then we are going to update the value of n in the frame to be 2 and the value of answer to be 3。

Now we jump back inside a fact helper。Pass the base case。 And once again。

 we're about to place a recursive call。 But instead。

 the compiler will make the code update the values of in an answer to the new arguments 1 and 6。

 We skip the base case and reuse the stack frame one more time。

 This time within having the value of 0 and answer having the value of 6。

This time we go into the base case and now return the answer of6 one time back to call site location1 in the function factorial notice that the stack frame does not need to be created for every call to fact helper what this means is that the space you require is no longer proportional to the size of in。

 you simply need one frame for factorial and one frame for fact helper。



![](img/89f8bdf230a585bc2b7413794b26fb69_2.png)