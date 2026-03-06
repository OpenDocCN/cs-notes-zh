# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p15 P15 Compiler foundations： Source code to running program (COP-3402 Fall 2024) -BV1v6vdBKEHB_p15-

And yeah， so welcome back to System softwares。Go into our next section of the class。

 the second half of the class where we talk about compilers。

We're in the compilers Foundation section， which is a little now broken up by the midterm because of class cancellations。

But today I want to talk to you about how your source code， which is really just a text file。

Gets turned into a running program， a process on your machine。



![](img/c268ccdcb0735ed18b7012070e74d212_1.png)

![](img/c268ccdcb0735ed18b7012070e74d212_2.png)

So to get started。呃。Let's answer some。You know of Miriam Webster questions。

 although it's probably a different definition there， what's a program？In the kind of architecture。

 you took computer org， what's in？啊吧。Did you raise your hand Oh sorry， up there you。What's that。

An abstraction， a program is an abstraction。Well， what's a program。

 a program so yeah we have the next question is going to be what's a running program or what's process。

 but I think you were first yeah。Yeah， this is a set of instruction。

 so I think this is the computer org。Description， right， But they say this。 It's like。

 you have a stored program machine where it has some memory storing a set of instructions。

 So a program is really just a sequence of。Instructions to a machine。

In the computer org world or in the processor world， that would be machine instructions。

But when we write C are we writing machine instructions that the processor will run， no。

 right we're writing for a different machine and actually a kind of a virtual machine。

So source code is written in a programminging language that may not actually correspond to machine code one to one。

All right， what's a process？In our systems context， yeah。A running program。

So they have a program which is a sequence of instructions， and then we have。A running program。

 which call a process。So the core thing I want to get across to you is how we go from this source code to a running program。

And in order to understand that， we have to actually understand a little bit about how programming languages work。

So if you have a C program， like your Hello world program。Does your processor。

 most of you have an Intel processor， maybe some of you have an arm processor。

 does that processor run C code？Who says yes？This says no。被答诉的。Okay， okay， good， okay。

 so then you'll see today how this works。So to motivate this。

This is typically how you run your C programs， rights probably you learn this in。

You probably learned this in Intro to C or Comporg。

This is what you do to supposedly run your C program， right？So why are there two commands to run it。

 why not just run hello， that's it。Good， yeah， one compiles it and one executes it。So GCC。

 if you're not already aware of this， GCC takes that source code。

And it turns it into a runnable program， a program that could be run on your system and your architecture。

And what makes this process so kind of mindwarping？Is that， if you notice when we run。

When we run this， what's GCC？GCC is a program too。So we have to run a program that somebody wrote。

 and that program takes your C code and turns it into。A runable program。

So this is a confusing part about this is what's sort of tricky about compilers is that there's really three programs that you have to keep in mind at the same time you've got。

Your source program。Your output program and you have the compiler program itself。

 which is yet another program which needs to be written in some language。

But then we'll do this translation for you。Okay， so there are two yeah。そ让。That's a good question。

 what turns GCC， so does anyone know what language GCC has written in？唉，我着。Okay。

 it could be written in assembly， it could be written in C， so GCC， as it currently stands。

 is written in C。So what translates GCC into a runable program？GCC right， GCC。

 so you get this kind of you know this self referential behavior in the compiler。

 which is one of the kind of fun and interesting parts about the compiler world。

 this is called the Botrapping problem where how do you compile a C program if you don't have a compiler yet。

😊，诶。One way to do it is you write a compiler first， a small compiler in assembly。

That will do your translation， and then you can eventually rewrite that program。

 that assembly program in your language。And so that way。

 you kind of need an initial program originally to。To compile your compiler。

This also creates some security and trust issues as well。But okay， that's a good question。

 so GCC current iteration is written in C。Needs a C compiler and a compile it。But okay。

 so let's look at how we actually write one of these programming language implementations。

So there's two core techniques， comp hirers and interpreters。

 anyone aware of the difference or some examples of them yeah。すに。イこれト。So yeah。

 so that's pretty close。 So interpreters， yeah， that's right。

 So interpreters look at each line of the code and they。

 they execute it or they simulate what the behavior of that line of code will be。

 Compilrs don't actually run the whole program。 They read the whole program in and translate it to another program。

 So compilers do know。Stricly well， in the strictest sense compilers do no execution of the program。

 as you'll see if they're compilers class compilers will do some interpretation actually of the program。

 but if we kind of make this a hard boundary， compilers doing translation and interpreters are simulating or emulating each line of code yeah。

Thattslash one？Okay， so that actually brings up another interesting question is。Hello is a program。

So the dotC program is being translated to hello and executable， and then we run hello。

 so is hello the hello executable being compiled or interpreted or something else？What reads it。

 what reads it？同 play。The computer knows， yeah， right， process so who runs the Hello binary。

 what machine is running it？どせ。Well， it could be a virtual machine。

 but if you don't have a virtual machine， and you were right there you had it。

 like what's running it？Who's running the machine code on your machine？the processor， yeah。

 the machine， the processor， the CPU is what's taking those instructions。

 a compiler is producing a binary that has machine code instructions。

If you remember from computerorg， I think you did MIPS computerorg。

So there's a physical processor that can read those commands in in binary and execute them。

 give you the output of those commands。So in that sense。Is hellello。

 if you could only pick between compilers and interpreters。

 is hello being compiled or being interpreted？Interpret it and who's doing the interpreting？

The problem with the CPU， you can think of the CPU as a kind of interpreter of machine code。

And it's the electricalal engineers who design it so that it will give you the output that you want for the instructions that you have。

