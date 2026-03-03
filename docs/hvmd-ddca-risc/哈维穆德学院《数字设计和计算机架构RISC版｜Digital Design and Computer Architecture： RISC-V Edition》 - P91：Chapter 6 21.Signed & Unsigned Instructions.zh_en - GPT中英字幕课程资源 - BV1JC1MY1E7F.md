# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P91：Chapter 6 21.Signed & Unsigned Instructions.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video we'll talk about signed and unsigned instructions。



![](img/1bcfe13599c6c0c2c5695a0e6cc00145_1.png)

So Rik5 has a variety of instructions for dealing with both signed and unsigned flavors of certain operations and also for detecting overflow。

So as we talked about with multiplication， when you multiply two numbers， 232 bit numbers。

 you get a 64 bit result。And we looked at the Mole age command， which does signed multiplication。

There's also unsigned flavors， Mole H。That treats the numbers as unsigned。

Or Moh S that treats the first opera brand is signed and the second as unsigned。

So when you're doing multiplication， the bottom 32 bits of the result are identical。

 whether the numbers are treated as signed or unsigned。

 and so we can just use mule to get the bottom 32 bits。

But the upper 32 bits depend on how we interpret the signs。 So imagine S0 had this value 8000。

 and S2 had the value C000。If we do treat these as signed。S1。

Is2 to the negative 31 S2 is sorry S1 is negative 2 to the 31， S 2 is negative 2 to 30。

 So the product should be 2 to the 61。Which has a two here and then all zeros。On the other hand。

 if we treated them these numbers as。Unsigned。Then S1 is 2 to 31。S 2 is three times2 to the 30th。

 and their product should be three times 2 to the 61st。Which is。S，0，0，0，0。Finally。

 if we treat the first number as signed and the second is unsigned。The S1 was negative。Of2 to the 31。

S 2 was three times 2 to the 30th， and their product should be negative 3 times 2 to the 61。

 which has a 0，0，0。 So you see the answer is different between these multiplications。

 depending on how you interpret the numbers as signed or unsigned。

 and you need to use the appropriate instruction。Division and remainder also normally are for signed numbers。

 but come with unsigned flavors。Branches。Typically interpret numbers as。Signed tos complement。

 but also come in an unsigned flavor。So for example， let's say S1 was 8000 and S2 was 4000。

If we do a branch less than S1 and S2， that interprets the numbers as signed， S1 is negative2 to 31。

 S2 is2 to the 30th。S1 is less than S2， and the branch is taken。On the other hand。

 if we did a branch less than unsigned， S1 is interpreted as positive2 to the 30th first。

S 2 is 2 to the 30th。 And so S1 is not less than S2， and the branch is not taken。Similarly。

 set less end comes in signed and unsigned flavors。And。One of the subtle points is that。

The immediate。Instructions always c in the immediate。

 even when we're doing a set less than immediate unsigned。So that's a little bit weird。

 let's say we had the same S1 and S2。If we do a set lesson。S1 and S2 S1 is negative to to the 31st。

 S2 is 2 to 30。If so S1 is less than S2， and our result gets 1。If we did a set less than unsigned。

 then we treat S1 as a big positive number， and it's not less than， so answer0。

Set less than immediate， let's say we do T2 compared S1 to negative 1。S1 is。嗯。

And treated as unsigned。 This is the sorry signed。 this is the signed version of set less than。

 so S1 is minus2。To the 31st。The immediate。Of negative  one gets signine extended， sets' all F's。And。

So。S1。Is less than S2， and so we set the answer to be true。On the other hand。

 set less an immediate unsigned with the same arguments。

S1 is 2 to the 31st now treated as an unssideign number。嗯。As negative one。

Is a sign extended to be all F's？But then interpreting that as an unsigned number。

 all F's is2 to the 31st minus1。So a very big positive number。And now。

31st is less than 2 to the 32nd minus1， so again， set less than immediate produces a1。

But we thought we were writing negative one here and we were actually writing a very positive number for a at less than immediate unsight。

Loads and will sign extend values。So when we do a load half or a load byte to load8 or 16 bits into a 32 bit register。

 the upper bits of the register are sign extended from the 16th or  eighth bit of the value we read。

There are unsigned flavors that zero extend， so if we load a half word unsigned or load byte unsigned。

 they put the half word or by into the bottom part of the register and put all zeros into the upper part。



![](img/1bcfe13599c6c0c2c5695a0e6cc00145_3.png)

Risk5 doesn't provide unsigned additional instructions。Because it works the same as regular edition。

 and it doesn't to provide overflow detection because overflow can be computed with existing instructions。

So if we want to detect unsigned overflow。Let's say we add two numbers。And we get a result。嗯。If。D暗。

Answer。Since these are unsigned numbers， the results should be bigger than either number。

If the answer is less than the first number， then we had overflow take place and our answer is wrong。

So that's how to detect unsigned overflow。To detect signed overflow。Now， we can add two numbers。

And then we can set less than T3 of T2 comma 0。 So that will set T3 to be true if T2 is negative。

We can also。Compare set less than to see if T0 is less than T1。And so。啲人。

T4 will be set if the result is less than T1。And now the answer was wrong， we had overflow。If T2。

What negative？And the result is bigger than T1。Where if T 2 is positive。

 and the result was less than negative， less than T 1。So， if。T 3。T4 are equal。

Then our result was correct if they differ than overflow occurred so we can do a branch on not equal to see if T3 was different than T4。

 and if so， detect that there was an overflow。