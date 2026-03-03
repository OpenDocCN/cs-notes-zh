# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p01 1694009700-Compliers_on_9_6_2023_(Wed).zh_en -BV14PAUejE98_p1-

![](img/bb5746d6ac0ae5f4bd7d7eb87fdb28e4_0.png)

I just started last year， so I'm probably not the best person talk about the history of。你据接测述证。

All right， well let's actually get started thanks everyone for being here really lovely to see some familiar faces。

 some new ones as well， so I hope to get a chance to catch up with the people that I know and chance to meet new people in this class。

😊，I'm Steve Chong。 I'm teaching this course on compilers。

 Today's class is pretty much going be a bit of an overview about what the course is going to cover。

 No idea about what compilers are。 also talking through some of the policy。

 some of the sort of administrative parts of the course。 And if we're lucky。

 if we have time at the end， we'll start looking at really simple representation of a language and interpretation of programs in that language。

😊，呃。Right。Let's jump in。So this course is about compilers。 So what is a compiler。 Well。

 let's think about writing programs。 We start off by writing source code。

 And these are essentially text files， right， You could write it in a word processor like Microsoft word。

 They're typically human readable， yet what the computer eventually executes this target code is low level。

 not intended for humans to read and not very expressive。 It's often a really simple thing。

So how do we get from this source code， this high level representation。

All the way down to target code。And that is， of course， a compiler。

 A compiler is the program that would take us from this high level language down to the low level  one。

嗯。One quick question。 Can you hear me okay at the back。If you can't， let me know。

 I have the microphone on recording for the video。 But if it's hard to hear。

 I can definitely turn up the volume in here。Okay， so a compiler is this thing that takes us from the source code to the target code。

 high level to low level。嗯。So what we're going to be covering in this course is answering questions like how are programs transformed into machine code。

嗯。How to ensure that a program， be it at the high level or the low level。Actually， mean something。

Right， but it actually does some computation that we care about。

 And this touches on some of the issues that those who have taken C S 152。

 the programming languages course will be more familiar with。

One thing that we won't really touch on formally， but a key thing is to make sure that the source program。

And the target program， the thing that's actually executed on the computer。

 do actually mean the same thing。Right， other ways。

 programmers would be writing programs and the thing that would be executing would be doing something different than their intention。

We'll be looking at issues like how to manage a program's memory at the low level。 right。

 So this is something that often high level programs source code glossover。

 let the programmer not pay attention to things like how the stack is managed precisely。

 how the heap is managed。We'll also be looking at how we can analyze programs to discover important properties about them。

 things that might hold true throughout the execution of a program and ways that we might be able to improve the performance of programs。

A little bit of history about compilers。

![](img/bb5746d6ac0ae5f4bd7d7eb87fdb28e4_2.png)

Until about the 1950s， when programs， when computers were programmed。

 they're actually directly programmed in low level， in low level programming language in assembly。

In the early 50s， Grace Hopper， a famous computer scientist。

 developed the a nt system for the Uniivac。Machine and she later went on to contribute significantly to the design of Cobal。

 a incredibly influential high level programming language and。I believe。

That actually parts of mydot Harvard still writtenden in Cobal。And interpreted。In the late 1950s。

 the Forran compiler was built at IBM。 Forranran is was a precursor the C programming language。

 He looked at Forran code。 It would look relatively submitted， to parts of C。Then in the 1960s。

 the first bootstrapping compiler was created for the programming language Lisp。

 A bootstrapping compiler is a compiler for a language。

Lisp that's actually written in that language itself。InLis。Right， so this is kind of meta， right。

 It's circular。 You do need some way of actually interpreting your first version of the compiler。

But once you've used that compiler， a compile itself， then you've just got a program in Lisp。

 that's compiling programs and Lisp。In the 1970s， this idea of like high level languages and compiling really took off。

 And I think a lot of the technology， a lot of the key ideas。

 at least that we'll be looking at in this course were kind of developed in the 70s and beyond。

 there's been significant improvements since then。And I'd say at the moment we're actually in a golden age of programming languages for a few reasons。

 but there are hundreds， thousands of programming languages out there。

 many of them have very small communities and some of them are better designed than others。

 but at the moment it's actually really exciting that there are all these languages out there that we as programmers as users can engage with。

😊，But also， this opportunity to create languages， possibly for very specific purposes。

But to be able to。Very quickly， build and deploy a language is actually pretty exciting。

So it some of what we'll be covering in this class。Well， in many ways。

 help you all be better programming language designers and implementers， right。

 thinking about how we can take these high level programming language features。

 Con them into things that can be executed efficiently。Okay。

 let's take a look at the basic architecture of a compiler。

 So I mentioned that we have this process going from the source code down to target code。

 Let's look at this in a little more detail。

![](img/bb5746d6ac0ae5f4bd7d7eb87fdb28e4_4.png)

So typically， the first stage in compiling is to parse the source code that is to take this text representation。

 the sequence of characters and turn it into some kind of data structure。

 a more structured representation of the program。Once you have that representation of the program。

 there's a phase called elaboration。 Think about this primarily as type checking， right。

 You've got the data structure representing the program。

 and we're adding more pieces of information to it。 For example。

 inferring the types of expressions and so on。 maybe checking to make sure that the program is well typed or ruling out various kinds of errors。

After elaboration。Thiss lowering from this high level language into an intermediate language。

Possibly into several intermediate languages， going through a sequence of moving into progressively simpler and lower level languages。

 moving closer and closer to this target code， the assembly code。

There are optimization passes in these intermediate representations。

 There is ways of modifying the program to hopefully make it run faster。Now。

 this is actually an iterative process by performing one optimization that is transforming the code in a particular way。

 It might actually enable more optimizations， more transformations to improve the performance。

 And so， in fact， we made apply optimization several times。

 possibly until we can't play anymore and possibly just a small， finite number of times。😊。

At this stage， we're at some representation of the program。 that's not the high level representation。

 It's an intermediate representation， but it's not quite the assembly code。

So one of the last phases of compilation is cogen， going from some intermediate representation into actual instructions。

 assembly level instructions， then the machine is going to be able to execute。And again。

 when we're at that low， low level of representation， the assembly code， that might， in fact。

 enable additional optimizations。 So there might be some sequence of some iteration of。

 of this low level code。Now， compiler is typically broken into what we call a front end and a backend where the front end is referring to the first few phases of compilation。

 typically from passingsing down into lowering into some intermediate level of representation and the back end is taking the code in that intermediate level of representation and compiling it further down。

 performing the optimization， the codegen and so on。There are some compilers。

 notably the LLVM compiler， which we'll be looking at in more detail。

 where it might have different front end supporting different languages。

