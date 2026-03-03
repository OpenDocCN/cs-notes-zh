# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P113：Chapter 7 17.Advanced Microarchitecture.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video， we'll talk about advanced micro architectureitecture。



![](img/62a71f12e7fab7b181736616e5e755c1_1.png)

So so far， we've covered three fundamental microarchitectures for the risk processor。Sle cycle。

 the multi cycle and the pipeline processor。 The single cycle was the simplest。

 The multi cycle broke our instructions into multiple smaller steps。

 and it was able to reduce the amount of hardware and share a single memory for both instructions and data。

 but it came with performance loss。The pipeline processor overlapped instructions and was quite a bit faster。

So now let's take a look at many of the techniques used in modern processor design that make for really fast PCs and laptops and phones and servers and so on。

So some of the techniques involve deeper pipelining。 If a five stage pipeline is good。

 more stages might be better。Micro operations for breaking complicated instructions into a sequence of simpler ones。

A branch prediction to reduce the branch hazard。Super scalary processors that can issue more than one instruction in any cycle。

Out of order processors that can execute the instructions in different order to reduce the number of hazards。

A register renaming as another technique to reduce hazards。 single instruction， multiple data。

 Here we have instructions that act on many registers at once。I work done in a single instruction。

Multi threading where a processor can switch between several different programs running on it。

 interleaved and multiprocessors where we have many cores running all on one ship。So in deep pipeing。

Many processors these days， especially high performance processors。

 tend to have more than five clock cycles，10 to more than more pipe stages。

 so 10 to 20 pipe stages is pretty typical。And the number of pipe stages is limited by the pipeline hazards。

 So if you have， say， too much of a branch。Mis predictiondiction penalty that may make performance get worse。

Liit by the sequencing overhead。That each pipeline stage we add add some setup and clock to Q A A。

Power， more registers and higher clock speed cost more power。And the cost of the extra hardware。So。

As we increase the number of pipeline stages。第。Cycle time goes down。

But the time to execute an instruction。Depends on the cycle time， but also the CPI。

 And if we get to too many stages， the CPI may actually start going up。

 and the performance will get worse instead of better。

An extreme example of this was the Pentium 4 microprocessor got to as many as 28 clock stages when processors were in a race selling based primarily on their clock frequency。

And some more pipeline stages would allow for a higher clock frequency。And therefore。

 the higher selling price， even though the actual performance wasn't getting any better。

Eventually the power consumption limit that， these processors were taking 130 watts or more。

And that was unsustainable， so eventually Intel switch to the core micro architectureitecture。

 which is what we see right now with fewer pop stages and more efficient use of them。

The idea of micro operations is to decompose a complex instruction into a series of simpler instructions called micro operations。

And at runtime， these complex instructions can be decoded into the micro ops。

So this is heavily used in complex instruction set computers。

That you can't efficiently execute on a nice， clean data path， like the one we've talked about。

So suppose you had a complex instruction that was load。From an offset of 0 relative to a base of S 2。

To put the result in S1 and also post increment by 4， meaning add 4 to S2 and put it back in S2。

So that's a common type of instruction and a complex instruction set。

It could be used for accessing elements from an array and walking through the elements。

We could break it into two simpler instructions。 first， the load word。And then， the addd。

To add4 to the base address。So without the microops。

 would need a second right port on the register file to be able to write two results in a single cycle that would make the register file larger and slower。

 so it's often better to break it up into these micro ops。In branch prediction。

 we take a guess of whether the branch will be taken。So if you have a backward branch。

 these usually occur in loops。And a loop usually executes more than once。

 So branch backward branches are mostly taken。嗯。For forward branches。

You might take a look at the history of the branch to try to guess whether it's taken。

 The branch was taken last time。 maybe it's good guess to be it will be taken again this time。

So with good branch prediction， we can reduce the inf fractionraction of branches that require a flush and modern branch predictors take well over 90% get well over 90% of branches。

 correct。So in an ideal pipeline processor， the cycles per instruction would be one。

But branch misproductdion is going to increase that CPI。

So our goal is to mispredt as rarely as possible to have the minimum penalty to performance。

Static branch prediction is the simplest technique， it just looks at the direction of the branch。

 if it's a backward branch we could predict that it's taken。

It's a forward branch who might predict that it's not taken。With dynamic branch prediction。

 we could keep track of the last several hundred or thousand branches in a piece of hardware called a branch target buffer。

In that branch target buffer， we would record the destination of each branch and whether the branch was taken。

Next time we encounter a branch， we would look for that destination and see if we encountered that branch before。

If we had。Well sorry， wed look for the。Program counter。

 it indexs the table with the branch targetet buffer with program counter， so we'd find that branch。

Then， we could。Find from the table where it was going and whether it was taken。And not have to。

Compute the branch again， but just guess that the same thing happened as before。

With dynamic branch prediction， we can keep some history。

 and two examples are a  one bit branch predictor or a 2 bit branch prediction。

So suppose we had a program here that was going to add up the numbers from  one to 10。

So initialized a sum nest1 to 0。We'll initialize our loop I。2，0。

And we'll initialize 10 into T0 for comparison。Now we'll have a four loop for I is 0， less than 10。

 I plus plus。So we'll check if I is greater than or equal to 10。Then we go to Dun。Otherwise。

 we do the body， some equals sum plus I， and I equals I plus1， and then jump back to the forelip。

So this for loop should execute 10 times。This branch greater than or equal to。

 should only be taken on the 10th time。They are one big branch predictor。Would predict。

But the branch was taken last time and do the same thing。So on the last branch of the Lou。

We'd been saying， don't take， don't take， don't take， don't take on the last branch of the loop。

be taken。So we would mispredict the last branch of the loop for sure。

But then if we came and ran this program again， it would see that last time we did take the grant。

So on the first time we repeat the loop。It would also predict that we should take the branch。

 which was rough。So anytime we predict wrong from mis predictiondiction penalty。

 we have to have flush some instructions。So the1 bit branch predictor will be incorrect on the first and last iterations of loop。

 If there are 10 iterations。 It's wrong 20 per of the time。And2，2 bit branch predictor。

 we could have a state machine like this。That would say start out in maybe this。

Weekly not taken state。And when we don't take the branch over and over。

 we move into this strongly not taken。And we predict to not take the branch。

Then when we get to the last iteration of the loop， we do the H the branch。

 So that brings us back into this weak not taken state。

Where we still predict the next time to not take it。 So this way。

 we only mispredt on the last iteration of the branch， not on the first time we do it again。

And so we get 90% accuracy instead of 80%。

![](img/62a71f12e7fab7b181736616e5e755c1_3.png)