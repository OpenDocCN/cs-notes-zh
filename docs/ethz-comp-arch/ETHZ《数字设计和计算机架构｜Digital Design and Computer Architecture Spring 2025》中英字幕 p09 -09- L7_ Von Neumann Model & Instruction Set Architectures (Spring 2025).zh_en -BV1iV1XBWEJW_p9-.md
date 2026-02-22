# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p09 -09- L7_ Von Neumann Model & Instruction Set Architectures (Spring 2025).zh_en -BV1iV1XBWEJW_p9-

![](img/2aeaa1a1411c66a2175e6eb0daf07961_0.png)

Yes。No。行。Yeah right。So。在有我的我さ。なしの。Yeah。所自己都。Do you know why the camera is like this？



![](img/2aeaa1a1411c66a2175e6eb0daf07961_2.png)

。啊，这。Right。就。

![](img/2aeaa1a1411c66a2175e6eb0daf07961_4.png)

Is live stream working？Okay， good。The。老还有。I。对。我直这个死。Yeah。I mean， we can use the camera right here。

有事实。This makes little sense。ち。Just use the camera over there。🎼，🎼Oh。🎼あ。两乜事。Yeah， that's better。个好。

Okay。I think there's some background issue， though， as you can see。It's related to this computer。

 yeah。Okay， let's get started。Everybody can hear me in the back。Good。

 looks like we've lost some people。This room was more crowded in the past。Do you guys agree？

I went for a conference and everybody's gone well not everybody， you guys are still here okay。😊。

Today we're going to start with the architecture part of this class。

And we're going to move a little bit higher up in the stack in the transformation levels of transformation。

 we're going to talk about the one moment model of computing and then instructions at architectures and then we're going to bridge the gap from there to the logic later on。

 but just some reminders for you。😊，Okay。There are office hours。

 these are hybrid Mondays one to 2 pm there's a moodle announcement you can check that's correct right and your extra credit assignments are coming up one is on March 21t some of you may have watched it some of you asked questions about it another one is coming on April 1s。

So hopefully how many people have done the extra credit assignments at least one， okay？

Is it interesting？Okay。Okay， hopefully you'll get extra credit。Okay， so what we have learned so far。

 this is what we've covered， we have covered three weeks of lectures plus we've started the labs。

 hopefully labs are going well， I'll ask you questions later on about them。

 but essentially we've started with the very high levelve device level abstraction。

 transistor as a switch and then we've built logic on top of that。

 and we've talked about how to design that logic， both combinational sequential。

 how to design finiteate machines， how to describe that logic using a hardware description language so that we can actually instantiate these things at the lower level and how to actually analyze the timing and verification。

 functionality as well as the timing of that circuit。😊，Does that sound good？

So this is all digital design， so if we are really done with the digital design part of this course since we don't have a lot of time in the bachelor's program in computer science here。

 digital design is a much bigger field actually you can take multiple courses on that topic。

 but we're dedicating one fourth of this course to digital design。😡。

Now we're going to move up a little bit higher， we're not going to go into micro architecture immediately because I want you to get the higher level perspective which is really how a computer executes things so we're going to talk about the one Neuman model and we're going to talk about example one Neuman machines。

 essentially instructions set architectures that operate based on one Neumman principles LC3 and MIPS specifically。

 I'm going to start with LC3 which Pat and Patel book does a great job covering the fundamentals of and then we're going to actually give examples from two architectures to instructions set architectures LC3 is the little computer3 which is an educational ISA MIPS is a real ISA that's used in the field and there are many。

 many other instructions that architectures like H86 arm risk5 etc。

 that we're not going to talk about。😊，And then we're going to talk a little bit about assembly and programming。

So we're really going to talk about programming interface to hardware today and then later we're going to start on micro architectureiture and we're going to have a lot of interesting micro architectural concepts on how to implement。

😊，And instructions at architecture such that you obey the software hardware contract。

And do that while exploiting the logic gates that we have designed in the past。这是上个。Okay。

 so basically， we're going to build a computer。So we will learn the basic elements of a computer today and we'll look at an example of one Neuman machine。

 and today and tomorrow we're going to cover instructions at architectures。

 including different types of instructions， operate instructions， data movement instructions。

 control instructions， we're going to talk about instruction formats， addressing modes， data types。

 etc。😊，These are some readings， the red ones are what we're going to follow today and tomorrow essentially。

😊，Especially Pat and Patel I'm going to follow but I'm going to give you examples from Harris and Harris as well and tomorrow we're going to talk about programming a little bit assembly level programming。

 I'm sure you've seen programming in other languages right high level languages and we're going to try to bridge the gap between high level language and assembly and ISA a little bit。

Okay， next week， hopefully we'll start micro architecture。

 we'll start implementing the ISA essentially next week。😡，Okay， so let's jump into it。

 How many of you heard about the Woon Neumman model， Does this mean anything to you， Okay。

 how many people did not hear about this。It's okay， so that's good。

 most people didn't hear based on the hands I've seen。😊，Do people who have heard about it heard。

 did you hear it in classes？No， okay， I see hands head shaken so probably you heard about it somewhere else。

So basically this model is really about building a computing system。

 I'm going to give you an alternative model， hopefully tomorrow， not today， we don't have time today。

 but this is not the only model， but this is really the most successful model that we've had so far。

😊，Because it came first， partially， and it's easier to program also secondarily， I would say。

Okay so recall， I've shown you this picture before， at some point。

 we will cover all of these components， we'll cover processing， memory and communication。

 but we'll especially focus on processing initially， and for this to work。

 we need a model of computation。😊，Basically， in past lectures。

 we learned how to design combinational logic structures， sequential logic structures。😊。

With those logic structures， we showed that you could build an ALU arithmetic logic unit execution units basically we could build a decision unit。

 for example， we could build memory storage units， we could build communication units we've seen examples of this all of these are basic elements of a computer。

😊，Today we will raise our abstraction level to a higher level。

 so to this level essentially software hardware interface and a little bit of micro architecture so that you can see that software hardware interface can be implemented in micro architecture。

 but we're going to look at different implementation choices later。😊。

And we're going to use logic structures to construct this basic computing model。

So what are the basic components of a computer if you think about the fundamentals， very basics。

 you want to get a task done right we want to solve problems as we have discussed in the first lecture。

😡，And to solve problems， we need to express those problems in a language that the computer can understand。

😡，So if we need a computer program basically right in the end， you write a computer program。😡。

And you have written computer programs at high level languages。

 we're going to look at computer programs at a level that the machine really understands。

 we're going to look at ones and zeros， for example， today。What is the computer program。

 computer program specifies what the computer must do， right？😡，That's the goal。

 And then we need to design the computer itself so that it could carry out this program right to carry out that specified task that's dictated within the program that hopefully that's obvious。

 You need both of these。😡，So a program is really a set of instructions in the end。

Each instruction specifies a well defined piece of work for the computer to carry out。

 this is really important because we're going to have instructions that are at the level that the hardware can interpret and understand。

😡，When you write programs at a high level language。

 you may write things that are very high level right it could be I don't know。

 you make an operation on a key value store for example。

 that could be part of your programming language， you do something on a hash mapap right that could be part of your programming language。

😡，Instructions may the hardware itself may not operate may not understand those hashmap。

 you need to map those things to the hardware we're going to look at what the hardware can do at least in the instruction sets that we're going to study but I'm going to also show you that instruction sets can be designed to be high level as well okay so what's an instruction instruction is really the smallest piece of specified work in a program。

😡，And these are actually all from Pat and Patel you can read the parts that I mentioned in Pat and Patel instruction set is all possible instructions that a computer is designed to be able to carry out so okay were going we're defined the instruction set right now we're going to build up to it。

😊，But before we get to that there should be actually a model of execution also。

 and that's where the Woon Neumman model comes in， if you want to build a computer that can carry out instructions。

 you need an execution model for processing programs。😡，So John W Neuman。

 whose name you may have heard of in the past， how many people heard of John Neuman。

 you may not know the model but you may heard of the name right he proposed along with his colleagues a fundamental model in 1946 which became very popular this is what he looks like。

And this is the paper。It consists of five components。

 later I'm going to distill two major things in a one Neyman model。

 but let's go through these five components first。We start with memory。

 memory stores the program and the data because you need to actually have the program somewhere。

 you need to have the data somewhere， and you need to do something to it。😡。

Processing unit does something to it， essentially， these are the processing units。😡。

And then there is an input unit that can take input from the user and there's an output unit that the computer can communicate with the outside world。

😊，And finally there' is a maisttro which is a control unit which coordinates everything the computer does。

 it controls the order in which the instructions are carried out， essentially。

 so these five components are proposed by W Neumman we're going to examine examples of these and throughout this lecture we'll examine two examples of the Wal Neumman model。

 the LC3 little computer3 and MIPS MIPS is a real ISA as I said。

 these are good examples these are good educational examples。

 but I'll give you examples from different ISAs， instructions that architectures as well。😡。

Does that sound good。Okay， go。Okay so I should say that all general purpose computers today use the Wal Neman model that's why we're starting with it this doesn't mean that it may be the most efficient model later for example。

 we're going to see accelerators for machine learning in lecture 18 or so that are based on completely different principles they may still take instructions。

