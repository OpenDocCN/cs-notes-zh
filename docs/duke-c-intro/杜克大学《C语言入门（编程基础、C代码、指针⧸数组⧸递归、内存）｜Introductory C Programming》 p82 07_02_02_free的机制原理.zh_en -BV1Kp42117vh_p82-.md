# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p82 07_02_02_free的机制原理.zh_en -BV1Kp42117vh_p82-

![](img/195b4999a6ae9fd43642f9db05d633ed_0.png)

Now that you can allocate memory with Malik， you also need to decate that memory when you are done with it using free。

 We are going to start this example code to show you the semantics of free。

 We have declared P and initialized it to point at an array of 4"s allocated by Malik。

 We then filled in the array with some data。 and to illustrate another point at the end。

 We made another point or Q and set it equal to P。😊。

We have a comment with dot dot dot to suggest that we have skipped showing whatever code would do some useful calculation with this data。

We now show the state right here before a call to free。

Let's now see what happens when we execute free。First。

 notice that we have passed the pointer P to free free P does not actually affect P。

 but rather the memory that P points to。Let's look at where P points。 It is this block of memory。

 the array of 4"， which Malick gave us earlier。Freeing this memory destroys that box and leaves P dangling。

Any further use of the memory pointed to by P is invalid， as with any dangling pointer。

 noticeice that since Q points at the same place as P， Q is also now dangling。

 We should not attempt to de referenceence Q either。 All right， Now。

 let us try a slightly more complex example。 Again。

 We are going to start at the point in the code where we are going to free things。

 What is the state of the program at this point。 You should work that out yourself before we proceed。

Hopefully， you came up with a program state that looks like this。

 We are just using multiple colors of arrows to help you keep straight what points where the arrow color does not have any special meaning。

😊，First， we step inside our for loop， creating I and initializing it to 0。

 We are going to free P at I。 I is currently 0。 So the pointer P at 0 is this arrow here。

 We will release the block of memory that point that it points at here。😊，Now。

 we have finished the call to free。 Notice that the pointer is now dangling。

 That is fine as long as we don't dereence it。We go to the next loop iteration and free the memory pointed to by P at1。

We execute free。And go to the next loop iteration。We step inside the for loop and free P at2。

We go back to the start of the for loop again and free P at3。Now I is4， so we exit the four loop。

Finally， we free P， which also points at memory that was allocated by Malik。

 Freeing P releases that memory， and now we have freed everything we allocated with Malik。😊。



![](img/195b4999a6ae9fd43642f9db05d633ed_2.png)