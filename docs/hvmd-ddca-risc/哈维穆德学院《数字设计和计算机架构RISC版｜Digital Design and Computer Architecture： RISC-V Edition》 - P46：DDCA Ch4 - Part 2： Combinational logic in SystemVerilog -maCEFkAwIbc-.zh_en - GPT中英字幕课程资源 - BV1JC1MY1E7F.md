# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P46：DDCA Ch4 - Part 2： Combinational logic in SystemVerilog -maCEFkAwIbc-.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Let's talk about how to describe a combinational logic using HDLs。



![](img/96ca725486cb28a087604cd5250e1cc4_1.png)

So here we have some bitwise operators on a bus。So here again， we have our keyword module。

It indicates that we're going to describe a module and the name of the module is gates。

We have two inputs A and B， but now。We have this extra information three column zero。

 and that says that we have a four bit bus that's three down to bit zero for each of those inputs A and B and same thing with our outputs we have a four bit bus for our five outputs。

Bits 3 to 0。So we're going to show five different two input logic gates， again。

 they're operating on these four bit buses。And so this first one， we get y1 equals A and B。

This is the end。opperation。If the or operation。Exor。M。And nor。And so。For NanN， for example。

 we can't write this。Because this inversion takes precedence over the and function。

So this would in fact give us。Not a。And be。Which is not what we want。

So we have to write Tilde and then put the A and B inside parentheses so that occurs first。A and B。

 and then a no occurs。And these are operating on four bit buses， so for example， for this Y1。

Y1 sub zero。Equals。A or the signed a sub 0。And。B sub zero。And likewise with the next ones， right？

Yhyice sub one。Y sub 1 is assigned A sub1 and B sub 1， Y sub 2。A 2 and B B2， Y 3 is a 3 and B 3。

And same for the other operations。And again， we can use either single line or multi line comments。

And we can see what this synthesized to and we can see the gates。

It optimized here by using an and gate to produce the。The Y1 output。And then just added an inverter。

 and that's really four inverters because of the four of the buses。

To produce the Nand function or the Y4 output。You can also use what's called a reduction operator where we can write instead of writing you know a sign y equals the and of an eight bit bus in this case。

 a， which is an eight bit bus， and'm going to add all those bits together。This is you know。

 kind of bulky and takes time to write instead we can use a reduction operator。

I just putting the and in front of the。The multi bit signal A。

So assign y equals and A gives us the and of all of those。E bits together。To produce the output wire。

We can also use conditional assignment。 It's also called a ternary operator。

 So this we have our inputs。D0， D1， those are both at four bit buses。 It's three to0。

 a select line and our four bit bus Y。 So this is a two to1 mux。 we call it Mu2。

 you call it other things too。SoMX2 and each of the inputs。

 the data and inputs in the output are four bit buses。And so。

We basically want y equal to right we want y to be connected to or equal to。D0， when S is 0。

And D1 when S the selectck line is one。So we use this turn error operator and we say y equals S question mark that means is S equal to1。

Is S equal to1， if it is， then y equals d1。And this colon here。Is like an ot。Y equals。D0。

So this is called a ternary operator because it's operating on three operas， SD1 and D0。When S is 1。

 y becomes d1。Otherwise。Or else。Y becomes D0。We've seen internal variables before。

 and here's another example。 So here's a full adder， a one bit full adder。 we have A B and carry in。

And as inputs， and we have our sum。Somemon carry out， see out as our outputs。And in this case。

 we're going to build it using internal signals， P and G。P stands for propagate。

 and G stands for generaterate。So we're going to assign these internal signals， P is going to be A。

 X or B。And。G， the generate signal is A and B。So then we can assign our sum as sum equals P X or C N。

 and we can recognize that as a。X or B。X or。Cn。Is there some？Like this A X or B。

It's just precalculated as that P。Interprenal signal。And our。Carry out is G。 This generates signal a。

And B。Or。Or P。Which is a。X， or B。Yess。c人。And now we can see this circuit synthesize into， well。

 here's our prop signal， the or of。Of A and B， here's our generate signal。The and of A And B。

 Then these are used to create our。Outputs。Or some in our carry out output。

So the operators that we use have precedents。And this is listed from highest to lowest precedence。

So like I mentioned before， the not operation has the highest precedence it will happen first。

And then multiplication， division and modo have the next highest precedence。

Adds subtracts so plus a minus and so forth， and we get down here and we have。And。

Has higher precedence over x or， which has higher precedence over or。

And the lowest precedence is the ternary operator。So using this precedence tells us when we need to use parentheses or not。

 So， for example， we want to write this assign。W。Equals。A and B， or。

Bee bar seat tillil the bee bee bar。And see。We don't need to have parentheses there， because and。

Has precedence what happened first before the or operation？And Tilde has precedence over all of them。

This till the be is not be。Happens first before that and operation。But sometimes we might need to。

 so for example， if instead we wanted to write a sign。Why。Equals。A or B。And。C or D。

 and we want it to be this operation。Y equals a。Orbi。And。C， or D。Well。

 now we've got to do that we have to put our front season。

Because otherwise we're going to get A or B and C or D。I otherwise were gonna get the precedence。

If you don't have prehes here， the end will happen before the orR operation。

But we want order to happen first。I this format not？And this is not recommended。Now。

 how many bits of this is not specified？It's unsized。But that value is， you know。

 some number of zeros in front of。The binary representation of。Have 42。Again， strongly recommended。

That when you use numbers in system Bar that you use the formatting Ntic B。

Where n is the number bits and b is the base。So here's an example of bit manipulation。

So we assign Y is a。Two is2 to1。 so this is bits2 and1 of the signal a。

Of bus a and then we repeat bit zero of signal B three times。咁咩。can count that with A0。

And then cancatenate that with the。Minary。how you。The six bit binary value1000 one0，So。

 here we see our。The least significant bits a 12 bit value。Why the 12 bit signal， we see our。6 bit。

Pinary value there， and then whatever a0 is could be what zero， whatever value that is。And then。

 we have。B，0， repeated three times。And the next most significant bids。And finally， at the end。

 we have our A。2 to one is the next。ま那。So again， underscores are used only for formatting。

And make it just make it easier for us to read for humans to read them。So here's another example。

 bit manipulation， so we have a two to1m still， but we have eight bit buses on our data lines2 zero。

And D1 and and our output， y。Our select line is still one bit still a two to one max。

And so we're going to build this， this is a structural module because we're instantiating two of the mues we built earlier。

 these four bit wide two to one mues。And we're going use one of the LSB mus or least significant bits。

 Mus， and one of the MSB mus taking the top four most significant bits of those buses。

 so this is again， a structural module where whentaniing two of these four bit wide。Two to one max。

And so， we take。D0。the least significant and you one the least significant bits of itss three to zero and output the least。

For significant bits of the output y。Select1 is the same for both of these instantiated nees and the second one we take the。

most significant bits of the data inputs and output the most significant bits of the output y。

We can take a subset。嗯。Of the bus。So we can also specify an output as floating。

 so here's an example of a tristate buffer or a four bit tristate buffer， in other words。

 this is like for individual tristate buffers。With an input of a3 to0。An output of y。

Three to zero and a single enable。 And so we use our ternary operator again。If enable is one。

If enable is equal to1。Ban。Thenen why。Equals a just acts like a regular buffer。But otherwise。

 remember or otherwise。Case。Otherwise else。Y equals4 bits。嗯。Floating。They output why floats。

And we can see what this synthesizes into synthesizes into a a tri buffer， as we expected。



![](img/96ca725486cb28a087604cd5250e1cc4_3.png)