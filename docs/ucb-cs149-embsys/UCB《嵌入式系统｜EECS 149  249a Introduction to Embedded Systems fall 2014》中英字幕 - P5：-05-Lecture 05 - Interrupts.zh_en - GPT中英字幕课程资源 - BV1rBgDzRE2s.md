# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P5：-05-Lecture 05 - Interrupts.zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

Yes， good， thank you。All right， we are here。September 11th。嗯。

Remember that homework is due today by midnight？Excuse me， you should turn it in online。

 any format that's legible is fine， whatever's easiest for you。

 we don't want to make it hard for you。Just make sure。That we can read it。On Tuesday。

 we're going to have a guest lecture。By one of the world's best experts on embedded vision。

who is very plugged into what's going on in industry in this area。

 so how vision is getting incorporated into a wide variety of different embedded systems。

 so I think you'll find that pretty interesting。And he hasn't decided whether he can allow his presentation to get recorded。

 so you might want to come live rather than trying to rely on the webcast。

And then after that we're going to switch gears fairly significantly。

 so as you recall at the beginning of the class we've talked about there's sort of three concurrent threads going on in this class that we call modeling。

 design and analysis。And。The textbook is in fact divided into three parts。

 and they're meant to be read concurrently。We've been focusing on design and it's very much on the nitty gritty of design。

Which my hope is that in a few years when you are all practicing engineers。

Most of what you learn here you won't have to deal with anymore because these low level nitty gritty details are kind of ugly。

 I think the technology is kind of immature， I expect it will be improving。

But understanding how it actually works under the hood is going to be an enormous advantage。

 and most importantly， it's going to make you really appreciate the improvements when they come。Okay。

 so one example of that is one of the homework problems that I know quite a few of you have been struggling with is doing the cash analysis。

It's an extremely difficult problem， it turns out it's a problem that is even difficult when automated。

 okay although the techniques that are used for automating it are really quite interesting and in fact we'll be talking about some of those techniques when we get to the analysis part of the course。

But starting next week， we're going to switch over to modeling。In my opinion。

 it very nicely complements the work on design because the modeling gives you a way to understand why things behave the way they do。

 whereas the design part is really about more about the how， how you make it do something， right？

Okay， so does anybody have any questions for me before I launch into today's topic？All right， good。

So today we're going to continue the discussion of IO。

 how you get data in and out of microcontrollers。

![](img/49cfe6a7c9c3a6f69bf0de0a0736c4fa_1.png)

And the focus is going to be on interrupts。And more fundamentally on managing concurrency。Okay。

 so interrupts are essentially a concurrency mechanism that exists in all modern processors at a very low level。

And it's a really treacherous technology okay concurrency is very difficult to reason about humans I think are not very good at reasoning about concurrent programs。

 although we're very good at reasoning about concurrent physical processes， right。

 but programs don't look at all like physical processes。

 and so our brains kind of haven't adapted to understand。

How concurrent programs work and as a consequence， it's a real struggle。嗯。

You can avoid concurrency in programs。You can in fact。

 create programs that are just a single thread of execution on a single microprocessor。And in fact。

 in certain industrial settings， you have no choice but to do that， so for example。

 if you're designing software for the flight control system of a commercial aircraft。

On the flight control systems of the commercial aircraft。You're not allowed to use interrupts。

 you're not allowed to use threads。ok。嗯。Everything is in a single thread of control。

The only allowed programming language is C。You can't use C++ or Java actually that's not quite true。

 fairly recently there was a bit of a revolution in that field where a programming language called Luster。

 which is a synchronous language and embodied in a tool called SCde was approved for use in the development of safety critical aircraft control software and。

We're going to talk a little bit about that language later on in the course or more fundamentally about the principles behind it。

 but not too much， but one of the key goals，In。In that language。

 and one of the key reasons for all of the constraints that are imposed on the engineers who develop these flight control systems。

Is that。Systems in software that have concurrency in them tend to behave non deterministically。

What that means is that。If a processor correctly executes your program。

 there are many possible behaviors。That can emerge from that correct execution。

That's not generally true of a single threat of sea。

 a single thread of C has a deterministic behavior in the sense that if you start with variables all at one value。

 you execute a single thread of C， you will deterministically end up with variables having a single finite value that is defined by the program。

Okay， but you lose that determinacy property when you go to concurrent systems。Of course。

 you lose another determinacy property even sooner。

 a single thread of C is not deterministic with respect to the timing of the program。

There are many timings of that execution that are correct。Okay， so when you care about timing。

You have a little bit of a problem because you're using a programming language。

That doesn't really allow you to express。Your timing constraints。

And so the timing kind of emerges from the design rather than being part of the design okay and that's。

 in my opinion， that's one of the biggest flaws in embedded systems technology today。

 and one of the things that I expect will be changing。

 timing will become a first class entity and you will have languages that will give you direct control over timing。

But it's not there in industrial practice today， and so today when you need to control timing。

 you can struggle quite a bit。One of the suggested projects for people involves controlling individually addressable LEDs on LED strips or LED panels。

And these devices， the way they're designed today， in order to actually control these LEDs。

 you need very precise control over the timing of the software。Okay， so you， in fact， you know。

 part of the design exercise is actually， how do you talk to the physical device where the behavior of the physical device is very timing sensitive？

And you're using a programming language that doesn't give you any control over timing。

so there's a mismatch there and you know you need to kind of understand the underlying mechanisms quite a lot okay。

 so one of the ways that you can get deterministic behavior and still do IO is do polling and in fact this is typically what happens in an avionic system。

 the flight control system in a commercial aircraft。Suppose you have a temperature sensor。

That is telling you the temperature of the engine。Okay， at some point in the engine。The software。

