# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p13 -13- L10_ Microarchitecture Fundamentals and Design II (Spring 2025).zh_en -BV1iV1XBWEJW_p13-

Going the speak。

![](img/69b2ec35480162aae1719352b12f7da7_1.png)

Yeah。I can go to the conference。是的那。coming here very great today。あ。然后。Thank。😊，そ然。Yeah。Is it good。

 okay？Oh good， thank you。对。那么还不是。是个。楽してくれまね。Oh。Oh good。う。四个都可。🎼。Yeah。Okay， let's get started。嗯。Yesす。

Let me reduce this a little bit。 Okay， can you hear me in the back， Everything's good。Okay。

So today we're going to continue the micro architecture that we started yesterday but。

Just as a reminder。This is your last day， today is March 21st， let's see we got the date correct。

 you can verify。Over here and here。And then there's another assignment coming up。

 so we've covered a lot of ISA today we're going to implement the ISA。

 as I said yesterday we actually start implementing the ISA。

 but now we're going to do it in a let's say， bare bones manner start from the beginning。😊。

These are the readings and just to jog your memory。

 what we were covering is really a very basic instruction processing engine。😊。

We were covering a single cycle machine， meaning each instruction takes a single clock cycle to execute。

 and we use only combinational logic to implement the instruction execution itself。😊。

So we won't have any intermediate program I state updates， so this is what we were discussing。

 you have an architectural state at the beginning of a clock cycle。

 you process an instruction in one clock cycle and then you have architectural state prime at the end of the clock cycle and then that will be the input to the next instruction and you process that instruction in the next cycle and that you'll produce architectural state prime prime and you keep doing this basically。

😊，Okay， we will see why this is a bad idea， it'll become more clear。

 but this is a very simple way of thinking about a micro architectureitect and this is what the micro architectureiture kind of looks like and we're going to build this actually your sequential logic。

 sequential state is really the architectural state， which is the programmer visible state。

 memory general press registers and program counter。😊。

And we've already discussed what is the clock cycle time of this is determined by。

 which is the critical path of this combination logic。

 and that critical path is determined by how fast you can process a given instruction。

 essentially in a single cycle machine， all state updates are made at the end of an instruction's execution and you execute everything in a single clock cycle。

 meaning that the slowest instruction determines your cycle time。😊。

And we will see we will calculate that this actually is not a good idea。

 it's you'll get a very long clock cycle time this way。😊。

Whereas on top of this we will build multicycle machines which are actually much more reasonable to build and we will see that the advantage over a single cycle is that slow stage will determine the clock cycle time meaning you can independently decide what your clock cycle time is you can say this is my target。

 this is what I'm going to try to achieve and then I'm going to break up instruction processing such that I'm going to achieve that target so this way you can optim things a lot better。

😊，Okay， these are some of the slides that I showed you yesterday at the very end。

 but you know the sort we have an instruction processing cycle and we're going to go through this instruction processing cycle and in a single cycle machine that phases of the instruction processing cycle take a single machine clock cycle to complete and compute essentially。

😊，In a multicycle machine all six phases can take multiple clock cycles that's the difference in fact each phase。

 for example， the fetch phase can take multiple clock cycles to complete in fact we have seen this right when we were actually discussing the ISA and the finiteheate machine for LC3 for example。

 we have seen that fetch state takes at least three clock cycles。😊，Okay。

 we're going to build up to that so let's let's start from scratch。

 but let me this is where we stopped actually yesterday we talked about we didn't talk about this。

 this was a slide that we didn't cover and this is a slide that I will introduce because this is the way we're going to build our machine。

😡，So we're going to essentially transform data to data prime。

 architectural state to architectural state prime， we're going to do in a single clock cycle to begin with。

Now to be able to do that， you need functional units that operate on the data， clear。

 these will do the function that is specified by every instruction， right？😡。

You also need some control units that tell the functional units and the wires， et cetera。

 to essentially do what to do with the data so there needs to be some control logic。😡，So as a result。

 an instruction processinging engine consists of two components， one is called the data path。

 which is really the first part kind of plus a bunch of other things。

 essentially these are the hardware elements that deal with and transform data signals。😊。

So the data signal that you get from the instruction register for example when you fetch well we won't have an instruction register to begin with in the single site I but the data that you get from the program count right that's some data and you need to process it and the data that you get out of the register file you need to process it how do you deal with that right so this consists of functional units that operate on the data ALU for example we will see again you had seen it in the combination logic but we will see it again and again and then a bunch of other hardware structures that enable the flow of data into the functional units as well as the registers in and out。

😊，These consists of everything that you've seen so far wires， Max multiplexers， decoders。

 triSt buffers， etc ceter， and also the storage unitss that store the data。

 these are all part of the data path because storage units need to store data and we will have store units like program counter needs to be stored in a register right general purpose registers need to be stored in a register file memory data and memory needs to be stored in a memory structure。

😡，So we're going to build this data path for essentially the instructions of interest today。😡。

But to really design a micro architecture， you should build a data path to execute every instruction。

😊，That is specified by that huge book， the manual， the ISA manual that we have seen last time。 Okay。

 so that's data path。And then you need to also design the control logic to essentially tell the data element。

 data path elements， what to do with the data， right These are essentially still hardware elements。

 You design some hardware logic。😊，That determine the control signals and these control signals are signals that specify what the data path elements should do with the data。

 So how do you control the multiplexors， for example， right that's one control signal。

 And we will see those control signals。 You've already seen it in the earlier architecture。

 but we're going to build it from scratch today。Does that make sense， Does that sound good。

 So I' really going to build a processor from scratch based on everything that we built on so far。

 of course。Okay we're going to first design the data path and then the control logic and if you look at what we had built I mean we didn't build this but we had assumed this and this was a multicycle machine actually so I'm going to ask you to forget about this this is a beautiful machine。

 multicycle much more realistic than what going to attempt what we're going to attempt to build today but you can see that theres there are data path elements。

 all of these are data path elements the processor bus memory register file ALU。

 the multiplexors another adder over here， a bunch of other stuff that are not shown here。

 there are data path elements try state buffers and then there's a control unit here which determines the control signals and if you remember I said that control signals in this particular picture is marked with arrows that are blank white at the end and data signals are marked with arrows that are black。

😊，And that's a very good way of distinguishing between control and data signals。

 but this control unit really orchestrates what the data path elements need to do to the data and when you design a machine。

 you normally take the specification of every instruction and you figure out how to design the data path first with some constraints and those constraints could be let's say minimize the hardware for example。

😊，After you design the data path， you decide how to generate the control signals to control the data path that you have designed。

 and we're going to do that。Okay， before we do that。

 let's take a look at how control and data are done in a single cycle versus multie machine。😊。

In a single cycle machine， everything happens in a single clock cycle， right。

 meaning you have to generate the control signals in the same clock cycle as the one during which data signals are operated on。

😊，So there's some delay that happens in generation of the control signals you take for example。

 you get the instruction from memory and you decode the instruction once you decode the instruction。

 you generate the control signals because control signals need to be determined based on what the instruction specifies right and after that you can actually control what's happening in the data path so this is kind of serialized processing right some of it can be overlapped of course when you design the combinational logic in fact hardware is very parallel but some of it is really serial you have no choice because you're doing everything specified by an instruction a given single clock cycle which means that the clock cycle is going to be long over here from a control and data processing perspective whereas a multicycle machine you have some more freedom。

😊，Essentially， you can generate the control signals that are needed in the next cycle。😊。

In the current cycle so while you're doing stuff in the current cycle you also generate the control signals that you need in the next cycle so that you don't serialize the control and data process。

 this is actually a very fundamental thing and important thing if you can do it of course in many cases you can do this in some cases you cannot do it because your control signals are really dependent on what you do in the current cycle and we will see some example cases also so this gives you more parallelism because you can overlap the latency of control processing control signal generation with data path operation this will become more clear also as we go along。

😡，Does that make sense so far， okay？Okay， so if you're really interested so appendix C in Patam Patel book has a very beautiful micro architectureit。

 which is the LC3 or LC3B micro architectureitect， it's a microprogram multicycle micro architectureure。

 we are going to build up to that hopefully by the end of today's lecture but we may not be able to cover everything so we may actually go to that in the next lecture let's see。

😊，So theyre also， it's good to also say that there are many ways of designing the data path and the control logic。

😡，对。So example ways we're going to see single cycle first， we're going to design that first。

 we're going to discuss the shortcomings of it and then we're going to move to have multicycle processor。

 and then we're going to discuss the shortcomings of it。

 we're going to build a pipeline processor and then we're going to discuss the shortcomings of it and we're going to build an out of order execution processor which is going to get you very close to what is really done today。

😊，And all of these require a different data path and different control。

Although some may be similar as we will see。So single and also there's another design choice we have a single bus or multiple buses in the system so the picture that you saw with LCC3 micro architectureitect。

 multicycle micro architectureecture has a single bus right remember that thing that's a big black thing that was a single bus but you could actually do multiple buses also your control complexity may increase so essentially your control complexityities depend on what you do in your data path if you do multiple buses you need to control multiple buses right。

