# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P39：39_09_05_模拟.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/85ebc5322df9b5e974b8a340bc4e031f_0.png)

Next， let's talk about simulation， which is a key concept in this realm。

Students asked this question all the time is toy real is there a real toy machine Well how do you think we debugged our toy programs Well we wrote a Java program that simulates toy that takes the actions that we expect the toy machine to make and the thing is and as you're going to see in a minute you could write a toy simulator。

 It's actually toys a simple machine， This is a simple program actually quite quite easy compared to other programs for other applications that maybe you've written。

And in fact， that's the way we designed toy was to take this Java code and continue refining it。

 you may find older versions of toys related to this court around all kinds of possibilities。

 but we just worked with this Java code and this is just to indicate that actually nowadays all computers are designed in this way。

 people write simulators for the new computer before actually building the computer。

And it brings up some interesting questions， so you have a system like Android or iOS is that do you consider that to be？

Real， there's a billion Android devices out there so in iOS similar and other systems。

 you consider those devices to be real there's no toy devices out there but on the other hand you say。

 well what about Java is that real， well Android runs Java。

 we could run our toy simulator on Android， so there's a billion toy devices out there。

 so toy is every bit as real as Java or Android？And that's quite a provocative question that we' just delve a little more into right now。

 First， let's take a look at this Java program to simulate toy。

What we're going to do is take the program， the toy program from a file named in the command line。

 and then use JavaScript standard in standard out for toy standard in standard out。

So here's an example where we have toy code to add the integers on standard In and all this code is to be loaded at Xlocation 610。

 this memory location 16 so that's the code， the toy code。

 then if there's data this is maybe the contents of the paper tape， then if we invoke our simulator。

 toy。 Java， the bycode is called toy。Then the first argument is the program and then the pipe take our input from data。

 text， this command will cause a simulator to simulate the operation that program。

 which is to add the numbers on data。 textex， and then the result of that goes to standard output。

 and it's sum of those numbers，00 F7。So let's take a look at what this code looks like。

 so we're going to start at Hex locationation 10 and we have a variable called PC which is our program counter。

 then we need 16 registers for toy and we'll just represent them in an array of size 16 called R and Java and same for memory we'll have an array of size 256 which will be the main memory。

Then we use an input stream to read from the file that's specified as the first argument。

And we'll just stay in a for loop as long as the input string is non empty， and we're less than。

Location FF will' just load the memory with the integer that's found on the input string now we use parsin the way we usually do in this case we have a second argument to parsson which just says that we're expecting the number there to be base 16。

 and that's all built into Java to change from those strings that we use to represent X numbers into integers and that's what we store in the memory。

And then what the simulator does is stay in a loop to read the next location。

 PC gives the address and the memory of the next instruction。

 we load that into the instruction register IR， which is just a Java variable。

 and then increment the PC。And then in the next two slides we look at the main function of the simulator which is to decode the instruction and then execute it and we'll look at those in the next two slides and that's the general structure of our program to simulate the toy machine and we'll look at all the code next so first thing is decoding this is kind of housecheing where people call it bitwaacking because we're tearing apart the instruction to look at different segments of it and extract those fields so that we can use them for later processing。

There's a simple technique called shift and maskask that works the same way in Java as it does in the machine language instructions for bitwise hand exclusive boringing and so forth。

 and after a few examples and you can read more detail in the book so say we want to extract the destination Reg D from1 CAB so that's what the instruction register looks like we're just looking at the right most 16 bits。

What we do is shift that right eight positions， so now the bits that we're interested in are the rightmost four bits。

 then we take the literal F0 xF which is41s and then we just and that against the result are shifting the instruction register right and the zero positions are all zero no matter what was in there。

 and then the one positions just copy the bits below the mask so that gives us our result which is the destination register C。

So the result of the bit wise and of the data and the mask is zero where the mask was0。

 it's the data bit where mask is one， and that's a basic technique that we can use to get all the information that we want。

So after we fetch and increment the instruction into the instruction register。

 then we can get the op code by shifting right 12 and ending with0xF we get the destination register that's the example that we just did we can get the source register by going four bits and then the other source by not shifting at all just masking off the for rightmost bits and then if it's an instruction that uses an address we need eight bits so we mask it with zero xFF and we compute all these things some of the instructions will use S and T some other instruction use adder but we might as well compute them all so that's the decode calculation that's bitwacking the toy instruction to get the information that we need to simulate its operation and then there's the execution so execution is the Java switch statement。

Each instruction dictates simple state changes， that's what the toy machine is。

 and all we have to do is change the values of the registers or the memory as dictated by the instruction。

So if the op code is zero， then we we just break out of our loop。

 but otherwise we use the op code and there's cases for each value of the op code。So if case1。

 it's an add instruction， then that means R of D gets R of S plus R of T and so forth for all the ame instructions。

