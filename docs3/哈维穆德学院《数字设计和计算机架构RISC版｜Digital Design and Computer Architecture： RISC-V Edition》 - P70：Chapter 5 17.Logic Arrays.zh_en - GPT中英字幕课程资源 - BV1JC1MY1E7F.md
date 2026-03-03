# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P70：Chapter 5 17.Logic Arrays.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/2e272bb403c2445dcfe72d9ab42f1684_0.png)

And let's talk about the last topic of this chapter which are logic arrays。

 are two main type of logic arrays， PLs， programmable logic arrays， and FPGAs。

 filled programmable G arrays。So PLAs are and gates or is an and array followed by an aura array and that kind of pattern。

You've seen before in our two level logic with an gates followed by or gates that can implement SOP form equations。

These only do combinational logic and the internal connections are fixed。

 so they're limited in that you can't perform any sequential logic and there's little flexibility in the internal connections。

FPGAs， on the other hand， filled peramble gate arrays。

Allow us to do both combinational logic and sequential logic and the programmable part of it。

 filled programmable gateatorways， we can program both the function performed and the internal connections。

😊，Both are still used because PLAs are cheaper in general than FPGAs because they're simpler and they only do combination logic。

But FPGAs are common for systems where we need both。Comational and sequential logic。

Here's an example PLA or programmable logic array， we have our and array。Followed by our war array。

Our and array performs the products。Or computes the products or imlicants。

 and then we or those together in the or way。 So here's our inputs， A， B and C。

 and there's you know those and gates pick off some of those inputs produce the implicants。

Or the product terms， and then our or array or them together so we can easily implement equations in some products or SOP form。

😊，Here's some dot notation for PLA just like RAOMs， we can use dot notation。

Here we have A bar and B bar and C。A and B and C bar and so forth。 And then we in that we're a way。

 we pick off which implicates our product terms we want。

Field programmable Gatorways or FPGAs are composed of LEs， which are logic elements。

 some FPGA manufacturers call these CLBs or configurable logic blocks。

 and these perform logic both combinational and sequential。And also IOEs or input output elements。

 and these IOEes are you know on the peripheral of the chip and they're used for interfacing with the pins on the chip。

Between these elements， both the LEs and the IOEs are programmable interconnects and these connect in a programmable way those different elements。

Some FVJs also include common building blocks such as multiplplayierers and Rams。

 just because they're commonly used by designers。Here's a picture of the general layout of an FPGA。

 You can see that we have our logic elements。Performing both combinational sequential logic in the middle of the chip。

 and then we have our input output elements or IOEs。

On the outside of the chip to interface with the outside world。

So let's dive into what is inside of a logic element so Ls these logic elements are composed of themselves lookup tables that perform combinational logic。

 so this is what we talked about when we talked about our memories using them as lookup tables that's exactly what the lookup tables are they're very small memories and flip flops。

😊，To perform sequential logic， and then we also have multiplexers that connect these lookup tables and flip flos together。

This is a logic element or LE from Altra's cyclone 4 FPGA。

 and this is a picture from that data sheet from the  Cyone 4 data sheet。就。

A lot of stuff going on here， let's focus on the main parts of this figure。We have this lookup table。

 which is a small memory。That has four inputs。Data1， data 2， data 3， and data 4。

And that's a two to the four by one bit memory， and so it can perform any function of four inputs。

And。And you may notice that we could choose this output here。From。A flip flop。

 So that next element there is。Our flip flob。 So here in green。We have our flip flop。

It has a clock input here。And it has an enable input。And。A low asserted clear input。

 and then also has synchronous load and clear logic ahead of it。

And so those two elements are the main elements of the LE or the logic element。

 we have our lookup table and we have our register and so on this you know we have a bunch of these little multiplexers and those control lines are configurable those select lines are configurable and you can see that we can either take out。

FromFrom those multiplexers， we can choose either。The output of the。Of the lookup table。Or。

The output of。Our flip flop。And then we can you know。

 depending on how we can configure those select lines。We can feed that to other logic elements。

In addition to that， there's， there's other， you know， there are other pieces。 There's a carry chain。

 So this helps speed up addition because that's a common common operation that the designers want to perform。

 And there's some you know， additional kind of。Asynchronous clear logic and some routing logic here。

For the， for the clocks as well。But again， the main things are this lookup table。And。The flip flop。

 and we can choose either a。Sequential output from the flip fl or we could choose the combinational output from our LE from the lookup table。

And you may also notice that this output here。Could also be fed back。

 so output from our flip flop could also be fed back to be used in this combinational logic。

 depending on。What the select line is for that multiplexer。

 and that could be useful for things like finite state machines。So again， the cyclone for LE。

 most important parts are the four input lookup table。That's small memory，2 to the four by one bit。

 Look up table。Or two to four by one bit memory， one registered output and one combinational output and we can choose between。

Whether you want to use a registered accommodational output。

Let's show how to configure a cyclone for logic element L to perform the following functions。

 So we have a function of three inputs here。And another function of， in this case， two inputs。

So our lookup table mean， our lookup table。Just is a small memory。It could have up to four inputs。