So these different languages have their own front end。

 which compile pile it down into a common intermediate representation。

And then a common backend will take that intermediate representation to produce assembly code。

Any questions at the moment。And in general， I want to encourage people。

 feel free to just raise your hand and ask if you have a question。

So I know when you're running code part of the process is also the machine code。

Is that a part of that we're gonna to ignore and' gonna to work on assembly code。

 Is that the level we're going to start。 Yeah， that's a great question。 In this course。

 we're going to be thinking about going down to assembly code。

 The process from going from assembly code， which is typically a textual representation of this low level into an actual executable。

 is typically straightforward。 There are a few subtleties involved in in assembly。

 But that step from going from assembly into a binary representation of code is relatively straightforward。

嗯。What's really interesting is that in modern， modern processes from that machine code。

To what actually gets executed is itself a really complex process。

 That's going be that if you're excited about this。

 I'm just this taking an architecture class will be really useful。 But essentially。

 what's going on is that that assembly language is a bit of a， it's an abstraction layer。😊。

RightAnd actually， the processor is actually doing a lot of work to take these。

Even though theyre low level instructions， it breaks it down into even smaller instructions。

 microcro operations that end up manipulating the components of a processor in a fine grain way。

 And there's actually a huge amount of scope for improving the performance of。

Of programs at this microcode level， which you should think about as being part of an implementation of a processor。

But the abstraction that the processor presents to us is essentially the assembly code layer。

 And that's as far down as we'll be going in this course。Thanks for the question。Yeah， wait。

 what's par become？Passing is the process of taking text and turning it into a data structure。

 a more structured representation of the program。So， thanks。没有。Over lowering。So don't worry。

 this is very much an overview of what's happening。

 We're gonna be spending a lot of time in this course looking at each of these phases。 And indeed。

 I'm gonna spend about 10 minutes going through some of these phases in， in more detail right now。

 So， you know， don't worry， you don't need to memorize this stuff right now。

 I'll get to it in in like three slides。 Ex a little more about lowering。 Yeah， these steps always。😊。

Is this。I信匹歌。嗯。Have these steps always existed。But it's a good question。

 I'd say this is a common architecture for compilers。 I don't know of the early compilers if。

 if that， if they had exactly the structure。Maybe some merely well。

 some languages without having type checking maybe wouldn't have had much of an elaboration phase。

 possibly some compilers， instead of having intermediate representations might have tried to go straight from a high level representation to a low level  one。

 But typically， the common this is representative of。Common architectures and compilers these days。

Cool， thanks。Yeah。So， you know， that took a hard so that。createative。

as you skip all the like target code later。タ分。Right， so this， this is really interesting。 I。

 I talked about how there's， we're gonna regard the assembly layer as essentially the abstraction level of processes and not dig down deeper。

 I think there's an exciting area of， of research and technology development。

 which is essentially the co design of hardware and software that can really enable。😊。

A different abstraction between between these layers， between the software and the hardware。

 And you're right， by kind of breaking that abstraction layer， there's the possibility of getting。

 say， more performance or or more effective use of the hardware。Okay。

 let me jump into talking about some of these。Some of these stages。So's thing about the front end。嗯。

Puzzling is actually broken up into typically into two pieces， Leing。And passingsing。

 Lexing is actually taking strings and breaking it up into chunks what that are known as tokens。

And so， for example， in a programming language， we might recognize certain keywords while W， H。

 I L E or else E， LS C， those would be tokens， putting together those four or five characters to be a token。

 Parsing is then the then takes a stream of tokens。And puts it into this data structure。

 an abstract syntax tree。So part of is something that happens in a huge number of applications。

 not just in compilers。 So really， it's the first step in going from data， you know， from stream。

 from a sequence of characters into more structured information。

One of the things about programming languages is that they're often。

The language is actually well defined。 if you think about passing， say。

 a query that you type into a search engine or if you have a calendar tool that's good enough to try and parse or interpret natural language to create an event appropriately。

 that's a lot more open and ambiguous than than the kinds of languages that we deal with in compilers。

in this。process of parsing。 It turns out there's a lot of relevant computer science theory。

 So if you've taken CS 121， when we end up talking about parsing。

 you'll be seeing a lot of familiar things， regular expressions。

 ways of defining those and recognizing or parsing them， contextfr grammars。

 which are analogous to push down automata， a particular kind of computational machine turns out to be equivalent to particular classes of languages。

And these abstractions are also going to show up in the optimization phase。

There's actually a lot of tool support for parsing。 Lex is a tool for Lexing。

 Yak stands for yet another compiler compiler。 So when that was created in the 70s。

 there were really a whole lot of tools out there to help with some of the some of the process of building a compiler。

 including parsing。 We'll be using a Paser generator tool called Min here。

 But there's also a lot of other ones out there。😊，Alright， the elaboration phase。

 I think about this as type checking。 So that is， we've got a more structured representation of our program of the text。

 But there's still a lot of information that we're able to essentially annotate the data structure with。

 So， for example， when we use a variable food。Which variable is it actually referring to There might be several declarations of a variable with the same names。

 So when we use a variable， what does it refer to， we might be figuring out types for all of the sub expressionions。

 and then checking to make sure that the various opera ends of operators are actually the appropriate type。

 And there might be other properties related to safety that is making sure that the program is free of certain kinds of errors or also security。

 making sure that the programme is。lessss likely to have vulnerabilities。

 So there might be some other checking that we're doing at that stage。

After elaboration comes lowering， this idea of moving from this high level language into a sequence of intermediate representations。

 So these intermediate representations are simpler than the higher level language。

 So the process of lowering is really about taking features in these high level languages and converting them and removing them。

 figuring out how to express them in the simpler lower level language。 So， for example。

 we might take a whole bunch of control flow constructs， like four loops， while loops。

 do while loops and so on。And all of them get compiled into a language that only has gos。That is。

 you have an instruction that says， go back to this instruction。

W's actually programmed in language with Gotos。What language was it。这些人。对。And see。

 And you actually use Gotos and see。No， okay， do not use Go tos and C in general。

First programming language language I used was basic。 and in basic。

 that was pretty much the only control flow structure was。

 was a go to command telling me which line of code to go to。Okay。

 there might be other high level language features that we're trying to remove。 So， for example。

 objects， functions that are passed around as values。 So those who have programmed a nocal。

 passed around functions as values， but clearly at the low level。

 the computer doesn't have a notion of function。 So somewhere or other in this lowering。

 that idea of a function as a value gets， gets compiled away。There might be things that， you know。

 at the high level language， the language might say， if you try and access an array out of bounds。

 an exception is thrown。Right， so in the process of lowering。

 we might be making those tests explicit， actually putting in code that says， hey。

 you're trying to access this index， Is that less than 0， Is it greater than the length of the array。

 And if so。Raise this exception。In the optimization phase。

 what we're doing is rewriting expensive sequences of operations into sequences that are less expensive。

 So the kinds of things might be， if somewhere in your code， you've got an expression 3 plus 4 or。

