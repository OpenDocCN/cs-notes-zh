# 【从零开始学习 ARM 汇编语言II Udemy】 p24 p23 06.1. Overview of General Purpose Timers -BV1RJU6YwEM8_p24-

Hello welcome back so in this lesson we shall give an overview of general purpose timers。

Before we move on actually let's talk about the difference between timer and counter。

 they are often used interchangeably， but if you want to know what the differences are or what they truly mean technically。

 so their differences lie in the differences in their clock source。

 so if the clock source is internal like the RC circuit or the PLL or the Xtor。

 this is known as a timer， but if there's an external clock source we call this a clock。

And an external clock source could just be feed clock from somewhere else into the CPU。Right。

 so these so this is the only difference if you had a word timer versus is counter should knowa。

 the timer is from internal clock source， the counter external clock source is being fed to the CPU okay let's move on。

So timers are often used。Or you can think of it as counters right， so when one says timer。

 you can think of it as a counter as well， just forget about the clock source but if you want to be technical about it。

 then if you say counter， the clock source has to be from an external device somewhere。

So when I say timer， I'm using timer encounters here interchangeably I don't care about the clock source。

 right， so timers are often used for creating delays。

 counting event and measuring the time between events we can count the number of times。

 a sensor crosses it threshold by using timers or the number of times a button is pressed。

 the number of times in fact any event， whether a hardware triggered or software triggered occurs。

 we can also measure the time between events。And we use time is to do this。

And time has come in different forms， and one way of classifying timers is the one shot timer versus the periodic timer。

Also we've got the down counter and the up counter for the one shot timer， the timer stops counting。

 once the timeout reaches， so as soon as the timeout reaches。

 the timer finishes its job and stops counting。But for the periodic timer， when the timeout reaches。

 it resets its stove。But for the periodic timer when the timeout reaches。

 it resets itself and starts counting again。And also the down counter timer is a timer that counts from a set value to0 and the up counter timer count from0 to a set value。

 so these are different ways of classifying timers we can classify them as either one shot or periodic or down counter or up counter often。

Often we hear the timer size quoted in bit size， such as 16 bit， 32 bits， etc。

 let's see how to convert this bit size into seconds。So as you may know。

 the way to get the largest value of a bit size number is just to do to raise the par number。

 for instance， the largest value of 16 bit is 65，536。

We just do two reach the power 16 and then we get this， so 16 bit equal2 reach the power 16，65536。

 and again assuming our system is running us 16 megaHz and our time clock is 16 megaHz2。

Now let's see how to get the timer size of this 16 bit timer in seconds。

All we have to do is multiply this 16 bit size， which is 65。

536 by how long it takes for a single cycle to execute right if our system is running us 160 megaHtz。

 this means，In a single second， we are able to execute 16 million cycles。Right。

 so if 60 million cycles are executed in a single second， then。

How long does it take to execute a single cycle？And we find that out by doing one over 16 meHz or one over 16 million。

 and this gives us 62。5 nanoseconds， in other words， 62。5 times 10 reached to the power 9 or 6。

25 times 10 reached to power 8， you get nanoseconds simply by moving the dot over here and adding a1 and subtracting1 here to get9。

 so it becomes 62。5 62。5 times 10 minus9 so if our system is running at 6 meHtz。

 then each processor cycle execute in 62。5 times 10 minus9 or 62。5 nanoseconds。Right。

 so all we have to do is multiply how long it takes to execute each cycle by the bit size value here。

 so we do 65536， multiply by 62。5 nanoseconds and we get 4。096 times 10 minus3 and this means 4。

096 milliseconds， so this means that when our timer or if our timer is 16 bits。

 we cannot get a delay， we cannot create a counter greater than this value we cannot create a delay。

Larger than 4。096 milliseconds， so if you want a five second delay， you cannot create with this。

You may have to call the function a number of times。

 but you can simply call the timer once and expect it to be able to give you a five second delay because of its size。

Right， so the maximum delay is 16 bit time I can create is 4。096 milliseconds。

 that's what this means Now let's see a 32 bit timer， so 32 bit the largest 32 bit value is above 4。

2 billion over here like this。Right， and again， our system is running out 16 megaHz。

 therefore 16 million cycles are executed in one second and if this's the case， then。It takes 62。

5 nanoseconds to execute a single cycle， so we take this 62。

5 nanoseconds and multiply it by the 52 bit size and we get 268。435 seconds。

So meaning if our timer is not 16 bit by 32 bit， we can create a delay as large as 268。4 seconds。

You see the difference， 16 bits cannot even create a5 millisecond delay， but 32 bits can give us 268。

4 seconds of delay， right， huge enormous difference okay。Now， let's see。

 what if we use our 16 bit timer and add a prescalear to it because some general purpose time is。

Allow us to add prescaleers right， and often the prescaleers come in different sizes。

 a very common size is the8 bit prescalealar， so let's see how that turns out。

Our timer size is 16 bit and the prescale is 8 bit so we add this and we end up with 24 bit。

 so we simply do two to the power 24 and this gives us a bar 16。7 million。

And we multiply this value here by how long it takes to execute a single cycle and this gives us。16。

7 multiply bys6。025 times 10 minus8， basically the 160777216 multipplly by 62。

5 nanoseconds and that gives us 1。048 seconds so if our timer becomes 24 bit。

With the addition of the preskier， we are able to create delays up to one second。

RightSo this is what it means when you hear of a 16 bit timer， 64 bit timer， a 32 bit timer， etc。

 there are 64 bit timers too， and you can use the same method to calculate how wide the 64 bit timer is。