Kind of makes sense。O。So let's diagram this out， so we' going to talk through this a little bit。

 let's diagram this。We can hopefully。Give you a。Better sense of what's going on here。So if we have a。

That's right， this doesn't。All right， here's our。CPU。Here's our compiler。

A compiler takes the source code， turns it into。A binary。

And then through processes that we'll talk about a little later。

 this hello machine code gets executed on。The CPU and then you get your output so where's the input go does the compiler take。

 so let's say instead of hellello world it's myLS and we pass it a parameter。

 does that parameter get passed in the compiler？Or does it get passed in the machine？Machine， yeah。

 so this is a massive oversimplification。 IO in the systems world is a little bit more complicated。

 but you can think of。The。Any input being passed？V the machine。So in the command line terminal。

 this would be through your keyboard and there's actually hardware that reads the signals from your keyboard and the kernel will process that input for you。

And similarly， the output is also managed by the machine， not really the CPU。

 but by the machine and the CPU。Yeah so the compiler is above the kernel。

 this is not like a complete diagram of the system， I've made some dramatic oversimplifications here。

 but the compiler is just another program that you run so it's in a sense no it's kind of equal to hellello。

 it's running on top of the running on top of the kernel kernel is providing access to the hardware。

So you're not able to directly。Control the CPU to tell it to run hello。

 but the operating system is mediaing this for you， but the compiler is also running on the CPU。So。

WeWe could actually kind of enhance this diagram。By showing。The compiler。Running on a CPU。

And taking your HL program as input。And producing a hello binary。

That hello binary also gets run on the CPU。So it's going to be a little convoluted if I。

Draw an arrow to the CPU because it's not really in the same。あ。

It's not really in the same step of execution， but then after you produce that program。

 it actually gets stored on disk。And later， after you compile it。You can execute it on。The CPUU。

And get your output。Does that make it a little clear？

So the compiler itself is a program also that's running。P on your machine。はいいいす。Like useace， exactly。

 so Ut has。So Intel architecture processor。And when you do dot s hello。

 the operating system will run Fork and exec。And it'll copy those machine code instructions into memory。

 and the kernel will tell the CPU to start executing。

 it'll change the program counter to start executing those instructions。From the machine code。

Our questions on compilation。And so as we point out， this step here is like interpretation。

If you think of the CPU as an interpreter。The interpreter takes both the program code and the input simultaneously。

And it executes each instruction， it simulates the output of each instruction of that program。

And eventually produces whatever output you have for that program。Okay， questions on。Compilr。Yes。

で成婚輩。Itas it like a stand。That's a good question actually， so no， not strictly speaking。

 but and I'll show this next time I have a diagram I can show from the LVM world。

But sort of modern industrial compile of design tries to。Support multiple languages in the compiler。

 So Gcc， you can， you can target multiple backends， You can target Intel or X 86。 You can target arm。

 You can target Spark， I think they have a lot of。Targes you can generate a lot of machine code you generate and it also has different front ends like C+ plus Eda。

 so I'll talk about this more next time， but you can design the compiler so that it will be able to more easily support multiple languages。

 but strictly speaking no， each compiler is for each language that you want to support each input and output program language yet。

I really like keep you down。Oh yeah， so you wouldn't be dialing the executecutables。

 you'd be dialing the source code。Well， it depends well， if you look at like apt or something or。

Yeah， depends on the system so like Mac years ago， I think they actually do this nail for Ar。

 but they had so- called， I think fat binaries where they would actually ship multiple architectures binaries in the same package and then it would sort of dynamically pick based on what machine you have a and other package managers。

 you can specify the architecture you want， they support binaries for multiple architectures and。

They'll just have the binaries for multiple different architectures available to you you can download you can also build from source so this tool chain that I showed you where you do get clone。

 make and run， there's additional tooling that will port that source code to a different architecture for you called auto toolsol or autoCf part of the same kind of family of the toolcha to that they talk about it in the book actually you read see programming book I think you mentioned auto tools in there。

As well。So MIPS is a machine code for a MIPS processor。

So that's kind of on the same level as an X86 architecture MIPS。呃。

Probably few people use a MIPS machine here。And I think you had to emulate it。

 you needed a virtual machine for it， Most people in consumer devices at least have X6 or arm。

But those are all just different process architectures that have their own。

Definition of the machine instructions， kind of like C versus Java。

 there they take different languages， even though they can compute the same thing。

 they just take different languages， they take different assembly。So that makes sense。Okay。

 so we're translating between two languages here， the C program， the hellL program。

 how do we make sure that it's actually going to execute what we want？So， you know。

 if you are going to China and you want to be able to communicate with people。

 you need an interpreter or you need to hand translate things ahead of time。

 how do you make sure that you're actually expressing the same thing。Well。

 the compiler has supposed to make sure that your output program behaves the same way as your input program。

 but what does that mean？If a C program has a for loop。

 does assembly language have a for loop construct？No， what do you have in assembly。

 most what you learned a mythPS or yet？You have jump， yeah， you have jump， you can branch。

 that's not a for statement for statement right， for a forlilift statement。

So what can the compiler do to make sure that the for loop， the behavior of the for loop？

iss the same or what does it even mean to have the same behavior in the assembly program。

 I mean obviously each individual instruction is not going to have the same behavior， right？😔。

So the for loop can't even be expressed exactly in assembly。

 so how can we guarantee or how can we check whether they're the same yeah？Yeah， by their output。

 so one definition of an equivalent program is a so called functional equivalence or observational equivalent。

That for the same inputs。You get the same output。And that's really all you can do for deterministic programs because there are different programming languages。

 how do you make sure that that's the same thing， it's like speaking Chinese or English？

The actual words are going to be different， the phonemes are going to be different。

 but you want to have be able to express the same thing。

