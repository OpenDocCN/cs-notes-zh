# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P14：Chapter 2 2.Combinational Circuits.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， the topic of this video is combinational circuits。



![](img/4376efb5cfb169b18289072acec2730e_1.png)

So let's start out by formally defining circuits and combinational circuits。A logic circuit。

Is a device defined by inputs？Outputs。A functional specification， and a timing specification。

The functional specification defines the relationship between the outputs and inputs。For example。

 the output might be high if the inputs are all low。

And the timing specification says how long it will take for the output to respond to a change to the inputs。

We can look at a circuit as a graph consisting of nodes and elements。In this case， we have a circuit。

With。3 input nodes called A， B， and C。2 output nodes called。Wanzi。And one internal node， named N one。

The circuit has three elements， E1， E2 and E 3， each of which themselves are a circuit。

They could be a logic gate， or they could be some more complicated circuit consisting of a network of logic gate。

So circuits are a recursive definition where the elements themselves are circuits。

There are two general types of logic circuits。Combinational logic and sequential logic。

Combinational logic is logic that has no memory。 In other words。

 the output is determined by the current value of the inputs。

And that's going to be the focus of this chapter。Sequential logic is everything else。

 It's where outputs depend on both previous and current。Values of the inputs。 So they have memory。

For a circuit to be combinational， it needs to obey the following rules。 First of all， every element。

Yourself needs to be combinational。So if the circuit was built out of logic gates。

 those are combinational。But if it were built out of something like foot flops。

Static RA cells that we'll talk about later。 those are not combinational elements。

 so that circuit would not be combinational。Secondly。

Every node in the circuit needs to either be an input。Where it has to connect to exactly one output。

So in this circuit。We have three elements。 Each one of them is combinational。We have。

These notes that are inputs。We have these internal nodes。

 each of which connects to exactly one output。And then we have an output node that also connects to exactly one。

And finally， the circuit has no  sickic paths。 That's no path from an output back to an input。

So this circuit is combinational。On the other hand。

Suppose that we had connected together these two nodes， Shorted them together。

 We'll call that node  one。In that case， the circuit would not be combinational because node 1 is connected to output of both this gate and this gate。

So it violates this rope。Similarly。If we had tied this output， say back to an input。Now。

 this would not be combinational because there's a cyclic path from an output。

 cycling back to an input and looping around。

![](img/4376efb5cfb169b18289072acec2730e_3.png)