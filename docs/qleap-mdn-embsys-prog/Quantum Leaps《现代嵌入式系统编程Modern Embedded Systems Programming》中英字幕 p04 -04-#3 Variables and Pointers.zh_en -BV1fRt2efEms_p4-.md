# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p04 -04-#3 Variables and Pointers.zh_en -BV1fRt2efEms_p4-

🎼Welcome to the embeddedded System programming course。

 My name is Miro Samak and in this lesson I'm going to talk about variables and pointers。

Let's start with making a copy of the previous lesson 2 project and renaming it to lesson 3。

 If you don't have the lesson 2 project， you can get it online from statemachine dot com slash Quickstar。



![](img/60f32a7444fbba11bdc88f6b25d3ac70_1.png)

Get inside the new lesson 3 directory and double click on the workspace file to open the IR tool set。

 If you don't have the I tool set， go back to lesson 0。

 So here is the C program you've created in lesson 2。

 Let's clean it up a bit and have a quick look in the debugger to see where the counter variable lives and how it is accessed。



![](img/60f32a7444fbba11bdc88f6b25d3ac70_3.png)

As you step through the code and watch the locals window。

 you see that the counter variable lives in the R0 register and is accessed by the machine instructions directly。

Now。Let's move the variable definition。Outside the main function。Recompile。

And go back to the debugger。Interestingly， the variable counter is no longer visible in the local's window。



![](img/60f32a7444fbba11bdc88f6b25d3ac70_5.png)

This is because it is no longer local。To see the counter variable now， we need a different view。



![](img/60f32a7444fbba11bdc88f6b25d3ac70_7.png)

Select the view menu and click on watch Watch1 view。 When the watch window opens。

 click on the first line and type the name of the variable counter in our case。



![](img/60f32a7444fbba11bdc88f6b25d3ac70_9.png)

As you can see， the location of the counter variable is now a big number starting with hex 2。

This address is the beginning of the random axis memory in this particular arm cortex and microcontroller。

 So the counter variable lives now in Ram。If this is really the case。

 then the variable should be also visible directly in the memory window。To check this。

Set the memory view to。2 he，0，0，0，0。And change the memory setting to four times units。

To conveniently see 4 byte integers。Now let's single step through the code。

And watch the various debugger views。

![](img/60f32a7444fbba11bdc88f6b25d3ac70_11.png)

Note that the STR instruction caused a change from 0 to1 in the watch1 view and in the memory view。

Now， the value changes to 2。Now to 3。And so on。

![](img/60f32a7444fbba11bdc88f6b25d3ac70_13.png)

Let's try to understand the machine instructions that the compiler has generated to access the counter variable in memory。

 The first interesting instruction is the LDr dot N， which stands for load from memory to a register。

 The LDR dot N instruction loads something from the label。 Que mark。

 question mark main2 to the R 0 register。 You can actually scroll down to this label to see what's being loaded。

 Hey， this looks familiar。The value loadeded to r0 is the address of the counter variable。

Let's execute the LDR dotN instruction and watch our0。The next LR instruction loads r0 again。

 but this time the value comes from the address that the r0 currently holds。

Which is the address of the counter variable。

![](img/60f32a7444fbba11bdc88f6b25d3ac70_15.png)

Single step and verify that R0 now has the value of 3。



![](img/60f32a7444fbba11bdc88f6b25d3ac70_17.png)

The AdS instruction does the actual work of incrementing R0 by1， so R0 becomes4。

The next LDR instruction loads the address of the counter variable to R1。And finally。

 the SDR instruction stores the value of the R0 register to the memory pointed to by the R1 register。

 Please note how the watch1 and memory views change after the instruction executes。



![](img/60f32a7444fbba11bdc88f6b25d3ac70_19.png)

At this point， I hope that you start to see the general pattern of accessing memory in the arm processor。

Arm is an example of the socalled reduced instruction set computer architecture risk。

 where memory can be only read by the special load instructions。

 then all data manipulations must happen in the registers。

 and finally the modified register values can be stored back into the memory by the special store instructions。

This is in contrast to the complex instruction set computer architecture Sic。

 such as the venerable X86 inside the personal computer。

Where some of the opera runss for complex opera instructions don't need to be in the registers。

And can be still in memory。But regardless of the process or architecture。

 I hope that you start to appreciate the role of memory addresses because every access to memory necessarily requires the knowledge of the address to load the data from or to store the data too。

All this leads to an interesting question。 If those memory addresses are so fundamental to the CPU。

 can they be somehow represented at the C language level。The answer is， yes。In the C language。

 the addresses can be stored inside variables called pointers。



![](img/60f32a7444fbba11bdc88f6b25d3ac70_21.png)

Here is an example of a pointer variable in C。Like most sea declarations。

