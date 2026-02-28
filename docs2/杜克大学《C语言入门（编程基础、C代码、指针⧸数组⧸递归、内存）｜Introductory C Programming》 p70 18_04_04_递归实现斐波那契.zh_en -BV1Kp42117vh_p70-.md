# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p70 18_04_04_递归实现斐波那契.zh_en -BV1Kp42117vh_p70-

![](img/c4ef749e19d76f2d151c913984dba664_0.png)

In this video， we're going to walk through the first four steps of the programming process in the context of Fibonacci。

 We'll begin by working out an example， computing Fibonacci of4。



![](img/c4ef749e19d76f2d151c913984dba664_2.png)

![](img/c4ef749e19d76f2d151c913984dba664_3.png)

Fibbonacci of4 is defined as Fibonacci of3 plus Fibonacci of2。 So what's Fibonacci of3。



![](img/c4ef749e19d76f2d151c913984dba664_5.png)

![](img/c4ef749e19d76f2d151c913984dba664_6.png)

It's defined as Fibonacci of2 plus Fibonacci of1。

![](img/c4ef749e19d76f2d151c913984dba664_8.png)

What about Fb 2？That's defined as fib 1 plus fib 0。And fis 1 and fib 0 are defined as1 and0。

 respectively。

![](img/c4ef749e19d76f2d151c913984dba664_10.png)

So1 plus0 gives one。Now， we need to move over to the right hand side of the blue expression。

 calculating Fibonacci of one， which， as we just said， is one。



![](img/c4ef749e19d76f2d151c913984dba664_12.png)

So now we add one plus one and get two。Since we have now computed Fib 3。

 we move over to the right hand side of the top expression， computing Fibonacci of 2。

Fib 2 is defined as fib 1 plus fib 0。 And as we said earlier。

 fib 1 and fib 0 have the values 1 and 0 respectively。 If we add those together， we get one。



![](img/c4ef749e19d76f2d151c913984dba664_14.png)

![](img/c4ef749e19d76f2d151c913984dba664_15.png)

So Fb4 has the value of 2 plus1 or3。And that's our answer。In step2。

 we need to write down all of the things we did in step1 to compute Fb4。

 so let's begin with the tree we just created and write down all the steps we performed along the way。



![](img/c4ef749e19d76f2d151c913984dba664_17.png)

![](img/c4ef749e19d76f2d151c913984dba664_18.png)

First， we computed Fb 3。 This prompted us to compute Fb 2。 And in the process of computing Fb 2。

 we had to compute Fb 1 and Fb 0。Then we went back up to the blue expression and computed Fb1。

Then we needed to move over to the right hand side and compute Fb 2。

 which required us to compute Fb 1 and Fb 0。Let's take a look at how we compute Fibonacci of each of these numbers To compute Fb 0。

 we simply answered 0。To compute Fb 1， we simply answered one to compute Fb 2。

 we were required to compute Fb 1 and Fb 0 and add them together。For Fb 3。

 we computed Fb 2 and Fb 1 and added those together。 and for Fb 4。

 we computed Fb 3 and Fb 2 and added those together。

Step 3 requires that we generalize looking for patterns in our series of steps。

 The first thing you may realize is that computing Fb 4， Fb 3 and Fb 2。

Looks like a very similar set of steps。Whereas computing Fb 1 and Fb 0 looks a little bit different。

 In fact， computing Fb 1 and Fb 0 are special cases called base cases。 We simply know the answer。😊。

So what we might want to do is determine if n has the value1。 and if it does， we just answer one。

Similarly， we determine if n has the value0 and if so， answer 0。Otherwise。

 we're going to have to deal with these complicated cases over here on the left。

So let's look at that a little closer Now。 The first thing you might want to do is look at the first line of each of these computations。

Why is it that when we were computing Fb 4， we began by computing Fb 3。

 And why is it that when we computed Fb 3， we had to compute Fb 2。

The general form here is that the first step for computing fib N is to first compute fib n -1。

So we can replace this first line in each of these computations with compute Fb n -1。

 which we will call fib n -1。We can replace this line in each of our similar steps below。Next。

 you might ask， why were we computing Fb2 here？And why were we computing Fb 1 here。

The general form is that the second step for computing Fibonacci of N。

Is to compute Fibonacci of n -2。The general form has S compute Fb n-2。

 and we're going to call that fib n-2。We can replace that in the computation below。And finally。

 we sum up our answers。The great thing about creating a general form is that now all of our steps for each of these calculations are identical。

 And so our otherwise case is simply these three steps， regardless of whether n is 2，3，4 or more。😊。

In step 4， it's important to test our algorithm。 Let's see if our algorithm works to compute Fibonacci of 6 or Fibonacci of1。



![](img/c4ef749e19d76f2d151c913984dba664_20.png)

How about Fibonacci of negative 2。

![](img/c4ef749e19d76f2d151c913984dba664_22.png)

When we perform the test to see whether Fibonacci of negative 2 is correctly calculated。

 we're going to discover a problem。

![](img/c4ef749e19d76f2d151c913984dba664_24.png)

-2 is not equal to 0 or 1。 So we're going to step into our otherwise clause。

 Comp Fibonacci of -3 and Fibonacci of -4 and adding these together。 However。

 in order to compute fib negative 3， we're going to find ourselves computing Fb negative 4 and fib negative 5。

 This process is not going to terminate。

![](img/c4ef749e19d76f2d151c913984dba664_26.png)

This is not good。This test case betrays a problem in our algorithm。 In fact。

 we haven't been completely true to our definition of Fibonacci。



![](img/c4ef749e19d76f2d151c913984dba664_28.png)

If you look back at the original definition of Fibonacci， you can see that there are five cases。

 the case where n is 0， the case where n is1， the case where n is greater than1。

 and there's two cases where n is negative。We didn't handle these two cases， and we need to。

 The other thing to notice is that our otherwise clause was handling the case where N is greater than one。

 even though we never explicitly said so。So we're going to have to explicitly place that into our code。

 testing whether n is greater than1。 And if it is， we perform those computations。😊。



![](img/c4ef749e19d76f2d151c913984dba664_30.png)

Otherwise， if n is less than0， we're going to need a few new steps。Now， normally。

 we would suggest you go back and do steps 1 to 3 to handle the additional Fibonacci cases for the sake of time。

 however， let's assume we already did that。 And this is what we came up with。 If n is less than 0。

 we're going to compute fib of minus n and call it fib Neg n。Then when n is odd， that's the answer。

And when n is even， we multiply fib of minus n by negative one。 And that's our answer。

We would now test the revised algorithm with the new test cases。