Will。Periodically go and query that sensor for a value。Okay。

 now it might be a lot more efficient to just have that temperature sensor tell you when there's a significant change in temperature。

 for example。Right。But that would not be a polling strategy， that would in fact require concurrency。

To do that。Okay， so polling means you just write your software so that it executes in one big loop。

And it will periodically。Ask is there anything interesting happening there no okay well is there anything interesting happening there。

 well no， and so there's a huge amount of overhead in doing that。

 most of the things you're checking when you're going through this one single loop are uninteresting。

Okay。And so there's an inefficiency there， but that inefficiency。ive the design style rather。

 gives us a measure of determinacy such that your program now becomes predictable。

Controllable in a way that it isn't with concurrent mechanisms。Okay。So the polling。

Flow is you do some setup in the processor， then you have one main loop。By the way。

 last time I was starting to talk about networking， but I've decided to。

Pospone that and actually do a full blown lecture on networking later in the semester because it's a big enough topic to really be worth it。

But yes， question。I'm sorry。From the previous slide。Okay。I'll get to that。Okay。

 I'm going to talk about this in some detail。嗯。So。But I did start talking about networking last time。

 okay， and one of the things I mentioned was that there's a family of domain specific networks that are used in industrial automation。

 in automotive applications in avionics applications and so on。

 and that these are different in character from the networks that we use to carry TCPIP traffic and internet traffic。

And one of the key differences is that theyre typically these networks are time slotted。

So they're reservation based with periodic schedules。

And devices have exclusive access to the network。For some amount of time at a periodic rate。Okay。

 and this is a way that you can get deterministic behavior out of networks。

 and that's one of the things that is really the driving factor for the existence of these domain specific networks is in order to be able to get this deterministic behavior。

Now， interestingly， when I talk about networking in more detail later。

 I'm going to explain to you that you can actually get this deterministic behavior today using。

Internet style networks， and so there's been some very interesting developments just very recently in the last few years that enable you to really get control of the networks and we'll talk about those when we get there。

For now we're at a much lower level， right which is。How do you get data in and out of a processor？

Okay so in a polling style， you might recall last time I talked about the snippet of code for an AVR 8 bit microcontroller。

 so this is the kind of microcontroller you find in kind of the low end Arduino platforms that some of you have probably played with。

Okay， so this particular snippet of code is just sending a bitete out on a serial port and it goes into a while loop that waits for a status bit to tell you that the serial port hardware is ready to receive your bitete。

Okay， and then when it's ready， you write your by into the memory map to register in the hardware and the hardware then begins shifting it out。

 okay。So if you want to shift out a sequence of bytes， the code would look something like this。

 you know， this would send out a sequence of eight bytes over the serial port。For each byte。

 you wait until the hardware is ready， and then you load your byte into the memory map register and the hardware begins shifting it out。

 and then you come back and wait until the hardware is ready again。

 it'll become ready when it's finished shifting out your byte。Okay， that's when it becomes ready。

And we did the calculation last time about how long it takes to execute。

 assuming the fastest RS 232 line， which is 57。6 kilobot。

And we discovered that each iteration around the wild loop takes 2，500 processor cycles。Okay。

 so it's a lot of cycles where you're not doing anything interesting in the process or you're just waiting for the hardware to be ready。

ok。So if you want to do things in the processor while you're waiting for the hardware to be ready。

 you need concurrency。Okay， that's the key。Inredient， right if you don't have concurrency。

 you're going to end up waiting for hardware a lot。Okay， but if you have concurrency。

 you can go off and do something else。While you're waiting for the hardware and then let the hardware let you know when it's ready。

 and then you deal with the fact that it's ready when you know the time comes。

 so that's what it interrupts her for。So。The way that interrupt mechanisms work in general is you define an interrupt service routine。

 which is a short subr routineoutine that handles the interrupt okay。

You set things up in your setup code， you register the interrupt service routine。

 I'll explain how that works， actually， it's useful to understand the low level mechanisms of how this actually works in processors。

Then your processor starts executing。And then when the interrupt occurs， you suspend the execution。

 whatever you're currently doing， you go and you run your interrupt service routine。

 and then you come back and resume executing where you left off。Right。So yes。

This is not operating system dependent， operating systems use this mechanism。

To implement context switching， but this is not operating system level context switching。Okay。

 there's no notion of a process， there's no notion of a thread here。Okay， this is hardware， right。

 you're executing a sequence of instructions。The voltage on a pin changes。

That causes you to stop executing that sequence of instructions。 Make a record of。Where you were。

 you record the program counter， you record the machine register state。Okay。

 and then you load into the program counter a new address。

 which is the address of the interrupt service routine。And you resume executing。

The interrupt service routine executes a series of instructions until it hits a return from interrupt instruction。

And when you hit that return from interrupt instruction， you take your recorded program counter。

 load it back into the program counter， load the machine registers that you saved back into the machine registers。

 and then resume executing your program where you left off， yes。I'll give you some examples。

 so I think it'll make it pretty clear， so first let me show you how you actually set up an interrupt service routine at the low level hardware。

So， this is。From the documentation of the At Mega 168。系。Apologize。

 but you probably can't even begin to read that at the back of the room， can you？Let me see if。

We can improve things here a little bit。Where is it， there it is。Is that better？Okay。

 so it's not a very high resolution image here but。If you remember。

 this particular processor has a 16 bit address space， so these are memory addresses。Okay。

 and the first few memory addresses in this architecture have a hardwired purpose。Okay。

 so at address zero。What what the hardware does when you hit the reset button。

Or when you power on the processor。Is it sets the program counter to zero？

Which means you start executing at this memory location。So the thing to put at that memory location。

Is a jump instruction。To。Whatever code you want your processor to execute when it starts up。Okay。

 so that would typically be a boot loader。So the boot loader will be a chunk of code that you've put in your flash memory。

