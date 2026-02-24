# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P4：-04-Lecture 04 - Interfacing to Sensors and Actuators.zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

I could get your attention， hello。Can you hear me in the back of the room？Okay。嗯。We are here。

 the ninth interfacing dis sensorensors and auators。

 but I'm going to start with a little bit of closing up the memory architecture's discussion with a brief discussion of caches。

A couple of announcements， if you are not in one of the lab sessions。

Then you're not in the class regardless of whether you're enrolled， okay。

 so you need to talk to the GSIs if you're not already fixed in one of the lab sessions。

 if you didn't get your lab account， you should see your GSI for your lab session to get your lab account。

 I think we got some of them after the first lab had already started and so some of you didn't get your accounts。

嗯。There's a homework assignment due on Thursday， you should turn it in on B courses electronically。

 and I think it's set to be due by midnight on Thursday and then it closes you out and we will be posting solutions shortly thereafter。

Are there any questions for me？Okay。

![](img/bd25340109397217e7475ccc2c610923_1.png)

So let's talk about memory hierarchy。嗯。

![](img/bd25340109397217e7475ccc2c610923_3.png)

Which is the。Last topic in the memory architectures chapter。

Last time I talked a little bit about the memory technologies that are involved in embedded systems。

 flash memories， static ras， dynamic ras。Et cetera， and if you remember static ras are。They're quick。

 they're usually designed to operate at the same speed as the processor。

 so often you can basically do an access to memory on every cycle of the processor in the staticgram。

 but they're relatively power hungry and they consume a lot of area on a chip and consequently。

 it's expensive to provide a lot of staticgram in an embedded processor in any processor for that matter。

So dynamic ras are much more scalable， they can be made。You know。

 more power efficient much much denser in the circuitry。

but they have the downside that the access times are generally longer you know the latency is higher。

 but in addition， there's a lot of variability in the timing because the timing of the accesses will actually depend on the sequence of addresses that you access。

 not just on the circuitry for each individual access。

So it is quite common if you have applications that require a significant amount of memory to use a hierarchy。

And there's a couple of different ways to organize this hierarchy basically。

The lowest level of the hierarchy is the register set in your processor， that's a memory。

 it's a rather small memory， but it's a place that you can store data and access it and in a typical processor you might be able to in a single instruction。

 access three registers， for example， to add the contents of two registers and put the result in a third。

嗯。The next level is either a cache or a scratchpad memory。

 and the difference between a cache and a scratchpad is that what's in the memory is either controlled by the hardware if it's a cache or by the software。

 if it's a scratchpad。Okay so what gets stored in this memory。

 if it's controlled by software we call that a scratch padd， if it's controlled by hardware。

 we call it a cache， all right， that's the basic distinction。And in both cases。

What will be in this SRAM at any given time？Will be some subset of the data that is stored out here in your big memory space and your big memory space will。

Physically be in the dynamic RA， or if you have a virtual memory system。

 it will be in some combination of the dynamic RA and the disk or flash。Are you testing the？

Accelerometer in the laptop to see if it shuts down when you drop it。Yeah。

Actually that laptop has flash memory， so you don't have to worry about that so much。Yeah。😊，嗯。Yeah。

Okay， so how you manage this hierarchy is important。

 I also talked last time and we' you know you're going to get a lot of hands-on experience with memory map IO devices。

 so when the CPU puts an instruction， sorry an address on the bus to fetch something from memory。

It's not necessarily addressing memory。Some other piece of hardware may respond besides the memory。

And an IO device will sometimes be the thing that responds。

 right we call that a memory mapped peripheral。And so if you want to send data to the serial port。

 for example， typically the way you do that is you write a byte into a memory location。

 which happens to be not in your static RA or your dynamic RA， but rather in a UAt。

 which is a hardware device that implements the serial port circuitry， okay？All right。

This memory hierarchy can be organized in a slightly different way where here the address space is segmented。

 So the idea of these pictures is that。When the CPU puts an address on the address bus。

 something responds， hopefully， unless it puts an address on the address bus and there's nothing there at that address。

 which you can do if you're writing C code。It's great fun to write a program that writes a lot of stuff into memory that isn't there and then tries to read it back and it's all gone。

But anyway， something responds。Cash or the scratch bad respond， then it'll respond quickly。O。

But if it doesn't respond in this architecture， it'll pass the request on to the next piece of hardware。

 which will then respond more slowly。If this guy doesn't have the requested address。

 then the virtual memory system might take over and it'll pass it to another piece of hardware which will respond even more slowly。

Okay so that's this organization， so here there's a uniform address space except for the memory map Io devices。

 all of the memory shares the same addresses so an address may be handled by this guy or passed on。

That address may be handled by this guy or passed on。All right。Yeah。Yeah。嗯。In this picture。

 I've not made a distinction between accessing instructions versus accessing data。And in fact。

 its a lot of architectures don't make that distinction。

 they use the same address space for both instructions and data。

 and the mechanisms for fetching are the same。In embedded processors， however。

 it's a lot more common to use what they call a Harvard architecture。

 where you actually have separate address spaces and separate hardware for instructions and data。

Okay， and in that case， you would have two of these。Mechanisms。

Both of which could have hierarchy and both of which could implement some variant of the same mechanism。

 Okay， so a Harvard architecture。That term is very old， by the way。It dates back to， I think。

 the Iiliac， which was a。Two based computer that happened to be at Harvard University。

Way back in the 1950s， and it was the first architecture that used two different address spaces for instructions and data。

 so it's always been called the Harvard architecture when you do that。嗯。ok。

So just as you could have separate address spaces for instruction and data， yes。第。

That's the way a cache works。我是老我为这个。I'm going to explain how it works okay so bear with me a second I think I'll answer that question in a second。

 but I wanted to first point out that just as you know you could separate the address spaces for instructions and data to get a Harvard architecture。

 you could also separate the address spaces by technology， so you might have。

 you know if you have a 32 bit address， you might divide up that address space。

