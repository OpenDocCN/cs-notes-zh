# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p10 -10- L8_ Instruction Set Architectures II (Spring 2025).zh_en -BV1iV1XBWEJW_p10-

![](img/79c2fb889ccf94ebd88f322bea6f0112_0.png)

Is that the reason， Okay， there you go， maybe human error， but it turned off by itself。

 you told me that you were hearing me。😊，O。Okay， people did not miss anything if they didn't hear online。

 we're just getting started with some delay。Testing didn't work well。 now， can you hear me online。

 Hopefully people can raise their hands online and。We can do the testing with people online。Okay。

 nobody says anything， so hopefully they're hearing if they're not hearing they'd better be in class right。

 I'm just joking because we have other people who are attending that are that cannot come to class。😊。

Okay。Yeah。😊，嗯。So office hours， some reminders， extra credit assignment one， two。

 hopefully you want to get extra credits。Don't let LLMs do that work for you。

We can actually see the difference between people who write reviews using LLMs。

 this happens in the scientific community also you submit a paper。

Like original scientific work and some person reviews the paper。

 but it turns out that person didn't review the paper because you can tell an LLM reviewed the paper very likely。

 or this person was like an LLM。Both of which are not good in my opinion， in the end。

 because you get something that's not very interesting， not very deep。

 you're looking for feedback from an expert that is supposed to give you some really good quality feedback on a paper that you've written and what you get is。

😊，Some generalized comments that are not very interesting。

Okay that's my I'm going to start tarping onlums at this point。

 but we need better ways of developing these things let me finish it that way okay but we're not going to talk about those we're going to talk about ISs instructions at architectures and i'm going to go through some slides to remind you what we were talking about we covered the one Neman machine i'm going to go through this very quickly again and we started looking at instructions at architectures and these are your readings this was the one Neman model you remember the five components we went through all of them。

😊，And we said there are also two major hallmarks of Wo Neuman machines to program and sequential instruction processing。

 you should remember this all the time and we started going through3 LC3 which is a oneon Neuman machine One Neuman model and execution model and ISA instruction that architecture implements a version of that execution model obeying the one Neumman principles and this picture is a micro architectureitecture that implements that ISA and this is one implementation as I said yesterday and we were going through some of it。

And we started going through some instructions， we specifically covered and operate instruction add instruction。

 for example， and a load instruction today we're going to branch out。😊。

hich is kind of synergistic with control flow branching out right you change the control flow change the sequence of execution we're going to see more instructions today basically。

😊，But again， just to remind you， instructions go through a processing cycle。

 multiple phases of execution， fetch decocode de address， fetch our， execute and store result。

 and you go back。To the fetch to fetch the next instruction that's the sequential execution right you keep doing this over and over for every instruction in the program until you get to the end。

😊，And we discussed that we have a stored program computer meaning you don't distinguish between instructions and data。

 whether a value fetched from memory is interpreted as an instruction depends on when that value is fetched in the instruction processing cycle I said this yesterday but I didn't put it into words now it's put into words on the slide also so for example when you're fetching from memory and if you're in the fetch cycle of the finiteate machine you have seen。

 you interpret that memory value as an instruction。😡，At that point。

 whatever you fetch from memory is interpret as an instruction and put it as an instruction register。

 if you remember IR。😡，But if you're in the fetch opera stage in the finite state machine。

 in the instruction processing cycle， and you're doing a fetch from memory。

 then they interpret the memory value as data。So it could be exactly the same memory location。

The memory address you generate and put it into the memory address register could be exactly the same in the fetch state and the fetch Opera state。

 except how you interpret it depends on whether you're doing it at the fetch stage or the fetch Opera stage。

😊，Okay。And this was the last thing one of the last slides we covered。

 not the last one last one is going to be the next one。

 we were actually going into the control flow instructions that changed the sequence of execution so that you can do hopefully more meaningful things like decision making in your programs so this is an unconditional branch or jump you can see that this operates on base register so this is the encoding we went through someonecodings also yesterday this is the upcode and this is the base register the rest are set to zeros meaning that they don't they don't matter for the purpose of this instruction and the semantics of this instruction is change the program counter or update the program counter with the value that's stored and register to base register in this case。

😊，So this is called register addressing mode， we're going to see addressing modes later today。

 but this' is an example of a jump and there are other examples of jumps that we will not necessarily see but we may look at later in lectures。

😊，So how does this work if you want to implement this in micro architectureitecture。

 you need to provide the data path or path from the register file。

 take one register and place it into the program counter。

 and that's what we do basically you access the register file。

 get the source register one out and how do you know it source register one。

 you basically index one of the source registers with bits coming from the instruction register over here。

 and you know exactly which bits over here， these three bits。And。Once the data is out。

 you ensure that。In the execute stage of this instruction， the program counter is loaded。

 meaning you will write enable the program counters that the data flowing from source Reg one goes into the program counter。

Makes sense。And you should know essentially the logic that goes into all of this because we have actually developed the registers。

 wires， and you know how to have a register file is accessed also。

 you're going to see more and more of this later on。Does that上个。Okay， so that's a jump。Okay。

 so this is the slide that we stopped at actually I will maybe go through this relatively quickly but these are this is the state machine or part of the state machine that we looked at it's not exactly the same state machine because this is a more instructional version but essentially this is what you do during fetch you have state one every instruction goes through these three state states in the first state you load the memory address register with the program counter and for this to work the sequential logic should assert gate PC and LDMR if you remember the gate PC this is the gate PC over here this is the。

😊，You take the value in the program counter， this tri state buffer is enabled so that the value in the program counter gets loaded on the processor bus。

 it's flowing and you ensure that it goes to memory address register we went through this yesterday I'm going through this again just to remind you but to make sure this happens you need to also right enable the MAR in this state meaning LDMR signal is asserted okay so the key takeaway over here is you have a finite state machine that's controlling the execution of every instruction in the machine and every instruction in this case goes to a state 1。

23 and in state one you have some control signals asserted and this case the control signal is our gate PC and LDMR such that the program counter gets put into the memory address register。

And then you also update the program counter by incrementing the program counter by one， this is LC3。

 it's word addressable， every instruction is a single word， so you go to the next word。

 so there's something else that's asserted if we go back to that over here switching between these two are too much overhead。

 but essentially what we do over here is in the fetch state you basically take program counter incremented by one and you need to have data path elements to enable that and the PC Max this multiplexia should select this input。

And load PC should be asserted so that you actually increment the program counter by one。

And the reason why we incleement program counter by one is because。

We're kind of done with this instruction right done in the sense that we fetched it。

 we're going to write the instruction to the instruction register， we didn't fetch it completely yet。

 we're going to fetch it actually in state three， but we are done with the program counter。

 we actually took the program counter， put it into the memory address register and we are going to fetch from that address now we should move on to the next instruction。

😊，So that's a design choice that someone micro architecting the machine made。

 you could have incremented the program counter somewhere else， essentially。

 it didn't have to be done in this state necessarily。

As long as you did before you start the next instruction。

And you don't start the next instruction until you finish this particular instruction that's pointed to by the PC。

😡，Okay so I'll go through the remaining states a little bit more quickly。

 the next state is memory access state basically you wait until the memory returns the data and the MDR so you need to make sure that load MDR signal is asserted。

 but this is just instructive because it doesn't have an arrow over here that should be going。

 this is a conditional it is a state where you stay conditionally if the memory is not ready you keep staying in the state until the memory becomes ready。

 okay。😊，You will see the full picture in the next slide and then when the memory is ready。

 the data is in the MDR and you need to ensure in state3 the finite state machine make sure that the data and the MDR gets put into the instruction register let's go back to that over here so in this picture assume that the memory is finished and loaded the data into the MDR we need to make sure that data flows from MDR into the IR instruction register to be able to do that the control signal for this gate MDR should be asserted such that the tried state buffer is enabled。

 the data from MDR flows onto the wire and then after it flows onto the wire it's flowing here and we need to capture it in the instruction register such that and to be able to do that we need to write enable the instruction register so LDIR signal is also asserted okay。

So it's very simple basically， of course， as a micro architect we'll need to design this finiteate machine。

 but here someone designed the finiteate machine and gave it to us。😊，Okay。

 this next state is decocode in this decocode state， basically what happens is the。😊。

The finite state machine checks the upcode which is the top four bits in the LC3 ISA top four bits in the IR instruction register and based on that it decides which next state to jump to and this next state the term is based on the up code for example。

 if it's an ad instruction if it's an a up code you go and follow the sequence of these states if it's a load register up code you go and follow these states if it's jump like what we have seen。

 you go and follow these states。😡，So in case of jump， you go to a state where。