Or in some form of read only memory。That will look for a program to execute at some location。

 load it into memory change and then jump to that， okay that's what a bootloader does。

In this particular architecture， at memory location2。

What the architecture uses that location for is that whenever an interrupt request comes in on。

Interrupt request line zero， this architecture has two interrupt request lines。

 so there's two pins on the processor。You change the voltage on one of those pins and that's a request for an interrupt zero。

 you change the voltage on the second pin， that's a request for an interrupt one okay。

If you change the voltage on IRQ0， then the hardware of the processor loads this address into the program counter。

and begins executing at this address。So what you're expected to have at that address is a jump to your interrupt service routine。

Similarly at location 4， you have IQ， the IRQ1 handler。Why are these0，2，4，6 and not0，1，2，3。

 why do you think？Remember， it's a 16 bit address in the processor， right？

And what you want to have at this location。Is a jump instruction to a 16 bit address。Wait a minute。

 how are you going to specify it's a jump instruction？And put a 16 bit address into 16 bits。Yeah。

 so you can't actually put your reset code anywhere you want in the memory space。

Because you've only got so many bits。For address， you have to specify an offset address。

And typically what will happen is in the architecture design。

 it tries to encode the jump instruction with very few bits。

Okay so maybe the jump instruction is specified just by the first three bits of the address。

 leaving you 13 bits。To specify an address。But that limits where you can put the interrupt service regime et cetera。

 so the compiler has to know all about this， it has to lay out the code properly so that your interrupt request program is put no further than 13 bits away from this location。

 okay make spreading compilers for these processors fun。But you know。

 people are quite expert in that。Okay。诶。So is it clear how the mechanics of how this works at a low level？

Yes。这と。Well， that's very dependent on the processor you'd have to look in the。

In the manual to see what happens， okay？Intrinsically。

 if you're talking about two voltage level transitions occurring at the same time。You know。

One could be arbitrarily earlier than the other。So there's no necessarily synchronous notion there。

So you could have a race condition and it could be just arbitrary， which one will be handled。Okay。

very good question。Okay， let's go back to。呃。The slidehow you。Okay。

 so what should you do in the interrupt service routine， so when the hardware interrupt occurs？

All that the hardware will do typically and in this processor。

 is make a record of the current program counter。ok。And then set the program counter to this address。

That's all it does。Okay， the processor is being clocked。So in the next clock cycle。

 the instruction fetch。We'll fetch the instruction at this address。ok。

Then the return from interrupt routine will do the converse， right。

 it'll take the recorded program counter。Loaded into the program counter registerister。

 and that's all it does。Okay， but your interrupt service routine is going to have to do a bit more。

Because presumably the interrupt service routine needs some of the machine resources。

 it's probably going to load stuff into registers。If it loads stuff into registers without taking proper precautions。

 it's going to obliterate data that the program that was interrupted is relying on。Right？

So when the compiler。Translates and interrupt service routine into assembly code。

One of the very first things that will go into that interrupt service routine is make copies of all the registers that you're going to use in the body of the interrupt service routine。

 and then at the end of the interrupt service routine。

 restore the value of all those registers before you do a return from interrupt。Okay。

 that's kind of the job of the compiler。Now the fact that all that occurs。It means that。

It's very hard to tell how long it's going to take for an interrupt to be handled。Okay。

It can be very unpredictable， it's going to be dependent on how the compiler does stuff。U， you know。

 you could end up- if you really care about how long it takes。

 you might end up having to really dive in deep and look at the assembly code generated by the compiler。

嗯。That's a nasty thing to have to do， but if you care about timing， sometimes you do have to do that。

All right。Yes， question。呃本。correct state of the register。

It only has to save the current state of any registers that it's going to use。So the compiler knows。

 the compiler is compiling the body of the interrupt service routine。

It chooses which registers it's going to use。嗯。And it only needs to save the values of the registers it's going to overwrite。

好的。Like， does it say that， okay， this particular registration。There's this value。

It just seems that these particular registers are reserved。They not be used byで。

It can be done either way， but the most common thing is。

The compiler decides what registers to use in the body of the interrupt service routine。

And then for the current value of all those registers， it pushes them onto the stack。ok。And sorry。

HeHe doesn't doesnt。It doesn't create a new stack， it uses the same stack right in this architecture there's only one stack point or register。

 so if you want to put an operating system on an architecture like this。

 so what is meant by a thread in fact， is a sequence of execution with its own stack。

But in most of the hardware， there's only one stack pointer register。

 so the operating system is reading and writing to the stack pointer register to create this illusion that you have multiple stacks。

Okay。But anyway， the most common thing is to push the state of registers onto the stack。

 that's actually a pretty important thing to understand when you're in a memory constrained embedded system environment and you're worried about stack overflow。

Right， because。I think in the last lecture when I was talking about memory models， I was saying。

 well。You know， if if you have a procedure that has you know an integer argument。

 well that's going to get pushed on the stack， that's four bytes on the stack。

 if it has an automatic variable that's an integer。

 maybe that's another four bytes on the stack so you know your stack pointer is going to be get pushed by eight bytes。

But it might get pushed by a lot more。Because the compiler is going to push a bunch of state onto the stack as well。

 and unless you know the inner workings of the compiler。

 you have no idea how much that procedure call is going to push down your stack。

So stack overflows can occur very easily by accident。

 even if you're being very careful about the code， because whether a stack overflow occurs。

Ultimately depends on details that are not very visible to you。

 right you don't see how the compiler works yeah。Right。Typically， it gets put on the stack。