But what about like random programs have you ever used RAD in like Python or C？嗯。

How can we make sure that that program compiled is the same or what even is randomness？

In a program in a machine， yeah。喂。Okay。是。Yeah， and that's exactly it。The program itself。

 when you call RAandD， the program itself is deterministic。😡。

It's just that the random number generator takes in。

An input that appears random or actually maybe random if it's generated through some physical process that you could not predict。

 but the program itself。At least in the architectures we're talking about are deterministic that when that CPU as long as it's designed correctly。

 whenever it gets the same input， it's going to give you the same output and randomness is achieved by just passing a new input to your program。

And that input may be randomly generated， but given the same random input。

 your program will behave the same way。There are new architectures like quantum architectures which are sort of intrinsically probabilistic and there are also probabilistic programming language that actually let you deal with statistical distributions and so in those you know。

They may not be deterministic， but there still are distributions like probability distributions that they follow。

 but for the architectures and languages we're dealing with this class。

 they're totally deterministic。so that makes it little bit easier too。

Validate that the translated program will be the same as the input program。Because you just say。

 well， for any input， you should have the same output。

 so you could even imagine testing by just generating a whole bunch of inputs and seeing if the outputs are the same。

So would that work actually is a way to prove that a compiler is correct。

 generate all inputs and generate the outputs。Yeah。夜ル約。パ？Okay， that's a good point。

 so how do you run the input program， if there's nothing to run it on you have to compile it。

 that's one problem。Let's say you were comparing two compilers to make sure they were the same。

 would you be able to generate all inputs and check all outputs？おな。Okay， a set of them， right。

 so you may not be able to do all them because there may be an unbounded set of inputs that may take an unbounded set of strengths。

And even if you could generate all inputs， there's a famous， well。

 at least for computers that have infinite memory， there's a famous result by Tring。

 the Tring halting problem， where you prove that even if you could generate all inputs。

 you actually wouldn't necessarily be able to improve equivalence。Of all programs。

 you want to be able to get the output of all programs because you could always construct a program that way。

Kind of violate your assumptions， violate your program that tries to prove the equivalence of two programs。

 take like a theory of computation class。Maybe it might have to be a graduate class so you can learn about decideidability and turning completeness。

So compiler writers have to resort to other techniques。

 there are formal techniques for proving you take a model of the input language in the output language and you can write a proof that the translation actually will be equivalent for all inputs and outputs。

That's also kind of kind of outside this class， but so in this class we'll use testing and we'll use kind of use reason informal reason to guarantee that our output is the same as the input。

All right， so that's compilers， questions on kind of the overall concept of a compiler。

It's only put the diagram back up。So compilers are translators。

 and their goal is to translate one program to a program in another language。

 usually a lower level language。And but preserving the equivalentvalence of those programs。

 preserving functional equivalence， that the same inputs will give you the same outputs in all cases。

For that program， all cases where the input program is defined。그하신 전에。Yeah。

It's just like looking at the di。No。No， well， so this is this is。It dependss on how your'， well。

 it's all going to be binary because the input will eventually reach the CPU。

 the CPU only works with numbers， but so there's if you take like an electrical engineering class。

 there's a whole suite of ways so peripherals for your device that you can give inputs to so there's cameras and microphones。

Keyboards， mice， these are all inputs to your machine， and they all ultimately are quantified。

As numbers that you're seeking will process， so no， the input itself doesn't need to be translated。

It's well， if you think of all programs as， if you think of all inputs as being binary data。

 then you can define that for hello。c as well。And you can define it for both machines。

 so you can say that both machines just take binary data， for instance。

 could sort of frame it that way。But yeah， that's a good question。Yeah。That's right， yeah。

 that's right。比要更。That's right， so that's yeah that's this diagram here of the compiler so that so I should have put like compiler do C here。

 so this is the or no， not compiler C， this is the compiler binary。

So to make this so to add a little layer make this a little bit even more complicated。

 your compiler binary is running on the CPU， it's taking your C program's input and giving you an executable output。

 but earlier someone must have if your compiler is written in C or a non anassembly。

Then somebody must have also。Take in your。Compilr program， what？Sorry， I'm confusinging myself here。

 so it must have taken your compiler program。And。Run it through your compiler to produce the compiler binary。

 And so this is that bootstrapping problem that we that we like talked about before where。

The compiler。Needs to be able to compile itself if you don't want to write the compiler an assembly。

So strictly speaking， if I want to use my same CPU diagram here。My compiler gets run on the CPU。

The C program is passed as input and then a compiler binary is the output。

 so this seems kind of silly right your input is the same or the thing running is the same as the output。

But。This is a good way to make sure that your compiler actually works。

 It also means if you want to modify your compiler or upgrade your compiler。

 you don't have to go back to scratch and write an assembly program， so this might be something like。

Compiler。c star， and this will be like a modified version of compiler or maybe port it to a different architect。

That kind of answer questions， that makes sense？So compiler is a binary that runs on a CPU。

 it takes the compiler source code as input， produces a compiler binary。嗯。

And then that compiler binary also runs on the CPU， takes whatever program you have and runs it。

ButYeah wait。把这。That's called decompilation and yeah there are tools to do that there are tools that will do that also a little outside to go this fast。

 but yeah this is used for like security analysis， reverse engineering tools to try to figure out sort to recover the source code there。

I think video game producers who want to get the。Euculators who want to get the source code of the original program。

 they'll use decompilrs， but yes， there are decompilrs that will go the other way now you lose a lot of information as we'll see when we talk about compilers you lose a lot of information about like names。

What original construct reuse， the compiler does optimizations that'll make it hard to tell whether you had a for loop or a while loop for instance。

 but yeah there are tools that attempt to do this， but they're like inferring trying to infer the original source code。

 they won't necessarily give you the exact source code。Yeah。Be compiling or compiling？

