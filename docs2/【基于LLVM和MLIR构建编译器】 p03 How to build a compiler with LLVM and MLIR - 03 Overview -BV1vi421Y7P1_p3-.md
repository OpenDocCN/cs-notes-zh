# 【基于LLVM和MLIR构建编译器】 p03 How to build a compiler with LLVM and MLIR - 03 Overview -BV1vi421Y7P1_p3-

Hello and welcome to another episode of how to build the compiler with LLBM and MLlIR。 This is Samir。

 and in this episode， we're going to talk about an overview。Of the entire。LLVM。

 MLR and serene is going to be like really high level。Just enough for us to get us started。

Let's jump to it， first of all， let's briefly talk about a generic compiler and some resources that might be useful here。



![](img/00ffc7f70dd86e82b55120050dbc44e0_1.png)

I listed two books， one is modern compiler implementation in ML。

 which I believe is available for free， but I posted a link。Hopefully， it would be free。

This one is like quite compact when it comes to compilers， it's like 500 pages。

 It has three different。Implementation， one in M L， which I already。

Posted here and two other one in C and another one in Java。To be honest， I started all of them。

 I read few chapters and the ML implementation is much， much nicer。

Just go with it if you don't know ML it's quite easy to learn ML to read the book the other two Java one and see you like you get into too many technicalities of the language like the host language itself so it's harder to cope you know so just read the ML1。

 it's a quite nice book and I highly recommend to read it。The second one。

 which known as the dragon book of compilers。I I love the name， by the way。

 is's kind of a Bible book， you know， a reference book for compilers。

's it's more than1 thousand pages and。It's well known。

 it's really good and highly recommend to read this one as well， but to begin with。

 I think like the first one is going to be much easier to read and it gives you enough to get us started。

One of my assumptions for the rest of these videos is that you know about compilers too。

Like a beginner， at least you have like a beginner knowledge of compilers。

So there's stuff that I'm going to talk about。 I'm pretty sure you already know， but just。

Let's go over them briefly because we're going to use use them for LLM and MLIR。Generally， speaking。

 most of the compilers out there have some steps， some phases to。Read the source。

 the source code of the language and generate the target code。

We like we split these steps into three categories。I most like most of the time。

 we split them in two categories， but like in some some books and some literatures。There's like。

 three。The first。The first。Category is front end of a compiler， which is。

A piece of software that reads the code and do someone does some analysis on the code and create a data structure。

Out of the source code。It has like three or more steps， like these three are the most common steps。

 but depends on the compiler and depends on the design it might be。More than three。

Or less than  three。The first step is lexical analyzer。Or like the。Pace of code that does this。

 we call it Lexer。 What it does to is to tokenize the source code into tokens and。

That's it so you give it a source code in form of a stream of characters。

 it creates a tokenized data structure for you， it's kind of like marking different pieces of source code as a well known semantic in your for your parure。

 for example it would like replace white space be the symbol white space or things like that right？

The syntax analyzer or parser is the piece of code which reads the result of that Leer provides to it。

Created abstract syntax3 or an ASD from it。What it does is basically to check the source code。

 the syntax of the source code and create an ASD from that source code easy， easy， right？And finally。

 there's another step called semantic analyzer， which tries like in this step。We get on ASD。

 The semantic analyze gets on ASD。And try to semantically analyze the ASD and reite it into another ASD。

 for example。嗯。In a language we might have function calls like let's talk about list in leastsp when we have a list by default。

 it's a function call， it tries to find the function name which is the first element and call it by pass it the rest of the elements of that list to it。

So from the syntax analyze standpoint， this is just a list right in the ASD in this abstracts。

In the S see， basically。That list is marked as a list with the。With the elements that we created。

while we were writing the code。But semantic analyze looked at it differently。

It looks at the semantic of the language and asks the question。

 is it a function call or is it just another list or like a data structure list list？嗯。

