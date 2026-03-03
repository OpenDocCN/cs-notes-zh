# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P29：Chapter 3 2.State Element 1 Bistable Circuit.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/68a29515a4027129ba7f1a754ee696ff_0.png)

So let's start by talking about the bi stable circuit。 Now。

 the bi stable circuit is called bi stable because it has two stable states。By stable。

And it's the fundamental building block of other state elements。

And so this circuit has two outputs Q。And then there's this other wire， so here's Q， the Q wire。

 and then another wire， the Q bar wire here。And。It has no inputs。

So let's see how this circuit is by stable。 So if the output is 0。 So if  Q is 0。

Then that zero comes back to inverter 2， the input of inverter 2， inverter 2 outputs a1。

 it inverts it。Now puts a one， one goes into。Inverter 1。

 the input of inverter 1 and inverter 1 continues to output that 0。 So this is a stable a state。

And it outputs this this Q， the state bit that's being stored。Is a0。

And you can see that similarly if Q had been a1。Well。

 one would have gone into the input of inverter 2 I2。Inverted to0，0 goes into I1， gets inverted。

 and we get our one out on Q。And so that's also a stable state， so it has these two stable states。

 Q be either one or zero。😊，But there's a bit of an issue， because。There are no inputs。

 And so you can't control what's being stored。 whatever it's being stored will stay that way， right。

 It has memory and it'll stay in that stable state of holding or storing one or zero。But yeah。

 that's you know， doesn't have any input so we can't control it。

And so another way of drawing this is。We have our output Q。 Here's our inverter。Inverter1。Output Q。

And we can see that that。Comes into the input of inverter1。So here's， I meanite inverter2。

Here's inverter 2。And that goes。Out from the output of inverter 2 and into the input of inverter 1。

 So these are the same circuits。But written in two different ways。 and this kind of this view of it。

 And here we have Q bar。This view of it where the output。

You knowThey both have the output of I1 going into I2， the input of I2。

 and I2's output goes into the input of I1。And we refer to this circuit as a cross coupled。Inverters。

 because they're coupled by the outputs of each inverter being tied to the input of the other inverter。

 So they're cross coupled inverters。 but these are the same。

 These are actually the exact same circuit。And we could also think of evolutionvol。

 two inverters back to back。Well， we lose our Q bar if we abstract away the two inverters。

 but functionally it's a buffer that is output tied to its input。

Two inverters back to back are the same as just a single buffer。

So here we go through each of the possible stable cases again withq equals to zero。

That gets fed around。The inverter 2 inverter 2 inverts it。

Feeds back into I1 and we get our0 back out and this is a stable state Q bar equals 1 Q equals 0 they're the inverse of each other Q is the inverse of Q bar and Q bar is the inverse of Q so that follows our kind of Boolean axions that that the inverse of Q has to be inverted value。

😊，Andq equals one， we can do the same thing if  Q were one then。One comes ran to in Ver2。I too。

 inverts it。Feeds it back to I1 and I1 inverts that zero and we get our one back。

And so this is also a stable state。And so it does store this one bit of state。

 but we don't have any inputs to control a state。So this next circuit we're going to talk about is going to fix that issue where we can actually control what bit is being stored。



![](img/68a29515a4027129ba7f1a754ee696ff_2.png)