You don't have to prereserve it right， I mean the whole notion of a stack is that the stack pointer is pointing to your next available location or your last filled location。

 right？So it unambiguously defines an available location。我。Right。Right。Right。Exactly， yeah。

 you got it， that's exactly the dance that happens。Okay， and you know， if you about about know。

 think about this in terms of processor cycles， well， that dance that you just described。

 how many cycles were consumed？Well each push under the sack is probably at least one cycle right if you have a cache。

 it could be more if your stack cash misses， your stack pointer points to something not in cash。

It could be many cycles。It gets really hard to understand the timing of these programs very quickly。

Okay。嗯。All right， so here is the processor that you're working with in lab this week， right。

 the microblze and this is the memory map for that。And。Again。

 it is going to be impossible to read as is in the back of the room， so let me do this trick again。



![](img/49cfe6a7c9c3a6f69bf0de0a0736c4fa_3.png)

And find。

![](img/49cfe6a7c9c3a6f69bf0de0a0736c4fa_5.png)

So at the bottom of this memory address， so this is a 32 bit processor， so the addresses are 32 bits。

ok。And。呃。At the bottom of that address space is a table。

 and it's very similar to the previous architecture that I just showed you the AVR architecture。

At address  zero is in this case。Just an address， not a jump instruction。So now great。

 we actually have 32 bits。 you can put the interrupt service routine wherever you want now okay。

 so the hardware just says， well the only way I'm going to use that location is to。

Get that address and branch to that location。This architecture has a user exception。

 which is an exception that you can trigger in your code that will jump to a location that you specify by loading it into that memory location。

It has a single interrupt request。And you specify the address and you stick the address in this location and so forth。

ok。So that's the processor that you will deal with in the lab， yes question。嗯。No。

 in this architecture， it doesn't just。It doesn't set the program counter to。OhW， maybe it does。

ThisThis is straight out of the。Okay， yeah， actually I was wrong。So。

What the hardware does is if you get an interrupt， it jumps to location 10。

So what you're going to have to put in there is going to be a jump instruction。

 it's got to be a jump instruction。Can't be just an address。Yeah， so I was wrong about that。

 so it's actually very similar to the AVR。Architecture。

It needs to contain the jump instruction because location 18 has another jump instruction and if you just started executing here and executed something other than a jump instruction。

Then the next instruction to execute is going to be your brake handler。Right？

Which is probably not what you want。Okay。Okay， so。So the low level mechanism in the microblazs is similar to the AVR。

 the only difference is that it's a 32 bit address space instead of a。嗯。

16 bit address base okay by the way， you know the compiler hides a lot of this from you and that I'm going to talk about that today because it's awfully tempting to use this Harry Potter style of programming where you just you know。

Look up for the magic incantation to make stuff happen。And stick at that in your C code。But。

It's not good enough， right， generally for embedded systems。

 certainly not for safety critical systems， you'll never get away with it for safety critical systems。

You've got to know what's going on in those magic incantations， and if you need to control timing。

 you need to know in quite a bit of detail what's going on。Okay。

 so this is straight out of the microbze data sheet， it explains how interrupts work。

 says the interrupt return address。It is loaded into a general purpose register R14 Yeah。

 why they do that？So your compiler had better not use R14 for anything。Important。

Unless interrupts are disabled。So why did they even call it a general purpose register？嗯。

It seemss bizarre。Nevertheless， that's what they did。 So if you're writing a compiler。

 you need to read these specs very carefully right and make sure you don't use R14 because if an interrupt occurs。

 whatever you put in R 14 is going to get obliterated。

unless the hardware also pushes it onto the stack before doing this， right？

Which might be stated somewhere in the manual。Okay。All right， the second bullet says， in addition。

 the processor also disables future interrupts by clearing the interrupt En bit in the machine status registerister。

And then the interrupt enable bit is automatically set again when executing the return。

 this is a return from interrupted instruction， this is actually a great simplification because it basically means that on this microbllaze architecture。

You can't have an interrupt， interrupt and interrupt。ok。

So the hardware doesn't support nested interrupts， so you don't have to worry about the logic that would occur with if nested interrupts were allowed。

Most processors actually do support nested interrupts and so if a nested interrupt is going to be a problem for you。

 then you need to explicitly disable interrupts in your interrupt service routine， okay？

Many processors also support prioritized interrupts。

 so if you're executing an interrupt service routine that has a certain priority。

And another interrupt request comes in while you're executing that。

 then whether that interrupt gets handled immediately will be dependent on what its priority is if it has a higher priority than the one you're currently executing。

Then your interrupt service routine will be interrupted， otherwise it will not。

Nestted interrupts are the primary reason why the state is typically put on the stack。

Rather than just put into a fixed location， right， but here they don't allow nested interrupts。

So they can use a register to store their return address。Okay， but otherwise。

 a register wouldn't work， right because if you had nested interrupts。

 where are you going to put the second return address？嗯。Okay， does that make sense？All right。Now。

 timing。In C， you have no control over timing。In assembly code you。

Have some in the sense that you can count。Instruction cycles sometimes for some processors。

 simpler processors。But not reliably， because if one of your instructions reads a memory location。

 then how long it takes to execute that instruction depends on whether you've got a cash miss or not。

Right， so。It can be even if you're looking at assembly code。

 it can be pretty difficult to know the timing。So when you want to do time dependent actions in a microcontroller。

 you typically use an external piece of hardware。Called a timer。Okay， timer is a peripheral device。

 you interact with it through a memory map register。

And the way you use a timer is you write to a memory map register saying。

I'd like the timer to go off in 16 milliseconds。Okay， you encode that。

 however you're told to encode it by the hardware， so hardware specification of the timer tells you how to encode that request。

You say， I'd like to be interrupted in 16 milliseconds。ok。

And then the hardware just happily counts off 16 milliseconds in parallel with whatever code you're executing。