In that particular state， let's say the register。Id that we have seen earlier gets loaded into the program count。

 which is essentially what we have shown in the previous slide this is state 63 in state 63 you ensure that the control signals are such that PC is loaded again and you actually access the register file using SR1 which is coming from the instruction register over here。

😡，Okay， so hopefully this is clear if not you can study it a little bit more。

 there's no magic involved， this is all based on everything that we have learned in the digital design part of the course and now a little bit micro architecture part of the course it's a finite I take machine。

😊，And the full state diagram is here， essentially this is actually the real diagram。

 the previous one wass kind of like a toy diagram to illustrate the decocode phase。

 you don't really need this particular state actually you can jump directly into a state where you update the PC with register as I will show you right now so these are the three fetch states this is the decode phase and then if this is a jump if you can read the jump over here that's a jump you directly go to in this case state 12 and you load the program counter the base register and the next state is 18。

😊，Where you do the fetch for the next instruction and this is LC3B。

 LC3B is byte addressable so you implement the PC by two。

 so these are all things that you need to think about for different ISAs and instructions and architectures。

😊，Makes sense， but principles are the same， you can build a state machine like this for MIPS。

 you can build a state machine like this for X86 or this computer over here。

 except the states will be a lot in that particular computer。😡，Okay， okay。

 so that was the instruction cycle。 Now let's go into instructions set architectures all it。

 Any questions before that。😊，This all makes sense， hopefully。

Okay so we're going to go a little bit more mean we have been talking about instructions and architectures。

 but we're going to talk about a little bit more other things like data types and addressing modes and a little bit more on opcodes before that。

 and we have clearly studied ad and LDR in a little bit more detail even though you may not have realized that I actually gave examples from a and load register and these are actually using upcodes clear their upcodes over here they're using some addressing modes which we called out but we're going to see more addressing modes and they're also using some data types for example this ad is operating on two complement integers which you may have read about in your book I'm going to briefly mentioned that also that's the only data type in LC3。

😡，But they could be operating on floating point of data types also and we're going to have some fun with data types also okay so what is instruction set architecture essentially it's really the interface between what the software commands and what the hardware carries out so you saw a version of this in a previous lecture this is a simplified version you have it's in a program and you have a micro architecture instruction set architecture is really the interface between the software program and hardware micro architectureect。

😊，I'm going to loosen this later on a little bit but this is actually the hard definition of ISA it specifies many things as you will see it's actually more than that but at the basic level it specifies the memory organization which we have seen it specifies the address space addressability whether your word or byteta addressable for example and we've seen examples of this it specifies how many registers you have near the ALUs in LCC3 it's8 in MIPS is 32 and we've seen that also and then it specifies this set of instructions and the set of instructions are defined by multiple things upcodes。

 data types and addressing modes and also on top of this length and format and encoding of instructions and you've seen all of these in some way now let's talk a little bit more about them。

😊，Okay off codes so essentially there are a lot of trade offs that you can make when you actually design ISA how many instructions do I have。

 for example， do I give thousands of millions of instructions or do I have only a basic set。

 maybe 10， 12。This is actually an interesting tradeoff and we're going to cover the trade off a little bit。

 but it could be a large set of up codes or a small set of up codes clearly if you have very large set of up codes。

 this complicates the hardware design right the hardware needs to support a million different instructions。

😊，If you have only 10， the hardware needs to support only 10 right the hardware can be simpler if the number of op code is smaller that's this actually the thinking behind reduced instructions at computers so MIPS for example。

 the ISA that you're going to use in your labs and the ISA we following is really a reduced。😡。

Instructions that computer with fewer upcodes。Okay， for example。

 this is an upco that was there in Hewlett Peard's precision architecture。😊。

You can see that a times B plus C， it's multiplying accumulate。

whichch may not be a bad idea you put together two things right as opposed to just having a multiply and separately having an ad。

 they decided in addition to having those separate things also let's have them multiply an ad， right？

😡，And you could make a floating point multiplying at。

 which makes it nicer for machine learning work goes of today。ionLater in lectures。

 when we talk about CMD and GPUs， we'll also talk about multimedia extensions。

 these are instructions that operate on many data values at the same time concurrenly。

We're going to talk about them， you may have heard， for example， streaming SD extensions。

 advanced vector extensions and more recently advanced matrix extensions。

 these are up quotes that are actually operating on many data at the same time。

 which could be useful for matrix operations， for example。😊。

There could be very complicated op codes like VX ISA had an op code to save all information of one program prior to switching to another program。

 all of the registers and some of the special purpose registers。😊。

So you can imagine many things over here， sky is the limit in the end。

 and if you define it in the ISA， then somebody needs to implement it in hardware。😡。

So there are many trade offs involved Walt。😊，Hardware complexity versus software complexity some of these op codes make the software simpler in the sense that at the high level language you have some constructs right it could be nicely matrix multiplication so if you're doing matrix multiplication and if you have an up code that says matrix multiply that's a very nice fit right you don't need to translate it with a lot of effort if you have an op code that is if your op codes are not if your instructions are not that high level if they're just for example。

 add and shift then you need to translate all of those matrix multiplication operations to add and shifts right。

And that's a lot of work for someone， it could be the programmer， it could be the compiler。

 but someone needs to complicate their lives， so software complexity increases if your op codes are not matching the high level language。

There are also tradeoffs like if you have simple instructions， simple up codes， latency is shorter。

 if you have complex instructions be they may take a long time。

 we'll learn more about that later on so they' are interesting tradeoffs I'm going to get to this in a little bit more。

😊，So in LC3 and MIps， there are three types of op codes。

 and we have seen them actually operate data movement and control。 And we're going see some examples。

 This is all of the up codes in LC 3。 LC3 is a really simple educational machine。

 You can see the instructions over here。 We're not going to go through all of them。

 if you're interested in them。 You can read the book。

 but this is the up code basically top four bits is always the up code。

 So this is very easy to decode。😊，You basically look at top four bits and you know what you're going to do in the instruction。

I mean， there are also extended op codes as we will see a little bit。

 so there's some the bitit over here that kind of enables you to interpret。😡。

Some part of the instruction， this could have been part of the up code。

 but they decided not to put it as part of the up code。

 so there are some bits over here that also determine what the instruction should do in addition to the up code。

Okay， this is LC 3b and they change it a little bit。

 this is bioad addressable and instead of having a knot， they have an extraor。😡，And by now。

 we should probably figure out know how to implement not using an XOR。I'll let you think about it。

 I'm going to ask that question later again。So you don't need a not operation。😡。

If you have it not as unary right basically as a single up。

 if you want to take the bitwise knot of something。

 you could actually do it using a binary operator like ExorR。😊。

And you'll you can think about it and there are some ups that are not used in the future they may extend it for example。

 right you may actually say， oh okay a lot of programs may need this up so I'm going to in the future incarnation of the ISA I'm going to map that to something else。

😡，Okay so these are the MIPS instruction types it's actually a little bit more complicated there are three types of instructions of the MIPS r type I type and J type and we've seen all of those in yesterday's lecture。

 we've looked a lot into our type for example our type up code is zero。

 but the real up code for i type is really in the funked part this function。😊。

I type basically our type operations are register to register operations you have two register app one destination register and the up code and function together determine what you do to the register i type is source you have a source register and then you have an immediate value and you do an operation on those and the up code determines what that operation is and there's also J type this is jump essentially as you have seen you have an up code and then immediate using this immediate huge immediate value you decide where to jump for example。

Okay， so let's take a look at this art type instructions a little bit， this is from your book。

 you can see that0 is up is0 in these arttyping instructions and once you see that up is 0。

 the decoder needs to look at the bottom six bits which are funked。😊。

Essentially that defines the operation for example， if the fontc is zero， you do a shiftlet logical。

 if thec is this 26， you do a divide operation and you can see there are many operations over here there are ads there are subts。

 there is nor， there's X or。😊，So this is what they decided again。

 somebody decided that these should be the ups and those are the ISA designers when they design MIPS。

😡，Makes sense。 And you can see that these ups are not that complicated。

 right These are actually relatively simple。 You don't see a matrix multiply here。

And later incarnations of MIPS people may add them， but they're not here in this incarnation。

Okay so those are ups let's talk about data types now so N ISA supports one or several data types basically this is how we interpret the data the data you access in the register file and you want to do an add operation How do you interpret that data value is it a signed value is that unsigned value is it choose complement value。

😡，Is it a floating point value？Basically in LC3， people the designers made the decision that it's all tools complement integers right essentially what is a tools complement integer it's a system arithmetic system where the negative of a binary value x is defined to be a bit twice not of x plus1。

😊，And this makes the nice thing that if you actually add x and the negative x， you get a zero。😊。

