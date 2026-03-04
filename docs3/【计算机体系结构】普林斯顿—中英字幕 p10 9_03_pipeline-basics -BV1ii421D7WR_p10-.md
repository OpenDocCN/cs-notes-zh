# 【计算机体系结构】普林斯顿—中英字幕 p10 9_03_pipeline-basics -BV1ii421D7WR_p10-

![](img/d84a78d88e72b607d83dc8abc401b5df_0.png)

And now we're going to move on to talking about。Basic pipelines。

 And we'll start off by just talking about how to build a pipeline and how to name things in a pipeline and how instructions flow down a pipeline and why you want to build a pipeline。

 And we'll start off with a very gentle introduction to this。

 And start off by talking about a idealized pipeline， not necessarily in a processor。

Pipelines show up many places in the world。 They show up in car factories， toy factories。

 I know Some people say， you know， when you go use the washing machine in a laundromat。

 you're pipelineing because you first put your laundry in the washing machine and then take it out。

 and then you can put in the dryer。 We can put more work in the or more laundry in the first washing machine。

 So we can， we see pipelines in lots of different places in the world。

 But we also see it in this class， we're gonna care about using pipelines in microprocessors。

So let's think about an idealized pipeline。So I have a picture here of an idealized pipeline。

What are some of the good or what are some of the requisite。Conditions for an idealized pipeline。

 Well， first of all， all work or all objects should go through all the stages。

 So here we have four stages in this pipeline。 and there's no sort of squiggly lines where things sort of come out of the pipeline or go around the pipeline or。

Exit early， that doesn't happen in this diagram。So in idealized pipeline。

 you want all of the objects to go through all the stages。

You don't want any resources shared between different stages， so。You don't want some resource here。

 which is shared between stage 2 and stage3。 So an example of this in a car assembly pipeline or assembly line would be one tool which two different stages in the pipeline have to use or two different assembly stages have to use that would cause what is known as a structural hazard in processor design。

The propagation delay between all different of all the different stages should be the same。

 So the time taken for stage 1 should be the same as2， stage 2， the same as stage 3。

 which is the same as stage 4 an idealized pipeline。And then， finally。

The scheduling of an operation or a transaction or an object going down the pipeline should not be affected by what's currently in the pipeline。

And。These conditions actually hold true for most assembly lines in plants where people go and build cars or something like that。

There's no dependence between the different parts。 A car comes into it。

 All cars are sort of separate from each other。 It's not， not really a problem， unfortunately。

If you go and look at something like a microprocessor executing instructions。

Instructions actually depend on earlier instructions。And they depend on in multiple different ways。

 They can either depend on the data values or they can depend on the fact that you took a branch or a control flow instruction。

So we have to look at these different hazards。 and we have to think about how to either solve them or deal with them and how we we have to think about how to deal with non ideal pipelines。

So， let's。Go one step beyond our micro coded processor design and look at a unpilined。

Data path for the MIPS instruction set。So this is going to be similar。

 Or if you've already taken a computer organization class。

 you've probably seen similar sorts of unppelined data paths。So in our unpline data path。

 we start with the program counter here， we have some instruction memory where we go fetch our instruction out。

 and this flows through， we fetch our registers from our register file， we flow through。

 we do the actual computation， we might have to go access data from data memory if we do a load or restore。

 and then finally comes back around， we write the result here。

 and we increment or change the program counter。And this is all done。In one cycle。

 And it's a very long cycle because you want shear。You go through all this work。

 you do all these things。He data he gets put back here。And have to has to happen because we're un。

 We have an un pipeline processor here。 It has to happen in one cycle。 So this is kind of。

Not great from a cycle time perspective。 It is good from a perspective of the number of cycles per instruction。

 It's always one。Because you launch an instruction and you wait till it's done。

Then you launch the next instruction。 you launch the next instruction， and。

Each instruction that launches is one cycle。So let's。

 let's simplify this design a little bit so we can talk about what's going on here in a little bit more depth。

 So we're gonna simplify our unpipelined processor design and just take out some of the。

 the extra stuff here and focus on you launch from the program counter。

It accesses the instruction memory all combinationally。

 You go through the register file combinational logic。

 You go through the data memory and you come back around。

 So that would be something like a worst case load instruction。

And the value gets written back here into the general purpose Reg file。

So let's now move on to thinking about how do we build。The same data path。

 But we try to want to pipeline it now。Well， the first thing we want to do is we want to cut the pipeline up or cut our design up。

 and we're going to put in registers。And it's just。