And we only need three， so we're going to tie A B and C to three of those inputs and then the last equipment we can't just leave it floating right all inputs have to be driven to something。

But we can tie it either to zero or one doesn't matter， but it has to be tied to one of those。

 doesn't matter if we tie it to one or zero， but it has to be tied to one of those。

And then our lookup table can perform the function that we want and how do we define that well we'd have to write a truth table for that。

 ABC and our output。X。And I'm going to draw what that tree table is。0，0，1，0，1，0， blah blah， blah。

So it would have a one here， A bar， B， bar， C， and then a one in the。1，1。

0 case and everywhere else would have。0eros。And then we would feed that through the final multiplexer as the output of our logic elements。

 we want a combinational logic output。Similar to that first problem。

 you we have only two input variables。 we can still use our Florida。For input， look up table。

Tie A and B here， and then we can ground the other two inputs。If have it's tied into something。

 member inputs always have to be tied somewhere and then we'll choose that。

That combinational output is the output of our logic element。

And then we would draw the choose table for what that is， 00，0110。11， and this is A and B bar。

And so that would be what we would store。In our。You know， you could put。0，0 for the other bits。

InIn our lookup table in our small memory。And so here we have it written out to data 1， two。

 and three。Connected to A， B and C in our lookup table， and this is what our lookup table。

Should hold inside its memory。And again， don't forget that we have to tile of our inputs to something outputs can be left unconnected。

 but inputs cannot， so data 4 would be tied to zero。And then。You know， similarly for。

Wigs A and B bar。Connect A and B to data 1 and data 2。And then our in our truth table。

 those we don't cares， but not in our connections， we have to tie data  three and data four to something。

And we store inside our lookup table。 This is what we're storing。A one in the。10 address or the 10。

Equals1 b equals zero case。Now I suppose we want to use LEs to perform this Xor function of six inputs。

Well， it'd be nice if we could just use one lookup table， but we can， right。

 but we can use one to do four。A b or a one a two，A 3， a 4， we could perform this。

 this look up table on one of valuess can perform， you know， that kind of partial。Calculation。

And then we feed that。Through to the output of that LE and then feed it to another LE。

right to the look up table of another l e。And then we have our a5 and A6。the other inputs。

Ground the fourth input。And now this this one performs， let's you know， some temporary。

Yhy1 or something？W1。X or。A 5 x or a 6。And then we feed that to the final output。As our Y。

 as our combination output。And so this room requires two logic elements because we're going to need two lookup tables。

 we can't fit in a single four input lookup table， we're going to need two of those。

How many cyclone 4 Ls are required to build a 32 bit， 2 to1 multiplexer？Well。

 let's think about two to one multiplexer， let's just draw this out。Has。A single bit。

 two to one multiplexer。Has a select line。And。two inputs d zero and d1，In the output way。Okay， well。

So。To build that with a lookup table， we would need， well， it has three inputs， D0， D1 and S。

 a select input， and so would need a single lookup table to do each of those。We have a lookup table。

 we have select。D0， D1。The fourth input of the lookup table to be tied to zero。

 so that would produce one of our bits。And would need。So that's a single L。

that last multiplex are to select the combinational output。And we're going to need 32 of those。

 so we're going to need 32。Logic elements to implement a 32 bit2 to1 multier。

And the last example for figuring out how many logic elements would need to build some circuit。

 let's do a sequential circuit， so we have some finite state machine has two bits of state。

And two inputs。And three outputs。 So how many Ls or logic elements would we need to build this？Well。

 two bits of state， we know each logic element has just a single flip flop。Or single register。

 single one bit register。And so just for the bits of state would need to figure out right。

 we're trying to figure out the next state。Next date。Well， we know already if we need two flip fl。

 we're going to need two logic elements， so there's two of our LEs。Okay。

 can we calculate what the next state should be with a single lookup table？Think about that so。

What do we need to calculate the next state while we need our current state。

 which we know is two bits。Okay， so there's two of our bits being used and our inputs。Okay。

 our inputs are twobits， so in fact we can calculate our next state for each next state bit with a single logic or a single lookout table。

Okay， so that'll work for calculating our。Next state or state bids。And。

What about our outputs Well our outputs are determined just by our current state so our current state is2 bits and we three outputs though。

 so we're going to need。three。3 Ls。To to give us three outputs， three combinational outputs。

That's a multixy。And so。Here we have one LE for each bit of state。

the next state logics that's two well together and one LE to compute each bit of the output again。

 we'll apply two of those lookup table inputs to zero because we actually only need two of those inputs to determine each of the outputs。

Someone these fiveLs together two to calculate the states and to store the state。

In the flip flos and three to calculate。The the outputs。

The FPG design flow is to use a CAD tool like Altara's Corus2 or Corus Prime。

Enter the design using either schematic entry or an HDL， most typically using an HDL。

 simulate the design。Not an national stock。And then synthesize it and map it onto the FPGA。

 that's what the CAD tool does and then download the configuration onto the FPGA。

 and finally we'll test the design in hardware。

![](img/2e272bb403c2445dcfe72d9ab42f1684_2.png)