In some other systems， you don't get that in some arimetic system So it's an arithmetic system again。

 we're not going into computer arimetic that much in this course。

 but there is a huge design space of how you do arithmetic using computers。

 And this is one very commonly used way of you doing arithmetic the negative of a binary value X is the bitwise not of x plus one。

😊，Okay， and if you're interested in this， you can read H& A chapter that。

 which talks about twos complement。😊，MyPS in addition supports other things。

 like twos complement integers， yes， but also unsed integers， meaning integers treated as unsined。😡。

It's not signed。 Everything is positive， or you can think everything is negative， right。

 That's another way of thinking。Or it a floating point arithmetic also。😡。

So there are tradeoffs involved over here again， hardware complexity or software complexity。

 if you actually have lots of data types， hardware becomes more complex。😡。

But software may be easier because in software you may have actually different types of things。

 for example you may actually have a matrix as a data type right none of these are supporting matrices but some of the advanced matrix extensions that are incorporated into general purpose machines today are supporting matrices。

😡，Because of the importance of machine learning。Okay， and again。

 there are trade offs in terms of latency if you， for example， have a supported data type。

 latency is fast， but if you don't have a supported data type， for example。

 again I as I discussed earlier， if you want to do a matrix multiplication。

But matrix is not supported as a data type。 What is support is only on signed integers。

 Let's say you have to convert every operation that you do。

 You have to convert a full matrix multiplication to many operations on un signed integers。Okay。

 now let me give you a high level perspective and then we're going to go into a little bit more detail。

 this course is about hardware software interface， right。

 we are going to talk a lot about that later on， especially when we go into other execution models。😊。

But this having different data types in the ISA is a very good example of the tradeoff that people make between hardware and software。

 in other words， programmer and micro architect programmer is who implements software。

 my architect is who glance hardware， if you have more data types。

 this is good for the programmer in general。😡，If you have fewer data types。

 this is good for the hardware designer in general。😡，So why， because if you have more data types。

 it enables better mapping of high level programming construct to the hardware。😡。

Hardware can directly operates on data types present in programming language， for example。

 this way you get small number of instructions and a smaller code size。

 your programs in assembly will be compact in machine code so they can fit small memories。

 for example， right？😡，So I've already given you examples from matrixes right。

 you can have matrix operations， a single in to say multiply matrix A and B。

 store the result in matrix C。😡，And of course there's a description of what these are exactly。

 but one instruction can only huge amounts of work on matrices that could be very large as opposed to you only have multiply add and load and store instructions like we are going to have in MIPS in LC3 and you convert the matrix operations into those smaller pieces of operations。

 then you have lots of instructions right。😡，As opposed to having a single instruction that does all the work。

 you may have millions of instructions that do a matrix multiplication。 Think about that。

 There are energy consequences of this also。😡，Another example could be graph operations if you're operating graphs on graphs。

 for example， you have you the graph traversal for example。

 and you may have graph traversal operations in the ISA as opposed to the individual load store a instructions。

😊，Again， you can have much better code size and also much better mapping of high level programming constructs to hardware the disadvantage of these complex data types or more data types is much more work for the micro architectite。

😊，Now， the hardware designer， micro architecttech needs to implement the data types and the instructions that operate on the data types。

😡，So once you have data types， you also need to add instructions that operate on the data types。

 right？😡，Matx at， matrix multiply， matrix transport transports， all of those are operations， yes。😡。

よくな？Certain operation。好个。And make it fast。I mean， you can make all of these fast right。

 you can make a single ad fast， a move fast， but yes， you can them matrix multiply fast also。😊。

So if you have an instruction， then the hardware designer can customize it。😡，Yes。

 exactly so that's another benefit of more data types certainly。

 but it's still more work for the micro architect， that's the disadvantage。😡。

It enables better mapping and you can customize it， you can reduce the latency， but it's more work。😡。

Makes sense。Okay。So another way of looking at it is a semantic level right if you think about data types。

 they're really tightly coupled to the semantic level or complexity of the instruction。

 I'm going to introduce a concept of semantic G， which is a good way of thinking about instructions that architecture design。

😊，Essentially， the semantic gap means how close are your instructions and data types to the high level language。

 pick your favorite high level language， Java， Python， C C is still high level。

 even though it's relatively low level。😊，Rust。If you're closer to the constructs in that high level language。

 then you have a low semantic gap。😡，So if you have complex instructions and complex data types。

 you have a small semantic gap， if you have simple instructions and simple data types。

 you have a large one。😡，So let me give you a few more examples， for example。

 you can have an instruction that inserts into a Aubly linked list this makes your life easier right a hash mapap instruction right an instruction operates on hash maps or instructions that operate on key value stores。

😡，Vax I I say actually had some of these， you actually had a high low semantic gaps。

 small semantic gap， you had instructions that operate on WE linked list。

 you had instructions that operates on multiple multidimensional arrays today we have matrix operations which are similar to what we had a long time ago with V for example。

 and they cater to these heavily used workloads that work on matrix operations right？😊。

Simple instructions we've already seen right basically you have primitive operations load store。

 multiply addd nor。😡，And essentially early risk machines。

 reduced instruction set machines had only integer data type， for example。

 later they figured out this is not good enough， so we're going to add more data types。😡。

So if you're too simple。You quickly figure out that this is not enough because there's a huge software world out there and you didn't really support the software nicely。

 your semantic gap is too far from the high levell language as a result you figure out and you keep adding to the ISA。

😡，If you're too close to the software， then your operations may be at some point not so useful。

 especially if the software evolves and start using something else right so your ISA also may get outdated。

😡，So it's good to think about the syllabates。Okay， so let me illustrate this a bit pictorially。

 essentially we're talking about how cool the instructions and data types are to high level language。

 you have a high level language pick your favorite one again。😊。

And then A have control signals at the low level， in the end。

 your goal is to map the high level language to the control signals， of course。

 over many clock cycles， right？😡，If you set your instructions at architecture close to the high level language。

😡，You have a small semantic gap， right you're far away from the control signals。

 a matrix multiply is much farther away from a control signals than a knot or end on ore operation。

 right？😡，If you have an instructions at architecture that's with simple instructions and simple data types or few data types。

 you're closer to the control signals。😊，So you have a large semantic app now you see the complexity now right now this mapping is hopefully easier for the software hardware for the hardware designer again hardware designer as your fellow student said can optimize things they can still make whatever instructions that are defined over here as fast as possible but they still need to do the work to do that if you're here then the hardware designer's job is easier because your closer to hardware now the software designer's job is hardware perhaps right because they need to get high performance using very simple operations。

😊，Okay。So let me wrap it up。 We're gonna you see the similar pictures with addressing modes also。

 So we're going to addressing modes。 But usually people talk about complex instructions and simple instructions。

 right， Com data types and simple data types。A good definition of complex instruction is an instruction that does a lot of work。

Many operations， basically。And we've talked about some of these right。You could， for example。

 have an instruction that copies one string to another。

 or you could do that operation using loads and stores only。😡，You could do fast Four year transform。

 for example， simple instructions and instruction does little work。

 but it's a primitive using which complex operation can be built。😊，Add exor multiply。

So the advantage of complex instruction and data types is you have much densesr encoding。

 your programs are much smaller。😡，You have smaller code size。

 which means that you don't need a lot of memory， hopefully at least for the code。

 you don't need to fetch that program far away from memory and storage into your own chip caches as we will discuss later on and because everything is smaller you keep things on chip so we're to go and talk about caches。

 this is good for caching for example as we will see later on。😡，Also， you have a simply compiler。😡。

Not only talk to my small instructions as much， and maybe you have a simpler。

A person who is writing programs， right， because you can map the high level language to the ISA more easily。

But of course， this comes with disadvantages as well， you get larger chunks of work。And as a result。

 the compiler has less opportunity to optimize with complex instructions。

But if you also provide the fine grained instructions like not Xor， multiply， et cetera。

 maybe the compiler can choose the best of both worlds now the compile is not as simple anymore though。

Okay， but and clearly you get more complex hardware because you need to translate from a high level to control signals and the optimization needs to be done by hardware。

Okay， so this is a summary， essentially。Does this make sense？I didn't go into like how to optimize。

 et cetera， because that's the subject of later some of the later lectures。

 but you can also take a compilerss course if you're interested， yes。😊。

Isn't I heaps this about just wasn' listed that basically is。If you have multiple really complex in。

That like through would still be。You won't use them all the time。

 whereas if you have fewer instructions， they will they will have a huge so you can。I mean。

 not necessarily you can do very similar optimizations for large instructions also right？

That's performance optimization。 That's， that's the reason why I didn't get into performance optimization here。

 You can optimize the performance of a chip。Whether or not you're having complex instructions or simpler instructions。

