# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P2：Chapter 1 1.Managing Complexity Design Principles.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello and welcome to the next exciting installment of digital design。😊。



![](img/feaa4a2ccfc4f7d74b3b5ac957212ce6_1.png)

The topic of this video is the art of managing complexity。So our fundamental question here is。

 how do we design things that are too big to fit in one person's head all at once。

Engineers have a variety of techniques to address this problem。One is abstraction。

 another is discipline， and another are the three wise hierarchy， modularity and regularity。

Abstraction is hiding details， when they aren't important。So， for instance。

 if we wanted to understand how a computer worked。We could start with a quantum mechanics。Ultimately。

 there are some electrons moving around in a lattice of atoms。

Their positions and momentums are governed by quantum mechanics。

And we could solve the wave equation for each electron。

But trying to do that for vast numbers of components all at once is completely intractable。

So instead， we'll move up level of abstractions to devices。

Will define things called transistors that are made out of doped atoms， but that we can treat as。

Several terminals within a relationship of voltage and current between those terminals。

Moving up in abstraction， we'll get to analog circuits。

 So an analog circuit might be something like an opamp or a filter that has input and output。

 It's ultimately made of devices， but we don't have to worry about the exact arrangement of transistors。

 We can just call it an amplifier。Continuing up， will move from the analog to the digital domain。

 We could define logic gates。That。Take zeros and ones in and put zeros and ones out。

Then we could talk about logic built from logic gates。 So， for instance。

 an adder or a memory could be comprised of many logic gates。

 but we can treat it as a box with a relationship between input and output。

We can combine these adders and memories to make things like data paths and controllers。

 And that's the level we'll call micro architectureure。Going up from there。

 architecture is the programmer's view of a system。

 so the architecture of a computer would consist of the instructions that the computer can run and the registers inside the computer。

Next up， we could talk about operating systems， so we might talk about a device driver you could。

 for instance， open a device driver to access the keyboard and then read keys that were typed without having to pay attention to the exact pa of zeros and ones moving across buses。

And finally， up to the world of application software， where you can write programs。For instance。

 print something on the screen。Or play a video game or do some kind of calculation。And ultimately。

 those programs rely on all the lower levels of abstraction。

 But when youre writing Hello world to print something on the screen。

 most programmers aren't thinking about the wave equation of the electrons that are causing all this to happen。

So that's the notion of abstraction。In this course。

 we will primarily focus on the middle levels of abstraction from digital circuits up through architecture。

We'll look a little bit at devices to understand what's underneath the hood and we'll also get to some software。

We're going to begin working our way up in chapter 1 up from digital circuits and devices。

Chapter 2 and3 will develop logic4 and five as well。Then in the second half of the course。

 E85B we' begin with software and work our way back down， programming。

 then assembly language programming of architecture。

 and finally we'll meet in the middle with microarchitecture to understand how to build a digital system that runs the software。

Discipline is another very important concept。 This is the idea of intentionally restricting your design choices。

So at first， that seems counterintuitive。 If you are limited to a smaller design space。

 Why is it better。But a great example is the digital discipline。That will use discrete voltages。

 instead of continuous。As a result， design becomes much simpler。

 and we can build much more sophisticated systems。For example， with analog television。

We have continuous voltages coming in that might set the color of a pixel on the screen and any noise in those voltages cause aesthetic static。

With a digital system， each。Pixel is represented by a pattern of bits。

And we can introduce error correction。 So even if there's some noise。

 the bits will still be recoverable and will get a crystal clear picture。

 even in that presence of noise。So as a result， digital systems have replaced analog predecessors in so many different fields。

 and that's part of why this class is so exciting。Another technique for managing complexity is the three Y's。

 hierarchy， modularity and regularity。So hierarchy is。Recursively。

Deeccomposing a complex system into subsystems。Modularity。Hiss building systems， with well defined。

Function。And。Interface。Would say the things that are modular have no side effects。

Regularity is related to the notion of interchangeable parts。

So as another example of the three y's in engineering， let's take a look at the Model T for it。

Model teeth ford。Was introduced in 1908， and it was a famous early example of using interchangeable parts。

So prior to this car， most cars that'd been around for about 20 years were handcrafted by skilled tradesmen。

