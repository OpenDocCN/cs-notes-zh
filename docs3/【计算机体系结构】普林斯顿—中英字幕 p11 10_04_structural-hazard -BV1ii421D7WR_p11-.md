# 【计算机体系结构】普林斯顿—中英字幕 p11 10_04_structural-hazard -BV1ii421D7WR_p11-

![](img/914b843e4aae7d66842af9518f6a0f8c_0.png)

Okay， so we've talked about structural hazard， we've talked about pipelining basics。

 And now we're going to go into the three main types of hazards。

Stuctural hazard data hazards and control hazards。 Let's start off by talking about structural hazards。

Okay， so let's。Overview structural hazards here。 So structural hazards， as I said before。

 occurs when two instructions need to use the same hardware resource at the same time。

And there's a couple of approaches on how to resolve this problem。I mean。

 we can't just throw up our hands and just stop the pipeline or maybe maybe actually。

 that kind of is one of the solutions。 But you need to somehow think really hard about how to deal with a structural hazard。

One thing you can do is you can explicitly avoid。Having different instructions that would be in the pipeline at the same time。

 Use one structure at the same time。And you could do this by the programmer or maybe the compiler could do this。

Next way to go about doing this is you actually have the hardware。

 Take care of basically all of the problems。 And there's some complexities in actually building this。

 But you want to stall the processor or stall a portion of the processor or stall the dependent instructions。

Or me， you install， let's say， the earlier one when you go for the contended resource。

 So a good example of this is if you have one resource， two things are trying to use it。

 You have a priority encoder in there the priority encoder says the earlier instruction gets to use that because if you sort of invert the priority order。

 you might end up with dead box。Another good way to do this is you actually can duplicate the hardware resources。

 or you can add more ports to a memory structure， which is sort of the equivalent of duplicating the hardware resource。

 And this is， to some extent， a solution that is used pretty widely in something like the the MIps pipeline。

 a basic five stage mips pipeline。 is we actually duplicate certain resources。 For instance。

 there's two memory arrays。 There's an instruction memory array and a data memory array。

And we'll look at an example where those two things are together。

But the simple five stage Mips pipeline was really designed not to have any structural hazards。

 And the I S A was basically designed for that to be the case。 But more complex instruction sets。

And pipeline designs， you know， you might have to deal with。Something like a structural hazard。

 And even if with the MIps I S A。If you go to deeper pipelines。

 you might end up with structural hazards。 and we're going to talk about that now。Okay。

 so the first thing we're going to talk about here is。Structural hazards。

 if we want to unify the memory。So as I said in the five stage Mips pipeline。

You have all the hardware you need for every stage， and all the stages are basically independent。

But let's say we were going to modify this and instead have one memory here。And we wire out。And。

 and we only have one port into this memory。 So only one thing can access the memory at a time。

 And we wire the program counter into here to effect fetch our instructions。

 We wire the data out up here into the instruction register。

 So it's just wired in the same place as the instruction memory was before。

And we take where we had the data memory access when we want to do a load or restore。

And we run those wires down here， and we put a multiplexer here to share the address。

And only one of these resources can use it as a time。嗯。Okay， well let's。Draw the pipeline diagram。

For what happens with something， something like this when， when you go to execute a。

Load instruction will say on a unified。Memory architecture。

So if we take a look at this structural hazard example where we have a unified memory。

Where we have the。One memory here， which is replacing both our instruction memory。And our。

 our data memory， we need to walk through， let's use this an example to walk through the pipeline diagram of how instructions would flow down this。

 this example here。So let's start off by executing something like a load。First。Then let's say。

 we have an ad。Followed by an ad。Fuled by an ad。Okay， so the first pipeline diagram here。

 We're going to have the load coming down the pipe。

And it's going to execute or it's going to enter the fetch stage。

Then it's going to go into the decode stage。 Then it's going to go into the execute stage。

That's going to go into the memory stage and finally right back。The first ad comes down here。

 and it's going to go into fetch。So you go to decode。 It's going to go and execute。

It's going to the memory stage and how you go to right back。

The third ad is going to come down the pipe and go to the fetch stage。Decode， execute。

Memory right back so far looks like a pretty idealized pipeline。This next ad。

Maybe we just put a F here。😡，Let's think about this。 is， is this right。Can we have an ad？

Fettching from our instruction memory at the same time as a load is accessing。The memory。

 this unified memory that we have here。And this is。

 this is the question is we have this unified memory。

 and we are trying to have two things accessing it at the same time。And this is a structural hazard。

 We can't do this。So instead， we're going to put a dash here and we're going somehow either stall or bubble or know up。

This ad for a cycle。 And then we're going to use the fetch。

We're going to use the instruction memory on the subsequent cycle。 And the reason we stall。The ad。

 and we don't install the load is because this is an earlier instruction。Than this。

 This is a later instruction。 we want the early instructions to finish first。 Otherwise。

 we might have some deadlock concerns or deadlock problems。 So now we fetch。We decode。We execute。

WeUse the memory and we write back， and you'll note here。

This gets pushed out one cycle because we had to stall here at the beginning， one cycle。🤧嗯。And。

This memory。And this point here。Is the structural hazard that we saw that we had to resolve。

 And in this case， let's say we stalled one cycle to resolve that hazard。

Let'sSo now that we've seen how to do a unified memory and what the pipeline should look like for that。

Let's go on to a different example here where we have a two cycle memory。And this two cycle memory。

 we're going to have stage M0 and M1。We put a pipe register down the middle of our memory here。

 but only one thing is able to use that memory at a time。So let's， let's briefly draw。

The pipeline diagram for something like。Like this。Okay。

 so the second ad is going to start flowing down the pipe。 and it's going to be in the fetch stage。

Decode， execute。M0， M1。Right back。Then we're going to have the load， going to go。Ftch， decode。

Execute。M0， M1， right back。And now we're going to see a structural hazard。We're going to have。

This second load here。Is going to fetch。It can give you own a decode。

It's then going to going to execute。Now， here is the problem。If we were to put M0 here。

What we see is， we actually have。Two different instructions in time。Wing to use one resource。

 the memory。So we need to solve this somehow。 Now， how do you go about doing this， Well。

 there's different approaches。 we'll talk about that in a minute。 One approach， let's say。

 is you could actually stall the pipeline here。So that was one of our solutions。

 is you stall the pipeline。 So we're going to put a dash here to mean we stalled for a cycle。

 And then we're going to have。M0。And1， and then right back。

And you can see that it's basically pushed this instruction back one cycle。

 but this doesn't happen with other instructions。And the other thing to note is it doesn't happen if you have something like an ad。

After a load here， because that's going to go fetch。Decode。Execute。Oh sorry， it stalls here too。

Execute。M0 M1， and these can be overlapped because we we don't actually have any hazard。In this case。

 because there's not a load loads or two things are not trying to use this memory at the same time。

 So you won't end up with a hazard there。

![](img/914b843e4aae7d66842af9518f6a0f8c_2.png)

![](img/914b843e4aae7d66842af9518f6a0f8c_3.png)