If you have lots of complex instructions， yes， you need more area， perhaps to support them。

 but as we will see， you can change the trade offs also。

So we will see some ways of changing the trade offs。You。Depends。

 depends on the workload you're executing。Yes， certainly primitive instructions。

 you can map everything to them， right？😡，But yes， if you are more specialized instructions。

 clearly they are going to be used fewer times， I agree。

But depends on the workloads you're targeting also right。

 clearly people are adding these complex instructions today because some of the workloads are so important。

😡，That you't and you can optimize those operations because there are benefits to it。呃。So in the end。

 when you're actually doing the performance optimization。

 you need to think about what workload you're optimizing for and you need to optimize for the common case。

Okay。O。Okay let me give you an example this's a fun example that I use this is a data type binary know coded decimal do people know what this data type is it's not covered in your books I think it is supported by the X86 ISA it is covered in your books。

 maybe maybe not okay basically you encode each decimal digit with a fixed number of bits。😊。

So this is how I would represent time。10，37，49。YeahAnd by now， you should be able to read this。

 right？I hope。This is 10， right， essentially to represent the first digit， you need two things。

And this is the lowest least significant bit。To represent the second one， you need four bits。

Think about why。Because there are 10 different values this can take， right。

And four it gives you 16 so you encode this with a binary four four bit binary value， this is 37。

 one2 over here， so you need three bits over here and seven， one，2，47 now hopefully you got the idea。

And this is 49， you need three bits again here， one，2， four， and not4 and quote nine。

 you have8 plus one。Now， if your brain was wired to process this data type。

 you wouldn't have to go through this exercise， you would just look at this and say this is 103749。

But your brain is better wired either by nature or nurture to read that， right？So essentially。

 maybe our computers are not using this data type naly。It is a data type， though。People use it。

Which clock do you prefer？H。😊，Now， if you're always using from your birth， this one。

 maybe you would prefer that one。This is a good to think about。

 don't say I prefer the left one because I'm a human。😊。

Maybe some other humans would prefer that one if they were using that one。From birth。

 and they never saw that one。Okay， good to think about。Okay， that's data types。

 And I think that's a great example of a data types。 Okay， addressing modes。

 This will make things a little bit more complicated。Essential。

 addressing mode is a mechanism for specifying where an all brand is located。

 We discussed this already in LC3， there are actually more addressing modes than in MIps。

 LC3 makes a different trade offs in this case。 is's more complex。😊。

There's an immediate or little mode， the upper end is in some bits of the instruction。

 and you've seen this。😊，We're going to see more of this。

There's a register mode that we've been seeing， the operaend is in one of the general purpose registers。

And there are three memory addressing modes， which we're going to see。 We haven't seen some of these。

 We saw a base plus offset。 We saw PC relative actually， We didn't see indirect。

 which is an interesting mode， but we were going to see that。😊，你皮。😡。

Actually has pseudodirect addressing， but doesn't have indirect addressing。

 It has based plus offset Also， it is immediate as well。

 So there are quite a few of these addressing modes， but it doesn't have indirect， for example。

Okay why do we have different addressing mode again the same tradeoff I'll go through this relatively quickly This is another example If you have more addressing mode。

 you can map the highlevel programming construct to hardware better because some accesses are better expressed with a different mode you get reduced number of instructions and code size。

 for example if you're indexing arrays， especially multidimensional arrays。

 you may have an addressing modes that makes it easier you can have indirect addressing modes that make pointer based accesses easier。

 you can have an addressing mode for example， if you have matrix operations again。

 if you want to access one element in the matrix you can specify XY coordinates。😊。

And if your matrix is multidimensal， for example， X Y， ZTP coordinates。

 if you can think multidimensionally， of course， that make things easier right。

 and if your matrix is sparse， meaning you have a huge matrix， but most of the values are zeros。

 maybe you have a different addressing mode and code where those zeros are and who your hardware can natively support those addressing modes。

😡，Okay， so clearly you can imagine many things and you will dedicate hardware for these so。😊。

That needs to be there。 is disadvantage again， if you have actually more of these addressing modes。

 there's more work for the micro architect and also maybe more options for the compiler to decide what to use。

 So here a compiler actually may become a little more complicated as well if you have too many options。

😊，Okay， so this is a semantic app， I will not talk about this again。

 but you can essentially what I've done over here is to add addressing modules。😊。

So your semantic gap depends on。What are your instructions。

 what are your data types and what are your addressing modes？😡，Okay。

 there are many other tradeoffs in ISA design， which we're not going to talk about right now。

 at least I'm going to talk about instruction types and addressing mode types。😡。

So let's jump into operate instructions a little bit more so in I see theory there are three operating instructions not we discussed it's a unary operation one source opera it executes bit twice not there's add and end there are binary operations to source opera and we said that the data type is too complement。

😡，And end is bit twice actually， SR1 and SR2 in MIPS there are many more。

 there are many art type instructions that I showed you earlier。😊。

I don't want to talk about everything， of course， their are i type instructions。

 meaning there are versions of this with one immediate print and one regstrar print。

And there's F type operations， which are floating point operationss。And again。

 I'm going through this relatively quickly because we've seen examples of this and these are not difficult concepts。

 but let's take a look at one example， this is not in LC3。😊。

You basically take the not of R 5 store the value in not3。 And again。

 we've gone through this exercise， a similar exercise。

 You can figure this out easily by looking at a manual L C3 manual， which is your book。

And not as an easy operation， you take the value in the source register， bring it to the ALU。

 ALU performs a bit twice not， and you get that from the finite state machine。

 meaning the decoded instruction， instruction registers decoded version specify that this a not and generates a control signal saying ALU should perform a bit twice not。

😡，And you get the bit wise not of the source register into the destination register。

 So this is all done in my architecture using control signals。So there's no knots in MIps。

 how is it implemented？😡，Okay， maybe I should not， yes。have one put the source out。Yes， exactly。

 XO with one， that's one way of implementing it。Another way of implementing it is using N。

 and you can think about that also。That's a good basically you you could do multiple ways in MIPS actually so you don't need a knot in MIps that's the reason they don't have a knot in MIps and that's the reason they remove knot in LCC 3B also LCC3B replaces knot with an XO they don't have a no either。

 but again I think you answered both of the questions over here but you could do a similar thing with no。

😡，Okay。So operating instruction， we're already familiar with add and end with register Mo and our type in MIPS。

😡，Now let's see how we can do things with immediate allprint， right？

We'll use subtraction as an example because there is some instructive value to subtraction。

 especially with two complement values。😊，Let's take a look at how subtractions implemented in LCCP and MIPS。

So recall， we have seen this already， this is register to register。😡。

Operation and if the op code is add， this is N Lc3， if the op code is 0，0，01。

 you add source Reg1 source Reg2 and store the result in destination register。 If it's end。

 you do a bit twice end between source register one and source Reg 2。 Okay。

 you've seen this before yesterday。Now let's take a look at how this is done with im。

Now we going to you make use of the spit over here， bit five。😡，🎼Bit 5 over here。

 It's called a steering bit。 Let me finish this。 and we'll take a break。

 So a bit 5 is a steering bit here， you see that these are all set to 0。

5 is the important one over here。 Now， if the up quote is。The same op as the register mod at0001。

 But if this bit is1， you interpret the lower five bits as an immediate。

As some literal value that's inside and quoted inside the instructions， you don't go to register。

So essentially what you do is you take source Reg one value in source Reg one。

 add to it because the up is that。😊，This immediate5 bits， sign extended。

 sign extended mean if you have a two complement value。 That's 5 bits。

 the top bits tells you whether it's negative or positive， right。 If it's 0， it's positive， it's one。

 if it's negative， signine extension means that take the top bit replicated for the remaining 11 bits。

Okay， that gives you the full 16 bit value， Okay， so that's the idea over here。😡。

If the upcode is end。😡，诶。whichhich is0101， you take the source register and you do a bit twice end with that and the sign extended immediate5 value from here。

Okay， I think we've already discussed。 So the key is basically the same up code is used。But。

This is an extension of the opcode this is also called a steering bit in some your book actually talks about it as a steering bit。

 it's also an it's really an extension of the opcode by just looking at this。😡。

You don't exactly know what to do。You also need to look at this， right？😡。

Does that make sense so when you're decoding an instruction this 1512 gives you some information。

 but not the full information about what you will need to do。😡，It's an endcoding issue。

 so let me finish this and then we'll take a break， essentially this is the end quoding。😊，You can do。

 you can write an assembly like this。 You can see that I can express a negative value because it's a。

It's a twoth complement。5ive bit value over here， you can easily express a negative2 over here。

 It looks like this。This is the negative value， immediate five。

 you can convince yourself that that's negative2 in two complement arithmetic， that is negative2。

