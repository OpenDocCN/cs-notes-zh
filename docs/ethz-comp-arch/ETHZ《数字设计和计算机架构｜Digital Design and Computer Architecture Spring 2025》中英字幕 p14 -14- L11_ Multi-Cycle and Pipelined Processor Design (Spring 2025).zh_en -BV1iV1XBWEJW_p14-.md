# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p14 -14- L11_ Multi-Cycle and Pipelined Processor Design (Spring 2025).zh_en -BV1iV1XBWEJW_p14-

Yeah。

![](img/833ea6c08e0c3e19afbe7578c4370f2c_1.png)

Yeah。方址。好。あ。あね。O。そね。哎好。Good。Yeah。就我们这个。这个意思这里。おめめ。そ。やそ。ど。行啊。不。あす。么还会。然。这这人。后面。可好。はこか。现在。あての。ま。す。嗯。さい。

は決めたい。そか十ま。喺边个。这。Yeah。Oh。This。3个。啥。没在。Yes是。Its。I't。这哪で。好。少。佢哋过噶。さ？Yeah。て。想见。在的话。あ。What。Yeah。で。为什么不。

我为你好。Yeah。🎼Oh。Okay。I think it's time。It's good to see a lot of people Fridays are a bit lonely here。

Hope to see more of you during Fridays。Okay， today we're going to continue what we started in the last lecture。

 which was multie processor design remember we're still covering micro architectureure。😊。

We have been designing the micro architectureure of a very simple MIPS processor for the last couple of lectures and we decided single cycle cluster design is not a good idea it violates three major fundamental principles which we will very quickly get to today just to jog your memory today we're going to。

😊，Design the full multie processor。Well， full， full for a subset of the MIPS I say。

 following your book， there's more in your book that talks about it。

 and then we're going to jump to pipeline processors which are actually the type of processors that we have today。

 but we'll actually build on pipelining also。Okay， you have an assignment。

Extra credit assignment two if you want to get extra credits April 1st。

And this is where we are I kind of covered all of this my goal by the end of this week is to finish pipelining we're going to cover a bunch of issues in pipelining and then next week we're going to talk about state maintenance and recovery precise exceptions。

😊，And out of order your execution， does that sound good？Okay。

 yeah by the end of next week you will know how a modern microprosor actually processes instructions in an auto order manner we're just building up to it right now。

 but we need to build up to it because you need to see what is data and control depends and languages pipeing etc and these are some of the readings for multicycle micro architecture I'm going to follow H and H。

😊，Chapter 7。4 which actually does a good job I think pattern Patel appendices。

 especially appendix C builds a full LC 3B micro architecture it's a very good one I'm going to briefly talk about it but if you're really interested in looking at it I would suggest looking at it because that gives the concepts very nicely and then we're going to talk about pipeing okay multicycle just to recall basically our goal with multicycle micro architectureures is to let each instruction take。

😊，Only as much time as it really needs， as opposed to the worst case instruction determining the clock cycle time as it happened with single cycle architectures。

 right？😡，And this is kind of the pictorial view， you have an architectural state at the beginning and every clock cycle you do something and update some micro architectural state to processing an instruction until at the end of the instruction。

 you finish the processinging and you update the architectural state。😊。

So we can we can use multiple clock cycles to process every instruction and you can use different number of clock cycles to process different instructions。

 and you can determine the clock cycle time independently of how long it takes to process any instruction。

And we said that you could do this by building a state machine and we're going to build that state machine today。

 a small version of it。😊，And this was the full state machine for LCC3B that we partially covered。

 but we're going to build a new one， not for LCC3 for MIPS。

 and this is the LC3 multicycle implementation if you read appendix C you'll see a lot of this。😊。

Okay so basically these are what what we aim to accomplish with multicycle design。

 we want to have a better critical path， reduce the clock cycle time。

 we want to optimize the finiteate machine for important things that we want to execute for example the most common workload。

 most common instructions and we want to have a balance design。

 we want to provide capability no more than that's really needed you have already seen these。

 but this will come at an expense if every idea there's an upside and a downside if you find some if you're given an idea and we want to analyze it always look for the upside and the downsides there's nothing without an upside there's nothing without a downside upside or downside may be different in terms of weight but they exist okay so in this case we're going to need to store the intermediate results at the end of each clock cycle and we're going to pay both the hardware overhead for that as well as a sequencing overhead meaning we're going to waste。

😊，Part of every clock cycle， as we've seen in timing and verification。

 And we're also going to see that we are going to have limited concur and we're going to solve that problem partially with pipeing。

😊，Does that sound good。Okay so you've seen all of this and this is a slide I stopped at last time basically we wanted to have a closer look at a multicycle micro architectureitecture。

 this is actually an idea that was developed by Maurice Wilkes who is a pioneer in the field of computer architecture and computer micro architectureure and he developed the concept of microcoded microprogram machines that we're going to see soon。

 but a lot of these concepts are based on his descriptions。😊，Okay。

 so basically the key idea of realization for realization for realizing a multicycle micro architecture is to see the process instruction step as a finite take machine。

😊，That sequences between states and eventually returns back to the fetch instruction state。

 So you keep doing this。 So you have a finite state machine that implements your entire ISA。

A state is really defined by the control signals asserted in that state。😊。

And control signals for the next state are determined in the current state so that we don't we can parallellyze processing。

 we don't need to waste part of the clock cycle for determining control signals makes sense。

 we've discussed a lot of these actually so now we're going to implement a basic one so we're going you've seen actually a lot of these concepts so hopefully a lot of these are familiar but the implementation will be similar to what we have done with single cycle we're going to start from a basic instructions and we're going to start from the data path and we're going to start adding things to the data path。

But essentially we're going to see instruction processing cycle to be divided into states and each stage in the instruction processing cycle can take multiple states and we're going to sequence from state to state to process instruction that's what a finite state machine is right and you've seen this a long time ago in these lectures。

😊，And the behavior of the complete machine in a state。

 the behavior of the entire machine a state is complete determined by the control signals。

 stored in that state， similarly to the control signals we had in a single cycle that essentially determine what the data path elements are going to do to the data and the instruction。

 etc ce， we're going to do the same thing， control signals are going to determine everything in that particular state。

😊，And the behavior of the entire press is specified fully by a finite state machine。😡。

So in a state or in a clock cycle， control signals control two things。

 how the data path should process the data as we have seen in the past and how to generate the control signals for the next clock cycle and this is what we have seen so let's build another example multicycle micro architectureecture。

😊，I'm going to follow your book so if you're interested you can look at your book。

 I don't remember if it's 7。3 or 7。4 maybe someone can verify this。

 maybe the figure is in both places I felt it was I thought it was 7。4 but this is 7。

3 so there might be a bug over here anyway， but this is a multicycle machine that is built by your book that supports a subset of the MIPS in sections at architecture。

😊，Oh， actually， this is a single cycle of micro architecture sorry this is correct。

 this is a single cycle that we developed up in your readings。😊。

So what is the issue with this single cycle right so we're going to build chapter 7。

4 from here so in the single cycle we already discussed this a lot so cycle times limited by the longest instruction you have low clock frequency。

 but we also said you have a lot of adders and ALUs and memories this gives you high hardware cost。😊。

Because you have to provide the。All of the combinational resources to process a single instruction。

 a given instruction in a given clock cycle If a given instruction needs to access memory twice。

 you need to provide the resources for that If a given instruction needs to do multiple additions which many instructions need to do。

 they need to increment the PC for example by four， they need to do an addition。

 they need to do something else， you need to add adders all over the place right you cannot reuse the same matter in a multicycle。

 we fix these problems you get a higher clock frequency。

 you get simpler instructions that taking only a few clock cycles and you can reuse expensive hardware across multiple cycles so I going to show this when we build the data path。

But of course we know the downsides also I'm not going to repeat that so when you want to design a multicyclemic architecture you go through the same steps as single cycle what did we do in the single cycle last week。

 we basically designed the data path right how did you design the data path we took every instruction we said okay let's start with our type instructions let's build a data path for that and then we added i type instructions and then we added load instruction and then we added store instruction and then we added branch instruction and then we added jump and then we stop there because you could keep going forever doing that you do the same thing basically you design the data path you add the control signals and then you designed the control logic so there's no magic you follow the same steps to construct a multicycle processor except it's a multicycle processor it's not a single cycle process。

Okay， so what do we optimize of course， when you construct the data path， you need to think。

 meaning what am I going to do in my data path right now I can optimize things as opposed to using two memories。

 we can only use a single memory and we're going to see that。😡，呃。It's going to be much lower cost。

As opposed to using three addressers， one for ALU， which you need， one for PC incrementing。

 and the other for branch address calculation， we're going to use only one ALU for all operations。

 and this's going to lower the cost again。As opposed to having each instruction take one cycle。

 we want to determine the clock cycle independently of instruction processinging side。

 so when we actually design the data path plus the finiteate machine。

 we're going to divide each instruction to multiple clock cycles okay？😊，Make sense。Okay。

 so let's construct a multie data path in this case we'll start with the load word instruction because why not？