So I have a little add in here for my course， I have a course on compilers， compiler。

So you can take this class， it's a graduate course but undergraduates can take it。

 I think programming languages is a prerequisite， but I teach this every spring so far。

 so if you want to actually get into the weeds in compiler construction， you can take this class。

I teach it and yeah， teach it should be every spring I teach it。All right， so that's the。

Joy of compilers and hopefully you can kind of look at these diagrams a little bit or try for yourself。

 you can actually build GCC if you really want， it's a big program to build。

 but if you can wrap your head around this kind of selfreential aspect of compilers then it'll make it a a little easier for you and also even just looking at this diagram。



![](img/c268ccdcb0735ed18b7012070e74d212_4.png)

When we go to write our compiler， just be aware that we've got the input program。

 the output program and the compiler program itself， you'll be writing the compiler program。

And your compiler program will take input programs and produce assembly code。So you。

 these are all going to be in different languages。So you just have to keep in your head the difference between。

The input program and the compiler， remember the compiler is not interpreting。

 it's not trying to give you the answer for the input program。

It's just trying to translate into a new version of that program。

 a new implementation of that program。But we'll get to that when we get into the compilers that's the confusing part is to resist the urge to start in writing an interpreter because that's kind of like naturally what you want to do。

 like read in arithmetic and then you were like， well， hey。

 I have arithmetic in my language so I'm just going to run arithmetic， I'm going to run plus。

But that's not what a compiler does， that's an interpreter。Okay， so。

An interpreter and I struggled to find the right terms for this。

 but an interpreter effectively simulates the actions of the source instructions。

 so if you think of your processor as an interpreter。

 the machine instructions are just invented by some electrical engineer。

 there's no physical thing in the world that will run that so what they do is they build。

A circuit that will give you the output of that human defined machine So addition。

 you know there's nothing intrinsic really about addition in a circuit。

 but you can design a circuit that will do addition for you。

 you know we have a notion of addition there。sortrt of metamaticeticians who try to aximatize what addition is。

 but if you just define addition on paper as an operation itself。

 then you can design a circuit that will give you the output of addition that you want。

So in the machine level， this is implemented in hardware。

But you could also implement a software interpreter。

 so as anyone know like interpreted some languages that have interpreters。Yeah。Javascript。Python。

 yeah， so these are interpreted languages， and in reality they actually use a mix。

 you know pretty much all programming use a mix of compilation and interpretation。

Python actually compiles to a smaller language。But if we pretend that Python is purely interpreted。

The interpreter will read in kind of like your MySH interpreter， which is a command line interpreter。

 it'll read in each line of that Python program， and it'll run code when it sees that。

 it'll see an addition， it'll run code to perform that addition and give you whatever the output of the program is supposed to be yeah。

So let me diagram it to show the difference between a compiler and interpreter。所以。An interpreter。

 let me do the overall diagram and then we'll see how the machine fits in here。

So my interpreter takes in。Let's say it's Python， it takes in my Python program。

 and it also takes in the input。So the interpreter takes in the input， just like our CPU。

 you can think of the machine as taking in the input。And then produces the output。

So if we use them a kind of CPU view of this。The CPU。Is taking。不要。

So let's put aside the CPU version of this for a second because actually this Python。

Program is also a- well， yeah， I think we can I think let's do。So the interpreter itself。It is。

A binary program， you have to compile the interpreter if you write the interpreter and anything out of an assembly language。

And the machine is also taking in。The Python program。And it's taking in the input。Ultimately。

 the interpreter is directing the machine to take him that input。And giving you the output。

 so this is kind of a way oversimplified view of the interpreter in terms of the processor。

But this is really the kind of like canonical diagram of an interpreter。

The interpreter program takes in both the source code。Andd whatever input you have to the program。

 and it produces the output for you。Yeah。Well， so see， it could。

 you could write a C program interpreter。So this is kind of like a question about whether languages are intrinsically compiled or interpreted。

 and strictly speaking they're not， you could write an interpreter or a compiler for any language you could compile Python to C or assembly or to see。

 which some people do， you could write an interpreter for C。if you want it， it may not be， well。

 you'd have to model the machine in your interpreter。

 but the language that says there's nothing really intrinsic in the language that makes it compiled or interpreter。

 you could write a compiler and interpreter for either one。

 but some languages are does have features that are more convenient for compilation or interpretation so C for instance doesn't define the bit with of integers。

 instead it just leaves it up to the machine， leaves it up to the it it defines out of bounds as undefined behavior so it ends up being kind of left to the machine to try to fix those kind of things yeah。

One way you could say that yeah， yeah， I think yeah。

 that is the main difference is that the compiler creates an executable that will run on the processor。

 whereas the interpreter，That never happens， you never create an executable and an interpret it。

Implementation， the interpreter reads the instructions of the interpreted language。

And directly executes them or simulates their behavior。Yeah。Youか about just。

So just in time compilation is one of these so compilation and interpretation are actually generally blended in most programming languages。

 so just in time compilation is a technique for improving the performance of interpreted languages by compiling on the fly commonly used traces through the program。

 commonly used paths through the program。So yeah， that's just in time compilation。

 so these techniques are really actually blended in most programming language invitations， but yeah。

 I think what your fellow student said if your programming language implementation produces a machine code binary。

 then you can call it compiled， if it gives you the output when you run it。

 we can call it interpret it。That's like kind of a simplification。All right。

 so let's see an example of a couple of these， so let me actually write some。Code here。Or actually。

 at the same time， let me just go through the code。Okay， so here is an example。

 so let's say we want to translate one plus two to machine gut so this is a string and I want to write a little calculator program so first of all。

 if I take this string，And I somehow， put it in memory and point my program counter to it and have my X86 architecture machine start running it。