And this is what will happen in the hardware essentially the source register is r4 in this case。

 so you get the value in r4， it goes into one input of the ALU。

 the other input of the ALU is selected。😊，From either the register file。Or the instruction register。

 which contains the bottom five bits that we want， and we have a sign extension logic that replicates the first bit。

 makes it a 6 bit value， and then have a multiplexer。And you。Let's。

's let's guess what this multiplex is controlled by。 It's bit5 from the instruction register。

Basically be5 says。If bit 5 is 0， take the value from the register file。If bit5 is one。

 take the value from this data path element， which is sign extended last five bits of the instruction register。

And this way you can implement a full ad。Depending on whether bit5 is1 or0。

 this still executes the right thing。 If bit5 is1， you get the sign extend immediate， if bit5 is0。

 you get the register， hopefully that makes sense。😡，Okay。

 so this is where it sits in the data path and this is where you see the bit five over here。Okay。

 I think this is a good place to stop。 Let's， I'm going to show you an example of how to do this in MIPS。

 And then we're going to look at the trade offs in terms of subjecttract and ad。

Let's be back when the bell rings， and we're going to continue with this。Oh。🎼，🎼，Yes。す。好。Yeah。是。Yeah。

对个是的。这个。Okay， we can hear me hopefully， right？い？Okay。Okay。

 so remember that we were talking about instructions。

 operate instructions with literals or immediate values encoded inside the instruction。

So one of the reasons or a major reason why this is provided in instructions at architectures is to make sure you don't waste a register So if you know that you're decrementing or incrementing for example。

 by a register by some amount， you can encode that information inside the instruction itself right that way you don't。

呃。Waste a general purpose register to store a plus one or minus one， right？

So it's good to think about the trade offs。 In fact， X6 ISA has an increment instruction。

 It's basically a very specialized instruction that does increment。😊。

So this is not an increment instruction， it's a more general purpose instruction because you have five bits of immediate that you can use。

😊，To do more than increment， you can add any five bit value and choose complement。

 but you save I register essentially that way。But， of course。

 if you need to add a known value that's larger than that it can be represented with 5 bits。

 and you need to store that in a register。 and then you do a register to register at。

 You cannot use an immediate。 So that's the trade off with literal immediate addressing modes。Okay。

 we've seen how this works。 and we have seen that we're complicating the data path so that we can actually execute this instruction。

 It's not that bad， but it's complicatedating data path still。 Now。

 let's take a look at a similar instruction mips。These are i type MIPS instructions。😊。

They actually have different up codes than our type。😡。

You essentially have two register print and immediate some operate and data moment instructions are like this。

 it looks like this essentially in MIPS instructions are longer as you know。

 up code is  six bits and you have an immediate that's 16 bits。😊，Okay。

 of course operation R as a source register， Rt could be the destination register in some instructions like add or load add immediate or load Word。

😊，It could be a source register and others。 So now it's it's not actually very clean， as you can see。

 right you're using the same encoding where the same。

Bits are t these five bits over here refer to either a source register or a destination register。

 you will see this in LC3 also， so you will need to have the data path elements that take those bits and route it to the right place in the register file so that you can index into the register file。

😡，Okay， the most important thing for our purposes right now because we're discussing literal values is this literal or immediate you can express a 16 bit immediate over here so this is an example a immediate and you can see that the up code is different from a it's not a anymore it's add I a immediate。

😊，These are the field values if you want to add five to source Reg 1 S1， which is represented 16。

Sorry。In this case， source register is really the 17 over here Rs and the destination register is 16。

Okay， so basically。You take Rs and add to it a sign extended immediate。

 which is very similar to what we have done for LC3 and store the result in RRT。

And this is the machine code that corresponds to all of this。

 this is what is stored in the memory as you know。Okay。

 now let's take a look at like why are we looking at this because one of the benefits of looking at。

This immediate subtraction right the question is do we want to have a subtractction in MIPS in your ISA in MIPS assembly you can express a subtraction in different ways so this is high level code now we have two operations one edition and one subtraction as you can see and you store the result in a this is one way of doing this in MIPS。

😊，Assuming these are in registers， you add the source register， zero source register。

 one put it into a template register， and then subtract that from S2 or subtract S2 from that and put the result into S3。

So this is subjecttract instruction that looks nice。In LC C 3， you don't have a subject instruction。

 So what you do is this。And this essentially accomplishes the same thing。

 except the registers are different， of course， but what you do is you add B and C which are stored in R0 and R1 implicitly。

 and then you take D which is stored in R3， you take the two complement of it， meaning you negate it。

😊，You take the knot of R3 and add one to it， that's the two complement negative representation。

 and then add that negative thing to the B plus C that you computed and stored into R2。😊，Okay。

 so this is the same code， implement the L B， yes。It thats going be the same as this month。

You could do that also， yes， that's possible。 This is one way the。People decide to do it over here。

Okay， so you can see now immediately a trade off right and this is actually the same tradeoff that I was talking about。

 do you want complex instructions or simple instructions subtract is a complex instruction compared to not an ad。

😊，Makes sense， right if your data types can be converted to a negative value using not an a。

 which almost all data types can be converted， then you can do whatever this is you can do everything with not an a you don't need a subtract operation The benefit of subtract is of course now you can see the denser encoding right。

I kind of told you that， but now you can see even with a simple operation like Subtract。

 which is more complex than not an ad。You have two instructions here as opposed to four instructions here。

 your encoding is better over here。Okay。Okay， performance is a different thing。

 you need to optimize the performance of both probably and I don't know which one would perform better depending on other constraints right maybe you can optimize subjecttract to be very fast or maybe you can optimize it's not an a to be as fast right。

😡，Okay， so you get more instructions in LCc3， but control logic is hopefully simpler because you don't have as many instructions。

 right？😊，Okay， so I'm the cycle got subtract immediate， so this is our high level code B minus3。

 let's play some more games in MIPS assembly you can express it this way subtract immediate because you have a subtract instruction S03 right。

😊，But it's really not necessary because you could actually do it this way also， right in MIPS。

You could do add immediate minus three， right？Okay in LCC3。

 essentially you could do the ad in LCC3 doesn't have an ad immediate。

 it basically uses the same mnemonic to specify ad versus ad immediate and you can distinguish them based on here。

😊，But those are all programming constructs also。Okay， any questions。

 so hopefully that give you an example of a little bit complex instruction versus simpler instructions now you can generalize this to much more complicated instructions。

😊，Okay， now let's talk about data moment instructions。

 we're going to deal with accessing memory and we're going to complicate things more because this is going to add more addressing modes because how do you address the location of the data that you want to get to？

😊，So in LC3， there are actually seven data moment instructionss。

 we're going to see essentially all of them， we're going to focus more on the loads。😊，呃。

And the format of load story instructions look like this basically you have an upcode。

 the top four bits， you have either destination register or source register after that。

 the next three bits and those are interpreted as destination register if you're loading。

 those are interpreted as a source register if you're storing because storing takes a source register stores into memory loading takes a memory location and stores into a destination register and then the rest are address generation bits and how those are interpreted depends on the upcode。

And there are four ways to interpret these bits。 and these are essentially the addressing modes that we have。

 We've seen some of these。 We're going to see more。 These are the names of the modes。

 PC relative indirect base plus offset immediate， and they all have either restrictions or downside。

😊，Or upside let's see in MIPS they're only base plus offset and immediate modes actually there's no inject mode and there's no PCL mode at least for data movement instructions there's a PC L mode for jump J type instructions that we have seen in the past and we're probably going to see soon again。

😊，Okay let's take a look at this PCL of addressing mode this is load and store and we have already seen an example of this I think。

 but actually we have not seen the example of this sorry this is the op code op code can be 0010 or0011 and。

😊，They distinguish the load versus store and if the up code is that the next three bits are either destination register or source register depending on whether you're doing a load or store and this is how you calculate the address this is actually the semantics the total semantics of the load the address calculation is done by taking the PC program counter which is the address of the instruction plus address of the next instruction next equation instruction because this is the IA designer specified this as the incremented PC take the incremented PC they had in mind somebody incrementing the PC while you're fetching the instruction so when you're about to execute the instruction you have the incremented PC at and you add to it。

The bottom nine bits sign extension， we already learned about sign extension。😡，Essentially， this way。

 you can go to a memory address。😊，That's。Relative to the instruction。

 instruction at this location in memory， you can go up 255， you can go down to 155。😊。

I'm going to give you the exact number soon right and then take the value in that memory location。

 put it into the destination Regstry。😊，So this is a limited addressing mode， as you can see。

 stored does essentially the same thing to calculate the address， but you go to the memory location。

 get the data value over there and then put the results into a source register。😊，Okay。

 we're going to see the limitations too so this is the we're going to look at the load。

 this is load and let's assume that the offset is 1 AF9 bits。

 and this is the machine code that you have。😊，This is how it's executed。 Let's take a look at this。😊。