😊，Last time we started with an ad instruction， why did we start with an ad instruction， why not？😡。

Basically， there's no real reason to pick one instruction over the other because in the end。

 you're designing a datapa for all instructions。And if you're going to execute all instructions。

 you might as well start with some random instruction also right and it's also good to think about okay。

 maybe you start with common case instructions right maybe why not is not the best answer a qualified answer is。

😡，Which instruction is going to be the most important one for me loads ads those are pretty common instructions so you can start with those without any let's say downsides so remember the load instruction essentially what this load instruction is it as a destination register。

 it is a source register， essentially it computes the address by taking the source register adding to it an immediate sign extent immediate。

And reads the content of the location in that memory address and then gets the data and puts the value into the destination register。

 I'm not going through the encoding， etcter because we've seen this but the encoding is kind of here it's an eye type instructions in MIPS essentially fetch is really the same for all instructions for load step one is really fetching the instruction but to construct the data path you need a program counter。

 you supply the program counter to the memory that we have seen before if you remember from earlier lectures you input the program counter to the address port of the memory and then you get the data from the output port of the memory and this data is really your instruction and you were going to latch it in an instruction register。

😊，We're going called the instruction register right signal to enable or write enable this register So if we added one control signal here。

 there's another control signal here， which is the right enable of the memory over here and we have one memory to begin with。

😊，Does this make sense， so this is our first cycle essentially and first cycle is defined by the control signals associated with it。

 IR right should be one， all other control signals over here should be do no harm。

 we have not constructed that yet so we're going to build the control logic later。😊，Okay。

 so that was the fetch， that was easy clear clear， this is common in all instructions。

 all instructions do this。😡，Okay， so the second step is to read the register。😊。

And the way we do it is essentially you take some bits from the instruction over here which is one of the source registers。

 we're going to calculate the address using that this is the base register if you think about it that's 26 through 21 supply to the register file and get read get the data out of the register file from the first port because we supply to the first port and latcht into a pipeline register over here so essentially adding registers as you can see so that at the end of a clock cycle we can store the output of what happened in that clock cycle so that's the difference from the single cycle we have not constructed the entire thing we are actually doing its step by step。

Of course， you need to also determine what to do in a cycle。

 but I'm assuming these are the things that we determine to do in a cycle for now。Okay。

 so you need to sort the control signals to enable this which are not that many actually。

 this is register files automatically enabled， theres no right enabled。

 you need to do no harm to the register file at this point when you're actually reading a register for load etc。

 and of course I'm not connecting other things that I don't need for now but we're going to use them later on。

😊，Okay so load word actually what load word does is it takes a register。

 which we actually latched over here in this it takes a general purpose register base register which we latched over here。

 concurrently you take the bottom 16 bits of the instruction sign extended。

 and that's going to be our sign extended immediate value that we're going to add to the base register。

😊，But we're not ready for that yet。For that， we need another cycle。 The next cycle。

 we basically take whatever was stored in this。Let's say let's call the a register register file aport register。

 send it to the ALU through a wire and send the sign extent immediately to the ALU and set the ALU control it to do addition because we do base plus offset if you remember and the ALU result will come out and you store it into into this register now this register is going to be the ALU output register okay。

So that's our third cycle， so one cycle fetch the second cycle， register read third cycle。

 generate address。😊，We're not done yet。 We generated the address。 What do we do。

Now we're going to do something that we cannot do in a single cycle architecture。

We're going to basically。Take that address。Loop it back into the address port。All there。

Instruction slash data memory and we're going to select that one in this cycle so that we actually access the memory with the address that is generated by the load instruction in this particular state okay so earlier in the fetch state we use the program counter to access the memory here we want to use this address that we calculate it to access memory so we need to add a multiplexer for that and we need to add a control signal to control that multiplexer basically are we doing an instruction access or data access。

Makes sense， right？Okay， now you can get away with using a single memory， as you can see。

 that's the beauty of multie architectures， one of the beauties。Okay， I think I've said this。

 but of course， you cannot use this memory for both instruction fetch and also data fetch in the same cycle。

😡，You can only do instruction fetch in one cycle and data fetch in some other cycle right and you control how do you know what you're doing control signals decide that what are the control signals determined by they're determined by the control logic。

😡，Which are based on which state you're in， okay？Okay， so now we read the memory okay。

 this is the address that we input into memory， we get the data after some point。

 we la it in a different register。😊，And that data is going to go to the register file in the final state of execution of the load。

 you basically take this data。Put it into the data input port of the register file。

 and you take this register identifier， which is a destination Reg identifier，20 through 16 Rt。And。

Essentially you assert the right signal because at this state we're going to write this data that we lashed in the previous cycle to this Reg ID because we are asserting the Reg right signal and because that's what we're supposed to do at the end of the execution of the load。

 right？😊，And that finishes the execution of the load。

 that's the entire data path you need to execute the load。😊，Not really。

 we forgot to increment the PC， right？😊，Okay。So we're almost done basically with the load。

 this is what happens with memory access， writing the data registergistry address calculation。

 etc cetera。 it took a number of cycles as you can see now let's also increment the address。😊。

Now your book does a fancy thing， that's why I follow your book。

 it basically shows that you can use the same adder ALU that you use to calculate the address in a previous cycle to also increment the PC。

So how do you do that basically？You take this program counter。呃。Go through here。

 add another multiplexer over here because we were going to input the program counter into the ALU earlier we input this register into the ALU so you select between the program counter or the register so there's an ALU source A multiplexer there's also an ALU source B multiplexer that got expanded a little bit more than load needs over here which is fine because it's going to be needed by other stuff but basically source B can come from this register which we're not used yet but now we need four well we use actually sign extent immediate so we can select between sign extent immediate or4 sorry what happened。

嗯。🤢，Okay， increment PC。Basically， this AluU source selects PC， which is zero。

 this AluU source B selects four because we are going to do PC plus4 and ALU control should be set to addition over here and we take the ALU result。

And put it into program counter， so we need a PC right signal to write enable the program counter register。

So to be able to increment the PC， we jumped through a lot of hoops because we didn't want to add another adder。

😡，This is a design choice that the designer of this processor made。

 I wouldn't make this choice and LC3B designers didn't make this choice in appendix B if appendix C if you look at it。

 they basically have an incrementer for the PC that's basically that can be done concurrently with everything else because of this design choice essentially a PC can there's more complexity over here。

 but this is a design choice is a perfectly valid design choice in the end they avoided adding an adder。

😡，Makes sense。Okay， so it's beautiful， right as you can see， you can get away with a single ladder。😊。

Okay。As long as you control it so that you do the right things at the right time， right？😡。

And don't forget to increment the PC okay that was load now we're done with the load。

 but load actually enabled us to fetch an instruction。

 deco an instruction then also increment the PC so we don't need to add any of those four other instructions now let's take a look at store for store we know how to access memory right okay basically what we need to do is we do everything very similar to the load。

 generate the address but at the end we need to actually access another register which is the store data register using bits 20 through 16 and also store it somewhere when we actually access the base register we also access this register。

😊，And then get the data value and write it back into MEmy。At the specified address。

 when the address calculation happens at that cycle。And we need to assert the memorymorite signal。

 so this is very similar to what we have done with a single cycle。

 we moved from store load to store if you remember over there。

 similarly we need to we have the entire data path almost we just need to read another register which is going to be the data that's to be written by the store to the memory。

😊，And we need to provide the data path element and storage for that this register。😡。

And then we need to take it and write it to the destination to the memory at the address that is computed the same way the address of the load is computed。

 I'm not going to compute the same address， but you already have the data path elements and essentially essentially this address。

 right？Yeah，L result that address over here， you just need to assert the mem right signal and do the IOD signal accordingly。

 Okay， so Stboard is very similar to load except you you write to memory。So子 good。Okay。

Now let's look at our type instructions， so this was storewart our type changes the pipeline a little bit。

 again I will not go through the entire thing because otherwise it will take forever。

 but basically you need to read from both registers。

 RS and RRT and also you need to write to RD destination register。😊，So to enable this。

 So what does our type instruction do， our type instruction actually。😊，Does two reach two registers。

 these two registers in this particular case so we already have the data path elements because of store actually and then we send the second register to the ALU also store it and need that install store the second register goes to memory here we're doing basically add R1 r2 store the result in R3 for example。

 so we get one register over here into the ALU the second register over here into the ALU and at that state you do the calculation store the result in this register now at the right back stage of this part of an R type instruction we take the result in the ALU and we need to put it into the register file。

