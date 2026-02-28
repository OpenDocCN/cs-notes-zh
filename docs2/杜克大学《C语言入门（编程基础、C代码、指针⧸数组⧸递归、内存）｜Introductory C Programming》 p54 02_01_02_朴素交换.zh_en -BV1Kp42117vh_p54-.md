# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p54 02_01_02_朴素交换.zh_en -BV1Kp42117vh_p54-

![](img/82294743e37e86115b2452c2ac71a70d_0.png)

To help you see the power of pointers， we are going to show you a piece of code that is broken without pointers。

 After we introduce the mechanics of pointers， we will revisit this code and see how it can work correctly with pointers。



![](img/82294743e37e86115b2452c2ac71a70d_2.png)

![](img/82294743e37e86115b2452c2ac71a70d_3.png)

![](img/82294743e37e86115b2452c2ac71a70d_4.png)

In this example， a misguided C programmer has attempted to write a function to swap two values。

 which you can see at the top of the example。 What does this function actually do。

 You could figure that out on your own since there is nothing new going on here。

 But let's see it explicitly。 As always， we start at the beginning of Maine。



![](img/82294743e37e86115b2452c2ac71a70d_6.png)

![](img/82294743e37e86115b2452c2ac71a70d_7.png)

We declare a and initialize it to3， and then we declare B and initialize it to4。Next。

 we are going to call swap passing in A and B as parameters。 We make a frame for swap。

 Pass 3 for its parameter X and pass 4 for its parameter Y。

We note that we will return to this line of code when swap returns and move the execution arrow into swap right before the first line of code。

 All of this is just the rules for calling a function that you have learned in since course 1。



![](img/82294743e37e86115b2452c2ac71a70d_9.png)

Next， we declare temp and initialize it to x， which is 3。



![](img/82294743e37e86115b2452c2ac71a70d_11.png)

We then assign x equals y， so we set the value of x to 4。



![](img/82294743e37e86115b2452c2ac71a70d_13.png)

Last， we assign y equals temp， so we set the value of y to 3。Now， we're at the end of swap。

 so we are ready to return。 We will return to the place。 We called it in Maine。

 which we have noted in the frame and destroy swap's frame。 Again， there is nothing new here。

 These are just the rules for functions returning that you learned in course 1。

Then we print out that A is3 and B is4， and then the program exits now。

Notice that A And B both started out as 3 and 4 respectively and ended up with those same values。

 The swap function did not really do anything to them。 This result makes sense， given the rules of C。

 The swap function was only able to operate on the copies of its own frame。

 It could not affect the values in mains frame。So what are pointers going to let us do differently。

 We'll have variables， which will give us the location of other data。

 even if it is in a different frame。 We can then effect that data through the pointer。

 This is just one use of pointers。 We will see others once we have developed the basics。



![](img/82294743e37e86115b2452c2ac71a70d_15.png)