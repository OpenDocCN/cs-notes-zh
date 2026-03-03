# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P111：Chapter 7 15.Pipelined Processor Control Hazards.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video， we'll continue looking at hazards in the pipeline processor this time focusing on control hazards。



![](img/4eb43fb97b3a82eb5d275c3257e92535_1.png)

So remember， a control hazard takes place when we don't yet know what instruction to fetch at the time we need to fetch it。

So this particularly shows up on an instruction like branch on equalal。The branch。

 we don't know whether to take it until the execute stage。

 because that's when we compare the numbers and see if the result is zero。

But there are instructions that are fetched after the branch。As issued。

And these two instructions must be flushed if the branch is taken。So let's see that in the pipeline。

 Suppose we had a branch on equal。 If S1 was equal to S2。

 we want to go to label 1 somewhere down here。Then we have two more instructions。 So in cycle 1。

We fetch the branch。And cycle 2， we fetch the subtract and cycle 3， we fetch the or。Then， in cycle 3。

We discovered that the branch should be taken。And we actually want to go down and fetch this ad。

Instead。But the subtract and or never should have happened， so we need to flush。The two instructions。

After the branch。This is throwing away work。 It is known as a branch mis predictiondiction penalty。

 and is the number of instructions that have to be flushed when a branch is taken。

So let's take a look at the logic to do flushing。So we need to flush when a branch is taken in the execute stage。

 we need tend to flush the instructions that were in the fetch and decocode stage。

And we're going to do it by adding flesh D and flesh E signals。

To as clear inputs to those pipeline stages。And we will。Fluush in the decocode stage。

 If I were taking a branch or taking a branch if the PC source signal was asserted in the execute stage that told the PC mus to take the value from the branch instead of PC plus 4。

Then we flush in the execute stage。If。PC's source E is true。

 that was happening if we were taking a branch or if there was a load word stall that we already realized we had to flush that execute stage on a load word stall。

So this introduces a little bit more hardware。We take a look at this PCE signal。

 saying a branch is occurring。And if it does， we need to assert flush in the execute stage。

 which we've already had。But we also need to add another flush for the decode register。就的。

So putting this all together， here is our complete processor with the data path， the control。

 and the hazard unit。The data path was essentially the same as the single cycle processor。

 except we've added some。Forwarding multiplexors for performance。The control。

Was the same as the single cycle processor， except we pipe going along the control signals to the appropriate stages where they're needed。

And the hazard unit。Is looking out for hazards。If they can be resolved by forwarding。

 then we enable the forward mues to do that。Otherwise， we might have to flesh。And。So， we could flush。

The stall or flesh。So we can stall the early stages， flush the execute stage。

 and if it's a branch misrediction， we also flush the two instructions after the branch。



![](img/4eb43fb97b3a82eb5d275c3257e92535_3.png)