😡，So that they can carry out some tasks， but they don't necessarily use the Wa Neumman model。Okay。

 so this is a pictorial representation of the Oneon Neumman model。

 it has five of these components that we have discussed。😊，We start with memory。

I'm going to define some of these and this is not magic basically we already built a memory。

 a simple one， but this was a  12 bit memory if you remember right we have four locations here and each location stores three bits we're going to build bigger memories and we're going to abstract it such that we can actually use instructions to specify locations here theres a logic level view of memory。

😊，That's a memory。So what does the memory store in the Wo Neman model。

 it stores both programs and data。😡，And actually， theres no distinction between them if you just look at memory。

 it's all bits。😡，There's nothing that says， oh this is a program and this is data。

You don't distinguish between them and memory， you will distinguish between them when you're processing when you're actually executing instructions as we will see。

 so control logic， that control unit distinguishes treats a particular memory location。

 memory address as containing an instruction versus data， depending on when it access it。😡。

This will become more clear。Okay memory contains bits， as I said， bits are logically grouped。

 they could be logically grouped into bytes and in these ISAs that we're going to look at instructions architectures that we're going to look at there grouped into bytes。

 a byte is eight bits。😡，These are actually terminology that comes from 1960s from IM 3 1691。

 which is one of the very interesting computers and words word could be actually 8。

16 or 32 bits depending on the instructions at architecture。😊。

So we have actually defined some of these things earlier。

 address space is the total number of uniquely identifiable locations in memory。😡，In LC3。

 for example， the address space is2 to the 16。😡，Mean you have 16 bit addresses， okay？😡。

In MIPS the address space happens to be 2 to the 32。

 32 bit addresses in a more like a modern ISA in structure that architecture XA664。

 the address space is up to 2 to the 48， meaning you can have 48 the addresses or your memories that can be this address space is what could be referenced by the programs。

 a program can reference very large amounts of memory if you're given this address space。😡，Okay。

 addressability is how many bits are stored in each location， meaning in each address。😡，For example。

 you can be 8 bit addressable， in other words byte addressable， many ISAs today are byte addressable。

 or you could be word addressable， meaning your address can specify 32 bits， for example。

 assuming your word is 32s in LC3 for example， a word is 16 bits and your word addressable。😡。

These will become also more clear， but these are some definitions and these are the things that the programmer sees whenever you program at a low level as an assembly programmer that looks at the instruction set of a computer。

 you see the address space， this address space is specified in the ISA document。

 you see the addressability so that you know what an instruction is going to do how big the address will be and how much data that you can specify with a single address。

8 bit or a single word and we will see that there are different instructions that could be referring to a single word or a single byte。

😡，So that we can， for example， get a single bike from Memi or get a whole word from Memi， okay？😡。

I just said this basically， given instruction can or on a byte or a word and we will see examples of this。

 hopefully toward by the end of this lecture。😊，Okay。

 this is a simple example as a representation of memory with eight locations。

 you have the addresses of these locations， since there are eight locations you have three bits to identify each location。

 you should be able to do these calculations very easily by now and each location。😊。

Happens to contain8 bits， one byte over here。So you can think of this as by addressable memoryme and the address space is eight。

😊，Okay， each location has eight bits。😊，So this is an example from Pat and Patel also if you look at this value6 is stored in address 4。

 address 4 is this and value 6 is stored there and value4 is stored in address 6。😊。

Just to confuse you。It's not confusion， of course， you know how to deal with your bits probably right？

Okay so one question is let's make this is one specification of the ISA for example。

 you can say my address space is this big and my addressability is 8 bits and this is what I have you could design ISA this way。

 but this is very limiting clearly you don't want memories that are this small so modern ISass are much larger as we discussed in the earlier slide but just for fun if I ask you the question how can we make the same size memory bits addressable what this would do is essentially the size of this memory is total eight locations8 bits each 64 bits if it's bit addressable you would have 64 locations where each locations is a single bit right so your address size would be six。

😊，Bits and each location would specify one bit。😡，So it's possible to do that。

 Most computers today are not programmed that way。 You don't have instructions that are paid on bits。

😡，The grand larity at which you can get data from memory is。Usually the smallest is8 bits。

 meaning one by， this is changing with machine learning a little bit。😡。

Because people are trying figuring out that sometimes actually you want to use smaller data types。

 I'm going to define the data type later on like one bit，2 bit，4 bit。

 so that you can operate on smaller data elements because it turns out operating on larger data elements is expensive in terms of energy and computation power。

 if you operate on smaller data elements， you can actually。be much more energy efficient。

So things may be changing if as ISAs and workloads evolve into the future and the energy requirements push people to do something different。

So it's good to basically know that you can go into trade offs like this Okay。

 so let's talk about word addressible memory word addressible memorymy says that each data word has a unique address。

😊，If it was bit addressable， each data bit would have a unique address。

 let's start with word addressable in MIPS， for example。

 a unique address you have a unique address for each 32 bit data word。😡，In LCC3。

 this is specified by the ISA designer， somebody designs a hardware software interface。

 somebody documents it， it's like a contract 4000 page contract as you will see later today tomorrow probably where they specify everything that the programmer some programmer needs to know in terms of how to program this hardware right in LCC3 somebody specified that a unique address。

 there should be a unique address for each 16 bit data。😡，Okay， so let's take a look at MiPS memory。

 MIPS memory looks like this basically。😡，So at the bottom， you see word zero。😡。

And then you have word one and then you have word two and then you have word three and these are some random data that we have right and here we have hexadecimal representation you have four bits here and you have eight of these four bits。

 so you have 32 bits total right？Hopefully， it makes sense。O。😊。

So you have a word address essentially， this is word address zero， word address 1， word address 2。

 word address 3， if you specify， oh， I want to get the data at word address 3。😊。

You will have an instruction that enables you to express that to the computer and the computer will access this memory location because it's I3 using a decoder。

 if you remember， and that data will be transferred somewhere as we will see soon and you will get this data。

 okay。😊，Okay， let's take a look at bio deersible memory in this case each byte has a unique address MIPS actually is biddeible。

 it turns out。😡，LC3 is not biotaderciible buts there's an updated version of LCC3。

 little computer 3B， that says byteteersible as well。😊，So now this is our MIps memory that's。

Became by addressable， I didn't show you the longer version。

 but I actually divided the words into four pieces over here， each of them is a byte， as you can see。

😡，And this is the byte address now， so you can see that we don't have a word address。😡。

Here we have a by that of zero。😡，And one of them is zero over here。

 we're going to talk about that soon。So let's assume that this is0。

 this is by the is 0 by the 1 byta is2 by the is 3 and then you have byta 4 over here， this is 4，5。

 six，7，8，9， 10，11 etc ceter， right you can do tism。😊，Okay。

 so now we're by to dis whenever we use an instruction that says， oh， get the bite for me。😡。

Let's say I want byte four。😡，And you somehow specify the address and we will see all of that。

 we will see how we specify all of those to the computer if you say I want PteS4 using an instruction the computer will get you F7。

😊，Assuming some ordering as we will， okay， so this all clearly brings up the question。

 how are these four bytes ordered？😡，So people actually think。

Some data is expressed in terms of white some data is expressed in terms of words。

 right you may have a large data type like 32 bits。😡，But your memory may be bite addressable。

 meaning it consists of eight per each。😡，Then if you think about a word。

 how do you actually lay out the word matters， so how are these four bytes ordered becomes a question。

😡，I'm going to quickly divulge into that， but basically the question is。

 which of these four bytes is the most versus least significant？😡。

Is the most significant bitetes here or is it here？😡，Okay， so you may have read Gullive Travel。

 so many people read Guive travels at some point。Not at school。

 they don't teach this at school anymore。Not for fun there might be more fun things these days I don't know but I would recommend reading this these are beautiful stories but basically Gulaware encounters the folks that are big Indian versus little Indian and this has influenced computer terminology also and these folks are different folks they're different in the way they break their eggs。

😊，You know， eggs look like this， right？They're asymmetric， they're not symmetric in general。

 and some folks decide to break their eggs on the site， the big site， they're called big Indian。

And some other folks decided to break their eggs on the left side， the little side。

 they're called Little Indian。Makes sense。Why do they do it this way？

Because they're used to doing it that way right if you're born to a place where everybody starts breaking their eggs on the。

😡，Big part， then you keep doing that probably。Well， you could start a new trend， of course。

 over there， but you may not be immediately accepted at that place。

 so this is a convention basically or tradition in other words。😡，So which one is better？

Neither of that maybe， I mean， it depends on your taste， perhaps， right？

So basically we have a similar issue over here， if you look at the memory that we have designed and now these are not data over here。

 these are the addresses， byte to addresses I have put for each word word addresseses are the same in a big Indianian machine you lay out the words such that the most significant byte over a word。

😊，Is at the lower address。So if you specify address zero。

 you get the most significant byte in that word that you store， if you specify address3。

 you get the least significant byte。😡，Why does this matter because if you have a 32 bit value and if you want to add it to another value？

😡，You want to know what's the most significant bits and what's the least significant bit， right。

 Because these are very different things。 bits 0。Effects the addition the least because it's the least significant bit。

 bit 31 affects the addition the most because it's the most significant bit right in the little Indian word world。

 it turns out least significant byte is in a word is at the lower address like this and most significant byte is a higher address。

