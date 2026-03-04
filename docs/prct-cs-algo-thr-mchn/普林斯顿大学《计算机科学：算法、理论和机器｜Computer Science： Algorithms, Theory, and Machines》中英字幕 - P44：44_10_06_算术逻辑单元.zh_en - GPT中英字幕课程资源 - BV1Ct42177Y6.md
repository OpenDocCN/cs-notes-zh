# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P44：44_10_06_算术逻辑单元.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/34f1cbffc9ccddd47a68defad578834e_0.png)

The arithmetic logic unit is a big combinational circuit that takes a substantial part of the real estate of any computer chip。

 so that's what we're going to look at next。 So we're going to move up one more layer of abstraction and the basic idea is that our circuits are computers are organized as modules that correspond to the functional units of the computer。

 So we know we need a memory， we need a register， we need the PC， the IR in and the ALU。

 which does all the calculations。And those is not too many of those。

 and there are big circuits that are built up on smaller circuits as we've been doing。

We need to connect modules together with what's called buses and generally bus is one wire for every bit in a word。

 and that's how we propagate information between modules。

 and then we also have single wires called control lines that control the behavior of the circuit。

And we adhere to conventions to make it easier to understand what the circuits are doing。

 usually we put the bus inputs at the top and we connect to them at the left。

And we put bus outputs at the bottom and we run any connections out from the right。

But often these buses have to run all the way through the circuit because different pieces have to connect to them。

And then we have control lines that we usually do in blue that also run all the way through the circuits。

 so we'll see several examples of modules in the next lecture。

 but our first example is the ALU and again the whole purpose of these conventions is to make the circuits easy to understand our design rules are not our rules are not designed to make the most efficient possible circuits what we're trying to do is get you to understand how the computer works in just two lectures so we're going to remove as much confusing detail as we possibly can。

So that's what the ALU looks like。 it's a module that takes this is an eight bit ALU so it takes two8 bit input buses at the top and it's got an8 bit output bus at the bottom and it's got three control lines for each one of the functions。

 This one has three control lines we're going to emit the left right shifter circuits you can see those in the details and this is what the whole circuit looks like。

There's one circuit for each function， it computes all the values in parallel。

 so that's our adder circuit， our 8 bit adder， there's an 8 bit bit Y X or that's just using the X or from the pop quiz。

 one for each bit。And there's an eight bit and， which is just an end gate for each bit。

So those are combinational circuits， they're always computing the value。

 their function of the inputs。And then we have the control lines， but the question is。

 how do we do this selection for the desired output when the add control line is lit。

 we want to see the result of the ad circuit and when the X or is one。

 we want to see that one and so forth。And the answer is we use a small subcircuit or a little switch called a one hot mux which we'll talk about in the next slide and the purpose of that is to select the proper result and carry it down to the output bus so this is the full design of the calculator that sits at the heart of the computer and we can check off a very significant module within the computer and we'll have a couple more to do next time。

So the idea of a one hop multiplexer is that there's M selection inputs， M data inputs。

 and exactly one output。And there's a precondition that at most one of the selection lines is one。

Eventually these lines come up from a decoder， so we can be sure of that。

 but we're not going to consider all possible inputs。

 either they're all zero or exactly one of them is one。

And the function of the circuit is to just give the output the value of the selected input。

So for example， in this case， select input 3 is on data input 3 is 0， so the output is going to be0。

All the other data inputs are just ignored。If data input 3 is1， then the output will be1。

This is a very simple circuit to implement you can probably guess how it's implemented。

 We just add together the pairs of selection and data inputs at most one of the if all the selections are0。

 then all the outputs of those an gates is zero and then the output of the circuit is zero because it goes into an or gate but if one of them is one。

 then either the and gate will either produce zero if the data input is0 or one if the data input is1 and most one of those things will be one if one of them's one。

 then the or gate will produce one as output the very simple circuit， but it's useful and in our ALU。

 this circuit is embedded for each bit in the ALU the data inputs are the result of the operation either the add the x or or the n and the selection input or the selection lines that' are supposed to select the operation。

So it's just built with hand gates and a multiway ore gate。

 and this is just the example showing how the hand gates work for those cases。



![](img/34f1cbffc9ccddd47a68defad578834e_2.png)

So we use these in the ALU， as just shown in the previous slide。

 and they also play an important part in the main memory that we talk about in the next lecture。

Now again， it's important to note that this isn't actually seems like a switch。

 but it's not actually a switch， there isn't a direct connection from the input data to the output data。

 it's just that it has the same value we call it like a virtual selection switch and that's important to understand that because that's misleading to think that there's actually an electrical connection。

So that's our summary in this lecture we've talked about some combinational circuit modules that actually play each play a critical role in the design of our CPU circuit and we built this all up from starting with just the idea of a controlled switch in wires connecting switches。

Next time we'll talk about how to build registers in memory using sequential circuits with feedback。

 we'll talk about connecting modules and then about how to control the connections to make a full CPU like the one in your computer。



![](img/34f1cbffc9ccddd47a68defad578834e_4.png)