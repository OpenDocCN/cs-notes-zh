# CoreDumped【中英⚡图解计算机体系结构｜Computer architecture from scratch】 p06 P6 How the Clock Tells the CPU to ＂Move Forward＂ -BV1mBWzzAEek_p6-

This video was sponsored by Brilliant。Computers operate on a very simple principle。

 they run instructions one by one。Running each instruction requires several steps。

 fetch the instruction， decode it， and execute it。But the question that often puzzles people is。

 how does the computer know to first fetch， then decode， then execute。

 and repeat this process in that order over and over again？



![](img/229aef04620937d5ea3a40ea2620caca_1.png)

The simplest answer to this question is the clock。A little device that produces an oscillating signal。

 which working in concert with a few logic gates， orchestrates the computer's step by step progression through each instruction。

Hi friends， my name is George and this is Core Dumped。

This video is not about how to implement clocks， but rather why the oscillating signal they generate is so important to computers。

There's a great video from Ben Eer on how to implement a clock like this one。

A clock signal can be thought of as a series of pulses。

 so it makes sense to think that each pulse prompts the processor to move one step forward。

 our goal today is to learn how， As always， there are multiple ways to approach this。

 and I'm not going to present the best one， but the simplest and most intuitive one I could think of。

 Let's start by analyzing the clock signal。First， it's important to note that clocks can generate many different types of waveform。

 but we focus on square waves because they take only two values。

 perfectly matching the binary nature of computers。Now。

 one aspect of the clock signal that is particularly important is the edges。

 the tiny portions where the signal switches from one value to another。

When the clock signal changes from  zero to 1， we call it a rising edge。

 and when it changes from 1 to zero， it's a falling edge。

The reason we aren't interested in the parts of the signal where the values remain constant is that nothing happens during those intervals。

 they're like dead zones where no events occur， and there's nothing for the system to react to。

But edges are different。For example， we can build circuits that can be used to detect them。

At first glance you might think this circuit always outputs zero。

 and and gate only outputs1 if both inputs are1， but since both inputs come from the same source and one is negated。

 it seems impossible for both inputs to be one simultaneously， but let's take a closer look。

 analyzing the input and the output over time。The input will be the clock signal when its value is zero。

 nothing happens in the circuit， it's stable and nothing changes， when the clock flips to one。

 the signal propagates to the left， but the inverted signal takes a bit longer to update for a very brief moment。

 measured in nanoseconds， the and gate receives a1 at both inputs， causing it to output a1。

A fraction of a second later， the updated output of the inverter reaches the and gate。

 turning its output back to zero。When the clock flips back to zero。

 the delay from the inverter occurs again， but this time it doesn't affect the output。

And nothing significant happens until the clock flips to one again。

The delay from the inverter once again causes the an gate to output one for a brief moment before the inverter corrects the output。

 dropping it back to zero。If we observe the output of this circuit over time and compare it to the clock signal。

 we see something clear。A quick pulse is generated at every rising edge of the clock signal。

In other words， we've created an edge detector， a rising edge detector。

There are other types of edge detectors， but we are not going to go down that path； instead。

 let's talk about flip flops， but first a quick message from Brilliant。



![](img/229aef04620937d5ea3a40ea2620caca_3.png)

There's one fact we all know about traditional studying；

 reading books might not always be the most effective method， but fortunately Brit is here to help。



![](img/229aef04620937d5ea3a40ea2620caca_5.png)

With Brilliant， you have access to dozens of different courses designed by professionals and specifically crafted。

 so you can interact with examples and improve your problem solving skills through small challenges。

Remember， one of the most important aspects of being a good developer is the ability to solve problems。



![](img/229aef04620937d5ea3a40ea2620caca_7.png)

The best part is you don't have to spend hours because Briiant is designed to help you learn a little every day through small lessons；

 even better， you can access it anywhere since Bri is available on your phone。



![](img/229aef04620937d5ea3a40ea2620caca_9.png)

