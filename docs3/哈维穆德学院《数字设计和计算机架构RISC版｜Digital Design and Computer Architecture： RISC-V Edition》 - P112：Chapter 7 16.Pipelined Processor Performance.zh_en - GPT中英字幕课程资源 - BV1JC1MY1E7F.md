# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P112：Chapter 7 16.Pipelined Processor Performance.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/c87968c507289d159a7d160405912a08_0.png)

Hello， in this video we'll analyze the performance of the pipeline processing。

So consider the second 2000 benchmark again with this。Mixture of instruction types。

And supposed that 40 per cent of the loads were used by the next instruction and caused a stall and that 50% cent of the branches were mis predicteddicted and caused two instructions to be fleshed。

Let's figure out the average cycles per instruction ideally in a pipeline processor it should be one。

 but in reality there are some stalls that increase the CPI。So for a load。F load word。

It's some one cycle， 60% of the time。And two cycles。40% of the time。Is one point。

Cyes per instruction for the branch。Is one cycle。50% of the time。And three cycles。

The other half the time， when we mispredict。2。And so the average CPI。Is。25% for loads times 1。4。Plus。

13。13。For the branches， times 2。Plus， the remaining。62。In one cycle。And that comes out to 1。

23 cycles per instruction on average。Now， let's take a look at the critical path。

So we have to look at each stage to identify the critical path in the fetch stage。

 we have a propagation delay through the PC registered。Plus， a memory delay to read the memory。Plus。

 a setup time。At the end。Fch stitch。For decode， we need to read the register file and set up the next register。

 and we need to do that in half the cycle， so the entire cycle time has to be at least twice that。

For execute， we need to come out of the first register through。 there's total of four mues。

 If we look carefully in the decode stage， there's the A U。

 Then there's time for the andor gate to do the branch logic。 And then we have to set up at the。

Foot fl to update the program count。In the memory。We have a propagation delay out of register time to load from the data memory。

And set up at the next register。And for right back in half a cycle。

 we need to come out of the first foot flop， go through a mucks。And write the registered file。

 and that has to happen in half a cycle， so the cycle time needs to be at least twice that。

So we could put in numbers for each of these and see what the maximum clock period needs to be。

And we find that the slowest cases in the execute stage。So here。We have。嗯。

Let's say we need to forward a value to a branch instruction。So the source is coming from。

The pipeline register here。Either one of these， it goes into a mucks。

The result marks we get that result value。Now let's say we needed to forward it。

So it has to come up through one of the forwarding muges。Then it can go into the AL source Bms。

And now we finally have source B。So the AL U can then use that source in a comparison fair branch and get the zero flag。

That zero flag goes through the andor gate。And then， to the。Next PC， Max。We choose the source。

And finally， the program counters ready。For the。PC， flip flip。So that's our longest path。

And we find TPCQ is 40 picoseconds， plus four mues， each with 30 picoconds。Plus。

 the A U is 120 piconds。 Plus， the and or logic is 20。Plus， a setup of 10 of 50。Is giving us 40。

120 mix， 160。2，80，300，3，50。So 350 picoconds， it's not quite as good as the 200 picooseconds we hoped that we might get with just the memory read being on the critical path。

 but it's still a whole lot better than the 750 of the single cycle processor。

So now if I have a program with 100 billion instructions。

This 100 billion instructions times an average of 1。23 cycles per instruction times 350 picoseconds。



![](img/c87968c507289d159a7d160405912a08_2.png)

Cycle time。It givesives us 43 picoconds to execute the program。So， in comparison。

Our single cycle processor took 75 pcoconds， Our multi cycle went up to 155 picoseconds。

 which is about half as fast as the single cycle。 So that was not a speed up。

 although it did save hardware。The pipeline processor costs the extra hardware。

 costs more pipeline registers。But it can execute our program in only 43 picoconds， which is 1。

7 times as fast as the single cycle processor。So getting a 70% speed up is a huge deal on a processor and getting it just for the cost of some extra registers is a very good trade off。

 and that's why nearly all processors today are pipeline。



![](img/c87968c507289d159a7d160405912a08_4.png)