# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P87：Chapter 6 17.Immediate Encodings.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video， we'll talk about the encodings of I in Risk 5 instructions。



![](img/6cde4ab8575b4fc769d6eb404c834cd0_1.png)

So。I recall that。Load word and store word use constants or intermediates that are immediately available in the structure。

For example， these are 12 bit2 complement numbers。Similarly， add I adds to 12 bit immediate。

There is no subtract eye because the immediate forat eye could simply be negative。

If we wanted to do a plus 4， we could add I S0 get it says 0 plus 4。

 If we want to do B equals a minus4， we can add I S1 it says 0 plus negative 12。So。

Immediates seem to have a really funny order when we looked at them in the instruction。

 But if we look at them in a different way， they make more sense。 Let's take a look at it。

 from the hardware point of view。So。嗯。Hey。I or S type instruction。Takes a 12 bit immediate。

And then sine extends that immediate into the upper bits。

A B type instruction takes an immediate with a0 and least significant bit。 I M M 11 through 1。

 and then sign extends the 12th bit into the upper positions。You type instruction。

Has zeros in the bottom 12 B and puts the immediate。In the upper 20 bits。

 a J type has a 0 in the beginning。Then， it has。11 Bs。And then。Yeah。Remainder of the immediate。

 and then assign extends into the upper bits。

![](img/6cde4ab8575b4fc769d6eb404c834cd0_3.png)

If we look at these， how they're encoded in the instruction。

We want to have as much commonality as we can between instructions。

And the hard parts of X decoding an instruction are finding the important things。

 the op code and the。H。Fun fields and the sources。 So the op code is always in bit 6 through 0。

For all of the types。For the other types。The register fields， R D。

 R S 1 and R S2 are always in the same place for every instruction。Similarly。

 Ft 3 is always in the same place。 So the only thing that varies is the immediate。

 and creating the immediate is one of the easiest things that hardware can do because it's just picking bits。

 We don't have to access a registered file or go out to a memory or use an AU。

 So it's pretty fast so we can afford to put the complexity there。Even so。

 we try to pack the immediate sin as systematically as we can。 So， for instance， bits4 through one。

For S And B， both appear here。S needs a bit 0。 B needs a bit 11。

 So that's why we pack the 11 here instead of。Shifting the branch over and putting 11 somewhere else。

 We get some consistency of the B4 through 1 by putting them here。The same way。

 we get some consistency。Of these bits。Where possible。

 And we get some consistency and the location of these bits when possible。

 So there are only a few bits that are scattered around in different places for different instructions。