So happens that this is a convenient place to put registers for something like a MIps data path。

And some important things that you might recall from your digital logic design course is that when you go to pipeline a circuit。

You need to make sure that you cut all lines which are going in this direction across the registers。

 So if we were to cut here， we need to put a register here。

 here and here because there's three sets of wires running from left to right。

This feedback path here doesn't need a pipeline register because it' it's flowing back and it's effectively running back into the register file here。

 combinationally。嗯。And， you know， the， the register file can either be clocked or unclocked。

 depending on how you actually do this design。So we've pipelined our data path now。

And let's put some names on these things that we're gonna be reusing throughout the class。

 So we're gonna call this the， the fetch phase or the， the instruction fetch time。

 Sometimes in this class， we'll either denote this with a uppercase F or we'll denote this with I F for instruction fetch。

🤧嗯。The next thing we're gonna do is we're going to decode the instruction。

 and we're also going to fetch the registers out of the register file。 So the decoded instruction。

 This is how we take the tightly packed bits in the instruction。

 and we blow it up into control wires。And the register fetch phase。

 we're actually going to fetch from the register file。

 And this is sometimes we'll denote with uppercase D。

 or sometimes we'll denote it with RFF or register fetch。This is the execute phase。

 We're actually doing real work here。 We're taking the A U。 We're doing some ad。

 We're doing some multiply， something like that。 maybe subtract or a shift operation。

 And we'll denote this with the uppercase X or。😊，The letters is EX for execution。The memory phase。

 we're accessing the memory here， the data memory。 And then finally， the write back phase。

 and we'll deote this with M。 And then finally or M M。 And then finally。

 the right back stage here willll typically denote with WB or W to denote when we actually go to write the data into the register file。

 We have a whole pipeline stage dedicate that。😊，So one of the， the important things now。

 I just picked five different places here to pipeline this， this design。 but this is not accidental。

What we're trying to do is we're trying to divide what was a long。

long time period and cut it up into smaller chunks here。 So we're trying to reduce our clock period。

And we can do this by dividing the execution up into multiple cycles。 And if we look at the time。

 the cycle time is greater than the maximum or greater than or equal to the maximum of the time to access the instruction memory。

 the time to access the register file， the time to access the A LU。

 the time to access the data memory。And the time to write back。

 And those are the different things in the five stages here。 So we're trying to。

we're're not trying to do anything here， but the， the time taken is greater than or equal to the maximum of the rest of these times。

And it's probably in most pipelines， equal to the time it takes to access the data memory。The。

 the time back of the data memory in most MIPS processors is， is probably your。Going to be your。

Limiting factor。 But people will try to pipe on this。

 And we'll talk about how to pipe that even more。 So try to cut the memory unit in half。Okay。

 so that's the easy part。 We pipeline the data。 So let's now move on to a little bit more challenging question here of how to pipeline the control。

So， we're going to。Sor of look at our control unit and we're going to put down our hardwi control here so the hardwarewi control is going to take the instruction register and decode the instruction that comes in。

H。Well。That's okay。嗯。One are the problems here？When you start to look at this is， well。Well。

 actually， before we do that， let's， let's first look at。How to use this processor in a multi cycle。

 yet pipeline fashion。So what do I mean by that？Let's say we're going to use the same data path。

And use the exact same control unit we had in the unpipelined MIps processor。And in this design。

The cycle time is now， let's say。Close to one fifth of the cycle time we had before。

 because we had five pipeline stages。 So our processor executes faster。But。

We're not going to pipeline our control unit。So what this means is we're going to fetch the first instruction。

And we' going to have to wait。For the instruction to go all the way to the end。

Write the register file and be done。 So what we just did here is we built a multicycle。

 yet pipeline processor。 And this multicycle， yet pipeline processor has the clock period。

 which is say， which is roughly one fifth of the time。Of the unpipelined one。

 But it now takes five cycles。So it's a wash。 It might be it's probably a little bit worse because there's some overhead。

From the instruction or overhead from the registers that you need to insert。 But it's gonna roughly。

 roughly be， be a wash so。Let's say we want to start building a pipeline processor that can actually execute multiple instructions。

At the same time， in different locations in the pipeline。In order to do this。We need to。

Go about adding。Pyline registers to our control。And by adding pipeline registers to our control wires。

 we can have multiple instructions flowing down the pipeline and where these multiple instructions are in different stages in the pipe。

 So we can have one instruction here and a different instruction here。

 and they have different control wires being asserted on them because we've pipelined the control wires。