So that a subset of the address is go to the SRAM。A different subset of the address is go to the DRA。

Okay， this actually， you know， if you're writing low level programs in C。

 this makes it a little easier to control the timing。

Because if you know which addresses you're accessing。

 you can kind of do the analysis to figure out what the latency is going to be of those accesses。

 if they're just separated address spaces。嗯。It has a disadvantage that your address space is now divided up into fixed chunks by the architecture。

You have more constraints on how you can put memory onto the system and be conformant with the architecture。

 but there's trade offs there， but anyway， it can be organized either way。All right。

So let me address the question of how a cache knows whether or not it contains the data at the requested address。

And for me， at least， I'm not an expert in caches， there are people who you know。There's。

Probably hundreds of people who have written their PhD thesis is on cash architectures。

 and there are people who have devoted their whole career to cash architecture。

 so there's people much more expert than me。But。For me。IWhen I have forgotten how a cache works。

The first thing I do is go to， okay， what's a direct map cache。

 it's the simplest one and it's pretty straightforward to understand。The way it works。

 there's a bunch of terminology here， but this is a set consists of a number of cache lines and with a direct map cache a set has only one line。

 so set and line are the same thing in a direct map cache okay。And the line consists of three fields。

 the valid bit， this is just one bit telling you whether what's in here is actually valid。

And then a tag， which is some number of bits and a block， which is some number of bits。

So given an address。Okay。Say it's a 32 bit address。You take some number of bits。

And declare those to be the tag。All right。So now what's going to happen is that when that address gets presented to the cache hardware。

What it wants to do is simply。嗯。It uses this tag address to go。😡。

To you know one of these fields here。 so it matches that tag， and then it looks up the。

If the tag of the address matches the tag of the line， then we have a cache hit。Okay。嗯。Otherwise。

 it passes the fetch on the main memory。O。So a set associative cash elaborates this a little bit and says。

 well， you can have actually several。Lines in each set。Okay， and now what's going to happen， wait。I。

I think I didn't explain that quite well enough， right the set index is what determines which set you're going to look at。

Okay and then the tag is going to determine whether you match what's in that set。So the set index。

 so it's easy to build the hardware to do this， you just extract these bits。

 use it to address the set。And then see if the tag matches。Okay。

 so it's not hard to-- if you've done digital design you kind of probably have in your head， okay。

 I know how to design that。This one's a little bit more difficult。 Okay。

 you still have the set index， so you know which set to go to。

But now there are several tags in that set。And one of them may match。

So you could brute force it and just search them。Okay。

 so check to see if the tag matches the first tag in your set。

 then if it doesn't check to see if it matches the second tag。But that's going to be slow。

So that's not what people do， what they do is they implement what's called a content addressable memory or an associative memory。

Where the memory gets addressed by content。So the tag is actually the content and it takes you directly to the block。

Okay。If you have a match， so that's why it's called a set Associative tag is because of this associative memory。

 so instead of providing the address， you provide the contents of the memory location that you want and you get back the location。

So it's kind of the converse of a usual memory。嗯。Okay。So in the case of a set as sociative cash。

 if you have a cash miss， then。You have a number of choices available to you right so if your set index takes you to a particular set。

And the tag is not present in the set， what should you do？Well， you're going to go fetch。

That memory location from main memory， and you're going to get it back。

But the way that a cache works is usually you want to now store it in the cache on the assumption that it's going to get accessed again。

 okay？But which of these should you replace？You have to choose one to replace。

So the hardware has to implement a replacement policy to figure out which one is going to replace with the new data that it fetched from the memory。

So typical replacement policies are least recently used。

 which requires a bunch of hardware to keep track of sorting of the access as within the set。

 or first in first out you just take the。呃。The last oldest the one that was put into the set longest to go and dump that one and replace it。

嗯。The hardware for these can get really quite elaborate。

 and it adds a lot to the complexity of the hardware。

Scratchpad memories are really much simpler because everything is managed by the software。

 the software treats this as a big memory space and moves stuff around to try to get stuff that's going to be used frequently into the SRAM and stuff that's going to be used less frequently into the DMRAM。

Okay。Yeah。So are you asking how to implement a content addressable memory？Right。嗯。Yeah。

 I'm not sure I understand the question。How位。Oh， yeah。

 I think your question is how to implement a content addressable memory。Right。

It'sI could describe a brute forceway， I'm pretty sure that's not what they do。I mean。

 I think there's a lot of cleverness in these circuits to do this right if you think about it。

 I mean， the simplest one would have say say you have a。Just a two line set。ok。嗯。

Then the only question right is does this one- so that in that case。

 you've got two tags available and you're presented with one and you just want to see which one matches。

Well， put two comparators in parallel。instead of doing a sequential search to put two comparators in parallel and one of them will give you a yes。

 one of them will give you a no or they'll both give you a no and you take the results of that circuit so you can always brute forces。

 but of course as the number of lines increases by that brute force technique。

 the number of comparators is going to increase exponentially。

with the number of lines so the circuitry would get complex and expensive。

 and so I'm sure people are a lot more clever than that。

 but I'm not an expert in the design of those circuits。Okay。

 one thing that I'd like to point out is that caches as a style。

 they do improve the performance for general purpose computing。

 but they do so at the expense of unpredictable and uncontrollable timing。

It can be extremely difficult to analyze the timing of a program in the presence of cash。Because。

You know the amount of time that a memory access is going to take is dependent now on many。

 many complicated factors， and it's really dependent on the complete state of the cache。

 as well as the history of accesses。Okay， the analysis problem becomes extremely difficult。

For general purpose computing， as long as your average case performance has improved。

 people are happy with that， but in embedded systems。

 this is often a problem where know if you have a safety critical system。

 you've got constraints on the timing， you have to design your systems for worse case。