And when the 16 milliseconds have elapsed。It flips the voltage on the interrupt request line。ok。

And then that'll cause the hardware to then go and invoke your interrupt service routine。

 and now you can do whatever it is you wanted to do after 16 milliseconds。



![](img/49cfe6a7c9c3a6f69bf0de0a0736c4fa_7.png)

ok。So that's how you control timing。 And so here's the Harry Potter way to do this on the。

At Mega 168。Okay， so this is again， let me。Zoom in so that you can see this more easily because I think this font is going to be too small。

That's maybe a little bit too big。Is that readable in the back of the room？Yeah。Okay。

I think you guys have better eyes than I do because I probably couldn't read it in the back of the room。

Okay， so this is assuming that you've got a processor running at 18。4 megahertz。Okay。

 what does that mean， by the way？When someone tells you your processor is running at 18。4 megahertz。

我再命。It's， it's the。It's the clock cycle， right， so this thing is getting clocked at that rate。

And depending on your architecture， a simple architecture。Will。Fettch an instruction。

 every clock cycle。ok。Slightly more complicated architecture， well。

 some instructions may require two cycles。In the arm processor， there's an instruction。

 a single instruction that moves。An array of data in memory。

And so the number of cycles it takes to execute that instruction is dependent on how big the array is。

ok。One of the interesting questions， if you're using interrupts to control timing。

Is what happens if the interrupt occurs in the middle of the execution of that？

Bulk array transfer instruction。Right， normally。An interrupt is handled between instructions。

But the arm processor has an instruction that can take an arbitrarily long amount of time to execute。

So if you want to handle your interrupt with a precise timing。

 you better not use that bulk transfer instruction because if you do。

Then you're going to get your interrupts delayed by an unknown amount of time if you happen to get the interrupt during that bulk transfer。

By the way， that kind of problem is also one that will never show up in testing。Okay。

 because the interrupt won't occur while you're doing the bulk transfer。In testing。

 and that's Murphy's law， right， it'll occur when the plane is flying。Okay。

 it will not occur on the test bench。So you have to watch out for those kinds of things。U。Okay。

 so here's a sequence of instructions that according to this snippet of code from the。

From the manual， set up and interrupt to occur once every millisecond toward the beginning of your program。

 set up and enable the timer I to interrupt with the following Harry Potter codeing。Okay， you say。

TCCR1A equals 0 x00， okay。Well， what does that mean？It doesn't even look like C code actually， right。

It's。This isn't a C variable on the left hand side of the assignment。



![](img/49cfe6a7c9c3a6f69bf0de0a0736c4fa_9.png)

ok。嗯。So let's put it in the context of a C program。So here's a main。And I have this instruction。

This statement， this C statement。And this is not Val C。Because this is not a declared variable。

So what is it？Well， there's this pound include AVr/o。h。Search your disk for io。h。ok。

And search for this string and find out what's in there。 all the information you need。

 if you can get this program to compile， you can figure out what this means。

because the compiler is not clairvoyant， it's stupid。

 it just does what you tell it and in order to turn this into valid C code you have to include a header file that is going to define these strings they're defined using pound defineds so here's。

A few of the things that are included in this AVR package。

 so when you get the thing working on your laptop。Or on one of the lab machines。

 you're going to have a bunch of。Library files， and they're going to contain a lot of junk like this。

Okay。Very poorly documented junk。Okay。Also， everything has cryptic names。Right。

TCCR is timer counter control Register。OCR is outputput Compare registerister。Apparently。

When they decide on these， they seem to believe that ASI characters are expensive。

So they use as few as possible。It's a conservation strategy。嗯。Okay。

 so TCCR1A happens to be right here， okay， so I searched my disk and I actually found it in another file。

 it wasn't in this Io。h file。Okay。But the IO。A trial had its own includes， lots of them。ok。And。

So I found it in a file calledx8。h。The search mechanism on your laptop or on the computer is extremely useful for this kind of thing。

 right to really understand what's going on， you've got to hunt sometimes because they're trying to hide this stuff from you。

For some reason， they don't want you to know。嗯。啊。Okay， so there's TCCR1A。

 which happens to be what was on the left hand side of that assignment state。

And guess what it's defined to be。 Well， it's defined to be underscore SFR， underscore M 8。

Prenheses 0 x0。Zero x，8，0。It's still not valid Z code。ok。

So you got to go find out what this underscore SFR M8 is。And in another file， you can find that。嗯。

So we found this。You can find underscore SfrR。Undersco M8 is a macro that takes an argument。

 the argument being passed is 0x80， and that's not vancy code either。Mh。😊，It's another macro。😊。

which happens to be defined in the same file。And that one actually is valid C code now。

So let's look at that valid C code。So this line of C。😡，Before the compiler even sees it。

Gets turned into this line of C。ok。So what is this line of C？Zero x0 is a constant。ok。

But it's being cast to a data type。Called volatile unsigned8 bit integer。

But a pointer to a volatile unsigned a bit integer。

So the 0 x0 is going to be interpreted by the compiler as a pointer to an unsigned8 bit integer。

And then it's dereferenced。Okay。By dereferencing it。

 you can put it on the left hand side of an assignment。

So this constant will be loaded into location 0 x0。That's what that Harry Potter incantation does。

It just writes to a memory location， 0 x80。Whi is presumably a memory map register。

That does some setup of the timer。To invoke interrupts。O。So if you go through this。

The details given here in this text here， you can find out what the other lines mean so this one says OCR1A equals 71。

Well。They explain here that OCR 1A is a memory map register that is going to determine how frequently a periodic interrupt is invoked。

ok。But the frequency is in terms of processor cycles。

 so you need to know that you're clocking this processor at 18。4 megahertz。

