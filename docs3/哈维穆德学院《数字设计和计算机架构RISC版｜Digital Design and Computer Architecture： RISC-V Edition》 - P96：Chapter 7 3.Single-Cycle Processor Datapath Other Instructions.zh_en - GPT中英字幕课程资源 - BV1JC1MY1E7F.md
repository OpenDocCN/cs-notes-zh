# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P96：Chapter 7 3.Single-Cycle Processor Datapath Other Instructions.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video， we'll implement the other instructions in the single cycle data path。



![](img/03f6dad01bc4832333481356232cdd2c_1.png)

So so far we handled the load word instruction next let's consider the storeward instruction。

So in our sample program at address 1004， there's a st or a word。The value of x6 into the address。

8 offset from x9。So this is an S type instruction。It's similar to load word， but the immediate。

Is in a different part， five bits are down here and the other seven bits are up here。And again。

 we have an up。Indicating that it's a storeward。We have a first source register x9 as the base address。

 and we have a second source register x6 containing the value we want to store。

So the machine language code is this。So now the hardware is mostly the same。

 the program counter is now at 1004。We will。Go to the instruction memory and read out the instruction from 1004。

 which is this store word。0，06，4， a4，2，3。We'll provide that to the register file and the sign Exer。

So the register file gets these bits indicating RS1 is register 9， and again we read out register 9。

Excuse me， which is 2004。We also。Read the value of register 6。

Which we had just written in the previous instruction。So register 6 contained the value 10。

We bring the。Instruction down as well to the sign extender。 And now we need to assign。

 extend the immediate found。In。These bits rather than all up at the top。

So we need to provide a control signal we'll call it immediate source to the signer extender to tell it where to look in the instruction to find the appropriate media。

So the same media has a value of  eight。And we extend that to be a positive6 32 B number of eight。

Now。Using the same hardware we already had， source A goes to the ALU。Source B also goes to the ALU。

 and again we tell the ALU to add， so we do 2004 plus 8 gives us 2000 C。

We provide that to the data memory。We provide the value 10 that we read from the register file。

As the right data input of the register of the data memory。

And we provide a new control signal we'll call memory when it's true。

 we're going to rate the value to the data memory。So on the next rising edge of the clock。

The data memory writes the value 10 into the address 200 C。There is data read out of the memory。

 but we're not using it， so we'll ignore that comes around to the register file。

 but we make red rightite be0， so we just throw away。The garbage since we're not。Trying to do a lot。

So in summary， the new hardware。Is the signine extender？

Being modified to take the immediate from a different place。A new control signal。

 IM M source to tell the signing extender where to look for the immediate。And the memor signal。

To tell us to write the memory。And the second value being read out of the register file。Alright。

 so that finishes storeward simultaneously we had the original hardware to add4 to the program counter。

 so PCX next is 1008 and on the next step we go on to address 1008 and do the next instruction of the program。

So the next instruction， oh， let's take a look at the immediate a little further。So so far。

 we have had two types of immediates to be concerned with for I type and S type。

 When IMM source is 0， we'll handle an I type and we'll get all 12 bits of the immediate from the upper。

Part of the instruction。 And then we'll assign extend that into the upper 20 bits。

For S type instructions， IM M source will be one and will'。

Take the bottom bits of the immediate from instruction bits，11 through 7。

The next seven bits from instruction bits， 31 through 25。And then we'll sign extend again。

To the upper 20 bits of the immediate。All right， let's go on and look at handling our type instructions。

So now the program counter is at 1008。And at that instruction there's an or x4 gets x5 or x6。

So this is an our type instruction。The app。Is this for all our type instructions？

And F3 and F Fc 7 and Fc 3 tell us what type of our type instruction。The sources are x5 and x6。

And the destination register is x 4。So all the art instructions are the same。

 except in the funct 3 and funct 7 fields。And although I'll tell the ALU to do something。

 so we need the same hardware for any R type instruction。

 except that the ALU control will be different。🤧Once again。We have our program counter。

 now it's at 1008。We put that into the instruction memory and we read out this instruction。0， zero。6。

2， E，2。3，3。That instruction is our or。We provide it to the register file and the extender。RRS1。5。

So we'll read out the contents of Register 5， RS2 is a6， and the destination register is4。

The sign extender， we don't care what it does。Because。We're not using the value。

Happens to extend some bits， so some junk comes out， but we're not going to pay attention to it。

