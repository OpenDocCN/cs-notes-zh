# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P46：46_11_03_位_寄存器与内存.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/6011aae7cd929f02b6f522581eeb05fc_0.png)

Comal circuits that we considered in the last lecture just compute and just do their thing。

 you provide values on the wires as inputs and the computed values available in the outputs。

 what we want to look at now is the very important idea that we want to have circuits that remember things。

And fortunate， as with the switch that we used as the basis for combinational circuits。

 there's a very tiny component that we can use as a basis for all the circuits with memory。

 that's what we're going to consider next。So a sequential circuit is a circle that has feedback that has loops in it now。

 just as with computer programs， when you add loops to a circuit。

 you're introducing a whole new level of complexity in the behavior of the circuit。

 wouldn it be extremely careful about how we introduce feedback。

And the reason that we use sequential circuits is the idea of memory。

 it really makes the difference between a calculator and a computer。

And but fortunately we can get by with a pretty small set of basic abstractions just as with combinational circuits。

 again we have on and off， we have wires that propagate on and off values。

 we have switches that we can control propagation through the wires with automatically controlling the switches。

 and now we're going to add something new which is called a flipflop and that's a very simple circuit with feedback that remembers the value。

That's what we're going to talk about next。So the thing is if you have loops in circuits。

 then the behavior is going to depend on the sequence of switch operations。

 and so we need some very tight control on this， so here's just the simplest possible example if you have two switches that are each blocked by the other。

So these are two switches connected to power dots， and they each block the other one。

Now we're going to pay attention to the value on the wire that comes out of this little unit。

 but the thing about it is that the state is determined by whichever one switches first so for example。

 if the one on the bottom is the first to switch and and therefore block the power dot on the bottom from going to the output。

 then the state is going to be zero， that output line will be off。

But if the one at the top switches first， then the power dot on the left is connected to the output and the output is1。

And the thing about this is this depending on which one switches first。

 if it gets in one of these two states， it's going to stay in that state。 so once it's set。

 the state never changes， but the thing is it's dependent on this kind of random event of which which is going to switch first。

 one of them will switch first， even if it's only by a tiny amount， and as soon as it does。

 then the circuit enters this stable state。So that's our basic building block for a memory circuitrcus。

 something this is a tiny circuit， the tiniest that we can imagine that remembers something。

 it remembers which one switched first。What we're going to do is add some control。

 so we control which one switches first， but once we've done that。

 we're going to take advantage of the fact that the circuit remembers。Now， this is the main feedback。

 like 99。99% of the feedback in our circuits are in little tight things like this。

 little memory bits。And the reason is that if you have bigger feedback loops。

 you can get unpredictable behavior so here's the same thing extended to three switches that block one another and again the state is determined by whichever one switches first but it's not stable these switches keep blocking each other and switching around and goes in a cycle that's called a buzzer and actually if you build your switches with relays。

 the physical electromagnets we talked about last time it actually makes a buzzing sound and actually old doorbells or an old sounding buzzers is exactly that it's just a relay turning on and off through a not stable cycle like this。

So because of that kind of behavior， we're going to stay away from long feedback loops。

 or at least make sure we have very tight control over long feedback loops。

The main way is to put all our feedback just in the two switch feedback。So there we go。

 that's the idea of memory and now what we want to do is control when the switch switches and that's what a flipflop is and we'll use the old historical terms。

 it's called many different types of flipfls initially but we're going to use what's called an SR flipflop and the idea is to add control lines to the switches to set the state basically determine which switch switches first。

So the R line， which is called reset， sets the state to zero， and the S line， which is called set。

 sets the state to the1。And the output is called Q， and that's always available。

So this is what it looks like， so you can see if the R line is on。

 then it's going to block the switch at the bottom from switching and then the state's going to be zero。

 that's just as if that switch switched first。And by contrast。

 the S line and we'll look at more detail is going to set it so the other one as if the other one switched first。

 and it'll always remember that。If you look at these as components。

 it's two na gates that are interconnected， the classic notation is that it's called a crosscod nor gates。

 so two simple nor gates that are cross coupled， that's a flip flop。So just look at an example。

 so if r is up， so r in this example r is set to 1 and s is0， and you can see the r blocks。

 the power dot at the left， and that means the other switch the other power dot at the right is on and now even when we turn r off。

 then the power dot at the left is going to be blocked。

So it's as if the switch at the bottom switched first， and we kind of forced it by putting R on。

 and that means the output is zero。On the other hand， if we set S to1。

 then it's as if the switch at the top has switched。

 which connects the power dot at the left to the output， puts the thing in state1。

 and then even when S goes off， then it stays in that state。

We never put both RNS on at the same time， so we don't have to worry about that。

 then we're talking about which one goes off first and they have the same kind of problem。

So with the R and S line， we can control what value goes in to the feedback loop。

 and that's the essence of a circuit with memory。Now。

 there are some physical considerations that come into play here depending on the switch technology。

 so if the switches are really slow versus the delay but we're not going to worry about those。

 we're going to make sure that we're going to assume that we've got a difference in。