To know how to translate this into some amount of time， so you do a little calculation and you find。

 yeah， want ther if I want the timer to trigger and interrupt every millisecond。

I should load a 71 into this memory map register。Okay。

 and that will give me a timer interrupt every one millisecond。All right。Okay， so。

I really hope that you know， by the time you've done a little bit in the lab with this， you can。

Work your way through。Any piece of code and demystify what's going on， right。

 generally the underlying mechanisms are really simple。

You have to have confidence that that's the case。Even though the engineers who design these systems and the supporting software are trying their hardest to hide all this from you。

It's not really that hard to figure it out。Okay。嗯。All right。

 now lest you think that all processors look like this， they don't okay。

 so one of the things that I try to do in this class is。You know。I give you one way of doing it。

And then I show you a different way of doing it because I don't want you to walk out of the room thinking。

 oh yeah， that's how interrupts or dealt with on all processors and it's not really that way， right。

You have to read the manual and understand it。嗯。So here's a different processor。

 this is a 32 bit processor on a board produced by Luminary Micro which was acquired by Texas Instruments。

 it's an arm processor which is a very common architecture that's used in embedded systems。

It's a 32 bit arm processor。So in this case。The C instructions look quite different。

 they look like C procedure calls， this actually looks like a legitimate C program。ok。

As long as cystic period set is。A procedure defined somewhere， this could be a legitimate C program。

And it might be a procedure defined find somewhere， or it might be a pound defined macro。

 you don't know until you look at those header files， right？But you can。Puzzle through it because。

If the compiler has enough information to compile this。

 then you have enough information to understand it。

 it's there on your disk somewhere and you can find it if the compiler can find it， you can find it。

That's the thing that you need to have confidence about。Okay， so you can figure out what that means。

 whether it's a macro or something， but ultimately it's going to be just writing to a memory map register。

And it's specifying the number of cycles per sorry。

What looks like a procedure here is returning the number of cycles per second。Sstic period set。

 these guys， I like them better。 They don't seem to think ASCI characters are so expensive。

I can actually tell what that does from its name。ok。

It's setting up a timer to trigger a periodic interrupt。Okay。

 and they're calling that the system tick。So periodically。

 you're going to get an interrupt request and how often， well， this often。You're every 1000 cycles。

 no， sorry， this returns the number of cycles per second， so every millisecond。

You are going to get an interrupt。If you're writing a Linux kernel。Right。

Suppose you're going to write your own version of Linux。Right。Favorite thing people love to do this。

Right。嗯。What should this be？Does anybody know how often the system timer in Linux ticks？

They call it the GIiffy interval， by the way。Okay。Well， yeah。60 hertz， no。

 it's much faster than that。It's every 10 milliseconds normally。Okay。

So a GIiffy interval is 10 milliseconds。So every 10 milliseconds in a Linux machine。

 an interrupt service routine will get invoked。And that interrupt service routine is a kernel function in Linux。

And one of the things that that interrupt service routine does is it decides whether you should continue executing whatever program you are currently executing。

Or switch to executing another program， that's how it does multitasking。

So if you decide to switch to another program。Okay。How should the interrupt service routine work？

Well， it's really pretty simple。When it returns from interrupt。

Instead of putting into the program counter， the location。Where the interrupt occurred。

It puts in some other location that it's saved。 and it makes a record of the location that was interrupted。

In the same table to come back to later。Okay， so you can play with the return from interrupt and not return to the same place you returned to or you were interrupted from。

And that's how multitasking gets done in a multitasking operating system，Yeah， that could be。

So I think in the microblas， I mean， it's relatively easier。

 if everything is done by a single kernel interrupt service routine that makes things relatively easy。

 yeah。No， I think this is of the processor， I think。I don't know， actually， well。

 typically the timer will be clocked with the same oscillator as the processor。Yeah。就。

But I'm not sure you'd have to read the documentation to really get the details of how this works。

Okay， so then this second line， cysts tick enable， starts the counter。Okay。

 and then cyststic interrupt an A。Enables the interrupt to actually be handled。ok。

These are all just writing to memory map registers。

 so there's hardware that's going to invoke that interrupt。

And handle the interrupt and the hardware is controlled by writing to memory map registers。Okay。

So if you want to write a program， say that does something for two seconds and then。

Stops doing that and goes on and does something else。ok。We could do a setup like we just did。

 so we just did a setup that's going to invoke and interrupt every millisecond。Once per millisecond。

 the interrupt service routine will be handled。So suppose I specify that this is the interrupt service routine。

 by the way， the way that I specify that is I call Ss tick int register。Okay。

 and I give an address of a procedure。Okay， you can do that in C， can't do that so easily。 Well。

 you can in Java using reflection， but it's kind of。Very indirect in Java okay。

But you can give the address of a procedure as an argument。So what do you think this is going to do？

With that address。Sticks it in the interrupt table， right。

 Sts It depends it to a jump instruction and puts that jump to that location in the interrupt table at location 10。

 if you're on the microbze or。Whatever the location is for the lu luminary， yeah， I mean。

 for the arm。To alert the compiler to that。Yeah， so the compiler does need to know that this is an interrupt service routine for various reasons right。

 one of them is that if the compiler does optimization， it can analyze the body of this code。

And determine that this procedure is never called。It never gets called in the body of the code。

 therefore the optimizer could just delete that procedure altogether from the image， not include it。

 save some memory。So yeah， you need a compiler directive that tells it it's an interrupt service routine。

Often what happens is you're given a nice gooey。For an integrated development environment。

And it's got the compiler built in。And the compiler is going to recognize just this line might be sufficient。

To give the compiler directive so that it knows not to optimize away that procedure。Right， yes。No。

Thiss because we set up the interrupt to occur every millisecond。

 regardless of what the clock rate is。So the clock rate is going to be returned by this。

