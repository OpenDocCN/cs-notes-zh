# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p03 1694441803-SEAS-SEC-SMP-2_LL_2_221_9_11_2023_2_16_PM.zh_en -BV14PAUejE98_p3-

remind you that Ed is also a really great platform， a way to get help。Homework 1 is out。

 I know that many of you have been working on it and submitting it to gradecope。

 It's due in two days on Wednesday。 A reminder that you can use up to three days worth of late minutes for any given assignment。

 and you have a total of 10 days worth of late minutes that you can use throughout the semester。啊。

Finally。For those who haven't filled in the student info form， please try and do that soon。

One of the reasons why I'd like you to do it sooner rather than later is we're going to be setting up study groups soon for homework 2 and beyond。

 homework 2 is going to come out on Wednesday in two days。

 there will be another survey I'll be sending out about for helping to set up study groups and I'm gonna be using the student infofo surveyve combined with the information in the study group survey to start setting up study groups。

 St groups will probably be set up by the end of the weeks or a little bit after homework 2 comes out。

But still with plenty of time for the study groups to work together on the homework。

Any questions about any of the administrative material。Okay。

So what we're going to be doing today is kind of starting to dig into content。

 Last lecture was a bit of an overview。 a whole lot of going over of policies。 today。

 we're going to just at the beginning， very briefly look at representing a simple language in Ocael。

But we're going to be spending the bulk of today's class and into Wednesday's class as well。

 looking at essentially assembly code。 we're going to be looking very briefly at how a C program gets converted into machine code and then start learning a bit more about the X86 machine model and then turning to X86 light。

 which was a simplified version of X 86 that we'll be implementing in homework2。😊，Okay。

 before we jump into assembly code， though。Let's think about。A really simple language。

 And think about representing this in many ways， the first step towards a compiler。

 So let's suppose that we had a simple language that had expressions and commands。

 So the idea of expressions is that they are arithmetic operations over， let's say。

 integers and program variables。 right， So we have some examples of expressions up here in the in the slide 6 as an expression  one。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_1.png)

IN S times x is multiplying two variables， X plus negative1 another expression。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_3.png)

So this is， that's kind of similar to what you will be， what you're working on in homework 1。

 a simple language。But here we also have commands。 Think about commands as actually doing things。

 And that those things might be modifying memory。 So here we have some statements that are assigning into memory locations。

 X equals 6 answer equals 1 or control flow statement。 So here's a loop。 A wh loop。 wh N Z is for wh。

 not 0。😊。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_5.png)

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_6.png)

Okay， so while that expression is not 0， it's going to execute the body of the loop。O。

So very hand wavy， but here is a simple language。In order to describe this language。

 let's go into more detail about。What this language is， what a valid program in this language is。

 We need to define two things。We need to define the syntax that is which sequence of characters are legal programs。

And we also need to define a semantics， a meaning for programs so that when you give me a legal program。

We can agree on what their program is meant to do。 What computation。It is meant to be doing。

So let's take a look at the syntax side of things。So here on this slide。I'm showing you。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_8.png)

Up here on the left。A description of the syntax。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_10.png)

Of this program。So this is really compact。But what this is doing is actually describing。

An infinite set。Of expressions。Okay， this is in a form called Bas Nower form for expressing syntax。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_12.png)

嗯。Here we've got E， X， P with angle brackets around it is what's called a non terminal that is it represents。

 if you will， a set of syntactic elements。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_14.png)

CMD over here on the right of the screen is also a non terminal。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_16.png)

And this。Double colon equals is saying， I'm gonna define the set of things。

 the set of expressions as。The following。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_18.png)

So on each of these lines here。嗯。We are describing one of the possible forms that an expression could take。

That's what the vertical bomb means。Different possible。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_20.png)

Different possible options。So here， for example， we are saying that an expression could be a program variable。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_22.png)

So we're using the capital X here to range over the names of program variables。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_24.png)

The second line here is saying， an expression could be。An expression followed by a plus symbol。

 followed by another expression。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_26.png)

So this definition of the set of expressions is recursive。系。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_28.png)

Over here on the right hand side， we're providing the syntax for commands in this language。

 So we have。Skip is a command。 We have assignment， a variable name X， followed by an equal zone。

 followed by an expression。We have an， if not0， command， if not 0。Followed by an expression。

 followed by a curly brace， a command， a closed curly brace， else， curly brace command。

 closed curly brace and so on with the other commands， Well not 0。 and then a sequence of commands。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_30.png)

So we're going to be digging a lot more into syntax later in the course when we talk about parsing。

But the thing that I want to emphasize here is。That we have a simple and compact way to describe the set of valid programs。

Using this backca now form。This is presented very compactly。 when we actually implement it。

 what we're going to be doing is having data structures。That pretty closely correspond to this。

 this description of the syntax。These abstract syntax trees。

Or essentially the way that within a compiler， we're going to be representing。A program。

It's useful for us to distinguish the abstract syntax。

 that is a data structure that represents a program for what's known as the concrete syntax。

The actual sequence of tokens that are used to describe a program versus the more structured tree like representation that shows how that program is structured。

 how there's， for example， a body of a whale loop， and if in an else clauses on a conditional and so on。

嗯。Once we have defined the abstract syn text trees。

 there is a representation in the program that describes the program that that represents the program。

We can think about how to implement the semantics。For that program。嗯。

One typical way of doing that is defining what's known as operational semantics。

 That is defining how， how a program executes。So， let me。Turn to look at some code。

 This code is on the canvasva website。 if you wan to take a look。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_32.png)

So here's a simple M。A simple language here。 I'm showing you the。

Backers now form grammar for the simple language， expressions and commands。

