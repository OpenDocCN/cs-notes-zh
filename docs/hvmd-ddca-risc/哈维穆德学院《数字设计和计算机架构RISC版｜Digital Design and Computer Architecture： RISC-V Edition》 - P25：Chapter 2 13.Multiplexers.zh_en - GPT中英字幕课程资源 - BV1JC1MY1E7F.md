# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P25：Chapter 2 13.Multiplexers.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， the topic of this video is combinational building blocks in particular multiplexors。

So now that we have a systematic way of producing combinational logic。

 let's take a look at some common building blocks that we'll use quite a bit。 And first。

 we'll look at multiplexors。

![](img/2c61ebb81202fa0292b4ca219ea5d37b_1.png)

So multiplexer is also known as a mux among friends。

 and it chooses one of n different inputs to connect to the output。So， for example。

 a2 to one multiexer has two inputs。And one output。

And then a select signal to choose which are the two inputs。We'll call the inputs D 0 and D1。

 the output Y， when select is 0。Y gets D0。When select is1， y gets T1。

So here's that simplified truth table of it。If we actually put out the full truth table。

When select is 0，50。0， we get out of 0。If。D 0 is a 1。 We get out of1。Same way here。When select is1。

 we just copy B D1 over to the output。So for an n to one multiplexer。

 we need log base two of N select bits to make the choice。For 4 to 1， we would need 2 Bs of select。

 For an 8 to1 Ms， we would need 3 Bs of select。Let's look at how to build some multiples so we can build anything out of logic gates。

We can use some of products。 so taking our truth table。From our mugs。

 we could put it into a carno map。If。This is the map we get。We circle。The ones。This。😔，S。

When select is0。D，0。When D 0 is one。We get it true。 And D1 doesn't matter。So， that's this term。

When select is1。Then， if。D 0 doesn't matter。 D1， when it's1， we get out of true。

We could also just do this intuitively。 We could say why is true if select is0 and D0 is true or why is true if selecting is one。

D1 input was true。We can take these directly to gates。So， here we have。P bar and D 0。

S and D1 or them together。Another interesting implementation of a multipleer is with a pair of tri states。

So here we have two tri state buffers。Each hooked up to one of the inputs。

And we control their select。 So we turn on exactly one of the tri states。If the select is 0。

We choose D0。 The select is1。 We choose D1， and we pass that through to the output。

Notice here that we have shorted the output of the two tri states。

Which technically violates our rules of combinational composition。

But since only one of the tri states has an active output at any given time， this does work。

 and it's illegal sick。Now， suppose we wanted a 4 to1 multipleer。 Here's the symbol for the 4 to1 Ms。

 It's got four inputs， D 0 through D3。It's got a 2 bit select when the select is 00， which choose d0。

 when the select is 01， which choose D1， select 10， which choose D2， select 1，1， choose D3。

 just binary。So we could do this with a two level logic。Here， we would need。For midterms。

To choose D 0， D1， D2 or D3， pour them together。We could also do it with four tri states。

To choose one of the four inputs based on the select。Or we could do it hierarchically。

 We could build our 4 to1 mus out of two levels of 2 to 1 mus。

So we could look at the least significant bit and choose either even or odd。

Even or odd based on the least significant pit。And then on the most significant rid of the select。

 we could choose either upper。Or lower。Depending on one or0。

One of the nifty things about multiplexors is you can actually use them to implement lookup tables so you can build an arbitrary truth table using a mux。

If we want a truth table with four rows， we can build it with a 4 to 1 mux。

By simply taking the values。And putting them at the inputs。

 taking the variables and providing them to select。So this mus will receive A and B。If A and B are 0。

0， then we want the output to be 0。 So we hook it to ground。If A and B are 0，1。That's this row。

 We want the output to be one。 So we hook to power。If A and B are 1，0。We want the output to be 0。

And 1，1，0 again。So。This multixer is performing y equals a bar B。

 This is a pretty complicated way to do a bar B。 But the neat thing is that by changing this connection of power and ground to the input。

 we could reprogram the multiplexer to do any logic function。 Any truth they will。

Same way to do a truth table for a three variable expression。 We would need an 8 to un multiply。



![](img/2c61ebb81202fa0292b4ca219ea5d37b_3.png)