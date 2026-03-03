# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P106：Chapter 7 10.Multicycle Processor Control for Other Instr.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video， we'll design the multie controller for the other instructions besides Loward。



![](img/469c55ef57145690cb71383ec05b14e9_1.png)

So just as a review， so far， we had a state machine。With。All these five states to do load。First。

 we fetch the instruction and add four to the program counter。Then we decode the instruction。

 read the registers and the。immediate。We calculate base address plus offset to get the memory address。

Then we read the memory， and then we write back the result to the register file。

So a store starts out in the same way the same first three steps， we fetch the instruction。

 decode it， and we also need to calculate the address。So， this arc。We will do for stores as well。

 So if the op is either three。Or this one for story word。

 We will either case add base address plus offset。But now， the fourth step is different for a storm。

In the fourth step， we want to write a value 2。やい？So here's the data path while doing that。

In the fourth step， the address was sitting here and a you out。 We need to make result source 0。

0 to choose that address。Bring it back around。And address source to be one to provide that address to the instruction and data memory。

 just like in the load word。But the difference is this time， instead of reading， we want to write。

The value we want to write is sitting on right data。F呗。Register file。

We provide that back to the data memory。And now， we need to assert。Mem right。

Did to make the right take place。So that's the fourth step of Stward， and it completes the storeward。

So at the end of either loadward or storeward。They have an arc back to the fetch stage。

 So once we finish the instruction， we go and refresh the next instruction and keep running。Allright。

 next up， let's take a look at our type instructions。So on the third step of an art type instruction。

 we need to do the ALU operation。Remember， the our type instructions are add subtract and or set last。

So， for any of these。The first source comes from register file port 1。

So A L U source A needs to be 1，0。The second source comes from register file port 2。

 So source B needs to be 0，0。We go to the A U， and we need to look at the instruction to know what to do。

 So A U up of 1，0。The funt fields to determine the operation， Which kind of value operation it is。

We get our answer out。And we store it。In ale you out at the end of the third step。Next。

 we need to write that answer back to the register file。 So after the execute step。

We go to the A U right back step。In the A U right back step， we have our value sitting in A U out。

 We want to choose it with the result mus。 So result source needs to be 0，0。We bring it back around。

To the register file。To the right data port。The destination register is coming from the instruction。

And we need to assert Ridge， right。To tell the register file， actually， to do the right。So。

 that completes the。At type instructions。Finally， let's take a look at branches。

So on a branch instruction， we need to calculate two things。 One is the branch target address。

 which is PC plus the offset。And the other is Rs minus R。

Sour 1 minus source 2 to see if the two sources are equal。

So notice that the AU wasn't being used in the decocode stage。

So we might as well take advantage of it being idle then to calculate the target address。

 which was to PC plus the immediate。Now， we're going to do that no matter what instruction we're doing。

 because when we're in the decocode stage， we haven't even decided what instruction it is。

 but none of the other instructions needed the ALU in the decode stage。

 so we might as well take advantage of having it。So， let's add some more。Control signals， to state 1。

So that while we're reading the registers， we're also calculating the target address。

So here we are in the decode state。The old value of the program counter sitting in this register。

The immediate is available here， but sign extend the immediate。Make A U source B 0，1。To choose。😔。

They immediate。Make as source A。0，1。To choose O PC。And tell the A U to add。 So A U up is 0，0。

 meaning add。And that will calculate。PC plus the offset and put the result。In A L U app。Next。

 we need a third state for branch on equalal。 So when the instruction is branch on equalal。

We'll go to a state where we compare the registers。 and if they're equal， we take the branch。

So to compare the registers now， in this third step， we have our two register values sitting。

At the output of this flapop。Will' select the first one by A U source being 1，0。

Source A source B needs to be 0，0。 Also to select， bring those to the AU need tell AU to subtract。

So AU up should be 01， which makes AU control 001， which makes a objectionion take place。

ALU computes the result that we don't actually care about。

 but it also produces a zero flag that we do care about。That0 flag goes back to the controller。

And we assert the branch signal。So you may remember from the controller if branch is true and0 is true。

 then PC right gets asserted。And we will write the program counter with our branch destination。

The branch destination we obtained because the PC+ offset was sitting in AluU out after the decode step。

So we make result source 0，0。Choose it。Bring that around。Now， that's ready。 Here is PC next。

For the program counter so that if we do write it， we write the branch target address into the program counter。

And that concludes our controller。For the multi processing。



![](img/469c55ef57145690cb71383ec05b14e9_3.png)