😡，Again， you can say， oh， okay， this is more intuitive for me。

Maybe because it's lease and the address is lower。I get that， but in the end。

 you could be living in a world where this is the norm for you。

And it's certainly possible to do that。 right， You just need to rewire your thinking。

 And if you're always rewired that way。This is more natural to you than this， no question about that。

So basically， the' second。Does this really matter in the end。

 if you know where to put your least significant bites， it doesn't matter where it really matters is。

😡，When one big Indian system communicates with a little Indian system and they need to talk to each other。

 so you have a computer that lays out the data in one way because it's in one ISA that is big Indian and you have another computer of the network that uses the little Indian convention。

 when they need to communicate with each other they somehow need to make sure that the least significant bite in one computer it stays the least significant byte in the other computer。

 right？😡，Basically， they need to do some rejoordering。Okay。

 this is good to know and it's also this actually has a lot of lessons that I don't want to go into。

 but convention actually affects a lot of the designs that we have。😊，Okay。

 so how do you access memory that is a logical view of memory that we have these significant bytes。

 more significant bytes， et cetera now let's talk about accessing memory。😡。

So there are two ways of accessing memory， you need to read or load data from a memory location。😡。

And you need to write or store data into a memory location， okay？😡。

So these are the higher level things and then internally we're going to use two things memory address register and memory data register to facilitate this access this is one implementation there could be multiple implementations。

 but now we're actually blurring the line between abstraction level of programming and implementation。

😡，There's a memory address register in the Wo Nemon model。

 and then there's a memory data register to read， you first load the memory address register with the address we wish to read from。

😊，It could be a 16 bit address， for example。And in the second step。

 data and the corresponding location gets placed in the memory data register using some circuitry in the memory。

 okay， we're going to demystify that circuitry later。😊，To write， there are two steps also one。

 the first step is you load the MAR memory address register with the address and MDR with the data we wish to write because we're going to write that data to that address。

😊，And you activate the write enable signal into memorym。

 which ensures that the value in MDR is written to the address specified by AMR。😡，Makes sense， okay。

 this is one way of implementation and this is perhaps the simplest way of thinking about measurement。

😡，Okay， so we've covered the memory right now， that's the memory part of the oneno model。

 let's talk about the processinging unit pressing unit looks interesting because it has one component that we have seen ALU hopefully people remember ALU but people remember ALU from last like not the last previous lectures okay good。

😡，But you probably don't know what temp is， temp is an important thing and it's going to introduce some concepts that are going to appear again and again and again and again in our lectures。

 which is locality and we're going to build a memory hiarchy out of that temp later。😡，Okay。

 so pressing unit， the main function of a pressing unit is to perform actual computations。

 This is what a computer is designed to do right add multiply， multiply and accumulate convolution。

 it could be any operation XO， the pressing unit can consist of many functional units。😡。

And we started with an arimetic logic event in the past。

 it executes computational and logical operations patients in LCC3 there are only four our patients well at and and not actually there are three operations there was an extra added later on。

😊，In MIPS， there are a bunch of these operations， you will see these later on， so there is a no。

 keep that in mind because there will be a question later on that will relate to N。😡，は。

But there are other things like multiply also。There's a story about multiply that I'm not going to tell right now。

 but there are interesting stories over here so the ALU processes quantities that are referred as words。

 so they operate on words in general， but they could operate and ALU can also operate on bytes。😡。

In LC3， the word length has 16 bits， in MIPS， the word length has 32 bits。

 this is the maximum operation length of NALU。😊，Okay。

So recall this is the ALU that we designed in a past lecture， I will not go through this。

 but this is the jo your memory， so this is again not magic， we know how to design this thing。😊。

At least the subset of the MIPS， ISA。Okay， so what else is there in the processinging unit？😡。

This is an important concept。 It's not just about trusting。Usually， well。

 essentially when you do processing， you operate on data， right， Where does the data come from， Yes。

 it comes from memory。😡，But you need memory close to the processinging unit as well。

 because memory far away is too far away。😡，And this is called the fast temporary storage。

 it's almost always the case that a computer provides this fast temporary storage。

 essentially a small amount of storage very close toLU and this is visible to the programmer so we're going to actually explicitly specify the storage。

😡，Separately from the memory， you can think of this as as a small amount of memory close to the A L U。

The purpose is to store temporary values and quickly the access them。😡。

This is how fundamental data access and memory is to our instructions and architectures。Okay。

 so for example， I'm going to do this calculation a plus B times C divided by D in that order。😡。

You have intermediate results right， your intermediate result of a plus B， if you do an ad， a plus B。

 you can store it in the temporary storage as opposed to writing it back to memory。😡。

Because it's too slow to store each ALU result in Memi and then retrieved again for future use。

 if you had some small temporary storage， small amount of MEmy， very close。

 you could do this very quickly。😡，As we have discussed in earlier lectures。

 that MEX is much slower than an addition multiplication or division， that's the key over here。😊。

That's true for the intermediate result of a plus B times C。

 you did an add operation to do this and then you did a multiply。😡，Where do you store the results。

 you store the temporary storage， we're going to call these registers。😡，Yes。

 basically this temporary storage is usually a set of registers。

 it's also called their register file， it's essentially a small amount of memory。😡。

That is addressable by the instructions so that you can store these temporary results so that you don't need to go to a main memory to access things。

😡，So basically we have fast temporary storage， let me motivate it。😡，Again over here。

 because this is going to appear again and again later on memory is large but slow memory。

 what do I mean by memory memory is this。😡，Well， let's go back。This is memory。

 This thing over here is large but slow in X86 is 48 bits，2 to the 48。Eight bit elements， right？

We don't want to go out there all the time。So we have registers in the processing unit。

 they ensure fast access to values to be processed in the ALU。

 typically one register contains one word， same as word length because you operate on words in an ALU。

So this is called a register set or register file， it's visible to the programmer。

 it's part of the instructions in architecture separate from memory。😡。

It's essentially a set of registers that can be manipulated by instructions。LC3， for example。

 has eight general purpose registers。😡，And they're numbered R0 through r7。Because you have eight。

 you need three bits to specify a register。So you can think of this as a small memory that is essentially。

😊，That has eight locations where each location stores a world。Register size word length， as I said。

 MIPS has 32 general purpose registers， as you will see in your programs， it gives you bigger。

 fast temporary storage。😡，And again， they are specified from R 0 through R 31。

 so you have a5 bit register ID or register number。😡。

hich requires more space in your instruction as a result your instructions need to be larger in MIPS your instructions are actually smaller in LCC3。

😡，And register size is larger in MIPS because MIPS word length is 32 bits as we have discussed。 Okay。

 so now we introduced registers， we're going to do a lot of programming on registers later on today and also later in this course。

Hopefully， this makes sense。Okay， recall this is not also a magic， we have built this register。

 recall this register， so this is a four bit register if you look at this。😡。

It could be you can imagine a 32 bit register also， right？😡，O。

So this is another example of this forit register so these are mnemonics that I'm not going to go through。

 but these are some conventions in terms of how registers are named in MIPS it's really r0 through r31 but at the higher level when you program you may refer to registers like this and the compiler can compile it into these numbers。

😊，Okay， we may get back to this one we do assembly program。Okay。

 so if we've covered memory and the pressing it， let's talk about input and output quickly。

 we're not going to talk about that in detail yet， but these are critical also they enable information to get into and out of a computer clearly。

😡，You can use many devices for input and output。These are also calledterrails， input can be keyboard。

 mouse， scanner， disks， et cetera， many things。😡，Output can be the monitor， printer， disks。

 et cetera。So today actually we have many more input and output devices potentially in LCC3。

 as you will see in Pat and Patel book， they consider a keyboard and monitor and they have special locations and memory to access them。

😊，We will not talk about this right now， we may get back to it later。

But let's talk about the control unit， which really orchestrates how all of these are put together。😡。

It's essentially like the conductor of an orchestra right you have orchestra。

 they're all doing different things and the conductor really conducts who should be doing what at what point in time。

😊，Essentially， the controlling unit conducts a step by step process of executing every instruction a program in sequence。

 and we're going to see that。😊，Today， it keeps track of which instruction is being processed via this register called PC oh sorry instruction register。

 instruction register is actually the bits of the instruction that you' are currently processing。

 it contains which essentially it contains the instruction word if you will and we will see that we will see different instruction word too。

😡，And then this instruction register gets interpreted by the processor that where the processor figures out。

 oh， this instruction specifiedifies that I should do an a right this other instruction specifiedifies that I should do a load。

 but you have one instruction at a time in this instruction register。😡。

It also keeps track of which instruction to process next via program counter。😡。

This program counter or instruction pointer， it's another register that contains the items of the next instruction to process。

😡，Does that make sense， so you basically start with a program counter， fetch an instruction。

 put it into the instruction register， and then increment the program counter once the churn instruction finishes processing。

 you fetch the next instruction from the incremented program counter。

 put it into the instruction register。😡，Process that instruction。

