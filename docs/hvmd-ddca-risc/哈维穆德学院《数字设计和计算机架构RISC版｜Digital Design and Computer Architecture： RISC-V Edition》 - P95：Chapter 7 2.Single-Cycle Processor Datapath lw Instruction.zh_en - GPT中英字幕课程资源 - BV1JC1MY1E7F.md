# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P95：Chapter 7 2.Single-Cycle Processor Datapath lw Instruction.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video， we'll talk about the single cycle risk5 processor and in particular。

 implement the data path for the load word instruction。



![](img/5d91ea98598784874c7821ce9ee7249a_1.png)

So we're going to break our processor into a data path。That operates mostly on 32 bit words machine。

AWord size for our computer， and then a controller。That receives the instruction。 And based on that。

 sends back control signals to tell data pathway to。So let's begin by designing the data path。

And as we're doing it， we're going to build up the capability to handle various instructions。

 so imagine the following program。嗯。That we'll use as an example to visualize what's taking place in the data path。

It programgram， let say starts at address 1000 in memory。And it begins with a load word。

So load x6 from some offset relative to x9。This is an eye type construction for load word。

So this is the op for the load word。It's source。Is R9？The immediate is negative four。

The destination register is our 6。And。F3， together with the op， determined that it was a load word。

And the machine language value for this load word。Was FFC4， A303。Next。

 we'll look at a storeward instruction。That's an S type instruction。And then an or instruction。

 which is an our type instruction。And then a branch on equal， a be type instruction。

Once we can run all of these， we're able to do all the interesting things in a basic program。

So we're going to begin again with this load word instruction， load word x6。

From negative four parentheses x9， where x6 was the destination register。

Negative  four was the immediate。X 9。Is the source register。And they op and front together。

Make load word。So。Let's begin with the architectural state， remember we had the program counter。

 the instruction memory， the register file， and the data memory。

And let's start by connecting the program counter to the address input of the instruction memory。

So the program counter was at 1000。Here。And we'll hook that to the address of the instruction memory。

 and we read out from the instruction memory the current。

The machine language for the current instruction。Which was FFC4A303， the load。

And that's this value here。On the instruction bus。Next， based on that instruction。

 we need to read the source registers for load word， there's just one source register x9。

So we take that instruction field。And we'll look。At the RS1 field。

 it is 19 through 15 of the instruction。Which happened to have a value 9 because the source register is x9。

We'll go into the register file， read out the value of x9。Which suppose happens to be 2004。Now。

 the load word also needs an immediate offset。So we take some more bits of the instruction。Bits。

31 through 20。Contain the immediate for lo word。And those are a bunch of ones and then zero zero。

Which in at asmal as FFC。Recall that we need to extend that immediate to be 32 bits long。

So we'll add a new block of hardware called a sign extender。

That will take in a smaller number of bits and put out a 32 bit word。

 Let's call that extended value IMM EXT。And so extending FFCc to 32 bits is Fffff F F FF。See。

Bunch of leading wins， and then two zeros。So now we have the two sources for load 2004。

And negative four。The next step for load is to add the base address to the offset。So。

Since we're going to be able to need to do a bunch of different kinds of arithmetic。

 let's put on a general arithmetic logic unit instead of just a single purpose adder。

The A L U will take the two sources。Source a from the register file。And source be with the immediate。

And it should add them。So let's provide an AluU control wire。To say what the AU should do。

 if we I think back to chapter 5 where we define the ALU， the code 010 meant at。So。

Then the ALU will put out a result。That's the sum of 2004 and negative4 is too fast。

That's the address that we want to load from。Next， we need to read data from that address so that's hook up AL result to the data memory。

We're putting in 2000 as the address to data memory， data memory looks in there。

 and it comes back with whatever value is at that address。 Let's suppose the value happen to be 10。

So now we'll put 10 on the reddit bus。And finally， we need to write that value back to the register file。

So it's add a wire bringing。The data out of the data memory and back to the right data terminal for the registered file。

The address we want to write to is register 6， which was in bits 11 through 7 of the instruction。

 so let's hook up bits 11 through 7 of the instruction to the register file and let's add a control signal called RegWite。

And we'll assert Ridge rate so the value。Tian。Will be written to register 6。

At the end of this clock cycle。And that completes。Need to do。Almost complete。

s what we need to do for loadway。 There's one more thing。Program counter is still at 1000。

So we need to add four to the program counter so that we're pointing to the next instruction。So。

 let's。Provide an。That will take the current value of the program counter。Four， add them together。

 we'll call that PC plus4。And we'll bring it around as PC next。

 the next value for the program counter。So 1000 plus 4 mix 1004。

And on the next rising edge of the clock， we'll load 1004 into the program counter。

 so we'll be ready to do the next instruction。

![](img/5d91ea98598784874c7821ce9ee7249a_3.png)

And that wraps up， handling Loward。