😊，You can actually design the control logic as a hardwired combinational logic。

 or you can have a memory that gives you the control signals that's called micro coded micro programgram control。

 which we will also hopefully see。😊，Yeah， I already said this。Essentially。

 the key takeaway is that there are many ways of designing the data path and control signals and structure depend on the data path design。

 but you still have some freedom in terms of how you handle the control signals also。

 you could do hardwid versus microcoded， etcter。😡，So there are many。

 many design choices and these design choices essentially affect performance and today we're going to talk about performance。

 also we're going to break performance， meaning execution time into three components and how you actually design your data path and your control signals is going to be affect two of those components。

😡，One of those components as you will see will be independent of what you do in hardware。

 it's fairly dependent on the program。😡，Okay， hopefully that's a teaser。Okay。Okay。

 that's the performance， let's see。Have you ever seen the performance analysis of a program？

Like how you would compute， of course you run the program and get the results that's how many seconds it takes that's in the end。

 that's your performance right that's what you really care about。😊。

But if you don't have the hardware to begin with， how do you do performance analysis？😡。

So you would like to get the execution time of a program ideally and you would like to。

 if your goal is to maximize performance， you would like to minimize how long it takes to execute the program。

😡，And when you're designing hardware， it's good to have an idea of how you can optimize this right Now。

 let's take a look at let's let's again， build from first principles。

We are executing instructions one by one， right。We're assuming a very simple micro architecture right now。

 execution time of a single instruction is determined by really two things。😊，First。

 how long it takes， what is your clock cycle， how long is your clock cycle， that clock cycle time。

So it could be one nanosecond， for example， right it could be 0。

1 nanosecond that's your clock cycle time， you designed the machine。

 you have a clock cycle time somehow。And the second component is how many of those clock cycles are needed to finish this instruction that's called cycles per instruction or CPI。

😡，And this is your execution time of the instructor， these are the two components that you will have。

 hopefully a lot of freedom to optimize。😡，Does that make sense， hopefully this is very clear， right？

There's no other overhead because everything is included that overhead clock cycle time includes a combinational logic delay。

 sequential logic delay， all the timing analysis and cycles per instructions。

 how many cycles do you take to finish that instruction a given instruction right now we're looking at a single instruction。

😊，Let's look at an entire program， and entire programs hopefully doesn't consist of a single instruction。

 otherwise it won't be a very meaningful program。You really sum this quantity that I show at the top over all instructions that are executed to finish the program。

😡，Basically for every instruction that you need， it could be a billion instructions。

 aterion instructions。😡，Many， many instructions in existing machines like if you're doing for example。

 training for a huge language model， it could be days and days and days and days or months。

 et cetera so imagine how many instructions that could be。

 it doesn't matter whatever you execute use sum the cycles per instruction times the clock cycle time over all of the instructions that you execute okay。

😊，There's another way of thinking about this which is this way because you can now optimize things right so you can break this down as number of instructions you actually execute dynamic instructions。

 how many instructions times the average cycles per instruction that you get average across your entire program times the clock cycle time these are two things that are equal because we just express this thing as an average right？

😊，Okay。Now， if you want to optimize things。😡，If you want to reduce execution time。

 improve performance。😡，You can improve your goal is to reduce all of these clearly， right？😡，Ideally。

 you reduce the clock cycle time， how long it takes for the clock to switch。Ideally。

 you reduce the cycles per instruction and ideally， you reduce number of instructions。

Number of instructions in hardware we don't have a whole lot of control over。😡。

That's really controlled by how good your algorithm is if your algorithm gives you too many instructions like the LLMs of today。

 you're stuck with so many instructions right now if you come out with an algorithmic breakthrough you can reduce that by orders of magnitude that's good that will reduce your execution time。

😡，呃。Number of instructions is also affected by the ISA instructions at architecture。

So instructions that architecture actually affects this。

But instructions that architecture also affects the average CPI potentially。

 if your instructions are more complex， for example。

 you may have fewer instructions to implement something， but your instructions may take longer。

 so now you can see some tradeoffs over here at the architecture level also but we're going to assume number of instructions are constant given an ISA。

 given an instructions at architecture， number of instructions are constant because your compiler compiled it done compiler also affects the number of instructions。

😡，So at the micro architectureure level， given a program meaning set number of instructions。

 we can deal with average CP and clock cycle time those are our degrees of freedom。😡，Now。

 let's see that we have that degree of freedom in single cycle microqua。In a single cycle。

 micro architectureure， cycles per instruction is always one。Because by definition。

 we set single cycle， right every instruction takes a single clock cycle。And unfortunately。

 as we will see your clock cycle time will be long。

And that's why this is's one of the reasons why this is bad。If you do a multicycle。

 now cycles for instruction is going to be different for each instruction。😊。

And hopefully your clock cycle time will be short because you can determine that arbitrarily actually。

 and hopefully you design your my architecture such that average CPI is hopefully small。

 it's clearly going to be larger than one。😊，Because by definition， again， this is multi cyclee。

 right？So clearly， you can see a trade off between clock cycle time and CPI immediately。

And this is a very fundamental trade off as you reduce the clock cycle time。

 your cycles per instruction normally goes up。😊，Okay。

But the good thing about multicycle and this is why we're going to build to it is we have two degrees of freedom to optimize independently。

 like cycles for instruction and clock cycle time here， we won't have a degree of freedom。

 and we will see that it's going to be bad。😊，Does that make sense？O。Okay。

 now let's build our single cycle mark architecture from the ground up for a subset of MIPS instructions。

😡，This is our single cycle machine， and we're going to look at that。😊。

Now I'm going to build with some basic blocks， I'm going to follow this notation in the lecture and as you will see it's very similar to the notation that's followed by your book。

 it's good to actually get used to different notations because there are many。

 many different types of art designs in the world， but let's take a look at what we're going to use。

😊，So this is the program counter。It's always right enabled in this particular architecture。

 meaning every clock cycle it's like a register like we covered the D flip fl right if you remember it's like a flipflop at the rising edge of the clock cycle you capture the input that comes in and then for a full clock cycle the PC remains exactly what it was and then at the end of the clock cycle you capture the new value right we've seen this before we built it actually completely it's expensive but it's there。

😊，And then we will have our register file， remember this is the register file。

 I mean this looks complicated， but it's not really that complicated。

 this is what we're going to assume。😡，え。This is MIPS， so each register ID is five bits。😡。

By definition of the ISA， so you have 32 registers， right？

And MIPS are type instructions read two registers， so we're going to provide two ports to the register file。

 meaning we can read two things concurrently。And then we are going to also there could be a destination register that's called the right register and we can write to one register。

 each register will be 32 bits based on the definition of MIPS ISA again。

 and this is the data input that goes into the register file。And these are the inputs。

And these are the outputs of the register file， so when you actually supply the register IDs。

 it could be Reg ID5， Reg ID 7 for example， for read register  one and read registerister2。😊。

You get the data value stored in Reg ID 5 over here and Reg ID7 over here。😡，Makes sense。

 right This is basically memory。 you these are the two addresses that you can concurrently provide to the register file。

 and these are the two data values they can concurrently get from the register file。

And then there's a suspicious signal over here， it's a control signal。

 that's how we're going to denote the control signal that's called Greg W。

 this basically says are you writing to the register file also。😊，Does that make sense So redright。

 if redright is asserted， meaning if it's one。😡，Then the register file also writes the data into the destination Reg ID at the rising edge of the clock cycle。

 okay that's what we're going to assume right now， we're going to change that later on。

 there could be different ways of building the register file， okay。😡。

Meaning that the data that you're reading from the register file is available for the entire duration of the clock cycle and that data that you're writing to the register file gets captured at the end of the clock cycle。

😡，Makes sense， so that's why we designed everything that we designed in sequential logic before。😡。

Because we want that data to be available for the entire clock cycle because we're building a machine that operates on a single clock cycle in that current。

Okay， is this clear， register file， okay？Before I go into memory。

 memory operates in a very similar way， actually， but you actually know how to build a register file。

 So this is。😡，A register file， our simple register file with deep looppls。

 you have four entries and each entry is three bits。😊，Now， imagine expanding this to 32 entries。

 and you could easily do that。 You just need to supply five addresss over there。

And imagine expanding the y axis， meaning the data bits 232 instead of three， you can do 32。

Makes sense right so what are we seeing here the address bits are the register ID。😡，The data bits。

Not all databases the databases coming out are the outputs meaning the register that you're reading。

 so in order to read one register you supply the address bits。

 write enable signal let assume that it's your this the right right signal that you've seen you get the data out okay。

😡，Now this is only one port， but if you want more port then you need additional logic to supply another address right and you just replicate this address decoder。

 basically have another address decoder that could also operate concurrently such that you can access。

😡，Any register with another port。😡，Meaning that you need to have another set of addresses。

 another address decoder， another set of data bits coming out so that you can go out of the register the second report of the register file。

😡，Makes sense。So you just extend this basically and again if you write data。

 you can see right data and the right register over here， essentially when you do writeable。

 now you need to actually add a right port to this。

 meaning have another address and write there is a specialized right port in that case。

 and then these are the data bits that you're going to write into the register that is specified by the address bits。