The best way to explain this one is to read it backwards。So P underscore int is a pointer。

 which is what the star means after the type to integers。In other words。

 P and is a variable that can hold addresses of integer variables。If so。

 then P underscore score in should be able to hold。 among others。

 the address of the integer counter variable。Indeed， this can be very easily achieved in C。

 The operator Ampersant gives the address of the counter variable。

 and this address can be legally assigned to P in。Finally。

 it is also very useful to get the value stored at a given address from the pointer。

 which is called dereferencing the pointer。The C operator for this is the star。

Star P in means the value at the address currently stored in the P end pointer。

 which is the value of the counter variable because of this equivalence。

 you can replace counter with star P in， and the program should work exactly as before。

Let's see if the compiler is happy with this program。All right。

 so now let's go to the debugger and prepare the views。 This time。

 we need both the watch1 view to see the counter variable and the locals view to watch the P and pointer。

Before you step through the code， let's take a look at the disassembly view and compare it side by side with the code before introducing the P and pointer。



![](img/60f32a7444fbba11bdc88f6b25d3ac70_23.png)

As you can see， the LDR instruction， which loads the address of the counter variable to the R0 register。

 has been moved to the top。And another copy of the same instruction has been removed altogether。

In other words， introduction of the P end pointer has simplified the machine code and improved its efficiency。



![](img/60f32a7444fbba11bdc88f6b25d3ac70_25.png)

Now you can single step to the code and watch the counter variable increment。

Both in the watch1 view and in the memory view， exactly as before。

This confirms that the pointer is indeed an alias of the counter variable。Finally。

 if you want to execute the loop to the end but are getting tired of single stepping through the code。

 you can set a break point after the loop and click the go button to execute the program at full speed。

After you stop at the break point， you can verify that the final counter value is 21， as expected。

In the last step of this lesson， I'd like to demonstrate the incredible power of pointers。

 At this point， it will be just a horrible hack， but it will show you a technique that is actually used all the time in the metays programming。

As I said before， a pointer variable like P N holds the address of an integer。

But this can be almost any address， not just the address of the counter variable。 If so。

 then let's try to assign a fabricated address to P in。 In your first attempt。

 you might try to use an address expressed as a hex number。 just as you saw it in the debugger。

But when you compile it by pressing F7， the compiler rejects the code。In your next attempt。

 you might try to use an unsigned number by preparinging the use suffix to the number。

But the compiler doesn't like this， either。At this point。

 your negotiations with the compiler really break down。

 But the C language has a mechanism to enforce a type by using type casting。

You perform such type casting by placing the name of the type in parentheses in front of the cast expression。

Now the compiler has no choice but to accept it。All right。

 so now let's dereference the pointer and poke some easily recognizable integer value into it。

 and whether it programmers seem to like dead beef for this purpose。Obviously。

 this hack needs to be tested， but to preempt your objection that the simulator can take anything。

 I'd like to run this code on the Stlaris Lapad board。 So if you have the board。

 plug it into the USB connector of your PC。 Next， said the debugger。

To the T I stellarlaris interface。And also， don't forget。To check the option。

 use flash loaders under the download tab。If you don't have the board。

 just skip this step and follow along in the simulator。 Either way。

 click on the download the debug button to get to the debugger。



![](img/60f32a7444fbba11bdc88f6b25d3ac70_27.png)

Make sure that you have a break point at the reassignment of the pointer and also make the watch view visible so that you can see the counter variable。

Press the go button to run to the breakpoint and click in thisasse window to step one machine instruction at a time。

 Ex the LDR instruction， which loads the fabricated address to the R0 register and verify that this address appears in the end variable in the locals view。

 as well as in R0 in the register view。Execute the next LDR instruction。

 which loads the value Haggs dead beef to R 1。 and finally， execute the SR instruction。

 which stores dead beef in memory and the P and address。 The effect of this is kind of scary。

 due to the intentional misalignment of the fabricated address。

 The Hag's dead beef value gets written partially over the counter variable and partially over the next word in memory。

 The cortex M4 processor accepted this misaligned address。

 But cortex M 0 would have a problem with it。

![](img/60f32a7444fbba11bdc88f6b25d3ac70_29.png)

![](img/60f32a7444fbba11bdc88f6b25d3ac70_30.png)

So now you see how pointers as any powerful mechanism can also be dangerous， if used carelessly。



![](img/60f32a7444fbba11bdc88f6b25d3ac70_32.png)

🎼This concludes this very quick introduction to pointers in the next lesson。

 you will put this knowledge to use to blink the LED of the Stlaris Lapad board。

If you like this channel， please subscribe to stay tuned。You can also visit statemachine。

com/quistart for the class notes and project file downloads。



![](img/60f32a7444fbba11bdc88f6b25d3ac70_34.png)