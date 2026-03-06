# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p23 P23 Compiler implementation： Branching (COP-3402 Fall 2024) -BV1v6vdBKEHB_p23-

All right， so welcome back to System softwareware。Today we're deep in the middle of writing our compiler for our intermediate representation。

 we went over arithmetic last time and just as a reminder Code Gen1 will be due today。

 that one hopefully will be pretty straightforward。

 you just spit out assembly code and a very formulae boilerplate assembly code。

And also today I'll be showing Co N3， which。Where you'll be extending your compiler to generate arithmetic and branching instructions。

 so we went over arithmetic last time we'll go over branching today。

Questions on generating arithmetic， questions on Intel's arithmetic instructions， how to use them。

 the ATMT syntax or the destinations on the right。Questions about which operators do use。

 questions about division， questions about special registers。Okay， okay I hope it's straightforward。

 it's because we're doing an intermediate representation and not like C。

 you don't have expressions that you have to you know figure out how to it's largely a one to one or one to a constant number of instructions。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_1.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_2.png)

So the languages are very similar。The tricky part is just going to be wrapping your head around this。

 the fact that you're generating code and not trying to evaluate code yeah。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_4.png)

えき？Me when you have Q at the end of。リ技術？

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_6.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_7.png)

はいてたおがわ。Why do you have to run CBQ？

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_9.png)

Is there saying？Why do you have to extend it？It's just the the way the。Division。呃。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_11.png)

Operators designed， it can basically take， I think， 128 bit。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_13.png)

Dvisor， I can't remember the words here，Ds， oh yeah， divisor。No dividend。

can take a 128 bit dividend that is the thing being divided。

And then it takes up to a 64 bit divisor so it's just the support you get for the division operation。

 I guess because it's division they can support。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_15.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_16.png)

If you just did 64 bit， then the result， for many cases， I guess would be a smaller number of bits。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_18.png)

When if for reason， they designed the divider to be able to do 128 bits over 64 bits。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_20.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_21.png)

The problem is is that the registers are 64 bits wide， so if you want to specify 128 bit register。

 well， you have to put the data into two separate registers。So the idea of instruction。

Assumes that you've populated the RAX and RDX register， RDX will be the high bits。

 RAX will be the low bits， it's assumed that you've already populated these registers with。

The dividend with the thing being divided。And so in order to help you not have to fill out RDX yourself。

 if you just have a 64 bit。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_23.png)

Dividend。This cQ operation will。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_25.png)

嗯。Sine extend， it'll extend the sign bit from the RAX register into the DX register。

And that's just because， know， if you remember two's complement or how negative numbers are represented。

 how are negative numbers represented in the machine or in many machines， yeah。Yeah。

 twos complement and what ends up happening is that the I always forget twos compliment。

 it always confuses me， I'm not a hardware guy， but the high bit will be one for negative numbers。

So if you took RDX and you just set it to all zeros and you had a negative number。Well。

 that 128 bit number is not going to represent the negative number you think。

 so if you just take that sign bit。Copy it to all the bits of RDX well then you have apparently a。

128 bit number that represents that。That's my understanding。呃。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_27.png)

So it describes it in here。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_29.png)

Does this sign extension？To the RDX so basically in our language， we're only going to have 64 bit。

Numbers as the dividend end of the divisor， we're going to put that number in RAX。

 but because the op takes RDX and RAX。Will。Set RDX correctly by running CDQ first。

And then running the idea the division instruction。呃。To get the result， that make sense？But who it。

 you asked it right？Requisite。Other questions on arithmetic。

 so this is just specifics of the Intel 64 bit architecture。And this also kind of， yeah， yeah。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_31.png)

What you mean having why do you need two instructions？



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_33.png)

Like， why does。it's just because the divisor， the thing doing the dividing can be any register。

 but the dividend is just fixed to be RAX and RDX。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_35.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_36.png)

So this is just the design of the machine。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_38.png)

And so this kind of illustrates a point about why you would want to have an intermediate representation。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_40.png)

It's。A lot more straightforward if you're writing a compiler from C。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_42.png)

To say exit of D6， it'd be a lot more straightforward if you could generate this simple IR generating something like this is a lot simpler to generate than having to generate the know the specifics of the Intel instruction set。

 know which registers it has。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_44.png)

And so the whole point of having this IR is to have a kind of simplified machine language。

 also other architectures may do things differently， they may not have a fixed。Register for it。

 they might not have division division you might have to do it in software for instance。

 so this kind of illustrates the benefit of having an intermediate representation of the compiler is that it just eases the compilation steps。

And at the extreme， there's even this actuallyly new compiler framework called MLIR。

which allows you to specify a whole hierarchy， a whole series of intermediate representations。

 each intermediate representation， having some optimization purpose or having some purpose before you get to a she code。

呃。All right， any other questions on arithmetic？🤧。All right， so let's talk about branching。

Fran is a little bit more complicated， but it's actually kind of similar to a arithmetic。

The way you handle opera， the way you do。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_46.png)

Use the instructions。Okay， so the goal。Is to take our IR。

 which specifies go tos like this where we have。A label。

And a go to statement which transfers flow of control to that label and translate it to Intel assembly。

 so it looks very similar， right？It'sVery similar for this kind of loop。

What does this program compute？What does this program do？Can you guess？Infinite loop， yeah。

 it' an infinite loop， but you know it's a legal program。In S IR and assembly。

 so this is the main goal we want to take branching operations that we have in simple IR。

And translate them to Intels。World where they call them jumps instead of branches， but same idea。

So any questions on the meaning of GoTos in simple IR？It's a jump， yeah。

 it changes which instruction you're executing。So if you learned about， I think。

 the Fech execute cycle in CDA， you learn about this， they call it the Fet Ex cycle。

