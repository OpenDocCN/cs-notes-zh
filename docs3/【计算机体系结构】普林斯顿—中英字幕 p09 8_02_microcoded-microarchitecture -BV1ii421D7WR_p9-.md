# 【计算机体系结构】普林斯顿—中英字幕 p09 8_02_microcoded-microarchitecture -BV1ii421D7WR_p9-

![](img/dbb16a5ac41781acd8b1e0f2f99d1dfd_0.png)

Welcome， so this is our second lecture of EL E475 computer architecture。 and today's lecture。

 we are going to be learning about microcoded microprocessors。

 So these are microprocessors which allow you to reuse components and reuse data path components in order to make a smaller processor。

And we are going to start our review， our first review of three reviews。

And like I said before in the previous lecture， if you are watching this lecture and think， well。

 I've seen this all before， stick through the first three or three and a half lectures that's designed to be reviewed to get everyone on the same page for this class。

 So I'm David Wesloff。 I'm a professor here at Princeton University in the electricallectical engineering department。

 And let's get started talking about our second lecture on computer architecture。

So a little bit of an agenda for what today is going to be about。

 We're going to start off by talking about micro coded micro architectures。

 And then we are going transition to talk about pipelines。

 basic pipelines and review of basic pipelines。And we're going to talk about the basics of pipelining that we're going to talk about。

And， and talk about the frameworks which we are going to need to analyze other pipelines or analyze pipelines that we're going to talk about structural hazards in pipelines。

 So these are。Problems where you might need to use a resource in two different locations in a pipeline at the same time。

Then we're gonna to talk about data hazards。 Data hazards are where you have one instruction or one operation or transaction。

 which is dependent on another operation or instruction in your pipeline。

 what they're in different stages。 So you might need to somehow interlock or control or stall between the different stages。

 then we're gonna to talk about control hazards。 We'll probably hold off on the control hazards。

 depending on how far we get in today's lecture。 And it might end up a little bit in another little snippet on the end。

 But in control hazard， we're going to talk about when you have an instruction which has to redirect the pipeline or change what the pipeline is doing or the instructions flowing on the pipeline are doing。

 that is another form of hazard。Okay， so let's get off start off by talking about micro coded micro architectures。

One of the， one of the big problems is you're going along。

 This is a problem that happened back when processors were first being designed and you couldn't fit a lot of the processor in either a room。

 let alone or nowadays on on a chip。 But one of the questions that comes up is what happens when the processor is just too large to fit in a room or fit in a chip。

 How， how do you go about solving this。 And this is not a question of how。

Do you solve putting multiple processors on a chip or room， But rather。

 if you really can't fit a whole processor in a room。

 So this would be if you're building your chips out of or you're building your excuse me。

 processors out of something like vacuum tubes or switches or electromechanical relays。

 You have to think pretty hard about what happens if it' your processor is too large。

 How do you cut down the size。Well， you can time multiplex the resources。 So that's right。

 You can use a resource and instead of。Physically building a bunch of resources and then connectinging them together。

 Instead， you can build one resource， which is in some way， general purpose。

 And then you can use that resource and then use it again and use it again multiple times for one instruction。

And this is called microcoded processor。 So let's look at a micro control unit and how one of these things works。

 so。In this， in this design， you'll actually have， here's the control lines which run to your processor。

 So these are a bunch of wires that are going to come out of your processor and are going to assert different things on A LUs。

 multiplexers， registers。And then you're going to have some way you need to drive this。

 So in a microcoded control unit， you're going to actually have a microcode address that gets decoded and lights up in a ro fashion a bunch of wires。

 And some of those are going to turn on these control lines。

 And they're also going to be used in this calculation of the next state。Now， if you look at this。

 you can see that this actually implements something like a small， finite state machine。But the。

 the one interesting thing here is that you actually have the app code from the program coming in here。

 And effectively， what you can do is for each instruction you're trying to execute in a program。

 you can cycle through a little state machine for it。 And you can have different state machines。

 depending on the app code that comes in here。😊，So the app code comes in here。 You might have。

 for instance， condition flags or some of that coming out of your processor。

 So whether the instruction is a branch and whether the instruction is taking that branch or not。

 And what you can do then is take that along with a little flip flop here。

 which will keep some piece of state or an address。

 you can actually step through step through a little state machine， which will do multiple things。

 And we'll look at this as a little more example of how one of these microcontrol micro control units will hook up to a microcoded microprocessor。

Or a microcod processor。 Last thing I wanted to get across here is。This is typically a rom。

And you can actually cycle through it multiple times。

 and the raM is going to tell you where the next microcoded instruction is。

So you'll be basically cycling around this loop multiple times or maybe only one time。

 depending on the actual instruction you're trying to execute。

Here is the micro coded control unit or the micro control unit hooked up to a microcontrolled micro。

Codated processor。So we have a data path sitting in the middle here。

have a bunch of wires coming out of our control unit here。

 which assert different things on the data path。 For instance， are you doing a subtract。

 Are you doing an ad， And it's going to swing different multiplexors inside of this data path to select what operation is actually occurring。

And I wanted to contrast the micro。Controller or the micro。Control unit with。

The memory where you're actually going to store your user programs。

So your user program is going to be stored in a Ram structure or randomly accessible memory structure versus a read only memory structure。

 So a good。Example of this is you'd have your actual ISA instructions here like X A6 or MIPS sitting in your RAM。

