# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P103：Chapter 7 7.Multicycle Processor Datapath for lw.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video， we'll take a look at the multicycle risk5 micro architectureect。



![](img/3a8cf224958db05e79cc091acea43c02_1.png)

So previously， we've examined a single cycle microarchitecture for a risk five that does an entire instruction in one cycle。

The data path has to be able to handle any instruction。

 and then the controller is combinational logic that looks at the up code and funked fields of the instruction and generates appropriate control signals。

The single cycle processor is nice and simple。And fairly straightforward to design。

Drropbacks are that the cycle time is limited by the longest instruction， which is load word。

And so some instructions might have a shorter critical path。

 but we still have to keep the same cycle time。We also have separate memories for the instruction and data。

 which is somewhat unrealistic。 Most microprocessors have a unified memory that can hold both instructions and data。

🤧。One more drawback of the single cycle processor is the hardware。

We needed three different adders or AluUs to do different operations all in one cycle。

So in the multie processor， we're going to address some of these issues by breaking the instructions into shorter steps。

That way， a simpler instruction could take fewer steps and thereby perhaps finish faster。

We can reuse existing hardware， so for instance， we could use an ALU on multiple different steps and that way not need extra adders。

And the cycle time will be faster because our steps are smaller。So we'd expect a higher clock speed。

 we might expect that simpler instructions could run faster than the complicated ones and less expensive hardware。

ADback is the sequencing overhead is going to be paid many times。

 we'll have to pay for that setup time and clocked。To Q delay on our registers on each cycle。

 not just。Once for the entire instruction。 so that will cut into performance。

We're going to go through the same design process as we did with the single cycle processor first we'll design a data path。

And then we'll design a controller。With a data path in this lecture。

 we're going to focus on the load word instruction， just like we did in the single cycle processor。

 and later we'll add other instructions。The controller is also going to be interesting because instead of having control signals that remain constant for the entire time the instructions executed。

 we'll be dividing into many steps and putting out different control signals on each step。

 So we'll need a finite state machine rather than a truth table to describe the controller。

So we'll begin like we did on the single cycle processor with our state elements。

But the difference is this time we're going to have a single unified memory。

That contains both instructions and data， rather than just a。Separate instruction and data memories。

 so this memory will have an address port of which element we want to read or write will' have the data that we read out。

We'll have a right data port。 And if the right na is true， then on the rising edge of the clock。

 we will write the data into the specified address。We also have a register file like before。

And we have the program camera， like before。So we're going to continue the same process of hook up these elements and adding ALUs and multiplexers like we did with a single cycle process。

So let's break the instruction down into six steps for loadward。

So the first step is the same no matter what instruction we're doing。We have a program counter。

And that's pointing to the current instruction。We connect it to the instruction memory。

And read out from that address， the current instruction。So。Then let's store it。Into a register。

 we'll call the instruction register， and that way we'll be able to remember the instruction。

 even as we go on to other steps。We only want to write this register on the first step when we're fetching the instruction。

 so we'll provide an enable signal called all IR writeite that will pulse on the first cycle to indicate that we do want to write to this register with a new instruction。

On the second step， we're going to read the source apps and immediate the register file in the S extent block。

Just like we did in the single cycle process。So we get the instruction out and we'll take it apart into some fields。

The Rs1 field， bits 19 through 15 of the instruction， will go to the register file。

And we'll read out the content so that registered， and let's store it in register。

 we'll call it the a register。We also have the immediate。

In some of the other bits of the instructions， so we'll pass that to the signine extender and we'll get out our immediate extend。

 and we'll need a control signal IMM source， just like in the single cycle processor to tell us what format the media was。

On the next step。For a load。We will do the calculate the memory address。So， we have the。

Source a coming out of the A register。 we have the immediate。Will put them into the A L U。

And set AU control signal to tell the AluU what to do in this case， we want to add。

We'll get our answer out， we'll call it ALU result。

 and again we'll store it in a register at the end of the step。 we'll call that register ALU out。

On the fourth step， we'll take this address and A you out and we'll use it to read the data from memory。

So we already had our unified memory here。And we already had the address coming from the program counter。

But now， instead， we want to be able to get the address from ALU out。 So just like before。

 we need to add a multiplexer to be able to choose our signal from one of several sources。

That multiplexor needs a control signal we'll call ADR source When ADR source is0。

 we'll take the memory address from the PC to fetch instruction When ADR source is1 we'll take the address from AU out to access data memory。

对。Data memory will read， we'll get a value out onread data。

 and we'll store it in register that willll call the data register。On the fifth step。

 we will write that result back to the register file。So we register file。Was hooked up。

To a result signal。And we're going to need to be able to choose that result now。

 not just from ALU out。But also in this case， from the data register。

So we'll add a multiplexer to make that choice to get an input result either from AU out or from data。

And in fact， soon we're going to need another source。

 so we'll leave an extra terminal and we'll need a2 bit control signal， result source1 through 0。

So on this step5。We'll take our result from data， bring it back to the register file。

And assert the red right control signal to write the value。On the data value into the register file。

And the address that we want to write to comes from the R D field。

 which is Bisy 11 through 7 of the instruction。Last thing we need to do is increment the PC。

To point to the next instruction。So here we had the program counter。But take that program counter。

And make it another possible source to the ALU。 So source A。

 instead of just coming from the register file， in this case will take it from the PC。Source B。

 instead of just coming from the immediate， will have the option of Done 4。

So we'll tell the AU to add and we'll calculate PC plus 4， put that value on ALU result。

We need to get it to the PC right away on this cycle。

 So let's add another input to the result mugs to choose A result。Bring that result around。And。

Write it。Back to the PC。And we'll have a enable signal PC right to tell us that we want to change the program counter on this cycle。

We also needed control signals， A use source A and ALU source B to select where source A and source B come from。

So this wraps up the load word instruction in these different steps。



![](img/3a8cf224958db05e79cc091acea43c02_3.png)