So you have a stored program and kind of by default， the machine will get the next instruction。

 execute it， and then increment the instruction pointer。

 increment the address that is holding the code。And then execute the next instruction。

That will let you have a straight line sequence of arithtic operations， but you couldn't implement。

More sophisticated computations like algorithms。So the go to instruction。

 all it really does is it just changes what the next instruction is that's going to run。

 so hopefully you learned about this in CDA there is actually a special register called the instruction pointer in the Intel world or the program counter。

That holds the address of the next instruction to run。

And what branching does is it really just rewrites that pointer to be a different address。

For us in simple IR， you can think of each line as having a line number and go to changing which line you're going to execute in the IR。

Questions about branching and GoTos， who's ever used to go to in C。Oh， interesting。Oh oh。

 you mean you it when you implemented a virtual machine or something。You had to write go tos。

So I ever heard that go to considered evil， ever heard this？

I hope you could go to there are cases use it， there are some special cases， but yeah。Okay。All right。

 so that's the goal。So the first first thing to understand is what a label is so labels are。

Named locations in the program。So how is code stored in our von Neuumman architecture machines。

 where is the code stored？Right， memory in RAM， wheres data stored。Registers where else they stored？

Stack where's stack， where's the stack？In memory， yeah。

 so in the architectures we use code and data are in RAM。

 did you learn about this von Neummann versus Harvard architecture， we have separate code。

And separate data， so there's lots of ways to design where you put code。

 but in the architectures we're using here， RA stores both code and data。So in some sense。

 code is also data because code is a set of instructions。

 it doesn't live separately from the machine， it is physically represented in the machine。

And how are locations represented in the machine level？Locations in memory。Coords and rent， yeah。

 it's just a number。It's just a sequence， like if you have byte addressing。

 which the machines we're using do， you just have one number assigned for each byte in RAM。Yeah。

Bite alignment， you mean like 16 byte alignment。The point ofSo it depends on the machine the machine architecture。

 so some operations will only work with specific alignments。诶。I can't think off the top of my head。

Like modern architecture is like bite aligned， so you have less restriction of that。

It might be that like for instance the push instruction will have to be aligned 8 bytes or 16 bytes。

 may just be in the design of the architecture， I'm guessing it was easier to write the or build the machine by assuming certain kinds of alignment。

 but again I'm not a hardware designer， but that's my assumption。That's why that's the case。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_48.png)

So just as a quick quick refresher， we've got。We have Ram。At the top。Addresses， we have the stack。

Near the bottom we have the heap。But also somewhere in here in RAM。

 we have the code and other static data。And we start them at memory addresses from zero in modern systems。

 the lowest addresses are typically reserved for the Colel Library。And。

Addresses grow upwards to whatever the。Maximum size of Rammyov， actually it would be。

Because of virtual labor， you can just do have a fixed maximum size。But code and data。

 the point is that code and data and the stack and heAP are all stored in the same memory space。

 and in order to access a line of code， it's the same operation as accessing， say data and the stack。

It's just a memory address。So the way the whole fetch execute cycle works is it。

Looks at a specific register to find the current address in code。Gets that instruction。

 runs it through the processor to get the output。And then performs whatever state changes that the machine ask for。

 and then just increments。Increments the instruction pointer to the next line of code and so on。

So code is just data and memory and locations in code are just memory addresses。Questions on this。

 was honest。Yeah，4フイ。Is what。It depends on the architecture。

 I think Intel has variable length instructions， they're not always the same length。

So I don't think they're always four bytes。And that you can save space in generated kind。最し？

Here operate。Well， so the disk。At least in our current architectures my symbol for the disk。

The disc is separate from RAM， it's a separate storage medium。哎。

So the addresses in the storage world are like。Done differently。

 so it depends on the medium you have， so like I think disk storage devices they have like sectors and bikes within those sectors。

So certainly if you repartition， well， when you reppartition most。

At least most tools I know of will require you to reformat the disc。And then copy data back。

 so if you do that， then there's no guarantee that you'll have the same position on the medium。

That you originally have， so the address or address on the medium， which is not the RAM address。

Will be will be different， but there are schemes in the file system level that make it so even the kernel is oblivious to where exactly on the media on the disk data is stored。

よなるです。Yeah， for sure， so that the schemeche you use to actually store data on the disk。

Will definitely affect where stuff gets storage on disk they use like effectively linked lists to help you find all the pieces of your file and so those links are pointing to the physical addresses of the storage medium so it is similar to RA and in the sense that you have a numbering scheme to specify each byte or sector or block。

On a storage medium。Yeah， yeah， I don't know if that answers your question。But yeah。

 it's the same kind of scheme， but they have different design decisions for it。

 so this data is persistent and you're not probably not going to be accessing this like programs use variables。

And function calls to access different parts of RAM。But what do we use to access storage media？実さがある。

Right， those are for， so what do we use？So we learned about this a few weeks ago， how do we access。

 at least in UniX yeah？System calls， yeah， the system calls panel that for。

 so under the hood there are IO calls。at the machine level that are asking for data from the storage medium。

 and this again depends on which architectures you have Intel uses a， I think it's a port based。

 they have instructions for interacting with other controllers that will ask other chips that will ask for data。

But you don't have the kind of direct access to RA through a memory controller that you have。

There are memory called memory map schemes where。I don't know how many architectures use today where they'll actually map part of the memory to disk or to two other parts of IO。

 and then you can actually do loads and stores to IO， but in the kind of traditional architecture。

 storage media and other peripherals they're considered like IO。

 they're not considered part of the CPU memory hierarchy。つ年のま。Yeah， so in the UniX world。

 all of the peripheral IO is handled through files a bit more or less。

 and then RAM is kind of its own Now there is actually a RAM file。

In UniX because anything could be a file from， so there is like slash dev slash。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_50.png)

Men， I think it's called。Yeah， so there is a file that actually is backed by RA and if you have。

