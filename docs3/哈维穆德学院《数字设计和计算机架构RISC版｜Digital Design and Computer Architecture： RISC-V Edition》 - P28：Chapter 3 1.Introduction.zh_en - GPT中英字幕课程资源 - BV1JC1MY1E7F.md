# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P28：Chapter 3 1.Introduction.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/41383d8ba316d4f9c20494f9c0b4f517_0.png)

In this chapter， we're going to talk about sequential circuits， so circuits that have memory。

 So we'll start by talking about state elements。And then we'll talk about generally what it means to be defined as synchronous sequential logic。

And then we'll talk about two types of synchronous sequential logic， finite state machines。

And parallel circuits or parallelism。 And then we'll also talk about how we calculate the timing of these sequential circuits。

Sequential circuits have outputs that depend on not only the current inputs。

 but also the prior inputs。 So the values of the prior inputs。 And so in this way。

 a sequential circuit has memory because it remembers not only it doesn't just use the current inputs。

 but it remembers what the prior inputs were。 So， for example， on your smartphone。

 if you're entering a code into your smartphone， it has to use memory because it's not just remembering the current value of a code you're putting in。

 but the prior digit that you entered as well。And so we need sequential circuits because they can remember what the prior inputs were。

And so let's define a few terms here。 First term is state and state is all the information about a circuit necessary to explain its future behavior。

 So， for example， if you're entering the code3。1，5 or something into your smartphone to unlock it or something。

 Then this。The state would be holding。 Well， what state are we in， Have you entered the three yet。

 If you have them， we're in the， you've entered the three state。

 And so now your smartphone is in that state waiting for the next correct input of one。

And then once the one is entered， it's now in the state of， okay。

 I know that you entered a three followed by a one。 And now it's in the waiting for the five state。

And so the state of a system is all the information about a circuit necessary to explain its future behavior。

 So what it does next。We're going to use latches and flip flops to store this， this state。

 And we encode the state using binary values。 So we encode the state using bits。And， actually。

We're really going to use flip flops in this class to store the state。

 but either latches or flip flops can be used。And will'll define what those are next？

So synchronous sequential circuit is a sequential circuit that uses full fs。

And each of those flip flops share a common clock。 And so the clock is like on your PC or your computer when you。

 when you buy it and you get a computer that has a 2 GHz clock。

 That's the clock that we're talking about。 So it's this common clock that all of the circuits。

 That's why it's called synchronous because they're all responding to that clock。

And we'll talk about how that clock is used in the circuit in this chapter。

So sequential circuits gives sequence to events。 that's what I called sequence circuits。

 There's some sequence like the code we talked about 315。

 We need to know a sequence of those events first detect the three input and then the one input and then the five input。

 So that's the sequence that we're looking for。😊，These circuits have memory， not infinite memory。

 but short term memory， remembering the prior inputs。

 and the way that they have memory is by using feedback from the output to the input to store information and the information that's stored is bits。

So。😊，Again， state is everything about the prior inputs。

 the circuit needs to predict its future behavior。And it's usually just 1 B。嗯。

And it's the last value that was captured， the last state that was captured。

So we're going to use these circuits or these elements to store the state。

And we're going to talk about four types of state elements。 that by stable circuit， S R Latch。

 D Latch and D flip flop。 And the one we're going to end up using is the D flip flop。



![](img/41383d8ba316d4f9c20494f9c0b4f517_2.png)