So now we're going to start talking about how do we go about？

Analyzing the performance of microprocessors。And。All performance basically boils down。

 this is just for performance。 There's similar sorts of things for power and area and other metrics you might want to care about when optimizing a processor。

 But in today's lecture， we're gonna to focus on optimizing for performance。

It comes with this idea called the iron law of processor performance。

 And this is be talked about a bunch in the first chapter of the computer architecture or a quantitative approach book。

And boils down to the very basic formula。Where。The time to execute the program。

 So this is the time it takes to run your program that you're trying to execute is equal to how many instructions your program has。

Times。The cycles that it takes to execute one instruction for the program， multiplied。By the time。

Per cycle。So as you can see， it's multiplicative。 So if you can actually make any of these numbers smaller。

The time。For the program will go down， which is a good thing。

 So if you can make any of these numbers smaller and it multiplies out， you can make。

The time of the program smaller。 And what you also note here is they're all equally weighted。

 So if you change any of them， thats， that's a good thing。

One of the things that we should probably do is think about the dimensional analysis or what is the unit on the time for the program。

嗯。Well， let's derive it from the three things on the right side of this equation。Time per cycle。

So what's the unit on time per cycle， It's going to be。

Seconds per cycle or some time you or nanoseconds per cycle。 But'ss。

 let's stick to seconds per cycle。Cyclees per instruction。Okay， what's the unit on that？Well。

 the unit actually is cycles per instruction。So if we do the dimensional analysis on this。

 cycles up here and cycle down there are going to cancel。And then finally。

 we have instructions per program。 And the unit on that actually is instructions per program。

 So the number of instructions in your program divided by how one the program。 And if we。

 you know multiply this out， the unit we're going get here for time per program is seconds。😊。

Per program or time per program that actually is the unit。Okay， so let's。

Think about where these different。Portions come from and how we can affect these three different quantities。

 So instructions per program。Can that be affected？You， you might say， well。

 my program takes 100 instructions， and that's what it takes。 Well， the world's not that simple。

 If you had a different instruction set architecture。

You might have different numbers of instructions。 So if you have something like the MiPS instruction set。

 which is a reduced instruction set， you might actually take more instructions to execute a program than if you were executing on something like a X 86 processor where youre very complex instructions or rather where you have one instruction that can do a whole string copy on something like MIPS that would take thousands of instructions。

So the ISA really matters。The other thing， other thing that can matter here is the compiler。

 If you had a smarter compiler， the compiler might be able to reduce or eliminate code。

 which is redundant or not very important or not important at all， rather。

 or can try to merge two instructions together。 So a smarter compiler can actually affect your instructions per program。

 It can actually change。The next thing is cycles per instruction。Well。

 this is actually dependent on your micro architecture。 As we talked about。

 we'll talk a little bit more in a second。The cycles per instruction。

 if you have a pipeline processor， you might be able to execute。

Or you might take five cycles to execute an instruction or complete a full instruction。

 but something like the microcoded processor we already talked about。

 It might take 10 cycles to execute a given instruction。

 So you can see there's different numbers of cycles per instruction on there dependent on the micro architecture。

 And it also depends a little bit on the instruction set architecture。

 If you have a more complex instruction。 you might need to take more cycles to execute that。

 So something like the string move instruction or the rep moves B instruction we talked about in last lecture on X 86。

 will actually turn into multiple microcoded instruction on something like an X 86 processor。

And then finally， time per cycle， this is dependent on your technology or rather the implementation technology。

 So or the transistor and device technology。 if you have faster transistors that will go down。

 it's also dependent on your micro architectureitect。 If you pipeline deeper。

 you can decrease the time per cycle。Before we move off this slide， let's。

Compare three different architectures that we've talked about so far。

 Both the clocks per instruction and the cycle time。And I wanted to find clocks per instruction here。

 So clocks per instruction is how many clock cycles it takes to execute。That instruction。

And the inverse of this， or if you take one over CPI， you get this other unit measure。

 which is very common in computer architecture called instructions per cycle。 It's just， you know。

 the flip of here。 So sometimes you'll hear us talk about IPC， and sometimes we'll talk about CPI。

And it's really important to know which is which， so you want a low CPI and a high IPC because that means better performance。