Route access， you can actually just start messing with RAM。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_52.png)

Because you can treat anything as a file， but there's no but the IO stuff is all kind of architecture dependent and in the Intel world you have to access a separate controller through a special set of like IO instructions stacks is that it's not done through RA。

 but there are systems that do that that have memory mapped IO。As well。But it's not going to ramp。

 it's just going to a special address。But anyway， yeah， interesting question。

 more for operating systems， but okay， any other questions on。This code is data， yeah。Yeah， well。

 I mean， the course they're all good online textbooks， you can read OS dev Wiki that I've given you。

 but yeah， it's more in the drem of operating system design how you，Manage this I。Okay。

 so labels are really just named。Locationations in memory。

But the question is what does this label actually correspond to at runtime。

 so if I compile this program？You know the Intel architecture does not allow you to put a string for where you want to branch to it's got to be a memory address。

 so what's the memory address going to be for this label。Was that。There yet。Aray x。No。

 so RAX is the programmer has control over RAX。Yeah。ねこでごめ。大一番だね。Yeah， no， that's exactly right。

 no not no was exactly right。 So what the asmbler does is it translates this name for you。😊。

Into a memory address。And the details this are a little bit complicated， but basically。

Whenever you jump to an address in the Intel world at least the jumps are relative。

 So this address will be an offset from the current instruction pointer。

 This is just how know the Intel instruction set works。 And let me show you the。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_54.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_55.png)

Documentation of this。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_57.png)

So it I't go into too much detail， but basically。You have， let's say。

 where does it describe relative trusts？So it says jump near relative displacement relative to the next instruction。

 So whatever the。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_59.png)

So let's say， well let's go back to my infinite loop example， if this is address 3。

And it says jump to loop， well， this is actually the same instruction。

 so it's just going to jump zero， it's just going to jump to itself。

But if this were 10 instructions earlier， it would say jump。10， negative 10。

So there's a columner function that creates this own stack frame。

 let jump and go to keeps it within the same stack frame。Well， so are this is in the code segment。

 this isn't in the stack frame。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_61.png)

So the stack frame is。A separate part of memory。From the code。

So the color has its own memory address that it's stored at。

And it's the instruction pointer that holds the current memory address， you know。

 RBP is what's meant to hold the current stack frame pointer。

So Ju will just basically take whatever the value of our IP is。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_63.png)

Add。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_65.png)

The offset that you've given in the jump instruction。And then use that to update。

The RP pointer so a jump。More or less is just RIP equal jump x is RIP equals RIP plus x。

Is basically what the jump instruction does it's just a relative offset Now this X is not the label X it could be any number as specified in this。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_67.png)

Architecture definition。This relative relative address。But it's a number。

 and it's the asmbler that will。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_69.png)

Help compute this for you。 The asmbler will figure out what this relative offset should be looking at the label you gave it。

Was there a question over here？Yeah。我说。Oh， RIP is the instruction pointer。

 it's an IP instruction pointer。It's managed by the processor。So when you tell the processor to run。

 it will automatically update the instruction pointer， pull the next truck。

 and this is the fetch execute。Lop that the processor has circuitry built in to do。It'll， you know。

 when you do a call， remember what a call was， what does a call do？

Remember the two steps that a call does in the until yeah？ワンテスチ。Yeah。

 and the wave branching were yeah exactly， so it pushes the current return address。

 which is the instruction pointer plus one， basically plus one instruction。And then it branches。

 and what does branching do， branching just overwrites RIP。That's all branching does。

Branching is just， let me set the instruction pointer to be a different address in memory。

Questions on that， does that make sense？So if I have a sequence。So this is my memory here。

 my code segment and memory。If I have a sequence of instructions。Like move， move。Compare， jump。

 et cetera。Then the architecture as circuitry to。Get whatever the instruction at the current instruction pointer is。

Execute it， which means discover when its output status this， do whatever state updates it ask for。

 so change a register， load or store for memory and then it。

Incrementence the instruction pointer to go to the next。Instruction。And so on。

 and then just continues。To update the instruction part to go to the next address。

 when it to use a jump， let's say this is jump loop。And in my assembly file。

 I said loop was some instruction down here， then RIP。The jump instruction will change RIP。

To go to wherever the label we specified in the assembly file。

So this is why a function definition in the assembly world is just a label， basically。

Because all a function call is at the assembly level is basically just branching。

 just changing the instruction pointer to another place in memory。

 to another part of your code and memory。Questions on this， questions on this。

This is I think this is in CDA， the Fech execute cycle where you have a stored program machine and the machine has circuitry to automatically execute the instructions。

 you know the very old school machines， the operators would have to kind of enter instructions one at a time kind of like a personal calculator。

 you enter the instructions yourself one at a time。

 but imagine you wrote down all the instructions you wanted to do first and then just wrote a little algorithm that would read through each instruction one at a time。

 that's a stored program machine。And the next trick you can add to that is you can have a special instruction that changes which instruction to go to。

It's kind of like ever read like a recipe or like a science experiment where it says like step one。

 get the beaker， step two， put water in， step three， and then step four is like， okay。

 go back to step two。You've all seen these instructions， that's all a branches。

 that's saying go to a different step in my sequence of instructions。That's all branches。

And that's also why functions at the assembly level are really just branches。

 and all of the functional semantics are kind of emulated by us。

 the compiler writer to make it look like we have like local state recursion， yeah。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_71.png)

Exactly， exactly right。Just skip ahead for one second。What would using branching instructions。

 what would it look like？To implement an if statement like this， but in assembly or simple I， yeah。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_73.png)

Some jumps， let's try it。 let's try this as an exercise what this。呃。Look at some scratch spaces here。

