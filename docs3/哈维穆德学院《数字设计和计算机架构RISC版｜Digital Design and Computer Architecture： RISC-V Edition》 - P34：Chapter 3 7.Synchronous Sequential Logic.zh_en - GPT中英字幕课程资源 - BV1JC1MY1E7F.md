# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P34：Chapter 3 7.Synchronous Sequential Logic.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/000169345ee880afb7d88b9563177282_0.png)

So let's talk about how we design sequential circuits。

 So sequential circuits are all circuits that are not combinational。

 So let's consider this circuit below where we have three inverters back to back。So if X is。

 for example。One， so transitioning from zero to 1 here in our timing diagram。

From zero to one with time。Going along the X axis。So x is transitioning from zero to 1。

 let's see what happens。So we get a zero to one transition on x so it goes to one。

Y then gets driven to 0。 gets， you know， X gets inverted。 And so some short time later， we have。

Why going to 0。And then y feeds through its inverter， and Z goes to one。Here。And then that drives X。

To 0。is Z going to1 drives x back to 0。And then this repeats。 So now we have。X， going to 0。Well。

 that's going to drive。W。To one。Y was 0， and elses can we get driven to one。And that， in turn。

 is going to drive Z。To0。He was one。 And now it gets driven to 0， which in turn drives。X。To one。

sing to zero。Driveries X to one。 And so we can see that this circuit。

The circuit oscillates all of the nodes， X， Y， Z， oscillate 0，1，0，1，0，1。So this has no inputs。

 the circuit has no inputs。1 to three outputs， depending on， you know， if we use all of those nodes。

 X， Y， and Z， And the period depends on the inverter delay。

 So how long does it take to get through and then go back and start inverting X。

So it has a cyclic path where the output is fed back to the input。

 but it's a little bit hard to control。 It's hard to control the delays。 You know， these， these。

 the delays of the inverter actually vary through operation。

So we're going to fix some of these issues， kind of uncertain timing and know。

 inability to control the circuit by。Doing what we call synchronous sequential logic design。

 So let's define what that means。So synchronous sequential logic breaks these cyclic paths by inserting registers。

 in other words， inserting flip flos。Within that cyclic path。

And our registers contain the state of the system。The state changes at the clock edge。

 And this is why we call it synchronous sequential logic design because it's synchronized or the the change in the state is synchronized to the clock edge。

And the rules of synchronous sequential circuit composition are， well。

 every circuit element is either a register or a combinational circuit。

 So synchronous sequential logic consists of registers and combinational logic。

At least one circuit element is registers， we have to have registers in our system to synchronize the system。

All registers receive the same clock。And every cyclic path contains at least one register。

 So if we have， you know， some circuit。Here。You know， kind of making up a circuit here。

We can't just have a cyclic path like that， We have to insert a register in our cyclic path。

Two common synchronous sequential circuits are finite state machines and pipelines。

 and we'll talk about both。 we'll start by talking about finite state machines or FSNs。



![](img/000169345ee880afb7d88b9563177282_2.png)