What'll happen， will I get three as the output？Can I execute？This string， one plus two。On say。

 a X86 processor。Kind of a subtle question， right， because you keep thinking in your head， well。

 yeah， it can do addition。But remember， the input to this is literally a string and what yeah， yeah。

お。ビー内イ？If it wasn't a string right， but it is in your hellello world program。

 those are strings right and you don't write like the Intelnemonic for addition。

 you write the plus symbol， so how do we what is the plus symbol in a string？In our editor。

 what is it？It's ASI code， right， and if you look at the ASI code for numbers。Like。1。

It's not the number one， it's not binary one。I forget out which one is 49 in decimal。

So the ASCI code for the symbol number one。Is decimal 49？

InSo if you actually open up your like hello world text file and look at the。Binary of it。

It is in no way reflective of machine code integers or addition。

 and you know the plus symbol is definitely not as far as I know anywhere close to the。

 so this is yet。Represented in a different way， but you know it's。Deimal 43 for the plus symbol。

 I'm pretty sure that does not correspond to the Intel instruction for this。So this string is。

A completely different representation from addition in your machine。

And that's where the compiler comes in， the compiler takes this representation。

 which no machine that I know of will directly interpret。And it converts it into machine code。

So here's a really little simple calculator program， so what does it do？It reads in one character。

And it says， well， okay， the first character is going to be the left operator or upper end of my operation。

The next character I read in is going to be the operator and the next character after that is going to be the right opera。

And so this is kind of like the little definition of your language because this is enforcing how the programmer is supposed to give or do write your language。

 so this implies that you have to give a character in ASCI。

 followed by an operator followed by another character for an integer。With me so far。

 just reading in these three characters from the input。Questions questions on this code。Okay。

 and so this is the compilation step。We look at what kind of operator we have。

 so here we actually check whether it's the plus symbol。And if it is， we generate machine code。

 we generate machine code that we hope is equivalent。Now there's nothing。

Telling us whether it's equivalent， we have to。Prove that。But how do we do addition in assembly？

Remember in MIPS or X86 or whatever you'd like yeah。对对。What车。Well。

 that's the name of the machine that does， what's the instruction？Yeah。Very believe。こいか。Yeah。

 there's several instructions for doing it， there's like multiple。Multiple instructions。嗯。

But this is one way。To do addition in the Intel world。

You can there are several instructions to do this， but you could move immediate。

 so this is we'll go over the Intel AT&T syntax， which is what this is， the sources on the left。

 the destination is on the right， but this is moveve immediate， the number one into the A register。

 move immediate， the number two into the B register。And then call the ad instruction。

 which stores the result。In the a instruction， so this is the intel this is an Intel assembly version of this input program as long as're know we're kind of assuming what the definition of plus is。

Which。I can't necessarily take granted it， you could write a language where the slash symbol is for P if you like。

 because it's just ASCI code， there's nothing intrinsic about the symbol that makes it addition。

 it's just a symbol。It's this interpreter or this translator that gives it meaning。

But this is what the output we want to see。Makes sense。

So do you agree that if we kind of take for granted that this is a calculator where we use ASI symbols for the arithmetic operations。

 then this is an equivalent output of that program， right？Makes sense。

Questions questionsions on how why or why these would be equivalent。Okay。

 so then the challenge becomes， how do we take any input。

 let's say our language is single digit character， an operator， single digit number。Well。

 we could use a little template here。For this assembly output。

And so this is a little bit of annoying printf formatting， but basically I say， all right。

 take whatever character I have in the left variable。

 take whatever character I have in the right variable and generate move instructions。And then。

 if it's a plus operator， then generate。The ad assembly instruction。Questions on that code。

That kind of makes sense so we have our first actually kind of compiler here where we're translating what is just ASI code。

 which has no meaning to the machine， has meaning to us because we're interpreting it in our head。

 we have the semantics of these symbols in our head。And then we're automatically generating。呃。

Assembly code that actually that assembly code will change depending on what our input is。

And as long as we've done this correctly， we'll always get an equivalent assembly code program for whatever input we give it within the definition of our language。

And so here's our。ThePro so I can give it other。

![](img/c268ccdcb0735ed18b7012070e74d212_6.png)

I don't think I did other operators， but you can see。This program will generate， you know。

 if you give it other numbers， it'll just like。

![](img/c268ccdcb0735ed18b7012070e74d212_8.png)

It's like a template it will just plug in whatever number you gave it for the left and right opera。

But if you run this， it should give you。The same output that we expect from our intuitive definition of this input language。

Quest on this， so here's our very first compiler let see in the that's pretty straightforward door right。

 so as long as you get the idea that this program is not meant to perform the addition it's just meant to generate another program it's really a code generator。

It's generating assembly code， but it's supposed to be equivalent to the input program。

And without any formal definition of the input language。

 it is this program that actually defines the meaning of it。

 so it's defining the meaning of the input program in terms of how it generates output。

 assembly code output。Questions on this？If you can wrap your head around this。

 you try writing it yourself and you wrap your head around this。

 you'll get the kind of crux of compilers， yeah。That's a good question why do we have so many programming language if it's all assembly that's kind of a question for like programming language class there are features in languages that make programming languages convenient for certain tasks so C has no object orientation but if you learn C++ or Java theres some utility to be able to express more coursegraed computational constructs or layout memory in more sophisticated ways so if you take a programming language class the main goal of programming language design is to provide methods of abstraction for the user so you can even ask to kind of。

