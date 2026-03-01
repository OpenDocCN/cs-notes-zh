# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p05 05_01_03_测试正方形模式.zh_en -BV1Kp42117vh_p5-

![](img/8337913be336478dae75c400a1b33869_0.png)

In this video， we will test the algorithm for a pattern of blue and red squares on a grid。

 Remember that testing is going to make us more confident in our algorithm。

 Since generalizing is one of the harder parts of the programming process and is prone to errors。

 such as leaving something constant that should be a variable。😊。



![](img/8337913be336478dae75c400a1b33869_2.png)

We need a grid to draw on an arrow to keep track of where in the algorithm we are。

And a box to list our variables in。Let's use2 for our value of n。

We make a box for x and start counting at zero。Then we make a box for y and start counting at x's value。

 which is0 here。 Now， we need to decide if x plus y is a multiple of3。 It is。

 So we go inside the if statement and put a blue square at 0，0。 Now。

 there are no more steps for this iteration of y。 So we continue counting with y equals 1。

0 plus 1 is not a multiple of3， So we enter the otherwise clause and put a red square at 0，1。

 There are no more steps for this Y。 So we'll count the next one。0 plus 2 is not a multiple of 3。

 So we'll put a red square at 0，2。 We continue counting and y is 3。

 So we are only counting from x to n， So we don't do any of these steps。😊。

And we continue counting for x。 So now x is1。 We're going to count from one to n and call that Y 1 plus1 is not a multiple of3。

 So we put a red square at 1，1。 incrementing y 1 plus 2 is a multiple of 3。

 So we put a blue square at 1，2。 We're done counting for y。 So next， we count our next x。

 counting from 2 to 2。2 plus 2 is not a multiple of3。 So we put a red square。

 We finished counting for y。 So we count for the next x。

 We're uncounting for x since we only want to count to n， which is 2。

 So we're done with the counting。😊，And we finished executing this algorithm。 We are done。

 and we found the answer we expect。 We can say our algorithm at least works for n equals 2。

 We're a little bit more confident in our algorithm。

 because we've shown it to be correct for at least one value of N。

 That was not what we used to come up with it。 If we wanted to be more confident。😊。

We would have to test it more thoroughly。 As always， testing can't prove that it's correct。

 It can only make us more and more confident。