Increment the program counter and then once this instruction is done。

 you remove it from the instruction register or fetch the next instruction into the instruction register and you keep incrementing the program counter so that you could go to the next instruction as sequential manner and instruction register provides a storage for the bits of the instruction that specify what the computer should do so a program counter is the address to fetch the next instruction from instruction register is the data value of the instruction。

😡，Does that make sense？O。So basically we've kind of built our architectural state。

 I didn't tell you exactly， but these are all visible to the programmer except for the instruction register。

😊，These are the things that are visible to the programmer when you program。😡。

Instructions that architecture exposes to the programmer memory。

 which is essentially an array of storage locations indexed by an address， you have addressability。

 address size， etc ce， and you have registers， general purpose registers。

 these are given special names in the ISA as opposed to addresses。

 fast temporary storage as we have discussed， there could be also special purpose registers which we're not going to deal with yet。

😊，And then there's a program counter， this is the memory address of either the current or the next instruction depending on where you are in the instruction processing cycle。

 which we will get to sue。😡，These are three。Key parts。

In a machine that are visible to the programmer。And instructions。Programs our set of instructions。

 specify how to transform the values of this program or visible state。 for example。

 an ad instruction says。Adds this register to this other register and put the result into this destination register。

Basically， add instruction operates on two registers。

 a load instruction will load a value from a memory location。

 load from this address in memory into this register。😡。

And then you may have a store instruction that says， take the data value in this register。😡。

And store it into this memory location。So all of the instructions that we will see will operate on these entities which are visible to the programmer that's why this is so important and that's why I'm spending a lot of time on the slide。

 this is the architectural state visible to the programmer。😡。

We will also see instructions that operate on the program count。Actually。

 all instructions operate on the program counter whenever you。Fetch an instruction executed。

 you go to the next instruction， you increment the program country in other words。😡。

But then we're going to do a more sophisticated thing to the program counter because。

Executing sequentially in a program is not that useful， right？

 Sometimes you want to do something else in a program based on some data value。 For example， you say。

 if this data value is greater than5， I execute this code。 if this data values。Smaller than five。

 I execute this other code right So you do some conditional action and if all you're doing in a program is actually going sequentially by incrementing the program counter。

 you don't have that。 So we have we'll introduce branches or control flow into the program that take the program counter。

 change it to a value which will take you to the right place in the program。😡，Does that make sense？

If you want to take secure function call， for example， you program with functions。

 I want to call this function that requires changing the program counter to the value to the address of the function essentially。

😡，And function is essentially a sort of instructions in memory somewhere that you can jump to using by changing the program card。

😡，Okay， so we've covered the one Neman model， at least at some basic level。😡。

Let me give you two other properties of the Wo Neymo model that I kind of implicitly suggested。😡。

It's also called as stored program computer instructions are in memory essentially it has two key properties。

 when it stored program I'm going to define it a little bit nicer and the second is sequential instruction processing which kind of I kind of harped on earlier。

😡，So essentially stored programming means instructions are stored in memory in a linear array。😡。

Memory is unified between instructions and data。 So there is no distinction basically in memory between instructions and data。

 the interpretation of a stored value depends on the control signals whenever the processor is actually。

Accessing memory in what part of the instruction cycle， as we will see soon。Okay。

 this may be difficult to understand right now， but it'll become clear soon。

 hopefully let's talk about sequential instruction processing。

 this is easier to understand you basically have one instruction process fetched。

 executed completed at a given time。😡，Program counter instruction pointer identifies the current instruction or when it's incremented the next instruction and this program counter is advanced sequentially to the by being incremented except for control transfer instructions which are branches or jumps as we will see but it's very sequential and this is part of the success of the one model whenever you write a program you write a sequence of commands and you expect that。

😡，One instruction in the sequence is executed first before you go to the next instruction before you go the next instruction and this enables a lot of things like easy debugging。

 easy thinking about how things are performed yes why is memory slower than the register。😡，嗯哼。😊。

Because largest is slope。If you have large memory， let's say two to the 48 locations。

Imagine based on what we have discussed earlier in earlier lectures。

 how big of a decoder do you need？😡，How big of a multiplexer do you need how big of an array do you need like all of them are larger and based on the timing and verification lectures that requires a huge amount of combinational logic to the delay is much larger right if you have only eight registers your decoder is much smaller your multiplexer is much smaller your array is much smaller so your access times are much slower。

😡，Okay， very good question because there's no magic basically we built up to all of these right， yes。

That's a great question I'm not going to answer that question meaning that's an important question what is stored in the registers versus what do you put into memory that's the job of a good programmer essentially everything can be in memory you decide not to use the registers your program will be terribly slow。

Today's compilers do register allocation， essentially what today's compilers do。

 they do some locality analysis in your program， they try to figure out automatically which variables should be stored in the registers next to the processing unit and they do the registergi allocation。

😊，If you're programming with a nice high level language， with a nice compiler， et ceter。

 if you're programming in assembly， you're on your own。

 you'd better do the register allocation yourself。😡，Makes sense。Very good question too。

These real issues will come up in the memory hiarchy again and again， what goes into the cache。

 what goes into the other cache， what goes into the other cache。

 who brings the data from one cache to another cache right we're going to see that in lectures 20 plus。

😡，But we are getting there， but we just introduced the registers。Okay。

 so these are the two key characteristics of the Wal Neman model that you should never forget。😡，Okay。

 now let's go start building a one moment machine， and I'm going to start with LC3 because this is easier。

 I think， and your book Patam Patel book does a great job explaining how this operates。😡。

I think for this part of the discussion， I would definitely recommend the Patam Patel book。Okay。

 so this is another one Neman machine， a lot of components are one Neman and basically what we have is all one Ne machines today。

😊，This is the LCC3 Wo Neman machine， and you can identify different parts。😡，This is the control unit。

 These are the control signals。 Let's just to a you with what is coming next。😡，We have data。

 data is marked with black edged arrows over here， control is usually marked with white edge arrows so that you can distinguish between control signals and data。

😡，This is memory 16 bit addressable， and you can see the MAR and MDR over here。

 memory address register and memory data register。😊，You have a keyboard and you have a monitor。

 you have different registers for those that we're not going to go into but you can read in the book there's an ALU two inputs。

 one output there's a register file fast temporary storage eight general purpose registers。

 you have two registers you can read concurrently from the register file。

There's an instruction register， as we have discussed。

 this stores the current instruction that's being processed。😡。

There is a program counter that towards the address of either the current instruction or the next instruction。

 depending on where you are in the instruction cycle。😡。

There is the finite state machine that generates the control signals that takes input。

 that takes us input the instruction registerist， it looks at the bits on the instruction it says。

 oh， I need to orchestrate things such that this ad is done right and we're going to see some of that。

😡，They're the clock。This is a synchronous machine， as we have discussed in the past and this control signals。

 one of the control signals that's generated is the ALU operation。

 what should the ALU do to process this instruction right？

And then there's another thing that tristate buffer。

 if you remember triSt buffers from the combinational logic lecture。

 this triSt buffer is used to place the result coming out of the ALU onto this huge thing called the system bus processor bus in this case。

😊，So that the result of the ALU can be potentially put to memory for example or can be potentially put to the register file and then there's a signal coming from the control unit that controls the tri state buffer so that if you generate the control signal at the right time when the results is generated and you put the results somewhere else we're going to see all of these soon and that's the processor bus so we're going to build up to this machine but I'm going to give you examples first on how the instructions are processed。

😡，Okay， we've already discussed this instruction and data are stored in memory typically the instruction and I is the word length。

 the processor fetches instructions from memory sequentially， it fetches one instruction。

 des and executes the instruction， continues with the next instruction after that。😊。

So the address of the current instructions is stored in the program counter。

 and then you implementedcrement it at some point while the instruction is being processed。😡。

If you have a word addressable memory， the processor increments the program counter by one because instructions is one word and then you keep incrementing the program counter if you have byte addressable memory。

 the processor increments the program counter by the instruction length in bytes we're going to see by four because your addresses are referring to one byte and each instruction is four bytes so if you want to go to the next instruction you increment the address by four right as opposed to by one。

😡，So there are some interactions with the operating system also that we're not right now going to talk about。

 but there should be a way for the system software to say， oh， start this program to the machine。

 we're not going to talk about those interactions yet。

 the system is actually more complicated than what we're going to look at today。

 but the operating system for example， when it starts the machine when it sets up the machine after the machine is reset it points the program counter to a particular location in this case that particular address that MIPS designer decided to say that's where the program should start basic。

😡，Let me give you this and then we're going to take a break so this is a sample MIPS program you have four instructions stored in consecutive words in memory it's essentially assembly code so if you take the MIPS ISA MIPS ISA would specify what these are to you。

😊，This a load instruction， this an add instruction， this an add immediate instruction。

 this is a subject instruction， Hopefully we're going to see a lot of these。😡。

There's no need to understand this program now， we will get back to it。😡。

But this program is not what the machine sees。😡，What the machine sees is。This。

And quoted instructions。So there needs to be a way of encoding this because this is not what you store in memory right in the memory that we design we store bits zero than once。

 there's no L， there's no w， there's no t2， there's no any of that right there's an encoding that needs to happen such that in memory we have the sequential set of instructions。

😡，Makes sense。So all the instructions and architecture， that 4000 page book， in part。

 specifies what that encoding is。😡，If you want to specify a load word or an ad if you prefer， okay？

