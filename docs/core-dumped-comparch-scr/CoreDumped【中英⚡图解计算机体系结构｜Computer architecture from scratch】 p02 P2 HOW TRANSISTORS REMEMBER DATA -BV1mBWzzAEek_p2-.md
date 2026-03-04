# CoreDumped【中英⚡图解计算机体系结构｜Computer architecture from scratch】 p02 P2 HOW TRANSISTORS REMEMBER DATA -BV1mBWzzAEek_p2-

This video was sponsored by Codecrafters In the previous episode。

 we learned how transistors can be used to create more complex components， such as adders， decoders。

 and even a basic arithmetic logic unit， but we didn't cover how computers remember information。



![](img/5eae9e45f834c78afc749c2606320cb0_1.png)

![](img/5eae9e45f834c78afc749c2606320cb0_2.png)

So hold on to your seat because in this video， we are going to create memory from transistors。

Hi friends， my name is George， and this is Core Dumped。

Remember you can find me on social media and now also on Twitch。

A few years ago I created a tool in Java to help people learn how CPUs work Now I'm planning to rewrite it in JavaScript so you can use it in your browser。

 I might stream the process which you might find interesting。

 personally I feel inspired because I can finally say I'm like the Prime agent。

 a guy without a fanang job streaming from South America。



![](img/5eae9e45f834c78afc749c2606320cb0_4.png)

![](img/5eae9e45f834c78afc749c2606320cb0_5.png)

So far， we've learned how to use transistors to create logic gates。

 and then combine logic gates to achieve more complex behaviors。

 with inputs and outputs typically flowing in the same direction， meaning signals move forward。

But when discussing memory， we're referring to the ability to retain information。

 so we might instinctively think about what occurs when we take an output and connect it back to the input of the circuit。

Let's examine the behavior of an or gate in this situation We establish a default state where everything is off remember。

 the output of an or gate is zero if and only if both inputs are zero。

 when we set the first input of the gate to one， the output changes accordingly。

 and for a brief moment measured in nanoseconds， the circuit looks like this。

 but because electricity moves extremely quickly， this output value propagates back to the input almost instantly changing the second input to one。

And now， with the second input of the orgate set to1， the output remains one。

 regardless of the value we set for the first input， as long as the transistors are powered。

 of course， so in other words， this circuit is remembering that the output was set to one at some point。

With the an gate， we can get something similar， recall that an an gate outputs one only when both inputs are one。

If we start from this state and then change the first input to zero。

 the output will become zero again for a brief duration， the circuit resembles this configuration。

 but the output immediately propagates back to the second input Now with one of its inputs permanently set to zero。

 the gate will consistently output zero， regardless of the value we set in the other input。

 thus in a sense we could say the circuit remembers that its output value was set to0。

Now we have two circuits， one capable of remembering a0 and the other capable of remembering a1。

 however， individually， they are not particularly useful because what we need is a circuit that can remember either a 1 or a zero。

 not just one of them。Intuitively， our next step is to attempt combining both circuits and observe the outcome by default。

 the circuit looks like this。The value held by the circuit depends ultimately on this and gate。

 in order to get an output of one， we can set both inputs to one。

 and since the output goes back to the or gate， we can reset the first input back to zero without changing the output。

 but not the second input because it goes directly to the and gate。

Let's add an inverter to the second input and see what happens。By default。

 the circuit looks like this Now with this arrangement， if we set the first input to one。

 the output of the an gate will indeed be one， because this inverter ensures that the other input of the an gate is one。

 even though the second input of the circuit is 0， the output of the and gate directly connected to one of the inputs of the or gate ensures that setting the first input back to0 will still retain the value of one in the output。

Similarly， if we set the second input to1 while keeping the first input at zero。

 the inverter will cause the and gate to output zero。

 and once again the output feeding back to the input of the or gate will make the circuit maintain a value of0。

 because even if we set the second input back to zero。

 the and gate needs its two inputs to be1 in order to output1。

 so it will retain a zero in the output instead。In other words。

 this circuit can remember one bit of information， whenever we need to determine the current value held in the circuit。

 all we need to do is read the value from this wire。And there we have it。

 we've successfully created memory。We can encapsulate this circuit within a box that we'll refer to as an and or latch。

The first input allows us to set the stored value to 1。

 while the second input allows us to reset the stored value back to zero。Unfortunately。

 with this setup， things get a little weird when we set both inputs to one at the same time。

I encourage you to explore what happens when you attempt to do so short answer。

 it doesn't make sense to try to set the stored bit to one while simultaneously resetting it back to zero。

If we desire a more intuitive mechanism， we require additional circuitry that enables us to specify which value we want to store using a single input；

 After all， a single wire can transmit either a1 or a zero， right？Well， yes。

 but there's a complication。As soon as the input changes， the output value changes as well。

 so it no longer fulfills the function of memory； instead， it simply outputs the current input value。

To address this issue， we introduce another input that we can activate whenever we wish to set the value being remembered。