So before we were actually doing something else into the register file right this one was coming load was loading this data into the registers file so you need to add this multiplexer to decide and this multiplexer is very similar to the me to reg register that we have in a single cycle design if you remember that me to reg register you either take the ALU output and put it into the register file or you take the memory output it's essentially the same register that you have well same multiplexer that you have except that multiplexs between this register and this register okay one register stored the data that we read from memory in the load instruction and the other register stored the data that we calculated as a result of the ALU operation okay。

And then we already had this marks in the single cycle architecture also because of the specific encoding in the ISA in our type instructions。

 remember the destination register is really， I think 15 through 11 as opposed to 20 through 16。

 so you need to select 15 through 11 as your destination register in i type instructions it's 20 through 16。

 This is based on the encoding so it's very similar to what we had we just need to build the data path again。

😊，长子个。Okay so let's do branch branch is going to be also interesting over here so you need to provide support for two things over here one is target address calculation and the other is branch condition calculation and we already have most of this now the interesting thing is your book uses the same ALU to do both the branch condition calculation as well as the target address calculation it's also another design choice that Pat and Patel book makes differently they have a special adder for branch target address calculation here everything goes through the ALU so let's first let's first figure out how to calculate the branch condition remember the BQ instruction in MIPSsa it checks whether two registers are equal R1 and r2 or our source1 and our source whether they're equal so you read these two registers theyre stored in A andB we already have the data patent elements for that you check whether they're equal so ALU control is checked set to subtraction for example。

😊，Then there's a signal coming from ALU nowob saying whether it's zero， that means they're equal。

 this is asserted if they're equal， branch is asserted when you're executing this instruction。

 so if they're equal and branch is asserted， then this an or PC is enabled。

And then you can write to PC。Whatever you compute in a cycle。

 so this is assuming that ALU can do a lot of our patients， as you will see。

So basically the calculation of the branch is done this way。😊，嗯。Okay。Yeah。

 calculation of the branch is also done through the ALU in your book basically the way you calculate the target address is you take PC plus4 which was stored over here at some point。

 so based on the design of the finite tape machine you already stored PC plus4 in your PC。

 you take that and you input that into the ALU in a different cycle you need to do that in a different cycle because otherwise ALU is doing this computation。

 also that computation or you actually have two ALUs or you replicate the gateil of the ALUs。

 but you basically take PC plus4 add to it the sign extended immediate left shifted by two you select the right things of course with these two multiplexs and then take the ALU result and that gets lashed over here and that ALU result gets input into the program counter by selecting the right PC source okay。

😊，Makes sense， so you can use this data path， but you need to make sure these actions are done in the appropriate cycle。

 so there needs to be a finite state machine that says I'm calculating the branch condition this cycle and storing it here and then I'm writing I'm calculating the target at in the ALU in this cycle and storing it here and then you actually do the update of the PC after all of this is done so there needs to be an orchestrator which is really the control unit that goes through the states。

 every state state by state sets the appropriate control signals to make sure that the data path does what we want to do。

 but with this data path you can actually do it。😡，Okay and this is the complete multie processor in your book again your book goes through this similarly to what I did if you're interested you can study it now what we have done is we've added a bunch of extra registerries。

😊，So these registers did not exist in a single cycle design。😡。

Now the upside is we have only one memory and only one ALU and adder。

 so your book kind of stretched the limits and with only one ALU it did things， but of course。

 if you have only one ALU maybe you increase the number of states that you have in the finite state machine for different instructions。

 right？Because when you're doing PC plus4， you cannot do something else when youre doing branch condition calculation。

 you cannot do a target address calculation， right？😊，Okay， hopefully that makes sense。Okay。

 now let's construct a multicycle control logic。 We have constructed the data path。😡。

We have added the control signals these blue things are the control signals in this case now we can construct the control logic I'll go through the control logic relatively quickly。

 but essentially we're going to construct the finite take machine this is going to be our controller we're going to supply the up code to it and there will be a finite take machine that determines all of these control signals。

😊，I the ALU operation， there's also a fact， if you remember in MIPS that determines what the instruction should do。

 I'm kind of ignoring it because we kind of covered it earlier。

 but these are multiplexuous select signals and also register write signals。

 register write enable signals。Okay， so let's start with fetch， we've already seen this actually。

 but you need to do this after you design the complete data path， of course。

 because you need to make sure you set every control signal to an appropriate value。😡。

So in this case， what so fetch looks like this basically IRD needs to be zero so that we select program counter and input it into the instruction register address memory address port。

 we don't write to memory so。😊，Memorite should be zero， clearly， the IR right should be one。

 meaning we're going to write to the instruction register。

And we're going to update the program counter， so that should be enabled。

 meaning PC right signal over here should be one， this is not a branch when you are fetching there is clearly not a branch so that should be set to zero。

😊，And a PC source over here should be set to zero so that we get， yeah， we essentially， let me see。

Yeah， we essentially set the L result over here right okay so basically this is the fetch state over here。

 you're fetching the instruction and you're also incrementing the PC， right？😊。

Because incrementing of the PC happens this way， as you can see， right， you basically take the PC。

 which was here。And you add to it for。And you get that into the PC so the control signals are needed to access memory as well as increment the PC So what are the increment the PC control signals One is AluU source A。

 this multiplexious source should be PC as we have discussed earlier。

 Alu source A source B should be4 as we discussed earlier， AluU operation should be add010。

 that's the code of add and we should take theLU result over here and send it to the PC。

And PC rights is already enabled Does that make sense， So that's the fish state。

 You need to do this for every single state， which clearly we're not going to do because we don't have time。

 but there's no magic over here as you can see。And your book is not complete because it doesn't list all of the control signals over here。

 but you can actually list， you can actually figure out the control signals on your own。 Okay。

 so that's fetch。 We fetch the instruction。 It's in the instruction register right now。

 Now we go to the decocode state。😊，De quoteote state actually。😊，s relatively simple。

 you basically read the registers because it doesn't do any harm。

 assuming it's needed and you basically don't do anything in the decocode state in your book deco state is kind of empty except do no harm of course。

 meaning we don't write to any register except for this one。

 but this doesn't have a right and enable signal anyway。

 okay basically we always read from the register file according to this design。😡，Okay。

 so the next state， let's assume that the up code is load word or storeward， we jump to the state。😡。

Both of them go through a memory address calculation stage clearly。

 so we kind of consolidate the finite state machine for both of them in the same state over here so this is the address calculation stage we set aL source A to essentially come from the register file base register AL source B to10 which is signine extend immediate and we set the AU operation to add and essentially the results get stored over here there's no right enable signal needed for this so you can see now we are actually using the data path by setting the control signals accordingly and all of the other control signals are set。

😊，So that we do no harm for example， we don't update the program counter。

 we don't update the instruction register that would be terrible because we're processinging this instruction right we should not update the instruction register until we're done with this instruction some of these are x's as you can see I don't care because you're not updating the memory for example I don't care what I do with it I'm not updating the program counter so I don't care what the multipleor selects etc so it's very similar to what we've done in the single cycle except we do it now state by state by state okay。

Okay so this is the complete load word state machine again I will not go through this。

 but you all after this， if the operation is load word， you go to a memory read state。😊。

And memoryory RE state basically has some control signals that you can also select and I'd recommend you doing it on your own if you're interested。

 IOD needs to be selected to be one so that you actually get the address from the ALU output just like we have built the data path。

 and then you go to a memory Write back state， meaning you write back the data value that you get from the memory into the register。

 just like we built the data path and you set the control signals accordingly。😊。

This is the complete load word execution， one， two， three， four， five cycles， as you can see。

 five states in the finite state machine。But we also played some tricks to merge states as you can see right we decocoded it and then we said if the operation is load word or load if the up code is load word or storeward we jump to the state and then if we're in this state and the up code is load word we jump to the state so there needs to be some sequencing logic that basically determines which state you go to from this current state and we've already seen that in the finite state design design right finite state machine design。

😡，Okay， Stwart。😡，Essentially after calculating the memory address， if the op code is storedward。

 you go to a memorymorite state， if you will， and here IOD is set to one again because the address is coming from essentially sorry。

 address is coming from here， not from here， not from the PC it's coming from the ALU result and we said memorymorite to be one。

😊，So that we can write to memory right here memorymorite is not set to one when you're reading from memory and then store word doesn't have an extra state because that store is done after you write to memory there's nothing you do with the registers after that point right so store word takes one。

 two， three， four cycles。😊，Okay， now we could keep doing this for all instructions。

 so if the app is our type after decoding， you go to an execute state。

 you set the appropriate signals in the ALU so that ALU gets the right inputs。😊。

And you set the ALU off， et ce， and then after the ALU generates the result。

 you write it back to the destination register by going into another state， right？

So you set the control signals accordingly just like we did， so I'm not going to do that again。

 but you can convince yourselfsve that this works。😊，Okay， that was our type。

 and then there's BEQ over here。😊，BEQ is a little bit more complicated， but you can also do that。

 but I'll leave that to you so there's only one state over here that enables BEQ。😡。