Then you encode it this way。 So we're going to see that encoding in the later part of this lecture。

 and this is important so someone needs to do that encoding in the past humans did that encoding today。

 compilers do that encoding right because this is actually easily automated In memory。

 this is what you see。😡，This is what MIPS memory looks like。 These are the instructions。

And lower is lower address in this particular case I show you by the addresses over here。

 so you can see that the first instruction is that this address for blah， blah， blah。

 the next instruction is that address plus4， the next instruction is that address plus8。

 the next instruction address plus four well plus four from the previous one essentially。😡。

And you can see this is what we store in memoryme， each of them is four bits。

 and you have eight of these four bits， 32 bits instructions。😡。

Initially the program counter is set here and the machine fetches this instruction。

 puts in the instruction register and executes it。😡，Once it's done。

The machine goes to the next program counter， meaning increments to program counter and fetches this instruction。

 puts it into instruction， register， des it and executes。😡，And it keeps doing that essential。Okay。

This is a good time to take a break。 Let's be back when the bell rings and then we're going to see this instruction processing cycle and then we're going to see the entire ISA hopefully soon。

😊，不诉。F。然后月是加一。暂时没吃。就这。是。对。嗯。嗯。我开。好现的。嗯。哦。是。嗯。Different in the space and that's。一个小分。我事再见。对同觉。

你 comes down full。说明要求是。你没什么粉。那。嗯，对对。我要家要收闭特点。刚这个词。我。Okay this。I谢。5第2的3。Yes。嗯。诶 what你对对。嗯。我早啊。Action。

Yes。The of。今天在。W不到是下。不个做死。这C。たです。反我。这公司。一。あ公です。第二个是。嗰啲钱量交。跟别样第个。This， this is good。你你这些。打。言でこ。我面啲咧个做。

对啊。B is even0。但0可。你。えどう？但是。It3 my I30 this I3 Do film for a good。嗯。In。你怎知道这情况还是还有就。So we can see how。

标志反到标志有。嗯有。I believe that can do。是。最包。And get that kind of sp。也。有。啊。啊就一个。对对。还是是单。我解个解时。

That those will be his。That's。也个。Just。It is。现在。Let's go for。啊 time all the time。Yes。S。我给他们2就别取消。对，对。

这子。也就是。3。系点。嗯，你现在班这样。It关接亮。What stop。Those啊。当。我知道。That's the movie she said。嗯清。在那。

Could be still and China。Lets。的时间。Let's。嗯。Yeah。う。不是。That' the big。这个大时。one我。这也是。那死人不有你都我说。

你基本诶就不作佢啲嘢个。佢切两是唔知。Yes。Exceent。在的公司。对对。诶。嗯，说这。Aman bus。では。我道。Yeah。はいですか。最生？No。好。🎼嗯。🎼Yes。🎼The。🎼我去。

Okay。为了。あ。有情。Yeah。3。好ね。Yeah。Okay。Let's get started for the second part of the lecture。嗯。

This was a slide where we finished now we're going to talk about instructions and we're going to get to the details of each of these instructions that may be of interest and we're going to talk about the instruction processing cycle and we're going to map these instructions a little bit into this picture that I showed you earlier of the Wo Neman machine。

 I should say that this is one particular implementation or micro architectureitecture that implements the LC3 ISA we're going to go a lot more into depth of this and some other micro architectureectures later on。

 but this is one way of implementing things。😊，This is not the only way there could be thousands of different ways of implementing things。

 this is a nice and clean way that is relatively simple。😡。

We're going to get to different ways of implementing later on that'll start next week。 Okay。

 now let's talk about these instructions。Essentially。

 instruction is the most basic unit of computer processing。😡。

Instructions are the words in the language of a computer， hardware understands these instructions。

 instructions that architecture is really the vocabulary of that language。😡。

So I could imagine different ways of designing the。

 like any other computer language or human language。

 there are many different ways of communicating information， right？😡。

The language of the computer can be written as machine language。

 this is the computer readable representation ones and zeros， which is basically what I showed you。😊。

Over here。These are not ones and zeros， but they're grouped into four bits each。

 this is the hexetademal notation， right？😊，They're basically grouped ones and theos。

 and then theres the assembly language， which is the human readable representation。

 which is essentially something that looks like this， right？😡。

Well not as human readable as a higher level language is right you could actually become more and more human readable right and at some point you don't need to read also you just speak and then things get translated into these things right today where the point where that is possible except maybe that's not perfectly good at this point yet okay so think about that so we will study LC3 instructions and MIPS instructions。

😊，These are it's good to study different instruction of architectures because fundamental principles are similar。

😊，But I don't want you to take away with just one ISA。

 it's good to know different ways of doing things because by contrasting some simple differences。

 you can really understand the trade offs much better if you just studied one architecture than you may not be able to see some of the trade offs that I would like to highlight a lot of things will be similar though。

Prciipples are essentially similar on other ISAs as well， like X86 arm risk 5。

 which are the dominant ISAs that exist today。Okay， so instruction is made up of two parts。

 up code and up， which is very fundamental what is an up code and up code essentially specifies what the instruction does or should do operation code in other words。

😡，All parent specifies， specify who the instruction is to do it to， basically。

 what are we operating on， right？😡，Both are specified in the instruction format or instruction encoding and we're going to see that specification。

 for example， an LC3 instruction encoding consists of 16 bits， that's the word size。😡，In LC3。

 each bit means something as we will see， so this is one example。😊，This is a 16 bit representation。😊。

This is the up code 0001 is the up code for an ad how do I know that I look at the LCC3B ISA manual it says that or LCC3 ISA manual。

 it says that if I want to write add in machine code。

 I should have the top four bits up code be 0001。😊，That way， someone。

Some hardware designer can design hardware that decos that and once you use a decoder。

 a 4 to 16 decoder， you'll figure out what instruction that is right so we have built these components。

😡，And then the next three bits specify a register， the next three bits specify another register。😊。

The next three bits should be zero and the next three bits specify another register。

 so this is one instruction in LC3 and we will see why it looks this way。😡。

So basically upcode is specified as the top four bits and therefore are 16 distinct up codes in LCC3 because four bits you can specify to to the four distinct values right we know this this is bread and butter for you right now and if you want decode this you use that decoder that's also hopefully becoming bread and butter for you。

😊，Bits 11 and 0 are used to figure out where the ups are， the remaining bits and。

This is we're going to call these addressing modes but basically how do you figure out where your upend are where your source registers are where your destination registers are in this particular case ad specifies because these four bit bits are at you're going to do an ad。

😡，It turns out because this bit is zero， these three bits are interpreted as a source register。😡。

We'll get back to that。 if this bit was one， these five bits would be interpreted as an immediate value over there as opposed to a register。

 So this is one of your source registers。 this is another source register and this a destination register So this。

Encoding specifies that we should do an ad。😡，And we should add the value in r6 to r2 and store the result in r6 these are general purpose registers so this end quoting specifies that you just need to build the machine。

 build the logic that does it and we're going to build up to that and we're going to give you the key parts today。

😡，Okay， so that was an ad， but there are different instruction types and there are three main types of instructions。

😡，Operate instructions execute operations in the ALU。Data movement instructions。

 read from or write to memory。Also， implicit and， operate instructions use reries。

Because registers are a critical component of this ALU， next ALU， right？😊，Okay。

 control flow instructions change the sequence of execution。

 Hopefully we're going to look at all of them today， but we're going to go into more detail。

So let's start with some example instructions this is an example of instruction right high level code is's not an instruction yet a equals B to b plus C you could use your favorite programming language declare your variables。

 you can say a equals B plus C right it's possible to do that。😡。

Assembly could be like this in this case add ABC A is the destination B is one up C is another up。

 this is not exactly low level assembly because it doesn't have the registertry allocation done yet these are variables ABC。

😡，Ad is called a p mnemonic to indicate the operationpatient to perform。B and C are source ofs。

 and A is the destination of。So that's the semantic specification of this assembly， right？

Now you need to map the variables to registers so this is the assembly in LC3 somebody needs to do that register allocation human can do it compiler can do it let's do it as humans and as human I decide B should be registered one C should be registered two a should be registered zero MIPS as a different kind of different way of specifying registers。

 but it's essentially the same as one as two as0 okay。😡，就。Now we mapped the variables to registers。

 this is what an LC3 instruction looks like after you do the register mappingping to the variables。

 add R0 r1 r2。😊，R0 is the destination。Destation， depending on the convention。

 destination can be on the left， destination can be on the right。

 but our convention is destination is on the left。😊。

So let's look at the field values if you want to specify this。

 you go to the manual and the manual says an addd up code is one。😊，And we're adding two registers。

 so this should be zero and these two should be zeros also。

I don't know how strict the manual was on that， but that's how it is and this is source Reg2 it's two。

 this is source Reg one which is one， this is destination register zero so if you look at the instruction and quoting these are exactly what 16 bits are。

😊，So each bit you can specify that's the machine called essentially it's essentially what I said over here where each bit is put into its place。

😊，So this is our encoding， you can also write this in hexadeciimal。😊，So you write this in Ex SM。

ll put it in memory when the program counter gets to it。