😊，Okay， so you've already seen this way just extending it so that can you can read two values at a given time and write one value at a given time。

 okay， yes， when does it on the rising or following it。😡，So this is basically what we discussed。

 it doesn't matter rising and falling yet， you have the full clock cycle。

 but we're assuming that your data value gets captured at the rising edge。Okay。😊。

If you have one full clock cycle， basically。When one pop cycle ends。The next immediately is。Yes。

 exactly， exactly。 that's clock keeps going basically。Okay。

Okay so that was our register file I spent some time on this because now you build actually a multiported memory memory we're going to assume two different types of memories for this single cycle design。

 one is going to be the instruction memory and the other is going to be the data memory and we're going to assume even more on memory and this is going to be our killer meaning achilles seal of this design one of the a killers actually but still let's assume it so memory you supply an instruction address。

😊，And it gives you an instruction。So this is actually a magic memory in the sense that program counter because to get the instruction。

 what is the instruction address program counter right。

 program counter is 32 bits and MIPS 32 bits and MIPS。

 so we actually have a memory that we're assuming2 to 32 entries that's big and each entry has 32 bits that's the size of an instruction。

😊，And then you get the instruction at the end we you're not going to write to the memory the memory is always enabled okay data memory is similar except we're going to be able to write to the memory。

 so we have a single port over here， a single address， 32 bit address in MIPS。😡，诶。

If you supply that address and set this memory read signal to one。😡。

The memory provides the data at that address again very similar to this imagine actually this memory is much similar this memory is much similar to this than this because this is multiported。

 this is actually single ported where single port could be write or read port。😊。

As you will see so basically imagine this being 2 to 32 entries and each entry being 32 bits that's what this will look like and there's a right enable port and a memory right signal。

😊，So there's a right enable signal over here and write data is over here again。

 32 bits you can write So the only difference。😊，except for the size and et cea。

 the structures is this memory read signal， you don't really have to have it。

 but the reason these folks and also your book added that memory read signal is because you don't want to enable memory unless you're reading it right that saves energy。

😡，But with the assumptions that we're going to make， that read signal is really。

 really not needed strictly well actually。😊，Yeah， exactly。

 it's really not needed strictly because if you're not writing to memory。

 you set memory right to zero and you will always be reading from memory。😡。

This memory signal is when memory right is zero and memory is also zero。

 you're not doing anything to memory， so there should be something that dates that's not shown in the design of memory that we had。

Okay， hopefully that makes sense。Okay， so your book actually builds something very similar。

 as you can see， it's a bit。😊，Actually your book doesn't have the a read signal for example that that's okay。

 I think we should talk about energy as well if you're interested in actually learning more take a look at your book's notation also and I actually will talk about that a little bit as well。

😊，but we're not going to talk about the state elements in your book。

 everything' is explained in this chapter， so if you want to supplement what you've learned in this lecture。

 take a look at your book。Okay， what else are we going to assume？

We're going to assume these because we want things to be done a single cycle。

Which is a bad assumption clearly right So we're going to assume single cycle memory and register file。

 because otherwise， how are we going to get a single cycle machine。Right。Clearly。

 this assumption doesn't hold very well， but this is what we're going to issue so that we can actually understand how you build a data path in a single cycle。

😊，So we're going to assume combination of read output or the red data port。

 the combinational function of the memory content and the corresponding input address。

 which is essentially。😊，What this is。Okay。And then we're going to swim synchronous right。

 target location is updated at the positive edge clock transition when the right enable signal is asserted。

 meaning that we cannot effect read outputs in between positive clock edges。

 this is what we already discussed。😊，And single cycle memory。

 we're going to later contrast this with memory that takes multiple cycles。

 What if memory takes multiple cycles， Well， then we'll have a ready signal as we will see。

 but I'm getting ahead of myself。 Let's not talk about it。 Now let's build this machine。😊。

So this is kind of the machine that we're going to build， so if you think about it。

 there are generic steps instruction fetch fetch the instruction， decode the instruction。

 read the register file， execute the instruction or evaluate the memory address depending on which operation you're doing。

 you fetch the operate from memory you store the result into the register file okay。😊。

So this is kind of what we really need in a single cycle machine。

 you fetch the instruction from the address program counter。

 we input that to the instruction memory as the address。

 and at some point you get the instruction bits because there's some delay clearly in memory it will take I mean I set single cycle but it's going to be very fast memory essentially in the end or clock cycle will be longer than how long this memory itself takes because we need to do other stuff in this other things basically with this instruction and then we supply the instruction to the register porch part of the instruction because remember the encoding of the instruction specifies which part of the instruction are register IDs and we will see exactly what those are。

 that's the fetch， this is the thecode plus register file access and then we're going to generate some control signals over here which are not shown to decide what to do and or what registers to use。

 which register IDs， which instruction bits to use to actually index into the register file。

We're going to do some execution or generation of the address， and based on the signals。

 based on what type of instruction where executing the ALU function will be determined by the type of the instruction。

😊，And then whether we access memory or not is going to be determined by the type of instruction as well so we will generate control signals to control this data memory。

 I'm not showing the control signals over here and then eventually we will generate control signals to rights or not right to the register file but this is kind of our data path without the control signals shown remember why I said were going to design the data path first and that's why I kind of did over here。

😡，But we're going to do it at an instruction by instruction level now。Basically。

 to design a micro architecture， you need to provide the data path and control logic to execute all ISA instructions。

And this is what we're going to build up to。Does it look complicated？

Now maybe right now but this once you know how to design it it's really not that complicated this essentially contains some instructions and your book builds up to something similar with some other tradeoffs。

 but you can contrast this to your book there are some that are more realistic here in this design than your book like having a program counter for having a separate adder for incrementing the program counter that's what's done in real machines。

😊，Okay anyway okay so let's start we're going to build a single cycle data path for atic and logical instructions first and we're going to start with what you've seen in two lectures ago these are our type ALU instructions remember our type ALU instructions have two register opera a source and one register opera as a destination okay and this is the semantics that we're going to provide with a data path。

😊，呃。Essentially。This is an example instruction that's at。

 but essentially what we will need to do in this instruction is if the instruction is our type instruction。

 in this case， add， what we're going to do is access two source registers in the register file。

 get the data values。Set the ALU function to add and get the results and place it into the destination register。

😡，And concurrently we're going to increment the program counter， so at the end of the clock cycle。

 we should have this value in the general purpose register designated by RD。

 which is coming from those bits in the instruction as you can see。

 and your program counter should be incremented by four。😊，Make sense。

 right We've actually seen the logic， but now we're going to construct from the beginning。

 So based on what I've shown you earlier， a little bit more detail。

 this is the data path you need to enable this。 Let's look at PC plus4 first。 remember PCc。😊。

PC plus four， we have an adder over here okay and at the end of the clock cycle PC plus four will get latshed over here not not during the clock cycle because if you do it during the clock cycle。

 then you will mess up everything because youll start reading something else from a memory right。😡。

concurrently， at the same time， this PC is input to the read address report。😡。

Of the instruction memory， which is actually the only port you don't write the instruction memory。

 that's the assumption MIPS， there's no self modifying code okay。

Basically this read address and at some point later you get the instruction and to execute this instruction。

 you can see that one of the registers is specified by bits 25 to 21 in the instruction and codingting the other read register is 20 to 16 and the destination register is 15 to 11 makes sense。

😊，Okay， and these are sub。😊，And you will read the data clearly because there's no enable operation for the register file。

 so you read the data， data flows after some point， and we connect those data to the ALU。

And we set the ALU operation accordingly such that we get an addition which is specified by this function over here。

 remember the functioned part of the instruction， okay？😊。

So we're going to generate those control signals and because we're going to write the result to the destination register。

 the result goes into the data input port of the register file。

 we set the red right signal to one while we're executing this instruction。

And the destination register ID is supplied already by the instruction。

 so when this becomes available， it gets written into the destination register because we write enable the register file。

 okay。😊，And if your clock cycle is long enough to accommodate all of that logic。

 you should be able to execute of that instruction， hopefully it makes sense， right？

So there's no magic here we've built everything that you see in this figure。😡。

Okay so that's our ALU data path， our type data path so you need two control signals as you can see in assuming this data path this redite should be set to one AluU operation should be set based on the function coming from the upcode or the latter part of the up code at the end and this is the ALU design it comes from some control logic that generates the control signal so we're going it should be 010 for example that function these threeDs。

😊，Okay。So okay， that was our type。Now let's build on top of this eye type。😡。

So our eye type is kind of similar， you do an ad operation。😊，And there are other operations also。

 but you do it on one register， one source register， actually source register is this one。

 and you add to it assign sign extent immediate and you also increment the PC as usual so I'm going to ignore increment of the PC until we get the branch instructions and jump instructions。

But basically， you need to provide the data path to do this now。

 we already provided the data path to do a PC plus for。😡，So this is actually the data path。

 so if you think about it again I showed it over here， now your source register is something else。

 unfortunately， let me see oh no okay， your destination register is RT。😊。