And the worst case may be extremely pessimistic with a cache。

 and if you have to design the system for worst case。

 you might as well not have the cash because you're not going to get any benefit from it anyway。

 because you have to over provisionvis your system enough to be able to deliver the performance you need in the worst case as if you had no cash。

so it's quite common in embedded systems for people to simply turn off the cash。Okay。

 in a lot of architectures， you can just write to a memory map register and that tells it。

Don't use the gas。Okay， and then you get repeatable behavior more or less。

 if everything's going to DRAm， it's still complicated to analyze because the access times depend on the sequence of addresses。

So one of the things about these kinds of architectures is that there's been design choices made by computer architects along the way about what to optimize。

And one of the things that is worth observing。their first objective is to correctly execute the program。

An architecture that doesn't correctly execute a program is not a useful architecture。

 but what does correct mean？Okay， well， it means that it should behave as if the sequence of instructions executed in that sequence。

The end results of a computation should be the ones that are specified by the sequence of computations。

Correctness has nothing to do with timing， however。ok。

And so timing becomes purely a performance metric for the architects。

 and they don't worry so much about trying to deliver repeatable timing to。You know。

 to the end system designers。So it's kind of interesting that in an embedded system context。

 you often see people using architectures that are。Pretty old fashioned， actually。They you know。

 the architectures don't have a lot of the innovations of the last 40 years of computer architecture because they need to control timing and many of those innovations just get in the way of controlling timing。

So。All right， so that's enough on memory architecture。 Let me turn to。



![](img/bd25340109397217e7475ccc2c610923_5.png)

Today's topic。

![](img/bd25340109397217e7475ccc2c610923_7.png)

Interfacing sensors and actuators。ok。嗯。So logically。

The problem here is about connecting the cyber world and the physical world。

And the cyber world and the physical world have。Very different characters， okay。

 the cyber world is very algorithmic。In fact， the very notion of computation is algorithmic。

 it's sequences of steps。 the Turing church notion of what a computation is is a sequence of transformations of state that terminates。

 that's what a computation is by definition。The physical world doesn't have that nature。

 the physical world things are happening in a continuum。

 you can get into quantum mechanics arguments about whether it really is a continuum。

 but for practical purposes it's a continuum。It's extremely concurrent， right， I mean。

 just in this room， there's way more concurrency than on any of our computers。

Lots of stuff going on at once。All interacting and interacting in a continuum。

And bridging these two worlds is really what this。啊。

Pro of cyber physical systems is about and you confront directly。

 you know the digital nature versus the continuum， the discrete in time versus continuous in time。

 the sequential nature of computation versus the concurrent nature of the physical world。ok。

The physical world isn't algorithmic， algorithms are a human construction。嗯。

In addition to kind of this philosophical gap， there's very practical challenges that are， I think。

 a direct consequence of the physical gap。嗯。You know。

Should your connections be wired or wireless that actually。Is， you know， kind of。

Connected to this basic semantic problem， should they be serial versus parallel？

If you're trying to convey a sequence of bits from one place to another or a set of bits。

 should you put them on a set of wires？Or should you serialize them through a single wire？ok。

So these are the kinds of issues that we're going to look at today。

 and I'm really going to focus more on the practical side than on the philosophical side。So。

Here's a typical microcomputer board that you might use in an embedded systems project。

 some of you in your projects will probably use this very same board， or you might use an Arduino。

 which is kind of a similar sort of architecture。This one happens to be a a bele bone。And it has。

A processor on it and a whole bunch of digital and analog inputs。

And what we're going to look at today is what are these inputs， outputs， how do they work。

 how do you use them？And how do you build systems out of them， okay？Now。

How many of you have used an Arduino or a bele bone before？A lot of you good。

They're extremely common among hobbyists right and they're really wonderful platforms Arduino is mostly open source。

 Beale bone is more closed source， a little more tightly controlled by TI， but also。More high end。

 right the bele bones tend to have more a bit more capability。

 although there's a constant race there。Anyway， everything I say about bele bones will pretty much also apply to Arduino platforms in fact。

 they have a similar mechanism for interacting with external hardware in the case of Arduino it's called a shield in the case of bele bone they call it a cape because they have this cute logo of a dog wearing a cape and the capes all have to have this little gap in them to allow for that ethernet interface so the form factor always has this little gap which makes it look like a cape they say。

The cape just。You flip this guy over and plug it in and the headers along here。Plug into these guys。

 okay I guess on the other side， into the pins。And then the headers are relayed to the next level up in the board so you can actually stack the capes。

Okay， similar to the Arduino shields。And。There's you know kind of a couple of different ways you can use this。

 you can use this as you know， most hobbyists do， you buy your Arduino， you buy your shield。

And you plug them together and you get some sample code that you download from the web that gets it working basically。

 and then you start developing your application by modifying that sample code。

 very straightforward way to do it。But a much more interesting thing to do that some of you will probably want to do in your projects is to actually connect hardware。

 your own hardware of your own design， to these headers。

And maybe using a cape that has a protoboard on it。

 which makes it relatively convenient to make connections。And。

Now you can build your own hardware to talk to these things。 Now， the question is。

 how do you do that？RightAnd that's kind of the question that I'm going to address today and even if you know I mean。

In my experience in the past。Probably less than well maybe half the projects that actually do some hardware work and it's projects that have where the team is some doubly focused people。

And the other half of the projects will work more at the component level and won't be building their own hardware at all。

 but that's fine， but even if you're working at the component level you really kind of need to know how the hardware works in order to do a good job with embedded systems today later you in the future maybe the layers of abstraction will get much better。

 but today the layers of abstraction are not very good。

 and you really do need to get down and dirty and understand the hardware even if you're not doing hardware design。

 you're doing software design okay。So。You can go and look at the spec sheet for the bele bone black。

 and it's very colorful。And very confusing。ok。Lots of mysterious acronyms。

