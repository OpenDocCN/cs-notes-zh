# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P9：Chapter 1 8.Logic Gates.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Greetings， and welcome to the next exciting installment of digital design。

 Our topic today is logicggate。😊。

![](img/9c4f7c505e259e6c1aef9cddebb9d5fd_1.png)

So logic gates are circuit elements that take zeros and ones in and put zeros and ones out。

And they can do all different functions that we'll talk about。

Simpplest logic gates just take a single input and generate a single output。

One of our favorites is the nightgate。The Sim the not gate has an input called a。An output called Y。

And the symbol。Is a triangle with a circle， and the circle is indicating inversion to do the opposite。

The Boolean equation is y equals a bar， usually pronounced y equals not a。

And not gate does the opposite of the input。 So if we put in a0， we get out of1。If we put in a1。

 we get out of zero。This is kind of like what my son did when he was two years old。

 Does exactly the opposite of what you ask him。The other single input logic gate is called a buffer。

And the output just follows the input if we put in a zero。We get out of 0。 If we put in a  one。

 we get out of one。 So the Boolean equation of y equals a。From a logic point of view。

 this seems useless， but sometimes from electrical point of view， buffers could be helpful。

 For instance， they might put out the same output， but at a different voltage level。

 or they might put out the same output， but with greater power to drive something like a motor or a light。

So single input logic gates aren't all that exciting， with two inputs。

 we get a little bit more interesting。most common to in book gates are and and or。An end gate。

Produces a true output only when both inputs are true。 So the inputs are A and B。The output is wide。

And the Booleing equation is called Y equals A and B。Written just like multiplication。

The truth table here。We can do。0 and 0， is 0，0 and 1， is 0，1 and 0 is 0。1 and1 is  one。

 So the output is only true when both inputs are true。

Or gate is true if either or both inputs are true。So0 or 0 makes 0，0 or 1 makes 1，1 or 0 makes1。

1 or one makes one。The symbol for ore。Is curved。And the Boolean equation is y equals A or B。

This so and looks like multiplication。 And sure enough， the truth table does look like a times B。

Or of a symbol can be addition。But this is not quite addition because one or one makes one。

Sometimes mathematicians use the symbol intersect， a intersect B for and。A union B。For what。

But there is no interor union keys on the keyboard。 So I prefer。

To stick with the regular bulling equations。There's some more to input budget gates。

An exclusive or produces an output that's true when one or the other input， but not both are true。

So 0， x or 0 makes 0，0， x or 1 makes 1，1 x or 0 makes 1，1 x or 1 makes 0。

 The output is true when either。Have the inputs so true。Not both。A symbol is like an or。

 but with two lines on the input。And the Boolean equation is written A， X or B。

 a plus with a circle around it。A Nand gate is like an and， but it has a bubble on the output。

 So it does the opposite。 The balloonan equation is y equals A and B bar。

And it's the opposite of and。 So and was 0，0，0，1。 N would be 1，1，1，0。Not a and 0， n0， mix 1，0。

 n and 1， mix 1，1， N 0， mix 1，1， n 1， mix 0。A nor is the opposite of an or。

 It's like an or gate with a bubble。 The Booleing equation has the bar over it。

 And so the opposite of a o。Is 1，0，0，0。Exclusive Noror is the opposite of Exor。Again。

 the symbol has the bubble on the output。 The equation has the bar over it。

 and it's the opposite of this table。 So 1，0，0，1。We could consider multiple input gates。

So for instance， a three input N。Is true。Well three input or would be true when any of the inputs are true。

So a three input nor would be true when none of the inputs are true。 That's this row。

 So why is true when the inputs are all zeros， otherwise。

A three input and would be true when all of the inputs are true。

It's only true when all inputs are true。Exclusive war for multiple inputs is kind of strange。

 At first glance， you might think a multi input exer would be only true when exactly one of the inputs is true。

 And that is not the case。Instead， we define multi input Xor as odd parity when an odd number of inputs are true。

So， for example， a three input exclusive work would be true when one of the inputs is true or all three of the inputs are true。

Drawing schematics is very helpful， but it's hard to do on a keyboard。

 So we often want to describe our gates with text instead。

And we'll be using a hardware description language in this class called System Verloc。

 This is an industry standard， very widely used language for describing hardware。

And here's some first examples。 So let's say we wanted to define some logic gates， gott inputs， A， B。

 and C and five outputs from five different gates。We could have a knot gate， an and gate， an orgate。

 and Nand and an exer。Each gate has a name， just to tell them apart。

 this not gate could be named Bob。 But instead， we're just going to name them G1。

And then the signals are listed as output。And then， the inputs。So， this not gate。

Has input A output Y1。And the notgate just happens to be named G1。Then we have an end gate name G2。

That has input a。B。And produces Y2。An orgate。That takes inputs a。B and C。And produces y 3。

 and so forth。So， this。Is a textual description of the second。



![](img/9c4f7c505e259e6c1aef9cddebb9d5fd_3.png)

The operations of and or a not date back to British mathematician named George Bull。

He lived in the first half of the。19th century， Aul was born to working class parents who couldn't afford to send him to school。

But remarkably， he taught himself mathematics by himself。

Sufficiently well that he was able to get a faculty position at Queen's College in Ireland。

So quite a character。Bll wrote treaties called an investigation into the laws of thought。

And he felt that the way the mind worked was that we considered propositions that were either true or false。

And we could combine these propositions in a way to get to conclusions。So in hindsight。

 maybe the way human mind works is not quite as rational as Bo suggested。But。

He laid the foundation for binary variables， and truth and falsehood。

And he introduced the three fundamental of logic operations and or a not。

