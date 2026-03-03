# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P65：Chapter 5 12.Counters & Shift Registers.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/0bb95405be87c71192aad9cc400ae82e_0.png)

Now let's talk about counters and shift registers。Counters increment on each clock edge。

 so your watch is a counter， let's going 0，12，59 and then it's going back to zero。

 so it's a mod 60 counter， but a counter increments on each clock edge。

And it's used to cycle through numbers。 So the example I just gave。

 or here's a 3 bit counter where it count starts at 0 and then goes to 7。And then。Goes back to zero。

So again， examples are digital clock displays， the program counter。

 which we'll talk about in the next chapter and chapter six keeps track of current instructions that are executing。

 so it says， hey， instruction zero is executing， oh now it's instruction one。

 now it's instruction two， so keeps track of of which instruction。

 we're on when we're executing your program。And here's the symbol of our counter， it has no inputs。

 but it does have a reset so we can。Reset it to zero。And has an ended output。And so it looks。

 you know， the symbol kind of looks a lot like a flip flops that doesn't have any inputs。

So here's our counter， how do we build this？We have an adder， right。

 we have an adder where we could say， okay。Well， here's an outer and。Well。

 what do you want to add together？SomeIts resolved want to add to one。

 right the endB representation of one。But can we， can we just do this， Can we just say， okay， well。

 I'm good。Well， we can't right， then we have a race， but we can put a flip flop in there。

And say okay， well here's a flip flop， that's a resettable flip flop， here's Q or output。And。

This is tied to reset。Clock。And then we。Feedback that Q output and add it to one。the next clock edge。

That increment value becomes a new value and so forth。And so here's a picture。

 remember this is the end bit representation of one， it's not just a single wire。

And so here's an end bit counter that increments by one。

 we could have counters that increment by different amounts。

We could have a counter the increments by four or some other number as well。

So here's a counter in Ver log forms is the。The systemem V idiom。Module counter。

 we have our clock and reset inputs and our single output Q in this case it's an eight bit counter。

And if。Alway it Pla edge clock if reset Q gets zero otherwise。It gets Q plus one。

And here's an alternate more of verbose version of the counter would have， again。

 our inputs and outputs are the same clock reset and Q。And we have a。Next Q。

 we're kind of explicitly showing the adder， a next Q internal signal。

Where we assign next Q equalsq plus1， we instantiate that adder。And then at Po edge clock either。

If it's reset is asserted， Q gets zero， otherwise。Q gets next Q。

We can also use counters to divide the clock。 So， for example， if we want to look at a blinking LED。

 if it runs as as fast as the onboard clock， typically at least 50 MHz or I won't detect that LED blinking。

 So we just slow down the clock in order to toggle the clock。 So let's take an example。

 So here's our clock signal。 And suppose we have just a 1 bit counter。 So here's a clock going 0，1，0。

1，0，1，0，1。And our our counter is going to increment on each clock edge。

 So let's suppose it's  zero here。 The next clock edge is going to be one， and it's going to add one。

ll back to 0， and then one。And so if we look at the cycle time here， here's our TC。

Our cycle time over our clock。And here's the output output of our one bit counter。

 and it has a cycle time of 2 TC or。Half of the frequency of the clock。

 And so for each end goods that we add， we get two to the end。

 a division of 2 to the end of the clock。 So， for example， a 3 B counter would have 0，0，0。0，01，01，0。

011。And so we can see that。This frequency at right every clock edge。

 you get  zero and another clock edge， you get one。 This takes2 TC。

 This one takes4 TC or divides the。Clock frequency by4。 And this one takes 8 Tc。

 So this three bit count。 If we look at just the most significant bit， it divides。

 it multiplies the clock period by 8 and divides。A frequency by aid。And so， it's useful for。

For dividing the clock。 so， for example， if we have a 50 meHtz clock。

 if we look at the most significant bit of a 24 bit counter our 24 bit counter。

 the frequency would be 50 meHtz divided by。Two to the 24， which is 2。98 hertz。

We can also use counters to produce digitally controlled oscillators。

 so we'll use the Nbit counter that we just talked about。

 but instead of adding one on each cycle we're going to add P。

 and so now the most significant bit of that counter。

 the most significant output of that counter will toggle at the native clock frequency。