Here's one of the tables from this bigle Bo black documentation。 This gives one of， I think。

 eight different configurations， so eight different configurations for the board that means。

How do you choose a configuration for the board， what do you think？Yeah。Yeah， but mechanically。

 how would you specify， how do you tell the board to use this configuration？Firmware。

 but what do you do in firmware？Right， so you'll write to a memory map register。

And if there's eight configurations， you have to specify three bits。Okay。

 so in this memory map register， you're going to pick a three bit number。That's going to say。

This is what I want the headers to look like。Because this is one of eight tables in the documentation。

And this table says， well。Everything on the header labeled P8。

 which I believe is the one on the right， I think I can almost read it on the circuit board。

down at the bottom under that header， there is a label printed onto the circuit board that I think says P8 right there。

 so P8 means it's got these many pins and in this configuration all of these are configured to be GPIO。

 general purpose IO。General purpose， I owe， well， what's that？Okay， well。

 GPIO is kind of what it says。It's a general purpose， well， maybe not that general。What can it do？

Under software control。You can make it， you can set it to be an output。

In which case your software can take this pin。And make it either five volts or ground。

You just set it high or low， under software control。Or you can have it be an input。Again。

 you write to a memory map register and you specify， I'd like this pin to be an input。

In which case you connect up a circuit to that pin that provides either five volts or ground。And。

And then your software reads whether it's 5 volts or ground from a memory map register。Okay。

 very basic mechanism， very simple， very straightforward。

 What do you think happens if you set this GPI open to be an output？

And then you wire a circuit to it that asserts five volts。Right？Well。

 it's a reasonable chance you'll fry the processor right？

If the external circuit is setting the pinned to five volts。And under software control。

 you tell it to set the pin to zero volts。It'll set the pin to zero volts。

 and you will have shorted out five volts in  zero volts。

And you'll get a substantial amount of current flowing through your processor。

 which will cause it to get very hot。And may cause it to fail。Okay。

 so you got to know whether it's an input or an output under software control。

 and it's easy to make errors， and it's easy to make errors， you。

 suppose that the memory map register that controls whether it's an input or an output gets overwritten by a stack overflow。

So something that was an input becomes an output。Okay。And it's wired to a circuit。Well。

That stuff happens。Okay， it can happen， so you kind of have to be aware of what's going on。Okay。

So wired connections。 So there's a few of the others in here that I think are a little more interesting on this pin。

 let's see。These SPIO pins， these are a particular serial convention for serial ports。Yeah。

So let's look at what some of the possibilities are。

Some of the wired connections that are fairly widely used。You have parallel connections。

 you have serial connections， and you have mixed connections。

So parallel connections are ones where essentially you have one wire per bit。

There's a couple of parallel connectors up at the top， PCI and Szi as it's known。

Both of which are pretty much。Obsolete。Okay。In fact。In fact。

 all the app parallel connections listed here are obsolete。

They've all been replaced by serial connections， some of which are also obsolete。So RS 232。

 anybody know how old that is？Yeah。All right， how old？50。No，50。Yeah。

 it was developed in the 1950s to talk to teletypes or actually even earlier。Okay。

It's a protocol for talking to teletype machines。All right。It's a serial port connection。

 I'll tell you a little bit about it because it actually gives some insight into the design of these。

So more recent are。As this spy connection， serial peripheral interface bus， and you can see。

These guys， there's actually two serial interface buses available on the header in this configuration of the board。

So what you might get， when you buy a cape for this board。One of these guys。

It'll typically specify which configuration works with this cape。

 because maybe it uses the S connection。To talk to the processor。Okay， on the circuitry。All right。嗯。

USB， of course is familiar to all of you， right？RSS 232 is kind of interesting when it was first developed for teletypes。

 the wires that were used to connect to it had 25 wires in them。嗯。

Only two of which were used to carry data。One in one direction and the other in the other direction。

Why did they have all the other wires？There's a。There was a lot of control logic， right。

 so there's a wire for what they call a clear toend， CTS。Okay。

 don't send me a bit unless I send you a clear to send。And then they got carried away。

 they put a whole communication protocol where everything you wanted to say in the communication protocol had its own wire。

Okay。Today that would be a really silly design USB has four wires。Okay， that's it。

 so it's a much more much leaner electrical connection。Than RS232 and even RS232。

 most of the 25 wires got。Thrown out jettisoned and so RS232 connectors that are more modern。

 maybe only 30 years old， have nine wires in them instead of 25。Which is still too many。

But it's a lot of control wires。Now。Why have the parallel connectors been replaced by the serial ones？

Yes。Yeah。That's exactly right， the issue is that the conventional wisdom in these choices was that。

 well， more wires should give you more bandwidth。Because you can send a whole bunch of bits at once。

Instead of having to serialize them over the same wire。

But it turned out that the limiting factor for performance on multiple wires is the skew between the wires。

The destination has to latch the voltages all at the same time。

And if the propagation delays are a little bit different in one wire than in the other。

 then you have to be rather conservative and slow down the latching。

And it turns out that you can outperform the parallel connections with serial connections today because the circuits can be fast enough。

That you don't have this sw problem anymore if you send all of your bits over the same serial line。

So it's a little bit counterintuitive because normally you would think， well。

 more wires must give me more bandwidth。But it turns out to be harder to make use of more wires。

More modern technologies。 so PCI Express， for example， is a common bus architecture for extending。嗯。

You know， processors， like in fact， it's used in the lab。In the lab setups。

 you've got basically a single board PC and then a bunch of plugin slots。

That have devices like oscilloscopes and voltage generators and signal generators and so on that you can control under software。

 those are all communicating using a PCI express bus。

And this is actually a hybrid of parallel material。 It's a bunch of serial lines that can be used。

 can be aggregated into a bunch of lanes that are used to combine a single communication。