So let's use should we use simple IR rather than let's use simple I。

 so what would this program or this piece of the program look like？Well， actually。

 this is a tricky example I just realized。😊，Because I haven't introduced one type of branching。

 but let's make a guess， yeah， what would something like this look like？Okay。

 we need a label for sure。So let's put a new label here， let's just call it like if statement label。

So we're going to have a label somewhere。So I haven't actually introduced like conditional branching yet。

 so maybe we can come to it yeah。一と？し？Go to somewhere， right？Okay。Yeah， so good reasoning。

 So we can if we want to do。If we want to have programs that do something different depending on the input。

 we need to be able to test those inputs and change the behavior of the program if we had no conditional branching all programs know with a determinous set of instructions all programs that have the same output for the same input well now I shouldn't say that because computation you can still have sequence of computations but all programs would take the same sequence of steps in the program without conditional branching so as your colleague。

Studley pointed out that if we had a notion of conditional branching。

We could implement this in our machine language。And so we indeed have conditional branching in the architecture level also in our IR。

 we've got this new kind of go to， which first checks。Comparison between two。Opper ants。

And only if that comparison holds， do we do the branch， otherwise we don't branch。Implicitly， this。

This instruction happens if x is less than or equal to 10。This instruction happens。

If x is greater than 10， because we。It jumped here。Because we jealous。Questions on this。Semantics。

 yeah。共ぞかです。So we won't gonna get into the too much that this place。 So you can take my compile span。

 I to do that。 But effectively， you're gonna to have to flatten or figure out how to do that with individual branches because there' just like with functions。

 there's no notion of nested constructs and assembly。 It's just sequence of instructions。

 And you can change what the next instruction is。 That's it。

 So you would have to carefully design your。Jumps in order to emulate the same behavior of that nest。

 so I think there was a question yeah。Well， there's so， you mean this to this increment？や这い。三被微国。

Okay， so you're already moving ahead to figure out how to do the rest of this。 So how would you。

 how would you make sure that。So we executed x equals 11。

But what about the program that where x is less than 10 if we were to jump here？Like， let's say。

X is 9。So is x greater than 10？No， right， so then this would be the next instruction。

But what's the next thing we run？At this point in the program。Yeah， x equals 11。So this program。

 at least as currently written， even if x is。Less than 10， we'd still end up setting x x equals 11。

Yeah， yeah。If we're doing that， why don't we。Okay， so that's an interesting idea。

And it kind of reveals the the challenge of trying to turn what you're comfortable， you know。

 what you're used to and see into。Kind of straight line assembly code or sequential assembly code。

All right， so let's see what happens when we invert that condition。

 so instead of x greater in the 1 we。We observe that the next instruction。嗯。呃。

The next instruction is what we want to execute if the statement is true。

But we want to skip it if the statement is false， and so branches are better at skipping code。

 because when the branch is true， we won't go to the next instruction。

 we're going to skip the next instruction。Let's call this false label。

Because this is the where we're going to jump to if we。If this condition。

 if or I should say this condition is false。Then we're going to branch here actually it's probably confusing to call cost label let's call it like。

Else label is probably。Probably a。More clear。All right， so with me so far on this， so x equals 9。

 we say if x is less than or equal to 10， then we branch to else label。Otherwise。

 if x is not less than equal to 10， then we don't branch。

 which means we go here if x is greater than 10。We did it branch。Questions on this， this make sense？

Questions， I guess。Okay， so let's， let's。Try to fill out the rest of this。And in the else label。

 of course， we want to do this。Incrbitt x equals x plus1。Okay， so let's run this program for X， yeah。

The first， the first line。The first slide。Just like in a C program。

 well in the C program the entry point is the main function， but in C and imperative languages。

 it's the first line。Oh， sorry。 You mean like this。 Oh， it's my presentation。 Sorry about that。 Yeah。

 yeah， let me get rid of the old one。 Yeah， this is， this is the coder running， yeah。Yeah。げにつ。

I keep blame。You mean here？あどき。To skip this one。What you need to branch to？To东北。Well。

 we resolve that by inverting the condition。大政ぱ言ってや。Yeah。

 you'd have to have another conditional branch to skip x equals 11。everything saying？

You'd need an additional branch， right， so this way we avoid the additional branch， yeah yeah。

It is yeah， and actually if you look at the compiler like the output。

 it will invert the conditions so that I mean you don't have to。

 you could write the code in a way that did it， especially if you have an ifNL statement。

 but it just makes the assembly code kind of look like the C code。

So the idea is you skip when it's not true because you want to run run this code， but but anyway。

 this is just yeah， this is a common trick in the compiler world sorry so let's execute this program。

All right， so if x equals9。In this program， what's supposed to happen。

 is's supposed to skip x equals 11， right， and then what's the result of x if x equals 9？Ted， yeah。

 all right， but let's see and let's see if this code matches that， so x equals9 here。

Is x less than or equal to 10。 Yeah， so we branch that our next instruction is here。

And then we increment x， and it's 10。So it's all good， right？So let's see what happens when x is 12。

So is x less than equal to 10？So we don't branch， right？All right， let me say here first。

 so if x is 12， what should the。What should the value be for x equal 12？不 said。Yeah。

 it'll be so x is greater than12 to go to 11， and then the next line will increment it to 13。Right。

So right， so what happens yeah。ワて。Because of this， so if we check how it is。

 then we're skipping the next sequence of instructions。

And then we'll have to do another test down here， I mean we could do it。

 but you'd need a second check。呃。To make it work。All right。

 so let's see what happens when x equals 12。 So we said here x should be 13， right？Ohm sorry。

 it should be 12。I'm confused myself X greater than 10 11 should be 12， so in this case。呃。Right。

 right， Okay， okay， so x x is 12， it's not less than。10， so we don't skip it。

 it becomes 11 and then becomes 12。Oh， good， right？All right， so let's take a look at。

Let's take a look at a little bit more complicated case。 and hopefully。

 it'll illustrate why inverting the condition。呃。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_75.png)

