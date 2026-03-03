# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P84：Chapter 6 14.More on Jumps & Pseudoinstructions.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello in this video， we'll look under the hood of Risk 5 assembly language to look at more about how jumps and pseudo instructions work。



![](img/a8be39c0bb8e957bc5a076055bd67466_1.png)

So we've seen a variety of jumps in risk 5， but actually if we look more deeply。

 the processor only supports two kinds of jump instructions， jump in link and jump and link register。

Jump and link。Takes。A 21 bit intermediate that it adds to the program counter。

That's a twos complement number so it could jump forward or backwards by up to a million。And it also。

Takes a destination register of where to store PC plus4 when we link。Jump and link。

 register is similar。But instead of taking an offset to add to the program counter， it takes。

A source， register and immediate。And it sets the PC to the source register， plus the immediate。

As well as linking。A return address and RD。So those two jumps are actually enough to do everything。

However， from the pgri's point of view， we don't always need all that capability。

So riskk 5 defines things called pseudo instructions。 They're not real risk 5 instructions。

 but they can be more convenient for the programmer。

 and the asmbr is going to convert them to real risk 5 instructions。So， for example。

 we have seen jump。To some label。And that translates into a jump and link x 0 the label。

So remember x0 is registered zero， it's hardwired to zero。

 so anything you write to it is just ignored。So a jump and link where we're putting the return address in Reg zero。

 we're just throwing away the return address and that can be a simple jump。Remember。

 we also used a jump in link for a function call。And that sQel went to jump and link RA。Ki。

The destinationest。So by default， JAL will' put the return address in RA unless we ask to put it in some different register。

U。To return from a function call， we used Ju register to RA。In general。

 we might jump register to any register， any source register。 and that's equivalent。To jump and link。

 register。嗯。X 0 comm R S comma 0。So that will put the return address in the0 register。 throw it away。

And it will take the destination Rs at zero， so just Rs directly。So jump register RA。

Is actually a jump in link。J R。To RA is really。Jump and link。Register。0。R0。

To jump to its S and throw away the return address。Finally， it's sometimes handy to use return。

Instead of jump register RA。Just as a way to return from a function。

 and those two are synonymous as well。So we see there are four different pseudo instructions for jump from the two actual jump instructions。

 JAL and JALR。Next， let's talk about labels a little bit more。Label indicates where to jump to。

And it's represented in the jump as an immediate offset as the number of bytes passed the jump instruction。

So， for example， if we were at 300 and we wanted to do a jump in link to simpleim， which was at 51 c。

The offset is 51 c-300， which is 2，1 c in heodadecimal。

So jump and link simple as actually encoded as jump and link return address come a 2，1 C。

Where they offset to jump by as the  two1 see。And these offsets are limited to 20 bits for a jump in link or just to 12 bits for jump and link register。

 and this limits how far a program can jump。So there's a special instruction to help for jumping further。

Called add upper immediate PC。It takes a destination register and a 20 bit immediate。

And it sets RD as equal to the current PC plus this immediate in the upper 20 bits。嗯。

So if we wanted to do a。Function call。Let's have a pseudo instruction called call that takes a 32 B offset。

It's just like jump and link to immediate， but it allows a 32 bit offset instead of a 20 bit。

So we can break it into two。True instructions。 First， add up remedia PC， R A comma。嗯。

And then our 20 bit upper immediate。And then jump and link register RA RA comma。

 the 12 bit lower immediate。So this will do the PC plus。I am am。

31 through 12 in the upper bits plus I M M。11 through 0。In the lower bit。 So altogether。

 add a 32 B immediate。And it's using RA as a temporary variable here and here。

 but then it's linking to RA， so we'll put the return address in RA。

So those were some examples of jump pseudo instructions。嗯。Jump to label。

His equivalent to jump and link0 comma label。 throw away the return address。

We saw a jump register to RA。 It like a jump in link0 comm RA comm 0。

Another handy instruction is move。So if we wanted to move S3 to T0， we could do that。

With the true instruction of add I T5 gets S3 plus 0。

But move is a little bit clear of what we're doing。

You've noticed there is no not instruction among the logical instructions in risk 5。

 And the reason is that we can do it with an exclusive or immediate。

If we wanted to invert T2 and put it in S7， we can exor immediate T2 with negative 1 put that in S7。

Remember， negative one as a tea complement number is 321s。

And exclusive or in something with a one inverts it。

 So we invert all the bits of T2 and put them in desktop cell。

A no op is an instruction that does nothing， maybe if we just wanted to pass time。

 and we can do that with an add eye of 0， get 0 plus0， do nothing。

Suppose we wanted to load a 32 B immediate。The L I instruction stands for load immediate destination register and then 32 B immediate。

 And like we saw back in the immediate section， we can do that by breaking it into two steps。

 a load upper immediate with the upper 20 Bs， and then an add eye of the bottom 12 bit。

You might have noticed that our instruction set only had branch less than or branch greater than equal。

So。Theres actually branch greater than if we wanted to compare S1 to T 3。

 branch greater than if S1 and T 3 is the same as branch less than T 3 S1。

Because if we just reverse the order， we switch less and greater。Sometimes we want to compare to 0。

 so a branch greater than or equal to 0 of T2 to a label L 7。

Can be written as branch greater than equal T 2， comma 0。H。To label L 7。

So that would C F T 2 is greater than or equal to 0。Attle bit ago， we mentioned the call function。

That does the add up re and then jump and link register to handle a 32 B offset。In our function call。

And then we'd also said return as a pseudo instruction for jump and link register。

 R0 comma RA comma0。

![](img/a8be39c0bb8e957bc5a076055bd67466_3.png)

That just returns。2， Im sorry。