So this we basically let's actually do the sign extended immediate These are the 16 bit coming from the bottom 16 bit of the instruction we sign extend it。

 it becomes 32 bits and we add it to the other input of the ALU the first input doesn't change it the data that you're reading from the source register okay so we provided the data pad for sign extended immediate。

And the result will go into the destination register。 Now， this is not perfectly correct because。呃。

Essentially， we also need to provide the data path for our type at the same time。

 so now we introduce a new control signal and two multiplexors。😡，And the idea over here is。

If the instruction is I type。This multiplexer would select。

The sign extend immediate to get input to the port second input of the ALU。

 if the instruction is not i type， this will be set to zero。

 meaning the data coming out of the register file like in our type earlier。

 willll go into the second input port makes sense， similarly there is a mess over here in the sense that the destination register ID is different in I type and R type。

 if you have followed what we've seen this is the destination Reg ID coming from bits 20 through 16 for i type instructions。

And the destination register ID for our type is really coming from bits 15 through 11。

 so if you're i type， you're going to select 20 through 16 as a destination register and if you're i type you if you're not i type。

 you're going to select destination register 15 through 11 as the destination。😊，So basically。

 you need to provide the data path elements to execute both our type and I type alien instructions and this is what it's needed。

😡，Does that make sense。It's unfortunately you need to obey the instruction encoding。

 somebody encoded those instructions that way and that was they were operating under some constraints and now we added extra hardware because our destination register in our type ID in our type is different from the destination register ID in our type。

😡，Okay， but this is the entire data path you need to execute I type and R type ALU instructions。

 and those differ only in the ALU operations， so this funt code determines what ALU operations you need to execute。

So you can execute andt， XOR， nor， et ceter。Okay， remember， this is actually to jog your me。

 similar things happen in other ISAs。😡，So if you look over here。😊，We have a multiplexer over here。

 this is the multiplexer in front of the second port of the ALU。

 you select from either the register file or sign extend immediate。

In LC3 and we have seen this earlier， so in different ISAs you see very similar structures because these are kind of similar IAs and there's something actually very similar in the register file that's not shown over here。

 but I'm not going to deal with that。😊，O。So that's the data type for data data path and some of the control signals。

 I didn't tell you how to exactly generate the control signals。

 but I kind of indicated that right if instruction is I type，😊。

You generate an eye type control signal is i type control signal。

 we're going to actually do that after we build the entire data path。Okay。

 let's take a look at data moment instructions this is a load instruction it's actually an i type instruction because of the structure destinations Rt as you can see over here 20 through 16。

😊，If this is a load instruction， this is how you calculate the address。

 you basically access general purpose register with a basease register Rs using bits 25 through 21 as the ID of the register。

 add to the data value that you get assign sign extended offset 16 bits， and that's the address。

 you input that into the memory， and then access memory， get the data。

 write the data value into the general purpose register specified by RT。😊。

Now you know how to do this hopefully， basically this was the data path that we had earlier。

 I kind of severed some connections over here。😊，But if you want to do a load。

 we're going to add a memory， of course， clearly， essentially everything is very similar to i type instructions。

😊，our destination register is i type basically we select the Rt bits coming from the instruction to decide the ID we're going to write to the register as we were doing with earlier instructions and we're going to now we're going to compute the address in the ALU to compute the address we're going to read the first register that's fine it's kind of i type earlier which is specified by some of the bits that we connected earlier to this input port and we're going to。

😊，Add to it as sineex and immediate， just like we did in the I type ad。

 We're going to set the Anu function to add。So everything is very similar type type instructions until we get to memory Okay。

 now what do we do， ALU result is not going to go to the register file。😡。

It's really going to be connected to the address。😡。

Input port to execute the load and we're going to set the memory right signal to zero because now we're not going to update the memory clearly there's a load not a store we're going to set memory read to one。

 we're going to enable the memory so that we don't waste energy if we're not enabling it okay and at some point memory gives you the data。

😊，We're not going to connect anything to write data because we're not writing to memory， Okay。

 and this read data needs to be supplied back。To the right data port of the register file。

 And our destination is already sent。 Okay， that is what you need to execute the load。Now。

 I was not extremely careful over here because this is just load we're going to actually。

We're going to actually complete this later on because if you want to execute the load as well as previous instructions that we've executed。

 there should be a multiplexer over here， right？😡，Because if you're executing an our type instruction the result the input to the destination register。

 the data value should come from the ALU result to here， if you're executing a load。

 the input to the destination register should come from here。

 so we're going to add that multiplexer later。😊，But I wanted to not add it here so that you can actually think about it。

If you want to execute right now， you can execute a load but nothing from the ALU operations。

 the R type and I type ALU operations with that multiplexer。

 you connect the ALU result into the right data port。

 but you need that multiplexer to select whether it's a load or not。😊，Okay， we will see that soon。

 But let's do the store while we are building the data pass store。 It very similar to load， except。

It calculates the address the same way except it's going to write the memory。

 we set the memory right signal to one。Now what is the right data？

Now write data comes from this second port that we use to read memorym。

So earlier in load we were reading from that second part， but it was kind of useless。

 we were actually selecting the sign extent immediate to go into the ALU and we were kind of not connecting this to anywhere else。

 but in store what you do is you take the base register。😡，Sorry。

 you take the register specified by Rt and supply it to the data port because you need to store the value of the register。

 sorry the value of the register into the memory okay， so if we're forming the data path。

 this is actually how data paths are formed， you look at the instruction。

 you look at and bond by one you add the wires， multiplexors and elements that are needed to execute that instruction。

😡，Make sense。Okay， and it's kind of messy to begin with。 And this is exactly how you do the mess。

 But control signals are important。 We're not reading from Me。 We're writing to Memy。

 So these are the store control signals。Okay， now this is Lord store together。左为可呃。

Ignoring all of the prior arithmetic and logical instructions。

 this is what you need to execute both loads and stores if it's a store you write to memory so this signal needs to be generated by someone if it's a load you read from memory but you don't write to me these are mutually exclusive clearly。

Okay， and then it's actually， if it's not a store， you write to the register。

 so you actually can think a little bit， but we're going to generate the control signals separately。

 but you can think about it， Think about whether this makes sense。 If it's not a store。

 you're going to write to the register， actually。Because it's a load， Okay， okay。

 now if you want to have both arithmetic and logical and load and store。

You just need to change this a little bit basically everything stays kind of the same。

 so it's unfortunately it's not aligned very nicely。

 but basically from here to here we just add this multiplexer。😡。

Because load and store are I type instructions and we already have mechanisms to execute i type instructions。

 but if you want to execute both load and store， destination register can come from either the result of the ALU in arithmetic and logical instructions or it can come from the output of the memory。

And the control signal that's needed to distinguish that is whether you're executing a load or not。

If you're not executing a load， then you're executing so far based on what weve built。

 you're executing a arithmetic and logical operation。😡，Or a store。呃。

Then the data comes from the LU result。And you write it to a destination register only if it's not a store。

 hopefully everything makes sense， right？Yes。Wouldnt it be nice to be able to store a value from the register but then not write it the different register。

Store a value to a register， but not write it to a difference sorry but Yes， you can you do it here。

 right？But if you。🎼Oh。🎼再遇到。Right。不。一般就对不对。So basically you're saying when we store。

 we store it to the memory， but you're not writing to the register right you set this control signal to zero。

😡，Okay。Okay， so we're doing exactly what you say。Okay， I'm not playing music here。Okay。

So let's quickly see the control flow of instructions and then let's take a break I think somebody is going to make an announcement also。

 so jump instruction， this is actually important because it's actually the unconditional branch as we have seen。

😊，And the idea is you again， take a， so whenever you want to add an instruction。

 create the data path for an instruction， you take the instruction。😡。

And then you basically figure out how to enable that execution of the instruction。

 this is the specification of the jump instruction。

Jump calculates the target address by concatednating this 26 bit immediate from the instruction。

At the bottom you have two zeros you add two zeros at the bottom。

 and at the top you actually take the top four bits of the incremented program count。

And then you set that target address you write that into the program count。

So this was our previous what we have actually considered， what we have built so far。

 now let's add jump to it。😊，Now to be able to execute jump， I want part of the instruction clearly。

 and I also want。😡，PC plus four and top four bits， I already have PC plus four。

 I just want to get the top four bits of that。😡，And I want to get to 26 bits from the instruction and add zero to it。

😡，So first of all， you set the control signals such that you do not do any harm and you can see that nothing over here is useful while you're executing the jump。

 right？😡，Does that make sense？Jump doesn't touch the ALU， Ju doesn't touch the memory。

 so you should not be doing anything to memory zero zero。😡。

You don't care what you're doing to the ALU， you don't care what you're doing here as long as do no harm。

 don't write to the register jumpmps is not writing to any register we're only going to update the program counter okay so let's take a look at this basically you take top 26 bits from the instruction。

😡，Concatenate to it， PC。And zeros at the bottom， and then we need a different way of updating the program count。

Because program counter can be increment or program counter can be supplied with a target address。