Makes sense。So let's add an else branch here。Let's say。Let's's just do this。

 so if x is greater than 10， we set it to be 11， otherwise we set it 20。This is yes， this is C。

See like language。All right， so let's let's start with our condition again。

 if X is less than or equal to 10， we want to。Skip， we want to go to the El branch。

And so what do we want to run if？X is less than or equal to 10， what's the next instruction？我在。Yeah。

 sign next to 20 so this is。This is the inverse of our condition here， so in other words。

 we want to skip whatever the next lines are and go to the elsewherecra， yeah。I don't know。

 I think it's whatever the mode， oh， it's in Lisp mode， that's why。呃。

So I'll turn that off so that it's。Okay， so we the x over here， we set x to 20。 All right。

 so what do we put if x is not less than or equal to 10 in other words， is f equal greater than 11。

Signith at 11， right？And then we're good。Okay， so what happens if I think I know what you're going to say。

 So what happens if X？Is nine。That effects is nine， yeah， we go， this is true， so we branch。

And now access 20。Right。Yeah。あ遅い。Oh sorry， yeah， yeah， if you go to， that's the syntax on it。Okay。

 so questions on this。 So if x is 9， then we skip all this， go to the El label， set it to 20。

All right， but what if x is？Greater than 10。So let's say it's。12。Yeah。It'll still be assigned 20。

 so let's see why that is， so if x is less than or equal to 10。That's not true， right， X is 12。

 So this is the next line of instruction。 It'll set x to 11。

But what's the next line that we execute after this？Yeah， x equals 20。

So this L statement is always being executed both times because we don't have structured code here。

Right， we shouldn't， it's not correct。So how can we correctly translate this if that out statement to yeah？

Yeah， we just use another branch to skip。The El branch， what was the El branch？D are。

In our C program。So I just want to illustrate the distinction between conditions in a structured programming language where you have this notion of blocks of code built into the language and how this differs from branching and conditional branching in the C level。

So you you're not going to worry about this too much of this class because we're not going to be generating IR。

 you've got to be computing stuff from the R， but I will ask things about you know。

How to translate probably how to translate code like this into code like this。Yeah。

Kind of like how switched it。One by one。Oh， that's a good point。 Yeah， yeah。 so that's a good point。

 So in switch statements， you would have to say break。

Which really just translates to a go to to the line outside。

 actually switch statements are often optimized as tables。

But I guess they would still have a they still need a break statement， but yeah。

 that's exactly right， it would still be， yeah， you have to tell it explicitly to jump out past the branch。

Okay， questions on conditional branches in simple IR。So it takes two operas， a relational operator。

And test that， if it's true， then it does the branch if the test is true。

And so just be aware when we actually in the compiler world。

The meaning of this conditional branch is slightly different。

 or at least how the execution of it is slightly different because we have this assumption of structured code。

 how that gets implemented in real compilers is actually inverted so that you can put the if branch right after the conditional。

statementまで。The connu would just translate to a go to。To the head of the loop， Yeah。

 do you want to see loops， Do you want to see how loops are are done the， okay， let's see。

 let's see loops。So's maybe make something。Fairly。See if I can make something。Pretty simple。

All rightSo here's my sea like language。I think this terminates。嗯。All right。

 so let's run through this program， what's the resulting value of some？For this program。

I think it's two right， so step through it one line at a time which is always good practice x is 2 sum is 0 is x greater than0。

 yes， so sum equals sum plus1 sum is now1 x is x minus1 some x is now two。Is x greaterd than zero。

 yeah， so sum equals sum plus1， it's 2， now x is 0， go back to the while loop， evaluate it。

It's not true anymore， so we。Exit the loop。All right， let's see how we can。Represent this。

 so I'll let you guys say how can we write a simple IR program？That。

Has the same kind of branching behavior as this。Loop。Yeah。I'Go to start with a label。 Okay。

 let's call this label head。Why why start with a label？你向单。Okay。Okay， so's let's yeah。

 this is reflecting the fact that。In this loop， you have to reevaluate the condition every time。

 So's okay， so we have the。We've got a label here， I'm going to call it head for head of the loop。

Yeah。What's that。Okay， so let's add sum equals sum plus1。Okay。

 so sort that we're getting some pushback and we need a condition， so what condition。

 what would the condition be？The zero you vote to。So that's an interesting question。

 so you're saying the condition should be at the end。Or the condition at the beginning。There are。

 So there are several kinds of loops and， yeah， I see lots of hands going up。 So's yeah， go ahead。

 go ahead。Check if actually。お付き合わせ。あんえ。です。あてる。Okay。

 so let's do both of these options where the jump at the beginning or jump at the end。

Let's just jump at the beginning。 So what's the condition if we jump at the beginning。

To exit the loop， right， yeah。Okay， so if x is less than or equal to  zero， go to end。

 we want to exit the loop or go to exit。So this is the same principle as with our if statement。

 you can think of a while loop as basically an if statement with a go to in it actually。

 and if this makes it easier to think about， you could rewrite this program as，嗯。呃。

One way to think of this program is like。This。These are basically equivalent programs。But okay。

 so let's continue this program so we've got， move me。D。So we've got the head of our loop。

We've got the check。If。The blue condition is false。Then we exit the loop。

 So this is the how you check whether the loop condition is false， otherwise we。Enter the loop。

And as your colleague already said， we need to。Go back to the top of the loop。

In order to continue to execute the loop， because that's the behavior of the loop， right。

 you continue running the body until。The condition is no longer true。Okay， so let's execute this。

 Are there questions on this， questions on this code。So it probably looks very。

 very much like this if we had translated our if statement。Oops。

 if we translated our if statement in the same way， but put a go to in our language。

 then it would look very much like this。This is very much what the if statement looks like。Okay。

 so let's execute it， so x is 2 sum is  zero。Is x less than or equal to zero， no， so sum is now1。

 x is now1， we branch back to the top of head。X is1， so it's not less than equal to zero。

