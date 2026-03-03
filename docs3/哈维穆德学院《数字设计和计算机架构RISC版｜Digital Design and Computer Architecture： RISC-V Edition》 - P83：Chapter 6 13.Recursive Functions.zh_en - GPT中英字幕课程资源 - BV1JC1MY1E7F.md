# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P83：Chapter 6 13.Recursive Functions.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video we'll look at recursive function calls that is functions that call themselves。

To handle saving and storing registers， a recursive function call needs to pay close attention to what it needs to save。



![](img/170fc433d4ecfaa3ba81b566b9f5eaaf_1.png)

So again， a function， a recursive function call is a function that calls itself。

And when I'm converting it to assembly language code。

 I like to do a first pass where I just treat it as if it's calling a different function and ignore the overwritten registers。

 and then go back and think about how to save and restore the registers on the stack as needed。

So as a classic example of a recursive function call， imagine the factorial function。

 factorial of n also written as n exclamation point。

 which is n times n minus1 times n minus2 times n minus-3 all the way down2。Tms1。So for example。

 six factorial，6 times 5 times 4 times 3 times2 times 1， which is 720。

Here's a recursive definition of a factorial。If we want to do factorial of N。

We see if n is less than or equal to one will return the base case of one。Otherwise。

 will return n times factorial of n -1。So let's say our main function called factorial with n equals 3。

Facty of three will return three times factorial of 2。To find factorial of 2。

 we see it should return two times factorial of1。And a factorial of one will return one。

So now we come back up， a factorial of one was returning one。

 so factorial of2 is returning two times that one mix two。

And factorial of three is returning three times factorial of2， which is 6。Hi。

 let's take a look at how to code this。So again， on our first pass。

 we'll treat it as if we're just calling another function and ignore the stack。

And we get the black code。So factorial。We need to see if n is less than equal equal to1。

 So we'll put one in t 0。We'll do a branch on the opposite conditions。

 So we're interested in less than or equal to。 So we'll do a branch on greater than。

If n is greater than1。We'll go to El。Otherwise， we want to do the body and the body is at I a0 comm a 0 comma 1。

 we'll put a1 into our return register a0。And we'll jump back to the return address。

If n was not less than or equal to 1， then we want to do the else part。

Where we need to do n times factorial of n -1。So， we need to put。

N-1 into the a register by adding the old value of n。And-1， put that in as our new argument。

And then we'll jump in link to call factorial。When we return。Will multiply。Or N。Times。

The return result。And。Sorry， a 0 is our return result。T1 is going to be the N that we get back。

 and we'll look at restoring that in a moment。Let me say this again。T 1 is the end that we head back。

A0 is the result of calling factorial of n minus1， and we'll put that in a0 to be the return result from our factorial and then jump back to RA to return to the color。

So。That's the main logic。 Now， let's look at saving and restoring registers。

So anytime factorial is going to call itself， it needs to save return address register because we need to know back where to go back to before we change it with a jump in link。

And we also need to restore or we need to save our value of n because we're going to change it when calling factorial。

So let's make room for two registers on the stack。It will save away A 0 and RA on the stack。Now。

 if we don't have a recursive call， we'll just restore the stack pointer and there's nothing else to do。

But if we are making the recursive called effect trail， then when we come back。

 we need to restore the value of n。But。And had been stored in A 0。Now。

 factorial return of n -1 returned its answer in a0， so we'd better not put n back in A 0。 instead。

 let's put it in T1。We'll also restore RA so our factorial knows where to jump back to。

And will' add 8 to the stack pointer。And that way， clean up the stack。And now， here at the multiply。

We're going to make our result be N。Which is now in T1 times the result of factorial of n -1。So。

Suppose this pre factorial function began at address 8500 in memory。Then the jump in link is at 8524。

And we want to store 8528 in the RA register as the place to come back to from each jump in link。

So imagine we're following the stack frames as we do this call。

So suppose the stack pointer initially at FF 0。And we begin our call。So on the first time we call。

 we'll move the stack pointer down。To F F 8。And we'll put a0。Which was three and of three。

 And the return address。Say to the main。Function at called factorial of three。Now。

 factorial of  three is going to call factorial of 2。And so we need to move the stack frame again。

To FF。0 and store away a0 from the second call。Which is now two。And the return address。

Which is now 8，5。2，8， or to return to factorial of three。Now。

 factorial of 2 is going to call factorial of 1， so we need to store away a0。

 which is the value of n of 1 and the return address， 8528。Of whatever。

Turn to from the call to factorial 2。Now， when we're all done。

Factial of one will return the value1 and bring the stack pointer。Back up here。嗯。Factorial of one。

We'll get the sorry， factor of 2 We'll pull off its value of n of 2， multiply it by the one。

 put its answer as2 and return to the address that was here。Pringtting the stack pointer back up。

And now we're in factorial of three again。Which will multiply its n of  three recovered from the stack times the two returned by factor of 2 to get an answer of 6。

And。Pull off its return address so it can return to mainine when it's done， and before it does that。

 it'll bring the stack pointer back up to FF0 where we began。



![](img/170fc433d4ecfaa3ba81b566b9f5eaaf_3.png)