And let's take a look at how we're going to represent that an Ocal。So first of all。

 we define a type var equita string。 This is just the type of variable names。

 which we're gonna just use as an alias a synonym for the set of strings， for the type of strings。

And here， we're using an algebraic data type。For expressions。Similarly， for commands。

 So we have a different constructor for each possible form of expression， for each possible command。

And then we might have some essentially arguments to those constructors。 So， for example。

 for addition。There's the left opera hand and the right upper hand， both of which are expressions。

So addition takes as an argument， a pair of expressions。

So let's just go up and take a look at that backca now form again。And。The Ocal definition。

For the data types。So one thing I want to emphasize。

Is just how similar this Ocal data type definition is。

Compared to the Baus now form declarationation of the syntax。Right，They're both incredibly compact。

Very， very brief descriptions。Yet powerful。And we have kind of one constructor for each possible form of an expression。

 one construct for each possible form of a command。Right。

This is hinting at part of the reason why Ocael is such an amazing language for us to implement compileism。

😊，Right we have here a very succinct representation of programs in the simple language。

That we're going then be able to manipulate in a straightforward way， using pattern matching。嗯。

But this is essentially why we teach why I'm teaching this course on Ocal， because Ocal is a really。

 really nice language to write compileism。 This representation of abstracts and text trees as。

Is very。Very nice and elegant。Here's an example of an A T of a particular program。Right， so here's。

Here's the program that I showed you on a slide earlier。

It's computing the factorial of 6 by accumulating the answer in the variable A N S for answer。嗯。

And right here we have a representation of this program。That is at the top level。

 it's a sequence of instructions where the first。First command is an is an assignment of the literal。

Inter just 6， into the variable。呃。Vable X， right， that corresponds to this command right here。

The second part of the sequence is itself a sequence。

Of an assignment of the literal one into A And S。Its up here， followed by the wild loop。

The while loop contains， has two arguments to it。The expression， which is the test of the wh loop。

 in this case， the variable X， and then the body of the wh loop， a command。

 which is itself a sequence of two assignments。So this is an example of。

A data structure representing a particular program。

The process of going from this sequence of characters。Into this kind of representation。Is paing。

And we're going to be spending a lot of time on that later in the course。 For the moment， though。

 let's just assume we have some way of constructing these。Constructing these data structures。

 representing programs。What I have here in the rest of the file is a simple interpreter。

That is a way of taking a program。And interpreting it， figuring out what that program means。

It's in two main pieces。The first is。A function， which interprets an expression。Okay。

 it takes this argument。An expression E， which is going to interpret， as well as a state S。

 a state here is simply the current value of variables， right。

 So it's just a function a map from variables to integers。

And interprett expression is going to use that state to figure out what's the current value of a variable。

And that's exactly what happens here to interpret a variable X。

 We look in the state to get its current value。In the other cases。嗯嗯。Wed up to interpret E1 plus E2。

We， first of all， interpret E1， then we interpret E2。

That gives us an in an integer for each of those sub expressionions。

 And then we simply add them together using Ocal's edition。This plus operation here。

 similar for the other instructions。We have another function that gives us an interpretation for commands。

Now， the difference between commands and expressions in this language。

 when we interpret or evaluate an expression， it gives us back an integer。

WeWhen we interpret a command。That command might be modifying the store， the memory。

And so the result we get is actually。The memory， the store at the end of the command。 Okay。

 so we see that here in the function interpret command， It takes an state。

 the state before the command， a command to interpret。 and it returns the resulting state。So。

 for example， with an assignment。X equals E1。We， first of all， interpret E one to get an integer。

And then， we update the store。To say that the new value of x is the value of V that E1 evaluated to。

 Upd here is just a simple utility function to let us update the store， update the memory。

With a representation of the memory。嗯。So， we got time to。To run this。

So starting up U top here and essentially loading this file。

We can see here that we loaded it in the type definitions。

 We define that value factorial as the data structure。We。Can try interpreting。The command。

 we're going pass in an initial state。That we defined to simply map every single variable to the integer 0。

And the command we're going to pass in to interpret is that factorial。Program。

The result that we get back is a state。 The memory as at the end of the command。 So let me。

Assign that state to the variable S。 And let's see what S maps。嗯。The variable answer to。720 right。

 so the factorial of sex， fantastic。You can play around with this。 This is on the website。

 And this is very similar course to part of the exercise in homework 1。 Hello Caml。

 but with a slightly more interesting language with commands。Any questions at the moment about this。

yeah， 맞아， yeah。I California。One definition for expression， one definition for。

But they both refer to like bracketct X。 Is that ever defined somewhere？Or does they not need to。

Yeah， so X here is the name。Is is also representing a set of syntactic elements。 here。

 the names of variables。So when we're doing concrete passingsing， yeah。

 we need to be careful to make sure we actually define that in a meaningful way。

 Different languages define it differently。 But typically。

 it is one or alpha numeric characters where the first character is a letter。And， and so on。

We could define it here， but we'd probably define it as just set of strings， something like that。Co。

 thanks。Yeah。So last line in the first packet no form is parentheses and expression Oh yeah。

Be like an order of operations， and how would we do that in no account？Yeah， this is interesting。 I。

 I forgot to talk about this。 This line of the back of now forms is an expression。

 One of the ways you can have expression is open parenthesis。An expression， closed parenthesis。

And kind of we know intuitively from our study of mathematics。

 So what this is really doing is kind of telling you the order of evaluation， right。

 you're saying that， you know， if I had three times open parenthesis  two plus  one。

Closeed parentheesis。 I know that that's three times the result of two plus  one， not three times 2。

Plus one。So turns out that you need this for concrete syntax。

 You need this when you kind of have a sequence of characters that are describing what the program should be。

 what an expression should be。But by the time we put it into an abstract syntax tree。

 the structure of the tree is actually telling us。The structure of the expression。

 what a sub expressionion is。 So what that actually means is that in our abstract and text tree。

 we don't need to indicate these parentheses。 It's really the structure of the tree。

 What's the sub expression of what that is， that is sufficient。

