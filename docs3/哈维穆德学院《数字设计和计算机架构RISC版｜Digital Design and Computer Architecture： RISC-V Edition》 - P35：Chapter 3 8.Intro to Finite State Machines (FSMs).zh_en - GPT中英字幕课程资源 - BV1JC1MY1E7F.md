# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P35：Chapter 3 8.Intro to Finite State Machines (FSMs).zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/7d191dc81e2652bcc25f7f46d73cdc00_0.png)

Finite state machines consist of a state register and a combinational logic。So the state register。

 here's our state register， contains the state of the system。And the state of the system S。

 or we can either refer to it as current state or just simply state。Is the output of the register。

 what's being held， the bit or bits being held in that in that register。 And at the next clock edge。

 So we can see our clock coming in here， right， We have our clock edge。Or clock point like that。

And at the next clock edge， at each clock edge， this next state。Becomes the current state。

And so we are overloading this， this prime symbol here and S prime。

With the prime after it refers to next state， S by itself refers to the current state。 or just。

 again， we refer to that as just the state。We also use combinational logic to calculate the next state or compute what that next state should be So C means combinational logic。

😊，And we also use it to compute the output。 And this is called the output logic。

 So we have two blocks of combination logic and a state register to define what what our finite same machine does。

In a finite state machine， the next state is determined by the current state and the inputs。 So。

 for example， if we have our smartphone and we're entering， you know。

 our code to unlock it and we have our code is maybe 5，7，3。And maybe we've entered our five already。

 So we're in a state that says， hey， five has already been entered。 Now。

 our next state is determined by this current state。

 The current state is have seen has seen the five， right。And the input。 So the the next input is 7。

 then。The state will become， hey， I've seen the 5 and 7 or the current。

 the this smartphone will say seen the 5 and 7。 Now， I'm in that state and depends on the input。

 Now it gets maybe it gets a 5，7 and a 4。 Now it says， no， I'm not gonna lock it。

 So it depends on the current state。Perhaps we're in the received a five and a seven state and what the inputs are。

So our next state or what it does next is determined by the current state and the inputs。

There are two types of finance state machines and they differ only in the output logic or how the outputs are generated。

So a more finite state machine， the output depends only on the current state。

 And so we have this picture of our more FSM。 we have a。😊，State， our state register in the middle。

 showing our current state on the output next state on the left。And we have our next state logic。

 our combinational logic block that uses the current state or the state of the system and the inputs to determine or calculate。

That the next state。And a more FSM depends on only the state of the system。

To calculate what the output should be。So outputs are determined by the state bits or in other words。

 the current state of the system。And more FSMs are by far the most common type of FSNs or finite state machines in。

 you know， that use。Just， you know， in industry or in other projects。

But there's also a second kind of finite Stay machine called Ameli FSM and。

TheThe current the state calculation or the next state calculation。😊。

Is determined by the inputs and the current state like it in a more FSM。

 but the output logic differs。Because the output is determined by the inputs and the current state。

In our more FSM， the output was determined by only the current state。

And so they only differ these two types of FSMs differ in how they calculate the output logic。

 and we'll give examples of both of these finite day machines。



![](img/7d191dc81e2652bcc25f7f46d73cdc00_2.png)