You know， we actually know the opera ends to that addition。

 There's no need for us to compute this every single time we run the program。 During compilation。

 we could simplify that expression 3 plus 4 to the expression 7。

There might be a computation inside a loop。And we might be able to analyze the program and realize that every time through the loop。

We're actually doing the same computation。So we could we again。

 don't need to do it every time we go through the loop。

 Maybe we can move that computation out of the loop。Just do it once。

And save ourselves time in the body of the loop。There might be more sophisticated optimizations possible。

 We might realize that each iteration of a loop doesn't depend on the previous iteration。

In which case， if we have parallel hardware， which， of course， modern hardware is。

 almost all of it is parallel。 It does have multiple cores。

 We could compile the program to take advantage of that， to parallel iterations of the loop。

And there's， of course， many other optimizations that are possible。

 and we'll be digging into some of them。Now， the final phase was this code generation translating intermediate code into target code。

There's a whole lot of steps involved in this。 One is that in our intermediate representation。

 we might essentially be using local variables。But the processor doesn't have an unbounded number of local variables。

 It has instead a small， typically a small number of registers that is。

Fast memory locations that are on the processor itself。

And so one of the phases of cogeneration is actually register assignment。

 assigning these local variables into registers to make sure that when we need a particular variable。

 then it's going be available in a register for us to use。

Choosing which low level instructions we're going to be using in some architectures。

 we need to be careful about how to schedule those instructions to be as efficient as possible。

 And there might be various other specific optimizations for a given architecture。

 for a given machine。Okay， any questions at the moment about this really quick overview of the compiler pipeline。

Seems like a lot of steps in the pipeline。So where is current compiler research trying to optimize on。

That's a great question。 What is current compiler research trying to do。I'd say，Some of the。

The optimization and analysis side is actually， I think some of the most interesting research is going on。

 So reasoning about programs is actually hard。 reasoning correctly about programs is。

 and precisely about them is really hard。 And so there's actually some quite sophisticated work on。

Examining the programs。Understanding what they're doing。

 perhaps towards optimizing them or perhaps towards proving various properties hold of them。嗯。

Taking that in some ways to an extreme is actually proving。That the result of a compiler is correct。

That is。Compr is a complicated piece of software。 We're gonna be spending， you know。

 a semester learning about how to do this， how to build a particular piece of software。

There's a lot of bugs and compilers。And this should worry you。Right，The fact that you write a code。

 you write some code， even if you're a fantastic programmer and you manage to write code that's free of bugs。

 free of errors。😊，It's producing。Machine code that's executed on the machine。

And you do not look at that machine code。 right， You're not looking at the assembly code and making sure that that's doing what you expected it to。

 It's really not human readable。 It's far too complex for。

 for humans to look at and really understand what's going on。But if there are bugs and compilers。

 then that machine code， the thing that's actually executing on the machine， may not be。

An accurate reflection of the code that you wrote。And I think we'll be talking about this。

 I think I might even have a lecture on， on this later in the course。

But there are a lot of bugs and compilers。 And so this idea of being able to verify， formally verify。

 formally prove。That the output of a compiler is a correct reflection of the source code is incredibly powerful。

😊，Right。Beyond that， showing that the output of a compiler is actually enjoy certain security properties。

 more than just being correct。But actually doing the appropriate thing in the presence of an adversary is trying to make something bad happen。

So those are some of the areas about kind of compiler research that I'm that I'm most excited about and。

 and aware of。 That's a great question。 I think there might be time late towards the end of the class。

 You know， So in， in November， December， that we might talk about kind of current directions and topics。

😊，In compiler research。Yeah， thanks for the question。There's an no one here。

 we compilers that satisfy。There's several verified compilers out there。

 The most well known is composite。Whose primary creator was actually the main creator of the Ocaml programming language？

But there's also other ones out there。 The Con is a verified compiler for C to X 86 code。

 There's a compiler K M L， which actually compiles ML code。

 So of which Ocal is a variant of M L down， I think to X 86 as well。

 And there's a few other verified compilers。错吧。这是。How do you compilers to compilers？

How to compilers compile compilers？A compiler is just a program。Right，You're going to be writing。

You'll be， you'll be writing parts of compilers。 So you're writing a program。

And so it's just another input to a compiler。So if you have a compiler， that's great。

 You can write whatever program you want， you know。😊，Right。You know， your， your data match。

 program rate， sorting algorithm， write a compiler。 It's all， in many ways。

 the same with a respect to a compiler。Right， so the question of how do you bootstrap a compiler。

 Yeah， the first compilers were written in assembly， written directly in assembly。

 And then they were able to compile high level languages。 And once you have that， though。

 you could end up using that high level language to write a compiler。For that high level language。

 and。And continue from there。So that's the problem of bootstrapping。

 How do you actually build a compiler。To， to get what you want。Like there's a lot of design choices。

For optimization and。Are there specifics of people joining words or resume？あさな。Yeah， there are。

 I agree。 There are a lot of design choices to make with respect to optimization。Yeah。

 there are some。Common optimizations that are kind of well known。

 as we'll get into when we look at optimizations。Typically， it's actually a bunch of heuristics。

 There is typically。You， you， you're transforming code in the hope that it will run better。

 Some things we can be pretty confident on， replacing 3 plus 4 by 7。Highly likely to go faster。

 But there are more complicated optimizations where it's the case that it might actually slow things down。

 So， for example， function and lining， you might say， you know， here we're calling a function。

And as we'll dig into， there's all this overhead at runtime of calling a function for those who have taken 61。

 You know， you know， you need to do all the stack manipulation in order to call the function。

 So maybe what we could do is take the body of the function。And inline it。

 replace the function call with the implementation of the function。So that seems like， you know。

 if it's a small function， that might actually be worth it。But in line。

 the function might end up doing something like increasing the overall size of your code if that function is called many times in your program and you're replacing each function and with a copy of the code。

Maybe the size of your executable is bigger now。But even if it's not bigger。

 it's gonna be maybe laid out differently。And this is gonna have an impact on， let's say。

 the code cache。So that is the fast part of memory that pulls in the instructions that are going to be executed。

And so changing the size or even the layout of inexecutable might have these impacts on， for example。

 the， the cache behavior of your program。 And typically， we never end up proving。

