# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P94：Chapter 7 1.Introduction.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello and welcome to the seventh exciting chapter of Digital Design and Comp Architecture。



![](img/84446fd1ca7183ca9494ff50d520baca_1.png)

In this chapter， the whole course is going to come together。So in the first part of the course。

 we began with zero and one and worked our way up to logic design。

To being able to design things like AluUs and memories and multiplexors。

Then when we jumped up to the high level， we looked at software and worked our way down to computer architecture。

 the native instructions run by the computer。And now we're going to meet in the middle to connect these two threads in topic of micro architectureitecture。

 we're going to look at how to put together hardware blocks to actually build a microprocessor。

So we'll use all the components we developed in logic。

And connect them together in a way that we can run the machine language instructions。

Of our risk microprocessor。So。As we look at a processor。

 one of the key issues will be how fast it is， so we'll talk about performance analysis。

Then we'll look at three different possible implementations。

 three different microarchitectures of a risk life processor。

The first one is a single cycle processor where all the work takes place in one clock cycle。

Because of this， the clock cycle has to be long enough to accommodate the most complicated instruction。

Next， we'll look at a multie processor where we break up the instruction into multiple simpler steps。

And that will allow each step to run faster and also allow us to reuse some hardware。

And we'll compare how that performance shapes up against a single cycle processor。Finally。

 we'll look at the pipeline processor earlier we had talked about a pipelining example of doing laundry and in the same way we can overlap the execution of various instructions to make run a lot faster。

So all modern processors where performance matters are pipeline。Finally。

 we'll survey some of the advanced microarchitecture techniques used in current processors。

So as we said， micro architectureitecture is the way you implement the architecture in hardware。

The architecture is the programmer's view of the machine。

And the micro architectureitecture is the hardware designer sphere。

So we'll take our processor and divide it into a data path and a controller。

The data path has the functional blocks that work on words of data。

And the controller is going to make control signals to tell the data path to do the right things at the right time。

As I mentioned， we'll look at three different implementations。

 three different microarchitectures of the same architecture， all of them will do the same thing。

 they'll all be risk by processors。But they'll have different trade offs among how fast they work。

How much hardware they take？So to measure speed， we look at the program execution time。

 the ultimate measure of how fast the processor is is how long it takes to run a program of interest to us。

And that execution time is the number of instructions in the program。

Times the average number of clock cycles needed for each instruction。

Times the number of seconds in a clock cycle。So let's define CPI to be the cycles per instruction。

The clock period。Also known as TC。Is the number of seconds in a clock cycle？

And sometimes we'll look at IPC instructions per cycle， that's the reciprocal。

Of the cycle is per instruction。And our challenge is to satisfy some constraints of cost。

 power and performance。Or get the best performance we can under cost or power constraint。

As we're building this processor to keep。Things tractable let's consider a subset of the most interesting risk five instructions We'll look at the R type instructions add subtract and or set West。

We'll look at the memory instructions， load word and store Word。

 and the branch instruction BQ and we'll build up a processor that handles these Later on we'll look at how to add other instructions such as addI or jump and link。

 but once you get the fundamental ones， the rest are very similar。

So the next important notion in microitecture is the architectural state。

 the architectural state determines everything that you need to know what a processor is doing。

So if you took a processor。And well in science fiction movie。

 imagine taking somebody and freezing their brain and then 100 years later。

 reimplanting it in a body and warming it back up。The person's there again。

We could do the same thing of freezing the brain of our processor if we record the architectural state。

 then we could even turn off the power to the computer。

Eventually we turn it back on and if we restore the architectural state。

 the processor will keep going just as it was before。So in the riskk five processor。

 the architectural state we need are the contents of the 32 registers。

The value of the program counter。And the contents of the memory。

If we restore those registers and restore what was in memory and then put the program counter back where it was。

 the program will continue running just as。So any implementation。

 a risk five processor needs to have that architectural state。Here's the program counter。

Here is the register file。With 32 registers。And a memory。

We may break up into an instruction memory and a data memory to separately hold those two parts of the program in the data。

So。In the upcoming sections， we will connect this architectural state together with things like arithmetic logic units to do operations on the registers。

And multiplex use to select the desired result。And put that together to build our data path。

And then we'll make a controller that asserts the control signals to the data path at the right time。



![](img/84446fd1ca7183ca9494ff50d520baca_3.png)