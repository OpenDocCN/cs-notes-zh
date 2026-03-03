# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P93：Chapter 6 23.Floating-Point Instructions.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/a571d413271a81e27cf0ee8397be7b7e_0.png)

Hello， and this lecture we'll talk about risk five floating point instructions。

So Rik 5 has three optional extensions， FD and Q modes to handle single double and quad precision floating point numbers。

 32 bit， 64 bit and 128 bit。It in these extensions defines 32 floating point registers。

 their width is the highest precision necessary， so for instance， if quad precision is implemented。

 the registers are 128 bits wide and single precision numbers are stored in the bottom 32 bits of that 128 bit register。

There are 32 registers used for floating point numbers。There are some temporary registers。

Saaved registers， argument registers， more argument， more saved and more temporary。

 just like inregular risk。The floating point instructions have an S Q or D appended to indicate the precision。

 so for instance， F add。 S indicates a floating point addition of two single precision numbers。

The arithmetic operations include add， subtract， divide， square root， minimum and maximum。

 and a variety of multiplication with addition。 So multiply an addd， multiply and subtract。嗯。

Negative， multiply and add， negative multiply and subtract。嗯。

And we'll come back to those in a little bit， there's also floating point move instructions。

To move between two different precisions， so for instance。

 you could convert a double precision number to a single precision。So conversion there as well。

Comparison to compare the values of floating point numbers and various things to deal with classification and sign injection of the numbers。

So floatinglo point multiply addd is one of the most critical instructions for signal processing programs。

 These programs typically involve keeping a running sum of products。

 so they multiply two things together and add it to the running sum。

And you get instructions like Fmad。f。Of F1 equals F2 times F3 plus F4。

These instructions require four registers， so we'll need a new instruction format。

Here's an example of a floating point program again we're going to add 10 to the scores array for 200 elements in the array。

So this program starts out like we've seen before。We'll initialize S1。

Is the value of I will toize it to zero。T2。We'll set to 200， that'll be our comparison。

And T0 will be the value 1 that we want to add。But this 10 now needs to be a floating point number。

So we'll do a convert。From integer W type to single precision。

To convert the 10 and t0 into a floating point number 10。Now we have our for loop。

 We've already done the initialization。 We need to do the comparison。

 So if I is greater than or equal to 200， we are done。We go down here， otherwise we do the body。

And to do the body， we need to find the address to read from。

 so we'll take I and multiply it by4 by shifting left and then add it to the base address。

 and that will give us the address of scores of I。Then we'll do a floating point load word。

From that address into floating point temporary Reg 1。

Now we'll do a floating point add single precision。To add scores of。H。

To 10 and put the result back in FT1。And then we'll do a floating point store word。

To store floating point temporary Reg 1。Back into the memory address。

Then we'll increment I and jump back。The for them to repeat。So。These。

Voting point multiply addd instructions。Need a new type R4。

 the other instructions can use the regular RI andS types that we've ever seen before。

But for floatinging point multiply addd， we have our op Fed 3。We have source 1， source 2。

 and then we use some of the upper bits to hold source 3。

 and we have a destination and then a2 bit fun2 code to say what kind of multiply ad we're doing。



![](img/a571d413271a81e27cf0ee8397be7b7e_2.png)