Now we need a multiplexer to enable that。And that multiplexia is controlled by a signal that's called PC source。

 but is jump is another way of thinking about it。Now， what I did was wrong。

And this is a very common mistake that people do。This doesn't obey the ISA， the ISA says。

The jump target address。Should come from incremented PC。

 What I did carelessly as a datapath designer is I took it from wherever was convenient。

I should not take it from here， I should really take it from here， okay。

 so you should never and you will easily make this mistake if you're not careful and a lot of ISAs have this PC plus4 thing because they usually are thinking of incrementing the PC and then doing something to it。

😡，So jump target address should really be coming from the incremented PC concatednated with 26 bit of the instruction and to zeros at the bottom。

😡，Makes sense， so you should be very careful with control instructions。Okay。

 but essentially now you have a philosophy right every instruction you need to provide the data path elements。

 plus the control signals， and whenever you know the specification of the instruction。

 if the instruction is not touching any other parts of the data path， do no harm over there。

 don't change the register， don't change the memory， etc。😡，Okay。

 there are actually other jump instructions that I'm not going to cover， jump register。

 jump and link， jump and link register for example， for example。

 we're going to jump register means you take the value in a register and put it into the PC so this multiplex area in front of the program counter it gets is going to become more complicated。

😡，But for the purpose of the simple data path and control logic。

 we're not going to talk about jump register， jump and link and jump and link register。

 but you can look at it in this slide or in your book。😊，Okay。

 so essentially you do everything that I said for every instruction in an ISA to form the data path and。

😡，Essentially， the data path needed to execute all instructions。 Okay。

 we're not done yet with the data path。 We're going to actually do something more complicated。

 which is conditional bench instructions and MIps。😊。

But let's take a break here and we're going to continue with conditional bench instructions。😊，Okay。

 let's be back when the bell rings and I think there will be some students who will make an announcement before that or after that。

So if they're here， they can come。So。ないです。自情发生。Oh， thanks， I'll just。



![](img/69b2ec35480162aae1719352b12f7da7_3.png)

![](img/69b2ec35480162aae1719352b12f7da7_4.png)

![](img/69b2ec35480162aae1719352b12f7da7_5.png)

![](img/69b2ec35480162aae1719352b12f7da7_6.png)

I you need to wear it。I will use it quickly like this。

No it's when okay hi all thank you for your attention we just have a quick question we wanted to ask you if you could fill out our survey we are observing problems that students are handling during their studies and you have the chance to also win two Covo of 10 francs and it would be very helpful so you can just scan it and fill out the questions it will take about five minutes that would be amazing also share the link with your friends and other。

😊，Colleagues。Thank you a lot。Okay。

![](img/69b2ec35480162aae1719352b12f7da7_8.png)

![](img/69b2ec35480162aae1719352b12f7da7_9.png)

知てます。我来我觉得这种。今そ。嗯。对。我去。Everything's good online。Okay， let me go back over here。So呃。Yeah。

 we completed the data path for unconditional jumps and hopefully。

You understand some of the intricacies。 So if you connect the wrong wire to the wrong place。

You may get PC as opposed to PC plus four and you will essentially violate the。Specation of the ISA。

 right， so you need to be very careful when designing micro architectures。😊。

This is not the hardest part， but there's more to do so。Okay。

 there are a bunch of jumps that we're not going to cover， but they complicate the design even more。

For example， some of the jumps jump to， for example， jump and link register。

 this is used for jumping to a procedure call or function call。

You need to supply the address of the function call in the register that you use to change the program calendar2。

 which is a source register， and you also store。The address of the next instruction in a destination register。

Why， because after the procedure all ends？You use an unconditional jump。

 which is essentially jump register。To jump back to the next instruction。

 so you basically have an instruction that jumps to a procedure call saves the address of the next instruction and at the end of the procedure call you jump to that saved address back okay。

So these jumps are necessary for implementing procedure calls or function calls。

 and they need to be implemented appropriately over here。

 but we are not going to consider them in this micro architectureitecture in a real micro architectureiture into consider every instruction that is specified by the ISA and this is a cheat sheet of the ISA。

 we're not even going to do even one10th of the cheat sheet in our design。😡。

So it's not going to be a complicated processor as you can see but this is a nice cheat sheet if you're interested in the MIPS IA okay now let's do a little bit more complicated instructions which are conditional bench instructions i'm going to lead part of the design to yourself your book actually does all of this so in the end you can find out the answers also but I'd like you guys to also think about designing things。

😊，So branch instruction looks like the branch equal' a conditional branch branch if equal essentially if this is the instructionss an I type instruction target is determined to be PC plus4 plus signine extend immediate just like well not just like the jump but very similar to how we actually do base plus offset except we do a PC plus offset so we will need a way to compute this target we don't have it yet。

😊，In our design。 So if we don't have a way of PC plus。Immediate right。

 or piece incremented PCPC plus 4 plus immediate。😡。

Immediate comes from the Sineex X 16 it we have the immediate actually we use it for something else in other i type instructions。

 but now we need to do a PC plus that， so we need to provide something in your book。😡。

Does it through the ALU， which is not a nice way in general， we're going to do it over here。

We're going to add something else， okay。Okay so now you compute the targets。

 then there's more complicated things， meaning there should be some checking that needs to happen over here if the general purpose register one of the general purpose register that you're checking is equal to the other general purpose registers in terms of data values。

 then PC should get the target value that you compute this way okay so there's a lot of computation going on right there's this and then there's this。

😡，Otherwise。PC should get PC+4。That makes sense right there's a conditional branch if the condition doesn't hold you go to the next instruction and there are variations of it。

 branch equal branch not equal branch less than or equal to zero branch greaters than equal to zero。

 all of these are variations of this， some of them don't have two registers。😡，Okay。Okay。

 so let's take a look at what we're going to do。😊，This is again， this is not complete。

 but this is PC plus 4 from instruction Data path， you get it actually from here。😊。

But you need to watch out just like earlier， if you get PC， you'll get the wrong thing。

 but PC plus four， we're going to add another adder。😡。

Which basically will take the cineex and immediate from the instruction。

And extend it and shift it left by two as specified by the instruction。

 add to PC plus4 from the data path， and that's our target address。

And that will increase the size of this multipleer over here。

 this multiplexer becomes more and more complex with different ways of computing the address for a jump instruction。

 but this is going to be one of the inputs to the multipleer。😡，And we're going to control it。

And control will become more complicated because this control is not only dependent on the instruction you're execute。

😡，It's also dependent on the result that we're going to get from the ALU meaning okay we're going to do no harm。

 meaning we're not going to write to register because branch instruction is not specified to write to register we're not going to read from memory it's not shown over here for good reason branch instruction doesn't read memory branch instruction doesn't write memory so do no harm in all of the other parts let's take a look at where we will do something so branch instruction needs to read two registers compare them so if your ALU operation needs to set to comparison or subtraction。

😡，toptraction is actually comparing them if they're equal you need to have an equality checker et cetera。

 so there needs to be some more logic to execute this branch and in the end。

 if the branch condition holds meaning branch should be taken that should be supplied。😊。

To this multiplexer that will select if the branch is taken， this input should be selected。

 meaning this this is the way we compute the branch target at is for this conditional branch and that input should be selected if the branch condition doesn't hold which was computed over here。

 meaning branch is not taken， then the PC plus4 input should be selected， which is this input。

And clearly， you're not going to select anything other than these two inputs if you're executing the conditional branch because those inputs are there because of other instructions like this concatenation was because of the jump。

 right？😡，Okay。就。Things get complicated， as you can see。😡，Things are actually even more complicated。😊。

There's something called a delayed branch， which is also a bad idea。

 meaning we'll discuss that when we talk about branch prediction， et cetera。

 but it turns out in the MIPS Ia。😊，Branches are not just branches。

WhenWhen you do a conditional bench。The next instruction。

That comes is always assumed to be executed and we'll see why later on。

So even if you are supposed to jump to the target。😡，Somewhere else。

 the next instruction is always executed after the bench this may sound mysterious but there's a reason why people added it it's a very bad idea again that's why we're not going to talk about it right now okay。

😡，Okay， but it's good to know about the bad ideas also， especially when we get to it。 So in the end。

 if you actually。😊，Introduce all of the instructions that I've discussed in a proper way。😡。

This is what you would get。Actually， we can use look at the conditional branch soon about that。

 but I'm omitting the three complicated jumps。😊，But let's take a look at the conditional branch over here。

Well as you can see this is not that complicated but it includes everything in a nice way this is a clean picture that you have you have the multiplexer that selects between the result of the memory or output of the memory and the ALU result and that is controlled by something called me to reg whether you actually whether if it's a load then you actually enabled this me to re to be one otherwise this is zero right and we're going to set the control signal so these are all the control signals that you need with this data path design and all the data path elements that we have added with the data path design let's take a very quick look at conditional branch over here because I didn't complete it over here saying that you should complete it but just to give you a hint there's no magic over here if you have a conditional branch let me see this is the PC plus4 input over here。