If it was a function call。It creates a new ASD， that replaces that list node with a function call node。

 and it does some magic to the ASD。Embbed some data in that node and some of the rest of that it's not it's out of a scope of this video right now。

 so basically we it tries to rewrite ASD into another ASD that has right semantics and。It。

It's ready to generate like an intermediate code from that ASD。That brings us to the second category。

 which is like middleland， oh， I have a typo here。Anyway， let me fix it actually。Indialand， yes so。

The middle end is like usually nobody talks about the middle end。

 There's no term like middle end in LM or others。 So at least I didn't came across it。

 I didn't come across it， but basically。What's what's happening in the middle end is we pass we have anD。

 which which we know is semantally correct。 and we're going to create some。

Intermediate language or intermediate code or intermediate data structure out of that ASD and then we do some kind of optimizer stuff on the intermediate code to。

Make it ready to pass it to the back end to generate the target code。

Different compilers have different intermediate medium code or data structure or whatever you want to call it。

 Later on， we'll see that in in the case of LLVM， it generates an IR intermediate representation as a。

Code， which is， in some sense。Similar to our assembly code。It has like two formats。

 like texture format and binary format。 And then it has the infrastructure for which like。

which you can write something like a pass， which is called a pass and you can have many passes。

 these passes are responsible for optimizing your IR in a certain way。

 I'm going to talk about them when we get to theium part but the important thing here is that when we create create this intermediate medium out of the ESD。

 then we have several service steps to optimize that intermediate medium even like more and more。

Remove some unnecessary code。 blah， blah， blah。 Finally pass it to the back end。

 which the job of the back end is to。Generate the target code。

 What is the target code depends on the compiler。Each compiler has like a target right it can be a machine code。

 it can be JavaScript like there's so many compilers for different languages to JavaScript right the target code for those compilers are JavaScript itself so if they have an intermediate representation the back end of that compiler would take that intermediate medium and。

Create Javascript out of it。 The target code is Javascript for different platform。

 different compiler， The target code might be different。 So， for example。

 Web assemblyly might be a target of a compiler。 So the end result would be Web assembly code。So。

 it was like。Super brief。And really， really short overview of a compiler。

I can't even say overview here， it was like， yeah， here's a compiler how it works in two minutes。

Make sure to read the first book at least to have some understanding of the compilers。

Somewhere around the chapter 12 of the first book might be good enough to get us started and to have like a good grasp of what compilries and how it works。

Because it's going to help you a lot with the LLVM stuff。Let's jump to the next thing， which is the。

E LM itself。LLVM obviously the website isVM。org I put a link to a video which is really good you can I highly recommend to watch this one as well。

 but I'm going to go briefly over what LLVM is and why we're going to use it。呃 but。Again。

 highly recommend you to watch this video。 It's amazing。

The stuff that I'm going to talk about is deducted from a really good chapter from open source architecture of open source software or something like this。

 which is like open source book， it has a chapter on LLVM who which is written by Chris Latner if I hope I didn't butcher the name。

 but he's the one of the main author of LLVM。You can't trust him。



![](img/00ffc7f70dd86e82b55120050dbc44e0_3.png)

Let's， let's talk about Lvium。By the way， the stuff that I'm going to tell you is only related to our project。

 It's related to serene and why I decided to use LVM。

There's so many other aspects of Lium that are really cool and like amazing。 but at this time。

 they're not kind of we don't gain any benefit。From them or talking about them。

 So I left them behind。As you can see in like this。Diagram。

LLVium is like a splits into three different pieces。 the front end， which we talked about before。

The optimizers， and the backend。Just like any other compiler at the front end is a piece of code that reads the code and creates an intermediate medium right in this case the intermediate medium is something called LLVMOR。

 which is LLVM intermediate representation。It's a language for it so like it's a language basically it's similar to kind of you can't think of it as an assembly code。

s it's really like it's totally different but you can think of it that way， you know。

The front end job is to read the source code， do whatever who do it wants to do and just emit that LLVM IR code。

嗯。That LLVMIR is kind like LLVMIR is kind of the international language of LLVM planet。Right。