That an optimization is going to improve things。Where we just kind of use heuristics and and experience to try and figure that out。

 So there are a lot of design choices。 And in some of the homeworks。

 youll be getting the chance to kind of explore around and figure out what sort of combination of optimizations is going to work best。

同意。Okay， let me switch gears for a bit。 I've been giving it a bit of a a very brief overview of。

 of compiler pipeline。 And the course is really about digging into that and getting some handson experience。

 programming it。 But let me turn now and kind of talk about the course itself， right？

 So why might you be interested in taking this class。😊，嗯。

I think one of the things I think is cool about compilers about this course。Is。

Compilrs are just critical infrastructure for us， as programmers definitely。 But also。

 I'd say for the world at large， right， the programs that are being executed are。Were compiled。

 right， Mach are running programs。 And so this is used。 compileilrs used incredibly frequently。😊。

And critical software relies on the correctness of compilers to be running。

 So think about this as code in your car， in your self driving car in your the nuclear power plant have been compiled。

And are running。So this is kind of peeling back some of the abstractions on this critical piece of infrastructure and figuring out learning about how it works。

 how it actually operates。It also gives us an appreciation for language features， you know。

Why does a language have this particular feature or why doesn't it have it。

 Why would it be difficult to add in that language feature and still maintaining， for example。

 efficient execution。So this kind of peels back those abstractions and lets us learn more about definitely how languages are implemented and also adjacent to that。

 the design of languages。嗯。We've already talked about the idea that a compiler is something that we just use incredibly often。

We've also already touched on the idea of compilers and the relationship with architecture。

So I think for those who are interested in hardware and architecture design。

I think one really needs to be familiar with compilers。

 There are some famous cautionary tales of Intel releasing new processes。

 but not having appropriate tooling。 That is not having compilers available that were able to take advantage of these new instructions that were being that were made available in this processor。

 And as a result， people weren't able to use those processes effectively。

 there wasn't a compiler that would actually get the the benefit， of these new processor。

 And as a result， those processess failed。嗯。So， we talked about this idea of co design。

 of co designing software and hardware， compilers and hardware together to be able to make really effective things。

For those who really enjoyed 51， not just because of the Ocal programming。

 but this idea of abstraction， this idea of creating。😊，The right abstractions。

 designing things appropriately so that it works， not just works， but works elegantly。

I'd argue that in many ways， a programming language is like the ultimate abstraction。Right。

 it's not just the set of functions， the set of data structures you're using。

 It's the way that you express meaning that you express computation。

 So compilers are a key part of this idea of language design。嗯。

Facebook's hack language is essentially their version of PhP。呃。So， from an interpreted language。

Removing and adding features in order to be able to compile and run it effectively。Right。

 that they weren't able to get the， the kind of performance and reliability that they wanted from。

 from this interpreted code。Some of the key learning outcomes of this course。

 you're gonna be learning。One of the things I like about compilers is it's one of the places where we see some elegant theory。

Meeting， practical engineering。And this is both with respect to， for example， parsing。

 already talked about how there's a whole lot of really beautiful theory behind parsing。

 And now we're concerned about actually building parers that can ideally par millions of lines of code in seconds。

But more generally， there's also other concepts， be it type checking or the correctness of translating language programs from one language to another。

 some really elegant theory。 And we're actually building the tools that bring this into practice。

We'll be looking at Leing and passingsing and interpreters as part of this course。

 thinking about high level languages that implemented in machine language。

 We're going to be targeting X 86， the Intel X86 architecture。 So as a result。

 you'll be learning more about X 86， probably to about the same level or a bit deeper than you learn in 61 for those who have taken CS 61。

We're going to be learning about common compilation tools， GCC and L O VM。

 two of the the main compilers will' be focused on on L O VM and we'll be using L O VM like ideas in the compilers that we build。

Sorry。Hit the wrong button there。嗯。I think this is going to be one of the。

For most students taking this class， itll be one of the more implementation。

 heavy courses that they've taken， working with complex software。

 complex specifications as we build parts of the compiler。

 So I think as a result of taking this course， just by shared dit of writing。

Sophisticated and complex code。 you're gonna learn a lot。

 You're gonna be a better programmer as a result of taking of taking this course。

 even though we're not gonna directly be teaching explicitly teaching principles of good programming or software engineering。

 It's more just we're gonna be， you're gonna need to figure out how to write programs in the large。

Preparation for this course， as you have hopefully seen。

 I suggest that you've taken both CS S 51 and 61。Indeed。

 I often describe this class class as CS S 51 meets C S 61。

 We we go from the high high level abstraction ideas and covenant CS S51 down to the low level system details that C S 61 focuses on。

If you've only taken one of those， it's C， S 51， I'd say is。Probably preferred。

 And that's because in this class， we'll be implementing the compiler in Ocal。 And， of course。

 those who have taken C， S 51 have strong knowledge of Ocal。

In homework 1 will kind of be a refresher on Ocal。 and for those who are newer Ocal will be an introduction to Ocal。

 But if you didn't take CS S 51， just be aware that you might need to sit aside some additional time to self-stu Ocal and to get up to speed on it。

 And definitely the first couple of assignments is gonna be useful to make sure that you're getting up to speed。

 if you're in that situation， excited about taking the course， having taken C S 51。

 please definitely reach out to me or the rest of the course staff and we can help make sure you're connected with with the resources and are on track to getting up to speed by the time you'll need to be really comfortable with Ocal。

We suggest 61， because you do need to know some information about low level operation of a computer。

 If you haven't taken 61， you can likely self learn the parts that are relevant。 For example。

 being familiar with two complement arithmetic that is low level representation of signed entitiess at the bit level。

The first two projects are going to be a good time to get up to speed on this。

 but more generally throughout this class， throughout all these assignments regardless of your preparation。

 please never hesitate to ask something in lecture on the Ed discussion board to the course staff。

 If you don't know something if you feel something is unclear or confusing。

 It's likely others in the class have similar questions。 So you're doing everyone a favor if you ask。

Speaking of the core half， we're really lucky to have some excellent T Fs。

 Cameron and Verun are actually here。 I didn't see Whitman。 He's not here， right。😊。



![](img/bb5746d6ac0ae5f4bd7d7eb87fdb28e4_6.png)

So Cameron Ver run up the front， graduate students studying programming languages and systems。

 Whitman's undergraduate senior。 You can reach all of us at CS， S 1。

53 staff or on the Ed discussion board。 All of us will be paying attention to that。In general。

 if you have a question about the course content， it's better to reach out to all of the staff。

 either on  Ed or by email。 that'll give you a quicker response than if you email individual staff。

Of course， if it's something about the administration of the course or any extenuating circumstances。

 please reach out to me directly。