And in BQ actually there's one trick that your bookplace。

 it determines the branch condition over here， which is interesting over here。

 it determines the branch condition over here and then it basically calculates the target address over here and update the PC using that。

 so this is all done to determine the branch condition so that you can actually essentially if you can look at it it sets Alu source A to0 which is PC which is the updated PC alreadyD because we update the PC in the fetch state if you remember。

 Alu source B to 11 which is sign extended immediate leftshift dot。😊。

And basically it does an edition in the ALU or something like that in your book。

And then in the next cycle， it determines its。Actually， is that true Yeah。

 I think it it does one way or the other， Probably it actually first determines the it first it calculates the target address that's what it does first and then it calculates the branch condition Okay this makes sense because if you look at these control signals this is really calculating the target address and these control signals are actually checking whether the branch condition holds if two registers are equal and if that's the case then you take the target address that you've calculated and place it into the program counter。

😊，Okay。Ass a question， Okay， no yes question。规反生区。It。这生。I cannot hear you very about。

 can you speak up？そです。Yeah。7。be have works today， for example， fetch structure。

Then we have to kind of wait one stage then the next stage queue that in。

 I think you this this fetch instruction。not story， but it has。So we it right。

 we store it in the instruction register。😡，So it's here yes。ほら。For example， slide 4 slide 40， okay。

 let's go back so we store it in the instruction register right this is the instruction register and you never update it yeah。

 that's why yeah you cannot do this in a single cycle machine in a single cycle machine there is no instruction register right。

But yes， the instruction bits need to remain， everything that you need to use later needs to remain。

 that's why you need to store them in registers。Yes， okay。Sure。O。Okay， great。Okay。

 so that was BEQ now we didn't do i type instructions but i type instructions like addI。

 you can also add it over here。😊，They require control signals again。

 you can go through it and figure it out basically this is the construction process。😡，To do jump。

 you need to extend the data path a little bit。 your book has a slice description that okay。

 if you want to do jump， you extend the data path slightly。

 So how does jump calculate that if you remember we take。😊，The bottom， I guess。

 26 bits from the instruction register。And left shifted by two and then extend it and then add。Yeah。

 I think we all need to， yeah。Yeah basically concateated with the PC all of these are done in this logic and then you basically update the program counter。

 so there's another way of updating the program counter which needs to extend the multiplexer and also needs an extended control signal for the PC source we did this actually in the single cycle processor as well。

 but if you want to add instructions you essentially need to add data path elements。😊。

And also new control signals potentially okay and then you actually need to change the control signals that you've done over here so if you forgot forgot an instruction for example。

 no worries you just need to add the data path elements。

 add the control signals and make sure all of those control signals are updated in all of your states accordingly so that you do the right thing so that that's one of the other beauties of this machine in the sense that you can easily modify things this sort of structure finite state machine enables you to modify things easily。

😡，OK。Okay， so basically this is the construction， maybe I took a bit more time than really I wanted to on this topic。

 but we construct a multicycle MIPS architecture right now。

 which is a similar process to constructing a single cycle architecture。

 but it's a little bit different because now we break things into multiple cycles。😊。

So this was our single psychomPS architecture， micro architecture。

 and this was the thinking over there， and this is our multicyclmPS architecture micro architecture。

 they look very similar， but now we have a lot of registers to store things like the instruction register pointed out by your fellow student。

😡，And if you want to learn more， chapter 7。4 does a nice job over here。So I'll ask you one question。

 one of the issues over here is it assumes something about memory and this is what we have assumed in single cycle so we assume memory takes a single cycle。

😊，Actually， memory doesn't say single cycle， memory it takes multiple cycles。😊。

And so there are some memory read states， for example， memory read over here， memory write。

 even here， fetch， we assume memory takes one cycle， right？

So how do you actually accommodate multi cyclee memory， basically， it's very easy in this design。

 actually。😊，If your memory has a signal saying that I'm not ready， I didn't supply you the data yet。

😡，Then stay in the same state。Right。You need to be a little bit more careful。

 you don't want to update the program culture multiple times that there's a danger over here。

 but you need to stay in the same state， if the memory is not ready over here。

 stay in the same state until the memory provides the value。😡。

So this a conditional change of the state again， yeah， I already said this。😊。

And memory needs to provide some bits or input to the control logic that determines the next state。😊。

And actually you have seen this kind of before when we looked at LC3。

 there's a MEmi access state and if you look at this MEmi access state。

 you wait for MEmy until the ME is ready， if the ME is not ready， this is not R or our complement。

 you stay in the same state if it's R then you go to the next state right？😊，Another memory access。

 another memory access， another memory access， so there are a lot of memoryaces that you do in a real instruction set architecture。

 and you do the same thing in all of those。😊，So that's a more realistic way of doing it。

 your book kind of assumes that， okay， it's one cycle。Okay this is something I will not go through。

 but I will recommend people to look at the book Appendix C or Pat and Patel basically very quickly what they introduce in that design is slightly different the principles are the same it's multicycle etcter but it's also a little bit more structured now let me quickly describe what it is essentially you have control signals it's a microprogram design。

😊，Again， I will not build this， I will not go through this in detail。

 but I'll give you the key idea you have control signals associated with the current state they're called a micro instruction。

😡，And the act of transitioning from one state to another is that requires determining the next state and the micro instructionion for the next state that's called micro sequencing。

And there's a control store which stores control signals for every possible state。😡。

Just like a small memory， it stores the micro instructions for the entire finite state machine。

 you can think of as like a program。😡，And micro sequencer determines which control signals will be used in the next clock cycle。

 in a sense， what we' are doing as hardware designers after we design the data path and the control signals。

 and if you think about it this way， you're microprogramming a machine。

 you're not programming it in the ISA level， you're programming it at the control signal level。😡。

And the program is really stored in that finite S machine。

 your finite S machine describes your program and your control store stores your program and you sequence from micro instructionion to micro instructionion and each micro instructionion determines the control signals in each state now if you think about it this way。

😡，It becomes very interesting right we're programming a machine at the very very lowest levels it's called microprogramming and this actually enables a lot of interesting things so this is what Pat Patel book shows you have a micro sequencer that determines the next state address of the next state and essentially address of the next instruction you can also think of that address of the next micro instructionion you access using that address。

 the control store which gives you the micro instructionion which are the control signals that you will use in the next state and that micro instruction supply to the data path so that you do whatever you need to do in this state and while the data path is happening。

 you also micro sequence to the next instruction and this is the full system over here that data design including memory and IO。

 which is pretty powerful。😊，Okay I think essentially the control signals for the current state controlled crossing in the data path as well generation of what's the next micro instructionion to process and data path and micro sequencer actually operate paid concurrently I think I already said this hard this on multiple times so I'm not going to ask that question but this is for your own study it's beautiful。

😊，I will not cover this particular slide， you can find it in appendix C。

But you will see that there is a control store， this is actually the program。😡。

This is how you program the control signals of a machine。😊。

Each entry in the control store is a micro instruction corresponding to the finite aid machine state。

And you actually use the address of the finite state address of the state or address of the micro instruction to get the relevant micro instruction。

Before I conclude let me say a couple of things so this makes the data path very powerful why am I telling you this so you can actually this is micro programminggramm you can actually go so how do you design a machine you designed the data path you design the control signals and then you go fill out this table for example this is the finite state machine part for load instruction that's someone designed it's very similar to what we designed earlier give or take a couple of things this is the micro sequencer someone designed。

😊，And now you go and fill out the table， this is your micro program。

 these are your micro instructions。😡，So this enables an abstraction right so earlier we had assembly programming now we actually control signals。

 but going directly from assembly to control signals， now we introduce some other abstraction。

 which is micro instructionsions right？😡，The hardware designer has this micro programming abstraction now this way the designer can translate any desired operation to a sequence of micro instructions。

😊，All the designer needs to provide is three things。

 the sequence of micro instructions needed to implement the desired operation。😡。

The ability for the control logic to correct the sequence between micro instructionsions that's micro sequencing。

 and also any additional data path elements and control signals needed。😡，If you already。

Have the data path and control signals you don't need anything so if your data path and control signals are powerful enough。

 you can implement new instructions， new micro instructions internally you don't need to tell anyone and that's what brings us to this thing that we have looked at earlier right remember we had the semantic gap picture you have high level language ISA with complex stuff。

 complex complex IA complex instructions， complex data types， complex address mode。😡。

These get translated into。Micro instructionsions in existing processor So existing processor actually operate this way a complicated I like X86 gets translated using this hardware translator micro sequencer that I kind of。

Went over quickly to actually go through translate every instruction to a sequence of micro instructions。

 and any instruction can be translated many micro instructions。

Let me cover this slide and then we're going to take a break basically there are other advantages to this。

😡，You basically can take an ISA and translate to microco and implement things in different ways。😡。