So it kind of gets the best of both worlds， it doesn't require the synchronization。

 the uniform latching。Of the signal for the old fashioned parallel connections。

 but the control logic for it is more complex also。

 so it takes a lot more circuitry to support this yeah。It kind of does。

 it gets rid of the skew problem at the next layer beyond the physical layer。

 the sw problem is occurs if you have，You say you want to convey a byte。

So you've got eight wires coming in if you use a parallel connection。

 you want to know what the value of the byte is。The most straightforward circuit。

Takes a snapshot of the voltages on those eight wires at the same time。ok。And then that's your bite。

In PCI Express it doesn't do that what it does is each of the eight wires will actually convey a sequence of bits okay and then those get。

呃。Captured。As independent sequences and then they get buffered and later on you count the bits and you align these bits at later stages in the circuitry。

 but you don't have to latch everything at once， so the wire skew problem doesn't bite you as badly。

Yeah。Yeah， you you I mean。At the physical level， parallel versus serial just means how many wires do you have。

 but there's a protocol level also because the idea there's several aspects to each of these standards right one of the aspects is just what is a physical connector。

Another aspect is what are the electrical specifications on the physical connector， so RS232。

 for example， requires 12 volt signals because that's what teletypepes used。T12 volt signals。

 very awkward for today's processors where you don't usually have a 12 volt supply。Okay。

Then there's a protocol level on top of that， right。

 when can you assert a voltage on a wire and when should you capture the voltage from a wire？Right。

Yeah。Because USB has the tremendous convenience of a nice light wire。It's thin。

If you put more wires in there， it's going to get bulkier。PCI Express has a lot of wires。

 but it's on a back plane， it's not being used for cabling。ok。

So there's lots of trade offs in these designs， right？Okay。

Let's look in a little more detail of GPIO。So。嗯。The way that GPIO works is you have a microcontroller and a pin。

Coming out of it。And you can use it as an output or an input。And a typical configuration。

 if it's being used as an output， uses what is called this open collector circuit。ok。

So you have a memory map to register。And if you write a one into the position。呃。

In this memory map register that is controlling this GPIO pin。Then it turns on this transistor。Okay。

Which will。Short pin to ground。Okay。Asserting a low voltage level on the pin。

If you write a zero into the memory location。Then the transistor turns off。

 so there's no connection to ground from the pin to ground。

And now you externally have a pull up resistor。Which will set the voltage to5 volts or3 volts。

 depending on what your supply voltage is。 if there's no current flowing。

 there's not going to be any voltage drop across the resistor。

So the voltage read on the pin will be five volts。At that point， okay？Now。

 the reason that open collector circuits are used is that you can now wire a whole bunch of microcontrollers together。

I'm using the same GPI op。And you get what's called a wired or if any one of the microcontrollers。

Connects to ground， the whole bus。Goes to ground。Okay。

So it's kind of a clever circuit that allows you to connect up a whole bunch of GPI opens together。

And now you can have something react to any request from any of the microprocessors。

It's called a wired or。So suppose， for example， that you'd like to use this to turn on an LED。 So。

 for example。You know， there's a。啊。A safety condition。And you're using triple modular redundancy。

 so you've got three distinct microprocessors all checking this safety condition。ok。

And you'd like to light up this LED if the safety condition is asserted by any one of the three。

Microprocessors。hen you could wire them up like this where you just put your LED between your pull up resistor and VDD。

 the power supply voltage right， and now if any one of the microprocessors shorts the bust to ground。

 the LED will light up。Make sense。ok。What should the value of the resistor be？

This is the thing that I want。To you guys to。Get out of。Today's lecture because。

If you don't understand the question， you're going to fry a processor in the lab。

So because you're going to be connecting stuff together and not all of it is going to be just you know。

 component stuff。嗯。So how would you choose the resistor value？Yes。Om's Law， yeah， so how exactly？

Yeah， that's exactly right， so you just use AlmMS's law， V equals IR。Okay。

And you need to know what your components are doing。

 so what is the voltage drop across the diode when it's turned on。

 you just get that from a spec sheet。Whatever diode you're using。Okay。

You figure that the rest of the voltage drop is across either the transistor or the resistor。

If you assume that the voltage drop across the transistor is zero， that's。

It's going to be pretty close to zero with the transistors that get used in this。

 so it does a pretty good job of shorting the pin to ground。Okay， so if you have a 3 volt supply。

 a2 volt drop across the diode。Then you're going to have a one volt drop across your resistor。

 And now you look up in your spec sheet to see how much current can you safely。

Sync through this GI open。The spec sheet for the processor that you're using will tell you that。

So say it says 18 milliampmps。Then you can calculate a bound on your resistor in this case。

 in order to not exceed 18 milliampmps， you need at least a 56 om resistor。Okay， so pick the next。

The smallest resistor that's greater than 56 ohms and connect that Why not just pick a much bigger resistor。

 Why don't I put a 1 kilom resistor。There。Sorry。Yeah， so how will that show up in your design。

 what why is that a problem？Having less current seems better than having more current。

 right you'll use less energy。Yes。Yeah， the LED will be really dim。

There not a lot of current flowing through the LED， it's not going to generate a lot of light。

If you're trying to alert a pilot to a danger condition， you want it to be bright。Yeah。Okay。

 so this is how you know kind of use spec sheets and check stuff out。All right。

 let's talk a little bit about serial connections。So RS 232 is kind of a nice case study because it's a pretty brute forest design。

 it was using， you know it was designed for some pretty primitive hardware。These days。嗯。

But it has a very simple idea。Right。The idea is that most of the time the wire is idle。

 nothing's happening， no voltage measurable。When you want to send a bite。

 you just send a single bite isolated。Okay， one bite at a time。

And the bite consists of first what they call a start bit that alerts。The guy at the other end， hey。

 I'm sending you a bite。ok。And what the guy at the other end does is， first of all。

 the two ends have to agree on the bit rate or as it's called in the field Bo rate。

That's being used Okay so if you're using 56 kilobo， that's a common one， that means 56。