😊，Kind of you absurdum to your question， why even have program layer just program and assembly。

 right？Why not just program an assembly， why bother using C？Take well。

 for if you're really good at assembly program might not take forever。

 but assembly program doesn't even have functions。So C provides functions in the way I'm going to define them in a couple lectures。

 but it divides functions， C and the machine don't have functions。

 so wrapping your code up with local variables，This feature gets added by the programming language and the programming language translation or interpreter or translator for trans machine code implements equivalent code to that abstraction。

 so's to kind of give you a lazy answer it gives you methods of abstraction and those supposedly make coding easier or harder they can also provide ways to check the program for you automatically so C will do type checking to make sure you're using the right kind of variable in the right context but yeah that's a really good question yeah。

Why do we- so this again， this is really an engineering choice if you ask like Linus Torvals。

 why Linux isn't C， he has very strong opinions about CQ+ and other languages。😊。

Some language so I view programming language choice as an engineering decision where you pick the right tool for the job so you'll see on stack Overflow of people saying this is the best language is the worst language。

 my opinion it's really an engineering choice you make an engineering decision about what's going to be the best tool for the job and sometimes unfortunately that means legacy code dealing with legacy code so C has probably billions of lines of code hundreds of millions that you are like running or not running but hundreds of lines of code that generated programs that you are probably running right now on your machine and there's a huge amount of legacy code that still exists for these languages so I would say it's a choice that goes beyond technical decisions but even in the technical decisions there are choices engineering choices about language design so performance of the language ease of programming how your developers are trained but this is also kind of outside the scope for this class but。

てあがったつ。Short answer， I would say。All right， other questions about our first little compiler here。

Okay， let's take a look at the interpreted version of this program。

So it starts the same way we need to process the input language。

 we need to read in the input language， so we just read in each。

 we read in the left right opera and the operator。But in this version of the program。

We first convert the ASI into the number representation that our interpreter language supports。

 and there are many ways you could do this。 is this is my lazy way of converting ASCI into。嗯。

An integer in C， the reason this works。Is because。You can actually subtract characters or just integers in C you can actually subtract them。

 so if you take whatever the ASI code for zero is， subtract it from the ASI code for any other number。

You get that get that number because they're all in sequence from zero zero to。そいになる。自民工。Yeah。

 that's a good point， so I'm really glossing over the definition of the language here。

 but all this language can take in and correctly translate。

 even though there's no explicit definition of it is it can only take in three single characters。

The first and last character are supposed to be。An ASI representation of a digit and the middle character is supposed to be the ASI representation of an operator。

 So that's kind of our definition of language。 And I glossed over defining it。

 I just kind of took for granted that you would like get it。 But yes。

 that that is a restriction on this language because of how we。Process the input。

 how we process the strain input， does that going of make sense？🤧So what does our interpreter do。

 we converted it into a representation that the language we're writing in represents integers in。

And then we just literally perform the addition in C。

 we use the CC notion of addition to perform the addition。It almost seems like toological， right？

We're reading in a plus symbol， why do we bother having to turn it into a plus symbol？

But if you run this， you'll get the same output that you get for the。

For the compiled version for a correct set of inputs， so here5 plus three。

Five and three get converted into the machine representation of integers because that's how we wrote our C program。

 and then the result is adding those two numbers together and printing them out。

 and so this is the output of our interpreter。Questions on our first interpreter implementation。

I'm sure you can see all sorts of problems with these and limitations， but yeah。

It's not the internal compiles， it's just that I think architecture is so much faster at running its instructions。

Yeah， without techniques like Jit， just in time compilation。

 I don't really know the latest results on performance。

 but I think it's just because hardware is so much faster than software because the software is running on the hardware。

 you also have memory and other types of pressures that are causing performance changes。

 but I don't know the exact latest results， but typically the kind of common wisdom is that you're running on the bare metal on the architecture versus running software thats trying to interpret that language。

All right， any questions on our interpreter？So this is kind of a silly looking interpreter because we're actually using the same symbol in our input language and in our compiler。

 So let me show a。

![](img/c268ccdcb0735ed18b7012070e74d212_10.png)

Example of adding using an operation that isn't in C to kind of show where an interpreter will really differ from。

ACompilr。So if we have a operation that doesn't exist in our language that we're writing the interpreter in。

 then we're going to need to simulate the behavior of that operation of that operator。

So here's the pseudocode for what that would look like。

 we'd read in know the opera and the operator and here's one algorithm for computing。

 so this is supposed to be power exponent， so this is one algorithm for computing that right it's just repeated multiplication you just loop over one to the right opera end and perform the multiplication of the left multiple times questions on this。

Algorithms is how you implement power because most I think most processors don't have exploits。

 I don't think。Questions on this。So hopefully this is I have like a full program you can see on the notes。

And you can go over and see， I have a little implementation of the assembly for power。

It just implements that same pseudocode。So this is what it would look like one way that implemented an assembly。

And here's the interpreter version。Quest on compilers versus interpreters。And their implementation。



![](img/c268ccdcb0735ed18b7012070e74d212_12.png)

So super basic intro， just remember that compilers translate to。

A language that's going to be interpreted by the machine， whereas。Interpreters do that。

Simulation of the input language on the fly as it reads in each line of code and produces the output。

Yeah。We were things big combining。不道。百年三。こ they be。

So for and while are neither of those are machine instructions， they are C code instructions。

 and both of them are implemented。Without optimization。

 both of them are implemented using jump and branch， so you could look at the pattern。

Of the assembly code and try to guess that this must have been generated from a for loop。

 but you just might not be right， it might have been a while loop that looked very much like a for loop。