You can access all sorts of courses， from math and data science lessons to programming oriented courses like thinking and code and how large language models work。

You can try everything Bri has to offer for free for a full 30 days and get 20% off in your annual subscription by accessing brilliantll。

org/coreded， or by using the link in the description below。



![](img/229aef04620937d5ea3a40ea2620caca_11.png)

And now back to the video， in my previous video on memory。

 we discussed that a latch is a circuit capable of storing a1 or a0。

 the one I'm showing here is made of two nor gates and is called an SR latch。

 which stands for set reset latch， the output Q with the little line in the top outputs the inverse of the value stored。

 while Q outputs the value stored， Activating the S input causes Q to output1。

 and this value is held even if we set the input back to0。



![](img/229aef04620937d5ea3a40ea2620caca_13.png)

The R input resets the value of Q back to0。When both inputs are zero。

 we're neither setting nor resetting anything， so the circuit simply remembers the last value。

Notice that setting both inputs to one doesn't make sense because we shouldn't be trying to set and reset the output at the same time。

 if we do attempt it， while both inputs are activated， both Q and it's inverted are forced to0。

 which doesn't make sense， they should never output the same value。And not only that。

 but another issue arises when we set both inputs back to zero in this situation。

 the circuit might end up holding either a one or a zero。

 depending on which input changes a few nanoseconds before the other， this creates uncertainty。

A variation of this latch exists， which is quite similar but includes an additional input called enable When the enable input is zero。

 the other inputs have no effect， we can only set or reset the latch by activating the enable signal。

This variation is known as a gated SR latch。At this point you might be wondering how all of this relates to the clock Well。

 if we use the clock as the input for the enable signal。

 we get a behavior where the levels of the signal 1 or0 determine whether the latch can be modified or not。

 but there's nothing new here， that's the expected behavior of a gated latch。However。

 if instead of using the clock signal directly， we place an edge detector between the clock and the latch。

 things get more interesting， because now the signal level doesn't matter。For example。

 at this moment， the clock signal may be1， but the edge detector is outputting zero。

What triggers the latch's right operation is the rising edge of the clock。

 the brief moment when the edge detector outputs one。

And that's the key difference between a flipflop and a latch while both can be used to store a bit of information。

 a latch is level triggered， while a flip flop is edge triggered。

While this particular flipflop triggers on rising edges。

 there are other types that trigger on falling edges。But this flipflop inherited a problem。

 the invalid state， when we try to set and reset at the same time。

Let's try to get rid of that problem to avoid over complicating。

 I'm going to start by abstracting the inner SR latch。

We can add a third input to the an gates and make sure they never receive the same value。

 so only either the reset or set input is allowed through， but never both at once。

If you think about it， the values of Q and its inverse are perfect for this。

 since they are always opposites。In this arrangement。

 the inputs are given new names J and K On a rising edge， J performs the set function。

 while K performs the reset function。But what happens if both J and K are activated at the same time during a rising edge？

Well it depends on the value currently stored， if the value is 1。

 only the K input will take effect resetting the latch， if the value is0， K will have no effect。

 but J will setting the latch。In other words， if both J and K are activated during a rising edge。

 the flipflop toggles its current value。A JK flipflop operates as follows， when only J is activated。

 a rising edge causes it to set， when only K is activated， a rising edge causes it to reset。

 and when both J and K are activated， a rising edge causes it to toggle its value。

This toggle feature is useful in various scenarios。

 but we are particularly interested in the following application。By permanently setting J and K to 1。

 by connecting them to the voltage that represents1， typically5 volts。

 the clock's natural oscillation causes the value to toggle automatically。

This creates a new signal at output Q that periodically alternates between two states。

 effectively generating a new clock signal。Looking closer。

 we can see that since toggling occurs only on the rising edges of the original clock。

 the resulting signal oscillates at half the frequency of the original clock signal。And with this。

 we can finally address our main problem， how does the clock constructstruct the CPU to follow these steps？