😊，You basically take the Sex and immediate shifted left by two， add to it。

 this is the target address。Now you need to， if the branch is taken。

 you should select this target here and here。😡，Let's take a look at whether it's selected。

 so if it's a branch conditional branch。😊，This end gate is eval to one and there is some computation logic that needs to be added to the ALU to check whether the branch should be taken or not if this is taken this should be also one if this is one and this is one。

This becomes one， so you select the target address。

And let's take a look at this multiplexer over here， so a PC source one is jump， this is not a jump。

 it's a conditional bench so this should be zero， this control signal should be set to zero when we're executing conditional bench so this data should flow through this marks。

😊，And hopefully get to program counter。And it does， that's good。

 so the multipleer that I showed earlier in front of the program counter is actually distributed over here。

😊，So this is the multiplexer that you have， it's two input multiplexer， which is same as one。

4 input multiplexer， right。😊，Okay， so we could actually have fun with this data path design。

 this is actually the entire data path design with all of the instructions that I intended to add earlier。

😊，Makes us。Okay， so I would suggest you go through this because this is very good for understanding。

😊，And you can see that there is an ALU control over here also。

 so if you we didn't really fully form that， but there needs to be some logic that decides what the ALU operation should be and that is dependent on the bottom six bits。

In the instruction， remember that functionc， if the app code is zero， meaning if your R type。

 this functionc determines your ALU operation， so that's part of your AL operation over here。😡，Okay。

Now let's design the control logic， so that was our data path。

 clearly we added control signals to control the data path， but how do we set the control signals？😡。

YouAgain， we kind of did this actually， but let's do it in a more methodical way。😡，Essentially。

 the methodical way， one methodical way is to design the single cycle hardwired control as a combinational function of the instruction bits。

 you look at all the instruction bits， you look at the parts that matter and you design some combinational logic。

😊，To decide which control signals should take which values Okay， you can think of as a truth table。

 right， The input is the instruction bits。 The outputs are every single control signal that we have over here。

 You can count all of them。And then。You basically do what we have seen in earlier lectures。

 you minimize that logic， and that's your hardware hardwarewired control logic。😡。

So we're going to do it not exactly that way， but you can imagine doing that that way。

 I'm going to show it to because if you do it that way。

 your truth table is huge right your truth table basically consists of these are instruction bits。

 2 to 32 bits。😡，Well， you can eliminate some things。 you can say okay。

 two of the six bits over here upcode， but I still need the function。

 maybe okay so let's we're going to do it in a different way。

 So there's a different way of designing， but this is also it something that you need to design and we're going to design the control logic for all of these instructions our type I type loadword toward word and branch of different forms and only jump We're omitting the harder jumps。

 let's say。😊，Okay， so essentially we're going to generate these orange colored control signals。😡。

And this is how we generate that， so for example， a rec desk signal。😊。

R de signal is what it basically selects whether destination Reg ID is 15 to 11 or 20 to 16。

 This is clearly determined by what your op code is if your up code is zero meaning your art type your destination register comes from 20 through 16 bits of the instruction otherwise it comes from 15 to 11。

😊，Well， actually the other way around sorry if your up is zeror type。

 this is your destination register otherwise this is your destination register and that's why we had that max to begin with okay so you can do this similarly for every other control signal let's do the map to egg because we discuss that multiple times so map to egg is this multiplexor over here whether the data input of the register file comes from the output of the memory or output of the ALU result and clearly when we design the data path we said that when we added the load we added this max if the load is executing then this multiplexer should select the data coming out of memory。

😡，Otherwise， it should select。What's coming out of the ALU results so you basically check whether the up code is the same as the upcode of load word which has an encoding and if that is true the multiplexer is steers the memory output to the general purpose register is right port register files right port otherwise you steer the ALU result which means this is one and this is zero and essentially this is one and this is zero as you can see okay。

😊，Okay， so you could do this for everything， let's pick one more。

 let's say Regrightite Rerightite determines let's look at the signal that we designed earlier。

 Regrightite Regwright says whether the register file register file should be written into to write an enable signal for the destination register essentially。

😡，Now you need to decide when this is set to one and when this is set to zero。

 clearly it should be set to one for instructions that right to a destination register。😡，Essentially。

 for all instructions other than storeward， branch， jump。😡，And jump register。

 I guess jump register is all included here， unfortunately。

 but that's how it is so basically for all instructions that are and。😊。

Not writing to the register file writing to the register file you set this bit to one otherwise you set this bit to zero okay so you do this for every signal I it becomes a bit boring to go through every signal but ALU source clearly is another one and then again this is dependent on whether you're executing whether you're operating on an immediate value or register value again you need to be a bit careful over here because branches also operate on immediate values。

😡，And then whether you're writing to memory， reading from Me。

 clearly you set the memory read signal if the up code is load， you set the memory right signal。

 only if the op is stored， these are easier ones。😊，And then there's the PC source registers。

 which are the maxes over here， multipleers， these two maxes over here。😊，呃。是。

So the actual PC source2 is this one over here， so you can see that if the up code is branch and the branch is taken。

 then next PC is based on the 16 bit immediate branch target。

 PC plus 4 plus immediate branch target shifted by two。Okay。

 you can see that this control signal is not only dependent on。😡，The upco。

It's dependent on the up code and also what's happening in the data path right so not all control signals are just dependent on the up code。

😡，Some control signals require input from the data path and clearly that multiplexer requires that input because it's executing a branch。

 the destination meaning the PC should be increment accordingly whether the branch is taken or not taken。

😊，Okay。Okay， so this is your table for control signals， it sounds like fun。

 you could construct in a different way also， but this is how it is。😊。

Let's take it now let's play the game of setting the control signals。😡。

So let's execute an R type AL instruction basically assume that you designed the data path。

 you' were given a data path， how do you set the control signals because we have designed the data path we know exactly how to do it so I'll go through this relatively quickly。

 so if you're executing an R type AL instruction。😡。

Control signals are set such that data flows accordingly。 For example。

 the destination register should come from these bits of the instruction 15 through 11。

 because those are the destination register bits。We write to the register file because it's is an our type AL instruction that modifies the destination。

The second input of the ALU should come from a register because it's an archived instruction with two register inputs。

Funnct bits from the up code determine what is the ALU function， we do no harm to memory。

 neither enable nor disable it。😊，And we ensure that the memory output doesn't get written to the register file。

 actually， the ALU result gets written to the register file， we increment the PC by4。

 we select the signals from these maxes， we set the select signals such that PC plus4 nicely flows through those maxes into the program counter makes sense。

😊，Okay， that was our type A。By type AL， the only difference looks like this。Does it look like fun？

And this is based on what we've designed。 Basically， you still write to the register file。

 but the destination register is different。 The immediate is different and the function is different。

 Okay， Lord word。Is actually similar to i type because load is an eye type instruction。

 You can see that we do exactly the same things except we do an addition in the ALU so that we can actually。

😊，Do base plus offset addressing？And oh sorry this is Lord word we enable the memory to read and we set this control signal so that we get the memory outputs into the destination register Clearly we're not changing anything over here because we're not these are not jump control flow instructions PC plus four should be always flowing so we're here in all of these instructions St word is very similar to the road word in the addressers generation except control signals change a lot if you think about it。

😊，So you should be we're not reading from memory address calculations is the same。

 we're not reading from memory， we're not we're writing to memory， we don't care what this maxes。

 so now don't care remember that don't care as we had in combination logic some multiplexer values we don't care in this case we're not writing to the register file this is set to zero so I don't care what the destination register ID is right because I'm not going to write it anyway I don't care what the value this multiplexer takes as a select input because I'm not going to get the data and write into the register file right so don't care is are useful for minimizing the logic as we have discussed in logic design part。

😊，So that was forward now let's talk about branches， let's talk about branches not taken。😡。

So a branch not taken is very similar to everything else so if you look at Stward branch not taken is very similar except branch could be taken also so we need to calculate we need to calculate the branch condition right so there should be a calculation of the branch condition so do no harm we don't write to the register file we don't read from memory we don't write to memory we calculate the branch condition over here and it turns out to be not taken then PC plus4 flows so this is a case where the data that you operate on determines the control signal of these maxes as we have seen earlier so essentially I said this earlier some control signals are dependent on the processing of the data and the data path。

😊，Branch taken differs very little。Everything that you do to execute the branch you still do except this signal branch condition taken makes ensures that this output this input of the multiplexer selected meaning you calculate the target address the way branch target address should be calculated so these are all clear hopefully and this is also end on the data jump we've already seen this also jump is actually do no harm over here。

 you only care about this multiplexer actually which is taking the jump address and placing it into the program counter。

😊，O。So I've covered almost all of the instructions now。

 but you need to do this for every instructions， so imagine you have thousands of instructions。😡。

So you have something to deal with。Okay， so a combination， so a control box。

 so we have this control box that we didn't form， but have we kind of formed actually。

 I've given you all the equations needed for this。😡，But there are different ways of designing it。

 so you can have hardwi control like I designed earlier。

 control signals are generated combinationally based on bits in the instruction and quoting。

 or you can have a memory structure that stores these bits you basically have a memory structure based on the up code。

 you index memory， and that memory or called control store gives you all the control bits。😡。

