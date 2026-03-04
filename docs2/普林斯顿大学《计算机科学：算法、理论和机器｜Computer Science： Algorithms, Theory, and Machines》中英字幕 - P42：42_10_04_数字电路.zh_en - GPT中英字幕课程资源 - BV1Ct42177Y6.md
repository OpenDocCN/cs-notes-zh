# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P42：42_10_04_数字电路.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/09ee2c2c004fab2284dbd6d065613328_0.png)

With Boolean algebra as a basis， now we're going to take a look at how to build digital circuits。

This idea was developed by Claude Shannon at MIT in 1937。

 it was really an amazing connection between the idea of designing circuits in Boolean algebra that Shannon wrote actually as a master's thesis。

 a paper based on his master's thesis， it's been called probably the most important and also the most famous master's thesis of the 20th century。

It's a simple idea， but it's a profound idea， people were working with developing circuits for computation without the formal basis that Boolean algebra provides and getting into conceptual difficulty on all dimensions。

What Shannon's idea was that we can use Boolean Al to systematically analyze and synthesize circuits。

 and that's the way that computers have been built ever since Shannon articulated this idea。

So we're going to just move up from switches up to a second level of abstraction called logic gates。

And what we're going to do is develop circuits that implement boolean functions。So for example。

 if we have the boolean function not that's x prime that's the truth table we already looked at that in classic circuit design say before the 1970s and '80s and some people still use these kinds of notations that's with the circuit element would look like。

 we're not going to use those classic symbols， we're going to use a simpler symbol that reflects what goes on underneath which is actually our circuit so most of the times we're going to work directly with circuits that are built according to our simple rules and it doesn't matter how they're oriented we can take this thing and turn it vertical any way you look at it this is a single controlled switch if x is zero than the output x prime is connected to power it's one。

If x is1， then the output x prime is block from power， it's0。

 so that circuit implements the not function， and we use the word gate to refer to a circuit that implements an elementary boolean function。

So that's a simple proof of the two cases for the not function。So here's a two argument function。

 the no function and we looked at the true table for that one and that's the classic symbol for that again our symbol is going to be much more geometric its just the cover over our actual circuit and if you take a look at that circuit。

 if x and y or both zero then there's nothing blocking the connection from power at the left output at the right so the value is going to be1。

 but if either x or y or both are on then the output is going to be block from the power dot and the result will be zero that's an implementation of the no function。

And in similar manners we can do other Boolean functions， so or is x plus y。

 that's the classic symbol， and again we're going to use a geometric one where all we do is negate the output of aOR so that's little proof with circuits the or gate that's drawn in the end of the cover column computes the orR function and similarly for and we can use de Morgangan's laws to not both in inputs to aOR and from de Morgangan's laws that gives an implementation of the and function。

And there we can do other things with other Boolean functions and we're not going to focus that much at this level。

 our circuits are going to be based on understanding how the or function and the and function in various generalizations are implemented and we're just going to use those forms directly and we don't want to get too far away from the physical world because we only have a couple of lectures to show you a real circuit and we're going to skip the abstraction where we work with classic symbols like the one shown in our classic symbol column that are connected by wires that then have to be fit into the geometry in some way。

Our circuits are always going to be directly tied to the geometry and you can imagine these being built from the drawing by laying materials on substrates。

 as long as you believe in the power dots and you believe in the automatic switches which are just the terminating lines across the line。

 then you believe that we have gates， and from gates we're going to build quite a bit more。

We often do have gates with multiple inputs， but those are easy generalizations of these basic things。

 so we might have a multiway or gate that takes a number of inputs and computes the function of oring them all together and that value has value0 if and only if they're all zero otherwise it's one and in our under the cover representation you can see that if all of those inputs are zero then there's nothing blocking the long power dot and that's going to block the output and make it zero if any one of them is one then it'll block the long power dot and then leave the output free to be one so there's an example where the result is one and another example where the result is one if any input is one then the result is going to be one that's a multiway。

Orgate。And actually usually in our search， the only way can be zero if they're all zeros。

Usually in our circuits， we're going to orient those vertically。

 so you should be sure to learn to recognize something like that as a multiway or gateit。

