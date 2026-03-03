# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P72：Chapter 6 2.Instructions.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video， we'll look at instructions used in assembly language programming。



![](img/2b2b773fde0d1aebca8501947465bdc2_1.png)

So suppose we had a simple program like a equals B plus C。

 and we want to write that in assembly language in risk 5。

 we would write it as add A comma B comma C， or you might also read it。 Add A gets B plus C。

The ad is called the pneummonic that indicates which instruction to perform。

And the instruction takes through two sources in a destination。The destination is A。

 that's where the answer is put， and the two sources are B and C。Subtraction is similar。

 only the pnemonic changes。 So if we wanted to do a equals B minus C。

 we could write it with the instruction Subtract。 A gets B minus C。 Again。

 the mnemonic now is subtract， and the opera ends are the same。 Dination as A。

 and the two sources are B and C。A design principle one is that simplicity favors regularity。

So notice that the instruction format is consistent。

 Both add and subtract have the same number of opera， two sources in a destination。

And they only differ in mnemonic。 This makes it easier to encode the instructions and handle them in hardware。

Suppose we wanted to write a slightly more complicated program。A equals b plus c minus D。

 You could imagine an architecture that had a instruction that did all this in once。But in risk 5。

 instead。We break it into two steps。 We'll add T gets B plus C。

And then we'll subtract A gets T minus D， which will give us the B plus C minus D。

So we've introduced a temporary Reg T。And a sequence of two instructions to run the program。



![](img/2b2b773fde0d1aebca8501947465bdc2_3.png)

Sles us to another design principle of making the common case fast。 So risk 5 only includes simple。

 commonly used instructions。As a result， the hardware to decode the and execute these instructions can be made simple。

 fast and small。And we'll look at that in chapter 7。

So if you want to perform more complex instructions that are less common。

 we break them into a sequence of multiple simpler instructions。

So Rik 5 is a great example of a reduced instruction set computer with a small number of simple instructions。

 and it stands in contrast to other architectures like Intel's X 86 architecture。

That are complex instructions set computers with a vast number of different instructions。

 including things like a single instruction that copies an entire string from one memory location to another。