So this is one of the differences between concrete syn text。

 It is the sequence of characters used to define。An expression of program versus the abstract syntax tree。

 which has a lot of structure in it。And again， when we get up to pasing， we'll。

 we'll dig more into it。 But， but thank you。 I did forget to mention that。That difference between。

The concrete syntax here。And the abstract and tax representation of it。就是。I about like。

 the abstract syntaxity tree provides the structure of the expression， Is that idea clear。错。

Any other questions before we move on。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_34.png)

O。Let's。Let's switch gears。Let's think about how we take a C program。And turn it into machine code。

So here's a simple see program's。A single function。 do sum takes two in arguments。

 I And J simply returns the sum， a plus J。This is essentially just text， right？

 You could have written this in a Microsoft Word and word processor。

Saveed it with the appropriate phone and A M almost。

The key idea is that this is not something the machine can execute directly。Of course。

 what we do is we use a compiler。Right， to convert this。Program into。A lower level representation。嗯。

GCC is a one own compiler。 the new C compiler is what GCC stands for。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_36.png)

The output of GCC。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_38.png)

In this case would be an assembly program。Assembly programs typically have the suffix dot S。嗯。

If we look at this assembly and we'll be looking at this in a lot more detail later。

 we'll see that there's this thing up here。 Do some， the name of the function。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_40.png)

Followed by a colon， followed by a whole lot of these assembly language expressions。

We'll be digging into a bit more about what this does。 But here you see there's an ad instruction。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_42.png)

There might be that turns out to correspond to that addition of the arguments， I N J。

This assembly program， though， is also not something that can actually be executed by the machine。

This is still actually just text。A textual representation of another program， an assembly program。

To get something that the machine can execute， we actually need to invoke what's known as an asemler within the Gu or the GCC tool chain。

 the asemler they use is called Ga G A S for Gnu asemler。

And what that does is it takes the assembly program and produces machine code。

That is sequence of bytes that can essentially be。Executed by the machine。嗯。

Machine code files often have the suffix dot O， standing for object file。Now。

 when you compile a program。You don't actually typically see the dot S file， the assembly file。

 What normally happens when you invoke an asmbler。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_44.png)

For example， GCC is that it goes directly from the。Dot C program。To dot o。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_46.png)

Okay， but if you wanted to， you could actually。诶。You could actually tell the。

Your compiler to produce the assembly code。 And that's something that's fun to do is you learn more about assembly and what's going on and see what's being produced。

Okay。That dot profile file。It's not quite something that can be executed。Okay。

 it contains this bitete level of information that tells the computer how to execute。

 But that dot o file。Might contain references to other entities。

 So to variables that are defined in other source programs， to functions that are defined elsewhere。

So， for example， if our code printed something using printf。RightIn myprogue dot C。

 it doesn't actually contain a definition of printf。Thatest defined in one of the standard libraries。

So what we actually need to do is take。A collection of these object files， these dot o files。

 and link them together。To form an executable。嗯。If we're writing a nice。

 simple program such as myprogue dot C， the files we're linking with might just be standard libraries。

 And all the standard libraries is a pre compileiled object file。Of source code。Alright。

So the linker takes these multiple dot files， these multiple object files。

Combins them together into an executable program。 And by combining them together。

 you can think of it at a high level as replacing references to variables and functions with concrete things。

With enough for them to， to actually execute。This is glossing over a lot of details。

 and linking turns out to be often quite subtle and challenging。

But the higher level idea of taking multiple object files。

 combining to an executable is a good mental model to have。Quick show of He， who's taken 61。

Almost everybody， great。Go through assembly probably a little quicker。

 but feel free to chime in with questions if anything comes up along the way。So as you know。

 assembly is very， very simple。 right， It's got minimal data types。 The interger data data it has is。

 you know，1，2，4 or 8 B， typically floating point data of various precision for 8 or 10 B。 But。

 of course， it doesn't have aggregate data structures。 There's no。Arays， there's no structures。

 These are kind of fictions， things that you would。

 if you will need to construct at the assembly level yourself。

Assembly only has very primitive operations， right， Arithmetic operations on registers or memory。

 reading data from memory into a register， storing data from a register into memory control flow。

 So jumping to a new address and executing the code there。😊，And related to that is conditional jumps。

Jumping to a new address。 if certain conditions are true。

 And so you've got some instructions that actually test those conditions。

 So you compare two numbers and setting things up so that you can jump some of the time。So。

 of course， at a high level language。We have some pretty complex operations， right。

 invoking functions。Doing manipulating data structures in simple ways。

 So these more complex operations， these more complex concepts have to be built up as a sequence of these low level instructions。

I mentioned the difference between assembly and machine code。 So assembly is text。

Assembly typically isn't intended for humans， but there are textual representations that we're able to read。

 So， for example， that sequence of characters， AD D， D，Q。

 space percent RB X comma percent R A X is an assembly level instruction。嗯。

The asmbler takes care of converting that this very simple assembly language into the ones and zeros into the bits that the machine can actually execute。

The asmbler also typically does a few things to make life a little more convenient。

 There might be what are called pseudo instructions at the asler level。

 instructions that are helpful order right at the assembly level that the asler actually converts into a short sequence of instructions at the machine level。

And then various other things that they can help us with。Intel。

 I mentioned that we're going to be working on the X 86 assembly language。

 This is developed by Intel， starting back in。The late 1970s。Right， so we're talking almost 50 years。

Yeah， this is a partial list of the Intel X 86 processes that have been developed over time。

