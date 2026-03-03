# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P98：Chapter 7 5.Single-Cycle Processor Extending.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video， we'll extend the single cycle processor to handle more instructions。



![](img/d2ce7cb5df212010788b210367c47975_1.png)

So so far， we've just handled a small set of instructions in the Ri five instruction set we've handled。

Load word， store word。Branch unequal。And five R type instructions add， subtract and or set list。

So are there are many other instructions。And in this section we'll support two new ones。

 add immediate and jump in link。But most importantly。

 I'd like to convince you that adding the new instructions is not all that difficult of a task。

 you just need to understand what the instructions do。

 think about what the data path and controller already can do， figure out the differences。

 and usually make small modifications accordingly。So let's start out with them adding immediate instruction。

So Add media is like add， but the second source is an immediate rather than coming from the registered file。

So it's similar to our type instructions that we already have。

 and I expect we could reuse most of the data path。

Difference is that second source is coming from the immediate。

So we need to change the ALU sourcems to choose the second source from the immediate。Instead of。

From the register file and we needed to make sure that IMM source is correctly set to pick the immediate。

So here's our truth table。For the main decoder and the rows in black are the ones we already built for what the processor should do。

And now let's add a new row。For a immediate， amedia has an op code of 19。

It's like add or other R type instructions， so Regrite is one。

 just like an ir regulargular R type instruction， we want to put our result back in the register file。

Memite is zero because we're not accessing memory。Result source is zero because we're taking our answer from the ALU result。

Branch is 0 because it's not a branch。 A U up is 1，0 because we need to look at the。嗯。

Function field to figure out what instruction it is。But the difference is in these two columns。

ALU source is1 instead of zero because we want to take our second source from the immediate rather than from the register file。

An IMM source is 00 because we need to treat that immediate as an i type instruction and sign extended accordingly。

So here's our full data path with that immediate。And'll start with the program counter following this blue line。

We read out the instruction。We send the instruction up to the control unit to generate our control signals。

The register file reads source 1。And we also send the immediate down to the sign extender。

That extends the eye type immediate。ALU source is one。So， we choose。

The second source source B from the sign extender。ALU op is 10。

 meaning we should look at the instruction。And the instruction is an ad， so。

We make ALU control 000 in that ALU decoder。And。We do the register file plus the immediate。

Result comes out here。Result source is。0。So we choose our result from the ALU。

Bring that result back around。To the right data port of the register file。Rgright。Is one。

So we write our answer back to the register file。I am M source。

Was 0 zero telling us to treat the immediate as an eye type。

TheMe rate is zero because we don't want to write register right to the memory and branch was zero because this is not a branch。

And that wraps up everything that's different about adding media。 It's a pretty simple change。

 All we needed to do。Was add a new row。To the main decoder。That was the same as the R type row。

 except。I M M source and A U source were different。

To choose the second source from the immediate rather than the register file。



![](img/d2ce7cb5df212010788b210367c47975_3.png)

that one was pretty easy。 Let's try the hardest 1 I can think of jump and link。

 That's maybe the most different than anything we have so far。But even so。

 it has still got some similarities。 It is similar to branch unequal。

 difference is that jump is always taken rather than being conditional。Because jump is always taken。

 we need to make sure PC sources one to take it。Another difference is that the format of the immediate is different。

 JL is a J type instruction， so we're going to need to enhance our sign extender to handle this fourth format of immediate。

And finally， Ju and Li needs to compute PC+4 and do the link part by storing that in the destination register to know where to come back from。

Now we already have hardware computing PC+4。So we need to add another input to the result multiplexer to choose that PC+4 as the answer direct to the register file。

So let's start by handling PC source。PC source， we wanted to make true to take the branch target address when it's a branch and the answer is zero。

For brand cheaper。For jump。嗯。If it's a jump， we also want to make PC source one。

 so let's add this orgate to make PC source true anytime we're doing a jump。Next。

 let's add a fourth option to the sign extender。So now when IMM source is 10。

 we want to handle the J type instruction。4 J type。

The jump destination was kind of swizzled around in the top 20 bits of the machine language instruction。

And so we need to put in the implicit zero because it's always even。

Put in the other bits of the instruction in the。Very place。 And make our immediate。Finally。

 we need to change the main decoder for jump in link。So when the op code is 111。

 this is a jump in link。And let's think about what it should do。

It needs to write the destination register RD with PC+4。So。We make redite one。Immediate source is 1。

1 for this new J type instruction we handled。A L use source。

It doesn't matter because the A is not doing anything。

Mem rate is 0 because we're not writing to memory。 Result source is 1。

0 because we're going to provide a new input to the result mugs to take the value from PC plus 4。

It's not a branch， so branch is zero。It's not an AU instructions。

 so it doesn't matter what ALU op is because we're not using the ALU and let's make this PC update or jump signal。

 This was also called jump。In the previous figure， let's make that one。

So now putting this all together。Our results source mugs。Now。Can take。PC plus 4。And。

We use that result source。Take it back around。And write that to the register file。

As our place to come back to after the jump。So that completes jump in link。

And just to summarize the three differences。Where that extender。

Has a new format with IMM sourceur B 11 for jump I。

PC source logic gets an extra or gate to tell us that we want to do the jump。And the。嗯。Result。

 multiplexer。Takes some new input from PC plus 4 that we're going to select to choose the return address to write to the register file。



![](img/d2ce7cb5df212010788b210367c47975_5.png)