So you cant pass it to any piece of any section in。LL VM unexpected to like。Show you some results。

For example， the optimizer or the press infrastructure gets an LLVM， it analyzes the LLVMIR。

 does some stuff to it， and emits a new LLVMIR。TLike basically， it gives you gives back an L VMR。

 right。So。The the optimizers are bunch of passes like the term pass like each pass is a piece of code that takes an LVMIR。

 try to optimize it in a certain way and return LVM IR again， you can think of optimizers。

 optimizers as a pipeline that the input is aLVMIR and in that pipeline。

 some stuff happens to that IR and the result is an optimize version of the input IR。嗯。

It's not only for actually optimization， you can do some others like semantic checks on and stuff like that。

 but we get to that later。And finally， in the back end。We have different pieces， different targets。

Targets depends on the project you can pass at VMOR to arm like to target arm platform， X 86。

 power PC or Web assemblymb or whatever and。When you pass the oil are to。Each of these backhands。

 they just generate the machine code or in case of Web assemblyly， the Web assemblyly code。

 or basically the target code for you。So。As you can see。It's cool， like LVM。

It's quite simple when you look at it， like。呃。From far away。But。The way like the design of L LVM。

 which is a set of libraries。To create a compiler helps us to basically take advantage of some different smaller pieces。

 smaller libraries that are well engineered and like they are battle test set So we can use them to create our compiler I don't have to be worry about like basically what we're going to do is to create a front end for LLVM like Kang compiler is a front end Rosl is a front end for LLVM has scale and Serene is going to be another frontend for LLVM。

 So what we're going to do is basically read the source code and create a LLVM or youre at the end。

And we can rely on the stuff that LLVM provides like the target cogen。

 like we're going to get so many platform supports。

 we're going to support so many platforms just because LLVM supports them The debugging functional is already there like I don't have to care about that I just have to instruct my LLVMR in a certain way to be able to let LLVM debug it basically and I'm going to get so many stuff out of right out out of the box with LLVM。

whichhich is a great applause for us。 Let's go to ride。 So yaang。嗯。Another。Good thing about LLVM。

 which is really amazing。 I the number of passes and optimizers that are already there。 So when I。

 like in case of certain， when we generate the LLVM Ir。

 the final piece of the string compiler would be the LLVM Ir。 When we generate that。

 we can use all of those optimizers on the LLVM on the。😊，Or your level。 and basically。It's amazing。

 I don't have to write。Tons of optimizers to optimize my code to be to run faster and more efficient because so many good engineers already wrote many。

 many optimizers and passes。 I can just use them and write only a few passes that might be specific to my language。

 right。So it's a huge plus。LLVium has like many， many， many cool features as well。

 I highly recommend you to take a look at the website and to learn more about LLVium and why it is such a cool tool but。

For now。These few bullet points are why we want to use LVM or why we use LVM。Now。

 let's get to the second piece species。

![](img/00ffc7f70dd86e82b55120050dbc44e0_5.png)

MLIR。

![](img/00ffc7f70dd86e82b55120050dbc44e0_7.png)

ML lawyer is a sub project of LLVM， obviously as you can see it from the website。呃。

It distributes with LVM itself。 So we talked about it earlier in episode one or two。

 can't remember really。We just have to be lit alongside equilibriumrium。 That's it。



![](img/00ffc7f70dd86e82b55120050dbc44e0_9.png)

Another simple diagram。ML IR is basically works at the optimizer level， or。

Whatever category we call it， like I call it optimizer。

 but it we can kind of think of it as the middle end kind of thing。We have the front end of stuff。

 which is going to be serene or clang or rust haskell， whatever， right。

They read the source code and emit some sort of IR， not L LVM IR St IR， I literally named it some IR。

 right。This sum IR might be way different than L L VM I。Here's the part that Emily enters in。