We go in to the next line， so it's two， x is zero， go back to the head。

X is less than or equal to zero， so we branch to exit。Questions on that。

So let's see what happens if instead。We did the condition check on the。Bottom of the loop。

 So basically we。Always， we run the body first。And then we check。

Is the condition still true if the condition is still true？Then we go back to the head or actually。

 no way， I can do the same thing。The condition is false， we leave the loop。If not。

 we branch back to the top of the head， so all I did was switch。

Move the condition from the top of the loop to the bottom of the yeah， get a question。Oh， very good。

 yeah that is what I was getting at， this is the semantics of a do while loop。

Did they ever use a do while loop and see？A do while loop actually looks very much like this。

 do while。The only difference between a do while and a while is that the do while always executes。

At least the body once， it's like one or more， whereas a loop is0 more。 So yeah， that's exactly it。

 So your intuition is right。 And actually， there are。

I think some of these compilers will turn things into a do while loop somehow。

 I'm trying to remember what GCC does， but yeah， that's the punchline。This is still a loop。

 but it's a do while loop in terms of C，You may need to go。いるて。エクシース？Rather than zero。つ。

And they cannot don't need the next。Oh， I see what you're saying。Yeah， that's right， that's right。

 Yeah， you could rewrite this， so you're saying you could rewrite this with a single go to。

So you say x is greater than zero go to head， yeah， yeah， that's right， that's right。

 yeah you could write it like this， that's right。Yeah， you could write it like this， so it's just。

 yeah， you could write it like this。So if you don't want to invert the condition。

 but this is still a do while。Because this will always be run at least once。Questions。

 questions on this。This is going a little more into compilers than I expected。

 but I glad there's some interest。Yeah。😊，たつ。I mean， put this on the bottom。That's a good question。

 let's see。Can we。Can we design this where？We check。呃。I don't know。 So we could。

Have the body here somewhere we say go to the body otherwise。Go to the exit。 Yeah。

 I think you could do it like this。I this right？You check the condition if the condition is true。

You branch to this body label and that body label always branch back to the head。

If the condition ever false， then you don't branch to the body instead you go to the next line。

 which is a go to exit。Does seen right yeah？to the。その回。So it's like。

This one the Rich only have before， but you also， I mean。

 I guess you check up here to even not even add to the loop。So another variation。Like that。

 you were thinking？Yeah， that's another variation， so you don't have to worry about understanding each one of these。

 but you can notice that there are lots and lots of ways。

 technically infinite number of ways to compile the same C like program into machine code。

And trying to prove the equivalence of programs in general is very， very hard to do。

But hopefully it's at least some exercise to learn about this machine like branching versus C。

 So in the same way that functions。Don't have a one to one construct in assembly。

 conditionals don't either， they have to be emulated with branch behavior。

And you don't get this nice block structure that you have， you have to be careful with your。

Remember that you're running each line at a time in sequence until you have a branch。All right。

 questions， questions on conditional branching。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_77.png)

This was a good deep dive into。The semantics of conditional branching。All right。

 let's see what I was skipping here。Yeah， I think I covered all this。So yeah， that's， that's。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_79.png)

Same thing went over。All right， so implementing this in assembly just as a refresher。

How do we access x's variable data when we translate this to assembly yeah？Right。

 offset from the base pointer， so just to remind remind everyone。Okay。

 so let's see how we do conditional branches in。Assembly。

 so unlike our simple IR language where it's a single if condition go to again。

 we've got two operations we have to execute an assembly an Intel assembly in order to perform this this comparison so the first is a comparison operator the comparison operator will。

As it says， these compare the values of the two registers。

 I think it can also probably take an address it'll compare these two registers。

And just like with arithmetic。The registers are swapped。

 the left upper end of the comparison is on the right， that's why RX is on the right here yeah。

That's a really good question where do the results go so another。You know。

 idiosyncrasy of the Intel world is that there is a special flags register that gets set。

That is not explicitly readable by we， the users of the machine。Instead， what you do。

Is you run this comparison operation and then you pick one of a series of jump instructions。

 different jump instructions， so there is a different jump instruction for every comparison condition。

That you need， so you have jumped less than or equal to。

 so let me actually show the whole table of these。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_81.png)

You have a series of assembly jump instructions， Intel jump instructions for each operator that we want。

 so we have jump if equal， jump if not equal， jump if less than jump of less than or equal。

 jump of greater than jump of greater than equal to。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_83.png)

And so what happens at the machine level is this comparison instruction。

Seets flags in a special flags register that is not directly observable by you。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_85.png)

And then the jump instruction will read those flag registers and decide whether to jump or not based on the condition that you've asked for。

 the condition code。All right， let me show。O。So what that means is that a statement like this and simple IR where we ask。

 is x less than or equal to 10？If so， branch。We'd have to make sure that X。

 the left operaand is in RAX， the right opera R here。

 we'd have to run the comparison instruction and then branch if less than or equal to call the JLE less than or equal to。

Up in order to hit the branch。So our conditional branch in simple IR becomes two instructions compare。

And jump using the corresponding condition code。That corresponds to our operator。Yeah。あで見え。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_87.png)

Yeah， yeah， yeah， you can。 and you can actually yeah so。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_89.png)

You could put immediate values， yeah， you can even put memory values in there as well。

So just like with all the load and store stuff， you can make a compiler to make fewer instructions and you're free to generate the code however you like。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_91.png)

I do things in ways that are like easiest for me to think about and easiest to write。

 and they end up being ver posts。Because I know that there are compiler optimizations that will do that for me yeah。