We read register five， say we get out of six， register6， we get out the value 10。

Now we need to be able to choose the value from the register file to be source B instead of the value coming from the immediate extender。

So to choose between two possible things， we can use a multiplexer， so let's add this multiplexer。

To choose source Sp either from the immediate as we've done before or from the second part of the register file。

And let's add a control signal to drive that ALU。 we'll call it AU source。

 and this time we'll make it0 to。Read from。The register file。The ALU needs to do an or。

 so let's make the ALU control signal 01 to tell it to orR。And if we do。Six or10。6 was 0，1，1，0。

10 is 1，0，1，0， or those together 0 or 0， makes 0，1 or 1， makes 1，1 or 0 makes 1，0 or 1 makes 1。

 So this answer，1，1，0，1，1，1，0， decimal is 14 is our answer。

Now we need to write that answer to the register file。So on a load word。

 the register file got its value to write from read data。This time we want to rate the value from。

Hey， I your result。So again， we need to choose result。From one of those two places。

And to choose something， let's add a multiple here。We'll call this the result source multiplexer。

And we'll make it the control signal zero to choose the value here from AluU result instead of the value coming from the data memory。

So that result will come back。To the register file and will' assert。

Readdge right true to write the value 14。Into register。Once again， the。

Addtter here adds for the program counter， so now PC becomes 1000 C。

And we're ready for the next instruction。So finally， let's consider a branch on equal。To do this。

 we need to calculate the target address that we want to branch to。

So PC target is the current value of the program counter plus the immediate。

So let's look at this branch in a little more detail， where it address 1000 C。

 which contains a branch equal， let's say it's a BEQ x4 comma x4 comma label 7。

Where label 7 was back to the beginning of the program。So this is a B type instruction。

R S 1 and R S 2 are both4， so they're definitely going to be equal。

The op and F 3 indicated branch on equal。And the immediate contained where to branch too。

 And it has this funny encoding for branch。Avan。Bititz kind of scattered around through the immediate。

Here is our machine language。So the program counter。Is that。1，0，0， c。We read out the instruction FeE。

4，2，0，8， E，3。And that contained Rs 1 and Rs 2 being4。 So we put those bits into the register file。

 and we read out the contents of Reg4， which were both for。

Now we need to compare them and we can do that by subtracting。So if we choose。

 source A is definitely coming from first port of the register file。

 source B should also come from the register file， so we need to make ALU source0 so the amongst selects from the register file instead of from the sign extender。

ALU control of 110 indicates subtract。So we do 14-14 mix 0。

And we're actually going to ignore that result。But the AU also generates a flag called 0。

 that will be true， indicating that。对嗯。Sour A minus source B was0。

 in other words that the two registers were equal。So this means we're going to want to take the branch。

Now we've computed whether we want the branch， next thing is where to take the branch。So。In。Be。

Instruction。We have bits of it。Ind the branch destination。These were the immediate fields。

And we need to。From that， compute the immediate。And if we look at the convoluted organization of the pitister。

 this turns out it represents an immediate of FF， FF， FF， FF4。Which is negative 12。And that's more。

So， we have。Current program counter。And we need to add。The？Offet。

 add the immediate to the program counter。 so let's provide another adder here。That can take PC。

 which is 1000 C。And the extended immediate of negative 12 had those together and get 1000。

we'll bring that back。And now somehow we have to decide whether to get the next PC either from PC plus4。

 like we usually do， or from this PC target adder in the case of a branch。

Let's provide a PC source signal。That will be one when we want to take the branch。

So this branch should be taken， so we'll make PC source one。And this multiplexer will choose 1000。

P PC target。Instead of PC plus 4， which was 110。So， we take our branch。PC goes back to 1000。

 and the program will repeat。So this concludes our example of our singles datata path。

And now we're able to handle all the different instructions that we've talked about， load word。

 store word， branch on equal， and the various r type instructions。

So one more detail is to look at the immediates。Now we actually have three different types of immediates。

 so immediate source now needs to be two bits instead of one。And we kind of glossed over that。

 but IM M source now is a twobit field。So we'll say it was。0ero，0 for I type instructions。

 01 for S type instructions。And now for branch tip instructions lets define a new immediate format of 10。

And in the B type。They immediate had this encoding， instead。So the immediate extender block。

We'll have to。Put a one in the least significant bit and then swizzle the other bits around to get the appropriate image。



![](img/03f6dad01bc4832333481356232cdd2c_3.png)