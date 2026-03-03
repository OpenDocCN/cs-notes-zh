# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P20：Chapter 2 8.From Logic to Gates.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， the topic of this video is from logic to gates。

 We'll look at how to go from Booleing equations into our logic。



![](img/cd94417f074b73d2d89eb0228e627d5c_1.png)

So let's say we had some Boing equation。 We met in dark alley。

 and we wanted to implement it with logic gates。So we could just read this off。 We have A and B bar。

So， here's an and。He。H。And invert it。That gives us A and B bar。Now we need C and C bar and D， and E。

 So C invert it。That gives a C bar。D。Y。And all those together。And then we need to ore those together。

特别坏。As you go to draw schematics， there are few rules to think about to keep your diagrams readable。

It's helpful to have your data flow in a sensible direction。

 So have your inputs on the left or top flowing to outputs on the right or the bottom。

Gates tend to flow from left to right。And keeping your wires as straight as possible as best。

 having to follow a rat's nest a wire is really hard to read in a schematic。嗯。

When you have wires that join or cross， it's helpful to have a convention。

So whenever you have two wires that come to join at a T junction。They always meet。

You don't need to put a dot there to say they meet because it wouldn't make sense for them to not me。

When you have wires that cross。If they cross with no dot， we say they don't connect。

If they cross and they have a dot。Then that means there is a connection。And that way。

 we unambiguously can tell whether there's connections or not。

 And we have as few gratuitous dots as necessary。Let's do another example of two level logic。

 So here we have a sum of products expression。And let's build a circuit。So we've got our inputs， A。

 B。And see。I like to run them in vertically。And run their compliments as well。And sea bar。Now。

 we need 3，3 input end。First one is taking a bar。And be bar。Xi bar。Second one is taking a。And B bar。

C bar。The third one。Is taking a。And B bar。That gives us our midterms。Then we can ho these together。

Taking our outputs and dropping them down。And in this way。

 we could systematically draw any summer products expression。Ass our output Y。

 our inputs start in the top left， they run down。Inputs run down with their compliments。

Then we have a set of and gates to form the products that top off of the literals。

And produce outputs coming across。And finally， we have set of or gates for each output。

That top off the in termss。Sometimes it's convenient to build multi level logic where we use many stages of simpler gates。

For example， if we wanted to build an input exclusive work。

We could do it out of 128 different minterms。Each involving eight different litals。

And it would be this ginormous two level sum of products。But it would be much better。

Say to build it out of a tree of two input exclusive os using only 7。Its another example。

 here's a circuit built out of three levels of Nands and nos。

 and this is common on a chip because Nands and nos are naturally available when we're working with asimmas skates。

Now， let's take a look at some multiple output circuits as an example， consider priority circuits。

Priority circuit is a box。F inputs。F outputs。Will say that input 3 has the highest priority down to input 0。

 having the lowest priority。And we want to assert at most one output corresponding to the input that had the highest priority。

So。😔，If a 3。Is true。Then we want Y3 to be true。And all the others。Be 0。If a 3 is false。

 but a2 is true。Then why 1， why 2 should be true。By3 is false。And these others are false。

If a 2 and A3 are both false， but a 1 is true， then that's the highest priority。And we assert y1。

If a0 is true。Then， and the others are false。 Then y 0 should be true。

And if none of the inputs are true， then none of the output are true。And again。

 this is called a priority circuit， and it comes up with much of useful applications on digital systems。

So we could design some hardware for this。We could pull off the booleing expressions by doing a giant summer of products and then applying Booleing algebra simplify。

 but often you can just do this by inspection。NowLooking at this， it looks like y 3。Is true。

 If A3 is true。And。These rows。Why 2。Is true here。That's true when a3。Its false， but a2 is true。

Similarly， y1 is true here。Which is when a 3 is false and a2 are also false。But a is asserted。

 So a1 being high pressed， highest priority asserted。 Finally， y 0。Be true here。If a3 is true。

 a 2 is true。 A1 is true and a。0， sorry， A 3 is false。 A2 is false。 A1 is false， and A 0 is true。

Writing this big truth table gets pretty tedious。 And so another option is to exploit don't cares to simplify it。

So we could write this out。If a3 is true， then we don't care about a2。

 A1 or A0 and we'd make y3 true， and the others false。The X here， meaning don't care。If a3 is false。

But a2 is true。Then we don't care what a 1 or egg a 0 are。Why 3 will be false。

 but why 2 will be true。If a 3 and a2 are both false， a1 is true。It doesn't matter what A 0 is。

We assert。Y1。If a 0 is the highest priority。Then we assert y zero and if they're all zero。

Then we put out all zeros。

![](img/cd94417f074b73d2d89eb0228e627d5c_3.png)

So that's using don't cares to simplify the truth table。