You can have a minimal data path to emulate the ISA and you can think of this as a user invisible ISA。

 like we've been kind of thinking of it， right？😊，This also enables easy accesstensibility of the IA。

 You can support a new instruction by changing the microco。 Someone creates a new instruction。

 You basically try to。Figure out how to include it by changing the microcode itself。😡。

You can support more complex instructions as a sequence of simple micro instructionsions。

 for example， string copy can be supported as a sequence of smaller instructions。😡。

Even though you don't have a native string copy operation。

 you can change the microcontroller to actually do this multidimenal array updates can be supported。

 it also enables update on machine behavior for example， if you have a buggy implementation。

 you have a bugging in your processor it gets discovered in the field smart security person some smart person discovered that there is a bug。

😡，You can basically fix that bug。😡，You basically say， okay， this particular instruction is buggy。

 I'm going to execute in a different way by changing the microcontroller by changing the micro program micro programminggramm this requires changing the microcode。

 of course， thiss called microcode updates， so you need to have a programmable microcode engine for this。

😡，Okay， this is where I'll stop， let's be。Back when the bell rings。

We're going to continue with pipelining and a lot of ideas， if you have questions， let me know。知道。

Is there anything good online， okay？Okay， so now I've kind of covered the micro program control relatively quickly。

 but this is really just for your benefit because I think it's a very nice and clean way of designing a system you have a clean microcode and you can update it。

😊，Even after the processor is in the field， right， you can patch the microco basically。😊。

So now you know what it means when， for example， a major company release a microco patch。

What they're doing is they're really updating the micro instructions。In that control store table。

 meaning they're updating how they press an instruction using these control signals and the reason they can do that is not everything is hardwired completely。

There is some layer of translation。Like this。That enables them。

 that gives them some flexibility to translate from the ISA to micro instructionsions and there's some programmability in this layer。

 essentially， right？😊，And what we've kind of done is when we actually were doing determining the control signals for every state in the finite state machine。

 we were really microprogramming the machine， we didn't call it microprogramming but it's really microprogramming the machine。

 you set the control signals and somebody does that and if there's a bug。

 they actually fix it and they release a microcodeote patch and you download it and your processor works better or more correctly or highperform also in some case。

😊，Okay。So essentially the ability to update or patch microcode in the field enables ability to add new instructions without changing the processor。

 which is very nice because of that interactiondirect that we discussed。

 ability to fix buggy hardware implementation， the ability to provide mitigation for security concerns。

 for example， etc， and there are many historical examples of this， for example。

 early IBM machines had microcodes stored in main memory， and they could update after a reboot。😊。

Similar things happened and they are very nice papers that talk about it。

 IBM calls this millic code and they actually describe how they do it in their Z series processor。😊。

These series processors are actually pretty heavy processors， they' really huge。

 they are millions of dollars and a lot of like big institutions buy them and use them for many。

 many years and they may need to update the microco many times over those many， many years。😊，Okay。

 interesting thing in some processors where actually you could update the micro while the processor is running。

This is very similar to a program right a regular program if you think about it。

 you program and you can change the program while the processor is running clearly right that's nothing new。

 but here updating the microco is really changing how the hardware behaves and you can actually do that also。

😡，So it was a more user micro program gamble machine。

 and there are actually interesting papers on that also。

And I already said that systems today use micro attachtaches to fix hardware bugs and issues。



![](img/833ea6c08e0c3e19afbe7578c4370f2c_3.png)

There's more， if you really want to learn about micro programminggramming。

 there's a longer lecture that talks about it， but I'm not going to cover it more here。😡。



![](img/833ea6c08e0c3e19afbe7578c4370f2c_5.png)

But I'm going to ask the question， can we do better basically you've designed some things and you've designed the multicycle MIPS processor and you've designed the multicycle MIPS finite machine。

 and we also said even though your book doesn't handle multicycle memory access。

 we can also handle multicycle memory access very easily。😊。

So we can handle a lot of really realistic things relatively easily with this multicycle machine。

 so if we're getting compared to single cycle machine。

 this is like heaven like you're really dealing with real things right now single cycle is kind of an exercise that you do but it's going to be useful actually in what I'm going to say soon which is pipeline okay basically can we do better what limitations do you see with the multicycle design I've already given you actually this so I'll go through this relatively quickly but basically one limitation is hardware cost of course。

😊，Hardwarere costs。Unfortunately， we're going to add more and more hardware costs to the machines later maybe in lecture 18 or so。

 we're going to look at paradigms where hardware cost will be reduced。😊。

But that will come at the expense of lower performance， so we'll have low performance。😡。

But limited concurrency is something we can fix by adding more hardware。So basically。

 if you have carefully followed what we have done。😊，We added hardware resources。

 they're less than a single cycle machine， but we're not using those hardware resources all the time。

 some hardware resources are ideal during different phases of the instruction processing cycle depending on which state you're in in that finite aid machine you're using only a small fraction of the resources。

 it could be a very small fraction actually。So for example， fetch logic。

 the logic that you added to the data path for fetching instructions is idle when instructions is being decoded or executed or calculating memory address。

 etcter。😡，Fch logic is used only when you're fetching instructions， right？😡。

Most of the data path is idle when MM me access is happening。

 you're just accessing memory waiting and everything else in the data path is idle right。

 even though those resources are there。😡，They're waiting for the memory access to finish so that they could be used。

Okay。So basically， people ask this question， can we use the idle hardware to improve insurance？

And the goal is to really get more concurrency。😡，Enable utilization of a bigger fraction of the machine。

Essentially， what is more concurrency right more concurrency is you do more things。😊。

In this at the same time， and this gives you higher throughput， higher instruction throughput。

 in other words， more work completed in one cycle。😡，Okay， I think I give you the idea over here。

 but essentially the idea of pipe planning is very simple when an instruction is using some resource in its processing phase。

 process other instructions on id resources that are not needed by that instruction。😊，For example。

 when instruction is being decoded， fetch the next instruction。😡，When instruction is being executed。

 decode the next instruction， when instruction is accessing data memory。

 execute the next instruction。😊，The instruction is writing its results into the register file。

 access data memory for the next instruction this way you can actually have many instructions in the machine at the same time right。

Does这三个。Even better， but essentially the idea is to potentially let's say six instructions right it depends on how many stages you break this down to。

😊，So it looks kind of like this when an instruction is writing its result and other instruction is accessing essentially doing ALU computation and other instructions accessing the register file and other instructions。

😊，Maybe fetching and also some other instructions updating data memory， which is not shown over here。

 So all these different colors are different instructions。But of course。

 we need to be a little bit more careful for reasons that we're going to study this lecture and in the next lecture and maybe even in the next lecture after that。

😊，Does it sound good？Does it sound like it will enable better performance？

It will right because you're as opposed to doing one thing at a time， only one red thing。

 you're doing many different things， colorful things over here， right？😊，Okay。

 so let's go into pipeline。Thiss actually an idea that's used in I'm going to show you a picture factories a lot right you pipeline the processing or the construction of a part。

 a car， for example， or part of a car and essentially the piece starts from somewhere and then somebody does something to it passes along to the next person and that person does something to it and makes it bigger。

 passes the next person， et cetera， et cetera， and you pipeline the construction of the car today robots do a lot of that so robots actually pipeline the construction of a car。

😊，So essentially， systematically， we're going to do something similar， pipeline。

 the execution of multiple instructions。😊，The analogy is assembly line crossing of instructions or in factories。

The idea is we're going to divide the instruction processing cycle into distinct stages of processing。

😊，Ensure there are enough hardware resources to process one instruction in each state for whatever we're doing in that state。

😡，And press a different instruction each stage， not the same instruction， different instruction。

 okay？😡，And instructions consecutive in program order are processed in consecutive stages， okay？

The benefit is this increases the instruction processinging throughput， we define， for example。

 CPI as part of the performance equation， if you remember the performance equation。

 execution time is equal to number of instructions， times average cycles per instruction。

 times clock cycle time。😡，How do you improve throughput， forget about number of instructions。

 we cannot do much about it in the micro architecture level， clock cycle time。

 that's one way of improving execution time， reducing execution time。

 but if you actually process more than one instruction per cycle。

 you're really reducing cycles experience per instruction right？😊，On average。

Because you're really overlapping multiple instructions at the same time right so you're really improving IPC。

 which is the immerse of CPI IPCs instructions per cycle， CPI is cycle per instruction。Okay。

 so clearly there's a downside and we'll start thinking about this and we're going to see a lot of the downsides。

 one downside is going to be more hardware， essentially we're going to add more hardware to enable this sort of processing。

😡，And then there will be other downsides， as you will see。Does that sound good？Yes， okay。

 I see some heads nodding Let me give you the benefits pictorially because a picture is worth  a thousand words。

 maybe in this case。😊，So this was multicycle。I'm assuming we do have four cycles per instruction。

 four ads， for example a operations， each ad takes four four states or four cycles fetch the execute right back and then you start the next ad fetch thecode execute right back and then you start next sta you can see that we serialize the execution of four different ads in this case when you do pipelining。

