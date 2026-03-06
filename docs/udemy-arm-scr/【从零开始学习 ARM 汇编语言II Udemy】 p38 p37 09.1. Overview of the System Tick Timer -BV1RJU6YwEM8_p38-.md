# 【从零开始学习 ARM 汇编语言II Udemy】 p38 p37 09.1. Overview of the System Tick Timer -BV1RJU6YwEM8_p38-

Hello， welcome back and this lesson we shall give a brief overview of timers。

Let's begin by talking about the system timer or the system take timer。

 the systemtic timer is presenting allA cortex microcontrollers irrespective of whether it's STM 32 LPC。

 TVC series， etc。The systemic timer allows the system to initiate an action on a periodic basis。

This action is performed internally at fixed rate without external signal， for example。

 in a given application we can use cyststic to read a sense of value。

 let's say every 200 milliseconds。Sysistic is widely used when designing realtime operating systems so that the system software may interrupt the application software periodically to monitor and control the system operations and those of you take in my othercourse on building your own realtime operating system。

 you saw how we use S as our time base to control everything and to sort of control our Sula the Ss is a 24 bit down counter driven by either the system clock or an internal oscillator。

 it counts down from an initial value to zero when it reaches zero in the next clock。

 it underflows and it raises a flag known as count and res the initial value and start all over again。

Now let's take a look at the cystic registers， when programming the cyst。

 we need to configure just three registers。We've got the system control and statusus register。

 the system reload value register， and the system current value register。

 and we shall see how to configure these registers programmatically。

Now let's see how to calculate the value to load into the Ci load Reg。

Let's say we want an action to occur every second if our clock frequency is 16 megaHtz。

 we simply need to load 16 million minus1 into the Ciic load register。

And we shall see how this works in code well 16 million minus1 because if our processor is running at 16 megaHtz。

 this means there are 16 million cycles in one second so in one second we are able to run 16 million processor cycles and because we count from zero。

 we do 16 million minus1 over here。How about one millisecond。

 let's say we want an action to occur every millisecond。

 how do we compute this Well we know there are 60 million cycles in a single second and we also know that one second equals 1000 milliseconds。

Then this means there are 60 million cycles in a000 milliseconds。

 so if 60 million cycles are in  a00 milliseconds， then how many cycles do we get in a single millisecond and we compute that by doing。

1 thousand milliseconds divided by0 equals 16，000 cycles divided by00， and this gives us 16，000。

So therefore， in a single millisecond we have 16，000 cycles。

 so if we want an action to occur every millisecond， we have to load 16。

000 minus1 into the Ci load register。Now let's take a look at the general purpose timer。

 apart from having the cystic timer in every cortex microcontroller。

 the silicon manufacturers like S， NxP， Texas Instrument。

 they also provide additional timers known as general purpose timers and we can use these timers to create delays and in fact measure the occurrence of events and other things。

 let's take a look at these timers。