Before we go into the downside of this， so you basically fetch the instruction and the instruction register。

 this is the incremented PC we're going to assume that that's the incremented PC for that instruction。

😊，And to execute this instruction， you first calculate the address， you take the increment PC。

We go through a specialized adder for address calculation。

This is which we're going to place in the larger machine later on。

 you'd sign extent the bottom nine bits of the instruction register。Add it to the incremented PC。

 you get the result， which is the address， you place it into the MAR memory address register。😊。

You access memory in a state， memory becomes ready at some point and then you move to the next state when the memory is ready the data is loaded。

 data at this address is loaded into the MDR and then when you go to the next state you take the data value in the MDR and place it into the destination register that's specified by these three bits in the instruction so there's some logic that that's not shown here but these three bits need to get connected to the index or address decoder of the register file and you've seen that address decoder when we built memory is earlier this is the address there are only eight addresses so you need three bits and you use these three bits to decide where to write and you need to write enable that location because you're actually writing in that state when you're moving data from MDR into the destination register again this is not magic we've kind of seen it before I'm going through this again and again so that hopefully it becomes like bread and butter for you。

Okay， so clearly there's a restriction to this， even though I mean， clearly you can do this。

 but the restriction is the memory address that you can address or specify using this sort of addressing mode is limited。

😊，It's very similar to the limitation that we have when we actually use an immediate value to add or subject right you basically have a small number of bits in that in the previous case。

 it was only five bits。😡，If you want to add a value that's larger than that you can express in five bits。

 you cannot do that here， the memory address is only 255 after this instruction。

 PC plus 2555 or it's maximum 256 locations before this instruction because the offset is nine。😊。

Okay， yes，那没白什。嗯。Well the memory addresses are un signed， the address is uns signedigned。

 but the offset is signed so that you can your relative value。

 so if your relative value was unsigned， you would only go either forward or backward。

 you cannot go backward and forward， right？Makes sense， okay。

But the address itself has no sign to it because it's really a linear array that grows from0 to2 to the n minus1。

😊，Where N is 16。呃， yeah。Okay。So basically the limitation is a PCL addressing mode cannot address far away from the instruction。

 it could be useful because the data may be located close to your program right you have your program and your data is before the program or after the program。

 but if your program is too big， you cannot put the data that close potentially。😡，Okay。

 that's why people develop other addressing modes and you could argue that this is not a great addressing mode and I agree that's why MIPS doesn't have this addressing mode。

 this an instructional addressing mode。😊，Okay indirect address mode this is actually an interesting one that doesn't exist in MIPS and it's a more complicated one and essentially it's called a load indirect and store indirect but it could be useful when you're doing pointer chasing meaning you have a pointer pointer is essentially stored in a memory location。

 but that memory location specifies an address that tells you to go to some other memory location right？

😊，That's a pointer， essentially。Okay， so what does this do this will become more clear when we do what we're going to do this instruction specifies so we can have load and store again the app code is like this if the app code is like this the next three bits are destination register for load source register for store and again we have a PC offset nine bits but we're going to interpret it differently because of the app code right now。

The difference between this instruction and the previous instruction that we saw is the upcode。

And this is how we're going to interpret it now this may look very similar to the previous one。

 but we have an additional memory over here as you can see memory memory。

 what does this mean we calculate the first address the same way we did the previous instruction。

 we take the incremented PC add to it a sign of sign extended nine bit offset that's coming from the instruction register。

😡，We go to that memory location， get the data in that memory location， and we say oh。

 this is an address， so I'm going to use that。😡，Again， Jack memory。

And then get the data from that location， so we first calculate one address。

 PC plus signexend offset， go to memory at that location， get the data value。

 that's our second address， we use that to index memory and get the data value。

 so you do two memory accesses， which means that the first address you calculate as the address of the pointer。

😡，To the location that you're going to access in memory afterwards。 and you could keep doing this。

 This is indexing using pointers。 You could actually do memory， memory， memory， memory。

 memory memory， and that would basically enable you to do many ins through different memory locations to get to what you want。

 potentially， and this could be very useful if you have linked data structures like graphs。

 for example， or linked lists or binary trees these are constructed using by linking different nodes through pointers in memory。

😊，Okay， then store is essentially the same thing you just store the data by doing essentially the same type of address calculation。

Okay so this is the instruction and this is an example PC offset over here。

 this is the machine encoting let's take a look at how this is done we're going to use exactly the same hardware that we designed for the previous instruction actually so we have the incremented PC over here we have the instruction register we have the sign extension logic for the last nine bits the first step is to calculate the first address。

😊，Which basically takes the incremented PC adds to it the sign extended nine bits coming from the instruction register。

That's your address， you place it into the MAR， that's the end of one state and then you go to the second state which is the memory access state。

 memory accesses itself using the value in the MAR the address in the MAR。

 and at some point memory becomes ready and places the result into MDR。😡，Once that's done。

 you take the actually， we're not using the same hardware as you can see， we're using。😊。

This connection which goes through the memory bus which goes through the bus actually cross your bus as we will see later on。

 but basically you take the value that is placed by memory into the memory data register。

 you don't put it into the destination register immediately， you put it。Into memory address register。

Makes sense， it happens to be 2110 in this particular example in your book。Okay。

 so that's the critical step。 This is the injection part。You calculate the address， accessed memory。

 memory provided some data， you treat it as an address and you put it into the MAR。

 and then you do another memory read。This memory read provides us the data that we're looking for according to the specification of the instruction and the data once the memory is ready。

 you get the data and the memory data register and you place the data into the register file as specified by the destination register bits and the instruction rates。

😊，Makes sense。Clearly， you need to modify the stick machine to enable this。

 so you do two memory reads to be able to do this。😡。

But now the benefit of this is the address of the offprint can be anywhere in the memory。😊。

And it's actually more powerful than this because you're actually using some pointer chasing if fuel will。

Okay。That's an interesting instruction， I think。It's not used in MIPS because it's too complex for MIPS。

 MIPS， the philosophy of the design of MIPS in the 1980s。

 actually late 1970s was let's make the instructions set as simple as possible。

So this is too complex for。And the reason they had that philosophy。

 as we will talk about when we go into micro architecture is if you make the machine as simple as possible。

 the hardware you can design as efficiently as possible。😊，Now the software job is much harder。

 of course， and for example， the original MiPS actually didn't even have a multiplying instruction。

It didn't have even have a load byte instruction。 they started with load word quickly。

 they figured out bad idea。 people use multiplies all the time。

So we cannot just have adss and shifts。They also figured out quickly word loading words is not enough bad idea people load bytes all the time so let's have a load byte so over time that ISA becomes becomes more complicated it's still not that complex as you will implement your lectures but this is the idea that's why they don't have this addressing mode but they do have this addressing mode which is equally capable let's say meaning I shouldn't say equally capable but it's expressive enough to address anywhere in memory okay base plus offset we've seen this essentially LDR and SDR and MIPS do this and you've already gone through LDR a lot in the last lecture so I'll go through this relatively quickly this is the en quoting as you can see and the way address is calculate is you access the base register which is specified by these three bits in the instruction register。

You take the value over there。 You add to it this sign extended six bit offset。

And that's your address now you access memory and get the value in that memory location and'm placed into the destination register。

Makes sense， right。 And store is essentially the opposite way。And we've seen this again。

 but just to show you pily we've not seen exactly this thing over here。

 assume that your base register is two destination register is one and offset is 1 d， this is LDR。

 this is how it executes you take。😊，You access the Bay register。

 which is register two in the register file。Actually， this is an LC3， sorry。

 but MIPS is very similar。So MIPS is going to be very similar but we're looking at LCC3 right now。

 you can get ISAs confused also as you can see because they are very similar to each other in some instructions。

 but you take the base register you go through the address calculation add that's a specialized adder and you add to it。

 sign extended six bits from the instruction and that is your address and that address gets stored into the memory address register and then you move to the next state in the state machine。

 that next state does the memory read。😊，And when the memory is ready。

 the data is placed into the MDR by the memory， and the last state in the execution of LDR is you take the data in the MDR and place into the destination register。

 which is one in this case。Make sense， okay。So again。

 the benefit of this is the address of the opera can be anywhere in memory but you don't do the injection。

 so if you do the LDI， you can do two of these accesses without going through a memory。😡。