For educational purposes， let's assume that each instruction requires four stages， fetch， decode。

 execute， and a final step to increment the program counter so the next instruction is fetched in the next cycle。

What we need is an electronic mechanism that deactivates all circuits handling stages that are not currently active。

For example， in the fetch stage， the CPU needs to activate three wires。

The address registers readenable input to send its value to the memory address input。

The memoryory read enable input to make it output the content at the provided address。

And the instruction register write enable input to overwrite its content with the data coming from memory。

In the next stage， the instruction must be decoded。

 meaning that the wires used in the fetch stage should no longer be active； instead。

 we need to activate the instruction register's readenable input。

 allowing its contents to flow to the circuitry that decodes the fetched instruction。

That's essentially what we need to achieve， activate only the circuitry for the current stage。

In other words， we need circuitry that can select between multiple options。Fortunately。

 we've encountered binary decoders before。For those unfamiliar。

 a binary decoder is a circuit made from logic gates， when provided with a binary input。

 the decoder activates only one output， the one corresponding to the binary input value。

And now we only need to figure out some electronic mechanism that periodically increments the decoder's input。

 so the CPU can perform these stages sequentially。This is where the JK flipflop comes to the rescue we just learned that in this setup。

 each rising edge of the clock signal toggles the flipflop。

 producing a new signal at half the frequency of the original clock signal。

What if we take this slower signal and use it as the clock input of a second flip flop？

For our particular case， we'll use the inverse signal， which we get by using inverted Q instead of Q。

If you've been paying attention， the result shouldn't be surprising。

 the second flip flop oscillates at half the speed of the first one。

 or a quarter of the speed of the clock。We can continue adding as many flip flops as we want。

 each additional flipflop makes the signal oscillate twice as slowly as before。

This effect has many applications unrelated to our main goal today， but they're still fascinating。

Some of you may have seen Steve Mod's video explaining how a quartz crystal oscillator producing a signal oscillating over 32。

000 times per second needs to be slowed down to once per second for use in digital clocks and when I say chain of flip flops what I mean Well a flipflop is just a little bit of logic circuitry。

嗯。I'm not going to go into how a flipflop can be built， This is exactly what he was talking about。

 although he took a rather literal approach with the flip flops。Anyway， that's not our current focus。

 there's another pattern here， and I'll give you time to recognize it。Did you spot it， If not。

 let me help you。Consider the content of the four flip flops as a4 bit number。

 if you look carefully you can notice that every clock rising edge causes this number to increment by one。

When the maximum value Reable by a4 bit number is reached。

 the next rising edge returns the number to zero， where it begins incrementing again。



![](img/229aef04620937d5ea3a40ea2620caca_15.png)

We can abstract this circuit into a single component。Note that the clock isn't part of the component。

 as we might not always want the value to increment automatically， for example。

 replacing the clock with a push button allows us to control when the rising edges occur。As a result。

 the stored value increments only when we press the button。And just like that。

 we've created a binary counter。Now we can finally assemble all the puzzle pieces remember we needed a mechanism that periodically changes the decoder's input to alternate between different execution process stages。

 since we're dealing with four stages， we need a two bit binary number as input。

 so a binary counter made from two JK flip flops is enough。

And since we don't want to push a button every time we want our computer to advance to the next stage。

 we connect the binary counter to a clock， making the computer progress to the next stage on every rising edge。

And there we have it now we have a very basic idea of how a clock continuously instructs a computer to move one step forward。

Of course， because electronic clocks can be extremely fast。

 this also explains how computers can execute instructions at incredibly high speeds。

 without electronic clocks， computers would not be as fast as we know them。

 because the oscillating signal would have to be created in another way。

 probably with moving mechanical parts， which would be many orders of magnitude slower。

And if you learned something today， don't forget to like and subscribe。Until next time， I'm George。



![](img/229aef04620937d5ea3a40ea2620caca_17.png)