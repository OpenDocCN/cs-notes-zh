# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p19 -19-#18 interrupts Part-3_ How interrupts work on ARM Cortex-M_.zh_en -BV1fRt2efEms_p19-

![](img/79930bc43e0700a1800184aad4575626_0.png)

🎼Welcome to the Modern embeddedded Systems programming course。

 My name is Misic and in this lesson I'll finally explain how arm cortex M handles interrupts。

🎼And why interrupt handlers can be regular C functions on the CPU。🎼Specifically。

 you will see how the designers of the chip have solved the problem with saving all the right CPU registers and returning from interrupt functions。

As usual， let's get started with making a copy of the previous lesson 17 project and renaming it to lesson 18。

 If you are just joining the course， you can download the previous projects from statemachine。

 com s Quickstart。Get inside the new lessons 18 directory and double click on the workspace file to open the IR tool set If you don't have the IR tool set。

 go back to lesson 0。To quickly summarize what happened so far。

 in the last lesson you saw how interrupts work on MSP430。

 which is simpler than Arcortex M and handles interrupts in a way that is much more typical for embedded CPUs。

Based on MSP 430， you'll learn that interrupts differ from regular functions in the two important ways。

First， interrupts return with a different machine instruction than regular functions。

 specifically regular functions like LED toggle return with the red instruction on MSP430。

 while interrupts like timer 0 handler return with red eye instruction。

 These instructions must be different because they pop different registers from this tag。Second。

 interrupts must save more registers than regular functions， For example。

 timer 0 handler saves registers R12 through R15， while regular function。

 timer 0 function with the exact same body does not need to save any registers。

So the question now is how arm cortex M addresses these two requirements so that it can indeed use regular functions as interrupt handlers？

As in the previous lesson， you will answer these questions experimentally to do this。

 you need to trigger the cystic interrupt on arm cortex M from the debugger so that you can precisely control when the interrupt occurs。

The method you used on MSP 430 was to set the counter register of the timer in the debugger to the value1 less than the limit。

 The timer then reached the limit on the next clock cycle， which triggered the interrupt。

Unfortunately， you cannot use this method with the assistic timer on Arcortex M because the ST current register is right clear。

 meaning that writing to it with any value clears the register without triggering an interrupt。

But not all hope is lost， as described in the Tva C data sheet。

 Arcortex M offers another even more direct way in which to manually set the interrupt pending bit in the interrupt control and state register。

 specifically B 26 in this register sets theistic interrupt to the pending state。 Okay。

 so let's use this information to generate the cyst interrupted will。

Loow the code to the Tva launchpaboard and set a break point at the top of the while1 loop Run the code When the breakpoint is hit。

 move the breakpoint to the very next LDr do N instruction and also set another breakpoint in your aistic handler。

Finally， in the register panel， select the system control block and expand the ICSR section。

Go to the pen S T set bit and set it to one。By the way。

 Cortex M provides an interrupt pending bit for every interrupt source。

 so you can trigger every interrupt in the system by this method。

Most of these pending bits reside inside a nested vector to interrupt controller， andviC。

But going back to your code， you have set up the following experiment。

You are stopped at the move as instruction by writing to the penS T set register。

 you arranged for the interrupt line to go high on the next clock cycle。

You have also placed two breakpoints at the two possible paths for your code。

One is at the very next LDR dot N instruction。 This breakpoint would be hit if the interrupt would not preempt after the move as instruction。

 and the program would execute as usual。Your other brakepoint is inside the cystic handler。

 This brakepoint would be hit only when they interrupt wood fire right after they move as instruction。

 thus preempting the normal program flow at this exact point。To experimentally settle this question。

 you cannot single step because it disables checking for interrupts after each instruction。 Instead。

 you need to let the programme run free。And the answer is。The dsistic interrupt has fired。

At this point， you have a verified method to trigger your interrupt at the machine instruction of your choosing。

You will use it in a minute to take a closer look at the interrupt stack frame and the interrupt return process。

 just like you did it in the previous lesson for MSP for30。



![](img/79930bc43e0700a1800184aad4575626_2.png)

![](img/79930bc43e0700a1800184aad4575626_3.png)

But before this， please go back to the project options and set the floating point unit FPU to none。

The FPO is a complex peripheral for speed up floating point computations。

 but unfortunately it adds complications to the interrupt processing which you don't want to deal with at this time。

All right， so after rebuilding your project without the FPU。

 you can finally take a closer look at the details of arm cortex and interrupt handling。

Let's set up the break pointss。And a trigger the cystic interrupt， exactly as before。But this time。

 let's also set up the memory view to watch the stack content。

Remember that the tag grows down on arm， so I scroll the memory view to place current S at the bottom。

Now， when you run the program。And hit the brake when inside the system interrupt。

 You can see that the S dropped by8 stack entries。When you look into the data sheet of your Tva CMCU in the section about the exception entry and return。

 you can see the internet stack frame without FPU。Remembering that data sheets show memory from high to low。

 you need to turn the picture upside down to align it with the memory view in your debugger。

When you do this， you can now identify which registers are saved on the stock。For example。

 you can identify the saved PC that is the address to return to after the interrupt。In fact。

 when you scroll up the disassembly window， you can see that the return address is the LDR dotN instruction inside the while1 loop。

But more importantly， let me mark for you all the registers saved in the interrupt stock frame with the hope that you might recognize this particular group。

Well， back in lesson 9， you learned about the arm application procedure call standard。

 A A PC S A A PC S was a convention that specified among others。

 which registers must be preserved by a function call。

 I mark these registers for you again so that you can see that this group precisely complements the registers saved in the interrupt stack frame。