We can also have multiway and gates and actually we're going to generalize them in a very specific and easy way。

 so an an and gate is going to be one if all the input values are1 or zero otherwise。

 and that's similar to the or gate or undercovers representation the only way that outputs one is if they're all one。

 if they're all one， then they block all the dots from blocking the long one that's connected to the result。

If any one of them is zero， then it's going to block the connection to the output。

 and so that implements a multiway and gate。And more generally if we have some of the inputs go through a not gate and others don't。

 it just implements a different function where the ones that don't go through a not gate are knotted in the function so this example this circuit illustrates u prime Vwx prime Y prime Z if you don't have a knot you put a prime so again there's only one set of inputs that's going to output1 and that's the set of inputs that ensures that the power dot at the left is not block from the output at the right so the ones that are not do not go through in not gate the input has to be0 the ones that do go through a not gate。

 the input has to be1。In any other set of inputs， something's going to get through and block the connection from the power dot left to the output at right and the result will be zero in this case we have six gates we can have two to the six different possible functions we can implement in this way just by including the not gates in the input or not actually a nor gate is a generalized end gate in this sense if we don't have any x's then the only way that thing is one is if they're all zeros and if there's any one in the inputs then it's zero so we could have called these generalized no gates but we're going to just consistently use n because we usually think of if we want to add another variable we're going to and in another variable where we put an x on it and those are going to be the basis for many。

 many of our circuits。So just a quick pop quiz， you want to be able to recognize the functions that these sorts of circuits compute。

 and it's very easy to do so with just a little bit of practice。

 So what Boolean function do these gates compute and what inputs is the output1。So again。

 if there's an X， then you don't have a not。 if there's not an X， then you do have a not。

 So this first one is U， V prime W， X， Y prime Z。And then from that boolean function。

 if it's not negated， you put one， if it is negated。

 you put zero and you get the set of inputs for which the output is one and if you want you can connect that you can check that those are the inputs of the ones that do not block the left the power dot left from the output at right。

So again， just practice this one is U prime VW X prime Y Z。

 and the set of inputs for which the output is one for that is 011，001。

Here's all the possible generalized dam gates for three inputs， starting with x prime y z prime。

 where the only inputs for which that is one is they're all zero。

 and then that's counting and binary and you can see the counting and binary in the pattern of x's in the circuits。

And the last one is X， Y， Z， which is one， if and only if all the inputs are1。

So be sure that you get the idea of how to read these gates， if you're not sure。

 just replay this slide as if it's flashcards because we're not going to label these gates from now on。

 we're going to assume that you can see what Boolean function gates like this implement。

So now we're ready for a useful combinational circuit one that's found in every computer is called a decoder so a decoder takes some input lines which is an address this example takes three input lines and it has two to the end outputs the idea is the input lines or a binary address that specify an output line so in this example the inputs are 110 which is a binary for6 in what's that doing is specifying that the sixth output is1 and not only that all the other outputs are zero so it's a circuit that translates from binary to interprets a binary encoding of values on wires to activate the particular address wire so how do we implement it well we just take our inputs and we feed them in。

to all possible to to the end generalize the end gates with n inputs and the only one of them is going to match the input address as we just look to every one of these gates takes the value1 for only one set of inputs and for decoder。

 it's the set of inputs that are found in the input lines that specify in binary。

 the output line to be lit up and all the other ones are zero。

So in the next lecture we'll see how we use a decoder to select words in our memory by and it uses the address bits of a toy instruction。

 we'll see how that works， but it's a very simple circuit that's based on the generalized and gates that we just looked at。

Here's a similar one that also is found in every computer it's called a Dmux or a D multiplexer and that's the same way it's got the n address inputs。

 but it also has a data input that's got some value say x and what the DmX does it also has two to the n outputs and what it does is the gives the address output line。

 the value X it's like a switch where we specify which line we want to get connected to x it's not actually an electrical connection it's got the same value it's like a virtual electrical connection and all the others are zero。

To implement that， we just use the decoder， but we add on anex to every one of the gates。

 so it's a very similar circuit to a decoder and a very simple circuit and we'll see the use of Dmuxes in the next lecture for implementing instructions where we use the op code bits of the instruction in the instruction register to feed into Dmux to activate control lines that implement the change of state change of state of the machine called for by the instruction and then we can combine those into a so-called decoder Dmux and that it has pairs of output lines and it's just。