And that's in number of cycles per second， and we divided that by 1000 to say we would like the system tick to occur at one millisecond intervals。

 that's what that says。O。So as a consequence。If we want to execute some code here for two seconds。

 we can do it like this right we set up this interrupt service routine。

 what the interrupt service routine does， it's nice to keep interrupt service routines small and simple right because they interrupt stuff。

They can disrupt the timing of the program。And if they disrupt the timing less。

 that's usually better than if they disrupt the timing more， so keep them simple。

 so this is a really simple one， all it does is decrement the value of a variable。Okay。

 where is this variable stored in memory？It's a static variable， right so it's in the program image。

 right？嗯。So we have a static variable， it's declared outside of any procedure。

 so it's going to put it in statically allocated memory chosen by the compiler。Okay。Not on the stack。

That's the key point， that variable is not on the stack， this variable is also a global variable。

 so it's visible within any procedure。Consequently。

 the interrupt service routine can see the variable。

 and so can the main procedure can also see the variable。

So what this main procedure does is it does the initialization for the interrupts。

 then it loads the number 2，000 into time or count。And then it goes into a while loop。

That will wait until until the timer count is zero， it'll execute some code。

And then it'll fall through to something else， yes。啊呀。Yes， you're ahead of me。

You have detected a bug。In this code。Okay。嗯。So hold that thought， right。

 let me explain a couple more things， one is this volatile keyword。呃。

That's really kind of an interesting keyword in C because。Semantically。

 it actually doesn't mean anything at all。With regard to the E program。

 it doesn't change the meaning of this variable。The variable is still a static variable。

 it's still global。ok。Adding the word volatile to the declaration doesn't change those facts in any way。

What it does is it provides a hint to the compiler。That the value of this variable may change， even。

Without the program actually causing that change。Okay。

So it prevents the compiler from doing certain optimizations。So， for example。

 the compiler will never。Store the value of this variable in a register。

And then use it over and over again from the register。ok。Because it's declared volatile。

Every time you reference this variable， it will be fetched from memory。Okay。

 because it's declared volatile， it will always be fetched from memory。

 You've told the compiler that it may change at an arbitrary time without。Me knowing about it。

Okay so the compiler didn't cause the change。But the change can nonetheless occur。

So it's a pretty important keyword to not forget。Because you might get lucky and your program will work without the volatile keyword。

Depending on what the compiler does。But you change a line in your program somewhere， recompile。

 and it doesn't work anymore， and the line you changed was in a completely different part of the program。

But it somehow triggered a different set of optimizations。

And your program stops working for mysterious reasons， yes。千は？Right。你例子啊。Right， yeah。

 the problem is that the compiler can simply analyze the flow of control of the program。

In this flow of control， this procedure is never called。So if without the volatile keyword。

 the compiler could determine that， well， I just set the timer account to 2000。

 therefore it's not zero， I just set it to 2000。So it's not zero。

And there's nothing in this body that writes to it。So therefore。

 I can replace this wild loop with just a jump。That makes it an infinite loop。

 I don't have to bother doing this test。A compiler optimizer could easily do that。

 but because this is declared volatile， it won't do that。Okay， makes sense。Yes。Yeah。

 that's a very good question。Right so what happens if the interrupt service routine it takes？

Longer than your interrupt interval， okay， so the way to think about that is the question you want to ask is I think the other way around。

 which is what happens if an interrupt request comes in while you're in an interrupt service routine。

 okay？In the case of the。啊。The Xylelinkx processor that you'll be using in the lab。

That interrupt request will be ignored， okay？Until you've return from interrupt。And at that point。

Depending on the hardware， the request may still be there or may not if the voltage is still high on the interrupt request line。

 if the timer happens to just hold it high long enough，Then you might get an interrupt handled late。

 but at that point。Okay。But if the hardware doesn't hold the request up long enough。

 if the voltage has gone back down， you could return and the interrupt just gets completely missed。

ok。嗯。These are the kind of nuances that can make it really difficult to control timing in processors。

 And this is partly， you know， part I'm sort of trying to do two things here， right， is。

Show you how stuff works today。And convince you that this is horrible and needs to be fixed。O。

We do need to control timing， these are terrible ways to do it。And they will change。But。Not yet。

 right it's going to happen。You know， in the next few years， I'm sure。Okay。嗯。So。

This is a concurrent program。ok。It's concurrent in the sense that this chunk of code logically operates at the same time as this Okay now。

 in fact， in a threaded a single core single instruction issue processor， it's not really。

It's not really concurrent， what happens is that this will get executed at an arbitrary point during the execution of this。

And I want to emphasize that an arbitrary point doesn't mean between lines of C code。

Tp it means between assembly language instructions。

And one line of C code could translate into many assembly language instructions。

So you could be halfway through the execution of a line of C code。In fact。

 you could be halfway through the execution of a single assignment。ok。If you have an a bit processor。

And you assign an int a value。There's four bytes that are going to be assigned。

 it's probably going to take four cycles to do that。

 and the interrupt could occur with the int partially assigned。

So the value of the int might have the high order bits updated and the lower order bits not updated。

ok。So。If you're looking at an int in an interrupt service routine。Don't trust its value。

Because it might be partially updated by the code if you're in an processor。This is nasty， okay？嗯。

All right， so this program as you who was it that pointed this out， yeah， has a bug。Right。嗯。

What could go wrong？Well。嗯。Suppose。Suppose the interrupt occurs twice during the body of this execution。

So the code that you're executing in here happens to take more than a millisecond。