If you want to actually do LDI using this， you need to do another LDR。Okay。

 so LDR actually saves one more instruction， as you can see， right if you think about it。

 if you want to do two memory accesses， if you want to access the memory。

 if you want to treat this thing that you loaded into destination as another address。

 you need to do another LDR with an offset of zero for that。😊，Okay。Okay。

 so let's take a look at this address calculation now we're actually making the address calculation more complicated by adding more addressing modes。

😊，So this is the global bus， this is the more complicated version like full version。

 this is the memory address register multiplexer so if we have a multiplexer over here so that we can put data into the MAR and we have the data path for that this is the adder that I was showing you earlier this is the address calculation adder。

 which is different from the adder in the ALU we need to have a specialized adder for this purpose。😊。

And these are the sign extension logic that we added。

 this is the bit nine bits coming from the instruction register sign extended for one of the addressing modes and six bits coming from the register for the other addressing mode。

And there are other addressing modes that actually we can use that we're not going to look at right now。

 but essentially as you keep adding addressing modes， you need to complicate the hardware。😊。

Which is what I said earlier right if you actually have more addressing modes。

 your hardware becomes more complex as a result your design becomes more complex， potentially slower。

 but you could also optimize it in different ways。😊，O。

So in MIPS we've also seen LW earlier you use essentially the same addressing mode base plus offset in MIPS it's also called base addressing mode。

 I like base plus offset better because there's an offset actually over there it's not just a base so this is the high level code this is the MIPS assembly and we are stream byte addressable so you know the reason for the8s because assuming this array is an array of words to get to the second element second word you need to multiply the address by four because each word is four bytes。

😊，So this is how you calculate the address， you take the value and register at zero， add to it eight。

 go to memory， and actually this is a storeboard， sorry。

 we just decide to use Stboard calculate the location address of that memory location and store register3 into that location。

😊，And these are the field values over here。So in this case， because MIPS has larger instructions。

 the offset or the immediate value can be much larger， it can be 16 over here。

 a defined extended to 32 bits， of course。Okay， now let's take a look at how these programs work in MIPS and L3。

 we're going to look at both stores and loads。These are the MIPS registers that we're going to allocate to again I will not go through this in detail and you can do it yourself。

 but what this does is the first load word loads the value into a temporary register a。😊。

And then you do an add a plus B， and then add I does the minus5。Now T2 stores what we have as C。

 and you do this store word from T2。To the memory location that's specified by a base register that stores the beginning address of this array。

Makes sense， Okay， that's hopefully simple。 we've gone through all of these instructions。

 store word may be slightly new， but it's the same thing as load， except it's the opposite way。

LC3 is essentially very similar， so this is the similarity of the ISAs。

 they have the same addressing modes in this particular case， same types of instructions。

 and once you have that it's just a difference of syntax right？😊。

It's kind of like having two different languages and you use the same type of instructions to implement a particular construct。

 right？So if your instructions are similar， your ISAs are also very similar in the end and there's not much trade off over here。

O。Let's take a look at the immediate addressing mode。

 this is going to be a little bit different because we're not going to access memory。😡。

It may be surprising because we're talking about data movement instructions。

 but this is really initialization of our register type of instructions。

 we're going to see the equivalent of this in MIPS。😊，And the idea is load effective address。😊。

It should have been called what MIps called it， in my opinion。

 it's really loading an immediate value into our register。

And you will see the name in immediate this load upper immediate load load yeah。

 you'll see that soon， but basically this is what the up looks like 1110 and there's a destination register and there's immediate over here specified by PC offset。

😊，Actually， listen sorry， it's a little bit different from MIPS because this is really using PC because you really want to load an address in this particular case。

😊，But maybe it's not as general purposes as what we will see in the MIPS。

So it's good to think about that so basically what you do in LEA in LCC3 is you take the incremented PC。

 you add to it a sign extended PC offset just like we did in a PC relative mode。😊。

As opposed to going to memory， you just load this into the destination register。😡。

Does that make sense， You basically load。If he see a relative address into a destination register without going through a membermo。

So what is the difference you don't access memoryEssential？

Instructions with the PC relative mode that we have seen some number of slides ago load from memory。

 but L A does not。 So that's the name。 that's why it's called the load effective address。

 If you do this now you can manipulate things based on the program counter。

 That's the benefit it provides。 But again， MiPS doesn't have this。

 Mips actually doesn't provide PC relative addressing for。I need a moment of instructions。

 but you can actually encode this in jump instructions as we will see again。Okay。😊，Okay。

 so this is what it does。Even though we cover it in data moment instruction it's really an odd instruction。

 it helps data moment because you're loading a PC relative address， you get the incremented PC。

 you add to it a sign extended  nine bit offset very similar to a PC relative address it's actually PC relative addressing but you don't access memory in the end you take that and place it into the destination register now what you have in the destination register is PC+ offset。

😊，Makes sense。Now you can manipulate something based on the current PC that you have。

 so it has its benefits。😡，Okay now we actually complicated this a little bit more What happens over here is you need to go through again the address box I will not go through this。

 but you will study this more and more as the lectures come essentially there's data path that's provided for this as well so it's really this one and。

😊，Yeah， there's a PC over here right you have the incremented PC that's already stored over here。

You select that one and add to it this sign extended 8 bit value。 and that's your address。

 And then you go through the MAR mark over here。 You need to set the control signals accordingly and you put the data value into the register file。

 Okay， so let's take a look at this。 It's a little bit different in MIPS， as I said。

 because it's not PC relative and it's。Arguably its because MIPS doesn't allow you to do this PC L addressing mode。

 this is a way of initializing the registers。So in MIPS， for example。

 you have an LUI instruction load up immediate that loads a 16 bit immediate into the upper half of a register and sets the lower half to0。

😡，Slightly different， right， You don't take， you don't do anything with the program count。

You just take the 16 bit immediate， put it into the upper half。

So it's used to assign 32 bit constants to average， for example。

 let let's say that we have a high level code that looks like this。

 we assign a 32 bit value to this variable MIPS assembly looks like this。😡，So load of per。

 what it does is it basically with this instruction， you specify 60， 5v， the top。

 the most significant 16 bits。😡，What this does is it sets the top 16 bits。Of S to this value。Okay。

 and the bottom 16 besides zeroed out。And then you can order that value with another immediate that's encoded in the instruction for F3C。

😡，Okay， this is one way of initializing values。Hopefully， it makes sense。

Without going through memory accesses， another way of initializing value is write some data to some memory location。

 load it， and then load into a register， but this way you don't have a memory access right you eliminate memory access。

Okay， it's a very similar addressing mode， it's not exactly the same addressing mode。

 it's not PC relative， as you can see。😊，But this is very useful for initialization。Okay。

 this is something that I will not go through actually I'd be interested in giving this to chat TPT and asking what this program does。

 these are actually a good way of reverse engineering。😊，But if someone gave you， for example。

 this entire program， you could reverse engineer it now based on what we have seen。

 you need a manual， meaning the LC3 manual in this case， but you know what to do。

 these are the instructions and you know the up codes and you can basically reverse engineer what each of these up codes do。

😡，how you basically take the patent Patel book， you start with the back cover， which has this。😡。

And then if you don't know exactly how the instructions operate。

 you need to flip a number of other pages to figure out how the instructions operate。And in the end。

 you go through the exercise， you figure out these are these instructions。

 and these are the immediates， and then you figure out the addressing modes and you figure out exactly what this program does and you simulate it。

 and in the end the final value of R3 is five。😊，People who do security actually do a lot of this reverse engineering。

Because they don't know what a program does， for example。

 they are given a bunch of bits binary zero than once。

 and they figure out what that program does and then they hack it。

For a good purpose or a very bad purpose。But this reverse engineering is actually fun。

 I don't know if you can try it with an yellow lemon to see if it actually is able to get you the correct value。

😊，It's good to check out， Julie， I'm curious。Maybe one of our TAs will check later on if the students。

 if you check it， let me know if it gets the right value。

But you should be able to do this right now based on what we have learned everything about ISAs today and yesterday with the right tools。

 meaning the right manual， you should be able to do this on your own and it's good to try this it's actually in your book the your book already does this for you but I would suggest doing it yourself so that you see how instructions operate。

😡，Okay， let's jump into jump instructions， control form instructions。

So we're going to treat control for instructions a little bit more。😊。

And hopefully we'll be done with control flow instructions by the end of this lecture。

These allow a program to execute out of sequence， and we've already discussed this。

 They could be unconditional jumps like what we discussed yesterday。 Today。

 we're going to talk about conditional branches。😡，Conditional branches are used to make decisions。

 for example， you have an if L statement， if x is greater than five， do this。😊，Or execute。

 go to this part of the code， otherwise go to this part of the code， right？So in LC3。

 LC3 and MIPS treat this differently。😡，And there are different I A is that to either what LC C 3 does and what MIPS does。

 For example， X 86 does。Similar to LC3， X 86 does also other stuff， but condition codes， for example。

 that LC3 uses are used in X 86。Let's take a look at what those are so jumps on the other end are used to implement loops and function calls we've already seen jump Jmp in LCC3 and J in MIPS we may see that again。