And up here， you're going to have microcode instructions。So if you go back to this diagram。

 typically the RAM entries are called microcode instructions。

 and sometimes people write little programs that say how do you sort of control the different lines that come out of here？

Okay， so let's put this all together and look at how we would build a。Bus based。Risk processor。

 So we're gonna build something like a MIPS processor。

 which you may recall from your computer organization class。

 And we're going to use a data path where we reuse data data path elements。Over time。

 so we're gonna time multiple the resources。 So this is not a pipeline design。

 and it's not even a single cycle risk design。 But instead， it is a micro coded risk design。

And we're talking about this because we are going to contrast this with pipelining in today's lecture。

So let's， let's look at this diagram。 We're going to see。That we have a register file here。

 which has 32 general purpose registers because we're trying to implement MIps。

 which has 32 general purpose registers。 And we also store the program counter。

Or the instruction pointer in this register file。 This register file actually has。33 elements。

 or maybe you can store it in where the zero register is。 the zero register is in MIps。 if you。

 if you try really hard because that's typically hard coded to 0。

So let's walk through how a instruction is going to be executed on such an architecture。

And a couple of other things to note here， this is main memory。

 So we're gonna have to fetch our instructions from over here。Our AUs here。

And this is our instruction register， and everything is connected together on a bus。We are only one。

Value can be driven at a time， and that value can be broadcast though to multiple locations。

So let's start off by thinking about what do we need to do to execute instruction， well。

To execute instruction， we're gonna start off by fetching the program counter for the instruction。

So the microcoded control unit is going to assert the wires to basically say。

 do a read out of the register file here。For the program counter。

 And we know that program the program counters can be selected because the microcont control unit is going to set on the register select lines here。

 assert the entry， which will choose。32 will say， which will select the program counter。

So the program counter will be this is all in one cycle right now。

 The program counter is going to be asserted onto this bus。

And now we need to latch it somewhere and register。

 So it's going to be broadcast all the way on this bus。

But we actually want to take it and load it into this memory address register here。And thats。

 that'll finish our first cycle of our micro coded control unit processor or micro coded control unit processor。

 The next cycle。This is all within one instruction。

 We're going to fetch the instruction we need from the。Data memory。Or and the instructionary。

 So that is going to get forced onto this bus。 And we're gonna take it。

And latch it here or register it into the instruction register。 So at this point。

 we fetched the instruction。O， that's， that's done a fair amount so far。

 The next thing we need to do is go get the actual operas。So in the third cycle here。

 we are going to take the RD， we'll say， or actually， we'll take the two sources， RRS 1 and RS 2。

 and we're going to fetch first RS1 from our register file。And。

Latch that or register that into the A opera end。 Then we do the same thing。

For Rs2 on the fourth cycle。 And now we can actually do， let's say an ad。

 So let's say we're assuming that we're doing an ad instruction here。 So now we can do the ad。

 So we let A and B actually add。And we need to store the results somewhere。 Well， conveniently。

 we know that we want to store it into the destination register。

So we don't have to store it into A or B。 We can actually store it back into the register file here。

 So we will be asserting R D as the address， and we will be the microcode control unit。

 We will be asserting register right on the register file。Okay。

 so the we've now actually done our actual operation。Almost completely。

 we next need to figure out how to increment the program counter because we want to go fetch the next instruction。

So as we said， we didn't store the program counter anyway anywhere here。

 So we need to go refresh the program counter out of the register file。

And we're going to reuse or time multiplex the ALU here。 So we're going to fetch that value。

 put it into a。And we're going to。Incremented by4。 So the next cycle will do let's say at operation here。

 Let's say AU has a special operation just for adding 4。Alternatively。

 you can try to load4 into the B register here。And we're going to add 4 because our instruction is 4 by long。

 and we're going to store that value back into the program counter。 So at this point。

 we've actually executed a complete one instruction。 and it takes。

 I think we added up something like5，6， though I think 6 or 7 cycles at that point。 Now。

 one of the things I wanted to point out before we move off the slide is that。

Depending on the instruction you're executing。You can have variable amounts of time taken。 So。

 for instance， if you're trying to do a branch instruction。

Branch instructions are a little bit different。 We're not going actually just add4 to the program counter。

 We might need to fetch a different value and do a compare and then fetch either the program counter or add a different value to the program counter。

 when we go to do a branch operation， Likewise for jumps and it can have different numbers of cycles。

 Another good example of different numbers of cycles is if we're going to be operating on a unary instruction or an instruction which only has one input。

 So a good example。 of this is a。Oh， let's think what is a good example of this。

 This is something like a logical negation where you just flip all the bits in a， in， in a value。

 I don't think Mips actually has that instruction。 Anyway。

 what I'm trying to get across here is you can actually have different numbers of cycles to execute instructions。

 depending on the instruction。 So example， something like a load instruction would also take a lot more cycles because you're gonna have to cycle the memory unit here。

More times。 So you'll have to execute an instruction where you actually go and fetch the data from the memory and then put it back in the register and maybe do some math with it and then store it back into the general purposese register file。



![](img/dbb16a5ac41781acd8b1e0f2f99d1dfd_2.png)

![](img/dbb16a5ac41781acd8b1e0f2f99d1dfd_3.png)