In fact， these cases look very much like the documentation of the programmer's card for the toy machine。

 so that's a shift left that's a shift right load address just set RD E adder and that's a store load instruction and a store instruction an indirect load and store and then the branch instructions the branch instructions might involve testing the value of a register and might involve changing the value of the PC there's the case 14 and 15 instruction E&F or about implementing functions where we can jump to an address given in a register and we can save the current address in a register and you can read in the book about how to use those and that's it that's the state changes that are dictated by the。

Definition of what the toy machine is supposed to do。

So that's the complete simulator putting together the code， there's the load part， load the program。

 and then there's Stan a loop， there's the fetch increment， there's the decode。

 and there's the execute。The entire simulator fits on one slide， and in fact。

 that was our main design goal for Toy was to get the simulator to fit on a slide for this lecture。

Now actually there's a few things that we emitted， so R0 equals zero we have to put in standard in and standard out。

 we didn't put in this code， you need to check if the adder is FF and then go ahead and read from standard in or standard out if that's the case。

 there's some places where we didn't take care in this code where we have to do some casting and other things because toy is 16 bit and Java is 32 bit。

And we need a more flexible input format because sometimes we want to load programs elsewhere in the memory。

 so you can see the full implementation Toy Java on the book site。

 but this one here is fine for a lot of purposes。It runs any toy program。

 it behaves exactly precisely as if toywood， in fact it is toy。

 so if we give the re array program and then we give Eaves tape。

 then we're going to get in an infinite loop just as if toywood。

And the really important thing to think about it is if you wanted to design another computer。

 all you have to do is change this program very easy to change the design should we really have three registers。

 should we have one register in memory which instructions do we want to include you can design any kind of computer you want with a simple program like this and by the way。

 we don't have a toy machine， but we could we develop toy code lots of toy code using this on another machine。

So with our simulator， we can develop code for toy， even though toy itself doesn't really exist。

In fact， this program is so simple you could actually implement this program in toy so you could simulate toy on itself and that seems a little crazy but that's what people do with real computers you write a program that simulates the next computer on this one here's another program that simulates the toy machine。

 it's a graphical simulator so it includes all kinds of aids to program development gives a full display of the state of the machine it allows you to single step through programs lots of other features like that there's a large number of simple programs included as part of the simulator you can think of that as a paper tape library and it was a student of this course that wrote it and you can go ahead and develop toy software to whatever extent you want on this simulator。

The simulators better than the actual machine because we can put all these program development tools in the simulator that don't exist on the real machine。

 and that's the approach that's used for all new systems nowadays we build a software simulator and development environment and we use that to develop and test software for the actual machine。

 it's only when we're satisfied that the software for the actual machine is going to behave well and we know that by exercising it extensively on the simulator that we actually build and sell the hardware。

It's an important concept to think about and again， all enabled by the idea of a von Neumman machine。

 and that brings us to the idea of backward compatibility so at any point in history。

 say that we're working long fine on an old computer。

 but we know that there's faster technology out there So it's time to build a new computer。

 so what do we do about the old software。Well， one idea is to just rewrite it all for the new computer。

 but that can be very costly in time consuming in error prone and also nobody wants to do that。

So instead what people virtually always do is write a program that simulates the old computer on the new one。

 it's not very difficult to do that in fact usually you already have a simulator that's very similar and so it's not a one pager。

 it's a three pager or something a small program but it's going to be actually more efficient than the old computer probably because it's only adding a little bit of overhead and it makes enables the use of all the old software so it's very powerful ideas we can progress to a new computer。

 use the old software， still be a little bit faster and then we can pick and choose which new software we want to develop。

But as the decades role so for example， in the 1980s。

 you had to buy a piece of hardware to play PAacmanan and people still kind of enjoy the idea of owning one of these pieces of hardware。

 but even by the 2000s you could run it on a laptop and certainly there's a simulator of PCM on your mobile device。

 it's not new software， they're just running the old software in a simulator on whatever device。

So the old software remains available and doesn't go away at all。

While there is an idea though that is a little bit disturbing is actually。

 does anyone know how that old software actually works。

 it was developed under pretty severe conditions， small machines， not much memory。

 maybe written in machine language and maybe it's actually running through several layers of simulators。

 maybe the mobile devices simulator simulating the laptop and the laptop is simulating the machine。

 so actually knowing how the old software works becomes more and more of an issue as it ages。

Here's an urban legend about this， Probably not true， but it tells the story。

 So there was the rocket booster for the space shuttle that needed to be transported by rail。

 So now US railroads were built by English expats。 And so the standard rail gauge in the US is what it was in England 4 feet。

8 and a half inches。And that was chosen to match the ruts on the old country roads in England。