![](img/bb5746d6ac0ae5f4bd7d7eb87fdb28e4_8.png)

Okay， technologies that we'll be using in the class。 We are using the Canvas website。

 Hopefully you've all discovered that we're going be pasting。

 putting things like the lecture notes for the lectures up there。

 releasing the homework assignments on Can and also this is recorded so youll be the lecture videos should be available pretty soon after the lectures and on the Panopto page of the Canva website。

The Ed discussion board access it via canvasva， there's a link to it in the menus。

 That's a great place to post questions about the course and benefit from your peers knowledge as well as from the course staff。

 So I highly encourage you to use Ed definitely for things like setting up your environment or any low levelvel problems you have and of course。

 use your best judgment when you're asking questions about whether it is revealing too much about an answer or the solution to homework。

😊，We're gonna be submitting assignments on grade scope。 A lot of the grading on grade scope will be。

Automated。 So that is we have test suites that we will be running。um。When we release the assignments。

 we're going to be releasing some of the tests that we'll be using， but not all of them。

So when you run it locally， you're gonna get。You know。

 the tests we provide will help you get some assurance about whether your code is correct or not。

 But we are holding some tests back that we're gonna run on grade scope and you're not gonna get the results when you submit your assignment。

 That is when you submit to grade scope。It should be pretty much a black box other than letting you know that it's compiled。

 So I'll mention this now。 I'll try and remember to mention it later as well。

 but you should write your own test cases， right， You should absolutely write more test cases than we are providing you with in the first assignment we're actually giving you points based on the additional test cases you're writing。

But what's really when it's really important to do this is in the subsequent assignments。

 when we're not going to be grading you directly on whether you're providing whether you're writing your own test cases。

 we're just going to be grading you on whether your code is meaning our specs。Okay。

 so those are the education technology tools we'll be using。 As I already mentioned。

 we'll be writing in Ocael。 I'll talk a bit more about why Ocael a little later in this lecture。

It's up to you to use what development environment you want to use。 We recommend visual studio code。

 it's a pretty nice A DE for Ocal， but really whatever you're comfortable with。 We will say， though。

 that you should be using version 4。14。1 vcal。 And that's what we'll be using to grade your code again。

 So you want to make sure it compiles against that。4。14。0 is broken。 So don't use that definitely 4。

14。1。And of course， if you want to do use your own version control using Git or whatever else you want to help manage your code。

 go for it， we just ask that any repos you use are private。

 So please don't put your solutions to the homework assignments out on the web for others to find。

Okay。There are no sections in this class， but we will be having lots of office hours。

 We'll be setting those up next week， we'll announce when they are and we'll be posting them on a calendar on the course website。

We're gonna have pretty good coverage of through days of the week。

 but likely to not have a huge number of evening or weekend office hours。 okay。

 it's gonna most of the office hours are gonna be business hours， Monday to Friday。

If you can't make it to office hours after we post these， let us know and we'll do what we can。

 We might be able to move some of the hours。To a time that。To a time that you' were able to make。

I'll talk more about sort of making the most of office hours in just a moment。

 But I would say that office hours are， I'd say， a key part of the learning and engagement in the class。

 So hopefully， you are able to make it to some。I've already mentioned the discussion board。You。

 it set up so that you can post anonymously to your classmates。

 that is you can post questions where your classmates don't know who are， you are。

 but the course staff will。 We've already talked about email addresses and emailing。

All the staff in general。There's no required textbook for this class。

 but you may find it useful to look at this textbook by Andrew Wel。

 Modern compiler implementation in M。 L。 It is available online through the Harvard Library。

 There's a link to that in the course website。

![](img/bb5746d6ac0ae5f4bd7d7eb87fdb28e4_10.png)

In general， though the lecture notes and the material we're giving out as the homework should suffice for you to understand things As I mentioned。

 the lecture videos and these slides in Pf form are going to be available in general I'll try and have the lecture slides release the night before lecture if it's helpful for you to kind of skim over those have an idea about what's coming up。

I'm happy to say that in this iteration of compilers。

 we're gonna be participating in the embedded ethics program at Harvard。

 hands up if you've had an embedded ethics module in a course。😊。



![](img/bb5746d6ac0ae5f4bd7d7eb87fdb28e4_12.png)

Keep your hand up if you've had at least two。3。4。Uncountable， yeah， awesome。 great。

 So this is awesome。 embedded ethics is actually this really innovative approach to thinking about ethics and how that relates to technology。

 And the idea is it's embedded。 It's actually embedded in courses that cover technical content like this class with the idea being that we want you all to get used to thinking about the bigger questions。

 So beyond how do I write this past of the compiles or it works and passes， you know。

 these low levelvel technical questions。😊，To get in the habit of taking a step back。

And thinking about， what am I doing and how does that relate to。Humans to society。

 to the questions of， should I be doing this， right， to unforeseen consequences。

And the hope is that you get used to that in the classes so that when you're not in class。

 when you're out there。You know， leading government， leading industry， leading teams。

 creating new businesses。ThatThis is something that you're also thinking about because not。

 nobody is probably probably nobody is going sit you down and say， okay， everyone。

 we're gonna take the week and think about the ethical implications of the startup technology that we're doing。

 Instead， that's on you all to be thinking about。And so。

The embedded ethics initiative is a really great collaboration between philosophy。

 the philosophy department and computer science。 There will be one lecture and an additional assignment beyond the six homework assignments for that more information on that coming soon。

 And if you want to learn more about the embedded ethics initiative the website actually is lays out a lot of really interesting information。

😊，Any questions at the moment on anything I've talked about so far。Yeah。

 how does the came familiarity need it to。Like CS 152。What do you think of using ChaBT to learn？

Great questions。For Ocal。 So1，52 didn't really require much Ocal at all。 definitely， I don't think。

So generally， when students are asking me， hey， should I do 51 and 1501，52。

 I'm generally telling them both， because what you learn in 51。

 some of the ideas of abstraction are design are really worthwhile。

 And those are gonna be useful and relevant in this class as we build complex software。 And also。

 I'd say the familiarity， you know， becoming fluent in Ocaml is something that I don't think 152 really teachers。

 I think it's possible to get through the Ocaml program in 1，52。

Pretty much kind of copying and pasting without really understanding the language features。

 So I'd say if you've done 1，52 without 51。Be prepared that you might have some ramp up speed on getting familiar with Ocal。

Why are we writing an Ocal， So it is actually a really great language for writing compilers。

 It was actually M L， of which Ocal is a member of the M L family。 M。

 L actually stands for meta language right， It was Oca M L was actually designed to write compilers and interpretism。

