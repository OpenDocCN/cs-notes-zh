# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P92：Chapter 6 22.Compressed Instructions.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/0c2bef7013ac689c3e725c129a8db53a_0.png)

Hello， in this video we'll talk about compressed instructions。

So so far we've looked at the 32 bit version of the riskk five architecture。

But Rik5 is trying to compete against microcontrollers。

 and many 16 bit microcontrollers pack their instructions in only 16 bits and therefore need about half as much code storage。

And since code storage is often the biggest part of the cost of a microcontroller。

 16 bit processors can have an advantage。So risk five and other instruction sets such as arm have defined 16 bit。

Compressed instruction versions， this is an optional feature in Ri 5。

 but most risk5 compilers will generate a mix of 32 and 16 bit instructions whenever possible to save code space。

The idea is to replace common integer and floating point instructions with 16 bit versions。

These compressed instructions have a m p mnemonic that starts with C。So for instance， instead of add。

 we have a compressed ad。Instead of load， there's a compressed load。Compressed out immediate。

So here's an example of a program that uses compressed 16 bit instructions。So。They have I equals 0。

 so there's a compressed load immediate。 let's keep I and S1 and we'll load in 0。Next， we need。

T2 is 200 for comparison， so we need to put 200 into T2。

But 200 is too big of an immediate to store in a compressed instruction。

 so we used a regular ad immediate T2 get0 plus 200 to handle the large immediate。Now。We want to。

See if we're done。We continue if I is less than 200。

 so we want to leave if I is greater than equal to 200。 We use a branch greater than equal to S1， T2。

 and done。And again。This takes too many bits to do the branch to packed into a compressed instruction。

 so this is an uncompressed。嗯。In our program， we wanted to fetch scoress I。And。嗯。At 10。Put it back。

So we could load。嗯。Relative to some T0。Put it into he1。Add the 10 and store it back。

Looks like we didn't initialize T0 should have been pointed to the beginning of the array。

Then we could add four。To S0。To go to the next part of the base address。

So this looks like this should have been Hesio。Bice address。So bump the pointer up to the next part。

And had one。To I and continue until we're done。So that was an example of a program where many of the instructions were compressed。

So to make thing instructions fit in only 16 bits instead of 32。

 some compressed instructions are restricted to only using a three bit register。

 identifier instead of 5 bits， and thus select one of the bit8 registers between X8 and X15。Also。

 the immediates are fairly irregular。 They're generally in the range of 6 to 11 Bs。

 depending on how much we can pack in， and the op code is only 2 Bs。So。

Here are a bunch of different flavors of compressed instructions， our type instructions。

Take one register that's both the source and the destination。

 second source they do the operations specified in Funt for。

I type instructions use one register as both the first source and the destination。

 and they have an immediate packed in these five bits plus these two more。



![](img/0c2bef7013ac689c3e725c129a8db53a_2.png)

Giving them7 B immediate。And a funt three to tell you which type of media instruction。

Same way for stores， branches， jumps， and so forth， jumps can take an immediate。That。

Is looks like 12 bits。11 bits long。

![](img/0c2bef7013ac689c3e725c129a8db53a_4.png)