And well， those ruts were made by Roman war chariots。

 and so what was the distance between the wheels on Roman war chariots。

 it was determined by the width of a horse's back in。

So it's the end result is that this dimension of the space shuttle rocket was determined by the width of a war horse's backhand。

And the point of the story is that maybe backwards compatibility is not necessarily always a good thing and there's a lot of software out there that seems to sometimes have this kind of characteristic。

So even broadcast TV has to be backward compatible even though everything is digital now。

 I had to be backwards compatible with analog black and white。

 lots of business software is written in cobal which is a dead language。

 nobody writes new programs in cobal anymore but it's simulated by many。

 many layers of simulation and people use it and there's no way of understanding it。

 around the turn of the century the Y2K problem was a big concern because there was no way to fix the software to know that there was going to be that 00 was going to be the year 2000 is' going to be a later year than 99。

 which was 1999。Airline scheduling， that software is written in the '70s and is used by over many layers of ambulation。

 and it's hard to be confident that anybody really knows how it works。Documents。

 everybody's experienced this， you need sometimes an old version of documented processing software to read a file that someone gave you in web pages。

 a real nightmare of web development is trying to maintain compatibility with all versions of all different browsers。

And don't forget the iPhone software， as we notice。

 is an unsafe language and but now it's done that way and then new devices have to maintain compatibility with that on safety。

But real， really the sobering thought is that a great deal of our computational infrastructure was built in the 70s or 60s。

 70s， 80s， really a lot in the 70s on machines not a lot different from toy。

So maybe it's time to design and build something new for today's world。

The computers and software and program environments that you have are way superior to the environments that we use to build the software that we use。

 and that means you， you know enough now to go out and do it so taking this to another level。

 let's look at the idea of virtual machines。So nowadays when people build anything they simulate it to test it and so a little it's an issue that the sim has to be really good it might not reflect reality and it might be too expensive but it's not as expensive as the rocket blowing up but for a computer there's all kinds of advantages to sim first of all the sim is the definition of the new machine。

 the simulator is built when the hardware is built tested against the simulator。

 the simulator is reality and the other thing is the time consuming difficult to engineer all the physical processes needed to create a computer in the meantime software can be developed using the simulator and the other thing is we can simulate the machine。

That may never be built Lake Toy it's a fine example and there's lots of examples in today's world so for example nowadays most programming system use what's called virtual memory programs have the ability to address a huge amount of memory way more than can ever exist in a real machine and the operating takes track keeps track of mapping the memory that the program addresses to the real memory of the computer and that's an idea called virtual memory that's been around for a long time and is quite useful as it makes programming a lot easier。

Java virtual machine is another example， that's not a real machine。

 but simulators for that machine run on all on thousands and thousands of real devices。

 and it means that quite a bit of software can be built on top of that without having to worry about the detail of all those devices。

AndThen there's a thing called the cloud， initially the Amazon cloud。

 but now there's many out there where there's virtual machines of all different types that are available for use on the web。

 all you need is a credit card number and you can call up a virtual machine that'll run your software of any configuration that you want。

In fact， really internet commerce and actually lots of software development is just moving to machines like this。

If you're forming a startup， just use a virtual machine。

 it's probably going to perform better than a real machine that you'd be able to afford just a decade ago。

 forming the big effort in forming a startup was getting the computer center going and getting at the compute。

 you needed whatever you were selling， whether it's photo processing or messaging or whatever else。

 nowadays startups don't need to do that， they just use virtual machines that are never going to exist。

 Comp is a utility like electricity using virtual machine。

So the whole idea is the idea of layers of abstraction and we see that over and over again in computing where we get something that we understand。

 we build something else on top of it， it's an extremely powerful idea and again。

 toy is real to the extent that your computer is real。If you're approaching a new problem。

 one good way to think about it is to create a language or a machine to help you express solution。

Whether or not you actually build the machine is an entirely separate issue。

 maybe you can just run the simulator for that machine on some real machine。

It's quite a powerful idea it's all enabled by the idea of a von Nemann machine and really open up the opportunities that we still have before us today。

I just want to finish by reminding people about touring and von Neman in the theory lectures we talk about touring theorem。

 which says that you can have a single machine that can do any computable task。

And the idea was that this concept called a Turing machine a virtual machine。

 that is a way of encoding any tasks that we can do with the computer and then we can have a particular virtual machine called the universal Turing machine that can simulate any Turing machine。

 and the whole concept of making this proof work is the idea of a program as data。

And von Neuman then very soon after created the idea of a computer design that's got all the characteristics of computers that we're used to and is a physical realization of the program as data concept。

These two ideas together show us that the idea of a program as data has always stood at the foundation of Computer science and will continue to do so for some time to come。



![](img/85ebc5322df9b5e974b8a340bc4e031f_2.png)

![](img/85ebc5322df9b5e974b8a340bc4e031f_3.png)