Okay， let's look at the micro architectureit here。So we had our microcoded。Architecture。

 and this took multiple clocks per instruction， but the cycle time was relatively short。Okay。

We had our single cycle unppelined processor。 So this is everything just has to flow to the end and but there's no pipeline stages in it。

 And the clock cycle was one。 But unfortunately， the cycle time is long。

So we have to do sort of all the work the microcoded instruction did。

 But it was doing over multiple cycles， but we need to do it in one cycle。

 So we have to sort of add all those things together。 and it's all additive。

 So we have a long cycle time。And then finally， we have a fully pipelined processor where the control is pipeline and the data path is pipelined。

 And here， the clocks for instructions coming out is one， and the cycle time is short。

And as a question。That I want to ask is we talked briefly about the multi cyclee unpipelined control processor。

 So this is the processor where the。You have pipeline the data path。

 but you have not pipeline the control。And you launch an instruction。

 It has to go down the pipe to the ends before you go and fetch the next instruction。

 But it takes multiple cycles。 So the question I have is， what should we put here in CPI。

And what is the cycle time relative to the rest of these？So I'll let you think about that。

And that's right， the clocks per instruction。For this example is going to be more than one。

 or in the five stage pipeline。 it's going to be 5。 We'll say， for every instruction。

But the cycle time is going to be short。 So this is not a great。

 great when you compare it against the pipeline， the fully pipeline processor。

 because the clocks per instruction is 5。Versus one。 And they have the same cycle time。

 So this is going to be five times slower than something like that on average。Okay。

 so let's graphically show some more clocks per instruction。Examples here。

 So if we look at the micro coded machine， we're going to be executing three instructions here。

 Inion 1， In 2， In 3， and time is increasing as you go to the right。

Let's say the first instruction takes7 cycles to execute。 The next instruction takes 5。

 and the third instruction takes 10。 And if you do the math here。

 you end up with three instructions executing in 22 cycles or a CPI of 7。33。

If we looked at the unpilined processor， we have to basically flow through all the the data to the end。

 every instruction takes the same amount of time here。But the cycle time is long， as I have drawn。

 So you have three instructions。 It takes three cycles。 The CPI is one， but the cycle time is high。

And， in an ideal pipeline machine。Well actually have multiple instructions executing at the same time。

 So time goes left to right on this graph。And we'll be able to cut the instructions。

 and an ideal world will have CPI of one。And our clock frequency will also be short。

 And you can see this is sort of smaller than those other solutions。

 And this is why we start to think about pipeing。 But we're using transistors to do this。Okay， so。

As we go along here。Some of the questions that come up is。

 what are the assumptions we made about this pipeline and why are we making these assumptions。

 And if the assumptions were to change， we'd actually pipeline differently。

 So one of the assumptions is that you can put something like a cache in your processor and have very fast memory access because the memory access was so slow relative to the processor speed。

 You probably want to want to put that anywhere in your processor and you might want to pipe the memory。

Another assumption is that you have fast arithmetic logic units to do your， your math。

 and you also have multiport register files， which。Or maybe slower， but you can still build them。嗯。

So if you take these sort of technology assumptions altogether。

 this assumption is reasonable for a five stage MIps pipeline。

 but it changes whenever technology changes or rather device technology changes。

 And you have to reevaluate this。In this class and in previous classes。

 you focused on five stage pipelines， and we'll talk a fair amount about five stage pipelines。

 But we'll also talk about much deeper pipelines in this course。

 We'll also talk about how to go about building those processors。 And to give you an example。

 some commercial designs。 Actually， this is this is outdated。

 If you go look at something like a penium 4。 they have or Intel Pentium 4。

 I think theres about 44 stages in that pipeline。 So they figured out how to cut up executing one instruction into 44 different little pieces。

Okay， so let's。Talk about pipeline diagrams。 So one of the important things we need now is to。

Think about the nomenclature and think about how to draw instructions executing down a pipeline。

 Because if you want to answer questions about。Where instruction is or how an instruction executes。

 we need some way to draw it graphically， because if you don't draw it graphically， it's。

 it's really hard to reason about multiple things going on at the same time。

 And this is what we're gonna try to solve here。 is we're actually executing multiple instructions at the same time。

 There's perilism going on。 There's multiple instructions in flight。

 And you have lots of overlapping。So the first pipeline diagram we're going to use here will plot transactions or instructions versus time。

 So we're going to put time。On the horizontal axis here。So we have time T 0 to T 7。

 and it's increasing。And now， we're going to have。An instruction flowing down the pipeline。

