# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p49 19_03_06_使用GDB收集信息.zh_en -BV1Kp42117vh_p49-

![](img/ee036cf460e865f209228ce27638ac32_0.png)

Drew has given me a program called Roate。 and he told me there's a bug in it。

 So let's look at the program and see what it's supposed to do。And then see if we can find the bug。

Here in rotate do C， let's look at the main。Main calls test rotate。

And what this program is supposed to do is take a10， take a point such as 10。

 rotate it by an angle such as 90， and then see what point is the output。Here in test rotate。

 we're calling it with 1，0 and 90。 so we expect the rotated point to be 01。

And the function test rotate will let us know if we're getting the output we expect。

 So let's look at test rotate。It takes an x and Y value。

A number of degrees to rotate it by and then compares it to the expected value。

 Here we have two assert statements。 this one that compares the x value to what's expected and this one that compares the y value to what's expected。

And。This function calls rotate。With a point and a number of degrees。 So let's look at this function。

 rotate。Here it does the work of the rotation by calling these trig functions cosine and sine。

That are included in the header mathth dot H。So let's run this program。And see what the bug might be。

Rotating 10 by 90 degrees， that was our first test case。Assertion failed。

And the assertion that failed concerns the y values。

 So we're having trouble transforming the y value to get the one we expect。Back in Emax。

 we can run the debugger to see what the values are in this program as it runs。

And see if we can find where it's doing something we don't expect。So I'll do meta X， GB。

Run it default。And once you start the program， it'll stop just after it enters main。

And in this program， there's probably no problem in Maine， we're just calling test rotate。

In test rotate。The work is really being done by the function rotate。

 and we can see that two lines later， this assert here is what's failing。

So somewhere in this function， rotate。We're probably doing something we don't expect。

 So one way to investigate that is to set a break point just inside the function rotate。

You can also set a breakpoint at a line number， but here I know which function I want to look at。

And then I'll continue running。Change buffers， I'm going to look at the program。Okay。

 so here I've set。A break point on the line just inside the function rotate。

And I'm about to execute this command that changes P dot X。And rotates it by 90 degrees。

 So one thing I can do if I， I'm very interested in the values of P dot X and P dot Y。

 So one thing I can do is display their values。And that way， each time I advance the code。

 it'll tell me what the values of those are。And I can do the same thing for P dot Y。10。

 those are the input values。 so at this point in the program， that's what I expect。So I will step。

And I've stepped into sign。 that's not what I meant to do。

 So if you enter a function that's not useful to you。

You can finish and go to the end of that function。And then I will advance to the next line。

So now the values of p。 x and p。 y have changed， P。 x is something times 10 to the negative 17th。

 very， very small， so close to0， and we're expecting the output to be 01， so that value of P。

 x makes sense， we're okay with that。Advancing past the next line。

 and we get a value for P dot Y that's also very small， that's not what we expect。

 we're hoping to get the 0。01 out of this。So let's see why this calculation on P do Y。

Might not be giving us the answer we want。The input value of p X is 1。Sine of 90 is1。

 so that part should be1 plus input value of p dot y is0 times the cosine of 90 is 0。

 so this line should say 1 plus 0， but somehow it's giving us the answer 0 instead。

Can you figure out why。Here we're using P dot X， but we're expecting it to be the value we had on input1。

However， we've changed its value on the previous line。So how can we change that。

 We'd like to preserve the input values of x and y。

 And one way to do this is to create a new point T called answer。

And then we will instead assign values to the answers X and Y。And then we will return our answer。

So let's save that。And compile。And then。And let's run GDP again。

We're stopping at that same break point。 once again， let's display P dot X。And P dot Y。

They're 10 on input。 That's what we expect。Advance to the next line。P do Y and P dot X are unchanged。

 That's the behavior we want。Let's print。The value we just assigned answer dot x close to0， good。

Advance it again。And then， print。The value of answer dot y。One， that's also what we expect。

 So I think we fixed our program。 Let's go ahead and clear the break point in this function。

And run it until the end。So here's the output from our program。

It's gone through all of these test cases， rotating 10 by 90 and got 01。

 That's what we expect rotating 01 by 90 and getting negative 10， also what we expect。

You could do some of these in your head and make sure they're right。

 But the important thing is that none of our assert statements failed。

So it looks like we fixed our program and we can quit the debugger。



![](img/ee036cf460e865f209228ce27638ac32_2.png)