A M D is another company， and they have a parallel line of processes。

 that is that were're accepting the same instruction sets， but had their own implementations。

 their own chips that interpreted it that that executed that instruction set。嗯。X 86。

 the assembly code is actually really， really complicated。呃。in part。

 because over the approximately 50 years， as these processes have changed。

The X 86 instruction set has only grown。 It's remained backward compatible。

 So code written to run on a processor from the early 80s will still be able to execute on a modern X 86 processor。

嗯。Approximately some caveats。 but definitely as Intel has developed the X 86 instruction set。

 it's made sure that it's backwards compatible。It's also had。

Takeaking a particular design approach to， to building this processor。

 to building this instruction set。 It's known as a。Complex instruction set。Or a cisk machine。

And what that means is。Even though assembly is kind of the idea is that there's， it's pretty simple。

 you do each instruction does a relatively small number of things。Within the Intel instruction set。

 Intel X 86 instruction set， there's a lot of different instructions。 theres like。Hundreds。

Is it hundreds。Yeah， there's definitely hundreds of different assembly instructions。嗯。And this。

 I'm sorry， I don't really like this clicker。 It's too easy to hit a button accidentally。嗯。呃。

Hundreds of different instructions in the X 86 As， X 86 instruction set。

And part of what that means is that to encode all these different kinds of instructions into ones and zeros。

 they actually use a variable length encod。So what that means is one instruction to the processor might take from 1 B to 17 B。

so this is how they are able to fit in all these different kinds of instructions。Into。呃。

Into a machine readable format。These cis machines are， by contrast with what's called risk machines。

 reduced instruction set architectures， R I， S， C。And those typically have a very small。

 unlimited number of instructions。The instruction encoding is typically a fixed number of bytes to encode each instruction。

And in many ways， the design of a processor to。Execute those instructions can be a lot simpler。呃。

Yeah， I I think that's all I wanna say about X 86， unless there's any questions。Yeah不认。Yeah。almost0。

Almost 1000 excellent。 So hundreds is correct。Thanks。Yeah， so a lot of instructions。

 some of them are hard to understand。 Documentation is notoriously difficult， challenging to read。

I mentioned that we'll be in homework 2。 and indeed， in the homework assignments in this course。

 we're going to be targeting a restricted subset of the X 86 instruction set。

 We call that X 86 light。 It's a very， very simple subset。 It's only using 64 B sign inages。

It's only gonna have about 20 instructions instead of almost 1000， but。

Just these2 instructions are going to be sufficient as for us to be able to compile some general purpose programming languages。

To this， to the subset。Okay， so when we think about the X 86 instruction set。

 it's useful for us to have in mind。At least a simple model of how an X 86 machine works。

So this schematic， this diagram that I'm showing you on the slides at the moment。

It's kind of at a very， very high level。Giveniving some of the key concepts。

So let's take a look at parts of this， parts of this diagram。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_48.png)

Over here， we have。Memory。ok， so呃。This memory is。Each location has an address。 We use。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_50.png)

Dropips says。Each address is specified by 64 B。A。8 Bs。

 There's a lot of possible memory addresses in a 64 B version of X 86。

 The way the memory is split up， is typically at。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_52.png)

The lower addresses。codeode and data。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_54.png)

Okay， so this is code that we're actually executing some fixed pieces of data that don't change。

At the other end of the， the memory， we have。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_56.png)

The stack。So as we'll be seeing， and as many of you know， this is how we manage function andvocation。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_58.png)

We have one stack frame， one section of the stack for each invocation of a function。

 and the stack grows downwards， if you will。 So from higher addresses to lower addresses。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_60.png)

And then we have the heap。Where we can allocate memory for general purpose computation。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_62.png)

For use by the program。 And that typically grows up so that programs can use the heap。

 Use the memory available for the heap or the stack as they need。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_64.png)

Over here on the left hand side of the diagram is the processor， representation of the processor。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_66.png)

嗯。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_68.png)

These areas in blue are registers。 You should think of those as being small pieces of memory that live on the chip。

 right， So they're going to be very， very fast to access the process that was able to take。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_70.png)

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_71.png)

Data from。Memory put it into these registers。We have the control part of the processor。

 which is going to be reading and writing values from those registers。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_73.png)

嗯。Connected to that is the A L U， the arithmetic logic unit。

 which is going to be taking those values， combining them various ways。 addition， multiplication。

 bid level operation such as and or X or and so on。The A L U might be in the control。 you know。

 might be putting those results。Into the registers。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_75.png)

The A L U， as it performs， the operations， might be modifying these condition flags。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_77.png)

Over here， S P。Sorry， O， F， S F， Z， F， these flags。

 which are going to be used by some of the instructions to figure out whether to do conditional jumps and so on。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_79.png)

Okay。How does the this part of the processor know what it should be doing with the registers？



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_81.png)

This is going depend on which instruction it's processing。

 So there's a special register on the chip known as R I P， the instruction pointer。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_83.png)

And that is essentially just an address into memory And to this code section telling it。

 what's the next address。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_85.png)

What's the address containing the next instruction to execute。So typically。

 the way the processor works is it's going to。Read the contents of memory pointed to by RIP。

Decode that。 That's the instruction decoder to figure out what instruction it should be performing。

And then the control unit and the A L U are going to essentially perform that operation。

By reading and writing registers and memory。Any questions about this high level of the view of the X 86 machine。

不要。co。Yeah。Essentially， the we talked about the idea that the instructions are represented just by ones and zeros。

 and in X 86， an instruction might be represented by one bit，1 by。 sorry， or up to 17 B。嗯。

And so part of what the instruction decoding is doing is it's going to start reading the bytes from the instruction pointer and figure out which instruction is it representing。

 Are we trying to add together R A X and R B X， Are we trying to compute a memory address in order to read from that location。

 Are we taking the contents of a register， R 10 and putting it into a memory address。

 So those are all the different kinds of instructions that's there and。