😊，If we have time， like I say， we'll see a really simple Oaml program that is representing a language and manipulating it。

 And it turns out that it's really concise and simple。In part， because it can use the。

Ocal algebraic data types。To represent abstract syntax trees really elegantly。

 And it's easy to manipulate those and compute with them really effectively。Also being a type safe。

 mostly pure functional programming language。 for those who have gone through 51 and drunk the cool aid。

 you can write some pretty sophisticated things very succinctly。 and， and a lot of the time。That's。

 that's a really powerful way of letting you get to the core of a computation without worrying about so much of the administrative things such as iterating over data structures in a painful way。

I mentioned that that our first homework will refresh us on Ocal and the canvas website。

 the resources page has some links to additional information， tutorials。

 reference guides and so on for Ocal。I'll get to your chat GPT question just a moment。

 I've got a couple of slides on it。Assessment in this class。 it is really implementation heavy。

 and that's reflected in the assessment。 about 70% of the course is going to be based on the six projects that we'll be working on plus the embedded ethics 1。

 they're not going to be weighted equally。 So， for example。

 the Ocal homework assignment is not as intense or involved as most of the later ones。

 There will be a three hour college administered final exam with 20% of the grade and 10% on participation So for participation this's really engaging in the course material in the course。

 and that might be by answering and posting questions on Ed by attending lecture。

 engaging in discussion， attending office hours key part is actually going to be participating in study groups and supporting the learning of others in this course。

 I'll talk more about that soon。 but I really do think that a key part of learning this is hands-on doing and learning from your peers。

For the projects，6 projects， most of them are about implementing parts of a compiler。 in general。

 theres you're gonna have about  two to three weeks per project。 Home one's a little exceptional。

 You have one week for that。You' gonna need to be pretty good about managing your time。

 There are going be multiple projects out at the same time。 That is。

 I'm going be releasing the homework projects once we've covered the material in class to enable you to work on them。

 and occasionally， the due date for an existing homework is going to overlap by about a week with the release of the new homework。

So you're gonna need to look at the rhythm of， of the homeworks。

 figure out what else you have going on in your life and other courses， other commitments。

 and be really good about actually working on this。You are gonna need to start early。

 I'd say that when in general， code often has really high variance in the amount of time you expect it to take。

Right， for example， imagine you have a bug that's hard to track down。 Suddenly。

 you've blown several hours on this thing。Rightright。

 and the fact that you had that bug was almost random。Right。

 if it's a small bug that was difficult to figure out。

 So it can be high variance on the amount of time。 I really encourage you to start early。

We are giving a lot of late minutes in this class，10 days worth of late minutes，14400。

 for any one assignment， you can use up to three days worth。

 three days so that we're able to grade those and give you give you back feedback in a timely way。

 but that's a lot of flexibility on， on the on the assignments。😊。

The late minutes are not meant to be a substitute for starting early。Okay。

 the lay minutes are really there to avoid you having a whole bunch of deadlines all falling on the same day or two。

Okay， so ideally， you should be thinking ahead and thinking about when you wan to use your late minute to move the deadline and give you flexibility。

 But maybe you also want to try and submit a homework early to avoid a crunch， okay。um。

Lamans are also not meant to be a substitute for to be used。 if there are extenuating circumstances。

 If you have health issues， there might be physical health， mental health concerns。

 Extenuating circumstances， family emergencies。 please just reach out to me or have your resident dean do that if you prefer and we'll figure out a way to make sure that we're supporting you as best we can in doing what we can to help you succeed in this class。

The projects themselves， if we think about the compiler pipeline again。

 the project projects we have actually fall in different stages。

 we're gonna start off with hello Camel， saying hello to Ocael again。

But then we're gonna be looking at the back end we're targeting X 86 in this class。 Homework 2。

 you're actually gonna be implementing an X 86 simulator as a way to try and really understand what X 86 code is doing。

We then jump back in the compiler pipeline and look at an intermediate representation， L O V M。

And so in the third homework assignment， we're gonna be compiling a simple subset of N of V M intermediate representation down to the subset of X A X 86 that you've done in homework 2。

We then go to the beginning of the compiler pipeline and look at pasing and Leing in a simple front end。

And then in homework 5， we essentially look at elaboration and add some more language features。

 So we're focusing on the front end。And a bit of code lowering。And then in the last time。

 Mocomomic 6， we'll be looking at data flow analysis and optimization。

 So that is techniques for understanding what a program is doing and using those results to try and make it run faster。

These homework assignments are intended to be done individually。

 That is all the code that you submit should be your own code。

You shouldn't be sharing your code with others。 You shouldn't be accepting code from others。

 You shouldn't be looking online for solutions to the homework。

And you shouldn't be posting course material publicly through GitHub or otherwise。That said， though。

 your peers and study groups are an incredibly effective way to learn。

 So I want to make sure that you are able to be talking about this work。

 about these projects with each other。😊，So to try and be clear about what that means with the guidelines for working with others。

 it's totally okay to talk about high level ideas， right。

 understanding concepts that we've presented in class。

 talking about how you might go about approaching and implementation。

 One of the key things to think about with respect to this high level discussion is you should be using words。

Right， not code。So this shouldn't be about like， oh， we'll take a look at what I ended up writing。

 This shouldn't be about writing up code on a whiteboard to share it。 Okay。

 this is about the concepts， the words。It's also okay to talk about low level details。

 If it's about how exactly do we use this Ocal data structure。

 What is this weird syntax error or type error that I'm getting， How do we resolve it。

 Also totally fine to be working on that low level stuff。It's really the stuff in the middle。

That you' got to be careful about。Right to make sure that you're not， for example， sharing code。

 taking the key insight about what's going on and sharing that with somebody else。

If you river in doubt， please ask the course staff to clarify what is and isn't appropriate。Okay。

 you are not going to get into any。Issues with the Onor council。

 if you end up talking with core staff about it。O。And so we just encourage you to do that。

We should also talk about the elephant that's in the classroom。 And， of course。

 I do mean generative AI。 So tools like chat， GT Bd and otherwise， Yes， this was。

 this image was produced using Dli at generative AI。So generative AI tools are really fantastic。

 I really think theyre a phenomenal leap forward。 And for programmers。😊。

They're an amazing and powerful tool。That said， a key part of the learning in this class。

key part of the pedagogical approach to this is that we're going to be understanding these concepts of a compiler。

By implementing it。By going through that thought process。

Of figuring out how to take these high level ideas and how to instantiate that in code。

And that's why we have those guidelines about working with your peers。 right。

 Let's understand the high level ideas。 Let's not， let's spend as little time as possible with painful and annoying low level errors。

But that hard work， that time you put in in the middle。