So I could do it combinationally or essentially using a memory structure。

And both types of control structures can be used in single cycle processors and actually existing processors use both types of control structures。

 which we may talk about in the end choice depends on the latency of the structure and how much the critical path。

 how much of the critical path control single generation is this could become big right if you think about it if you have thousands of instructions。

This could actually become pretty big。Okay。So this is our complete single cycle processor we've designed and went over。

 we're going to analyze it soon。😊，There' is another single cycle processor that your books developed。

 it's going to be very， very similar to what I have developed。I will not go through this。

 I'll just go through one instruction that your book develops， but if you're。

In in reinforcing what we have done， you can actually read the book and this is the processor it's slightly different。

 but it essentially has very similar signals as you can see over here。😊。

And maybe some of the multipleplxs are placed in different ways， et cetera。

So this is how your book does it， essentially it does what we did， so this is load word。

 you need to input to fetch the instruction PCs input to the address and you get the instruction。

 some bits give you the one of the registers and that' the base register over here and then some bits in the instruction give you the immediate you sign extended and then you put them into the AL set the ALU control to some values such that you can do add ALU results gets connected to the data memories address input and then redda gets connected to the destination or write input of the right data input of the register file and then you use some bits in the instructions to determine the destination register。

 so it's essentially what we did。😊，Except your book does it slightly differently for some instructions for load。

 actually， it's exactly the same and you do a PC plus4。😊。

And your book also discusses some of the control signals that I'm not going to discuss。

 but it's going to be very similar to what we have discussed。Okay。

 and this is a complete single cycle proor that your bouque。Okay， so basically。

 if you have questions over here， go through the lecture slides and the backup slides and do the readings。

😊，Hopefully you will be able to design datapath and processor and control logic easily。Okay。

Now let's evaluate the single cycle micro architecture， any questions？Okay， let's evaluate。

 let's see if it makes sense。 I already given you that it doesn't make sense， but。

Let's pretend it may make sense under some conditions because any idea may make sense under some conditions。

 but those conditions may not be satisfied very frequently。Okay， so essentially is this a good idea。

 when is this a good idea， when is this a bad idea。

 how can we design a better micro architectureitect？😊，So remember the performance analysis， right？😊。

I will go through the Torontoquiive because I actually discussed everything。

 but this is actually for your benefit in the end we're going to optimize for performance each instruction needs to be executed。

😊，And each instruction takes one or more clock cycles to complete right how long is one clock cycle that is determined by the critical path。

 so you have clock period that's the critical path that determines how much time one cycle requires clearly the clock frequency is one over the clock period。

😊，And this is the equation that I showed you earlier right you have any instructions that are executing on average each instruction takes some cycles per instruction。

 average CP and clock cycle is some T seconds right you could express it as one over frequency also right？

😊，Okay， let's let's look at our design， so in this design CPI is set to one as we said before。

 you have no freedom to optimize it because that's the definition of the architecture and I'm going to we design this architecture such that every instruction takes one clock cycle。

😡，Okay， now how long does each instruction take？😡，呃。Essentially。

 how long each instruction takes is determined by how long the slowest instruction takes to execute。

 even though there may be some instruction that don't need that long to execute。

 youre determined the clock cycle is determined by the longest taking instruction and we're going to analyze that。

😡，Okay， essentially， clock cycle time of themic qua architecture is determined by how long it takes to complete the slowest instruction。

😡，Which is the critical path of the design is determined by the processinging time of the slowest instruction。

Then the question becomes， of course， what is this slowest instruction let's take a look at it with our design with our assumptions。

 our assumptions can be actually very optimistic， so we're going to look at all of these instructions that we designed。

😡，Does every instruction take the same time latency to complete if every instruction takes same time or latency to complete。

 this may not be a terrible design。😡，Still multicycle would probably provide you benefits。

 but this may not be a terrible design as long as the latency is short。

 but there will be some instructions that take a very long time。

 Okay so let's find the critical path on this design that we lot It's another game we're going to play right now。

Before we play the game we're going to make some assumptions for this design in the previous slide。

 which is this design that we have developed， we're going to assume memory units take 200 picoconds。

 AL and adders take 100 piconds register file takes 50 picoconds either read or write and another logic magically takes0 or picoconds。

😡，Okay， we're very optimistic as you can see， memory never takes 200 piconds。😊。

It takes hundreds of nanoiseseconds if it's big memory。

 but we assume that this is very fast memory right I'm not going to violate the assumption even with these assumptions。

 these are the latencies that you expect the instructions to take。😊，So for example。

 a jump instruction， it only fetches the instruction。

 it goes through some Max to update the program counter。

 we've already assumed the delay of the maxes and the wire is zero。😡。

So it should take only the memory access optimistically， 200。😡，That's the fastest instruction。

 actually。The slowest one。Fetches the instruction， accesses the register file。

 executes in the ALU to compute the address in the memory， Accesses Memy data memory。

 and then writes into the register file。 It turns out to be load word 600 piseconds。 That's 3 x。

The latency of jump。So now every jump needs to execute， take at least 600 piconds as you can see。

 right， even with our optimistic assumptions。Okay。So this is one of the reasons why this is a bad design so if you actually want to really do the critical path analysis you need to do it again based on each instruction so our type and I type ALU there are two paths one is updating the program counter which is 100 piseconds through this adder and then zero through all of these mugs etc because of our idealistic assumptions and then to actually do the computation you need 400 piseconds because you need to fetch the instruction access the register file do the addition and then go through this mugs which is zero again but yeah right to the register file that's where the latency comes from so that's 400 piseconds the word as I said accesses memory twice as you can see that's why it takes 600 piseconds。

😊，Every instruction a is me to fetch the instruction store word is 550 percon。😊。

Because it's really not。Yeah anyway yeah Stward if you go back over here Stboard is missing writing to the register file50 right as a result it's 550 so load is actually so this is very realistic loads actually take the longest and real processors also in general we're going to get back to that later branch taken is actually not that bad so a branch taken actually has two potential critical path one is the take not taken and the other is a taken path if the branch is taken you actually need to go through the branch condition computation through the ALU that is actually 350 peoseconds over here。

😊，And Ju is the fastest as we have discussed， but there are still two potential critical paths over here through the sms。

😊，The reason is one of the passes determined by the branch condition taken conditioner。

 right this multiplexer。 Okay， okay， so that was our analysis。 And hopefully with this analysis。

 you see that some instructions。Can be very fast， but they're becoming slower because every instruction is determined。

 the clock cycle is determined by the slowest instruction to execute in this particular case with these particular assumptions the load。

Okay， what about control logic， we kind of ignore the control logic here。😡。

Those all of this ignores the control logic for a good reason you can optimize the control logic so that it doesn't affect the critical path。

 but this is a food forough for you can control logic be on the critical path absolutely yes。😊。

Usually not if you design a processor very carefully， usually not。

 but if you have a lot of things to control， if you have so many instructions this may become part of the critical path but not in this design hopefully okay so that was our toy example now let's talk about the real world。

😊，Me we assume this magic， right， We assume 200 piconds， but that's not the case。

 if you design a two to the 32。Entry， memory。That's not going to take 200 piconds to access in any technology of today。

And sometimes it actually takes 150 nanoseconds to access。Now clear。

 this is orders of magnitude slower than the fastest instruction， which is the jump。

 it doesn't need to well it needs to access memory once， but if you need to access memory twice。

 then you have orders of magnitude difference。😡，So does it make sense to have a simple register to register add or jump take all of the length of the memory access because some instructor needs a memory access。

 rate？And in some instructions， you need to access memory more than once。

 and every instruction requires accessing memory once actually。😡，So basically。

 your clock cycle becomes too long if you assume a realistic memory， which we didn't assume。😡。

So that's one of the reasons why single cycle mytics are good for forming the data path。

 control signals， you don't need to think about multiple clock cycles， et ceter。

 but these are not real。😡，Nobody in their right mind would design architecture like micro architectureit like this because it makes no sense for the reasons over here。

 I'll go through it relatively quickly。😡，Yeah， it's contrived。

 it's inefficient all instructions run as slow as the slowest instruction， also as we will see。

 you must provide the worst case combination of resources in parallel as required by any instruction。

😊，Meaning because you're doing everything in a single cycle。

 if an instruction needs two memory accesses， you need two memories or multiple multipleported memories。

 you cannot reuse the same ALU to do multiple things because you're doing everything in a single clock cycle you cannot basically change what's happening right so it's actually not good for hardware resources also。

😡，So you need to replicate a resource if it's needed more than once by any instruction during different parts of the instruction processing cycle。

 this will become more clear when we actually see multicycle microacts。

 which are going to be much more hardware efficient。😡，So this is not only slow。

 but it's also hardware inefficient。Which is really what you really don't want， right。

 you don't want your this is extra costly plus extra slow。😡。

