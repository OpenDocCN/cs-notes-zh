# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p83 08_02_04_存在内存泄漏的代码.zh_en -BV1Kp42117vh_p83-

![](img/7b6ae7a26395d09d116d0b46bf6694ef_0.png)

In this video， we're going to step through the following code。

 which repeatedly mals an array inside of a for loopbe。 In the first version。

 we're not going to free that array causing a memory leak， but in the second version。

 we are going to use free。Let's see how both versions play out。

We begin inside of main and initialize a variable x and step into a for loop where I initially has the value 10。

The first line in the for loop is going to mall space on the heap for 10 integers。

 and P will point to that location on the heap。Let's assume we have a function。

 do some computation that will initialize that array and perform some kind of computation such that the value of x will change。

Keep in mind that at the end of this iteration of the for loop， the variable P will no longer exist。

 So when we return to the beginning of the for loop， P goes away。

 What this also means is that we've lost our pointer to the memory that we allocated on the heap。

This memory is now leaked。 There's no way to access it。 There's no way to free it。

 We've incremented I to 11， and we're going to execute another iteration of the for loop。This time。

 we're going to mall space for 11 integers。 Now， notice what's going to happen in every single iteration of the loop。

 We're going to allocate memory and then leak it a larger and larger amount each time。

This is not what we want。Let's consider instead a version of this code where we have included a statement to free the memory that we allocate on the heap。

Once again， we begin in main。 We initialize a variable x to 0 and enter the for loop where I initially has the value 10。

 We mal space for 10 integers， then perform this computation。

 which initializes the array and changes the value of x。Finally。

 before we leave this iteration of our for loop， we're going to free the memory pointed to by P。Now。

 when the variable P disappears， we haven't leaked any memory。I has been incremented to 11。

 We go back into the for loop。 We're going to mall space for 11 integers。 Once again。

 we call this computation function， which initializes the array and changes X。 and once again。

 we free the memory pointed to2 by P。Now we could do another iteration of the for loop。

 notice that every time we allocate memory we free it。

 so we're not amassing more and more leaked memory in the heap， as we did in the first example。



![](img/7b6ae7a26395d09d116d0b46bf6694ef_2.png)

![](img/7b6ae7a26395d09d116d0b46bf6694ef_3.png)