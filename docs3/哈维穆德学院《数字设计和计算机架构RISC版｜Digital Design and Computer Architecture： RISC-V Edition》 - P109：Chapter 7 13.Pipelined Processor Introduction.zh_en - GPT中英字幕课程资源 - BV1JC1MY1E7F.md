# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P109：Chapter 7 13.Pipelined Processor Introduction.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video， we will look at the Pipe Rik5 microprocessor。

So recall that we looked at a multi cyclee processor in the hopes of getting some speed up over the single cycle and were disappointed。

Now we'll look at pipelining and we're going to find that this is much more effective， and in fact。

 pipelining is such a benefit that virtually all commercial microprocessors these days are pipeline。



![](img/327b2b7bca45f2e7c340f0570786aa9e_1.png)

So to understand pipelining， think back to our example of pipelining laundry if you had a bunch of loads of laundry to do instead of washing one and then drying it and then folding it and then putting it away and then starting the next。

 you could overlap those steps so that one load is washing while the previous one was drying while the one before that。

 you could be folding while the one before that， you are putting away。And that way。

 he'd get four times the threeput。So pipelining microprocessor is an example of temporal parallelism where we're going to overlap steps to get a big speed up。

We're going to divide our single cycle processor into five stages， we'll call them fetch， decode。

 execute， memory， and write back。And we'll put a pipeline register in between each stage。

So if we think of a single cycle processoror。We have to do all those steps， fetch， decode， execute。

 memory， and write back。嗯。And it took about 200， if we just think about the longest parts of each。

 the fetch is mostly reading memory that's about 200 picoseconds。

 decoding is reading the register file that's about 100 ALU and execute is 120 another 200 for memory and a little bit more to set up writing the register file。

 so this comes out to a little under 700 picoseconds not counting to set up。

And clock to Q delay of the register。So。Here。And the single psychoprocesor it would take close to 700 pecoseds to do the first instruction。

 and then we could do the second one and about the same。For the pipeline processor。

 we're going to break it up into steps and we'll take the time for the longest steps。

 so the longest step is to access memory that takes 200 picoseconds。

But once we fetch the the first instruction， then we can start fetching the second instruction。

While we're decoding the first one。And the decoding involves reading the register file。

 I'm going to show that at the end of this 200 Pcosecond window because later on I'm going to want to write to a register file in the beginning part and let them both happen in the same cycle。

On step 3， we can fetch the third instruction while we're decoding the second instruction。

 executing the first。On step four， we could be fetching a fourth instruction。Decoding。A third。

 executing the second。Doing memory read。For the first instruction and so on。

So now we can overlap the instructions and our throughput is about one instruction every 200 picoconds instead of about one every 700 picoconds。

 so there's a big speed up。Ideally， we might get a 5 x speed up if we could truly break each instruction to five identical parts。

 That's hard to make things exactly balance in practice， but we're still seeing a big benefit。

So to understand how pipeline processors work， it's helpful to have a little cartoon showing what's happening in each step。

So imagine we were in this program， starting with a load word as two gets a value with an offset of 40 for S0。

Then we do an ad then a subtract and and a store in。In this cartoon。

 I'm going to have the five different parts of the pipeline divided by registers。

 So in the fetch stage， we have an instruction memory。 I am。

And the gray will indicate that that block' is being used。

 so we're using the instruction memory and we're fetching load work。And。Cycle two。

 so the horizontal axis is indicating time and the vertical axis is indicating which instruction we're doing。

So in the second cycle， the register file is used in the second half。To read out。40 NSs0。

And the instruction memory。Is used to read out the ad。Now in cycle three， looking down here。

The instruction memory is reading the subject。The registered file is reading S 9 and S 10。For the ad。

And the ALU is doing the addition to add 40 and S 0 for the load。In the fourth cycle。

 that's this column。In memory is fetching the hand。The register file is reading out T1 and S8。

The ALU is doing an addition for the ad instruction。The data memory is being used for the load。