確に自で。We're putting this label。Between our。もうい緒です。Yeah， if you use the JLE branch， yeah。

 so there's lots of ways you could do this， you could swap these and then invert the condition。

 so what's the inverse of less than or equal to。Greater than yet， not greater than greater than。

 So you could do R A X， RB X， and then do J G for greater than。And actually a little。

Something that's interesting about the comparison operator is it's really just a subtraction。Up。

It's a subtraction that does not save the result。So it turns out that all arithmetic operations。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_93.png)

Does it actually say it here？Yeah， the comparisons were performed by subtracting the second upper end for the first。

 well， it's reversed in the AT&T world。But actually， these flag registers。

 which are described somewhere， I think I' put a link to describe the comparison the flag operators。

 but basically every operation you do， every arithmetic operation， the flag registers are always set。

And the flag registers hold， is the result zero， was there a carry flag， is the result less than？

And so every time you do an arithmetic operation， these flag registers are always set。

And so you can think of comparison as turning。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_95.png)

As turning the。The relational operator， which I think you probably know from。Like math。Class into。

A comparison to zero。It's one way you can think of what the comparison operator does。

You can always turn any well， it's sort of weird to see with this with this case， but if I have。

If I have like is x greater than y， that's the same thing as asking。Is x minus y greater than0？

And so at the machine level， this comparison is really just doing a subtraction and then checking whether checking the property of the result is it greater than zero。

 is it equal to zero， basically？So that's why comparison is done this way。

 and that's why comparison is really just a subtraction in the Intel world。But anyway。

 you don't have to like worry about those details， you can just remember that。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_97.png)

This is， if you want to generate a conditional branch in the assembly world， this is how you do it。

 you put the left upper end here， the right upper end here。

And then call the corresponding jump instruction。To implement this Sr。Instruction。Questions on that。

So this stuff is simple to the point of being difficult because you have to be really meticulous about the operator opera end order。

And。The details of how to emulate a conditional statement in assembly。And the fact that comparison。

 there's no explicit saving of state it's done for you by the machine。

That's also why Ju El is just takes a label， it looks like an unconditional branch。

But in the machine， it's actually checking these flag registers。

 checking these condition codes to decide whether it should branch or not。Okay yeah。

 but I'm going to give， you know， you have this you know in Cogen3。

 you have like all the details about these instructions and so it'll be pretty。

Formic when you actually generate the cop power， you don't to be an expert in writing assembly。

I'm sorry， second。Yes， Coent3 is assigned today， starting today。

 and I have the project questions on this。Questions on assembly， yeah。Yeah， yeah jump false。Yeah。

 RAX is less than or equal to。RBX。Yeah， this is saying， yeah， yeah。Yeah。

 so this jump less than is saying RAX less than or equal to RBx if that's true， then then jump。

The job。So in the compiler world， I think what they'll actually GCC will probably do is that you know we know when we saw and when we tried to compile a CF tape and we inverted the condition。

 I think what GCC will do is it'll actually swap this jump here instead。

 it'll use the same opera and then it'll convert。It'll actually swap this opera instead。

We could test it， but we don't have much time left。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_99.png)

All right， so here's the whole table， this is the simple IR op。Yeah， I take it up。Yes， yes， he will。

 yeah I think I think he did， I think he's doing the project。

 I gave it to him a little late unfortunately， so hopefully he'll have finished the project by then and he'll he'll give you tips。

🤧。Okay， so this is a kind of like template or pattern for how you do a。嗯。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_101.png)

forgot the forgot the actual label。 So this is the kind of template for。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_103.png)

For your compiler， for branching。Oh， that's the wrong。Let me improve this a little bit。

So this is the kind of template。Antler will give you the left and right upper end。

 it'll give you the operator all as ASI and it'll give you a label and you basically just plug those into。

A move to populate right this is one way to do it， but you populate it into a move。

 just like with the arithmetic。You load or do the immediate load。Into RAX and RBX for the two opera。

Then you always do the comparison。Always what you do at least in my scheme。

And then you just pick the right op code here in assembly and go to whatever the label was that was given to you。

That kind of makes sense， this is where the pieces of simple IR go into。

 so this is like a template for doing any conditional branch。In Intel assembly。

 and then you just kind of fill in these。These placeholders。So that's how you do the branching part。

Of our compiler。Questions， questions on that。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_105.png)

All right， so let me show a complete example are this was yeah， this is the one we had originally。

 so x is less than equal to 10。 go to false label。If it's not， go to the next instruction。

 which is x equal 11， and then what's the next instruction there for that。

 it'll just be whatever the next line in simple I is just like in assembly。

So let's see what the assembly code will look like。

So here's the translation of our conditional branch。We got to get the operas。

 so why is this negative 8 RVP thing， what's that？There the offset， this is how we get x。

And this is the immediate store of。Imediate copy of 10 questions on this。Hopefully。

 hopefully that's somewhat clear right now。 Here's our comparison。

 It's always the same if we design our。A compiler to do this， it's always the same。

 This is how I like to do compilers， I like to have compilers where I don't have to write a lot of conditional code。

 it's like everything's the same as much as possible。And then we have our branch。

So in this case it's based on whatever our operator is， we pick the corresponding assembly op。

And just copy whatever the false labelel is here。Questions on that。 So there's an example of。

Generating assembly code from this simple IR。Second。Oh， sorry。 this I just I'm missing a space。

 This is， this is just getting。The source for each for RAX and RRPX。So the x gets translated here。

This is how you translate x， and this is how you translate an immediate10。In AT&T syntax。

 so this code the code to do this is basically given to you in enter a sign。

 I've given you enter a sign and the code in there actually shows you how to check the antler operaand and determine whether you need to do an offset or an immediate value。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_107.png)

So that code is like， I think did I give it to you here as well。Yeah， I gave you this code。

 so this code will。We'll check for you whether the operaand is a name or a number。

 and it'll actually give you the string。Of either the load or the。