The switching time in the delay through the wires， it's sufficient that we don't have those kinds of problems in real life。

 you might have to worry about timing a bit， so I don't want to minimize those。

 but let's just abstract them away。Because it does depend on the technology。

So we're going to assume when r goes1， then we set it to zero， when S goes1， we set it to 1。

 and that happens pretty quickly compared to everything else。

So what we're going to do now is implement a memory bit that even gives us more precise control what we want to do is provide data value on an input wire instead of fooling with too much with the SNR controls directly。

And we're going to have a control wire for every memory bit that if that's the one that enables the actual change in the flip fl value。

 and then the flip fl value is always available as output。

And you know this is the reason that we don't need to worry so much about timing as we have these extra controls to make sure that things happen in the way that we want。

 and I'll talk a little bit about that a little later。

 but it's this one piece of operation that makes our circuits reliable。

 it's possible to make our circuits reliable in lots of technologies。

So if we want to set the value of our flip flop to one， then we put one on the input。

 and then we turn this right control wire on and usually we think of turning this on just briefly just enough to to get the flip flop to flip for a few gates and then we turn it off right away。

So now you can see with that right on and the input one。

 we and those two signals and then feed that to S， so S is going to be1 if and only if both our input's one and writes on。

 and when S is1， then the flipfl gets the value 1。And at the same time。

 the other an gate on the left has the second input is the opposite that's going to block。

 and so R will be zero always when the input is1。And then when right goes off。

 then the flipflop has its new value， so all we assume is that a quick right pulse gets the flip fl to change and that time is pretty small by comparison with everything else in the circuit。

And similarly with0 we do the opposite0 signal in is going to wind up with R being 1 and S being0 always。

 and when the right pulse comes on， which sets the flip fl value to0 and then even when right goes away。

 it stays 0。That's our basic unit of memory， a memory bit that operates in this way。

 you give it an input， give it a white right pulse。

 remembers that input value until the next time it gets a right pulse and the output value is always available。

Our computers our computer circuits are filled， filled filled with memory bits。

 as most of it is these。 So it's important to understand how they work。Again。

 we're exercising very tight control over what happens in the feedback loop。

 and that's how we get our circuits to be reliable。So here's an application of a memory bit。

 It's a circuit that's got just one memory bit in it。

 and we're going to use it to implement the clock that drives our computer。

So we have another assumption about the physical world。

 and that is that we can get a regular on off pulse from the physical world somewhere。

Even von Neuman needed this and imagined it in the terms of oscillations of some physical material。

 and we make two assumptions about our clock signal。

 first is that the duration of the time when it's one is just enough to trigger a flip flop。

And number two， and we'll talk about this a little more later is that the duration between pulses is pretty long。

 there might be lots of flip flops that have to stabilize and we assume that that duration between pulses is long enough for the longest chain of flip flops to stabilize。

Analysis of this is sometimes difficult and actually in real computers。

 what they do is make that interval very long to make sure the computer works。

 and then they make it shorter and shorter until it stops working and make it a little bit longer and then sell it to you。

 That's absolutely what they do。 build computers nowadays。Okay。

 so what we're going to do now is attach that clock signal to a memory bit。

And that is going to give us the signals that we need to get the fetch execute that we use to drive the computer。

So you can think of this physical clock as just the。

Minute hand spinning around and every time it hits that little triangle at the left。

 it makes a pulse and again， there's lots of ways we could do that。

And the clock itself in the physical world has a run control wire that starts the clock。

 So when you press the run button on the front of the computer， it turns on the clock。

 it starts spinning around and makes these clock pulses。

 There's also a halt control wire that stops it。So now what we do is so we get the run to start on the halt when it stops。

What we do is we take the output of the memory bit， what it remembers。

 and we take the output and the negation of that output。

 so right at the bottom we put a knot gate so we have two signals that we give out one called fetchch and one called execute and they're always the opposite of one another。

So our computer， when it's running， is either got fetch high or it's got execute high and the other one is zero always。

 they're absolutely the negation of one another， and then we take that knot signal and we feed it back in the input to the flipflop。

And so what's going to happen is that since the right enable line is fed by the clock pulse。

 every time the clock ticks， the flip flo is going to change its value。

It remembers what its value was the last time the clock tick and its changes to the new value。

 that one bit is what we need to implement the sequence of fetch and execute that control the CPU。

It's a very useful one bit， a circuit and one memory bit。

 it's a circuit with one that one little loop of feedback， it's quite useful。

We actually use a more complicated one where we want to add in the right pulses。

 so I might as well talk about that one now it's just a slightly more complicated version of this clock。

What we want is we want to have a fetch signal and then fetch right pulse so the fetch part of the computation。

 things happen， but nothing gets written until the right pulse happens and that right pulse is a short one that just gets flip flops to change and same with execute and to get that we just and our two signals。

To the fetch execute clock。 so the fetch right pulse is just fetch and clock and the execute right pulse is just execute and clock。