依啲れ那个打位。It so it doesn't have to be implemented with jumps so there's all sorts of techniques like loop unrolling or if the compiler can figure out how many times the loop runs。

 it can avoid using a jump so you know this is again count of getting into like the compiler you know bigger picture of the compiler but there are many ways to translate programs to equivalent programs there's not just one equivalent program even in C you could write a for loop in a while loop and implement the same program with two different see programs so same when you translate to assembly there are many different ways to translate it but there are kind of easy ways to do it or easier ways for certain constructs that allow you to do this very easy template approach。

And typically modern compilers are implemented by having the most naive。

 simple way of the translating and then optimizing later to have a more performant implementation rather than having the first step of the compiler try to translate to the best。

Asmbly code instead， they translate to the simplest version of each construct and then do later optimization to improve performance or change the behavior of the change the implementation of the assembly。

 I don't know if that answered that answered your question。Sort of。

So basically there's more than one way to skin a cat。

 there's many assembly versions of the C program that will be equivalent in a sense that they'll have the same output。

So for instance， I could， instead of addition， I could do subtraction。

 I could negate the number and then do subtraction。And that would be an equivalent program。

 but it would have a different sequence of instructions。Okay。

 so we'll get more into compilers we'll actually build a small compiler in this class。

 but I also want to get to。Yeah， so yeah， again， just a little ad for my class if you're interested in this compiler stuff。



![](img/c268ccdcb0735ed18b7012070e74d212_14.png)

I want to learn more about this， I teach a class on this。

 this is the graduate class but undergrads can take it。

 I think programming languages and something else maybe CS2 or discrete maybe is prerequisite。

 but undergraduates are free to take I think up to three graduate courses so if you really really like this stuff and you really want to get into the weeds with it。

 take that class。Okay。Okay， so that's actually， its okay， so that's the programming language part。

Let's look at the whole flow from source code to running program。

And each one of these has a tool associated with it。

That will take your source code into a running program。All right。

So the C program is first run through the C preprocessor。

 I don't have time to get too much into this， I do some research working on this。

 but this is basically processing your includes， headers， your macros。Then we get a C program。

 a pure C program。This gets compiled by GCC into an assembly program。

So before it reaches and executable， it gets turned into assembly code。

And then that assembly code gets turned into what's called an object file。

 this is just a fragment of a program， this is machine code， but it's not yet anecutable yet。

And then this machine code gets。Join together with other machine code that turns it into an executable file that can then be run on your operating system。

And the colonel will take that excutable file and turn it into a running program。

In the manner that we describe using fork exact。As we described earlier in this class。

So the CPprocessor produces C code， a C code turns into assembly， assembly turns into machine code。

 the linker combines the machine code with other code necessary for running。

 and then Exec VE takes this machine the say executable file， loads it into memory。

 and that's when you get your running program。So questions on the big picture of this。Yeah， yeah。

 what kind of like additional code that comes from。Okay， let's take a look at it。 So let's let's go。

 let's let me show you each of the。Instructions that。Get。Let's look at the output of all of these。

Okay， som let me to show this here。So let's take a hello world program。As usual。All right。

 here's our Hello world program。So I just confirm that that's here， here's our H World program。

Now let's run the preprocessor。Preprocesor gives you dot i files。Dhi runs the preprocessor。

So this is what your program looks like after。Running the pre processorsor。It is a mu。

 It's hundreds of lines of code with lots and lots of definitions at the very bottom here is our。

Body here's our main method and what the preprocessor does is it resolves among other things it resolves this。

Include， so this include is not really part of the C language proper。

 It's part of the preproor language， which。We'll talk about it a little more when we get into our assembly code。

It gives you all of the definitions like print F。Gives you declarations of all those because without those。

 the compiler would not know about that function name。

So the first step turns your little 10 line program into a many 00 line program that has a ton of just declarations of library calls。

So that's what the preprosor does。Next step is the compiler。

 so if we useS we can actually tell the so what the compiler will do is it'll run all of these phases up to executable GCC will by default run all of these tools for you behind the scenes。

 but in reality if we separate these steps out， decompose these steps。

 we can see what the output looks at each phase so the actual compilation part if we compile the preproces the dotI file is now like pure C。

We can compile this to its assembly code version， just like we did in our compiler。

So let's take a look at the assembly code。And so this。

 I don't know how familiar this will look coming from MIPS。These are。

These are the mnemonics for X86 assembly code and you can see we've got move， we have load。

 we have call， move， so same kind of instructions you would have seen in MIPS， P。

 know there's a lot of extra declaration stuff here that you don't need to worry about。

 but you can see here that our basic Hello world program is being turned into an equivalent assembly program。

Here's a string， this is basically saying， put the string in memory。And then。

It's actually loading the argument。Into a register and then calling our actually in this case。

 it's the compiler turned it into put S instead of print F。

 but put S is just another library call that will'll print a string。

But there's our equivalent assembly code。Questions on that kind of makes sense， right？

So there's so we've pre processcessed， we've assembled。

 and now let's get into what object files versus executables are， so to create an object file。

 this is the dash。あ？Dash C command。They make sure。Bron。So dash C will do an object file。

 so if you remember from the make file lecture we。嗯。Use dash she to do an object file。

So we can't actually， the object file is going to be now a machine code。

 so we won't be able to view it in a text editor， it's going to look like al do good to us。

But there's a tool we can use。Called object dump， which dumps object files and we can actually。

With DD we can disassemble it so it's kind to look very much like the assembly code because the assembly code is almost a one to one mapping to machine code so if we disassemble it。

 if we had to look at it in binary， I don't know Intel the actual Intel ISA like in binary。

 but we can disassemble it back into assembly mnemonics and you can see it's it's the same basically the same stuff here。

 we're loading the hello world string of memory。

![](img/c268ccdcb0735ed18b7012070e74d212_16.png)

