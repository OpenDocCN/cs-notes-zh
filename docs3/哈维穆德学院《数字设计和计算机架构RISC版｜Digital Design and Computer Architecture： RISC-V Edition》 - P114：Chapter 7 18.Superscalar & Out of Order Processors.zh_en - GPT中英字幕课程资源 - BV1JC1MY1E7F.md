# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P114：Chapter 7 18.Superscalar & Out of Order Processors.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video we'll look at superscalealar and out of order microprocessors。



![](img/2c84385f8dc5469d548dae6e6de01768_1.png)

So a superscalealar processor is one that has multiple copies of the data path to be able to execute multiple instructions at once。

So in this example。Lets say we took our pipeline risk vi processor。

And instead of reading out one instruction， we read out two instruction。

Then let's say we had a registered file。 instead of having three ports on it， we had six ports， so。

We could fetch。嗯。The opera ends for two instructions and write the results from two instructions on each step。

Then instead of having a single ALU， let's say we had two of them so we could execute two instructions on each step。

And then instead of having a single ported memory， we have a double ported memory that could read and write two values per cycle。

And then two result marks。So this way， ideally， our superscale processor could issue and execute two instructions on every cycle。

Unfortunately， they are dependencies， and this sometimes limits our ability to issue multiple instructions at once because one thing depends on previous。

Let's take a look at some examples to understand dependencies and understand some techniques to get around dependencies。

So for starters， let's have a program with no dependencies。

 say we have a load word that puts an answer in S7， then an addd。Into S8。

 subtract into S9 and into S 10 or into S11 and store into S5 and none of the inputs to any of these instructions depended on previous ones。

So on the first cycle。We could fetch both the load and the add from the instruction memory。

On the second cycle， we would read S 0 and 40 for the load T1 and T 2 for the ad。And meanwhile。

 we could fetch the subtract in the ant。On the third cycle， a load and add could both。Do addition。

And the register file could read the sources。For subtract demand。Meanwhile。

 we could fetch the or in the store war。On the fourth cycle， the load uses the data memory。

 the ad doesn't need it。The A U is doing a subtract， in and。And the registered files。

 reading operations for the。Or subjecttract。Finally， on the fifth cycle。The register file write。

 S 7 and S 8 back to。For the load and add。The data memory isn't used at all by subtractor and。

 and the AL U is doing or。And add for the or store instructions。

So here we're issuing two instructions every cycle。And so the instructions per cycle is two。Now。

 let's consider a superscalealar processor with some dependencies。So we load into S。

 but now suppose the ad uses S。And then suppose we have subtracted whose destination is also essay。

 and the and depends on that essay from the subject。Finally， let's say we have an or。

 whose destination is S11 and a store that depends on S 11。So in the first cycle。

 we could issue the load。But we can't do the add because it needs S8 that we don't yet have from the load。

On the second cycle， we could issue the ad。The ad will go， but it stalls。And so。你。

ad needs to wait until S is available here in cycle 5。The subtract is independent of the ad。

 so we could also issue that。And both of them finish up in step 7。On cycle 3。

 we could issue the and the or。They stall as well because the adds subtract had been installed。

And finally， on cyclee5， we could issue the story。So now it takes five cycles to issue six instructions。

 so the actual instructions per cycle is6 fifths or 1。2。Better than one， but not all that great。

So to try to get around these issues， we could design an out of order microprocessor that can look ahead across multiple instructions and issue as many instructions as possible at once。

 so long as there are no dependencies。Can issue the instructions out of order。

So the dependencies we need to look for are called Ra， war and w。And I read after write dependency。

We have one instruction that writes and a later instruction that wants to read that register。

 We have to write， wait for the right to occur before we could read。

 or at least we need to have forward。For right after reading。

 we have one instruction that reads and the later instruction that writes to register。

The instruction that writes it can't be moved out of order before the one that reads。

 where we might get the wrong answer。And then in a right after write， one instruction writes。

 a register， and then a subsequent instruction write the same register。

And we need to keep those instructions in order so that when we finish the right。

 we have the result of the second instruction， not the first instruction in the register。

So with an out of order in strict processor and a lot of hardware， we could theoretically issue many。

 many instructions at a time if we had a million execution units in a 3 million ported register file。

 we could。Ideally， issue a lot of instructions。But in real programs。

 we find that there are a lot of dependencies， and even with an infinite amount of hardware。

 it's often not practical to issue more than three instructions on a cycle because of these dependencies。

Out of order， processors are typically built with a device called a scoreboard that keeps track of the instructions waiting to issue the functional units available and the dependencies between instructions。

it finds the next instructions in the scoreboard that are ready to issue that have available function units and have all the dependency satisfied。

So let's take a look at this out of order processor。So we have the load word instruction。

 we could execute that。嗯。嗯。Addd depended on it。 so we couldn't do that。

But we could look far ahead in the program and find the or。

And issue the or at the same time as the load。Now those could run through。The or。Produces He11。

The store needs S 11。So on the next cycle。Cycle 2， we could issue this store。

And forward the results of S 11 from the ore to the store。We'd like to also issue an ad。

 but the ad depended on S 8。Which wasn't ready yet from。A mode。So we would have had to stall anyway。

 so we can't issue the ad at the same time as the store。Instead。

 we issue the add and the subtract in cycle 3。And then finally， the and depends on the subtract。

 and we could issue it in cycle 4。 And now we've issued six instructions in four cycles to get an IPC of 1。

5， which is better， but still not yet ideal。So one more technique is called register renaming。So。

We couldn't issue the subtract。Until after the load word。Because both of them write to S 8。

 and there's a right after read dependency here。That the subject can't be done until after this ad。

 which has to happen after the load。And then。S8， the and can't happen until after the subtract。

So if we were willing to rename registers and instead of this subtract be。Going to S 8。

 let's come up with a new temporary register called R 0。And。Then we could issue the load。Into S8。

 simultaneously， we could issue the subtract。To register our 0。Then the and。

That depended on the result of the subtract。 now we with a renaming hardware。

 that assay has become R 0， so we forward R 0。From the subtract。To the and。The or。Can access S 11。

 so it can be issued simultaneously with the end。Finally。

 the ad in the store can be issued simultaneously， and when we're all done。

 the processor would have to keep check that the final value of essay is actually in this renamed register R0 instead of the original essay。

So with Reg renaming， we can issue all six instructions in two cycles and get IPC of two。

 which is terrific。One more technique for issuing more operations at a time is single instruction multiple data or CID。

And this technique， a single instruction acts on many pieces of data at once。

So a very common application for this is graphics。 Mach learning is also common。

And it can apply to any sort of short arithmetic operations， sometimes this is called pact arithtic。

So， let's say we had。And add instruction to add 8，8 bitten elements。

So suppose we have 64 B registers， D 0 and D 1。And we issue a packed ad。On eight bit chunks。

The registers would be treated as 8，8 B values and would get 8，8 B sums。

And any overflow between columns would be discardided instead of affecting the next。

So if these values were say pixels， we could be doing arithmetic on a pixel simultaneously and get eight times the performance。



![](img/2c84385f8dc5469d548dae6e6de01768_3.png)