And that's what we're going to use to implement our Fe execute cycles。

 the ones that these signals are going to turn on control wires that change the state of all our components。

And this diagram is looks complicated but it's really just pointing out that there's going to be four distinct times in this clock cycle。

 which repeats endlessly where interesting things happen。 So fetch comes high。

 then some control lines come along。 And then fetch right happens。

 and that causes certain flip flos to change。Then execute comes high and certain control liness go on。

 and then execute right happens and certain flip flos change。

And that cycle is going to continue over and over and over again。

 and that's what's going to drive the changes in the circuit that implement instructions。

And all of this is made possible by a single bit connected to a simple clock。

But of course most of our memory circuits are more complicated， so let's look at registers。

 so a register is a bunch of bits so here's a four bit register and again our convention is to take inputs at the top and provide outputs at the bottom and to have blue control lines in the middle so we have an input bus in this example this input bus is representing the four bit values 0101 or maybe five and then those are available on the input bus butre they're just sitting there。

 they're not being used because the right control is off so we might have different values on the output bus。

 those are the current values of what's in the memory bit in this case 1100 which maybe represents 12。

And so if we give it a right pulse， then what's supposed to happen is the values in the input bus go into the memory bit and are available on the output bus。

So in this case， right is off， so now when we turn right on。

 then we get those values put into the memory bits and available on the output bus。

 and the implementation is quite simple it's just a sequence of memory bits just connected to the buses and the right pulse controls all of them。

And in Toy8， we have this is precisely what holds the address for the PC。

 a four bit register like this。We need an eight bit register to hold the current instruction。

 it's the same thing just with eight bits and our actual processor register R also is an eight bit register that's exactly like this。

So a sequence of memory bits connected with buses and a right pulse， that's a register。

 and that's three of the main components of our CPU circuit。

And then we can extend the same idea to get a memory bank so now we've got two to the n words in the case of toy 8 little I'm sorry little Ns3 because we have eight words in this example that we'll show right here。

 we're going to have a four word memory that are each six bits just so you can see all the gates。

And again， to emphasize that our design is parameterized just by really the number of bits in word in the number of words or the number of bits in the address。

So this exact same design is' going to work even when n is 30 or when in which case there'd be a billion words as when in this case when n is two in which case is four words。

 so we have to give inbits of address input that's over at the left。And then however。

 many bits per word， we have an input bus。And then the value of some word。

 the word whose address we give is the one that's available on the output bus， that's a memory bank。

Then we also have a right pulse and the memory bank has the property that when the right pulse becomes one。

 then whatever is on the input bus gets loaded into the selected word and its values available on the output bus。

 so it's a sequence of registers register sort of on each row。

 except that we use the address to select one of them to work like the register on the previous slide。

So here's the implementation， so for every memory word。

 in this case there's four words each with six bits， so we have W bits going across for each word。

And those are just memory bits just as before。 Now， over at the left， we have a decoder Dmx。

So that's remember if we take the address bits with those address bits and then there's a value that comes in that's the right enable so there's one exactly one pair of lines that becomes high that's what the decoder demux does for us and all the rest of those lines are zero that's why we call them selection lines。

 the address selects which part of the memory is going to be active in this case we say right enable is high so they're both one if right enable was off then the top one would be zero but either way only that word in this case the bits are 10 so word two is the one that's selected。

呃。And then what we need to do is as we've selected a word， we want its value。

 but we have to collect the output values， only one of them is going to matter for each bit position。

 the one for the selected word， so only one of them could possibly be one and so all we need to do is collect them together in an or in a big tall or gate that goes from top to bottom。

 and the contents of the memory bit with the select line。

 so that's a one hotms that we've used before， and those things then take the selected word right to the output bus。

So these are all components that we've seen before just put together to implement the memory that gives us the behavior that we want。

呃。And， of course。In Toy 8， this is going to be our implementation of our main memory。

So this example where you can see all the switches is 24 bits， so for Toy 8 it's a bigger， it's 16。

8 bit words， so that's 128 different bits。And the decoder DmX has 16 different gates because it takes four bits as address。

SoBut otherwise it's the same， it's got an input bus， it's got an output bus。

 it's got an address to select a word and it's got the right control signal。

 that's our main memory bank for toy 8。

![](img/6011aae7cd929f02b6f522581eeb05fc_2.png)

So again， a major component of the Toy8 computer。And again， if you implemented this circuit for toy。

 there would be 256， 16 bit words， wouldd be hard to see every switch for sure。

 but wouldn't really add much insight。So the input bus comes from the register。

 the output bus goes to the register in the instruction register。

 and the address bits come from the PC and we'll see how the memory connects up to the other components。

And again， your computer might have a billion bits。

 you you need an electron microscope to see them all， but the design is the same。

 so that's starting from the idea of simple flip flop across couple na gates。

 we get several of the main components of our toy computer。

 we get the clock that has one flip fl in it， one bit of memory。

 we get our registers and we get our main memory。

![](img/6011aae7cd929f02b6f522581eeb05fc_4.png)