That instruction gets executed when the program counter program counters the address of the instruction to execute if you remember earlier things that I said。

 essentially that instruction this instruction specifies that an addition should be done on register one and register2 and the results should be stored and registers zero okay I'm going through this around really slowly because we're going to do more of these soon。

😊，So that was our instruction format basically， this is our instruction format and encoding LC3 operating instruction format is actually very general。

😊，You have an up code four bits in the top four bits， bits 15 through 12。

 these are the most significant bits。😡，And then you have the destination register and then the source register。

 these three bits are always set to zero， and then you have the second source register over here。😊。

So up is up code what the instruction does or should do。😡，For example。

 addop quote happens to be 0001 because whoever designed the LC3 ISA said that should be sold。😡。

And up code is actually 01，01。😡，Okay， SR1 SR2 our source register is D R is the destination register。

 Okay， so the semantics of add is DR gets the value or。Value of SR1 plus SR2。

 basically the data value in SR1 gets added to a data value in SR2。

The result gets stored into a destination register， like ADR。Semantics of end is very similar。

 it's not at， it's essentially an ant logical bitwise ant operation， okay。😊。

And this is one example where we actually looked at this in this case you do an addd r2 plus r6 and the result goes to R6 so source and destination register can be the same right you can overwrite the source register after you produce the result。

😊，O。So this is add and MIPS， it's going to be very similar。😡。

You add S1 to S2 and store the result in S0。 These are the field values。

 They look a little bit longer。 I'm going to look at the machine code directly What what this does is basically RD destination register specified over here gets。

RS plus RRT in this case you basically it turns out SC or S1 and S2 R 16， 17 and 18。

 there's a Mac also over there that is done， but don't worry about that right now。

This thing specifies that you should add Rs Reg 17 to register 18 and store the result in Reg 16。😡。

Okay， this is the machine code， the instruction encode up code is zero。

 this function is actually very important because it's an extended up code。😊，So in MIPS。

 things are a little bit more complicated， as you can see， instructions are 32 bits。😡，Longer。

 there are more general purpose registers， so you need morebis to specify them。😡，Five bits each。

 so you need 15 bits to specify two source registers and one destination register。😡。

And your op code is， as you can see， six bits， and then theres function。 that's also six bits。

 It turns out that's an extended op code。You need more operations than a real ISa。😡，Okay。

 and that's the encoding。Okay， now this is the art type instruction format。

 so you have three restr prints。😡，Z is the up code。😡。

Our S and RRT are the source registers that's where they're placed in the end quoting because somebody decided that it should be so。

😡，RD is the destination Reg。Shamamp you don't need to worry about that it's a shift amount for only four shift operations you may see that later on F is very important this is operation our type instructions basically our type instructions are operating instructions with register with register values they operate on registers zero is always the up。

😊，Funk is the extend up code， it tells you what really you should do zero doesn't mean anything in a sense。

 zero means you should do something to these registers。😡，Fk means whatever you're going to do。

 meaning it's an up also， okay， we're going to look at that later on。😡。

Okay with operating instructions such as addition， we tell the computer to execute arithmetic or logic computations in the AL we already said that actually。

 but we also need instructions to access the opera from memory if everything was in registers you don't need anything to access memory with but registers are small you need actually large amounts of memory for storing data so if we need to load data from memory to registers I need to store data from registers to memory I need instructions to do that and so far we have not looked at that yet。

😡，So we're going to see that soon， read how to read or load from memory。😡。

Writing is performed in a similar way， but we will talk about that later。

 Writing is exactly the opposite action。 So let's take a look at load work。 This is high level code。

 This is an array operation。 You have an array at base I A and I is the Ih element in the array。

 How many people are programmed with things like this。 Okay。

 good How many people have not programmed with things like this。😡，Okay， good。

 I am not surprised you should you should have program with things like you're basically accessing eye element in this array and then。

😊，I'm assuming the array is stored in memory， assuming it's a huge array， right？

Later we will see models where things can be stored in registers like GPUs。

 some folks ask questions about the GPU execution model。

 wait until lecture 16 or so or later actually， even later。Okay， so this is the assembly。

The destination is are variable a。😊，I'm going to have a base address a and an index I and this assembly says load from that base address。

 calculate an address into the actual location indexed into this array from this base address。

 get the data from there， put it into variable a， and we're going to map the variable to our register。

😊，Load is mnemonic to indicate the load word operation and in this case it's a load word。

 meaning get a value of size word 32 bits in minutes。😊，A is the base address， I is the offset。

 this is also called it immediate or literal， essentially it's a constant。😊。

A is the destination opera destination variable and the semantics looks like this。

 I already said this basically。😊，Okay， so let's take a look at how this is encoded in LCc3 and MIPS3 assembly looks like this in this case index is two and this is the assembly we have a load register。

😊，LDR upcode。You this is a register zero stores a base address a。

 and number two is encoded in the instruction， this is a constant encode quoted in the instruction specifying what is the index and this is destination register。

Okay， and this is the semantics basically， you take the value in R0。

 which is hopefully a add two to it。Calculate the address， go to memory， get the data。

 place the data into register3 okay so if you look at MiPS assemblyly it's going to be very similar essentially the same code the same high level code translate into a low word instructions the syntax is a little bit different but it's essentially the same thing right what we do is this。

😊，The base address is S0 we get the value over there， add to a two and access memory。

 get the data put the result into destination， register S3 okay this is assuming that MIPS is word addressable I'm going to look at a byte addressable version of it we're going to multiply that two by four basically that's what's going to happen because if your byte addressable your word is essentially each element assuming your elements are word sized each element is four bytes right okay so these instructions actually happen to use a particular addressing mode we're going to study addressing modes later today or tomorrow the way the address is calculated addressing mode is also specified by the instructions at architecture。

😊，Tells you how do you calculate the address in this case。

 we calculate the address using and addressing mode called base plus offset。

 we have a base register and we add an offset to it and the offset happens to be an immediate meaning a constant specified in the instruction。

😡，Okay。Now let's take a look at load word and biodireible MIps。😡，This is high level coach。No。

 there's some film coming。Okay， so basically MIPS assembly of this code is assuming you have word sized element in this array and your memory is wide addressable in order to access element two。

 you need to multiply the offset by four right two times 4 is eight。

 so my offset is going to be eight over here。😡，And that's how I access the second word in a wide addressable memory。

Basically， by addresses calculated as word address times bytes divided by word byte divided by word bytes in a word in MIps is four。

And we are discussed that if LC3 were by the addressable。

 you have two bytes per ver and you would multiply it by two essentially and you will see that later on。

😡，Okay， now let's encode this， these are the instruction formats with immediate for LC3 and MIPS。

 as you can see they look very similar， I look at the byte addressable version of MIPS because MIPS is really byte addressable。

 that's how the ISA is defined。😡，LC3 is word disable， that's how the ISA is defined。Okay。

 and these are the field values now you can see there's a different kind of format up quote in LCC3 is6 specifies LDR destination register is three。

 base register zero and there is a six bit offset field over here with a six bit offset field you can easily encode two right and you get two over here。

😊，So this is the I'm quoting basically， we use all of the bits over here。😡，In MIPS。

 it looks like this。Yeah， the upcode， it happens to be 35。😡。

You don't have funt because Op code looks like this， the rest of the instruction looks like this。😡。

Meaning you have a source register。You have a destination register。

So0 happens to be 163 happens to be 19 in mapPS and codingding and immediate as huge。

 16 bits as you can see， and that's eight。So basically， this is the encoding of this instruction。

 it's called an i type immediate type instruction， which means that it has a 16 bit immediate value。

 half of the instruction is dedicated to encoding a constant value。😊，Does that make sense？Okay。

We're going to see more of these soon。 we're just studying the en quoting right now。Okay。

 so hopefully this gives you an idea of how instructions are encoded。

 we're going to see more of these encodings， but before we do that let's let's see how these instructions are processed a little bit because we're going to tie the encoding to the processing also Su。

😡，Okay， we're going to introduce the instruction processing site。😡，Or instruction cycle。

This is not to be confused with。The clock cycle。It has nothing to do with the clock cycle。

 It's really all the instructions are processed in the machine。So basically。

 how are these instructions that be encoded， yet executed？😡。

Now we can speak the language of the computer because we encoded things in a way the computer can understand and the computer can decode them using a lot of decoders。

😡，Which you have seen。So we know how to tell the computer to do things like execute computations。

 the ALU by using， for instance， an addition instruction。

 access operates from memory by using the load word instruction。

But how do these get executed on the computer so the process of executing an instruction is called an instruction cycle or instruction processing cycle。

 I like the second one better instruction processing cycle because you're a processing instruction it's called the cycle because you keep doing this repeatedly。

😡，Okay， so basically every instruction goes to a sequence of steps or phases。😡，To be executed。

And these are the general cases。Fettch， decode， evaluate address， fetch or。

 execute store result these phases may not may not be needed in every instruction。😡。

Not all instructions require all the six phases， every instruction needs to be fetched。

 you have a program counter， you need fetch the instruction。😡。

