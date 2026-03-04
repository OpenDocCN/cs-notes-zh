# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P47：47_11_04_程序计数器.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/2b644c04c90819d1d1d649e2901dba26_0.png)

Next， we're going to look at how to connect these components together and actually get them to change state in a controlled way。

 and as a warmup， we're going to look at the program counter， which is。

 as you'll see is kind of a mini computer。So the idea is to what we're doing is designing a digital sequential circuit in such a way that we have precise control over feedback cycles。

And so we've already described our interface， we have input buses。

 output buses and control signals in what we expect components to do。u。

Then the next step is to figure out the connections that we need from between components。

 one component to another。 and then we have to establish the sequence in which the control wires like the right wire are become one。

 those are the steps。 and we're going to as a warm up just look at the toy8 program counter or the PC。

 It's a little digital sequential circuit。 So a couple of things that we need。

 The first thing is we need it needs to increment， So we need a circuit to increment the PC。

 that's relatively easy。 And then the second thing is we have to consider what happens when we have multiple buses connecting to the same circuit。

And that's also relatively easy， but it takes a little bit more thought。

 So let's look at the incrementor。 Well， this is actually just an exercise in designing a combinational circuit。

We need to design a circuit to compute x plus1。 We could actually use a full adder and just feed in1 and X。

 but it's worthwhile to just start with a slightly circuit bill for this purpose just as an exercise in designing a circuit。

 So what we'll do is we'll just start with the adder idea。

 but we'll just forget about the y inputs and then set the carry in to one。

 So it's like you have a number x and you're adding it to0 with a carry in of1。

 So then these are our tables。 So over on the left we have the carry bits we have x。

 and then we have to figure out how to compute the next sum bit and the next carry bit。

 So carry bit now is just two bits the carry an X。 And then the only time that we have to carry a1 out is when those are both one。

 Well that's nothing more than the and function as shown in the true table at the left。

In the sum bit we have our two bits so if they're both0， the result is0。

 if one is0 and the other one， the result is1， if they're both one the result is0 with a carry the one and now if we look at that truth table that's just x or and so we're going to do the same thing as with an adder except with an and an x or rather than the majority and the odd parity and so that's our incrementer。

Just like the adder with a bus X at the top and and an X or where the carries carry through the same way as we did in the adder。

 and then the value x plus1 is always available at the bottom。

It's a nice exercise in doing a combinational circuit so that's our incrementor that's going to be a component in the PC。

 Now the other problem that we have to consider is what about having multiple bus connections in components so if we have component outputs that need to go to multiple other components well there's no problem with that we just use T connections just a wire comes through and we just connect to that wire it's got the same value the values on both of the buses are the same and we use that like the register has to connect both to the ALU because sometimes the register gets is one of the opera of an arithmetic operation and it also has to connect to the memory for a store operation。

But the other way if the inputs come from multiple other components that's a problem。

 so for example the ALU has to connect to the register because the output of arithmetic operation might go to the register。

 memory has to connect to it for a load instruction register has to connect to it for a load address but how do we do that connection the values on the those buses are going to be generally going to be different so how do we connect it so what we need is a selector switch for buses it's a busms and it's actually easy but it's worth taking the time to think about this concept because it really is a key thing in the design of a digital circuit。

So we're going to use a onehot Mway bus mug and all it is is M copies over the onehot bus mugs that we did the last time。

 so our interface is we have a bunch of input buses in this case we have three input buses and for each input bus we have a selection line and we have one output bus and again we're going to have the precondition that at most one of the selection lines is one and the output bus is going to have the same value as the selected input bus lines。

And so in this example there's three different values going into the threeway bus mus at the top right and they all have different values but in this case select two is one。

 so that's the bottom one， and those values are the one that are going to appear as the output of the bus mus which we use input to the next circuit。

 and again we take output back to input by staking around like that just to make it clear what's the output and what's the input and make it even more clear than the top bottom relationship。

 right left relationship we're going to stick to that to make it very clear where the buses are coming from and going to。

