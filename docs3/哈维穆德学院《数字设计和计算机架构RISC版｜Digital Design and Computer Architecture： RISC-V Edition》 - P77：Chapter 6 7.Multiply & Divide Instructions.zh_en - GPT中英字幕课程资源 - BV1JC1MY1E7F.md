# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P77：Chapter 6 7.Multiply & Divide Instructions.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video， we'll look at risk 5 instructions for multiplication and division。



![](img/041171a880d100b2e4843264947f6b57_1.png)

So remember that multiplying 232 bit numbers produces a 64 bit result。And as to handle this。

 riskk five has two instructions， Mole and Mo H。Mole S0 gets S1 times S2。

 puts the lower 32 bit result。Into S0， mole H puts the upper 32 bits into the destination。So。

Suppose we wanted to get a full 64 bit multiplication。

Where we want S4 and S3 to collectively hold S1 times S2。

We could do a mole H S4 gets the upper part of S1 times S2。

 and then mole S3 gets the lower 32 Bs of S1 times S2。So for an example， suppose S1。

Was the hexom decimal number 40，00，0000， which is2 to the 30th。And S2 was the number。Hex 80，0，0，0。

000， which as a twos complement number is2 to the minus 31st。Then their product。Should be2 to the-61。

Which in hexodadecimal is。E 0，0，0，0，0，0，0。And then all zeros in the lower part。

 so S4 would get that E and S3 would get all zeros。A division。When you divide2 32 bit numbers。

 you get a 32 bit quotient and you also get a 32 bit remainder。So again。

 risk five has two instructions。Give S3， S1， S2 computes S3 equals S1 divided by S2。And remainder。

Compututes S4 is the remainder or the modulo of S1 mod S2。

 it's what's the remainder when dividing S1 by S2。So suppose S1 was x Sal 11， which is decimal 17。

And S2 was3。Then S1 divided by S2 should be 5。An S1 modo or remainder。As 2。

17 divided by 3 is 5 remainder 2。 So the remainder is 2。

Division also works for negative numbers and you need to be a little careful about defining what the quotient and the remainder are when dividing negative numbers。



![](img/041171a880d100b2e4843264947f6b57_3.png)