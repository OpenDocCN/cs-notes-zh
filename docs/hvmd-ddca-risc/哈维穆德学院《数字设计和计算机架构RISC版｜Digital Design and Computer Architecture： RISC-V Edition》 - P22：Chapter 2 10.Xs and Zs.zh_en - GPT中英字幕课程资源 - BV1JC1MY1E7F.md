# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P22：Chapter 2 10.Xs and Zs.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， the topic of this video is X's and Z's。

![](img/eff2c6f61bc55ead8cb8ea0fbc146e34_1.png)

So now that we've talked about 0 and 1， those are our good logic levels。

 Let's also talk about X and Z。X typically means contention on the output of a circuit。

So imagine that we had two night gates。Trying to drive。Shared note。

This would not be a combinational circuit because we've shorted two outputs together。

And let's say a is1， and B is 0。Then y this top inverter is trying to drive y to 0。

 The bottom inverter is trying to drive y to a1。And depending on the relative strengths of those inverters。

 you might end up somewhere high。 You might end up somewhere low。

 or you might end up somewhere in the middle in the forbidden zone。And moreover。

 where you end up might change with a voltage with a temperature， with time as things wear。

power supply noise， and it might vary from one ship to another。

 depending on the relative strengths of the inverters。And furthermore。

 it tends to cause a lot of power dissipation because the inverters are fighting with each other。

So we call this an X。And if you see an X show up in your circuit simulation。

 that's often a sign of contention and it usually indicates a bug。

 treat those xes pretty seriously and fix those。Another place we use X in circuit simulation is uninitialized signals。

 For instance， we'll talk about flip flops later。 They have memory。

 And at the start of the simulation， we don't know what the flip flop is holding。

 We'll say that's uninitialized and we'll use an X to indicate the values unknown。And again。

 you want to fix those。Now， remember on the last slides。

 we talked about using x as a don't care on an input。

So you've got to look at the context of the X on an output and mean contention。On the input。

 it may mean undefined。Sorry， on the input， it may mean don't care。

So when you have contention that can cause power dissipation。

 if it's contention with big output drivers that can dissipate a lot of power and potentially burn out pins。

So in honor of all that， I have a special tie to day。About digital design。

See a digital design and it has a picture of Ben Bitdddle。

And here Ben is blowing up his chip due to contention。All right， let's talk about floating。

So if a node is not driven either high or low， we say that it's floating。

Other terms for this may hear high impedance an open circuit or high Z。And typically。

 in a circuit simulation， we use the term Z for floating。So now put that's floating。

 it might happen to be floating at a low voltage。It might happen to be floating at a high voltage。

 It might be floating somewhere in the forbidden zone in between， and it might be floating。

 so that it's changing。 It may change 60 times a second as you're getting radiation from the fluorescent lights。

 or it may change if you touch it。Trouble with floating is a volt meter won't indicate that the node is floating。

 In fact， the volt meter may disturb the node and cause it to go to a well defined value such that your circuit works every time you touch the volt meter to it。

 and it stops working as soon as you remove the voltmeterter。Similarly。

 it may work every time you test it in the lab。 And then when the instructor walks over and touches it to and check off。

 it may stop working。So unintentional floating notes can drive you crazy。

And they usually occur unintentionally if you forgot to hook up a wire to an input。

Floating can also occur on purpose。 We have an element called a tristate buffer。

Let's click a regular inverter。 It's got an input A and an output Y。

 but it's also got an enable signal。When the enable is asserted， this works as a regular buffer。

 when pay is 0。Y is 0 when a is 1 y is1。But when the enable is turned off。Then the output floats。

 no matter what the input does。So this lets us build a circuit that can just leave the output unconnected when it's disabled。

An application of Tri State buffer is in Tri State buffers， Tri State buses。

 where we'd like many different drivers to connect to something。So， for example。

 if we had a shared bus on a computer。And we wanted a processor or a video system or ethernet or memory all to be able to talk to that bus。

 One at a time， Each one could have a tri state buffer。Controlled by a separate na。

And as long as we're careful that exactly one enable is true at any given time。

Than this bus is driven by the one thing that needs to talk on to it。And。

The other systems have their output floating so they don't fight。 They don't cause contention。



![](img/eff2c6f61bc55ead8cb8ea0fbc146e34_3.png)

With the driver that' sacked。