😊，This is what you do while you're fetch while you're decoding the first ad。

 you're fetching the next ad， while you're executing the first ad。

 you're fetch you're decoding the next one， you're fetching the third one while you're writing back the result of the first one you're executing the second one。

 decoding the third one， fetching the fourth one。So it's kind of beautiful like this。

Assuming the instructions are not dependent on each other， which is something we will discuss。

 but you can see that our throughput has increased， we get four cycles per four instructions。

In other words， we complete one instruction per cycle， right？And in the steady state。

 you can see that there are four instructions that are concurrently in the machine。

 the steady state means when the pipeline is full with instructions。This is a steady state picture。

 but basically the key takeaway is you're completing one instruction every cycle。😡，Whereas here。

 you're completing one instruction every four cycles。So that's the throughput improvement。

So it improves your throughput， it improves your execution time in this case。

 and you can calculate the execution time improvement here it's 16 cycles， here it's four， five， six。

 seven cycles， right？😊，Okay。😊，So it improves your instruction through it。

 it improves your execution time， it doesn't improve the latency of a single instruction。

 a single instruction still takes the same amount of time as you can see right。😡，Here。

 each instruction was taking four clock cycles， assuming clock cycles are the same in multicycle and pipeline。

 which may not be the best assumption， but we are going to assume that for now， they're close enough。

Each instruction still takes four cycles in the pipeline machine， right？😊。

So we didn't change the latency of the instruction。

 but we improve the throughput of the machine and the execution time of the entire program by overlapping the execution of different instructions。

 so this is actually a critical distinction between latency and throughput。

 your latency of an individual operation may not improve but your throughput of the overall thing that you're doing in your program may improve by overlapping latencies of different operations that you do。

So that's the power of overlapping latencies。😡，Okay， so the question is， of course。

 is life always is beautiful， this looks beautiful， this is perfect pipeing kind of because。😊。

Because we can do what I show you over here。This doesn't happen if the instructions are dependent on each other。

 for example， so we're going to look at when life becomes not as beautiful and we're going to try to solve those issues。

Makes sense。Okay， so another book， the Heness and Paterson book actually has another analogy that I like。

 which is the laundry analogy， which you may actually empathize with laundry is a pipeline process basically you have a bunch of loads and each load takes some time。

 you basically put them into a washer and then into a dryer and then you fold them and then you put into the cabinet assuming each step takes。

😊，I guess 30 minutes over here， you finish one load in two hours。

 right and then you start the next load， right？Multicycle machine looks kind of like that。

You wait until you finish the entire load until you use the washer again。

This kind of doesn't make sense if you want to save time， right？

Because you can you can start using the washer over here for the next load okay so you can read this song year old。

 but basically steps to do a load a laundry load in this case are sequentially dependent on each other。

 but there's no dependence between different laundry loads。😊。

Different steps do not require the same resources either。😡。

And washer and dryer are completely disjoin from each other。 Of course。

 you could have a washer and dryer that's put together。

 You can either do washing and drying and they are machines like that。

 And those machines are terrible for pipeing。And they're actually not good for latency also。

I have one， so I know。So it's good to a separate washer and separate dieter， frankly。Specialization。

There are multiple reasons actually， you cannot specialize a washer and dryer to be as good as a dryer specialized for just drying。

Very similar actually tradeoffs happen in architecture。😡，You design an ALU。

 you can much more easily design an adder that's specialized for addition as opposed to adder plus multiplier that's good at doing both。

 right。😡，Okay， anyway， I digress。 So basically， this is what。Every one of you do laundry， right。

 how every one of you do laundry if you have four loads， hopefully not。What you do is basically。

 if you do this， you finish one load every 120 minutes or two hours based on the parameters that I just described。

😡，え。But if you pipeline， which is what reasonable people would probably do after you finish the first load and start drying it。

 you also concurrently do the washing of the second load， right？😡。

So you do four loads of laundry in parallel in the steady state。

 which happens to be over here in this case。Yes。And this way you can start and finish one load every 30 minutes。

 so you increase your throughput by 4X， as you can see。

 even though the latency of every single load did not reduce。

 latency of the entire four loads actually reduced significantly。

Makes sense right it's the same example that I gave you instead of ads now we have laundry loads。

So okay， I've already said all of this， no additional resources in this particular case。

 you don't need additional resources， you may need slightly more amount of time to switch between one load to another。

 but that's the additional overhead that we're going to kind of see soon。😊，Okay， in practice。

That damn dryer takes always long， right， so who suffers from the dryer？

Which one's the longest dryer washer， nobody does laundry laundry here anymore robust to laundry for me it's a dryer dryer is always long。

 especially a high performance dryer consumes a lot of energy and a lot of time。😊。

So you do one loads every 150 minutes with that dryer right that dryer takes one hour as you can see。

😡，Now， how do you fix the sprout？This is essentially a problem that you have in real machines also。

 and addition takes and multiplication takes long， for example， right how do you deal with it？😡。

What this dryer has done to us is basically made our life worse for pipelining also， right？😡。

So as opposed to having one load every 30 minutes now I have finished one load every 60 minutes because I have a slow dryer and slow dryer is really my bottleneck if you think about it。

😡，I cannot really。I cannot really start the second drying process until this first dryer first load finishes in the dryer。

 so your dryer is really the bottleneck， your execution， right？😡，Okay。So how do you fix this problem。

 anybody？Yes， second dryer， okay？Okay， there are multiple fixes， second dryers won't fix。😊，Okay。

 I already said this the slowest step the dryer decides the throughput buy a second dryer， dryer。

 A dryer， B， alternate between them for consecutive loads。

 and this is something that you do in real life also。😊，And adder A， adder B， multiplier a。

 multiplier B。 So the same concept in life actually apply nicely to architecture as well。

 Now this is one solution， the other solutions make your dryer fast， right。😡。

So spend a lot of effort to have a fast der， that's another possible solution。 So either way。

 your cost increases。😡，Your cost essentially increased over here， right？😡，Okay。



![](img/833ea6c08e0c3e19afbe7578c4370f2c_7.png)

Okay， you basically restore the throughput using two dryers。😡，Okay this is just fun for you。

 these are automobile assembly lines and one of the main things this was tested on was a particular part。

 this is a Ford assembly line a long time ago， like early 20th century， maybe late yeah。

 before everybody here was born including myself。😊，Yeah。

 basically they had this component that supplied ignition energy to the engine before generators became common and they called this the magnetnio and was a pretty complex and innovative component at the time and they basically had to build that assembly line to assemble this component I'm not going to go through anything over here you can read it clearly but you can read the numbers over here on average a worker could assemble 35 of them in nine hour shift or roughly one every 15 minutes so it's a throughput and latency thing over here by moving to assembly lines like this which is essentially pipelines。

😊，They were able to reduce the assembly time from 15 minutes to five。

 and the required workforce decreased from 29 to 14。😊，So with robots。

 you can do even better probably， but I like magneto for another reason。

 does anybody know magneto for some other reason？😊，No， nobody follows X man， am I am I still too old？

In next man， there's a magneto and it's inspired by this magneto， actually。😊。

That particular device that's used in cars， early cars inspired something in X。Okay， anyway。

 this is more like a regular automobile assembly today。Okay。

 a real computer that had pipelining was IBM stretched。

 this actually in 1960s and you can see that computers were a little bit larger at that time。😊。

Good luck carrying this in your pocket but and also a little bit more expensive as you can see。

 but anyway， pipelining is real and it's been used for a while。 Okay。

 now let's talk about what it means to have an ideal pipeline and how a modern microproor pipeline is not ideal。

 essentially， our goal is to increase throughput with little increasing cost。😊。



![](img/833ea6c08e0c3e19afbe7578c4370f2c_9.png)

But we saw that if you already have a slow component， you need to increase cost。In this case。

 we want to not increase the hardware cost， also you don't want to increase latency。

 we're going to talk about that as well。😡，So ideally。

 you should be repeating the same operation many， many times right the same operation repeat on a large number of different inputs。

 for example， all laundry loads go through the same steps。😡，Ideally。

 you should your operations should be completely independent of each other。

 Theres no dependencies between different loads in your laundry， for example。

 right that should be nice and ideally you should be you should be able to uniformly partition them into so patients so you can divide processing into uniform latent sub patients that do not share resources again in the。

😡，In the laundry example， we saw that we had 30 minutes for each each step that's uniformly partitionable。

 but ideally we would like to make it even more partitionable。

 we would like to have a five minute dryer。😡，That' would be nice， right， okay？

So but doing laundry is not bad actually SM line is not bad， what about instruction processing site？

😡，We're going to talk about that， but let's talk about this ideal pipelineing element instruction processing cycle you have basically some combination logic this's a single cycle kind of processor right have you store the results in registers essentially this is your input registers your output register they can be the same but essentially you have some combination logic is to assume that it takes t seconds to process some instruction to put is one over T。