![](img/c268ccdcb0735ed18b7012070e74d212_17.png)

![](img/c268ccdcb0735ed18b7012070e74d212_18.png)

![](img/c268ccdcb0735ed18b7012070e74d212_19.png)

And calling。Some address here， so we lost that put as name in this assembly code。

This is the same kind of code we saw with HelloS。But now it's in binary。

 So if you actually look at the。The heckx of this， it's you know， it's not ASI code。

 it's not a text readable， it's not a ASI readable。



![](img/c268ccdcb0735ed18b7012070e74d212_21.png)

Okay， so there's our object code。To see the difference between object files and executable files。呃。

We have to know a little bit about what linking does， so let me first link this。



![](img/c268ccdcb0735ed18b7012070e74d212_23.png)

So unfortunately， we lost a lecture on functions in the C runtime。

 which we'll have to make up for next time， but I'll try to explain this。Quickly here。

So this LD instruction， even though it's misnamed as a loader。

 it's actually the linker and what the linker does is it takes。Multiple。Object files。Hello。 c， Ho。 O。

And。Any other files you might have？So you could even have like standard IO in the old days。

And it takes these multiple object files。Into the linker， and it produces your executable file。

 let's call it。Hello。L4 hello。In the Windows world。So it just takes multiple compiled C programs。

And it joins them together into a single program， so in your when we talk about make files。

 we did separate compilation， we talked about separate compilation where you break your program down into multiple source files。

In the C world， you compile each of those individually into a machine code and then join them together。

Into an executable，So that's a very good question， so it's not just concatenation。



![](img/c268ccdcb0735ed18b7012070e74d212_25.png)

So let's say we've got a call to a function。So there's our。There's our linker， we produce this。This。

This object file here。sorry， our executable， so this is our executable has a lot more。

 so here's our main， but this has a lot more code in it now that we've linked。

 so we've linked it together with several other compiled programs。啊。

But the reason it's different from just literally concatenating the code is because of branching。

So for instance， in our hello world。呃。Object code， we had a call to this function put S。

But put S was never defined in our program， right， we never defined putS whatever or print S or any of these other functions that you call。

 you just call them and magically through compilation that function is now available and you're executable。

So what linknking also does is it resolves function calls with their actual definitions of the function calls。

So if we look inside of the executable， so this is the object code， if we look at the table。

 the function call table and the executable。We'll see that now。😡，Put S。 Oh， okay。

 So this is because of dynamic linking， but。Let me。So this is this is going to call a。

Where's the actual function。 So this is going to。So this is easier to show with。Let's say。

Let me show this very quickly with an example to show you because this is really the last step。

So I'm just going to call。One function here。I'm not going to define it， I'm just going to call it。

对那个呢。To find the colee here。The cols just got。Return something。

So I'll just compile both of these programs。in the wrong spot。Okay。

 so I've compiled these two programs。Callan Cuer。If we look at what functions。

Are defined in these two。Programs。You'll see in one， we have a call to。The function call E。

And there's no address of it， it's not the code for it is not in our。In our。M in our code here。

 it only has the function caller。Whereas call E， this other file has the definition of it。

So what the linker does， in addition to just concatenating the code is it links up。

 it combines these two。Programs into a single binary。 So let me put a main。Method here。

So that I can link them。So if I ask GCC to compile and link these into Maine。



![](img/c268ccdcb0735ed18b7012070e74d212_27.png)

You'll see that。Now call E and call her。arere both defined in this executable。

 so the linker doesn't just concatenate together， it also works out function calls。

 it also works with dynamic linking， which is a I have leading material if you want to learn about that and also works out branching and locations of memory。

So the linker is what takes all of your separately compiled programs， turns it into an executable。

 also importantly gives you the。It also gives you the C runtime which I didn't have time to cover last time you lost the class。

 but the C runtime is actually what interfaces with the operating system when your program gets run。

 the kernel by default will actually call this function。

 the start function underscore start function and that's what calls Maine it does a little setup like passing an AV and stuff like that so the C runtime does a little setup for you and then calls main for you。

 but the kernel actually calls start so this is the loader when the loader runs this program it loads all of this in the memory it looks at the table and it calls start and it's the C runtime which we linked here。



![](img/c268ccdcb0735ed18b7012070e74d212_29.png)

In our loader step， this CR run time， this CRT1， this is what actually calls Maine for you。

 it's a separate special program that you link with every C program in order to have Maine get executed with all the information that you expected to be executed with。



![](img/c268ccdcb0735ed18b7012070e74d212_31.png)

So that is how your program， your source program。Through many series of steps that we all take for granted because we just runs GCC and all of it gets run。

 gets turned into a running program， C preprocessor resolves includes macros。

 compiler turns it into assembly， the assemblysembr turns it into machine code。

 the linker combines machine code into an executable with the right runtime and right behavior for the loader。

 and then the loader goes into start， and that's what kicks off actually running your executable。

All right， so there you go， if you want to read more， oh yeah， question please。对对。Oh yeah。

 GCC will give you an error， this is why GCC errors are a little confusing because they may be at different steps。

 so you may have a preprocessor error， you may have a GCC error， you may have a linker error。

 like if you miss mainine， and so the error is just given to you and you don't they give you a little prefix and say loader error or preprocessor error。

 but yes， the error will just come from whatever stage you have the error。

And that actually explains why you have errors at different phases， that might be confusing。Okay。

 so if you want to read more about like there's a whole bunch of material here。

 practical material like from OS Dev。From the Linux news magazine， but yeah。

 can read about the runtime， read about how programs get run anyway， have a good one， exam next time。

 don't forget and I'll see you all next time。

![](img/c268ccdcb0735ed18b7012070e74d212_33.png)