ML IR provides a different。Ways it provides a certain way to create。ORs， right。

 to create inter intermediate representations different than L mayR。So if you read the web page。

 read the homepage， you'll see that basically from the experience of other languages like Ross。

 Swift and Julia or other languages that works on LLVM。That uses use L LV I'm sorry。

 in almost all the cases， they had to create another representation。

 another intermediate representation layer on top of LLVM or or to be able to sit like。

ananalyze the language semantically or do to be able to make smarter decisions about how to optimize their code or how to do certain stuff。

On O level。So。With that in mind， the the Lviium community。Created a a lawyer， which exactly。

Has that goal to let the engineers who wants to create a compiler to create。

A your intermediate representation on top of L Vor。It has a concept of dialect。

 so you can create a new dialect， which is going to be a new inter present。

New intermediate representation。And each day， like can have can has its own types。

 its own operations。 and like everything can be。Tailorored for that I， specifically。And at the end。

 when you created your dialg， you have to create a layer to transform that IR into LLVMR。

And like M I or provides anything that you might need from from a framework to create transform jobs。

 transform manual analysis jobs to rewrite rules。 it's， it's really good。 And it has it。

I don't know the history here， but if you look at the web page and the documentation。

 there's a long list of dialects that are already available to us for different purposes from AsInc facilities to。

 I don't know like loop optimization and different stuff like GPU related sorry。

 dialects and so many other stuff。So we can actually use all of those dialects。

And mix them up with our own dial to create some I R。Be as smart about the semantic of oral language。

 do like， it's a higher level You can think of it as a higher level language in compared to a lower level language。

 like compare something like Python with C。Python would be the ML IR generated I and C would be LL VM IR。

 you know， so you you can be smarter in in a higher level IR， do some like directly map your AD to。

to the IR and then use the pass infrastructure to basically relote your IR to different IRs and so many like coolest stuff we can do one thing that I didn't note down here that works for LLVM and obviously for MLl IR as well。

1ivium has a cool tool called T ofgen。You can write backends for table like its a。Sorry。해별젠。

Itself ist like a language， you know。You write what you want。 it it a。The collaborative language。

 you say what you want and you pass it to a table gen backend it generates C plus plus code for you and you can obviously tune that code and'm like。

You still have to do some stuff like implement some of the functions。

 but basically the way it generates the code is amazing。

 it saves us a lot of time and MLIR has back and forth the table itself as well so when you want to create a new dialg you can just like use that declar language to describe what you expect from your IR and let MLIR generates the code for you。

 which is like really amazing and one of the reasons that I decided to move back to C++ as the host language because。

Just this feature。It generates everything。 it saves us a lot of time。 It's brilliant。



![](img/00ffc7f70dd86e82b55120050dbc44e0_11.png)

Now， let's move to the next section， which is setting itself。I'm not going to talk a lot about Sein。

 I'm just going to show you the flow of how Se compiler works at the moment。

We're going to pick like any of these steps。And have a I'm going to pick them up and have an episode on each of them or more than one episode and go in depth talking about the code and everything。

First of all， obviously， serene is a compiler from1 to LLVM and MLOR。

So what we do is actually like the main goal is to read the code。

 the read the serene code and generate。LLDMY are from it， but。That being said。

 like in the serene itself， we still generate the object files。

 we still use the C compiler to link them together and generate the machine actual machine code。

lot we're writing in a compiler and we， it should be able to do that。

 but we still use LLVM to do that。So here's a flow of what we do and how student actually compiles the code。

The main entry point is setting C or setting compiler， which is a binary。

 all it does is to parseel input argument， command line arguments and set up a reader context and stuff like that I'm going to talk about the details。

In future episodes。But for now， it creates a reader， reads the input file and the reader section。

 the reader part is going to generate an ASD。Then we use that ASD with another piece which is called semantic Anaer and that semantic Anaer works the ASD and node by node tries to rewrite the node。

According to semantics of our language， for example， the same thing that I mentioned earlier。

 it looks at a least and decides whether it should be a function call or it should be a least or。

