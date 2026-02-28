# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p39 09_02_02_规划isprime函数.zh_en -BV1Kp42117vh_p39-

![](img/e73114b8a0915f535968aed419b69be0_0.png)

In this example， we're going to plan and write a function that takes one integer in and determines if it is prime。

We begin with step 1， working at least one instance by hand。

 We might start with something like is 7 prime。 And you might just say， yes， I know this。7 is prime。

 However， this is not very helpful。 Just knowing the answer does not help us develop a step by step approach to solving the general problem。

Unfortunately， when you already know the answer， it can be hard to see past it， in which case。

 there are two things you could do。First， you could consider how you would convince someone one that this is right。

 That is， if you said 7 is prime and I said， I don't believe it。

 What would you do step by step to show me that it is。Second。

 you might think about a harder problem where you don't just know the answer to see the step by step approach you take。

If that problem is too big to work through all the way。

 you might use the step by step approach you begin with to inform how you work through a more manageable size example。

As an example of a harder problem， let us consider whether 29393 is prime。

 I suspect most of you do not know the answer off the top of your head。We'll start with step 1。

I divide it by two and get 14696 remainder 1。Dividing by three gives 9797 remainder 2。

Dividing by4 gives 7348 remainder1。Diving by5 gives 5878 remainder 3。

Dividing by 6 gives 4898 remainder 5。Dividing by7 gets 4，199 remainder0。

Because my number is evenly divisible by 7， I will answer。 no，29393 is not prime。Next。

 I'll write down exactly what I did， and this involves thinking through my actions and describing the steps to get the answer。

I checked if 29393 mod 2 is 0。 That is， if it is evenly divisible by two， it was not。

Then I checked if it was divisible by three。 If mod 3 is equal to 0， it was not。

Then I checked whether it was divisible by 4， divisible by 5， divisible by 6， divisible by 7。

 The answer was yes。 When I found it was divisible by 7， I answered no。

The next step is generalizing the result of step 2。

 but we may wish to do multiple instances of steps1 and2 first in this problem in particular。

 since we have a yes or no question， it may be very useful to do an instance where we get a yes answer before we try to generalize。

Now， we'll return to our first question is 7 prime having already thought through how to do it step by step。

 we may be able to get past our mental roadblock of just knowing the answer。

7 divided by 2 is 3 remainder 1，7 divided by 3 is 2 remainderder 1，7 divided by 4 is 1 remainder 3。

7 divided by 5 is one remainder 2，7 divided by 6 is one remainder 1。 So at this point。

 I'm going to answer。 yes，7 is prime。 I tried all of the numbers from 2 to 6。

 and found that 7 is not divisible by any of them。

![](img/e73114b8a0915f535968aed419b69be0_2.png)

Doing step 2 for this same problem， I'm going to write down that I checked if 7 mod 2 is 0。It is not。

Checked if 7 modd 3 is 0。 It is not。Check of 7 modd 4 is 0。 Check of 7 mod 5 is 0。

 Check of 7 modd 6 is 0。 And after doing all that and verifying that the answer was no for all of them。

 I answered， yes。😊。