And they were very expensive as a result。The Model T introduced mass production on a moving assembly line that greatly reduced cost。

So Henry Ford laid out his manifesto to be able to build a car that an ordinary person could afford。

Let's see how the three ys apply。 So we'll start with hierarchy。We can think of a car as a whole。

Being broken down into components such as the chasis， the wheels， the seats and the engine。

Then we can recursively look at each component。 for example， the engine has cylinders。

 has a spark plugs， has an exhaust system， and it has a carburetor。We can continue recursively。

 look at the carburetor。 the carburetor has an air intake。It hass an inlet needle。It has a feed pipe。

And as a coupling that。So we have reduced from a very complicated car object like a car that we can't understand all at once。

Into simpler components such as a nut that we do understand。Next， let's look at modularity。

So the knife has a well defined function in interface。

The functions of the nut include holding the fuel line to the intake elbow。Preventing leaks。

And being inter easily removable。So that we could repair the system。The interface is standardized。

Has a standard diameter， a standard thread pitch， a standard torque。

So we can build a standard fuel line and a standard intake elbow held together by the standard coupling nut。

And if something breaks， we can replace any one of them without having to custom craft the others。

Regularity is the notion of interchangeable parts here。

 So we could buy the standard nut with its standard dimensions from any one of many suppliers。

And that will drive down cost。And increase availability。

Another famous example of regularity on the Model T Ford was Henry Ford's statement。

 Any customer can have a car painted any color that he wants。 so long as it's black。

By making all the cars black， all the parts became interchangeable。

 and it could be painted all at once。 And if you needed another part， you could swap it out readily。

So one of the key abstractions for this course is the digital abstraction。

Most physical variables are continuous， such as the voltage on a wire。

The frequency of an oscillation or the position of a mass。But in the digital abstraction。

 we're going to consider a discrete subset of these values to define our zeroes and ones。

One of the early examples of the digital abstraction was a mechanical computer called the analytically Engine。

This was designed by Charles Babbage in the mid 1800s。

 It's widely considered to be the first digital computer。

 but it was built instead of from electrical logics that do zeros and ones is built from mechanical gears。

 Where each gear had 10 different positions，0 through 9。

And you could turn a crank and the gears would interlock。And move each other。

 and they could cause the system to do things like addition and calculate tables。

So Baavch got this idea。 He was a mathematician in Britain。

 and he was very frustrated by the number of errors in tables of mathematical functions。And one day。

 he and a friend were looking at these errors and he said。

 I wish we could just calculate this by steam。And after some thinking about it， he realized he could。

 He could build a machine that would calculate the tables。Unfortunately。

 every time Babbage got close to finishing a machine。

 he would come up with a better idea how to do it even more elegantly。

 He'd abandoned the work he'd been on and move on to the next system。Also at the time。

Machning was nothing like it is today and building thousands of interchangeable precision parts that all mat it together was really pushing what the best craftsman of the day could do。

Finally， Babbage had a difficult personality， and many people had trouble working with him。

So Baavage worked on this for most of his life before he。I hadd funding cut off by the queen。

And he died with a system unfinished after spending 17000。

 That saw 17000 of silver back in the day enough to buy something like a dozen locomotives。😔。

And it left him with an unfinished machine that was ultimately melted down for scrap。So Babbage died。

 a bitter and broken man。But in the 1990s。Eineers revisited Baavage's plans。

 and with modern CNC machining， they were able to build the system from his plans and demonstrate that it actually worked。

And in fact， two copies were built。 There's a copy in the。

Computer museum in Silicon Valley and a copy in the Science Museum in London。And if you go see。

 you can actually see the machine。And it calculates these tables。So returning to electrical systems。

 system of 10 different gears is pretty touchy， it's much easier to only have to distinguish between two things。

 say two voltages。And nowadays， we can build transistors that are extremely small， extremely fast。

 extremely cheap。 They cost nanocent a piece。So that lets us build digital systems very easily。

We'll call our two discrete values，0 and 1。A 0 might mean false or a low voltage。

 A one could mean true or a high voltage。And these could be represented with all sorts of different physical quantities。

 but voltage is what we'll typically use。We also have the term bit。Which is short for a binary digit。

 That's either a0 or a one。

![](img/feaa4a2ccfc4f7d74b3b5ac957212ce6_3.png)