😊，We divided into two， ideally， we would like to put to be2 over t multiplied by two。😡。

And we divide into three， we would like3 over T。Now。

 this is not that realistic because we cannot divide work nicely this way。😡，What happens is。

When we actually。Look over here there's some amount of useful work over here in the TPse and there is also a register sequential logic delay。

😊，So when we actually try to divide T， even if we can divide t equally into k。😡。

Components or K stages。The register delay stays the same。

 You still need to latch things into a register at the end of a clock cycle。

 So your throughput is really dictated by。This equation over here。

T T gets divided by k that's also ideal if if you can exactly divide it。

 but you cannot get rid of this s this sequencing overhead or sequential logic delay is there so ideally if as k goes to infinity。

😡，This， let's say goes to almost zero， maybe one gate delay， whatever it is。

 so your throughput maximum is really dictated by the sequencing overhead of the registers。😡。

So always keep this in mind， register delay through it reduce throughput and that's your limiter why don't we pipeline things to very small amount of combination logic。

 this is the reason。Well， this is one reason， essentially you get dominated by the sequential logic transitioning overhead and most of your clock cycle gets wasted on essentially putting things into the register and taking things out of the register as opposed to doing useful work in computation of an instruction。

 right？😡，Okay， this picture still assumes perfect division of work between stages we're going to get back to that。

 you may not be able to perfectly divide t over k right because you have grand las of processing like accessing a register file。

 accessing a memory， doing something in the ALU， you may not be able to perfectly pipeline all of them。

😡，Okay， cost cost is also interesting basically if you look at a non pipeline version with some cost。

 you need G gates to implement things， you also need some register cost G plus R。😡，As you pipeline。

Perfect pipeing assumes you divide G by T。😡，And without you don't increase the compilation logic。

 we're going to see that that's not true， but even if that's true。😡，You need more registers。

 so you need to multiply the register cost by take at least linearly maybe it's not exactly。

 but registers essentially increase hardware costs。

 you need to add pipeline registers at the end of each pipeline stage， okay。😡，Okay。

 this still ignores the fact that you may need to actually replicate resources and also some registers。

 but register cost dominates if you pipeline too much， essentially。Hopefully， this makes sense。

 right， This is why people don't pipeline。Too much， let's say。If you could actually pipeline a lot。

 maybe we could have like 50 gigahertz proors by now。You could get that potentially。

 but you would increase frequency， your cycles per instruction would be much worse today if you do that。

Okay。Now let's go into a bit more detail。We're going do more pipelining and you've seen this many times that's why I'm going through this relatively quickly just to jog your memory we have an instruction processinging cycle and we're going to essentially pipeline it this was our single cycle micro architectureure that we developed in an earlier lecture not the multicycle so I'm going to actually start with a single cycle micro architecture as I said there is a good reason to teach single cycle micro architectureure one reason is to show you that this is a bad idea。

😊，It's always good to show bad ideas also the other reason is it's actually enables a good educational purpose to transition into pipeing because a lot of what you will see in the single cycle will be very similar in pipeing also。

😊，The logic control signals are actually going to be exactly the same。

But if you look at the pipelining over here， this is our throughput one over T in a single cycle。

 right？😊，This is one way of pipeline。 so if we basically add register somehow。

 we need to do some register， right， etc cetera。 but let's assume that somebody divided the stages like this。

And ignore these back edges for now those backages are always problematic in pipeing and you need to be very careful because there may another there's another instruction over here right there's another instruction over here。

 the different instructions are in different stages so you cannot just take something over here and put it into the program counter because it affects the other instruction that's over there right。

😊，Now you need to think about the hardware as catering for different instructions in different stages。

 you need to be very careful what you do when you actually cross different stages right if there's a line that crosses different stages。

 you should be very careful。Okay， anyway， basically instruction fetches 200 picooseconds Decode is 100。

 this is 200， 200， 100 okay right back so these five stage pipeline somebody designed that it's not a perfect design right now we're going to build a trade later drawn in some way is this the correct partitioning this always something that you can ask。

😊，Maybe that's not the correct partitioning right maybe you need a six stage pipeline maybe need a four stage pipeline why not choose different boundaries right this is always a problem in pipelineing we you're not going to talk much about this but keep this in mind when you're designing a pipeline processor you need to make some choices and there are no easy choices in a sense。

😡，But let's analyze this design earlier that we have in this picture。

So if you assume that these are the instructions that I have。

 different loads completely independently the band of each other。If you don't pipeline。

 and if you somehow design a processor that takes， let's say， single cycle。

You need 800 pickcoconds for this load， 800 picons for this load 800 picoseconds for this load okay because register files is only 100 pickcoseds to access when you pipeline every stage needs to take it needs to take the same amount of time because you move one instruction from one stage to the next stage in consecutive cycles you cannot have different stages taking different cycle times that breaks the clock cycle time in this case you see that this load takes actually 1000 cycles right 1000secons sorry 1000 picoseds to complete because it goes through five pipeline stages and each pipeline stages 200 piseconds。

😊，So even though instruction， this didn't need 200 piconds completely， it only needed 100 piseconds。

 you still need to ensure that you spend this full clock cycle in this pipeline stage。😊，Okay。

 and the next instruction is also similar。 So what happened here is。Our throughput increases。

 we have one instruction every 800 pickconds previously now we have one instruction every 200 pickconds。

😡，But our outputput is not perfect， meaning we pipeline with five stages。😡。

If it was perfect pipelining， we would expect a speed up of 5 x， right？

But we have a speed up of 4x in terms of throughput。😡，Well， because we wasted。

Some of the clock cycles right， basically half of the clock cycle is wasted in two stages whenever you're accessing is essentially the Decode and register file access stage over here。

😊，And the right backstage。Makes sense。 So basically， you don't perfectly partition work in general。

 There's no easy way to solve this problem also。 And as your pipeline stages。

Do more work are not balanced。 So this is called balancing the pipeline。

 If your pipeline stay are not perfectly balanced， meaning work is not perfectly partitioned across stages。

 you will not get the ideal speed up。So this is a first immediate hit at our pipeline， let's say。

We expect 5 x speed up， we get 4 x it's not that bad if you actually pipeline more。

 maybe you'll get a little bit more， but you will not get the idea。😡，Okay。

 we're going to see more and more hits to the pipeing and we're going to try to solve those。😊，Okay。

 so if you want to enable pipeline processing， you need to add pipeline registers right so this is a stripped down version of a single cycle processor that we have seen earlier。

😊，Mean you need to do what I show you at the bottom over here。😡。

So this is a pipeline version of the single cycle or the basic single cycle process。😡，Basically。

 you fetch the instruction， you increment the program counter。

 we keep this nice incrementing program counter over here as opposed to multicycle because this helps pipelining actually。

 and then you store the intermediate results in this instruction fetch instruction Decode pipeline register。

 we're going to call these pipeline registers。And then the decode and register file access does something and you store the intermediate results。

Over here and then the execute stage and the branch calculation stage does something and you store the intermediate results over here。

And then the memory access stage does something and you store the intermediate results over here。

 and then the right back stage does something and you store the result in the register file， etc。

And then there are also arcs that go this way， as you can see arrows that go this way。

 this is basically to change the program counter the branch finishes execution over here。

And the branch condition is calculated， target is calculated。

 they' are stored in this register in the next cycle if the branch is supposed to be taken。

You change the program counter to the target address， although those paths are not shown over here。

 but you need those paths to execute the instructions。

But the key takeaway over here is that if you want to pipeline the processing。

 you need to have pipeline registers to enable one instruction to be fetched。

 store its result while another instruction is being decoded to store its result at the end of the cycle。

 while another instruction is being executed。😡，And while another instruction is accessing memory while another instruction is writing back to the register file。

 makes sense。 So we added these registers。These registers also kind of existed in the multicycl in a different way Okay here you need to think differently because what we're doing is we're pushing new instruction into the pipeline in multicycle。

 we still have single instruction。😊，To process。Okay， so for example。

 these are some example registers， you have some instruction register， you have PC plus4 over here。

 you have registers that you've read， you have the immediate over here， you have the ALU result。

 you have one of the registers so whatever registers that you're going to need later you need to keep。

In in your pipeline register， for example， PC plus4， PC plus4 is needed here。 why。

 because we're going calculate the target address over the branch by adding a sign extended left you immediate to it。

 And this is the next PC of the branch。 As you can see。

 there needs to be also branch condition that says a store。 This is not showing the entire picture。

 But these are the things that you need。 You need data elements。

ThatThat are required to process the instruction later in the pipeline stages and need to propagate them across these pipeline registers。

So we will later see control also you need to do the same thing for control。

 so these legiss can become quite large。😡，Makes sense。Okay。So of course。

 you need to make sure no resources used by more than one stage。😡，While you're reading the registers。

 you should make sure nobody is updating the registers。😡。