You get the data bits of the instruction and then you need to decode the instruction to figure out what the instructions is telling the machine to do and then you need to evaluate the address so that you get the ups and then you fetch the ups。

 you execute the instruction by doing something to the ups and then you store the result。

 but not all instructions require everything for example， load。😡，Register does not require execute。

 right？You fetch the off。 You fetch the off from Memy。And put it into a register。

 destination register。 There is no operation that you do， really in the ALU for that。

 as you will see later on。Ad doesn't require evaluating a memory address in this case evaluate address implicitly means memory address。

 you don't have at least in LCC3 and MIPS， you don't have ad instructions that directly operate on memory。

 all of them operate on registers。😡，Okay， this is good to keep in mind。

It's also good to keep in mind that this is not the case in every single ISA in the world。

People have imagined many different things。 X 86， for example。

 has instructions operating instructions like a。That operates on memory values， Regstry values。

 you can in x86， you can specify。😡，I want to add the data value in this memory location to this register and store the value in some other memory location。

😡，Okay。This enables you better expressibility， you don't have to do things only in registers and then put the value into memory。

😡，You can directly operate in the memory locations。Without bringing the data into the registers。

 and there could be value to this， as we will see in later lectures。😡。

But we're not going to see ISAs and you're not going to implement ISas like this in your labs。

 for example， but this is an example instruction in X86 that says。😊。

Yet this EAX is a register if you use it in an address， you access the memory location。

 get the data value in that memory location add to it the value in the EDX register and then store the result into the memory location that's addressed by EAX again okay so source and destination are the same in this case again you don't need to understand this but there's no one single way of doing this and the benefit of doing operations directly on the memory locations is you don't need to waste register for example you just need to add something to somewhere in memory you don't need that value again。

😊，Remember， registers are very small， precious， you want to keep things that are being used over and over inside your register file。

 but you just want to increment some random location in memory because you're keeping count somewhere once in a blue moon。

 just do it in memory， don't bring it into a register。😡。

So there are good reasons why people add these things into the ISs。

 but they do complicate the ISA also they do complicate the implementation in the end。Okay。

 so after you store the result and if happens， basically， that's why thiss called a cycle。😡。

Now we're going to go through each of these stages。Does that sound like fun？Okay。

 you're already having fun， I can tell， okay， so Pe face。😊。

So this phase obtains the instruction from memory and loads into the instruction Reg I kind of said that actually earlier。

 but every instruction has to go through this。😡，The complete description looks like this actually。

 I'm going to show you a picture also you load the memory address register with the contents of the program counter。

 which is the address of the instruction， as you know。😊。

And simultaneously increment the program counter because you're going to go to the next instruction later at some point。

😡，And then you access memory or interrogate memory as used by Ha and Patel memory returns the results。

😊，呃。Into the MDR， basically by interrogating memory， what the memory does。

 it takes the address and memory address register， accesses itself and puts the data into the MDR。😡。

What is data， these are the contents of the instruction， right。

 because we're accessing memory with the program count。😡，Okay。

 and then you take the data that's put into the MDR by memory memory data register。

 put it into the instruction register。😡，Does that make sense。

 so there are three steps to get the contents pointed to by the program counter。

 which is the address of the instruction that you want。😡，Eventually after these three steps。

 the instruction that you want at that program counter at that memory location gets placed into the instruction register now you have the full content of the instruction you fetch the instruction。

😊，What we have done in other words。Is we have interpreted。The address， the program counteror。

As the address of an instruction， because we're accessing memory in the fetch stage。😡。

Now we're accessing memory using the program counter in the fetch stage， putting the。😡。

Data that's coming out of the memory into the instruction register。

 we're interpreting the data at that location as an instruction， right？😡，Okay。

 this is going to be hopefully clear later on because we're going to access memory in some other stage also。

 we're not going to put the data into the instruction register。😡。

Just because we're in the fetch stage of execution。

 the control unit is putting the data value coming out of memory into the instruction register。

 so we're treating that data value in memory as an instruction。😡，O。

Okay let's take a look at how this is done in this high level picture microarchit of LC3 so step one。

 you load MAR and increment the program count what do you load the MAR with you basically take the program counter so there's some program counter over here there needs to be control signals set accordingly in this stage so there needs to be a finite state machine controlling this as we will see also soon the finite state machine says I'm fetching the instruction I'm in the fetch face so I'd better set the gate PC signal to enabled so that the value on the PC gets gated under the bus remember the tri state buffer。

😊，That value flows on the bus。And I'd better。Take set the enable signal or load MAR signal to be one so that whatever flows on the bus gets placed written into the MAR register load MAR means write enable。

 it's essentially a right enable signal for MAR。😡，So， now， we've kind of。

Put together all of the concept that we've seen earlier， we have a register PC， we're gating it。

 its value using a tri state buffer onto this wire bus。😊。

And then we're right enabling the register where we want the address to be placed into the may。

That could take one clock cycle， okay？Don't worry about clock cycles right now。

 this is these are steps。😡，Okay， and then there's another step where we access memory and at some point memory accessing memory happens by it basically takes the address and the MAR。

 which is essentially the program counters value， accesses itself using the decoder。

 all of those bits， multiplexors at the end， and the data that you need eventually comes out in the MDR。

 the word， the instruction word。😊，Of course， you need to set the load MDR signal to be1 so that this MDR gets written into。

The third step is once that is done， you load the instruction register。

 which happens to be over here with the content of the MDR to be able to do that。😡。

We need to have a path from MDR to IR and that path already exists and the finite state machine。

So you can think of these as three different states and finite state machines， state one， state two。

 state three， finite state machine in this state enables MDR signal gate MDR signal to be 1。

 such that the value in MDR goes on this large bus that we call the processor bus。😊，It also。

Write enables the instruction register or low DR， as it's said in this book。

 such that the data value that's coming out of this processor bus gets written into the instruction Reg。

O。😊，So now， hopefully。You kind of connected the dots。

 everything we have seen previously enabled what we have done over here。

 we're now able to fetch an instruction using both sequential and combinational logic and a finite state machine that I didn't show you。

 but you could imagine that finite tape machine I'm going to show you that later on in one state you do this and then you move to the next state。

😡，In the next state you do this。And once the memory says I'm done， you move to the next state。

In the next state， the finite take machine does this， so after three states。😊。

You get the instruction that you want Okay， so all of this is done using sequential and combination logic together。

😡，But of course， you needed to design the machine to do that also。Sounds good。Okay。

 so that was fetch。We're going to see more of this later on let's talk about decocode now you fetch the instruction the contents are in the instruction register the decode phase does what decocode means we decode the instruction identify what the instruction is and what we should do afterwards right it also generates essentially what we should afterward means it generates the set of control signals to process the identified instruction in later phases of the instruction cycle basically it determines your next states in the finiteate machine if it's an ad I execute the sequence of states if it's a multiply I execute this other sequence of states if it's a load I execute this other sequence of states in the finite state machine right okay we're going to see that finiteate machine so basically we're going to use a decoder。

😡，So in this case， we have four bits up code and LC3 and a4 to 16 decoder identifies which of these 16 up codes is going to be processed。

😊，So the input is four bits， the top four bits of the instruction register because we were fetch the instruction for Meme and the remaining 12 bits identify what else is needed to process the instruction based on those four bits。

😡，Okay， so let's take a look at Decode， we're not going to see a the whole lot here。

 but basically we identify the instruction to be processed。😡，Essentially。

 the top four bits of the instruction Reg goes through a decoder and essentially affects this finite tape machine that we're going to see later。

😊，It also generates a set of control signals to process the instruction later， for example， it says。

 oh， I should go through these states next。😡，We're going to see this more。But that's thecode。

 actually， I identifying't find the instruction and generating control signals for what should happen next。

In the future， because I have fetched this instruction， right？Okay， first on decoded。

 so you can see there are a lot of control signals over here we will demystify this picture later。

 I don't want to go into a lot of my architectural detail right now。

 but you will see a lot of this later and you will see different kinds of control logic。😡。

Okay decoder hopefully you remember again there's no magic over here a4 to 16 decoder is identifies what instruction you're executing and remember I said that the input pattern could be the instruction in the program and the processor needs to decide what action to take pages on the instruction up code hopefully now it's much more clean so this is the full finite take machine I don't want to scare you but this is L3D actually which is quite addressable it makes sense it's slightly more complicated you can find this online。

😊，We should also upload it into Spring 2025 website if we haven't done so。

 but just to show you these stages that we talk about， this is the fetch face。

If your finite state machine is here。😡，What you do is you generate the control signal such that PC gets loaded into memory address registers。

 And concurrently， I forgot to say this in the picture。 Sorry， concurrently。

 you increment the PC by2。Because you're going to go to the next instruction later at some point。

 right？😡，You could do this later also somewhere， but they decided to do it in this state。

And then unconditionally， you jump to next state， remember in finite state machines。

 we have the next state logic。😊，After one clock cycle unconditionally you go to the next state okay unconditional and the next state memory uses the memory address register to access data to access data from itself and places the data into the memory data register and stays in the state until the ready signal is asserted if the memory is not ready meaning memory access may take a long time。

 it's actually an analog process as we will see later on， analog plus digital process。😊。

Memory starts there ready signal once the data is placed into the MDI。😡。

