# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P110：Chapter 7 14.Pipelined Processor Data Hazards.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video we'll look at handling hazards in the pipeline processor。



![](img/d41b8171db993804b14e68b304693769_1.png)

So a pipeline hazard depends， happens when an instruction depends on the results from a previous instruction that hasn't yet completed。

So there are two types of hazards， one is a data hazard。

Where we need to use a register value in one instruction that hasn't yet been written back to the register file by a previous instruction。

Another kind of hazard is called a control hazard。And that's when you haven't decided yet what instruction to do next。

 So， for example， if there's a branch。🤧嗯。Let's take a look at an example of the data hazard。

 Suppose we do an ad。S 4 plus S 5 goes into S 8。And then the next four instructions all use S8 as a source。

So they add。We fetch it in step1， we read S4 and S5 and step 2。Perform the addition step 3。

 we don't use the data memory in step 4， and in the first half of step 5。

 we write essay back into the register file。Now the subtract comes along。

 fetch it in step 2 and step 3。The subtract tries to read the value of S A from the register file。

But it's the old essay， not the result of the ad， which doesn't get written into this until step 5。

In step four， we try to read the value of essay for the or。And again。

 this is the wrong value because we haven't yet written essay in step 5。Finally。

 for the and on step 5。We。Readta8。And remember that we wrote essay in the first half of the cycle。

 We're reading it in the second half。 So now we do get the proper essay。 So the and works。

 but the subtraction or。Producuce the wrong answer because they got the wrong value of S8。

 and this is a good example of the data hazard。So to handle it data hazards。

 there are a couple of possibilities。One of them。It is during compile time。

 we could add no opera instructions that just do nothing between an instruction and the time it's needed。

So when we have an instruction right to a register and then read to it。

 there's two cycles between the time。We write in the time we can read so we could put two no ops in between。

If we go back to this code after the ad， we could put a no up and no up。

And now the subtract won't try to get S until cycle 5 and would be okay。

This is a fairly unfortunate way to solve the hazard though。

 because it makes the program slower and also it blos the program by putting those no ops into the code。

Another possibility is that we could rearrange the code at compile time。So， for example。

 let's say we had this bit of code， and then we have some code doing completely unrelated thing。

 Maybe we could bring that unrelated code forward。And do it while we're waiting for the essay to be ready。

And that way。We don't have to。waste time， waiting for essay。

A drawback of this is in a different architecture， there might be a different latency between time you issue your instruction of the time the results are ready。

 so a compiler may not know what processor。Micro architectureiture is running on。

 and it might not be able to optimally rearrange the code。Another possibility is the forward。对。

In the hardware。At rent。So coming back to this picture。

The answer of S4 plus S5 is actually known here in cycle 3。At the time， the subtract needs to get it。

 So if there were a way that instead of waiting for essay to go back through the register file。

 we could forward it in hardware during cycle 3。Then。Subtract could have a value it needs。

That works in this case。 It's not always possible， so one more option is to stall。At rentan。

And in a stall， the hardware detects that there's a hazard that information is not yet available。

 and it has part of the pipeline stop until the information becomes available。

So let's look at these options of forwarding in stocks。First here， this was the No op example。

Here is forwarding。So， S 8。Is computed。In step 3， we have S 4 plus S 5。 The subtract needs it。

Nes to do the subtraction in step 4。 So we read the wrong value of essay here， but we could forward。

The correct value down to this object。And step before。In step 5， the or needs the value。So。

 we could forward it。Ss it again。And finally。The and。

Ss8 is written into the register file in the first half of step 5， read on the second half of step 5。

 So there is no need to forward to the end。So to do forwarding。

You need to check if the source register in the execute stage matches the destination of a register and instruction in the memory right back stage。

 And if so， we forward the result。So here in the execute stage。The source register is S8。

The ad is in the memory stage and its destination was S8， so we need to forward。Same way in step 5。

 we have a source register in the execute stage S8。And a destination。In the right backstage of S8。

 so again， we need to forward。So here's some hardware we could add to handle the forwarding。

 the black is the processor we had before， let's add a hazard unit down here。

To deal with a variety of hazards and we'll start with forwarding。So to forward。

