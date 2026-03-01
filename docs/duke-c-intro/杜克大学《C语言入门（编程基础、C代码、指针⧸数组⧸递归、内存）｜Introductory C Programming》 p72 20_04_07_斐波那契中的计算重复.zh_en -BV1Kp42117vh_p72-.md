# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p72 20_04_07_斐波那契中的计算重复.zh_en -BV1Kp42117vh_p72-

![](img/2a3656443f26138277bdafbe8e04c9d3_0.png)

In this video， we're going to trace through a series of recursive calls to the function Fibonacci。

 Re that Fibonacci is defined for any value N as the sum of Fibonacci of n -1 and Fibonacci of n -2。

 If we begin with the Fibonacci of 5， we're going to see two recursive calls for n-1 and n -2。

 and this will occur repeatedly until we hit a leaf node。

 A leaf node is Fibonacci of 0 or Fibonacci of1， which simply have the definition 0 and 1 respectively。

 at the end of this series of calls。 You can see that we've called Fibonacci many times。

 Specifically， we've called Fibonacci of 0，3 times。Fibbonacci of1， five times Fibonacci of two。

 three times。 And we've called Fibonacci of three twice。

 So although this recursive definition is correct， it's not particularly efficient。

 The problem is not that recursion is slow。 It's that algorithms that recompute the same thing many times are slow。



![](img/2a3656443f26138277bdafbe8e04c9d3_2.png)

Whether or not this is acceptable depends on your programming context。

 but you should be aware of how a problem like this can affect performance。

If slow performance were unacceptable。You could rethink your algorithm to avoid repeating calculations。

Or you could use memmoization， keeping a table of values that have already been computed and check that table to see if the answer has already been computed before doing it again。