So that's the description of the bus mugs and we actually have two of these now again。

 as with all mues that we talked about before it's not that there's a direct connection from the input to the switched output that it would be misleading to say there's an electrical connection it's just that the signal is the same。

 whatever the 10 pattern and the input is the same as the 10 pattern on the output。And again。

 this is very easy to implement， it's just for each bit we just do our one hot mux for each bit extremely simple just ending the selection line with the corresponding bit line。

 only one of those selection lines is one， so then only one and then is vertical orig gateates collecting the results as always。

 so only one of the inputs to the orrgate is one， so it does the job as we've done in several other circuits。

So we're going to need this right away to implement the PC to select among two different inputs to the PC。

All right， so what's the interface for the PC so it holds an address。

 it's got an input bus we might have to load the PC from somewhere else in the case of a branch instruction。

 branch instruction we load it from the address bits of the instruction register and then it's got an output bus that's always available that's going to be connected to the memory to get the instruction out of the memory。

So our control wires are though that there's different things we might want to do。

 so one thing is we might just want to increment it when it's time to change its value。

 the other thing is we might want to load from the input bus when it's time to change its value。

 and then we have a right signal， whichever is up increment or load that right control line will cause the value to actually change。

And then it's a register， the current value is always available on the input bus。

So clearly it's going to have a four bit register inside， it's going to have an incrementer inside。

And now we have to consider the connections among those two components that we need in order to implement this behavior。

So clearly we need to go from the input bus to the register and it has to be a way to load the register from the input bus。

 we also have to go from the incrementer to the register once x plus1 is known that's going to go into the register at some point。

Then from the register to the incrementator， that's the number to increment and then from the register to the output bus。

 that's how we make output available。But the thing is that once we determine these connections。

 that tells us that we're going to need a bus mug because we have two connections to the PC register input and those might be different at different times。

 of course they'll be different， the value of the PC+1 is going to be different than the address bits of the instruction registered。

So that tells us we need not just those components but we also need a bus mus so the actual picture is this so we've got the PC register we know what that is we've got the incrementer at the top we know what that is and we've got the bus mus in the middle and we know what that is and then we can check the connections one at a time the input bus is one of the connections to the bus mus the incrementer so the bottom that's the output of the incrementer goes into the top increment of the bus mus those two match up with the increment and load selection signals for the bus mus so when increment is high it's the incrementer that goes to the output。

 when load is high it's the input bus that goes to the output。

The output of the bus marks goes the input to the PC register。

 PC register loops around to the incrmentor and also goes to the output bus。

So that's the complete set of bus connections and control lines for the program counter。

And with these connections and these circuits， it's going to have the proper behavior really。

 it supports two different control signal sequences。

 So that is if load comes up and then there's a right pulse Whatll happen is it'll set the。

take the value available on the input bus and store it into the PC registered。

 That's what happens when we have a branch instruction and that value is available on the output bus。

On the other hand， if increment comes up and then write， then it results in adding one to the value。

 the output of the incrementer goes through the busms into the PC and the right pulse happens。

 then the values in the PC register change。And in this case we have a long feedback loop back into the PC and that's a very important note。

 this is the reason we have the short right pulse， we want to get those values to change but we don't want to if we didn't have the short right pulse blocking the thing we just keep incrmining it only has the chance to change values during that very short pulse that is just enough to get a flip flop to flip。

So those are the two states and that's exactly what we want to support in our program counter in order to get it to do what we want it to do。

 we have to give it those control signal sequences we do something else if we leave right up for a long time we're going to get some unpredictable behavior so we have to arrange to do that and the art and science of designing sequences of pulses like this is really the heart of processor design。

And now we'll look at these same principles in the context of the whole processor。



![](img/2b644c04c90819d1d1d649e2901dba26_2.png)

![](img/2b644c04c90819d1d1d649e2901dba26_3.png)