😡，But let's talk about conditional branches because enable those enable us to do something more sophisticated。

 based on a condition， go you jump to a particular part of the program or you go in sequence。😡。

That's the idea so how is the support in LC3 so in LC3 each time you write a general purpose register there are three single bit registers that are updated so while you're writing to the general purpose register there's also something else happening in the data path that says check the value that i'm writing。

😊，And set the condition codes。Each of these condition codes are either set， set to one or cleared。

 set to zero。😡，So if the value that I'm writing to destination register is negative。

You set the endbit and ZNP are cleared。 Now， that means the value is negative， clear， Li。

 it's not zero， It's not positive。😡，If the written value is 0， you set this ebit。😊。

If the written value is positive， use that the p。So clearly now you get the idea right。

 you have NZP and this specifies whether the last value that you wrote to a destination register was negative zero or positive。

😊，Clearly。Only one of those could be true， right？A value that you write is either negative or zero or positive。

 and you don't get any of those other combinations。

So none of those only one value should be one and exactly one value should be one。

So X86 and Sparker actually examples of ISA is that use condition called this is used in real life if you program x86 you will see it so let's take a look at branch if zero。

😊，So this is the。Assembly of this， this is the encoding， so the branch up code happens to be 0，0，00。

There are three bits in the instruction and quoting which tell you which condition code does this instruction test In this case。

 branch zero， branch if zero means that you should change the program counter to a target value only if the condition code is0。

😡，NZP are the small NZP are the instruction methods to identify the condition codes to be tested。

 and these are the registers that are set by the when you write to a destination register， large NZP。

 those are the values of the corresponding condition codes in other words。

PC offset is the usual PC offset that we' used to immediate or constant value  nine bits。😊。

And this is the semantics of the instruction if I'm testing for the n condition code and the n bitta set or if I'm testing for the P condition code and P is bit set。

 or if I'm testing the Z condition code and Z bitta set， meaning the value that was written was zero。

😡，Then I changed the program counter to inemented program counter plus sign extended PC offset。

 Otherwise， I don't do anything， meaning PC was incremented anyway， so I go to next chart。😡。

So I branch only if。I'm testing a condition code， and that condition code is set。

 That's a more human way of describing it。Brch 0 means I'm testing the condition called zero。

 if the last value written was0。😡，Then I'm going to take that branch。

 meaning I'm going to change the PC to PC plus signine extended offset。😡，Hopefully that makes sense。

 right？Okay， this may be a little bit mystical， but it's really you just test the condition code and if the value is negative。

 you take the branch， otherwise you go to the next instruction。😡，Okay。😊，All right。

 so let's take a look at how this is executed。 This is how it's implemented in hardware。

 now we have condition registers NzP， these are actually special purpose registers。

 Remember we talk about general purpose registers， that's the register file Now we have special purpose registers。

 each of them is one bit。😊，They're called condition codes NZP。 And I already describe how their set。

 The last value that you wrote to a destination register can be negative0 or positive。

 I'm not showing the logic that sets these condition codes here。

 There should be logic that sets the condition codes when you're writing it a destination register。

 there should be a comparator that compares that value to。😡，Zero， for example， actually， yeah。

 there should be a zero competitorator， unfortunately， and you know how to design this。

You could design it That's the hardest part Ne and positive are maybe easier but you need still a zero compared anyway。

 so basically how this instruction is executed you have the up code it's a branch Zbit is set so you're testing the Zbit so you have an end with the Zbit this yes means whether the branch is taken or not right whether you're going to change the PC to PC plus offset okay so there's actually a multiplex there's actually a write enable signal or a multiplexer depending on how you implement it。

😊，If this evals the yes。Then you take the incremented PC， Add it to it。 There's concurrently。

 there's an addition going on。 The incremented PC comes here to one input of the adder。

 This a special adder also that adds that that generates what the next PC should be。

 sign extended 9 B immediate over here。 And then you basically。😊。

Decide whether you write this into the program counter。 So if this yes is true。

 you write enable the program counter。Again， it depends on the implementation。

 That's why I don't want to go into the implementation exactly over here。

 but you will see an implementation later when I be discussing things。

You set the program counter to the target value only if。The condition called your testing。

Is true meaning one makes sense， right， and you can you can guess this logic Now there are interesting things you can play。

What if you're testing all of the condition codes， n is1， z is 1 p is1。😡。

This is called branchnch NZp。Then what do you do， yes。WellYes， exactly， basically。

 you always take the branch。Now， if this is the branch that you encoded。

 this an unconditional branch at this point。😊，Even though you're testing all the condition code。

 you're testing all the condition called， you should take the branch。😡。

Now there's another game you can play， what is NZP our old zero？

IfIf you're not testing any of these bits。😡，Yes， yeah it's a no op basically no operation meaning you always go to the next instruction this branch is doing nothing right it's a way of implementing a no operation and there is a reason we use no ops as we will see later in later lectures okay MIPS does it differently there's a branch equal now MIPS is more complicated here what it does is basically this is the branch up code source and there are two source registers our S andRT。

😊，And what this is the specification of the instruction and there's an offset if MIPS checks if the data value in Rs is equal to Rt。

😊，If that's the case， if these two data values are equal。

 then the program counters change the PC plus Sineex n offset that's left shifted because of byte addressability。

😡，Otherwise you don't take the branch， it's called branch if equal。

 essentially you test two registers and there are other variations of this branch if not equal branch less than or equal to zero branch greater than equal to zero etc ceter。

 there are other variations of this but branch equal is useful for implementing branches so let's take a look at how to implement this in MIPS。

😊，So the same instruction， this instruction is implemented with four instructions in LCC3。

That's the benefit of branch equal so you're checking two register if two register equal so a loop condition for example。

 if one register is the counter of the loop， how many times you iterate on the loop and the other register is how many times you should iterate to execute the loop once you get to the number of iterations you should iterate you should take the branch meaning get out of the loop right that's the benefit of BQ instruction if you want to implement this in L3 you don't have a BEQ you just have condition code so what you do is。

😡，You take one of the registers R1。Take truth complement of it。

And subtract it from the other register that you're comparing to R0 in this particular case。

 and if the result is zero， then you take the branch。

So this ad will set the condition code and if the result is0， that means r0 minus r1 is 0。

 meaning r0 and r1 and z are equal to each other， and then you take the branch。😊。

Now you see another trade off in the instructions set which is essentially a very similar trade off at BFC。

 the same functionality， exactly the same functionality requires four instructions in LC3 and only one instruction MIPS。

😊，But the control logic requires more complexity in MIPS right now because you need to take two registers and compare them and then branch based on the value。

 So this is the same trade off that we have seen earlier。Which is， where do you put the instructions。

 Are they more complex， Are they more simple， I didn't give you extremely complex instructions clearly。

 but even with very simple instructions like B EQ。

![](img/79c2fb889ccf94ebd88f322bea6f0112_2.png)

![](img/79c2fb889ccf94ebd88f322bea6f0112_3.png)

There is a level of complexity involved that's more complex than primitive instructions like not at and branch with condition codes。

😡，Okay， so we were able to cover actually， all of what I really wanted to cover。

 we covered a lot of things today and yesterday， there is a lot more to cover on ISA that we're not going to cover if you're really interested。

 there are a lot of tradeoffs over here that we're not going to go into。😊。



![](img/79c2fb889ccf94ebd88f322bea6f0112_5.png)

![](img/79c2fb889ccf94ebd88f322bea6f0112_6.png)

There have been many different ISAs over decades。So later。

 for example we're going to look at some GP type of ISas we're going to talk about VIW it's too early to talk about these but these are some names that I'm throwing at you all kinds of ISas are there and the fundamental differences are essentially in at least from an instruction set perspective there are other differences from a system level perspective that we may get into how instructions are specified and what they do how complex are the instructions data types and addressing modes for example Vex was a very complex ISA it had many instructions maybe more than x86 today X86 over time evolved over the course of 5060 years and it added many many instructions so it's pretty complex some of the IIs are much simpler actually。

Okay， I think this is a good place to stop， maybe let's see。

No I'm I'm right on time This is just a good place to stop to remind you the semantic gap。

 this is where the ISAs differ next week we're going to cover a little bit more on the ISAs and then we're going to start themic architecture。

 which is really the implementation of the ISA。😊，So have a good weekend， I'll see you all next week。

😊。

![](img/79c2fb889ccf94ebd88f322bea6f0112_8.png)