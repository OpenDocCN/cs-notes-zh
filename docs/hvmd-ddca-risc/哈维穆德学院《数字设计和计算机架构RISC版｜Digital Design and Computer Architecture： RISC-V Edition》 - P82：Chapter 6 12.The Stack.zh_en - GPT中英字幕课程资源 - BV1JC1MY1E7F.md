# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P82：Chapter 6 12.The Stack.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/fa34c243685493d8011e225af018d7ff_0.png)

Hello， in this video we'll talk about the stack。So a stack is part of main memory used to temporarily save variables。

It's kind of like a stack of dishes last in first out Q。

 if you put more dishes on the top of the stack， then when it's time to pull them off。

 those same ones come back off the top of the stack in the same water。So a stack can expand。

When you need more memory space and it can contract when you're done and you don't need the space anymore。

In computer architecture， the stack is upside down。

 it generally grows downward from a highest memory location to a lower address。

And there's a register called the stack pointer， S， one of the 32 registers。

That points to the top of the stack。So imagine we had some memory。And。At the top of this stack。

 the stack pointer is pointing to some data。Ys。Topmost element。

And now let's suppose we wanted to put two more words on the stack。So the stack grows down。

 So the stack pointer moves down by two words。And the old value stays in place。

 but we can put on two new values。Like this。And here's the stack pointer now。

 pointing8 bys slower in memory。So when we're doing function calls。

 remember we said function calls must have known unintended side effects。

But recall the difference of sums function overwrites3 registers， T 0， T 1 and S 3。

And so we may want to save those registers before we change them and then restore them before we return from the function。

So here's an example of doing that to save three registers， each registers 32 bits or4 bytes。

 so we need to move the stack pointer down by 12 bytes to make room for the three things。

Then we can store word。We can store S 3， T 0 and T 1 on the stack at 0。

4 and 8 above the top of stack。Now we've saved away the values we're free to do our Dff of sums function that touches T0。

 T1 and S3。And it puts its result in a 0 at the end。Next。

 we want to clean up by restoring the values。 So we use a load word to load T 3。

 T 1 and T 0 back again from 8，4 and 0 relative to top of the stack。And finally。

 we moved the stack pointer back to where it was before。

 so now we're all done and none of the registers have changed except a0。

 which was supposed to hold the return result。And the stack pointers back where it was before we started。

 and now we return with our jump register to RA。So here's looking at the stack and picture point of view。

So let's say the stack pointer was initially here， some top of stack。

And whatever was on it from previous function。Now we move the stack pointer down。By 12 bytes。

 three words， and we put S3， T0， and T1 on the stack in that order。During the call。

 they're saved there and after the call， the stack pointer moves back up to where it was。

So now let's think about which registers we really need to handle。嗯。带来。

S registers are used to represent variables。And so when a function calls another function and comes back。

 it's reasonable to expect that your local variables haven't been trashed。

 So we need to save those across a function call。The same way the stack pointer。

 when we're done with a function call a stack pointer should be back where it was。

 and the return address register should be unchanged so that we know where to return to。

And any parts of the stack above the stack pointer shouldn't have gotten trashed either。

So if a function that was called， in other words， the call E。Want to use any of those。

 the S register stack pointer or RA。 It needs to save them before it can use them。

The temporary registers and argument registers are what we call not preserved。

So temporary registers are intended to be temporary and you can't count on them keeping their value across a function call。

So if the color does want them to keep the value， it should save those itself。In the same way。

 the caller is going to pass arguments in a0 through a 7。 So they're inherently getting changed。

 If the caller cared about the old values of the A registers before making the function call。

 the caller was responsible for saving those。So， let's revisit diff of sums。But this time。

 only S3 needs to be saved。Because it was one of the preserved registers。

 Diff of sums has to promise it won't trash any of the S registers。

 but it's free to do what it wants with tea registers。So here in diff of sums。 Now。

 we're only going to move the stack pointer down by one word，4 bytes。Stirway S3。

Now we can do our F plus G or H plus I， put our answer in sorry S3， and then copy it over to a0。

Now we clean up。With the load word to restore S3 off of the stack。

And bring the stack pointer back up。We could do even a little better。 We might as well。

 since the result was going in a 0 anyway， there was no particular reason to put it in S 3 along the way。

 And if we don't use S 3 that we didn't need to save or restore anything。

 So now here's an oftenized diiff of sums that just puts our answer。

In a0 and doesn't have to save or restore anything。Let's say we had a non leaf function。

 That was a function that was going to call another function。

So let's say we're in function  one and we want to call function two。Before we can do that。

 function1 needs to know where to go back to。So it needs to move the stack pointer and save its return address onto the stack。

Then it can call F 2。That will mess up RA。So when we come back， we've got our answer in a0。

 and we need to load RA back off of this stack。And move the stack pointer back to where it was。

So any sort of nonlay function that's going to call another function is responsible for saving the return address first。

Here's an example of a somewhat more complicated pair of functions。F1， F2。

 let's say F1 is a non leaf function because it calls F2。

 F2 is called a leaf function because it doesn't call anything。Say F1 uses S 4 and S5。

 and it also needs a 0 and A 1 after it comes back from it's called F2。So， F1。Willll start by。

Making room for five things on the stack， moving the stack pointer down by 20 B。

It will save a 0 and A1 that it needed。 It will save its return address。

 So F1 knows where to go back to at the end。And it will save S 4 and S5。That it wants to use。

Then we can do a jump and link to function 2。We can do a bunch of other stuff in F1。

 including possibly messing up S4 and S5 as we're using them for internal variables。

When we're all done。We need to load the return address back off of the stack。

Move the stack pointer back up to where it was。 Restore the other variables that we cared about。

And jump back to the return address。F2 is a little simpler。 Let's say it's only using S4。

 that's the only saved register that it needs。 and it doesn't call any other functions。

So all it has to do is save S 4 on the stack， Mo the stack pointer down by 4。

Storetores S4 on the stack， does its business and then restores S 4 off of the stack。

 brings the stack pointer back to where it was。This should be a plus four。

And then jumps back to the return address。So here's an example of a stack during the function calls to say the stack pointer was initially here somewhere at top of stack。

And then we call F1， we'll put a0 A1 RA。S 4 and S 5 on the stack。

 And this is known as the stack frame。For function F1。Then， when we call F2。

A stack pointer will move down。Yet another word。NS F2 will save its S4 register on the stack in the F2 stack frame。

Once we're done with F2， we'll delocate F2 stack frame and the stack pointer moves back to here。

And once we're done with F1， stack pointer comes back up to here。So in summary。

When a caller wants to call another function， it puts any arguments in a0 through a7。

It saves any registers that it might need。That would include RA and possibly the temporary or A registers。

 which is better save before it put the arguments into it。

And then it will call the colleague with jump and link。When it comes back。

 it will restore any registers that it saved and still needs， and it will look for the result in A0。

The colleague。Will save any registers that it might。

 any preserved registers that it might want to disturb， such as the S registers。

It'll perform its function and then put the result in A0。

 restore those registers that it touched and return with a jump register already。



![](img/fa34c243685493d8011e225af018d7ff_2.png)