Essentially depending on which instruction we're doing。

It's going to be taking data to and from registers， putting it into various inputs in the ALU。

 performing instructions in the ALU and so on。It's actually interesting how they get is implemented。

 particularly in modern compilers， Where as I talked about， there's。Essentially， a， sorry。

 a modern processor is itself an incredibly sophisticated machine that's compiling and optimizing these machine code instructions。

 But I believe if you take like one of the architecture courses。

 you'll end up designing a simple processor that does this kind of stuff， reading an instruction。

 figure out from that how to manipulate values and so on。自 answer的 question。Thanks。

Any other questions。O。X 86 lights， I mentioned as using a subset of the 64 B version of X 86。

 So we have 16 different registers。The names of some of them R A X， R B X， R C。

 X and so on are kind of legacy。 They're kind of based on what the registers were originally intended to be used for in early versions of the architecture。

 These days， many of these registers are can be used。For general purpose。generaleneral purposes。

 although convention often means that certain register registers are used for certain purposes。 So。

 for example。R A X is typically used as the register to return a value from a function。

Other registers， their purposes baked into a lot of instructions。 So RP， the stack pointer。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_87.png)

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_88.png)

Is actually directly manipulated by a lot of the commands that are based on， say。

 pushing and popping values on and off the stack。嗯。The X 8 D 6。

64 instruction set added a whole bunch of general purpose registers0 weight to 15。Fortunately。

 not called with confusing combination of letters。The instruction pointer that I mentioned， R I P。

Is a different kind of register than the other registers on the slide。

 and R I P is manipulated only indirectly via control flow instructions。

 jumping to new addresses and executing the code there， returning from function calls and so on。

Let's take a look at。A。Particular instruction， the move instruction。M O V Q。Source test。 So here。

 source and destination operates to the instruction。 And intuitively， what this is doing is。

Copying a value from source to destination。Coup of interesting things to note here is that。

The destination opera end is treated as a location。Is telling us where to put the result。

And there can either be a register。Or a memory address。Source， however。Is treated as a value。

So if the source is， it can also be， the source can also be either a register or a memory address。

But interestingly， when a register is given as the source opera end。We mean。

 read the contents of that register。Same with the memory address。 If it's the source opera end。

 we mean let's take a look inside their memory address and the contents of it are the the things。

 the thing that we're gonna be moving or copying。In addition to。Being a register or a memory address。

 the source opera could also be an immediate value。 as a constant。Or a label。

Which you can think of as a memory address that hasn't yet quite been determined。

It's gonna be resolved by the linker。So a concrete example， M O V Q， Doloone 4 comma percent R A X。

 This is moving the immediate value for。Or rather， the 64 bit representation of the same inte of 4。

Into the register， R A X。Okay。嗯。In the notation we're using registers are indicated by the percent sign in front of it。

 immediatemedia values are indicated with the dollar sign in front of it。Another one。

 move Q percent R B X， percent R X is moving the contents of R B X into the location。

 R A X into the register R X。Just quickly about the syntax， there's actually two common。

Syntaxes for X 86 assembly code， the A T and T notation， the sources listed before the destination。

And as I mentioned， we're using A T and T notation。 and in this one。

 immediate values are prefix with doll sign registered prefix by a percent。

And the instructions actually have a mnemonic suffix to tell you which variant of it we're using。

 That is whether the instruction is operating on 1，2，4 or 8 B。Okay。

 so Q here stands for Quadword4 words， L for long two words， W for word， which is。

The two bites and beef a bite。By contrast， an Intel notation， the operas are in a different order。

 destination before source， and the variant of the instruction that you're using is actually determined by the register name。

 So whether the register is referring to a one by register， two by register。

 four by register and so on。Okay， so as I mentioned。

 we'll only be using the A T and T notation and only the 64 B version。

So we'll be seeing that Q suffix on， on our instructions。Any questions so far。All right。

Who's comfortable with twos complement notation。嗯。Who would like me to do a quick recap？

I will do an incredibly quick recap。Representing。Non negative numbers in bits is really easy。

Representing negative numbers， we have a few options。There's three common encodings， S of magnitude。

 ones complement and twos complement。 Two's complement is the most common and is the one that the X 86 architecture uses。

The basic idea is that。To represent。If the integrated K is represented in n bits。

 then we represent negative K。By。1， the number one followed by n zeros in binary。Minus。

The good representation of K。嗯。I'm going skip over the encoding。 if this isn't clear。

 you can look in more detail of the election notes with the C S 61 notes cover it in more detail。

I think one of the important things for our purposes， though。

 is just recalling the idea that if we're using inbits。We can represent two to the n possible values。

And what that means is that we kind of need to choose which values we're representing。

And in two's compliment。We can represent more negative numbers than we can represent positive numbers。

And this plays out in interesting ways when we think about performing operations on numbers。

Because the result of the operation may not be representable。In the encoding we're using。嗯。

There are some nice properties of twos complement。That。For example。

 addition in signed and unsigned representations is the same。 There's only one representation of 0。

Which isn't true for some things。 The downsiders， as I mentioned， it's notsymmetric around 0。

 We represent more negative numbers than positive numbers。嗯。

This idea that if we're doing an operation， we may not be able to represent the result。

 That's known as overflow。嗯。So。For example， if we think about adding together to unsigned。

Inteagegers。This graph， have you seen these graphs， these kinds of graphs before。No， okay。

 let me explain these。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_90.png)

This is a three dimensional graph on one axis here labeled to U。We have an opera end2 addition。

 This is an unsigned integer ranging from 0 up to 15。 right。

 So where this example is dealing with 4 bits where we can represent the unsigned numbers 0 through 15。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_92.png)

