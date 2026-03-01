# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p57 05_01_03_硬件级交换.zh_en -BV1Kp42117vh_p57-

![](img/67854699d35a5661ec7d67447643f6e1_0.png)

In this video， we're going to revisit our swap function。

 paying special attention to a few things that happen at the hardware level。

 recall that memory is divided into different sections that have different purposes in this video。

 because our function doesn't actually use the heap or static data。

 we're only going to be looking at what's happening in the stack and what's happening in the code section of memory。



![](img/67854699d35a5661ec7d67447643f6e1_2.png)

The first thing we'll do is imagine what the code might look like in memory。

 What I've done here is assume that each instruction of the program takes up exactly four bytes。

So you'll see that each of these instruction blocks is far away from the next。 Now。

 whether this is exactly accurate or not depends a lot on the machine the program is running on。

 You can think of this as a representative drawing。

You'll notice that because memory's address increased going upwards。

 the first instruction from mainine， where A is being set to three is actually the bottom of memory。

 and you always move to a higher instruction in memory as you progress through the program。

At the top of memory， we have our stack where we store all of the local variables that our program needs。

 so let's show you what the stack might look like here。Previously， in our conceptual drawings。

 we have always shown the stack frames as separate boxes， each with their own label。

 which was the name of the function that we were in at the time here with a more hardware centric view of memory。

 We're going to show the stack as it really is， which is one continuous stretch of memory that just moves from one stack frame to the next。

 I'm going to use two different colors to highlight the sections of the stack frame for the functions's main and swap。

😊，Here， the stack frame for main is highlighted in blue。

 and the stack frame for swap is highlighted in purple。

There's another slight difference in the way stack frames are built in this video versus the way we've been showing the stack frames in previous conceptual videos。

 We're going to put the parameters in the stack frame for the call instead of the called function。

 which matches more closely with how things happen in the hardware。

We can begin executing our program now and we'll execute the first instruction。

 setting the value of A to B3。The next instruction sets the value of B to be 4。

The next thing we want to do is call our swap function， and to do this。

 we need to prepare its two arguments。The first argument is the address of a。

 so we look in memory to see what the address of a is。In this case， it's FFFC。

 So we store this value on the stack in the location for the parameter x in the swap function。

The next argument to swap is the address of B。 So we look in memory to find the address of B， FF F 8。

And we store that on the stack in the corresponding location。 Now。

 we're almost ready to call our swap function。😊，In previous videos。

 we would often mark a call site location with a little numbers circle。 In this case， a one。

 we're going to be a little more explicit about how this works now that we have a better understanding of how pointers work and how code sits in memory。

 In fact， the last box in our stock frame is going to be dedicated to what's called the return address。

 What the return address tells us is what is the next instruction we should execute when we finish executing the swap function。

😊，In this case， the next thing we should execute is the line of code in which we call printntf。

 this is located at address 4008 in memory， so we store the address 4008 for the return address。

 and this will tell us what to execute next when we're finished executing our swap function。Now。

 we can go in and execute our swap function。 Re that the swap function now has its own stack frame shown here as a purple box that holds only one variable。

 The first line of code is going to take the thing that x points to and store that in the variable temp。

If we look at x on the stack， we can see it has the value FFFCc。

 which is pointing to the value 3 in memory， which is the variable A。So we're going to take three。

And store it in our temp variable。The next instruction is a little more complicated。

 We need to figure out both the L value and the R value of this assignment。On the left。

 we have the thing that X is pointing to。 so once again， let's go see what x is， the address FFFCc。

It's pointing to the box with the address FFFC， and this is the box whose value will be changed when we execute the assignment statement。

Now let's take a look at the R value， the thing that y is pointing to y is FFF8。

 and it's pointing to a box with4 in it， so what we're going to do is take the value 4 and store it in the box with the address FFFCc。

 namely the variable A。And now our final line of code will finish up the swap function for us In this case。

 the L value is that which y is pointing to， so if we look at y it has value FFF8。

 so we're going to change the box whose address is FFF8， namely the box B。

What value do we store into this box， the value of temp， which is3。

So we store three into the box with address F F F 8。 Now we've completed the entire swap function。

 At this point， we no longer need our stack frame for swap。

 So now the only stack frame we have is the blue stack frame for main at the bottom of this stack frame we have a pointer that tells us the next line of code we should execute after returning from the swap function。

 So we're going to do exactly that。 we're going to move our execution arrow to the code that has address 4。

0，0，8。 And now we would execute the rest of the code for the rest of main。