That's going to be an important concern for us later on。诶。Okay。

 so basically each stage is kind of exclusively。Reerd for the instruction that's being processed in that stage。

Okay， so also all instructions classes must follow the same path and timing through the pipeline stages because of this design right so for example。

 you fetch the load。😡，At the end of the cycle， you store whatever you need to store PC+4 and the instruction register。

 et cetera， some control signals， maybe。And then load goes to the decode， and in the next cycle。

 you do the processinging over there， store the results into the next pipeline register。

 execute next pipeline， and memory next pipeline register。And right back。

 you write it back to the register file。Okay。So even something is happening here。

 even though a load actually is a good example， because load goes through all of the five pipeline stages。

 But if you're doing， for example， an ad， you don't really need the memory state， right。

 But a still needs to go through the memory state， right， because it's a pipeline。😊。

And this pipeline just。You cannot just bypass。Because if you bypass。

 there's a lot of complexity that's added， you could actually bypass in very advanced designs。

 but not in classical pipelining。😊，So basically， this has a performance impact。

 meaning an instruction goes through some pipeline stages， even though it doesn't need it。😡。

It basically consumes some cycles for instruction right essentially it's very different from the multicycle design if you think about it and the multi cyclee design instruction takes few as few states in the finite state machine as possible right that's the ideal design choice here every instruction takes the same number of stages in the pipeline。

😊，But it's not as bad a single cycle because single cycles insurmountable as we have discussed。Okay。

 so this is a pipeline operation example， you fetch the load and then you fetch the subject。

 for example， and then they flow through the pipeline kind of like this I'm showing you two instructions。

 right？😊，Now it's nice while Lord is doing memory access， subjecttract is doing execution。

 while Lord is writing back data to the register， subjecttract is going through the memory stage。

 doing nothing because subjecttract doesn't access memory in the memory stage。😡。

And load gets out of the pipeline after it's done and subtract goes to the right backstage and writes this result。

😡，So hopefully this makes sense right basically you fetch one instruction per cycle and every cycle an instruction moves from one stage to another stage so that other instructions keep coming into the pipeline。

😊，So I kind of shown you every clock cycle over here clock cycle one clock cycle2 clock cycle three clock cycle  four。

 five， six， these are very simple concepts， so hopefully this is simple we're going to get to the more complicated concepts like。

😊，Is life always this beautiful？Meaning。What if that subject was dependent on the load？Right。

 what if that subject needed the value produced by the load， then it cannot keep going。 Okay。

 we're gonna get to that。 but let me give you an operational view of the pipeline also。

 because this is kind of fun to think about。 So these are different time units， time  zero， time 1。

 time 2， time 3， time4 time 5， this instruction 0 doing fetch instruction fetch at time 1。

 there are some concurrency at time2，3 instructions are in the pipeline fetch thecode execute。

 As you can see at So basically。😊，You can fill the pipeline。

 this is called the steady state of the pipeline。And you keep basically filling new instructions into the pipeline as you can see instructions zero is the oldest instruction。

 it finishes after it does right back， instruction one is the second oldest， third oldest， etc ce。

 so you can see that we are assuming a five stage pipeline here that's divided similard to what I've shown you earlier and this is called a steady state。

 meaning this is where your pipeline is full。😊，All of the stages have an instruction yet。

 And once your pipeline is full， that's good， you you have the highest throughput at that time。

 This is what we would like ideally。 Your pipeline always full and you keep。

Being full just like in this picture， but life is not going to be this beautiful So this is an operation resource for also if you look at the different stages over here。

 fetch thecode execute memory right back and if you look at the time over here。

 this is how the instructions flow。😊，Again， this is just here for you to think about some of this is actually used for formalizing the pipeline and actually building the pipeline。

 et cetera， but I'm not going to go through that in this course。

 so you can see that instructions zero kind of flows at different timelines to different stages。😡。

And this is where your pipeline is full and all of these cycles。

 T4 through T10 are very useful for performance。Okay， let's talk about control points in a pipeline。

 This is where the single cycle is actually quite useful。

 You basically take the single cycle design and you have the identical set of control points。😊。

It has a single cycle data path， except you have some more registers。The pipeline registers。

So this is actually very similar to the single cycleproor we designed。

Acepted as these pipeline registers also， there's a five stage pipeline， fetch。

 decode and read registers， execute memory access right back。

 and you have four pipeline registers in between stages。

 but the control points are exactly the same as the single cycle data path and you can confirm this on your own if you would like。

So what do we do with control in a pipeline for a given instruction。

 we have same control signals as a cycle single cycle processor that we designed earlier。😡。

But we don't use all of those control signals at the same time because as a single cycle press you have a single cycle。

 you use all of those control signals they' are distributed to everywhere at the same time here control signals are required at different cycles。

 depending on the stage。😡，So you have the same control signals for a given instruction。

 but you use them at different cycles。😡，If the instruction is in the fetch stage。

 use some control signal， if the instruction is in the decocode stage。

 use some other control signals。😡，Makes sense。So how do you do this basically one thing one thing you could do is you could decode an instruction once using the same logic that we use as single cycle and buffer the signals until they are consumed。

😡，And this is what things kind of look like this is again an abstract view over here this is the fetch stage you know the instruction after the fetch state there is some decoding that happens in the decocode state and this is where you generate the control signals if you remember these control signals can be generated for all of the downstream stages these are the control signals that I'm going need in the execute stage these are the control signals that I'm going need in the memory stage and these are the control signals that I'm going to need in the right back stage so I generate all of those control signals as much as possible of course some control signals may not be easy to generate because they're dependent on processing as we discussed like the branch condition ignore those whatever you can generate based on the upcode you generate you put them into the pipeline range try and designate where they're needed maybe and then use them when they're needed so these control signals that are only needed in the execute stage are not needed in the memory stage you don't need to propagate them into this register that's between execute and memory stages。

😊，And these control signals that are needed only in the memory stage and not needed in the right back stage。

 you don't need to propagate them to the pipeline register between memory and right back stages okay。

 but the control signals that you generate are the same as a single cycle control signals。

 you just delay when you use those control signals because。Of the definition pipelining。

 right an instruction does something a part of the instructions processed at different cycles and different instructions are processed。

😊，On the same hardware at different places。Okay， this is not the only option。

 but you could also have another option， which is instead of decoding all of the control signals that you need ahead of time in the deco stage。

 carry part of the undecodeded instruction， let's say instruction word or field down the pipeline and decode locally。

 so basically distribute the decoding to happen locally across later stages clear there's a benefit to that that way you don't need to store all of this pipeline registers。

 you basically trade off sequential registers with combination logic。😊。

But we're going to assume kind of the first option for the rest of the discussion。

 but the second option is equally viable。Okay， which why kind of gave you the answer。

It depends basically。So here if you this is actually from yeah。

 this is actually the same single cycle processor divided into pipelines and the control signals delayed。

😊，As to when they really needed， for example， the execute stage needs ALU source。

 these multiplexors over here， they need to be controlled and these control signals are generated in the previous cycle。

😊，Stored in the pipeline register and used in the next cycle。😡。

These are the control signals that I need in the execute stage memory stage。

 some controls like branch， whether this's a branch is needed because we calculate the branch condition in the previous cycle like that's zero if the branch condition if if which what we're processinging is a branch and the branch condition is satisfied meaning it was zero then。

😡，We basically set PC source to one， which means that we get the PC from。

The target address that was computed earlier right so there's no magic。

 we've actually built all of this data path。 The data path is already there。

 We just delay the control to the appropriate time， right。Does that make sense？Okay。

 this may require some more thinking and going through the figures， but essentially。😊。

This is your single cycle processor divided into different stages。

 control signals delayed to the appropriate place， so let's take a look at memory also memorymorite signal for example。

 this memorite signal generated if the instructions if it instructions a store。😡。

And it's stored over here in the pipeline register， the store instruction moves。😡，That signal。

 that signal is moved to the next register， store instruction Cals address over here。

And then that address is used。To write some data value that's also latched by that store instruction the previous cycle into this register。

 and in the memory stage the store instruction uses the address that slash the data that sted。

 the memorymorite signal， memory is of course zero at that point。

 if you remember the signal and then basically writes the memory。Okay。

 so while store instruction is moving from fetch to decode to execute to memory stages。

 necessary control signals are also being propagated with the instruction。Okay。

But the data path is very similar to what people've designed。

 the data path does essentially the same things except it does in different cycles。😡，Okay。

 so this is one example over here this is for the register right signal okay essentially the register right signal needs to be propagated so that you write to the register in the right backstage as opposed to earlier stages Okay tomorrow we will pick it up over here we'll go until a bit more depth and then hopefully we'll finish by I'll see you tomorrow。

😊。

![](img/833ea6c08e0c3e19afbe7578c4370f2c_11.png)