This' axis here V。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_94.png)

Is the other upper end to addition？Again，4 bits going from 0 to 15。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_96.png)

In the vertical dimension， we're showing the result of adding them together。Represented。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_98.png)

In four bits。So。If we look over here，0 plus 0 was 0。 fantastic。 If We look here along this axis。

 you know， 0 plus 2 is 2，0 plus 4 is 4，0 plus 6 or 6。 we see this really nice。

 straightforward representation of the result。😊。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_100.png)

What， of course， is interesting is if we have two large operas。

The result can't be represented in four bits。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_102.png)

We get overflow。 So， for example， if we had。15 plus 1。The result is going to be。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_104.png)

呃。Need 5 bits to be represented。 A one followed by four zeros。 Since we only have four bits。

We drop that leading one， and the result is 0，4 zeros。

 And so we see here that the result of 15 plus 1 is 0。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_106.png)

15 plus 2 is。嗯。1，15 plus 3 is 2 and so on。 So this whole region of the graph here。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_108.png)

Is overflow。It's where we did not have enough fits to correctly represent the result。

So for unsigned vintages， hopefully this idea is nice and straightforward， right。

 We can hold in our heads pretty easily， and we can look at this graph and interpret that that this region of the graph over here is where the result。

was too big to fit into the number of bits we had。Any questions about that。Great。

 so now we're gonna look at the same kind of graph。But now， on this U and the V axis。

We're going to be using sign inages。Okay。So here we have numbers going from negative 8。To positive 7。

So those are the numbers we can represent and two complement with four beds， Sam on the other axis。

 negative 8 to positive 7。And so， there's。For numbers that are， you know， near 0。嗯。Sorry。

 for numbers in the middle of the range here， we're actually doing pretty well。 right，0 plus 0 is 0。

0 plus 2 is 2。0 plus negative 8 is negative 8， right。Where does that work out。Yeah，0 plus。DYeah。

0 plus negative 8 is negative 8。It's way down there。 Tcked in the middle。7 plus negative 8 is。

Negative  one。So this region here is all correctly represented。Over here， we have overflow。

 In this case， positive overflow。Right， so we added。Let's say，1 and 7。And the result was。Should be 8。

 but we can't represent 8。 It turns out that we。got the value 0。 Okay， so positive overflow。

We also have this negative overflow。When we are adding together two negative numbers and can represent the result correctly。

嗯。This is probably the main thing we need to be reminded when you're thinking about toos complement over the next。

Coup of weeks in this course， right just the idea of overflow。

 the difference between signed overflow and unsigned overflow and realizing that whether we're interpreting a sequence of bits as a signed or an unsigned number。

Will differ on。Whether or not we regard that value as overflowing。看。And indeed。

 we'll see that we have different condition flags representing。 hey。

 if I think about this number as a unsigned number， did the result overflow。

 If I think about this number as a sine integer。Did the result overflow or not。Okay。

 within our X 86 instruction sets。We have a number of arithmetic operations。Okay， we have Neg Q。

Destination。And that's just taking the twos complement negation of a number。嗯。

We have operations to add， subtract and multiply numbers。嗯。

One of the interesting things about multiplication。Is that。呃。The destination has to be a register。嗯。

And multiplication typically over， you know， often overflows。

 There's a lot of values that will overflow for multiplication， I believe。

The implementation will actually do 128 B multiplication。

 So I have enough space to compute everything， but the result ends up being truncated。嗯。是。

Theres all I'll say about it at the moment。嗯。O。Four arithmetic instructions。

We also have a small number of logic and bit manipulation and operations。

So not Q of a destination takes the logical negation。

So how does this differ from toth complement negation。やこは。Take answer。Right， so in logical negation。

 all you're doing is flipping every single bit。Individually， with two complements。

 one way of thinking about it is you flip every single bit and then add one to the result。Ha。Right。

So not Q， logical negation。 We have conjunction and Q disjunction， or Q， exclusive or， X or Q。

And then we have shifting left and right， S， HQ。Is a bitway shift to the right。嗯。Sorry。

 let me rephrase this。SH LQ。Takes a destination。And a number of bits， the amount to shift it。

 and moves those bits to the left。Into the resulting gaps that you get， it puts a0。Right。

 so shifting the number one bit is kind of like multiplying it by two。

With appropriate overflow caveats and so on。Shifting to the right。Is interesting。

I shift a sequence of bits to the right。 I've got a question of what bit do I put in in the gap that was created on the left and the most significant bit。

And there are two options。This corresponds to the two different instructions we have here。

 bit waste shift right or arithmetic shift right。With bitwise shift， right。We always put in a zero。

Into the gap。With arithmetic shift， right。We're going to put。A copy of what used to be there。

So why is that？Why and for this arithmetic shift rate。

 do we kind of want to put a copy of what was there。하지。It preserves the sign， right。

 So it means that if we have a negative number， that is a number where the most significant bit is a one。

 we do an arithmetic shift straight， it'll continue to be  one。 It'll continue to be negative。

And what this means is that if you want to think about shifting。A number to the right， as being。

Dividing by 2。It's correct with respect to both signed and unsigned representations。sorryrry。

It's correct， with respect to signed representations。If you had an unsigned number。

 you'd want to use arithmetic。Sorry， you'd want to use bitway shift right to always put a 01。Okay。嗯。

So we've looked at some of the arithmetic instructions， some of the logic instructions。

Let's dig a little more into the upper ends that we have for these instructions。嗯。

I've already mentioned that we have immediate opera ends， registered opera ends。

 memory addresses and labels。We're going dig more into these。嗯。

Immediate operas 64 bit signed integers。A label。Is representing a machine address。

That we don't know yet。By the time the。A similar thing Lier and loader have finished。