In figuring out how to design your code and figuring out the right way to express that concept and code。

 that's where the learning actually happens。 And that's how this class is designed。

 And so for the same reason。That you're gonna be cheating yourself out of the learning benefit。

 If a peer gives you code。You'll be doing the same thing if you end up getting chat GT to write large parts of the code for you。

So the guidelines in this class for using geneative AI are actually pretty similar to the guidelines。

For interacting with peers。Okay， for exactly the same reasons。That is。

 it's okay to use it for higher level ideas。If you want to ask chat ET to explain a concept。

 S something， Talk about how something interacts with something else。 Go for it。

 And this idea about using words rather than code is perhaps a really good guideline。

 If you are talking， if you're doing conversation， not code。With a gene a tool， fantastic。

 Use that to help triangulate your understanding of the concepts。😊。

It's also O to use it for low level details。If you wanna ask Cha AT to give you some example code for how to use Ocal's set data structure。

 Great， that can save you tens of minutes looking up documentation， go for it。It's， again。

 that mid level that's concerning， right， that that youve got to be careful with。Well。

 you don't want the generative AI to be producing large portions of your assignment for you。

My suggestion is that you disable the automatic cogen tool where。

If you end up writing high level comments as you're starting your code。

 that you'll get auto suggestions for you know， entire files， disable that。

So that if you want to end up using chatt ET for low level code。

 go and ask a specific question that's kind of isolated from the context of the compiler itself。

Sorry。😔，嗯。诶。And then I also just ask that when you submit your homework assignments。

 please just put in a comment in the files， just if citing it essentially。

 So just saying how you what tool you're using and how this is the first time I'm offering the compileless course with such weight availability of generative AI tools so we're going to see how it goes I'm actually really interested to hear from you whether you end up feeling that generative AI was supporting your learning in this class or if we're going to need to think about other ways to achieve the pedagogical aims given the technology。

Any questions at the moment about any aspect of this， gender AI， the academic integrity。

 policy and so on。Yeah， canny。えと。ここちて。Do like they set to take that amount of time or is it。

That's a good question is。How intense are those two to three weeks going to be。嗯。

I aim for the course to take a total of about 12 hours a week on average， meaning， you know。

 two and a half hours in the classroom。 So approximately 10 is hours outside the classroom。

 call that an hour or two wrapping your heads around， you know。

 covering the material in class to make sure you understand it so。

A naming for about 8 hours a week of coding。But like I say， there's high variance encoder。 And I'。

 I'd say even。 so it's hard to predict exactly。You can definitely look at the Q scores for this and see the range of time that people take。

 But I will say， I do think starting early is key because of this variance and also figuring out when the right time to ask for helpers。

嗯。In the sense of figuring out。1， I would suggest not starting to code。

With the exception of homework  one， which is really just taking you through some O camera refresher in general。

 not starting to code until you understand the problem is useful。 I think this is true in general。

 right， often when you're designing a system， the last thing you want to do is start coding。Right。

 figuring out the design is， is kind of key and is going to reduce a whole lot of debugging later。

 The same thing applies here。 Understand the concepts。Look at the， look at the skeleton code。

 understand what you're actually meant to be doing before you start writing code。

Figure out when you're stuck。Right， when you're actually spending a whole lot of time。

Just moving code around， tweaking code。 and， and you're stuck in a loop。

 It's easy to spend a lot of time there。 So figuring out。

Recognizing that and then seeking help from a peer from core staff or so on is key。So， yeah。

 it's programming intensive， but this isn't meant to be a class that consumes your entire life for the semester。

That's the intent。Individual mileage may vary。I'd say if you， if you do feel like you're spending。

 you know， more than 15，80 hours a week on this class， get in touch with us。 It's。

 it's not something that we're want to happen。 So it's probably good to touch base and find out where the time is going and what's challenging。

Any other questions。对。AI might be a bit early for the final exam。Is it more of a 51 style final exam。

 61 style or not？Let's delay that。 Just， I got about 10 minutes left。

 And there's a few other things I'd like to cover。 And we'll think about the final exam closer to the final exam。

um。Okay， I mentioned study groups。 so I think learning from each other is key。

 And I realized that people come into this class with varying levels of social capital。

 That is varying levels of how much they know other people in the class。

So one of the things we're gonna be doing is for homeworks 2，3，4 and 5。

 we're going to be randomly forming study groups。 I want will emphasize that the homework assignments are individual。

 You are writing your own code。 This is not group work in the sense of you're not gonna be。

 your assessment is not going to be based on what others in the group are doing。

But we are gonna be connecting you with people， other people in this class。

 And those study groups are a key way of engaging in the material and working with each other。

 My personal opinion on study groups is that theyre to everyone's benefit， if somebody。

Knows more about the material than somebody else。Actually。

 needing to explain that to others is an incredible way to actually consolidate and clarify your knowledge。

 Teaching is the best way to learn something。 And somebody who's been teaching here at Harvard for 14 or 15 years。

😊，Yeah， my understanding material before versus after teaching a class is immense。

RightAnd so the same is true when you get to participate in study groups。 And， of course。

 students who are less comfortable， less familiar with things。

 being able to have a peer to talk with about it and to talk through ideas is incredibly useful。嗯。呃。

We will bell be building up to this for homework2 and doing some surveys to help match you in an appropriate way。

 And at the end of each survey， we're actually going be asking who contributed to your learning and how。

 and how you contributed to the learning of others。 And this will be part of。

 and then we'll be looking at these surveys and that'll be feed feed into some of that participation grade。

You're welcome to opt out of the study groups。 If this is something you really， really strongly feel。

 you don't want to do。 That's okay。 But I will point out that it is one of the key ways of participating and contributing to the learning of others for a significant portion of the total grade。

😊，Happ to talk about this more。 This is something an experiment when we're trying this year for the first time。

 So feedback will also be seeking feedback on it， but I really do think that I want to make sure that everyone has the opportunity to learn from their peers in addition to the lectures。

 the course staff and the course material。part of that。

 that really falls into this idea that I want to create a learning environment that supports everybody in the course。

 diversity of thoughts and perspectives， experiences and honor the people in this class and their identities and their backgrounds。

So what that means concretely is if there's particular set of pronouns you wan to use。

 if they're notdding right out Harvard， let me know。

If you feel like your performance in this class is being impacted by anything that's going on for you outside of the classroom。

 please don't hesitate to get in touch with me or if not me， then another core staff member。

 your resident dean， just make sure that you're reaching out to the support networks that are offered by the college。

嗯。呃。I also want to acknowledge that I'm in the process of learning as many of us are。

 And so if there's anything that happens in this course in person in office hours on Ed or other ways or on a study group that makes you uncomfortable。

 please let me know about it。 I really do appreciate hearing feedback on this。