000 Bs per second。Okay。Then when the receiver detects the start bit。

It simply starts latching the signal。At one over 56，000 seconds。Eight times。Okay。

And it gets 8 bits from that。 So it'll look at this1560th of a second later， then another2。

5600 of a second later，3，560 of a second later， and it gets a sequence of bits。Okay。嗯。In RS 232。

 the highest bit rate is 56，000 bits per second。Why？I mean。

 we can today we can make circuits that would be able to。Latch this at， you know。

Five nanoseconds later， 10 nanoseconds later， or even less。No。

 it actually it doesn't have anything to do with how long it takes the signal to propagate through wires because the whole signal flows。

Together。Right？It does tend to get distorted over the wire。

 right but that turns out not to be a dominant factor， so other ideas， yes， back of the room。

With the what？Capacitates though wire are not really。's particularly at these bit rates， you。

 these waveforms stay really quite clean over rather long distances of wire。Other ideas， yes。

Because of what？A larger voltage thing。Oh， you're saying that the voltage will degrade in the wire。

Yeah， yeah， that's not it either again， you know， it's pretty easy to make circuits that will generate a very clean waveform that will propagate very cleanly over a long wire and be almost perfect at the far end at these speeds。

 so that's not it yes。Why would you have to oversampble？Again， trust me。

 let's assume the waveform gets to the far end perfectly， no distortion。Okay。

All you have to do is sample it 15600th of a second later，2， 5600th of a second， 3。

5600th of a second， and then you're going to get your eight bits。嗯。Back of the room。嗯。

It is an old standard and they didn't imagine it， so that's a valid complaint。

 but that's not the reason。Yes。Sort of， it does have something to do with what。You know。

 the simplicity of the receiving circuit， but there's a very specific reason for this。Yes。No。

 that wasn't it either。Because are the what？No， that wasn't it either。All right， one more idea。

Clock tolerances， what's your name？That's it。I said， sample at 156，000 of a second later。

How do you know what 156000 of a second is？Well， you have a crystal oscillator。

And it's doing your time measurement。And these oscillators are pretty sloppy。

And they have tolerances。And the standard was designed to work with cheap crystal oscillators。

Could have a substantial error in them。And if you tried to transmit it higher than 156000 of a second。

Then the clock at the transmitter and the clock at the receiver could disagree by enough that what you think was 15600s of a second was off by enough that you would get a bit error by the time you got to the eighth bit。

So no matter how good your clocks are。Your first sample is going to be a little bit off in time。

Your second sample is going to be a little bit more off in time。

Because the clock at the transmitter and the clock at the receiver don't run at exactly the same rate。

Okay， the clock error compounds with each subsequent bit， which is， by the way。

 why you only transmit eight bits at a time。Not 16， not 64， not 128，8。ok。And。Then yeah。

 so it was clock tolerances that determined this maximum rate because it allowed you to then design equipment with cheap oscillators。

That have fairly sloppy clock measurements， and you could still get reliable communication。

Makes sense。So by the way， USB still uses this same principle， okay。

 it's just clock tolerances are a lot tighter， circuits are a lot better， bit rates are much higher。

 you can get gigabits per second through USB。Okay。But it's still an asynchronous protocol asynchronous means。

The transmitter and the receiver are not sharing a clock。They have their independent clocks。Okay。

And there's errors when you have independent clocks。O。So a UA is， in fact。A device that。I。In fact。

The mechanism by which you use a serial port interface， so whether it's USB or RS232。

There's a UAt involved， and the way that this works is basically when you have a byte， eight bits。

You need to convert that into a sequence of voltages on the output。

 and the U takes care of that transmission。But it also takes care of the receiving end。

 so when it on the incoming line， when it sees a startk bit。

 it starts latching signals and then it sticks the eight bits into a register which you can then read in the software。

 on the digital side， there's also a memory map register that tells you not only what the data is that it read。

 but also whether data arrived。so you can read a memory map register to determine whether anything came in on that serial line。

ok。So here's an example of how you could use it right。

Sort of torture you with some real low level programming here。Okay。

 here's a little snippet of C code。嗯。And。It looks like a sort of magic incantation。

 what is this while not UCSR0A and 0 x20？What's that wild statement doing？Yes。

It's checking a bit somewhere and it's waiting until that bit does what。It's。Because of the bang。

 it's waiting for that bit to be zero。So specifically， it's looking at the sixth bit。

At a memory location that is given by， what is that UCSR 0A？It doesn't look like C。Yeah。

 it's somehow referring to a memory mapped register， the contents of a memory map register， how。

I mean， it looks like a C variable。But it's actually， if you look at the program here。

 it's not declared as a C variable。Yeah， it's actually a macro。

That's defined in a header file somewhere， and when I'm sure if you've programmed an Arduino。

You've seen programs like this where you have to include a particular header and then you do these magic incantations that don't look like C really。

 but the sample code did it and it worked so you do it and it works right I call that the Harry Potter style of programming。

Which is you learn the magic spell， well UC see our0A bang。Yeah。😊。

But you don't have any idea why that makes it happen。Okay。

I'd like to ensure that by the end of this course， you have the confidence that you can。

Find out exactly how that works。 By the way， a search engine on your disk is really nice on my Mac。😊。

A lot of times when I'm working with a piece of C code and I say， what is that symbol， you know。

 I'll just go to my search window at the top and type in UCR0A and look at what it shows me and there's a dot H file that matches。

I open that dot H file and I go and look at what's in it。

And you can figure out what this C program is really doing by looking at that dot H file and you can get a lot of insight。

Okay， yeah， so the while statement is just waiting。

 the notice the body of the file statement is empty。

So it just waits until this bit in this memory map register is zero。Okay。And then。So presumably。

 the bit in the memory map register says。That you art something serial is ready on 0 a or something like that。

 it's some real cryptic， but it's telling you that it's ready to send。