Taking back the decoder output so that each pair of output lines， most of them are zero。

 but the one that's addressed， the top line will be one in the bottom line will have the same value as the data value X。

 just a combination of the decoder in the DmX and we use that to control the memory as youll see in the next lecture and these are all quite simple circuits to take inputs and use gates to get the appropriate function performed。

 but the really real power of Shannon's idea is that we can create a digital circuit that computes any Boolean function and let's look for example。

 at the majority circuit。And all we're going to do is just follow through the proof of the universality of and or or not。

 but in the context of circuits。So same way we're going to identify the rows where the function is one。

And then for each one of those rows， we're going to create a generalized end gate。

It correspond to the terms for which for that set of values is one and otherwise is zero。

 and then we just or all the results together it's same as we did before。

 but now we make a circuit where we use a multiway or gate to or all the results together。

 vertically oriented multi multiway or gate。That's a circuit that computes the majority function so here's an example where x and y are 1 and z is0 and the only way that this function computes the value1 is if one of those gates matches the input in this case is' the third one down which is one if and only if x and y are 1 and z is0。

 so that one has one is its output and that output blocks the power dot at the top of the or gate and means that the power dot at the bottom produces the output1。

 but it's just computing and or function if any one of those gates is one， then the result will be1。

So in this case，1，10， the input， and that's two ones and a0。

 so the majority function can compute one。And now we can use majority function as a component in our circuits and we'll represent it like this。

 it's kind of like think of it as a cover on the circuit where we have our inputs running through in our output computes the majority function。

And this works for any function here's odd parity， for example。 So again。

 just find the rows where the function is one， use a generalized hand gate for each one of those rows So 100 is x Y prime z prime or there's the generalized end gate for that that's going to be one if and only fx is1 y0 z0 and then the last one is an hand gate and then just or those results together using a multiway or gate。

You can easily see after looking at these two examples that you could implement a circuit for any boolean function at all and certainly if you take a test on this material you'll find yourself doing that for sure So here's our example where x is 1 y is 1 and z0 then that's not a odd number of ones。

 so none of those gates match the input so they're all put zero out so none of them block the powered dot at the top of the or gate from blocking the power dot at the bottom so it produces the result0。

And again， now having seen that circuit， we can work at a higher level of abstraction where we can just run our input lines through a blue box that computes the odd parity function It's really quite a profound ending that you can design a circuit that computes any given Boolean function we just have basic gates and we use not a nor gates to make these generalized and gates and we have wire and our method is to represent things with Boolean variables。

 construct truth tables， identify the rows where the function is one and immediately build the circuit by having a generalized and for each place where the function is one and then oing together the results。

It's a very profound idea that we can get a circuit for any boolean function if we have more variables。

 we have bigger generalized gates， we have more that are one。

 we have lots more inputs into the or gate and so forth。

 but just the concept that any boolean function that you can specify you have a circuit for is a very profound idea Now there might be more efficient ways to do it。

 and in fact we there's plenty of applications where we do not use this idea because we want to have a more efficient circuit that uses fewer gates or less real estate and we'll talk about that in just a minute。

So again， if you take a test on this material you'll be asked to design a circuit to implement a boolean function。

 so for example， what about the x or function again you just use the same rules。

 use the truth table for every entry where the function is one you use a generalized and gate in this case it's x is 0 y is1 or x is 1 y0 and then or the results together so that's a circuit for x or that now we can use in at a higher level of abstraction。

And someone might ask to design a circuit to implement the function of four variables where the number of ones is equal to the number of zeros or whatever。

 any kind of specification of a Boolean function we can build a circuit to implement it。

' it's a very powerful idea。So just a summary of where we are so far。

 we're familiar in software design with the idea of encapsulation and the same thing holds in hardware design our implementation is the circuit from wires and switches。

 we have an API which defines the circuit by its inputs and its outputs and controls that we'll talk about。

 and what we do is we encapsulate circuits the same way that we do in software。

 we build bigger circuits out of small ones just working with the definition of what the circuit is supposed to do and so far we've built a bunch of different circuits that actually we find useful in putting together to build the arithmetic unit。

 the CPU of our computer。 the idea of encapsulation or building layers of abstraction is essential in this process。



![](img/09ee2c2c004fab2284dbd6d065613328_2.png)

![](img/09ee2c2c004fab2284dbd6d065613328_3.png)