So you can check enter a for how to do that。Okay， so that's the conditional here' is of course。

 the assignment， this is enter assigned， at least my version of En assigned。

We do the immediate copy to RAX of 11， and then same thing， this is the offset of x。

 so this is a store to update the value of x。Questions on this。Then we had our false label。

 how do we translate that to assembly？What does an assembly label look like？It's the same thing。

 It's identical。 It's identical in assembly that the syntax of labels is basically identical。

And then we've got our x equals x plus one， and here's this is the more of the error arithmetic part of。

That's a though， this is like the arithmetic part。That's what we covered last time。All right。

 questions on this。So hopefully this is mostly straightforward if you' got like Code Gen1 and especially CodeN2 and you got the hang of emitting assembly code。

 which can be a little mind boggly when you first do it and actually normally we're writing programs to solve a specific algorithm to give us some like numeric or string result and compilers our outputs are other programs and so it can be very tricky to wrap our head around this because we're writing in a programming language and we're writing code in that programming language that's meant to be output and not evaluated。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_109.png)

So if you can wrap your head around the notion of just printing out assembly code。🤧う。

And hopefully this will be。Not too bad， a little bit more straightforward。

 and so just review the lecture notes， review how arithmetic and conditional jumps work。

I'd like to make things very， very template driven where I don't have to do any creativity in generating the code。

 I just have a very simple template。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_111.png)

And I've given， you know， like， for instance， this one。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_113.png)

This template that I gave you。So if you use a template like that。

 you can literally translate this to Python as printing this out but replace these operas。

 et cea with。Python variables that you set according to whatever the developer gave you in the input language。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_115.png)

Okay， so for CoN3， we'll be implementing。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_117.png)

Arithtic and branching。And so I've given you template code that has local vars and enter a sign。

AndThese are the only four functions you'll need to implement operation is the simple IR arithmetic arithmetic operation that we talked about last time that we've got label。

 which is super， super simple， it's just spitting out the label in a colon。Go to。

 which is also very simple， it's just JMP and the label。

 and then if go to that's the trickier one where you' going to have to test the operator。

You'll have to convert the opera ends。And then generate that assembly template code。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_119.png)

Let me show you one。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_121.png)

And then I've given a description of what you need to output， so there's some helper stuff here like。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_123.png)

Example code。呃。How you can check the operator。For if conditional ifs in Python。

 this is how you can do it。And so here's where you would just set which assembly operator to use。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_125.png)

呃。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_127.png)

Oh wait， that's not the opera。This is for arithmetic， sorry it looks very similar for branching。

 so this is how you check the operator in branching， it's the same idea。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_129.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_130.png)

But let me show you one little facilityve。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_132.png)

Given you。So one challenge is that， yeah， yeah， could。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_134.png)

Oh I actually that's funny to ask I expected somebody might ask this， so it's just Python for No op。

 it's Python for don't do anything and because of their indent specific world you can't just like have an empty branch so you use pass for an empty branch that's all it's a Python thing。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_136.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_137.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_138.png)

All right， so I've made it so that you can test this project even if you haven't done CoJN1 and2 so these are all separate projects that you submit separately。

 but you can by all means copy your CoJN1 and CoN2 code and see the joy of having the complete compiler but you don't have to do that you don't have to get CoJN1 and2 right in order for this to work。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_140.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_141.png)

So I've set up this little wrapper。Which gives you a pre compileiled assembly template。

That will automatically plug your compiler output into it。So let me show you what I mean here。

 this is the IR。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_143.png)

Fun that I've precompiled for you。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_145.png)

So it just it defines a function， it gives you a bunch of local variables。

 hopefully enough for your testing。Gives you a result variable。

And all the template does is it prints out whatever's in that result variable and then returns。

So this is this you need CoN1 and Cogen2 to do correctly。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_147.png)

嗯。And so what you can do is you can modify this program。To add the code you want to test。

And so make sure you don't have any of the codeN1 or two functions implemented。

 so just use the template that I gave you here。You mean the template I gave you？



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_149.png)

No， this is an IR， this is an input program， this isn't the codegen program。 This is IR。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_151.png)

So I've given you an IR template Yeah， you can fit when you want to test it。

 when you want to test your compiler， you put in the code that your compiler will generate so your compiler won't do anything for function。

 call or return because you'll just leave those functions unimplemented as it is in the template is in the code template I've given you。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_153.png)

And then you run this through your compiler。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_155.png)

And it'll give you just a fragment of a complete assembly program。

 it'll give you just the compilation of this stuff here。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_157.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_158.png)

And you run this make change directory wrapper， so put a make file in here that will take the assembly template and glue it on either end of your compiler output so that you'll have a working complete program。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_160.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_161.png)

So if you just follow these directions， you don't necessarily have to understand how it works。

 but if you follow these directions， just add your code here。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_163.png)

And then run make。On it。It will。Put your code in the assembly file and put the code that you produced in an assembly file template and then run it and you'll be able to see the output。

 so put whatever you want to test in results and it'll print it out for you。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_165.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_166.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_167.png)

🤧And this run this is how you can run it。You can make several copies of these or you can have several versions of it that you copy in or out of the wrapper。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_169.png)

If you're interested in how it works， it it has a template split into two files。

 the start and end of the template， and then it just runs your compiler。



![](img/da712e8a7e1fc71b29ce50ef670ea7ff_171.png)

On the input program and save it as a program called mains。body the ascent of it。

 and then it just uses the CA command to print out the start of the template。

 your generated code and the end of the template， and then that will give you a complete working assembly program that you can build and run。

If you want to like do it yourself。All right， questions on that。So good luck on Cogen3。

 CoJN1 is due tonight， but remember you have a late policy and have a good weekend。

 everyone see you next week。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_173.png)

え。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_175.png)

Sure， take care。