Your UAt is ready to receive a bite。Okay， their software can give it a bitete and it'll send out the byte。

And so the next line uses a similar macro and writes a byte to some memory map location。

 which goes into the UA， and then the hardware takes over and serializes that byte out on the wires。

So if you want to send a sequence of bytes。You could use some code like this。

The sequence of bytes is in a byte array。And。You wait for your U art to be ready。

Then you give it a bite， then you wait for it to be ready again， you give it another bite。

So let's figure this out， how long does it take to execute that four lines of C code？All。

 so let's assume。57600 ba， that's actually the maximum RS232， right？Okay。嗯。

And you're going to send eight bits。So I'm a little sloppy here because I probably should count the start bit too。

 so that really should be nine。plus you're required to have a stop bit which is just a zero。

 a trailing zero， okay a trailing ground， sometimes two stop bits which just means more guard time。

 so maybe it should be a 10， but it doesn't matter we're interested in the ballpark right so it's got to be bigger than eight anyway。

 so it's going to take at least 139 microseconds to send out a bite。

So that means it's going to take 139 microseconds before the U is going to be ready again。

So the wild statement is going to have to wait 139 microseconds。How much is that？Well。

 if the processor operates at 18 megahertz， you can figure out how many instruction cycles it is。

Okay， and it turns out that。Each pass through the wild loop takes 2，500 cycles。ok。Meaning。

Instead of sitting there in that wild loop， doing nothing， waiting for the UA。

You could have executed 2500 instructions and done something useful。Instead。

 you had your processor just sitting there waiting for incredibly slow hardware to catch up。Okay。

So it looks like a short snippet of code。It's consuming an awful lot of resources。

It's also consuming a lot of power， by the way。Each of these reads。

 puts a voltage on an address line， gets a response from the memory map register。

 there's a lot of energy consumption in this kind of busy way。

So it's going to drain in your battery as well， pretty lousy design， actually。嗯。

So you can receive similarly。 So notice this uses the same memory map register。

 but it looks at a different bit。Okay， instead of using looking at the sixth bit。

 it's looking at the。8th bit。In that register。And that bit is where the UA tells you， oh。

 I've received something， something has come in over the serial line。

 I've got it here if you want it。Okay， so this is just waiting for something to come in over your serial line and then writing it to。

诶朕。Location。Now。What if nothing comes in over the she line？

What if you're running this C code and somebody trips over the cable？So it becomes disconnected。

What's the program going to do？It's going to freeze。Okay。就。What do you do then？

Pull up your Apple menu and say， know， kill。Force quit the application， well。

 what if you don't have an operating system？嗯。You know。

 this could freeze your whole system right just because of a single hardware failure， so again。

 a really lousy design。All right。嗯。And again， you can calculate how long this is going to take。

So let me talk a little bit about how this maps into the hardware that you're using in the lab。

 so this is the hardware that you're going to use。嗯。Which is an interesting architecture。

A little bit of a kind of a compromise architecture that is。

Fulfilling a lot of conflicting requirements that we had in the design of the lab。So in some ways。

 it's not ideal。 The tool chain is a little more complex than I would like。But。

That's the reality of the real world as well， so facing a complex stool chain is not necessarily a new thing。

It's a pretty sophisticated piece of hardware， though。

 it's got a arm cortex A9 dual core processor running Linux。

So that's very convenient because you can SSH into it and talk to the processor in ways that are fairly high level。

 which is a lot harder with a low level embedded processor。

But we wanted you to have experience with low level embedded processors。

 and so the strategy that we used here was to preconfigure the FPGA that's on the board with what's called a soft core。

Which is a microprocessor， it's a 32 bit microcontroller。

That is just configured on this field programmable Gator array that's on the board。

If there are hardware designers among you。You might be you might want to design some other hardware to go on this FBGA at some point。

 but that's not something we do in this class， we don't really expect you to do any hardware design at that level。

嗯。So we give you a preconfigured personality for the FPGA。

 which has a 32 bit microblaze microprocessor， and that processor is the one that you're going to program at the bare iron level。

With no operating system。 So it's kind of a convenient。Combination， because the board itself。

Running Linux。Will stay running very reliably， pretty much whatever you do in the micropase。

 even if you write code like this。the microbllaze may freeze。

 but the Linux processor will keep working and you can probe things and reset them under software control。

The microbze architecture， however， is a little bit of an idiosyncratic processor。

 I'd rather you were doing the bear iron programming on an arm， for example， than a microblaze。

And it's idiosyncratic for a very specific reason， which is it's meant to go onto an FPGA where you're going to connect it to custom hardware。

And we're not really using it that way， we're using it as a generic microprocessor。

So when you look at the documentation， the documentation for this processor is written for hardware designers。

 which makes it a little harder to read if you're a software person。嗯。But。

You'll figure out how to demystify it。Here's a table of some acronyms。

And the basic trick is going to be to think of it as the personality is just like what I've described to you for processors in general。

Your address space includes a bunch of memory map registers for peripherals。

It includes some regions that are referring to memory。You need to know what those are。

 those are defined in this personality。So you can do things like。Access eight digital eyeOs。

 GPI opens。Unfortunately。DIO and GPIO mean the same thing， two different acronyms for the same thing。

 but you'll get used to that。嗯。And you'll see some of these same mysterious symbols。

 So there's a mysterious symbol， DIO。1，5，8。 That means bits 15 through 8。Okay。

 of a particular header。Confired as an output。Okay this is something defined in a header file。And。

It's a pound defined in a header file。And if you write to their memory location， defined by this guy。

You will assert。The value of pins 8 through 15 on the header on the board， okay。

 set the voltages at that header to higher low。So this is the kind of thing that you're going to be kind of demystifying as you work in the lab to get control over the hardware。



![](img/bd25340109397217e7475ccc2c610923_9.png)

Okay， everything I've talked about is interfacing at a very low level so far。