Times p over2 the n instead of1 over2 the n。So let's say， for example。

 our clock frequency is 50 megahertz and we want to create a 200 hertz signal。

So we want to make P over 2 to the n equal to 200 divided by 50 megaHtz。So we can try n equals 24。

 a 24 bit counter and p equals 67， and we're going get the output frequency is equal to 50 megahertz。

Times。P， which is 67 over 2 to the N or 2 to the 24。And we got it。Pretty close， 199。676 hertz。

 we could also use a 32 bit counter。And get even closer so with a 32 bit counter and a P of 17，179。

 we get even closer to approximately a 200 hertz。A clock frequency。

So shift registers are also useful where we can shift a new bit in on each clock edge。

 so it looks like a bunch of registers right back to back registers here。😊。

But we have this input S in shift in or serial in。S stands for a serial input that we're going to shift。

So serial in， and then we also have serial out S out， where we're going to shift out some value。

So Q0， we also have these internal outputs， Q0， Q1， Q2， all the way up to Q sub n minus1 at the end。

And so， for example， we could， in time， shift over some value， give some value 0，1，1，0，1。

 something like that。 right， Over time， that zero is going to shift in and that's going to keep shifting over as the new bits shift in and we're going to get。

That value。You know。Let'lls do part of it， zero，1，1。And zero is waiting to be a good shift then。

And so we can actually turn this serial input into a parallel output。

 I can read those bits now and parallel off of those internal wires。

So we call shift register serial to parallel converters because it's converting again this serial input SN to a parallel output that I can read in my circuit。

And this is often useful for， so for example， chips where we have a limited number of pins are always limited。

 right we always need more pins than we have so these external interfaces to our chip。😊。

I can just use a single wire to over time or in series。

Shift in a bunch of bits and if I have a shift register in there I can then use those bits in parallel inside of my chip。

So for example， if I'm trying to set the value of a counter。

 I could shift in the value of it in series and then use that within my counter。

So another version of a shift register is a shift register with parallel load。

So let's look at this when this looks， you know， this part。

 if we took away the multiplexor and just fed S in here。This is actually just my。

regularular shift register if I didn't have that multiplexor in there and that load signal。

But now we may want to have the case where our shift register could also act like a regular shift register。

So when load equals1， we'll see what happens when load equals1 well。Into these registers。

 I'm actually just feeding。AVal D， my data into these registers。

 So it looks like a regular endbit register。When load is equal to one。But when load is equal to zero。

Now it's going to act like。A cereal。That that series input is going to get shifted in。

 so now it acts like a shift register。So we can we can use this in that that case I just talked about where we have a counter and usually we want it to act like a regular register right or counter that。

With。Part of our， I mean， our register that was part of our counter usually wanted to act like。

Just you know， part of that counter。 And so we'll use load equals one。But sometimes we want to。

 they want to shift in。And in the serial in input， the S in input some value into that counter。

 So maybe want to preset it with some value。 And so then we will we could make load equal to zero and say。

 actually， I'm going to shift in a value now I'm like just ignore what D is doing。

I want to shift in these values from serial the serial input。

So this is a shift register with parallel load that can either act as a regular regular register and it register when load is equal to one or when load is equal to zero。

😊，Acs like a shift register。And we often use shift registers or this shift register with parallel load to test chips。

 so give our register some preset value and actually you know all or most of the registers in a chip can be connected in series so we can load into all the entire registers of a chip with some known value using the serial input and then set load back out equal to one and it ignores the serial input and starts computing at that state。

Here's our system B idiom for a shift register with parallel load， so we have our inputs。

Clock and reset， and。Load and cere in。And we also have our D input when we're treating it like a regular register when load is equal to one。

And then we have our outputs， our parallel output Q， and our serial output S out。

And so here we have an asynchronously resettible。Should register。

So it reacts to reset going high if reset。We reset our register Q gets zero。Otherwise。

 we check if load is true， if load is true， then Q gets its inputs from D from the data input acts like a regular register。

Otherwise。Q gets well。The shifted value。Of Q。So。Instead of going from Q sub n minus1。

 we shift it left by one， so Qs sub n minus1 gets shifted out into S out and everything else shifts left。

K of n minus 2 to zero。And we shift in the serial input。



![](img/0bb95405be87c71192aad9cc400ae82e_2.png)