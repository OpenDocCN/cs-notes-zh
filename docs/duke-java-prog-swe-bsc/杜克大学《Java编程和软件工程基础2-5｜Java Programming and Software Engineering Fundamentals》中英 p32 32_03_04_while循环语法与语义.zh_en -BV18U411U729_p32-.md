# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p32 32_03_04_while循环语法与语义.zh_en -BV18U411U729_p32-

![](img/134344c2502829c68ab396671bf1c4e0_0.png)

To implement our improved gene finding algorithm， you need to learn about while loops。

 the code that generally comes up when you have a step in your algorithm like。

 as long as some condition is true。

![](img/134344c2502829c68ab396671bf1c4e0_2.png)

![](img/134344c2502829c68ab396671bf1c4e0_3.png)

You can see an example of a while loop here。 Let's look at this example to delve into the syntax and semantics of the while loop。



![](img/134344c2502829c68ab396671bf1c4e0_5.png)

![](img/134344c2502829c68ab396671bf1c4e0_6.png)

All while loops start out with the key word while。

![](img/134344c2502829c68ab396671bf1c4e0_8.png)

Then they have some condition， sometimes called a guard in parentheses。



![](img/134344c2502829c68ab396671bf1c4e0_10.png)

This is the condition that you want to check to see if you should continue doing the loop。



![](img/134344c2502829c68ab396671bf1c4e0_12.png)

Then you have the loop body in curly braces， these are the statements that should be executed each iteration of the loop。



![](img/134344c2502829c68ab396671bf1c4e0_14.png)

Let's walk through this example to understand the semantics of the loop。 what it means。



![](img/134344c2502829c68ab396671bf1c4e0_16.png)

For example， let us assume that x was previously declared and initialized to 0。

 and y was initialized to 7。 When execution reaches the while loop。

 The first thing that happens is Java evaluates the condition is x less than y。



![](img/134344c2502829c68ab396671bf1c4e0_18.png)

![](img/134344c2502829c68ab396671bf1c4e0_19.png)

In this particular case， that means is zero less than7。Zero is less than7。

 so the condition evaluates to true。Since the condition is true。

 execution will enter the loop body and continue executing statements there。

The first statement prints x， which is 0， so we would output the line 0。

 The second statement sets x to x plus 3， which would update the value of x  to be 3。



![](img/134344c2502829c68ab396671bf1c4e0_21.png)

Now， execution has reached the end of the loop body。 The closed curly brace marks its end。

Then execution goes back up to the start of the loop。 And we are right back where we started。

 but the variables have different values。 X is 3 instead of 0。We continue following the same rules。



![](img/134344c2502829c68ab396671bf1c4e0_23.png)

Evaluate the condition 3 is less than 7。 The condition is true。 So we enter the loop body。 print X。

 which is 3。

![](img/134344c2502829c68ab396671bf1c4e0_25.png)

![](img/134344c2502829c68ab396671bf1c4e0_26.png)

And update x to be 6。Now， we have reached the end of the loop again。

 So we go back up to the start of it。 And again， follow the same rules。 Check the condition。

 It is true。 So we enter the loop body， print X， which is 6。 Upd X to be 9。

 Now we have reached the end of the loop body again。 So we go back to the start。 Yet again。

 we follow the same rules。

![](img/134344c2502829c68ab396671bf1c4e0_28.png)

![](img/134344c2502829c68ab396671bf1c4e0_29.png)

Now， when we evaluate the condition， something different happens is 9 less than 7。



![](img/134344c2502829c68ab396671bf1c4e0_31.png)

![](img/134344c2502829c68ab396671bf1c4e0_32.png)

No， so the condition is false。 Instead of entering the loop body， we go past it。

 We would then continue executing whatever statements come after the loop。



![](img/134344c2502829c68ab396671bf1c4e0_34.png)

![](img/134344c2502829c68ab396671bf1c4e0_35.png)

Great， now you have learned the basics of while loops， their syntax。

 the grammatical rules for writing them and their semantics， their meaning。 Now。

 you are ready to go code your improved gene finding algorithm。😊。



![](img/134344c2502829c68ab396671bf1c4e0_37.png)

![](img/134344c2502829c68ab396671bf1c4e0_38.png)

![](img/134344c2502829c68ab396671bf1c4e0_39.png)