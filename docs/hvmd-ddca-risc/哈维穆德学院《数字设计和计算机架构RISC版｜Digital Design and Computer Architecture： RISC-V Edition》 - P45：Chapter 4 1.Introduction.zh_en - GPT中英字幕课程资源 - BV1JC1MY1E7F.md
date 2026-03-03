# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P45：Chapter 4 1.Introduction.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

In this chapter， we're going to talk about hardware description languages or for short HDLs。



![](img/12d3c70d9e4c2a162d3bbdb172f7cad9_1.png)

Hardware description languages allow us to describe logic。

 both combinational and sequential logic using a language。

 and so we'll talk about how to describe combinational logic， how to describe delays。

 and that's only in simulation。Sential logic。Comation logic using what's called an always block。

Blocking and non blocking assignments， finite state machines， parameterized modules and test benches。



![](img/12d3c70d9e4c2a162d3bbdb172f7cad9_3.png)

![](img/12d3c70d9e4c2a162d3bbdb172f7cad9_4.png)

So HDLs allow us to specify logic functions。It's a computer aid design tool or CAD tool that will produce the synthesized gates。

From the description language that we use。Most commercial designs today are built using HDLs instead of schematics。

Two leading HDLs are system Bar and the HDL System Bar was developed in 1984 and was simply called Vlo and became an IEE standard and it was extended in 2005 and is now called System Barlog。

TheHTL was developed in 1981 by the Department of Defense and is also an IEE standard and was updated in 2008。

So we first describe our circuit in the HDL。Of our choice。

 we're going to show how to do it in system B and then we can simulate our circuits。

 we can apply inputs and then check the outputs for correctness and this simulation saves millions of dollars by debugging it before the circuit is put into hardware。

And then we'll synthesize the circuit， which transforms HDL code into what's called a net list。

 which describes the hardware， the gates， and the connections between the gates。So this is very。

 very important， this is why it's in red， hardwares description languages are not a programming language。

 so whenever you describe a circuit in an HDL， it's important to know what kind of hardware you expect to be synthesized from the HDL that you wrote。

So if you think of it just as a software language， you'll get yourself into trouble because you'll produce hardware that either doesn't work or is so big that and necessarilyces big for what you need so again。

When you write your HD， think of the hardware that you expect。For it to produce。

So there's two types of modules， behavioral module and a structural module。

 know the modules have inputs here we show A B and C's inputs on the left and an output why so they have an interface。

 but the difference between these two types of modules are the behavioral modules describe what the module does。

 so it describes the behavior of the circuit but not how the components are put together。

Structural modules， on the other hand are describe how the modules are put together。

 so build from submods。And typically the lower level modules are behavioral and the higher level modules。

Put those lower level behavioral modules together in a structural way where we have a bunch of sub modules that we instantiate and connect together。

So here's an example module declaration and system Bar。 We can see here we have the。Name。

In this case， we called it example。And this keyword module says， hey。

 the next thing that's going to happen is the module name。

 so we have module example that tells us what the name of our module is and now we have our inputs。

In this case， A， B and C， and we also have outputs， in this case we have one output， output Y。

So if we were to draw a black box of our system， this is what it would look like。

And the other last thing that we need to have for module declaration is this keyword end module that says。

 hey， that's the end of the module， and then we'll put some。Module body。

Stating what the function of that module is， and we'll talk about that next。

So here is a behavioral system Bar module。 And so we've， you know， we have our interface and the。

Module， keyword and name example， the end module keyword。And now we look at the body of。

Of the module。 So what the function of the module is。 So in this case， it's a sum of products。

 So y equals tilde a means not a。This ampersand sign。Means， and。

And then we have a not B that's tillil a B and not C。And this vertical sign means or。

