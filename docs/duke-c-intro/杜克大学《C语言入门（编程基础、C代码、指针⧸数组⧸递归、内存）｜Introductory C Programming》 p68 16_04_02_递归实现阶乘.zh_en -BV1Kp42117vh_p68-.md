# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p68 16_04_02_递归实现阶乘.zh_en -BV1Kp42117vh_p68-

![](img/d025a21b842fd74acea412f250841217_0.png)

In this video， we're going to walk you through the seven steps to figure out the algorithm that computes factorial。

 The first step is to work an instance of the problem yourself。

 So let's begin by computing4 factorial by hand。 The first thing we would do is recognize that four factorial is defined as four times 3 factorial。

 which now gives us the problem of solving three factorial。

3 factorial is defined as3 times2 factorial， so we figure out what two factorial is。

It is defined as2 times one factorial， so we figure out what one factorial is。

Which is1 times 0 factorial。And zero factorial is just one。Now that we know what zero factorial is。

 we can replace  zero factorial with a one。Now we know what one factorial is， 1 times 1。

 which equals1， so we replace one factorial with one。2 factorial is2 times 1， which equals 2。

 so we replace two factorial with 2。Three factorial is 3 times 2， which equals 6。

 so we replace three factorial with 6。4our factorial is 4 times 6， which equals 24。

So this is our answer to the whole problem。In step2。

 we need to take a moment to think about what we did in step1 and write down the sequence of operations。

When we needed to figure out what4 factorial was， the first thing we did was compute 3 factorial。

 When we needed to compute3 factorial， the first thing we did was compute2 factorial。

For two factorial， we computed one factorial。 for one factorial。

 we needed to know what zero factorial was。But for 0 factorial， we didn't need to compute anything。

 We just knew that0 factorial has the value of one。

 Once we figured out what the value of 0 factorial was。

 we used it to compute the value of one factorial by multiplying that by one。

 Once we knew the value of one factorial， we used it to compute two factorial by multiplying it by two。

Once we knew the value of two factorial， we used it to compute three factorial by multiplying it by3。

 Finally， we used the value of three factorial to figure out the value of four factorial by multiplying it by4。

Let's take a minute to write down the steps we did for each of these computations。

To compute zero factorial， we simply answered one。To compute one factorial。

 we computed zero factorial， Then we multiplied that result by one， and that was our answer。

To compute two factorial， we computed one factorial， multiplied that result by two。

 and that was our answer。To compute three factorial， we computed two factorial。

 multiplied that result by3， and that was our answer。Finally， to compute4 factorial。

 we computed three factorial， multiplied that result by four， and that was our answer。

Step three is to generalize our process， let's take a moment to look over the computations we performed。

The first thing you might notice is that computing four factorial down to one factorial involved very similar steps。

 whereas computing zero factorial was a little bit different。

 This is a special case called the base case。 and usually it's incorporated into the definition of the thing we're trying to compute。

 For example， part of the definition of factorial is that zero factorial equals1。

So the first thing we might write down when trying to generalize this process is recognizing the one case that's a little bit different。

 We should determine if n is zero or not。Then the answer is just one。Otherwise。

 we need to do something a little more complicated。

Let's look a little more closely at how we computed four factorial down to one factorial。

The first thing you might wonder is。Why are we computing three factor to compute4 factor。Also。

 why are we computing two factorial to compute 3 factorial in generalizing this。

 we had realized that every time we compute in factorial， we compute in-1 factorial。

 which is the first step in the process。 We're going to compute in -1 factorial。

 and we'll give it a name。 We might call it in-1 fact。

Now that we've figured out the pattern of behavior。

 we can update our description below using this generalized description。

Every time we compute a particular factorial， we compute in minus1 factorial and then multiply that by some integer value。

 So let's take a closer look at that integer value When we compute4 factorial。

 we multiply in minus-1 fact by4， when we compute3 factorial， we multiply in one-1 fact by 3。

The pattern that we see here is that the integer is always in。

So we can generalize our steps to say that we are multiplying n minus1 fact by n。

And that resulting product is the answer。Now that we've written carefully generalized steps for calculating factorial。

 it's important to take a minute to test our algorithm using a variety of possible inputs。

 try computing several test cases yourself。Does it work？

Testing on negative input values is actually going to show us a flaw in our code。

Consider the calculation of negative 2 factorial。 Ne2 is not equal to 0。

 So we're going to recurse and compute negative 3 factorial。 Ne 3 is also not0。

 So we're going to compute negative 4 factorial and so on。

 you can see that this code is going to recurse forever since it doesn't make progress towards the base case。

 In fact， we have a mistake in our algorithm。 we need to be testing whether n is less than or equal to 0。

 not just whether it is equal to 0。 Now， we have written out our algorithm and tested it。

 Even finding a bug in our algorithm。 In the next video， we will translate this algorithm to code。



![](img/d025a21b842fd74acea412f250841217_2.png)