Maybe you get a really unlucky sequence of cash misses。 and it takes more than a millisecond。

 you get two interrupts come in。Okay。And what if it just so happens that when you first entered the body of this while loop。

 the value of timer count was one。ok。The two seconds are almost up。The interrupt occurs twice。

 timer count gets decremented to zero and then。Timer count is an unsigned integer。

 so it now becomes equal to 2 to the 32 minus1， a very large number。Okay。

You come back to your beginning of your while loop， do your test， and yeah sure enough。

 timer count is not zero， it's now 2 to the 32 minus1。So you keep executing the code here。

Past the two seconds。In fact， way past the two seconds。

Because you're going to have to wait two to the 32。Miseconds before it's going to hit zero again。

 and if you're lucky。It won't have the same problem at that point。

 and you will have not executed this for two seconds， but for a very， very long time。Not good， right？

So don't keep your interrupt service routines too lean。Okay， here's one possible fix。ok。

Where the interruptop service routine will decrement to zero but no further。Okay。Yeah。这都是。絶三。Yeah。

 it could。Yeah。嗯。If the interrupt occurs during this assignment， you're saying。Yeah。呃。

You have to occurs。Yeah， if suppose it sets the lower order bits。Then invokes the interrupt。

Which will。Yeah， I don't actually I don't think that'll kill you。

 It might introduce a millisecond an off by one millisecond error， okay？But。

Reasoning about these things is really difficult， very， very tricky， right？

There's lots of stuff that can go wrong。With this particular variant of the code。

What if you allow nest interrupts？And an interrupt occurs right here。Okay。

 you've just tested the timer count is not zero， say it's one。And an interrupt occurs is right here。

 and it gets handled。What's going to happen？Well， this same interrupt service routine is going to get invoked。

And it's going to decrement the counter to zero。And then you're going to return from interruptt to this point。

And decrement the counter again to 2 to the 32 minus1。ok。

You went right through zero without stopping。so if you allow an nest it interrupts。

 that could happen。hopefully you can see now why they don't let you use interrupts if you're writing the aircraft control system software。

Right because。How are you going to know you got it right？It's really hard， yeah。Yeah。

There's all kinds of things that can go wrong here。Right。嗯。Okay， so。

The issues you need to watch for is you know what's the end of service routine execution time that's you know。

 in essence， you have to think of it as a pause time。

 your program could be paused for an arbitrary amount of time at an arbitrary point。

And that makes it difficult to control the timing of that program。If you have an operating system。

 the interrupt servicer routine is often a fairly involved thing that's going to execute some context switching policy to decide。

To where it should return from interrupt， okay？You need to worry about nesting and have a higher priority interrupts。

You need to worry about interactions between the interrupt service routine and the application and interactions between interrupt service routines。

And， by the way。Bugs in this kind of code are far and above the most common cause of crashes。

when I plug the projector into my laptop here。There's hardware there that detects that I've just plugged in a projector。

An interrupt request gets made， an interrupt service routine gets invoked。

 and sometimes it interacts in a nasty way with the kernel and causes the laptop to crash。Okay。

There's a bug。I would contend actually that every nontri program of that with that kind of concurrency has bugs in it。

It's just。Some of them haven't manifested themselves yet， you haven't seen them in action。

But they all have bugs。嗯。And you know， to me， that is an indication of a flawed technology。

 which is why you know I believe， you know a big part of my message is this is going to change because it has to。

 we need to be able to make these systems more understandable and more bulletproof if we're going to have self-driving cars。

ok。We need processors that are not relying on the kind of analysis that we were just doing on a six line program。

Right。You can't do that kind of analysis on 100，000 line program。All right。One comment。

 what's the difference between concurrency and parallelism？Yeah。

 so parallelism is a physical property， it means that there's actually two pieces of hardware doing something at the same time。

ok。Concurrency is a logical property。 It means that conceptually the two things are happening at the same time。

 but you don't really care or know whether they're happening at the same time。

 they might be interleaved， you know， in some arbitrary way。But that's not important to you。

 The fact is that。It just a logical property that they're happening at the same time。

So a program is concurrent if different parts are conceptually executing simultaneously。

 and it's parallel if they're physically executing simultaneously。And。

From the perspective of debugging these programs。It really doesn't make any difference whether you have parallelism or not。

 So for example， you know， suppose that you had a multi core processor。

Where two cores share the same memory space。And your interrupt service routines are always executed in core number two。

 and your main program always executes in core number one。Right？

Then your main program doesn't ever get its timing。Disrupted。Actually。

 it does because of contention for the memory system。ok。

But if you pretend the memory system doesn't have any conion， which is not a good choice。

 but nevertheless。Then at least， well， you get less disruption of timing。

But the possible interleavings of the actions are still just as complex。

Whether it's parallel or concurrent。Okay， the point with in the case of。A single threat of execution。

 this interrupt style， one of the real hazards。Is that。The bugs in these programs show up rarely。

Because。Interrupts are occurring in a small fraction of the cycles。

And the bug may manifest only if an interrupt occurs on this particular point in the execution of the program。

And it just may be extremely unlikely for that to occur。

So the problem here is that if you're using interrupts。Testing is not a good strategy for assurance。

 it doesn't give you assurance。No matter how much testing you do。

 you have no assurance that you've freed this program up from bugs。Okay。

 you have to analyze the program。And to do a full blown analysis is difficult。

 and there are tools that can help you， and we'll talk about those tools in the analysis part of the class。

Okay， how you can analyze these programs automatically。Partially。So。

I think we talked about all these issues， so the summary is。

Interrupts introduce a great deal of nondeminism into computation and very careful reasoning about the design is。

Is necessary if you're going to get assurance。Okay， so that's it， that's what I have。

 So remember that we have a guest lecture on Tuesday on embedded vision。

And then we're going to start talking about modeling。



![](img/49cfe6a7c9c3a6f69bf0de0a0736c4fa_11.png)