Those labels will be resolved。Essentially， glossing over some details。

 they'll essentially be resolved to memory addresses。You can think about it， though。

 as a label as simply a memory address that we're not quite sure of yet。

 that we' are able to treat symbolically。A register opera end is simply one of the 16 registers。

That we have in X 86，64。Most interestingly， is a memory address。Offfer known as an indirect address。

呃。It's relatively complicated。Let's take a look in a bit more detail about how Wix 86 goes about doing memory addressing。

So， in general。When you're doing a memory address in X 86， there are three different components。

Of this， there is the base。So， that is。A machine address that's stored in one of the registers。

There's the index and scale。so诶。This is essentially an offset from the base。 So given the base。

 the index plus scale。Sorry， index time scale is added to it。 and then there's a displacement。

Which is a constant。Displaced from the base。So in particular。

 when we are given an indirect opera end。When we're thinking about what memory address it refers to。

 you can think about it as being computed as the base。Plus， index time scale， plus displacement。嗯。

We talked about the idea of an opera end being used in two different ways， right。

 as a source or a value。And as a destination， orre a location。

So when we have one of these indirect opera ends。When it's used as a location。

 it's talking about an address and memory。Soking about a place where you're going to be putting something。

When you use that as a value。You're talking about the contents of that address。

 and so this distinction。Treating an opera end as a。

 as a value or as a location is gonna be important。

 It's gonna be important when you start working on homework 2。

 and also important to keep in mind as you're thinking about these instructions。So why do you think。

Intel had this really complex form。For addressing memory。

 base plus index time scale plus displacement。Maybe its because you can't index into array。Right。

 it's exactly right。 It's to be able to access a raise easily。

 I saw some other hands that went up after a delay。 Does anyone want to expand。好了。不有。

Like on the arraying， if you're arrays， let's say。イ。What might take out home。我 bite。And then。Yeah。

 actually， the， the interesting way to think about this is the most useful is actually。

 when you think about a C structure。So let's suppose you had an array of seastrs。Right， so the base。

Upperand would point to the beginning of that array。对。

Let's suppose we wanted to access the third element。Well， the index there is going to be。The。

 let's say two， you know， the index into the third element。

And the scale is going to be the size of one struct。Right。

 so what that means is base plus index time scale。Is going be a pointer to the beginning of that。

 of the Istruct。Fantastic。The displacement is used to access a particular field within the struct。

 So if you remember from 61， your struct is laid out and memory and different fields within that struct are going to be at different displacements from the beginning of the struct。

So essentially， what's going on here in this instruction is that it's really nicely set up。

To be a target for C code。Right， or for this particular layout where you've got a rays ofstructs。

 And， you know which elements， which field of thestruct you're wanting to access。And moreover。

 it's gonna to be set up to be compiled nicely and efficiently。 So that is。

 you could have the base held in one register。And let's suppose you're looping through every single element of the array。

You might have an register that's holding the index that started at 0 goes up through 1，2。

3 for the length of the array。And then inside the body of your loop that's going over this thing。

 you might have varying displacements。You access the， you know。

 the X field and add it to the Y field and put the result into Z。

 So these are different displacements。But the computation of the address gets to use the same base register and index register for all of these different field accesses。

RightSo this is why there's the complexity of， of that way of addressing it is because it ends up being fitting in with a lot of the ways that we want to represent things in memory and access them with loops where one register holds the base another register holds the index。

嗯。Okay。In terms of notation。It's typically written as。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_110.png)

An optional。Constant value at the front。 That's the displacement。

Prenheses in which there's one or more additional opera。 If there's one operaan。

 that's just the base。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_112.png)

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_113.png)

If there's two opera ends， the first one is the base。 The second is the， sorry。呃。

Itll be one or three。Opers inside the parentheesis。The first one is the base。If there's three。

 the next one is the index。

![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_115.png)

And the third one is the scale。Right you so you can see that here in the computation。

 this index percent R E X percent R C X 4。Is the base R A X plus index time scale， R C X times 4。

And so here's an example of the full。Using the full flexibility of memory addressing， right。

R E X is the based。 R C X is the index，4 is the scale，12 is the displacement。In X 86 late。

 we won't be using index and scale。 You can still do everything you need to do。

 but maybe it just won't be as efficient。 say as you're looping over every element in an array。

Yeah for the。あそ？I realized that for the cs before we had to use dollar site。Sure。

 the the do sign was used to indicate an immediate opera end。This number is。I'm sorry。 I。

 I misuseed the word opera end。 This number here is part of an indirect。嗯。Of an indirect opera brand。

 of a memory。A memory opera， if you will。 So it doesn't need the dullll sign in front of it。O。

I'm actually gonna wrap things up there。 The next thing I want to talk about is the stack。

 and I will not be able to fit that into four minutes。 So what I'm gonna do is pause here。

 And on Wednesday， we're going keep looking at our understanding of the X 86 machine model。

 thinking about how。How we end up thinking about memory and the stack。

Any questions before we wrap things up。Yeah哦系做系销。This mess。ち。I wanted to generate this exit。so诶。

What we'll be doing in。Great， that's a great question。

The way the homeworks will be working is each homework is kind of standalone。 for the most part。

 That is we're gonna give you scaffolding。For things。 And you're gonna be implementing parts of。

A compiler。嗯。In some of the later projects， you would be able to use some of the things you wrote earlier。

As a component。Or you'll be able to end up using something else so that you're able to work on that homework regardless of how you did in the previous homework。

 And you know， so a bug in the previous homework isn't going to mess you up as you work on the next one。

For homework， too， what we'll be doing。Is implementing an X X 86 litte simulator。

So that is what you're going to be doing is essentially implementing an Ocal。An interpreter。