Or even like is it a definition is the first element of that least a de if it is a de。

 let's rewrite it as a de note don't worry if you don' don't understand what I'm talking about at the moment I'm going to go in details about each of them in future videos it's just a high level dont don't worry about that just know that the semantic analyzer job is to get an ASD and generate another ASD which is semantically correct。

Then we create an intermediate representation from the ESD and we call it SLIR。

 Ser language intermediate representation SLIR itself is a dial act of MLIR。

Theres a table gen file somewhere I'm going to show it to you later with the description of how SLLR looks like。

 what operations it has and what types it has。I'm trying to map the ASD directly to SLIR。

 so each type of node in the ASSD has some sort of operation assigned to it。

 you know it's going to be more or less one on one to one mapping。

one too mini mapping I mean like the one note from the a s d too many operations from a seller ya。

Then MLR supports something called lowering。 So the lawyer。Where peer is a term in MLIR。

 It is a concept in MLIR。That is like。Changing a dialect to another dialect or changing a dialect to L L VMIR。

So we lowered the SL IR to。To some of the built dialects of MLI art。And。

I guess I could have chosen a better name。We call the resulted IR MLIR again。 I know it's funny。

 but its it's kind make sense， you know， SLIR is something external to MLIR。

 but when we lower it down to built in dialects of MLIR， I just call it MLIR right。And finally。

 we do some sort of like analysis analysis on the MLIR dialect and lower it down to the LLVM orR dialect。

 This one is like a built in dialect again， but this is the lowest dialect you can think of in MLL IR。

 Everything has to be converted to LLVM orR because the LLVM or or dialect knows how to be converted to LLVM orR itself。

 So I call this。IR LIR， like lowered IR it makes sense。

 and finally we lower the LIR to LLVM IR itself and generate the object file from it。

By generating the object files。The comp like we can stop here， right， The compiler is done。

 It generates some object files， and you need a link here to link those objects files to generate the the。

Machine code or the native binary or whatever。But unfortunately。

 using the linkers directly is really tricky。I had no idea about it while back。

 I thought like using the linkers because I always use Linux。It seems like it seemed obvious to me。

 but when I studied Lnker for a while， I was quite surprised。Like it's really， really complicated。

That's why everyone uses the C compiler to。basically link everything together as far as I know Ru is doing the same thing they call the C compiler to link the objects file but don't take my words for it I just read it somewhere。

So as the final step， we try to figure out the default compiler of the platform。

 which is in our case， Kang or GCC， and then we use that compiler to link all the resulted object files and create a machine code from it。

At the moment of recording this video， and if you take a look at the EP3 branch on the repository。



![](img/00ffc7f70dd86e82b55120050dbc44e0_13.png)

We have a pun here。So we have all the steps。 All of them works fine。

 We can generate the object files， but we don't have the final step。 The code is there。

 but I have a memory link there。 I have to debug it。 And like basically， it's a。



![](img/00ffc7f70dd86e82b55120050dbc44e0_15.png)

Just an attempt to。Do it。But don't worry about that。 we're going to get there eventually。

 also one more thing to。Do talk about right now。I didn't talk about the type system here at all。

I didn't talk about different aspect of。Programming language at all， because。

They're really important， but they're not important to the wiring of the compiler。

 We can leave them for later and implement them later on， but for now we want something that works。

With the most minimal set of features as possible。Sene at the moment。

 only understands integers and nothing more， so。We're going to implement everything little by little。

 but don't expect a full fledged language at this stage。I guess that's it for today。

But in the future episode in the next episode I'm going to talk about the reader itself。

 we're going to have a look at the entry point of the compiler which is3 C。

 we're going to go through the reader， show you the code。

 tell you how it works and basically re out the different pieces of reader to make it as clear as possible。

If you like what I'm doing， please subscribe to this channel。 Let me know what you think。

 or if you have any feedback， I， I would be happy。😊。

For you to share them with me and thank you for being with me today。

 I hope to see you on the next episode。

![](img/00ffc7f70dd86e82b55120050dbc44e0_17.png)