So here you have the answer to today's first issue。

 Cortex M interrupt entry complements the arm pro standard。

 so that's why a regular C function can be used as an interrupt handler。

Please note that this elevates the AAPCS from merely a calling convention that in principle could be different for each compiler to a hard rule that must be implemented the same way by all compilers。

Okay， so now let's step through the interrupt function and take a look at how it returns。Well。

 the function returns in a completely standard way via the BxLR instruction， because after all。

 this is just a regular C function。But wait a minute。 the value in the L R register is Hx F， F， F。

 F F， F 9， which is negative 7 in toolss complement。 This is not the valid address in the code space。

 So what the hell is it。Well， this is an arm special when this special value is loaded into the PC。

 the cortex M hardware treats this as a return from interrupt。

That's why when you execute the BXLR instruction， you can see that the SB goes back to hex 3 F8 and that the contents of registers is restored to the preinterrupt state。

 The PC jumps back to your while1 loop， just after your original break point。

 which is exactly the point of preemption。So here you have the answer to today's second question。

 a standard return from a function works also as a special return from an interrupt because the LR is loaded with a special value upon the interrupt entry。

Another way of looking at this is that what other processors such as MSP 430 achieved by a special instruction interrupt return。

 I read。Armcortex M achieves by using special data content of the LR register in this case。

The arm solution based on data is actually more flexible and extensible than a special instruction。

 In fact， Arm provides several variants of interrupt returns。

 which are all summarized in the data sheet。I am not going to discuss in detail all the options which you can simply read about。

 but let me only quickly explain the terminology used in this table。



![](img/79930bc43e0700a1800184aad4575626_5.png)

Handler mode is the distinct processor of state when it handles an exception。

 such as an interrupt or a fault。 Thread mode is when it executes regular code。

 such as your while1 loop inside your main function。

Floating point state means here that FPU is activated and that interrupts use the FPU stack frame as opposed to the regular stack frame。

I am going to show you the FU stack frame in a couple of minutes。

MSP stands for the main stack pointer， while PSP stands for processorsor stack pointer。

The data sheet makes this distinction because your arm CPU has actually two stack pointers。

 S main and SP process， but only one of them is visible asP。

 depending on the internal state of the CPU。

![](img/79930bc43e0700a1800184aad4575626_7.png)

This concept is called Reg banking and is another of the Ar specials。At this point。

 I only mention banking of the SP register to explain the terminology。

 but the concept will be important when we'll talk about the real time operating system， Arts。

 which I plan to do in one of the future lessons。

![](img/79930bc43e0700a1800184aad4575626_9.png)

But to finish with the basic interrupt stack frame， let me only explain the optional aligner word。

 The purpose of this optional stack entry is to align the interrupt stack frame at an address that is a multiple of8 bytes。

The reason the hardware needs S to be aligned is to perform highly optimized block transfers of registers to and from the stack。

In fact， interrupt entry and exit take only 12 clock cycles each。

 which is very fast when you consider that eight registers are pushed or popped from the stack。

To show you when stack alignment will be necessary。

 let's run the program again but intentionally misaligned SP into debugger。As before。

 when the breakpoint in your while1 loop is hit， you trigger the cystic interrupt。

You also set up the memory view to watch the stock in the same way as before。

But this time to better see what has changed on the stack。

 you additionally prefill the unused stack above the current value of SP with some easy to identify garbage such as heggs。

 dead beef。And finally， you misalign the stack by subtracting4 bytes from the S。

If you wish you can check that the value Hx 3 F4 is not divisible by 8 After you hit the breakpoint in the system interrupt。

 you can see that the8 register interrupt stack frame has been pushed on the stack。But interestingly。

 one stack entry at address Hex 3 F0 has been skipped。 This is the alignr word。



![](img/79930bc43e0700a1800184aad4575626_11.png)

Upon the interrupter turn， the whole nine word stock frame is removed because the S goes back to the original misaligned value of hex 3 F 4。

Please note that in practice， stack misalignment should never happen。

 This is because the8 by stack alignment is a requirement of the A A PC S。

 and compilers make sure that the stack is always aligned。 Still。

 the stack alignment concept will be important when I'll talk about the real time operating system。

 Arts， in one of the future lessons。As a final subject of this lesson。

 let me show you the impact of the FU on the interrupt stack frame。



![](img/79930bc43e0700a1800184aad4575626_13.png)

To do this， please open the project options dialog box and reenable the FPU。

Rebuild the project and set up the interrupt entry experiment， exactly as before。

Note that right before they interrupt， the S hass3 F 8。

When the cystic interrupt is entered this time， please note that the S drops all the way to hex 390。

 which is 264 byte words。

![](img/79930bc43e0700a1800184aad4575626_15.png)

Also， please note that the LR is now set to Hx FffFF FFE9 instead of Hx FffFFFF9。

 which is the special FU type interrupt return utilizing the much bigger FU stock frame。



![](img/79930bc43e0700a1800184aad4575626_17.png)

。The moral from this is that you need to size the stack significantly bigger if you use the FPU。

 there is also an additional price to pay in longer interrupt entry and exit time。

🎼This concludes this lesson about interrupt entry and exit on arm cortex M。 In the next lesson。

 I'll talk about race conditions， which is a concept that you absolutely need to understand to effectively work with interrupts。

If you like this channel， please subscribe to stay tuned。You can also visit statemachine。

com/quistart for the class notess and project file downloads。