I'd like to pop up a level and talk a little bit about networking。Okay because。嗯。Networks are useful。

 you might have noticed。ok。In the context of embedded systems。

 there's a long history of domain specific networking technologies。

Can controller area networks as were invented by Bosch in the early 1980s。

To control machinery on factory floors。Okay， and to coordinate。Communication within cars。

 So in cars you've got。Typically many microprocessors。They're interacting with a lot of hardware。

 things like traction control systems and the like on the cars。

And there's a lot of time critical behavior。In those systems， and at least at that time。

 people thought， well。The networking technology that's developed for general purpose computing like Ethernet and TCPIP over Ethernet。

It doesnn't give you enough control over timing， it best effort technology。

 it's not good for safety critical systems， so they develop their own networking technology。嗯。

And it persists， but it's slowly starting to creep in。

 you know the more generic networking technology is。

Particularly with the advent of clock synchronization， which I'll talk a little bit about next time。

It's starting to get used in more safety critical applications。Actually。

 it was going to talk about clock synchronization right now。So。What is clock synchronization。

 So I mentioned you know with RS232 that the rate limitation is due to the inability of the clocks that the two ends to perfectly agree on the rate at which time is progressing。

If you can get clocks to agree。There's a lot of stuff you can do that is much more powerful than having completely disjoint clocks。

Okay， think about your use of wireless networks， for example。If you can have clocks that agree。

 you can coordinate the use of wireless networks much more effectively。

One of my favorite stories about the power of synchronizing clocks comes from my colleague。

 Chris Pester， who started a company called Dust Networks。

To make sensor network devices and the devices that they were trying to make are small battery powered sensors with wireless communication。

That could be deployed in the field and last for years on， say， a coin cell battery。

So a typical application of this， for example， I was on the dissertation committee for one of his students recently。

 who， as part of his thesis， did a wireless sensor network system deployment and design and analysis for the Chevron。

perochemical plant up in Richmond， where they deployed hundreds or thousands of battery powered sensors all around the perimeter of this very large sprawling petrochemical plant。

To。Detect intruders， detect leaks， detect fires， things like that。

 so they had a variety of different sensors， all mesh network。Now。The problem。With a。

Battery operated a device that's wanting to communicate by radio with other devices。Is that。

If you want to be able to send data to that device， the radio needs to be on。The radio is not on。

 it's not going to hear the data you send it。But if you leave the radio on。

 the battery is going to go dead。If it's a really good radio design。

 the battery is going to go dead in a week。And they want the battery to last five years。

So what do you do？You synchronize clocks。 it turns out you can run clocks with very low energy。

We know that already， right？You're wearing a wristwatch。

 I think the Apple wristwatch being announced today。

Will consume a little more energy and probably won't run a week。

 but old fashioned wristwat is can run for years on a tiny little battery and keep very precise time so we can make clocks that are very energy efficient。

But they're not perfectly synchronized， they will drift over time。

 they will disagree on the current time of day， but if you can get them to agree。

Then you can have all your battery powered devices wake up at the same time， communicate。

 and then go back to sleep。And then sometime later， wake up again， communicate， and go back to sleep。

But if the clocks drift， this clock is a little faster than this one。Then。

This one's going to wake up too early and this one's going to wake up too late and they're going to miss each other。

So you have to actually synchronize the clocks。And there's a variety of different ways of doing this。

 this is one of my favorite ones because。develops truly it can be used to get extremely astonishingly precise。

Cs synchronization。So this is used on wired ethernet networks and you can when it was first the first。

Product release came out in 2007， and it was a。An ethernet physical interface chip made by national semiconductor。

 and they advertised that you could have clocks that would agree to。

Approximately eight nanoseconds is what they were advertising。

So two clocks separated by a kilometer of cable。If you ask them at the same time， what time is it？

They will agree within eight nanoseconds。Okay。This is a nanosecond at the speed of light。

So that's not a trivial thing to do， but it's been improved since then。

At a project at Cern in Switzerland and France， so CEern runs this project called the Large Hadron Collider。

 and this is a picture of the large Hadedron Collider under construction。

 these are catwalks to give you a sense of the scale so this cavity is about the size of a fourtory building inside okay。

The large Hadedron Collider is a 27 kilometer ring that straddles the French Swiss border。

 so it crosses the border twice。Okay， so it's about 10 kilometers in diameter。

And in the Cern project， they can synchronize a clock here and a clock here。

To precisions of about 80 picoseconds。Which at the speed of light is about that far。ok。

So they use this to orchestrate physics experiments so they can effectively get simultaneous measurements and simultaneous control。

In machinery 10 kilometers apart。Because they're able to synchronize these clocks to this extremely high precision。

You might remember two years ago， there was a big splash because some physicists had discovered that neutrinos were traveling faster than the speed of light。

嗯。And you know when they announced this， they said there's probably。A flaw in our experiment。

 but we can't find it。Okay， and this is what the measurement is telling us。 It looks like， you know。

 neutrinos are traveling faster than the speed of light yeah。About 100 people， yeah。

None of them could find it， and they had really done their homework， I mean they had really。Tried。

Everything they could to figure out what could possibly have gone wrong with this experiment。

 but no they were getting repeatable results， neutrinos were going faster than the speed of light。

And it was a graduate student at CEern who used this IEE 1588 protocol。

To find their experimental flaw。 And he discovered that they had， in fact。

 had very carefully synchronized clocks。But there was a loose connector somewhere。

 and it turned out that their synchronization protocol was affected by that loose connector。

 and so the clocks， you know， even though they had done the theoretical analysis that said these clocks would be synchronized within this precision。

 they weren't。And using this IEE 1588 technology， this grad student was able to find the experimental flaw。

The order of the universe was restored because neutrinos don't in fact go faster than the speed of light。

Okay， so we'll pick up on that next time， I'll explain to you next time how clock synchronization actually works。

 and then we'll talk a little more about higher level network level interfaces。