We need to take the value。That is。And either the。Memory or right backstage。From。

Previous instruction or two previous instructions。And bring that around and choose it here。

 have source A or source B instead of the value that we read from the register file。

So here we want to forward S to source A。The S8 that was in the memory stage。

So we could take this value of essay in the memory stage。Bring it up here。

And choose it as the value for sourceure。So this forwarding requires some multiplex or controls。

 we'll call them forward AE and forward BE to tell us if we want to forward result into the execute stage。

And they depend on knowing。The source registers。In the execute stage。And the destination register。

In the memory stage。We also need to know Reg Wright。

To know if that destination register is actually being used。

Because if we weren't going to write the register， then there's no need to forward。

So now we're ready to work out the logic equations for forwarding。Case one。

Is that a source register in the execute stage matches a destination register in the memory stage。

So if。Let's handle for source register Rs1 first if source register1 in the execute stage matches the destination register to an instruction to memory stage。

And the instruction of the memory stage is going to write the register。Then we need to forward。

Were forward for source A。From the memory stage。Otherwise。

 if there's an instruction in the right backstage。Whose destination matches the source we want to execute。

And the instruction that's in the right backstage is going to write。

 then we can forward from the right backstage， otherwise。

 we don't need to forward at all and we'll just take the value from the register file。

The forward B equations are identical except。Replace source one with source two。

There's one other subtlety here。If we were writing to register  zero。

 remember register zero is hardwired to zero， so any rights to register zero should be discarded。

So we need to check。If the destination register was not zero or the source register was not zero because we wouldn't want to accidentally forward some junk。

Instead of getting the zero。All right， that handled。Forwarding， but you can't always forwarding。

For example， imagine there's a load。Into S 7， and then three subsequent instructions。

 all of which use S 7。So the load， we fetch cycle 1， we read S5 and 40 in cycle 2。

 in cycle 3 we add S5 plus 40 to get an address in cycle 4 we read from that address。

 and now we have the value that we want to put into S7。However。The。

And what that value at the beginning of cycle four？

But we don't have it until the end of cycle for it， so we're unable to forward。

This is a case since we can't forward， we're going to need to stall。On the other hand。

 the or could forward the value from the right backstage。And the subtract can S。

7 is written to the register in the first half of five。

 We can read it out in the second half of five， so there's no need to forward as7 of the subjecttract。

So let's look how to stall。A case like this。To do a stall the end instruction that needed S 7。

It's not yet available。So let's hold the and instruction up in the decode stage， not let it advance。

 That's called a stall。Then the subsequent instruction is the or。It has to be stalled in the。

Ftch stage。Because it can't move into the decocode stage because the end was already installed in the decocode stage。

So if we stall the end for a cycle now。We can forward S7。From the load to the end。We're good。

So to figure out the logic for the stall。We need to see if either source register in the decode stage。

Is the same as the destination register in the executive stage。

And that instruction in the execute stage is a load word。Because load words have。

Require this stall since the load isn't available until the end of the memory stage。

So check for lowbri install。We see if source register one or two in the deco stage matches the destination register in the execute stage。

And。啊，嗯。Execute stage instruction is a load word。For load word results source is true。So。

We can look at that to tell that it was a load word。Now， if it is。

Load word that needs to stall will stall the fetch and decode stages and will flush the execute stage to just cause the execute stage to do nothing at all。

Based on that way stock。So here's some hardware to do that。So we' look at source registers。In。

Decode stage。And at the destination， register in the execute stage。

And at this result source to tell that it's a load word。If the register is match。

 and it's a load word。Then we will stall the fetch Decode stage。Flesh the execute stage。The stall。

Is done by turning off the enable。25。So we'll make these PhOps enable and turn off their enable when we want to stop。

The flesh will handle by providing synchronous reset， we'll call that clear。

And when you want to flush， we'll assert that clear signal。

And that will put zeros into the registers and cause that instruction to do nothing because we turn off all the right enabled。

So all this is a little bit dizzy and you've got to be careful getting the hardware right for flushes installs。

 but it certainly can be done。

![](img/d41b8171db993804b14e68b304693769_3.png)