A and not B and not C。 another or。你。And。B bar。And see。And so we've used system ver。

 this language to describe what the behavior of this circuit is。

 we haven't said a hey instantian angate and an orgate。We actually let the synthesis tool decide。

 well， how do you want to implement those in gates？And so after we've written our system V module。

 we can simulate it and we can see A， B and C here are inputs。And then we have our output， why。

And we can see， well， let's see， A， B， and C are 0，0，0 to start。And we see that in fact。

 we get a1 here because of this term， not A and not B and not C， we expect our output y to be 1。

When our inputs are。0ero，0，1。We expect our output to be zero， because。

None of these terms would force a one in that case。One of those product terms。

And so we can continue onward， you know， again， time is in the X axis increasing to the right and the values。

Are here in the vertical direction。ABC and the output Y， we have 0，0，0。0，0，1，0，1，0，0，1，1。

100 on A B and C 101110 and finally with our last value of 111 and we can probe through simulation and see what our output y is and if it's not what we expect。

 we can go back and change our system B to make it correct to correct it。

And then the next step is we synthesize the system V module and the tool， the cens tool turns our。而。

Module into gates。 And so we can see that it turned it into y equals。There's our。B bar。Sar。We。A。

And B bar。And this is case sensitive system barrel is case sensitive， so I。You know。

 even better as it would be to put those in lower case。So we kind of recognize that。

That case sensitivity， like equals B bar， C bar or A and B bar。 And here's the。A and B bar。

And so we look at what we wrote up here。A signed statement， we assigned the output y some value。

 and we notice， hey， actually that's different than what we wrote or is it。RightThis is this tool。

He's combining and said， oh， hey， these terms I can combine into B bar C bar， right。

 reduced the terms and then said， oh， and actually these two terms。last two terms。I could combine。

And。yi。B板。And so the synthesis tool won't always minimize the equation but。In this case， it did。

 it was easy， and so we noticed that hey。Our circuit a little bit different than what we describe。

 but it's the function is the same。 and it used a minimum number of gates to。

To produce that function。So some system fairs， syntax rules。System Bar is case sensitive。

 and this is where a lot of people get into some errors that they can't figure out is。So for example。

 the signal reset with a lowercase R is different from the signal reset with an uppercase R。

And so be careful with that。Those are two different signals because system very is case sensitive。

 no names can start with number， so for example two mus would be an invalid name because it starts with a number two。

Ms too would be valid， but not two mus。White space is ignored and we can write comments and should in our system very。

 a single line comment。Ass two slashes at the beginning of the line and multiline comment。

Has a slash and a star to begin it and a star slash to end that。That comments。

Here we have an example of a structural system fair module， so this module Nand3。

Is a structural system error module。 and we can see that well， it still has this interface。

 ABC and Y。 So if we。D a picture of a black box， ABC inputs， and the output Y。And now we notice。

 well。Two things。First there's this signal called N1。

 so logic indicates that it's just a signal and it's an internal signal called N1。

 and we instantiate inside of this module， we instantiate an andgate。This three input and gate and3。

And connect its output so we can see that order。A， B and C happen to be the same names here。

And the output is connected to this internal mode， so the fourth。Interface signal， Y。

Its connected to N1。 So we have A， B and C。 Here's our and。3。Module that we've instantiated。

And now we connect the output to N1。An internal signal。And then we instantiate a second module。

 this inverter module， I and V， and this is the name of the module and this is the instance name。

 so inverter is the instance name。We'd have inverter one， inverter two， inverter 3。

This has to be the same。As the module name。But then the instance name can be you know our cheeseing。

Can't start with a number though。So then we have our inverter and we instantiate。

Add and connect the input。To N1。 So again， the same order， this input is N1。

 and then the output we connect to y。This is our。Inverter module。

So this module is structural because we've instantiated these submods， in this case。

 this and three module， three input an gate and the inverter。And connected them。You know。

 internally inside this module。Using this internal。Signal， and one。It is not an input or output。

 It's just an internal signal。

![](img/12d3c70d9e4c2a162d3bbdb172f7cad9_6.png)