We'll name this new input as write enable with the addition of a few extra logic gates。

 we can achieve a more useful behavior。When the right enable input is set to zero。

 the value in the data signal is completely ignored and nothing will happen。However。

 when the right enable input is set to one， the circuit will retain whatever value is being passed to the data input in this example1。

 and the value will persist even if we set the inputs back to zero。Later。

 if there comes a time when we need to overwrite the value stored in the circuit。

 all we have to do is activate the right enable signal while inputting the desired new value we wish to store。

 in this case，0。As long as the transistors that make up this gate are connected to the current。

 the value will be remembered。One more time， we can abstract this circuit into a component known as a gated latch。

And before continuing， I just want to clarify that there are several other ways to create latches。

 what I'm showing you here is not the only way to create circuits capable of remembering information。

A gated latch is capable of storing one bit of information； if its right enable input is set to zero。

 no action will occur， but if the right enable input is set to one。

 it will retain whatever bit of information is passed through the data input。

With just a single bit of information， we can represent basic data like1 or0， true or false。

 or simple distinctions like black or white， but that's it， nothing too sophisticated。

 if we aim to represent a broader range of numbers or a larger set of colors。

 a single bit becomes insufficient。We'll discuss the solution after a quick message from Codecrafters If you like watching content on this channel。

 I'm sure it's because you love understanding how things work If you've ever wondered how your favorite tools like Git Redis。

 Docker， DNS servers and even databases like SQite work internally there's no better way to learn than to build all those tools by yourself Codecrafters offers challenge-based courses that will guide you through crafting these tools step by step and the best part is that you can choose the programming language you want to use so you are not only learning about these tools。

 you are also improving your skills with the programming language of your choice remember one of the best ways to become a better developer is by building projects if you are interested and want to support me you can sign up for Codecrafters and choose the plan that best suits you using the link in the description below。



![](img/5eae9e45f834c78afc749c2606320cb0_7.png)

![](img/5eae9e45f834c78afc749c2606320cb0_8.png)

One single bit of information is not really useful。

 but we can use multiple latches to expand the range of values we can store， for example。

 to store one bite of information， we can employ eight latches and combine all of their right enable inputs into a single input that we can use whenever we want to override all of the individual latches at the same time。

A collection of latches interconnected in this way is known as a register， in this example。

 an  eight bit register。If you've seen other videos on my channel。

 you've likely come across the concept of registers。In previous episodes。

 I've discussed various types such as general Pur Regs， the instruction register。

 the address register， and the stack pointer。Registers are often likened to variables integrated directly into the hardware circuitry。

 which is a solid analogy， although somewhat abstract。Ultimately。

 they all consist of logic gates composed of transistors。

 interconnected in a clever manner to retain values。

The primary challenge with registers is their demand for numerous wires；

 the quantity of latches within a register determines its length， which can vary。

Registers come in different sizes， however， larger registers imply an increase in both inputs and outputs；

 for instance， achieving a 1 gigabte storage capacity would require a big register with millions of wires for data inputs and outputs if we want to remember bigger amounts of data。

 we need another solution。Instead of arranging latches in a linear array。

 we'll organize them into a 4 by4 matrix， totaling 16 latches our task now is to establish a method for identifying each one to accomplish this we'll utilize four wires for columns and four for rows by activating a single wire in both the column and row we can pinpoint a unique latch in the matrix if we think about it。

 this mirrors the process of locating addresses on a map where streets and avenues are typically numbered so we can say each latch in the matrix has an address。

Next we need special circuitry to activate these wires in the described way。Fortunately。

 we've previously explored decoders， a decoder when given an input activates only one of its outputs。

 for instance， inputting 00 activates output 0， inputting 01 activates output 1 and so forth。

By employing one decoder for rows and one for columns。

 we can input an address to select a specific latch in the matrix； for example。

 inputting 0000 activates the first output of each decoder。

 inputting 0001 activates the first output of the column decoder and the second output of the row decoder。

 thereby selecting a different latch in the matrix。Each latch possesses its unique address。

 which gives rise to the term memory address。Now that we can identify each latch in the matrix by its address。

 our next step is to devise a method for both reading and writing its value using the fewest wires possible。

We can start by adding a few extra components to each latch so we can use a single wire both as input and output To do this。

 we create a new input to let us toggle between reading and writing to the latch。

Activating the read enable signal configures the data line as an output Now someone might ask in the comments about the output signal feeding back into the input of the latch during reading this is not a problem since the right enable signal is inactive。

 thus disregarding any input。When the read enable input is off。

 the transistor prevents the signal from reaching the output。

 allowing the data line to serve as an input。With the data line functioning as an input。

 we can set the right enabled data to one， overriding the current value stored in the latch。

All latches within the matrix can be modified in this manner。

 having the required number of data wires。Instead of 32 wires， 16 inputs and 16 outputs。

 we only need 16 wires that can be toggled using the write En and read enableable inputs。