And also it's very tough for complicated instructions。

 we didn't even look at any complicated instruction。

 what if you have a complicated instruction like a string copy。

 matrix multiply indexing into a multidimensionalal array。😡，It becomes essentially unreasonable。

 easily。😡，And also， as we said， optimizing the common case， frequent instructions don't work。

 meaning。😡，If you want to basically optimize performance here。

 you cannot change the cycle per instruction because by definition。

 you can change the clock cycle time， but now you need to optimize。😡。

The clock cycle time for the worst case and reducing that worst case is much harder than optimizing for the average case。

 And this will become more clear again。So I basically need to optimize the worst case all the time as opposed to saying this is my clock cycle time。

 I'm going to try to achieve it as much as possible， right？😡，Okay。

 so this brings me to micro design principles， so there are three major design principles if you want to optimize for performance。

😡，And these are listed over here critical path design。

 bread and butter or common case design and balance design。

 let's take a look at each of these I'm going to define them and i'm going to show you how single cycle architectures violate all of them。

😊，Essentially to have a critical path design， ideally you would like to have a high frequency。

 find and decrease the maximum combination of logic delay。

 break your path into multiple cycles if it takes too long by definition of single cycle micro architecture doesn't do that right clearly it says single cycle。

😊，It's not even there multie can still reduce the critical path， but you don't have a lot of freedom。

Common case design says spend time and resources on where it matters the most。

Improve what the machine is really designed to do。😡，Common case were Suncom case， for example。

 if your machine is executing a lot of ads。😡，Optimize for ads。😡。

You cannot do that easily in a single cycle machine， right。

 because your cycle time is determined by the worst chase instruction that you have to execute。

 even if most of the time that instruction doesn't appear。

 even if that instruction appears once in a blue mood。😡。

Meaning that instruction gets executed every 30 days by someone。

Still you need to support it this part of the ISA。You cannot say people are executing matrix multiplies I opties only for those right okay so basically you break that principle also B design says essentially you balance the instruction and data flow through hardware components。

 essentially designed to eliminate bottlenecks， balance the hardware for the work and this is also violated in the sense that you actually need a lot of hardware resources to execute instruction you need to replicate a lot of resources。

😡，Okay， so let's take a look at these principles， I think I've already covered this actually。

 you can do it on your own， we're going to look at it for multie micros as well later。😊。

Does this make sense？Okay。How much time do we have are we still？

Okay we have I'll finish the system design principle I'll give you the basic idea of multicycle but we're not going to cover the multicycle design next week we're going to start covering the multie design so let's in aside as I said in the first lecture it's good have principles when you're designing things so I've given you some other principles。

😊，This is true for any other system design， actually， real architectures， buildings， bridges。

 anything。And we need to add more principles today actually， I think one of the issues， for example。

 with machine learning driving our systems is some of the designs are not very principled。😊。

We get some results。 We don't even know how to trust them， right， So think about that。

So we discussed principle design， but theres a very famous architect who said architecture should be based upon principle。

 not upon precedent。😊，And this is maybe precedent based design。

And this is the architecture he designed， which's a more principle design。

 and I'm not going to talk about this， but this in an organic architecture and contrast these。😊，Okay。

 I'm going to skip this because I'm going to talk about the system design principles if you're interested in system design。

 not computer system design principles， there are a bunch of works that discuss this。

I've introduced this paper very briefly， if you're interested， take a look at it。

 I will mention a key system design principle。😊，Which actually the single cycle architecture violates。

 keep it simple。Single cycle is not simple。If you don't do anything else， follow this principle。😡。

And this is actually not just me， somebody said this， Does anybody know who said this。

 Everything should be made as simple as possible， but no simpler。Yes， you have。Older。Yes。Yes。

 exactly paraphrasse， as you can see something similar is right？😊。

And keep it low cost that's also important and actually somebody said this I don't know who said it。

 but an engineer or a designer is a person who can do for a dime what any fool can do for a dollar。

 let's say 10 cents versus a dollar for more design principles I'd recommend butler Lamson's hints for computer system design which he updated after 40 years or so so if you're interested you can take a look at that paper that talks about things including keep it simple。

😊，So in the remaining time I'll introduce the core idea of multicycle， which you've already seen。

 but basically can we do better， we violated a lot of principles with single cycle。

 but that was good for instruction， education， let's say。😡。

Now let's design some more real machines and these are actually real machines people have designed these machines。

 they are very elegant machines， there are multiple ways of designing multie micro architectureectures as well the idea is very simple or gold let each instruction take close to only as much time as it really needs。

😊，Don't have the worst case instructions dictating in the clock cycle essentially。😡。

You determine the clock cycle time independently of instruction processing time。

Each instruction takes as many clock cycles as it needs to take。

And you have multiple state transitions per instruction。

 The state followed by each instruction is different。 That's why I' will get a finite state machine。

That is larger。Okay， so this is actually what you have seen right we remember that my architecture。

 we had two choices， we covered one choice。😡，You go from architectural state to architectural state prime in a single clock cycle。

 and now we're going to take multiple clock cycles to do that。

Essentially this process part of the instruction one clock cycle and then process the next part and another clock cycle。

 process the next part another clock cycle， et ce， eventually you produce the architectural state pride。

😊，And this is what we kind of implicitly did， we're going to form a processor that does it from scratch soon。

 we're going to do it relatively quickly， but I don't think we have time today to do it。😊。

But this is actually what we're going to something like this is what we're going to build up。😊。

And this makes a lot of sense， as you can see， this is the full finite state machine controller a multicycle LC 3B microctic this way each state takes a single clock cycle。

😊，And you say my clock cycle will be one， nanosecond， let's say。

 and you basically break down an instruction to as many states as needs to finish the instruction。

 it could take 1000 states， 1000 clock cycles。Some instructions will take Mon clock cycle。

And if there's an instruction that really matters that everybody' is executing。

 you optimize the state machine such that that takes as fast as possible right now you have degree of freedom。

 degree of freedom one clock cycle， you determine it independently of anything else you can say okay。

 you can imagine and say I'm going try to achieve 50 gigHtz and then based on that what are people executing what do I want this machine to execute 10 years down the road。

 I optimize for that So you optimize the state machine for that and not the instruction that appears once in a blue move。

😡，And this was what we have seen actually earlier， so let's talk about the benefits you can keep reducing the critical path independently on the worst case processinging time of any instruction that's good now we can do critical path design。

😊，Whereas previously with single cycle we couldn't do any of that。

 you can optimize the number of states it takes to execute important instructions that make up much of the execution time。

 assuming you know that remember we cannot predict the future completely and you don't need to provide more capability or resources than really need it you can have a very frugal design very few resources and you can reuse those resources across different states in different clock cycles you can reuse the same resources。

Meaning an instruction that needs a resource X multiple times does not require multiple X's to be implemented。

😡，You require all multiple exit to be implemented only if you're doing everything in a single clock cycle。

 right？😡，So this leads to more efficient hardware。😡，Of course。

 with every idea there are downsides also。So before essentially。

 we will need to store intermediate results， this was not an issue earlier， right？😊，Remember。

 we do something in a clock cycle， we generate some intermediate results。

 we need to store them somewhere， those need to be stored in their register called micro architectural registers。

😡，This is not good for costs， so there will be additional costs。

 even though we will save some cost based on the upsides earlier。

 but now this is also going to be not good for latency also。😡。

So there will be a register setup and hold overhead or sequencing overhead that's paid multiple times for an instruction because at the end of every clock cycle。

 we're going to store some results into these micro architectural registers so part of the clock cycle will be wasted as we have seen in timing and verification right that waste is minimized if you have only a single clock cycle takes execute an instruction。

😡，We will also see that this will have limited concurrency and this is going to be the reason why we're going to be built pipeline machines later on we're going to use only a small part of the machine at any point in time because we're going to break the instruction execution such that only a small piece of the instructions executed at a given time which means that not all of the hardware resources that we're going to provide will be used at any given time now that's not necessarily bad。

😡，But you're not using the machine completely， meaning not you're limiting the concurrency。

 you're limiting the performance potential of the machine。😡。

So let's quickly take a look at the earlier design that we had。

 so some of these are extra registers that are not needed in a single cycle design。

 so in a single cycle design you don't need to store the instruction bits right？😊。

You basically take them out of the memory and those flow through the pipeline here。

 because we need to fetch the instruction and we need to break the instruction processing into multiple clock cycles。

 we store the instruction bits in an instruction registergitry。😡。

In a single cycle design you don't really need a ME address register and memory data register which we had introduced part of the Wal Neman model。

 one Neman was smart， you didn't think about single cycle designs。

 but essentially you do need them if you actually if you actually want to break the instruction execution such that MM access starts at the beginning of a clock cycle and end at the end of a clock cycle and you don't want to do anything else in that clock cycle right so you need to introduce additional registers to store intermediate results there's more that is not depicted in this picture。

😊，So basically， the upside will be we will have freedom to optimize both CPI and clock cycle time。

 and we're going to do that。😡，This is where I'm going to stop because we don't have time to go into this closer look in the next lecture we're going to develop this multicyclemic architecture and probably not only that we're going to see the downside time we're going to do all pipeline processors as well。

😊，So have a good weekend， I'll see you next week。

![](img/69b2ec35480162aae1719352b12f7da7_11.png)

。对。