It's the way that we actually make sure that we're try to make sure things。Do we do better。

More generally， if you're ever struggling， just want someone to talk to。

 you're welcome to reach out to me。 I'm one of the support resources that's available to you。

 And I'm really happy to chat about any aspect of this course or anything else。😊。



![](img/bb5746d6ac0ae5f4bd7d7eb87fdb28e4_14.png)

We all learn differently。 This is part of the reason why I make lecture videos available and lecture notes。

In general， though， if there's any aspect of the course that's preventing you from learning or excluding you。

 please let me know as soon as possible。 for students with accommodation letters from the Disability Access office。

 Please get them to me sooner rather than later。 that'll help me in supporting you and more broadly I'd recommend the academic resource resource center is' a great resource for academic counseling for peer tutors don't know how many compiler peer tutors will have。

 but but they're a great starting point。As well as things like they have a whole bunch of interesting workshops on。

 say， time management， study schools， accountability groups and so on。

 So fantastic resource for the college to have。😊，I tend to like to be explicit about the expectations for the course to make sure that we're all on the same page。

1st of all， I expect that you're going to do well。 This is not a class where I'm grading according to any particular curve。

 If everyone does phenomenally well， fantasticastic， you can all get great marks。

 So my expectation is that you all are going to do well。😊。

You also expect you to stay up to date on materials， right？ So the course moves pretty fast。

 We've already talked about the fast rhythm of the assignments and order to。

 in order to be prepared to do the assignments， you actually need to stay up to date on the lectures。

Right， so that means you're gonna need to be。 you know， you're going to need to。Stay up to date。

 The recorded videos and the slides can help with that if you happen to miss lecture。

 for some reason。But getting more than a lecture or two behind will make it harder to stay up to speed。

 If you're worried about falling behind， if you feel you are， please reach out。

I expect you to look after yourself。 That is get enough sleep， eat well， take care of yourself。

 Try not to do too many orniers。 Try not to do any orniers。

 if that's really going to disrupt stop you。 I know it did for me in undergrad。

 I managed to get through all of undergrad without any orniers wasn't until grad school that I really started to get short on sleep。

嗯。Attendance， I don't actually take attendance at lecture。 And like I say， I appreciate that people。

 different people learn differently。 Some people like。Watching the lecture video at two time speed。

 some like being able to pause it， rewind it and hear parts again。 But I will say。

 figure out for yourself what works best for you。 And I'd say for a lot of people。

 actually being physically here is incredibly helpful。 be it in terms of focus。

 be it in terms of making a commitment to actually stay up to date with the material。

 both seeing it life。 And， of course， the chance for interaction for questions we go along。

 is helpful for learning as well as making it more fun and enjoyable for me and others in the classroom。

 So so participating engaging is great。😊，Related to that devices in the classroom。

 I appreciate that for some people having a laptop or a tablet or something out can really help them with their learning。

 be it from taking notes or from looking up information for many people， though。😊。

Be honest with yourself。It's a distraction。Right， and having the device there means that something you w to pull out。

 shop online， check social media or something。 So what I typically do in。

In my classes is designate some portion of the rum is device free。And so if you're sitting in that。

Part of the classroom， you're committed to not pulling out a device to distract you or others around you。

 and this will help to let you focus and others around you focus on the material。

Quick show of hands at the moment。 Who would like to use devices in class。Okay。

 what I'm gonna say is if you w to use a device in class。

 please sit in this half of the room as of next lecture。 If you want to commit to being device free。

 please sit in this half of the room。 and I'll try and remember to remind everyone about it as we sit down。

You don't need to prepare for lectures， but I mentioned that I will try and make the slides available early。

 and you might find it useful to skim them if that helps you absorb the material in a lecture better by kind of having some idea about what's coming up。

There's also no preparation required for office hours。 Just show up。

 be it to my office hours or any of the course staff。 You can ask about any aspect of the course。

 It is a great time to work on your on the homeworks。 So that's absolutely fine to do。

 The course staff full of course， not be handing out answers。

 but leading you to figure it out for yourself。 that can be office hours can be a really great time for you to meet with your study group so that you can work together there and then reach out to interact with a course staff member if。

 if you all are stuck。😊，One thing I want to do is encourage you to talk with other students in office hours。

 This is， again， part of making sure that you're learning from your peers， learning from your peers。

 introduceuce yourself to people if you don't know them。And as I mentioned。

 if you want to make office hours， but can't， once we post the times。

 let us know and we'll do what we can。We've talked about course participation。

 significant chunk of the assessment is based on that。

 And there are many ways that you can engage in the material， definitely through the study groups。

 but also on a office hours， lecture。 There are some extra credit parts of the homework。

 So engaging that is a way to engage in the material， engage in the course beyond it。

I'd also very much like to have the chance to talk with everyone in the class。 have a。

 have some kind of conversation with each of you be that in my office hours。

 I'll also be trying later in the semester to start up something like coffee hour or something to meet with a small group and have a chat。

😊，嗯。呃right。I've already talked about managing your time for projects。 I expect you。

To take a conscious and active effort to manage your time。

 to start early and to get in touch with me if there are any extenuating circumstances。And of course。

 I expect you to be following the academic integrity guidelines that we've talked about collaborating appropriately。

It's on。Any questions about anything at all？So I know there's no required textbook was like recommended。

 will you like let us know what kind of like the corresponding chapters are with what？

That's great question。I think they might be posted on the website already。

 So if you look at the schedule page， it's laying out the lectures。

 And I believe it's referring to the appropriate chapter or section of of the textbook。Co。Thanks。

Any other questions。Okay， we're at the end of the time。

 I did not get a chance to talk with you about M L。

 but I do want to say one thing is that hello Camel has been released on the canvas website。

 There's a page called Homeworks where you can download it from。

 The instructions for the homework are actually in the homework in the doc subdirecty。

 So take a look for an HML file there。 And it' would also like everyone to sometime。

 let's say by the end of this week by the end of Friday， fill in just this survey form。

 Get a chance to know who exactly is in the class a bit about your background。

 that you have coming into the course。😊，If you are interested。

 you can look on the slides for a little bit of the history about M L。 And I'll also put a simple。

 simple dot M， A file that takes a simple language shows how we can represent it in nocal data structure。

 show how we can interpret those programs using an interpreter。

 So you're welcome to play around with that。😊，Thanks very much， everyone。

 I'll catch some subsetid of you on Monday。😊，The rest of the course。



![](img/bb5746d6ac0ae5f4bd7d7eb87fdb28e4_16.png)