But we can take this further。By connecting the data lines of all latches to a single general data line。

 the write enableable input of each latch to a single write enableable line。

 and the read enableable input of all latches to a single read enableable line。

 we can set the value of all latches in the matrix without employing 16 data input wires and 16 right enable wires。

Making all the latches remember the same value is not the behavior we want though。

 we need each latch to remember its own value； Fortunatelyly we are almost there。

 because we already know how to use decoders to activate the cables intersecting precisely where each latch resides。

We can use the trusty old Annegate to make some clever modifications to ensure that the write。

 enable and read enable signals only reach the intended latch specified in the address input。

As soon as the address input changes， the angate obstructs any passage of input signals through this point。

 so in this example， even though the data input of the latch is set to zero。

 the latch will retain the value 1 in its memory because its right enable input is zero。

When all of the latches are connected in the same way， we get this。Beautiful， isn't it？

Let's see the circuit in action。Setting the right enable input to one allows the signal to traverse the matrix。

 yet it won't reach any specific latch due to the and gates blocking its path。

For the signal to target a particular latch， an address must be provided。

 prompting the decoders to activate one wire each for the columns and rows。

 the Sole and gate producing an output of one， thereby enabling the signal to flow to the latch is where the active outputs of the decoders intersect。

 that's why this latch just changed its value from1 to zero。

 as dictated by the value on the data line， now utilized as input。

To revert the value of this latch back to one， we simply maintain this configuration while inputting one into the data line。

If the address input changes， the output of the decoders will change。

 causing the activated outputs to intercept at a different location。

And the write enable signal will exclusively target that specific latch。

 thereby overr its value with the data passed through the data line。

If we intend to read the value of a specific latch。

 we supply an address and activate the Readenable signal。

 this will make the signal traverses the matrix， but exclusively targets the latch specified by the address。

 making the data line act as an output。And this is how we read the value any specific latch in the matrix is currently remembering；

 it's noteworthy that the value of the latch being read is propagated throughout the matrix。

 directly reaching the input of all other latches。Since none of the latches in the circuit have their right enable input activated。

 this value remains disregarded， so the value contained in the other latches won't be overwritten。

Okay， what you see here is actually an oversimplification。

 and even so this is starting to get too complicated。

 I might have gone too far this time so let's abstract all of this with the address input。

 we can select any of the internal latches by using the read enableable signal。

 we make the data line output the current value of the selected latch。

 conversely if we use the right enable signal， we can override the value in the selected latch using the data line as input。

Now we are still dealing with single bits， you probably already know that the minimum data computers handle are bytes。

To store bytes instead of bits， we can use eight matrices。

 all these matrices will share the same address input。

 allowing us to select corresponding latches across the matrices using the same address。

The Read enable and W write enable inputs should also be shared as we want to read or write an entire byte。

 not just individual bits。Each matrix will have its own data line。

 providing access to any bit within the byte， for example， to write a byte to memory。

 we input all the bits that make up the byte through the data lines and then activate the right enable signal。

This action causes each bit of the bitete to be stored in the corresponding latch at the specified address in each matrix。

 the byte is now stored in memory。Later， if we want to read that byte。

 we input the address and activate the read Enable signal。

This causes the data lines to output the value of each bit that makes up the byte at that address。

When we write programs， we don't need to concern ourselves with the underlying electronic matrix etched into the hardware；

 instead we think of bytes as sequences of bits stored contiguously。

 thus we abstract this further and conceptualize memory as a list of bytes， in this abstraction。

 addresses aren't intersections in an unseen matrix but rather indices in this list of bytes。

This is called randomandom access memory， since we can point to any random byte in the list by providing its address。

To simplify things， we can define these sets of wires as a bus。

 the width of the address bus determines how many bytes we can handle， for example。

 with an eight bit address bus using two decoders each capable of controlling 16 different outputs。

 we can locate any of 256 bits within the matrix。Generally， if the address bus has n inputs。

2 to the power of n bytes can be managed， for instance。

 a 32 B wide address bus can address 4 billion bytes。

 which explains why 32 bit computers can only handle up to 4 gigabytes of RAM Finally。

 keep in mind that the type of memory we have learned about today is known as static RAM。

This type of memory is very fast， but all these logic gates require quite a few transistors。

 so the production cost is higher， it turns out that those small memory cells in the matrix can also be achieved using a single special transistor called a MosFt and a capacitor。

 it is cheaper to produce but it is slower than static RA。

 I'll make a video comparing these kinds of memory。

And that about wraps it up for now in the next episode we will interconnect all the components we've learned about in this and previous episodes。

 this will help us understand how instructions like load， move， and store。

 work at the hardware level to make data flow between components。

So make sure to subscribe because you don't want to miss it and if you enjoyed this video or learn something。

 hit that like button， it's free and that would help me a lot see you in the next one。



![](img/5eae9e45f834c78afc749c2606320cb0_10.png)