In the。Fifth cycle。The instruction memory is fetching the store。第。Register file。

 the second half of the register file cycle is being used to read S11 and T5。

The ALU is doing a subtract。For the subtract instruction。

The data memory is not in use because an ad doesn't need data memory。

And the load word is writing to S2 in the first half of the cycle and so forth。

 So this kind of cartoon thats says。F out what the pipeline processor is doing on any given step。

All right， so let's think about how we build this pipeline processor。

 We'll start by taking our single cycle processor just like before。

 And I'm going to stretch it a little bit to make room to drop some registers in。

So this is exactly the data path we had before， except stretched out a little。

Now I'm going to divide it into five chunks by dropping four registers to separate the chunks。

And the first chunk is for fetch。That's where we're starting with the program counter。

 reading out from instruction memory， store that into the pipeline registered。

And simultaneously add 4 to the programme counter to get ready for the next instruction。

Then the first instruction would go on the Decode stage where we access the register file and do sign extension。

Then on the third cycle， that first instruction would be in the execute stage where we choose our sources and use the ALU。

In the fourth cycle， it would be in data memory， reading the writing memory， if need be。

 And in the fifth cycle， it would be in right back where we choose our result and then bring it back。

And write to the registered file。The registers files a funny thing here because it lives in both the decode and write back stages。

 because we're reading it in Decode and we're writing it right back。

You'll notice that all the signal names here have suffixes on FD。

EM or W to indicate which of these five pipeline stages we're in。

And it's important that signals from。Only interact in the same pipeline stage。Because otherwise。

 you'd be messing with。One part of one instruction and a different part of another instruction。

 which doesn't make any sense。 It's kind of like ghosttbusters don't cross the beams。All right。

 so if you look closely at this， you might find a problem。And that is。That when we get to right back。

 we're writing a result from the right back stage。Into an address that depends on the instruction。

In the deco stage。So we write to the wrong register。And to solve that。

 we're going to need to keep a copy of the destination register R D and run that through the pipeline alongside the rest of the data。

 So when we get to write back， we know not only what to write， but also where to write it。

Here's a diagram where we've made that change in blue。So bits 11 through 7。

 are the destination register。And instead of feeding it straight to the register file。

 we run it through the pipeline stages alongside the data。

So by the time we get to the right backstage and we have the answer result W that we want to write。

To the register file。We also have the proper register number。

R D for the right back stage that corresponds to that instruction。

Let's assume that we're writing the registered file on the falling edge of the clock and reading it on the rising edge of the clock。

 that way we can do a read and a write both in the same cycle。

 the read in the first half and the right in the second half。Now。

 let's add control to this pipeline processor。And we'll take exactly the same control unit as the single cycle processor。

So this is exactly the same hardware we already developed for the single cycle processor。It puts out。

TheVarious control signals。That we knew of from the single cycle processor。

 And those are all in the decode state right now， because the control unit。

Is based on the instruction of the decocode stick。We need the immediate source。Right away。

And then the decode stage to do the sign extender。 but the other signals aren't needed until later。

 so。We bring them into a pipeline register。And we get the same signal out。 Now。

 we've changed the suffix to E。So Ridgewrightite D and Ridgerightite。

 E and Ridgerite M and Ririte W are all reflecting the register right。

 but they're with respect to the instruction that's currently in that stage。So in the execute stage。

 we need to know A U source。And we need to know A L U control。So， that the。

AL you can do the proper thing for that instruction。Also， if it's a branch or a jump。

That gets resolved in the execute stage based on the0 flag。Coming out of the executed stage。

And that goes back。To the program counter and could cause us to take a jump。

And you'll notice that is an interaction between pipeline stages。Where they。

Result in the execute stage of one instruction as changing the program counter down tostream。

 and we'll have to be careful about that。The memory signal continues on into the memory stage。

Where its the right enable to the data memory。And result source and redright signals go on to the right backtage。

And are used to write a result。So you see the control signals are traveling along through the pipeline with the data。

 and they drop off where they're used。

![](img/327b2b7bca45f2e7c340f0570786aa9e_3.png)