For an X86 light program。Okay， and this is a really great way to make sure that we actually understand。

Those aspects of the， of the X 86 assembly。 And then in later assignments。

 we're gonna be targeting X 86， X 86 light。 And then， yeah。

 you'll be able to take the output of your compiler， X 86 light。

 pass that on to an assemblyr and get something that can actually execute。2。Qu here。

 And then who do I。他觉什么。Yes， X 86 is byte addressable and。I'm trying to remember， yes。

 in the homework， you will be implementing by addressable things。

 even though you'll be reading 4 bytes at a time。You can address every。

4 Bs starting at any particular bite。Yeah， on the process。Ls。这什么。Yes， you will be implementing。

Those condition flags and learning more about what they are。 O F。

 S F and Z F overflow flag for unsigned overflow S F is the signed overflow flag and Z F is the zero flag。

 And essentially， what happens is this will all be detailed on homework 2 for some of the instructions that you'll be doing。

Based on the result， youll need to set。O， F， Z， F and S F to  one or 0 as appropriate。

 Other instructions are very specifically not meant to modify those flags。 and then。

The control instructions that we'll get to end up。Essentially looking at those flags and and doing conditional jumps。

So you， you'll be digging more into that。 and I'll be talking a little bit more about it in the next lecture。

Any other questions at the moment。Yeah， that' one of the Beck。Are there registers？

Oh that's a good question。 So are the registers physically the same。 And， and by that， do you mean。

先輩。Physically， like。Oh。That's a really good question。 Like how is。

 how is the sex86 machine model actually implemented at a lower level and are all the registers treated exactly the same。

 So the short answer is no， they're not， they're not all treated exactly the same。

 And we'd be seeing that some of these registers are， in fact， special。

The stack pointer and the base pointer， for example。

 indicating the stack frame are special and I would expect that some the and so some of the operations are treating those specially。

There。Also， a lot of convention that's used。 So things that are not actually baked into the architect。

 into the specification of the instruction set， but the way that these registers tend to be used。And。

Because a lot of the process designers are trying to eke out as much performance as possible。

 particularly on certain benchmarks that are used to compare the performance of one processor to another。

 being able to take account some of these idioms， some of these conventions that are used can end up being useful for performance。

 And so， for example， some of the idioms are about。

 you know which registers are used to pass arguments in So if there are things that you can do at the lower level。

To。To help optimize that。You might eke out a bit more performance and do a little better on these performance things。

 So to be honest with you， a lot of the time， the implementation of these chips is a black box。

 It's proprietary information that companies are very protective of。And in some ways。

 what we're talking about now is the interface to that。 right。

 So you can build up a mental model of how X 86 assembly is meant to work。

And use that appropriately and correctlyly。And to be honest with you， implementation ways。

 they might be doing something completely different。

But that's okay as long as they're kind of meeting the abstraction。同。Great， thanks everyone。

 I'll catch you on Wednesday。 Please remember to fill in the info form and keep it eye out for an email from me for filling in a study group survey to help me match people up。

😊，こ。Therere fact。ILooking into。い対語がってます。まずる。Wait， we arrange。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_117.png)

然后就是。そ likeてす。こいくらた。嗯。I think the main thing to think about is we're targeting X。嗯。わは。When。

a lot of this material。Intel。エサセますか。Apple user an our based chair。And so。没个あか。Yeah。

 Apple search is based on。他那个事。mall portion。Yeah。Yeah， in some ways。This complex instruction scale。

Means that there's actually a whole range of instructions and some very specific points。

And the idea that if you can。If your compiler can take advantage of this wide range of instructions。

You might actually be more efficient right so in risk what you might need to accomplish in two。

 three， five instructor。Maybe there's a single instruction in the F86 architecture that does so for example。

 making this up off the top。Okay thing。There are like instructions and the Intel instructions to do a thing like。

Take this value dectriment by one and put the result over there。啊。And so in rescue。

 that might require civil。read it。Drementing store back then。Okay so because it。

do this there's the possibility of the process of being able to implement that。

Single instruction in one， essentially in one cycle， I right。

 meaning that instead of in the risk construction stage' need to。Three cycles。W it in， modify it。

 write it back， made it as possible for you to do it in one issue。

And so in some ways you can think about it as。In the cis construction seat， you've got this wider in。

You've got these ways of telling the process so what it is you want to do。AndAs a result。

 there's the potential for the process of it to be。Do those things more efficient。嗯。

Pside is you could say， like if you've got risk a simplified instructions set。

 you can work on that stuff real efficiently， or maybe you could actually take that sequence instructions。

And do more stuff on it。那个。Take the simple instructions in and then do much more sophisticated stuff to try and optimize it improvement So' they kind of like different approaches。

嗯。I don't have enough of an architect person to tell you which is winning are。

 but risk is definitely。嗯。B thing。Increasingly， increasingly used。

Does the interpretation of ci play take longer？じゃ終い。Iums more energy。

I don't actually know if the consumes more energy。呃。Maybe什么。な not nothingな。

And this is kind of the instruction on other day。10 years。I don't know a huge amount of this。

Common details。New， common implementation。I think that bit他。

Probably implementations of risk that could be quite low energy。You你 have a simple活。

く I had a more household。Paient risk is doing a lot more stuff。Secres one instruction。パス。

But maybe one way to think about it is with risk。With a simpleant interface。

 you've got maybe that gives you a wide range of them。

It's opportunitiesport and so you can get away with a very low time。Some implementation whereas。

There would be harder to do with ci where， for example。

 even just the variable in construction means that you need more sophisticated logic even。

Update to the instruction point for the next。anything。The next instruction is going to hand on。

What's the current instruction and how many items？W is in riskfully you have that fixed。



![](img/811d7af71fa49e3aa4eb2c8e7e92f74b_119.png)