# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P134：Chapter 9 6.Timers.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video， we'll talk about making delays and using timers on a microcontroll。



![](img/326b09e4776df28ee874e1bc985b6c04_1.png)

So one of the most common things that you need to do in interacting with the real world is to measure time or generate an interval of time。

So let's start with a simple way of making delay just by having a loop in a program。

So suppose we wanted to delay for a certain number of milliseconds。We could declare an integer eye。

And。Set it to some value and then count down to 0。 So while I minus minus keeps counting subtracting one for I until he get down to 0。

If we set the initial value as the number of milliseconds we want to wait times some number of counts per millisecond。

And then we calibrate that counts per millisecond with a stopwatch。Until。

We account for the desired amount of time， then this will make a loop。So when I did this。

 I found it needed about 1，600 counts for one millisecond to go by or 1。6 million counts per second。

So this is a simple program to generate delay。And now we could say。Flash a light。By say。

 making pin 5 an output， remember， pin 5 is hooked up to the blue LED。And then we have a loop。

And in that loop， first， we turn pin 5 on， make the LED on， wait for 500 milliseconds， half a second。

 then turn it off and wait again， and this will blink the LED indefinitely。

So trouble with that delay loop function is it requires calibrating the counts per millisecond。

First of all， that's kind of tedious to do by hand。 Second seemed exact。 was it exactly 1600。

 or maybe it was 1670。 I didn't measure accurately enough with my stopwat to know。And finally。

 if the compiler changed， let's say it made some better code that ran the loop faster。

 then the amount of delay would no longer be accurate。

So a better way to make delays on a microcontroller are with a peripheral called a timer。

Many microcontrollers have a whole bunch of timers。

 Our particular one has a single 64 B timer that counts ticks of an external 32。768 kHz oscillator。

So we can take a look at the manual to see how to access this register。

We see that it's in the core local interrupter。Memory and map peripheral。Addd an address。Of2，0，0， B。

F， F 8。嗯。Ands that it's a 64 bit register called M time。So when we read that register。

 we get the amount of time measured in these 32 kilohertz ticks since the system started。

So let's declare a pointer to that register。This time it's a Uent 64 type because the register is a 64 bit number。

Let's also declare a UX in 64 called Duntime。That is a current time。Plus。

 the number of milliseconds we want to count。Times this 32，7，68 milliseconds per second。

 divided by 1000 milliseconds per second。So 32768 hertz， that's clocks per second。

So that will give us the value the timer should be at when the time is elapsed。

Then we can do a loop and keep reading the current time。

 And as long as it's less than done time than we wait once we get up to done time。

 then time is finished。

![](img/326b09e4776df28ee874e1bc985b6c04_3.png)