And right now， we'll look at an idealized pipeline of idealized instructions。

 We'll soon be looking at non ideal pipelines where there's dependencies between the different instructions。

And this slide is really important for this class。 And if you don't understand this。

 go back and watch this again， because the。Understanding pipeline diagrams is going to be key to this class and be able to draw these yourself is going to be very。

 very important。 So let's， let's look at an instruction flowing down the pipeline here。

So we have instruction 1 at time 0。 it's in the instruction fetch stage at time。One。

 it's in the decocode stage in time 2， it's in the execute stage in time 3。

 It's in the memory access stage and in time 4， it's in the right back stage。Okay， that's basic。

 Now let's put another instruction on here。It goes through the same set of stages。

But it's shifted by one because it can't go and use this resource。

 It needs to be fetched the next cycle。 So it's not going to be executed in cycle T 0 or time T 0。

 is's gonna be fetched in the next time。 And what you'll notice here is these resources。

Or these pipeline stages don't have multiple instructions in them at the same time。

 There's certainly only one in each pipeline stage at a time。So we put on more instructions here。

And this is what our pipeline diagrams are mostly going to look like in this class。

 is we're going to have transaction or instruction versus time pipeline diagrams。

 And we're going to plot these out。 And you'll see that instructions sort of flow down the pipe。

And what's what's really cool about this is if you draw a vertical slice or you draw one slice through here。

You can freeze time and see what is in every stage of the pipe。 So if we freeze time here， T 4。

Instruction 5 is in the instruction fetch stage。 In 4 is in the decocode stage。

 Instruct 3 is in the execute stage。2 is in the memory X stage。

 And then instruction 1 is writing back and finishing。

And it's really important though when you're drawing these diagrams。

 that only one instruction is in each stage at a time。 if you ever draw something where you have。

 let's say。This instructions is in the right back stage and this instructions in the right back stage。

 That's a hazard or a structural hazard。 You made a mistake somewhere in your diagram。

 or you had to stall a processor or something else has to happen。

So make sure that when you slice your time vertically here or look at one time segment that you don't have multiple things in that time segment at the same time。

We can also draw a different pipeline diagram。So this pipeline diagram is instead going to plot space。

Versus time。Or resource versus time。And this is gonna be less common in this class。

 but it's still useful to think about。 So what we have here is we have time on the horizontal axis。

 and we have resource on the vertical axis。So we have here the fetch， decode， execute memory access。

 and then rippack stages of the pipe。 And we can see that we have different instructions flowing down the pipe。

 So instruction Fe has instruction 1， then In 2 and In 3， In 4， In 5。Flowing down it。

 And this is sometimes useful。 Likewise， you can cut vertically here and see at a certain time。

All the instructions in your pipeline。So it's， it's a useful diagram。

 but it's a bit less useful than the previous one。 And when I refer to things as pipeline diagrams。

 I will be focusing on transaction versus time pipeline diagrams。Okay。

 so now we're going move off idealized pipelines and talk about。Non ideal pipelines or why pipelines。

Are maybe not ideal。And we're going to introduce a piece of nomenclature here called a hazard。

So a hazard is。Anything where you have multiple portions of your pipeline interacting in a way that will cause。

 cause a problem。 So， and there's three， three main types of hazards。 We have structural hazards。

 data hazards and control hazards。A structural hazard is an instruction that's in the pipeline that needs a resource which is used by a different stage in the pipeline or someplace else in the pipeline。

 A data hazard is when you have two instructions and the two instructions are dependent on each other somehow。

 So the one instruction to generate some data。 and the other instruction needs to use that data。Well。

 that's that's called a data hazard。 You need to make sure you get the data。

 which is computed by the earlier instruction and somehow move it to the data to the input of later instruction。

 And that's kind of key to actually executing code on a processor is being able to do that。

 And we call this a data hazard。And then finally， there' control hazards。

 Control hazards are another type of dependency， but it's a dependency， which comes from having to。

Change the control flow of the program。 So an example of this is something like a branch or a jump instruction can cause a control hazard。

 So it's a dependency based on some control decision made by an earlier instruction。

 So if you have earlier instruction， the branches， the later instructions have to be the ones at the target of the branch。

 we'll say， and you can't just execute the ones which are the fall through for the branch。



![](img/d84a78d88e72b607d83dc8abc401b5df_2.png)

![](img/d84a78d88e72b607d83dc8abc401b5df_3.png)