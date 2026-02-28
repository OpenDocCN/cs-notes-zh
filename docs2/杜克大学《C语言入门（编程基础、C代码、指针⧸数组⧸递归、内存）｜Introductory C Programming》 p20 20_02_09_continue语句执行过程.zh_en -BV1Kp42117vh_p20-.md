# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p20 20_02_09_continue语句执行过程.zh_en -BV1Kp42117vh_p20-

![](img/d98926f05499fe16766d28016a49d264_0.png)

In this example， you're going to learn how to execute code with a continuous statement in it。

Here we have a for loop that has a continuous statement inside with a for loop。

 When you execute a continuous statement， the loop increment is performed with the continue。

To see this， let us first convert this for loop to the equivalent wire loop。

Here we've taken one step in the conversion process， moving the variable declaration before the loop。

To move this closer to being a while loop， we've moved the increment statement。

 I plus plus to the end of the loop。But notice that we also put i++ right before the continue statement。

Now we have finished changing this for loop to an equivalent wire loop。

Since I will go out of scope at the end of the function anyways。

 we can get rid of the extra curly braces that we wrote here without changing our code's behavior。

Now we are ready to begin executing。We begin by calling our print remainder function。

 passing in negative2， 4 and5 as parameters， we then declare I and initialize it to low and reach our while loop。

I less than high is true， so we enter the while loop。I equals0 is false。

 so we skip past the if statement and print5 mod negative2 is 1。

 We increment I and now have reached the end of the while loop。So we go back to the top of the loop。

I less than high is true， so we enter the loop body。 again， I is not0。

 so we skip the if statement and print out5 mod negative 1 is 0。

 We increment I and then return to the top of the loop。I less than high is still true。

 So we go inside the loop body。 However， now I is 0。

 So we enter the thin clause of this if statement。 We print that we cannot divide by 0。

Increment I and now reach the continue statement。 The continue statement just takes us to the start of the loop again right before we check the loop condition。

 so we move the execution arrow back here。Now we just do the next loop iteration as you would expect。

 since i is 1， not zero， printing out a message and incrementing I。

We do the loop again with I being2， printing out that5 modD 2 is1。And finally， one more time。

Through the loop with I being 3。After this last iteration。I， less than high is false。

 So we skipped the body of the wire loop and returned from print remainders。

Now we return from Maine exiting the program。

![](img/d98926f05499fe16766d28016a49d264_2.png)