And you go to the next state only when memory does that and the next state memory data register gets loaded into the instruction register so this is our fetch face and this finite state machine controls all of those operations as you can see again there's no magic we've seen finite state machines。

 we've seen logic。😡，This is the controller that we have next phase is decocode now what's happening over here is again unconditionally you go to the decode stage theres some stuff that we're not going to talk about right now。

 but based on IR 1512 over here。😡，You decide where to go in the finite state machine。

 the next state is determined by the up code， right？😡。

And each of those up codes have a different thing to do， for example。

 if the up code is at in the next state。😡，You do this。You add SR1 to SR2， store the results in DR。

 and then you go to state 18。Which happens to be the fetch face right so you've got the next instruction basically and you've already incremented the PC。

 you fetch the next instruction。Does that make sense？

So this is the operation of an entire LC3B machine。which is a simple machine。

 existing machines you can specify as so a processor over here， it is also a finiteate machine。

 it's a much more complicated finiteate machine， but it is a finiteate machine。😡，Okay。Okay。

So that hopefully is clear the next phase in execution is evaluate address phase。

 this computes the address of the memory location that is needed to process the instruction。

 so this phase is necessary in LDR because it requires access to memory and you need to evaluate the address that you need to access。

😊，So in LDR， you need to compute the address of the data word that is to be read from memory。😡。

By adding an offset to the content of our register， if you remember， based offset addressing mode。😡。

This is not necessarily an ad， so ad doesn't have a state。😡，In the finite S machine for this。

 So if you look at the finite S machine， ad doesn't evaluate its address。

 It just takes a star1 S R2 does something。Where's LDR？This is testing my eyes。

Now while this is LT3B， so there's an LDW， which is same as LDR， it does some address。😊，Evaluation。

 this is the E address state。Okay。Okay。So not necessarily not。

 so let's take a look at this in the micro architecture LDR calculates the address by adding a register and then immediate to each other。

😊，This is a specification if you look at this， you have a base register。😊。

And you have a sign extended offset， we're going to see this later more and more。

 but basically you need to take the register value in the state from one of the registers and then you need to add to it the bottom part。

 bottom six bits。Coming from the instruction register， and you need to put that into the MAR。😡，Okay。

 so that you can access memory now where you can access memory with that。

 so I've added that adder because you needed it in this particular case。

 it'll become more and more complicated that adder， we will see that in the next lecture。😡。

But this is not magic again， You can imagine building this and it's not that hard to build。Okay。

 let's talk about fetch Opera， Fe Opera phase obtains the source opera needed to process the instruction in LDR now we've calculated the address。

 you put the you load the MAR with the address calculate in the evaluate address stage。

 you read the memory which place the source opera in the memory data register。😡，In At。

 you obtain the source of append from the register file。😡。

In some microprocesors open fetch from Reg file can be done at the same time。

 you're decoding the instruction that's also possible LC3 micro architectureitecture that's discussed in Pat and Patel doesn't do that。

 but we're going to see that later on also when we build pipeline processors or when we build one of our Mi processors you will see that okay let's take a look at fetch opera quickly in LDR again the step one is。

You take the you load MAR with the address we calculated earlier， let me just jog your memory。😡。

We calculate the address over here， that address needs to get into the MAR so in the finite state machine。

 you need to set the control signal load MAR to be one so that the address that you calculated。😡。

Get loaded over here。And then you do the ME access， which is very similar to the fetch state。

 except it's a different state。😊，Because now we're treating memorymi as a source of data that will be used as an off as opposed to as a source of instruction that will be placed into the instruction register。

 right？😡，Okay， so now the data comes to MDR and that will be placed somewhere later on。

 but we'll talk about that。😡，Execute phase， executes the instruction in add。

 it performs addition in the ALU in XO， it performs it by XOR in the ALU， etcter。😊。

It happens basically add， let's take a look at ads ads SR1 and SR2 in the state。

You set the control signal such that you access the register file， the data comes。😡，Through the ALU。

 so you have SR1 and SR2， there are some control signals that make sure that both of these registers go to the inputs of the ALU and the ALU operation is at。

 these are all control signals。And the data comes， the result comes out of the ALU that needs to be gated。

 meaning this tristate buffer called gate ALU should be enabled such that the result gets put onto this wire processor of your bus。

😡，And later in the next phase， it's going to get stored into the register file。😡，Makes sense。

 I'm kind of breaking the phase， but these may actually be complete in a single cycle。😡。

These phases have nothing to do with clock cycles， as I said earlier。

 one particular two multiple phases can be collapsed into a single clock cycle。

 a single phase can take many clock cycles like fetch itself takes at least three clock cycles right？

😡，But here， execute and store result actually happens in the same clock cycle for ad instructions。

 okay， store result， this phase writes the result to the designated destination。😊。

So once store results is completed， a new instruction cycle starts with the fetch face。😡。

So let's take a look at store result loads the ALU result into ER。

 so our ALU result was gated onto the processor bus。

 and then you need to set the control signals such that you write enable the destination register and you have the destination register ID coming from the instruction register based on the encoding。

 if you remember。😡，So there's no magic again， the destination register ID is encode in the instruction register and gets connected to the register file and the register file gets right enabled such that you write this data that's coming off the processor bus into the register specified by the instructions。

😡，对。😊，LDR， if you do LDR， you load the data that was placed into the MDR Me data register。😡。

And set the control signals such that you get the memory data register tryt buffer。

 and the memory data register gets on this processor bus。😊，And you set the destination register。

 a load register signal accordingly， such that you write enable the register file and destination register comes from the instruction register。

 instruction bits over here。😊，So you need to set the control signal sort accordingly such that MDR gets into destination register。

 we're going to see different ways of doing that later on。

 but now I've given you a complete instruction cycle for multiple types of instructions。

 different instructions do different things clearly， we've looked at add and load。😡，Hopefully。

 this makes sense。We're going to see more and more of this。Okay， how much time do we have， let's see。

We can change the sequence of execution， there is enough time。Because it's important。

 you need to change the sequence of execution， and then there'll be a clean state。

 So we've seen a couple of examples of instructions。 have what we have not seen is this。Normally。

 we execute instruction and program order， sequence， sequential order， first instruction。

 second instruction and third instruction， you keep in command the program count。😡。

Unless we can we change the sequence of execution， so control instructions allow us to do this。

 they allow a program to execute out of sequence。😡。

They can change the program counter by loading it during the execute phase。😡。

Meaning there are instructions that operate directly on the program counter program counter is an architecturally visible register to the programmer programmer can say I'm going to put value X into the program counter。

 which means that the next instruction that I'm going to execute is going to be at addressSX right so you're very powerful as a programmer as you can see。

😡，The program doesn't need to be executing in sequence。Okay。

So basically that wipes up the incremented PC that's load during the fetch phase and loads the incremented PC loads whatever you're loading after the execute phase。

😡，So let's take a look at an example unconditional branch or jump in LCC3。

 it looks like this jump R2， R2 is the register， and what this does is you take this is the encoding。

 you have a base register， base register is a value。😡，Its good program Con gets。

The value in the base register。Makes sense， right， whatever value you put over there。😡。

So you can jump to anywhere in memory， any place in memory can be construed and interpreted as an instruction。

 so you could have instructions all over the place。😡。

This is the register addressing mode as we will define later on there are variations of this。

 there's a return， this a special case of jump where base registers are seven。

 you can do function calls。😊，This is how you can jump to a function， for example。

 you have a base register， you jump to a function and then you can return these are jump to subber team this is actually how you really jump to a function that you will see later on and then there's a jump register also。

Okay。Okay， so there's a jump in MIPS， this is unconditional branch or jump。

 it looks like this actually in MIPS it's a little bit different if you look over here。

 this is the up code to Op code is the top six bits and the rest is the target。😡。

So how do you use that target， this called the J type instruction MIps， somebody defined it this way。

 not my fault。😡，Somebody else's def。ATart address is essentially the target address。

 essentially where you want to jump。😡，But this is how that。Full program counter is computed。

You basically take the incremented piece， the top four bits of the incremented PC。😡。

Concatenate to it。These 26 bits。Multiplily by four why this target is by the addressable。

 you multiply it by four because instructions are word aligned。

 they're actually word words so you multiply this by four so that you can get the word address。😡。

And you cancateate to it the top four bits of the PC。

This way you can jump relative to the program country， your program country is here。

 you use the top four bits， they don't change， but relative to it。

 you find a location to jump to right it could be anywhere within the vicinity of to the 26 up there and to the 26 down there。

😡，You want to take some minus one。Okay let's use a pseudodirect addressing mode。

 we will see the s drum it's also called a PC relative addressing mode。

 so there are variations like jump and link function code that I'm not going to talk about。😊，Okay。

 let me just show you at then really we done。 So how do you update the PC jump， for example。

 loads SR1 into PC。 There is a path from register file。😡，That goes through a multiplexer。

 and you can actually set the load PC signal over here。 That way。

 you can put a register into the program count。Okay， this is where I'll stop。

 this is where we will pick up， hopefully we will go into more instructions and look at trade offs in the ISA I'll see you tomorrow。

😊。

![](img/2aeaa1a1411c66a2175e6eb0daf07961_6.png)

今约是。

![](img/2aeaa1a1411c66a2175e6eb0daf07961_8.png)

あげます。