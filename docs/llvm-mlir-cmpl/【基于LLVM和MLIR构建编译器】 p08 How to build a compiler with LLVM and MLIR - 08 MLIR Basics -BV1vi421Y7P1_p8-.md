# 【基于LLVM和MLIR构建编译器】 p08 How to build a compiler with LLVM and MLIR - 08 MLIR Basics -BV1vi421Y7P1_p8-

Hello and welcome to another episode of How to build a compiler with LLBM and MLLIR。

Today's episode is a bit different than previous episodes because in today's episode I'm not going to show you any code。

 we're going to talk about J an overview of MLR and the basics that we need to continue working on the serene compiler。

Before we start on the topic， I need to mention few changes that I made to the compiler。

 actually I'm still working on them。嗯。In the previous episode。

 I mentioned that I'm working on the Justin time compiler and that work kind of pushed me。

Toward adding a source manager to to the compiler source manager is a concept that we're going to talk about in future episodes。

 but。Basically adding a source manager for us kind of forced us to make changes to the reader process as well。

 so the reader is now different， the logic is the same but it has to be able to work with the source manager。

And。With these new changes， I had to make a change to the serring Sea itself and the CLA interface of serringency is now completely different。

Whatever we talked about in the previous episode and especially like I'm going to talk about the old interface today as well。

 so all of them are going to change in the near future。

 but I'm going to have another episode describing the changes and everything so。This is just for you。

 if you look at the master branch today， you see different code than other branches like other episode branches。

And that's totally okay， I'm going to have another episode about these new changes。And a disclaimer。

 today obviously we're going to talk about MLIR， but I'm not an expert in MLIR， I'm just a user。嗯。

I'm trying to keep today's episodes like a high level overview as a high level of overview。

 but I already included some of some talks and some resources about MLIR by MLIR developers。

 so I highly recommend to watch them and read them to have better understanding of MLIR。

Moving forward， first of all， let's talk about why。We want to use M L IR。

I already talked about this in the first or second episode I can't remember。

 but a brief history of what happened and why I chose to use MLIR。So。Long ago， I， I had to。

Find the right platform for the。For my new language。呃。

I did some experiments on like different platforms like the JVM。

 looked at different house languages like wow。Rt， go Lang and some other their stuff like Java。

And finally， I came to the conclusion that LLVmeE is the best platform that。

Like the best choice I have。So I read a lot about LLVM， I kind of talked to many people。

 I ask for different opinions in different communities and overall。

My overall my understanding was LLVM is the best thing that I can use。

 it's just a set of libraries to create a compiler to create a language and that's really what I'm looking for。

So。I try to use allerium with different languages because to be honest I'm not comfortable with C++。

 I don't like the language that much， it's an awkward language， but whatever that's my。

Onwn opinion and skill set。 So I use other languages like Ro and Golan， as I mentioned。

 but I didn't have。A good experience with the C API of the LLVM。

Somebody already mentioned to me that there's something called MLI R is's really cool。

 you have to have。Take a look at it。And use it so some people already suggested MLIR to me。

 but when I looked at MLIR initially and I read on the website that it's part of the LLVM。

 I thought okay I have to learn LLVM fairs to be able to use MLIR sorry。

 but that wasn't the case and。So if you don't know LLVM that much， it's okay。

 you can start by using MLIR， it's not necessary to know about LLVM， especially LLVM IR。

 if you knew already。Perfect， you're an advantage。 But if you don't， that's totally okay。

 And obviously， when we move forward， we're going to learn the whole。

MLO you on LLVM library together。If you don't know LLVM， no big deal。

 we can start by MLIR and when I look at MLIR and like try to understand it and like work around it。

 work around with it a little bit。It was clear to me that， okay， MLR is。

Really good and it's that good that I can abandon any effort I had on like with other languages and just stick to C++ and ML lawyer。

And that's where we are today。But why MLIR is actually beneficial for us， why it's that like so good。

 so if we put MLIR aside for a moment and just focus on LLVM in order to use LLVM as I mentioned in earlier episodes。

We need to create we need to create a front end that reads the source code of whatever language we're working on create and translate that source code into LLVMIR。

And then feed that LLVMO to the compiler backend， and then the backend will take care of code generation and stuff like that for us。

But here like this design is actually really good in compared to other libraries that might be out there。

 but there's like a big issue here LLVMIR is too low level so you can think of LLVMIR as it might not be a right it might not be like a correct example。

 but you can think of LLVMIR as assembly instructions so LLVMIR on its own has a set of instructions that you can compare them to assembly instructions so if if we don't want to use LLVMIR we had to come up with some form of IR for our own and then translate that IR to assembly actually to assembly instructions。

And that's what the backend of LLVM does for us。So and it's kind of limited like LLVMIR is to some sense really similar to assembly so it's kind of it's really limited。

 so when when I wanted to like do some experiment on LLVMIR and write some basic some basic animal languages with LLVMIR。

I had a tough time because it's really hard to。kindind of model a high level concept into LLVMIR which is like really low level and really soon I was like okay I need to break down the problem like this is like a really hard problem I have to break it down into a smaller problems and like easier problems to solve like create abstractions basically on top of LLVMIR。

And I was trying to cut like I already。Recommended two books in this series one is like the Dragon Book of compiler。

 the other one is the Tiger books， they're kind of well known so in those books if you read them already you'll know that。

All the steps that I'm talking about are kind of common in all the compilers。I wanted to create a。

 like， a high level。Abstractions abstraction layer on top of the LL VM IR to。Kind of solve a problem。

That is really hard， like basically mapping a really high level concept to a low level concept is。

Really tough， so。When I tried to come up with the abstraction。

 that was around the time that I learned about MLIR and basically。

To put it like this as simple as possible， ML IR is actually a framework to build a compiler with our own IR。

 So basically。It helps me to create the abstraction that I need on top of LVMIR so I can break down the problem into smaller problems and like well design abstractions。

The name of Emmet， like to be honest， I still。don't know exactly what ML L stands for in M A or MLLR like there。

 I saw a talk from。And L VM developers， they made a joke around it as well。

The best definition like I heard is multi layer or multilel IR。That is really like nice。

When we create abstract。Mathematically speaking。Abstractions。

in different layers so we create an abstraction on top of like a problem we have to make it simple like to be able to understand the problem at hand like better and then we create another layer of abstraction on top of the previous one to help us see the bigger picture and like we create these layers of abstraction on top of each other to get to a point that the problem is simple enough that we can reason about it and break it down into。

Smaller pieces and shuffle things around and come up with a solution， right？

And that's what exactly MLIR is doing for us， so many other people that uses MLIR in different companies or individuals or whatever。

 they came up with their own layers，In MLIR I'm I keep saying layers or levels because there's a term for layers or levels in MLIR we call it like MLIR called them dialect。

 so from now on whenever I say dialect， it means those layers on top of each other。

So people actually came up with different dialects。

 they created their own dialect to do some specific things or general things。

They came up with those abstractions。 So and some of them are open source。 and as as far as I know。

 like I watched a talk about Meti I by Me Amini， he was saying that。At that time。

 Google has like 60 different dialects and。Most of them are not open source。诶。

When people create these dialects。Some and open source them as a。Compil their programmer。

 I can actually。Use those dialects in my advantage。

 I can leverage other peoples work and create my own dialect。My dialect would be kind of a model of。

Concepts around my own language and use other people's dialect to kind of fill the gaps and create the entire。

Compilr， we're going to have a look at it like。a few minutes。

ButM sorry MLIR itself works around a language， so it it kind of have a language on its own that describes the different dialects。

 let's have a quick look at what that language is and how it works so first of all that language is SSA based。

What is an SSA， I included a link to a Wikipedia article describing what SSA is， but for short。

 SSA or aesthetic singular assignments。Is a concept in intermediate languages that based on like whenever an intermediate representation or whenever an IR is based on SSA it means that variables in that IR has to be defined before initialization and we can assign one variable only once and it doesn't change ever again we cant reassign it right so in terms of LLVMIR and assembly。

 we can think of SSA values as kind of registers but。In MLIR， since it's really high level。

 we can think of SSA values as variables， I don't like the name variables here because basically they don't change。

 they're not variables。But think of them as bindings， we have a name for a value that's it。

 and it never changes， we can't reassign it。The MLIR language itself is typed。

 but the good thing and the thing that I really liked about MLIR is that the types of MLIR are not hard coded。

So unlike LL VMIR， which you have a set of types to use and you have to。

Kind of modeling your own types around them。Sorry。😔，In ML L， our types are kind of。A basic block。

In the entire system， we can create our own types and。

Come up with different types like a different type systems based on the API that MLIR provides for us and we can use them to create our own types。

And finally the language itself is context free， it's a weird term context free for lack of better words。

 I chose to call it context free， but what it means is the ML your language itself is just bunch of text。

If you。There's a tool called the。I now just I remembered about it， so there's a tool called MLIR OPT。

That you can use it to kind of interact with MLIR， I wish I could actually include this one in the talk。

 but hopefully for the next episode I prepared some stuff to talk about MLIR up。

So you can actually pass some start like start a file， sorry， create a file。Right bunch of。

MLOR in it and pass it to MLO or OPT and interact with it。As far as the Miller you concerned， that's。

As long as the syntax is valid， it's okay。 MLR doesn't know what that。

What what that code that you wrote。Does， but。It can verify the syntax and if there's like a dialect that ML already knows about it。

 it can do some stuff for you， but when you create your own dialect。

MLIR doesn't know about what it does necessarily， right， that's what I meant by context free。嗯。

As I already mentioned， the layers of abstraction in MLOR are called dialects。

Each dialect is a collection of operations， I'm going to talk about operations next。

 a bunch of custom types， some metadata， and we can use different dialects together to like solve a problem or something to that sort。

One thing that I have to mention here is that。If we take a look at the other programming languages that uses LLVM already。

All of them actually had the same problem。 They tried to come like。诶。

Translate their source code into LLVMIR and pass it to the back end， but they they needed to do some。

They need to process the input like the source code and analyze it and make some changes and be smart about the different type of optimization they want to do on their source code。

You can't do that on LLVMR that much because it's really low level。

 so they had to come up with their own abstraction layers and。Basically。

 all of them had to create their own IR， as I mentioned earlier。

But MLIR is kind of like is an effort to actually unify all of them under the same umbrella and like with the same API and set of rules。

So for example， I'm not sure about this， I don't know how Ro， for example。

 implements their other layer of IR。But if someday they move to MLIR。

 I can use their dialects in Serena as well and do some stuff with their dialects， or for example。

Excuse me。呃。I might butcher the name， but there's like a for time compiler in LLVM called F。

 I guess I don't know how it pronouncedno flying maybe。Flanang itself uses LLVMIR sorry MLIR。

 so right now I can actually use Fs dialact in my own compiler。

Use the things that flying people already implemented in their dialects in my own compiler。

 and that and that's totally okay。 I can mix and match all the。Whoops， what happened。

I can't mix that much all the。Dialects together to get what I want from a a different layer of abstractions。

Some of the basic。Dialects that ML IR already provides are likeD， dialect， LLVM， dialg， math。

 dialects， A dialects， actually。

![](img/64f1576f0836b4af49b069f14dabfccf_1.png)

U。Let's。Have a look at the different dialects there， okay。Oh， I actually let me 10 of my dark mode。

 okay。

![](img/64f1576f0836b4af49b069f14dabfccf_3.png)

So。All of these dialects are there for us to use。I don't know like the built dialect is like what you get out of the box and it's quite limited。

 It doesn't have much to offer。 actually， that's a wrong statement。 It doesn't provide。

Anything more than it should， so it's quite it has quite reasonable amount of functionality and that's totally fine。

Besidesside that built in dialect， the SDD one is kind of important。

 it provides like different operations to do like to call a function。

 I don't know to compare some of stuff to create conditionals。Or。S Cf is kind of interesting。

 we can create parallel execution， reduce E for yield while， you know。

When we want to use the if I use the SCF dialect today， I don't have to make any of these anymore。

Like to create like a conditional， I have like a CF if I can use it。

 actually I don't know how it works at the moment， I have to read the docs obviously， but I mean。

It's really nice to use other dials like it solve many problems。 And as a programmer。

 I don't have to do much， you know， my problems， like I can focus on what matters to me and to my language to my compiler。

 or for example， the async dialg like。It is actually really amazing。

 we can take like we can leverage these operations to create our own AsInc infrastructure for our compiler and don't do like don't be like we can escape all this there's nothing to be worry about like I'm as a programmer who works on this compiler alone most of the time。

This makes me really happy， like。This is actually one of the best things I like about MLIR。

It's just amazing so。Let's escape all that and stay on track。



![](img/64f1576f0836b4af49b069f14dabfccf_5.png)

A very。Okay， so。Now operations， what are operations。

The name might be a little a little bit confusing， but operation is a concept is like a unit of abstraction in MLR。

 so dialects is a collection of dialect is a collection of operations。

 each operation is an abstract like abstract concept。It's not an instruction。

 It's not an instruction。Unlike LLVMIR， that has its own set of instructions。It uses SSA form。

 so operations usually return something in type of like as an SSA。

We can write our operations fully in C++ or we can use table ja。

There's a backend for it to define our operations and table will generate everything for us。

 including the C++ implementation and most of the things that we need。

 we might need to add few things to like to make it work but it's a huge advantage to do it I'm going to show you how it works in a bit。

And finally， since， as I mentioned。The dial is just a bunch of text so。Just it takes format， right？

Kind of。啊。I don't know what to call it， but。Kin of an example that MLIR engineers。诶。

Used in their talks is that they don't want the they didn't want the ML IR to be the Json of compilers。

 As you know， Json is just a。Like you。Format that there's no constraint there no there's no types and things like that。

 So everything is in a string format。 you can pretty much do whatever you want。 It might sound cool。

 but actually it's not because then you have to deal with the verification validation of the data and things like that on your own instead of the format like the format doesn't provide anything for you。

 if you're a closure fan， you know that there's like a alternative format like EDN that。

Sove these problems or port above or A or stuff like that。

 They try to fix like formatting issue that Jason have with like different types to be more strict。

 things like that。 And ML IR engineers didn't want ML IR dialects to be like J as well。

 So operations have different。Kind of， I don't know。 let's call them behavior。

Operations might have their own verifiers and printers by default they don't。

 there's like a P team one that MLIR will use， but we can provide a custom verifier or printer that actually works as a serializer and decent serialreizer for our operation。

Basically， whenever we want to read the operation from an MLIR file or some other sources。

 we can verify the structure of that operation and make sure that that operation is in a form that we want and semantically is correct and the printer obviously serializes that operation into like a text format that I'm going to show you。

There's another concept called attributes in MLR that kind of confused me to begin with。

I'm going to show you how what it is and how it looks like in a bit。

 but this is new to MLLIR I couldn't find anything like that in LLVMIR if you know about attributes and if attributes exist in LLVMIR I don't know。

 please let me know。I'm going to show it to you it's better to talk about it on an example also blocks and regions。

 so blocks are everywhere LVMR has blocks as well even like if we don't talk about LLVM at all blocks are kind of basic。

I want to say blogs， but basic concepts in。Compilrs。A block of code。Actually。Excuse me。You know。

 you might hear the word block and think， okay， it's like a block of code in Java or C++ or stuff like that。

Whenever we talk about blockss in compiler wordss， block is actually a straight line of instructions。

That there's no branch in them， So there is no branching in a block。When you enter a block。

 there's like a list of instructions you have to execute and till the end of the block when you want to exit the block。

 right？In terms of compilers。Whenever we want to like translate the IR code and generate the machine code from it or target code from it。

We try to create blocks of code and kind of link them together it would be like jump from this block to that block if you already know about assembly you'll get it like in no time。

 but blockss are think of it as like a straight line of instructions with no interruptions in between by interruption I mean like no branch in between so when you enter you start executing the instructions till you exceed the block。

But region is something， actually。Only MLO your has and LLVMO your doesn't have regions。

Regions are a list of or an ordered list of blocks， so each region might have one or more blocks。

Ordered in a certain way。We can both nest blockss and regions inside each other。

 so regions it like a。What I'm going to say is not 100% accurate。

 but you can think of regions as blocks in different programming languages like Java and C++。

I'm going to show you examples and that would makes it easier to understand and finally types I mentioned it already LVM types are we can create our own custom types on MLIR dialect and that's a huge advantage。

Another concept that we need to know to continue working on the serene compiler is the passing for structure。

Pa infrastructure is something that LLVM has actually not MLR， it's not new to MLLR。呃 so。In the LLVM。

 by the way， we're going to have another episode about LLVM。

 another episode like this about LLVM as well， when we get to the point that we need to talk about LLVM and specifically。

 we're going to have another episode about it， but for now I decided to exclude LLVM talks for now。

But LLVM itself and MLIR both provides something called pass infrastructure Basically what it does is we come up with an IR either LLLVMIR or MLIR or whatever and then we create some stuff called passes so each pass basically we run different path on our IR and each pass does something as for example we might fold constant values in a path we might have a pass which actually I don't know analyze the code and decide to remove some of the IR based on some。

Conditions and things like that and。The infrastructure part of it are the API and things around the past management。

It's pretty neat and in MLIR the Pass manager is multi threaded， I don't know about LLVM。

 but I guess it's not multi threaded in LLVN since the engineers kind of try to make a big deal out of it and actually it is a big deal what I mean。

Each LLVM probably doesn't have a multi traded past management and that's why MLIR engineers were happy about it。

So。How it works is we create our。IR and then we specify some passes that we want to process that IR for us and after applying those passes on the IR。

 we end up with a new IR like a processed IR that might be optimized。

 depends on the different passes that we applied on it， it's a different pass。So。

In previous episode saw I showed you how semantic analysis works in the Australian compiler。

 but in the future， in the near future。We're going to move most of the logic of semantic analysis into the past infrastructure。

How it works。What I want to do is actually to have a one on one mapping from the ASD nodes into SLIR operations I'm going to show it to you in a bit。

 but when we do that then our first layer of abstraction would be exactly the same as the ASD we have。

And then we can use different passes to do some sort of analysis on it， type checking on it。

 and then pass it to the second layer to run some other passes。

 like lower them to other dialects and things like that。These passes can actually。

To pattern relating， how it works is you can define your patterns。

And MLI or and Lium both provide a pattern matcher。

 So the pattern that you write will be matched against some patterns in the I on the IR level。

 and then you when your pattern matched to a certain code。

 you can make decision on what to do with it either rerite it to another。

SSA form or like a other make some changes to the IR remove it。

 add more stuff to it or change change it to another dialg。

 which in case of changing to another dialect in MLl IR terminology it's called lowering to other IR。

 So for example， our first layer of IR is called SL IR and。

What I do is actually to use the pass infrastructure to lower or to translate or SLIR to other dialects like STD diallas or a CF dialg that I showed you earlier。

We can write these patterns and like rewriting rules with table Gen as well。

 which is a big plus list got to write， so that's perfect。

And let's talk about the operation definition of specification or ODS and basically how that table like how the table gen looks like。

得得得嗯。What is this thing， actually， Oh whatever。I'm going to show you something from MLIR itself。

 it's actually the table gen definition for toy arts， toy something a new dialect， not a new dialect。

 a dialect called Toy。Which is for an example， like for the ML official MLA or the tutorial。

This is how we use the table again as you can see it's kind of similar to an inscripting language like I don't know Python or some other stuff like it's it's quite simple it's much simpler than C+ plus right we include some of the definition that we have in other places in other TD files and then we created dialect。

that inherits from dialect class， this de actually creates a class。

 then we give it a name some C++ name and space， and then we can create like a base class for our toy operations。

 then we can define different operations that we have in that dialect like constant OP here and the name that will appear。

In the MLIR textural format would be constant and then。Excuse me。

Some actually traits that defines the different aspect of that that operation， a summary description。

 like it's really nice you can actually document your operations here and there must be some tools that generates the documentation out of this description here the arguments。

 the result and result type if there's like a par custom parser for it， a different P layer methods。

 by the way don't worry if you don't don't understand any of this in the future episodes when we want to work actually on the SLIR itself。

 I'm going to talk。🤧Like talk about these kind of concepts in details。Excuse me。

 so what happened to my voice？嗯。As you can see， it's much simpler to write operations and different things that we might need for our dialg in this format rather than writing C++ code and on build time MLIR and tableG our tableG are smart enough to create generate the C++ code for us out of these definitions。

Going back to your slides， I can't call them as slides， but whatever。Let's see some examples。

I'm using old mode， as you might already know if you want if you're。

If you want to actually see the or see this or file for yourself， just。

You have to have MLIR mode and LLVM mode installed on your emX both of them are distributed alongside LLVM and in the LLVM T so just load them up and you're good to go。

So， let's see the general syntax of。LLVM， sorry， MLOR。I kind of。Use the same。Line of code from。

One of the talks that I put a link to it in the resources section and for。

I hope it's okay I made some changes but。I don't think were going to have a like licensing issue。So。

Let's start by talking about this section。 So as you can see， this thing。

This line of code looks like an assignment。 By the way， it's like a very long。

 very long line of code， and I wrapped it into three lines， so it it should be。Something like this。

 right， I， I broke it down， but it's fine because like， I just wanted to。Wanted it to be nicer。

So the first part， this percentage sign here kind of。

We use personency design to describe a local variable， so the result here is local to that scope。And。

The name result here is an SSA or a CA。Read it's an， yeah， actually。

 it's an S say that has two values。 So unlike LBM or ML I or operations can return multiple values。

 not just one。 And here we have a。Very well that I don't like to say very well。

 let's call them SSA phone。We have a necessary form that has two values。

And the blur operation returns two values。The sum dialect， this part is the name of our dialect。

 which is some dialect and after the dot is the operation ID or operation name so right now。

We're using an operation called bh， the bla operation has one input argument。By the way。

 as I mentioned， the percentage sign is like， okay。

Use this variable or SS SSA form here and this part means I want to use the second third sorry third value of this SSA form。

 like probably this SSA form is defined somewhere and it has more than three values。

 so we want to use the third value and pass it to operation b as the input argument。

Then we have a map of attributes。So we have attributes called sum dot attribute and the value is true。

Another one called so attribute and the value is3 there's a like underline here to demonstrate that we can differentiate them with different characters they're not the same that's obvious and finally after a column we have the input types so since P already just accepts one input argument and that input argument has to be in example type the type of this thing here。

Is example type and this example type here is a custom type for Sun dialect。

And we define types like this like this explanation mark here is kind of a sign to define。

Types2 point to types right so our some dialect must have an example type and that example type is the type of the input argument。

 so it's better like the xSSA form， the third value of XSA form has to be in this type。

And after thisarrow， we defined the。Output type of the current operation like functions。

 you know functions have like a result type operations operations have result type as well don't compare them to functions。

 they're different。Operations， the name is confusing but it's just a concept。

 we can call it whatever we want we are modeling something that we have using operations it doesn't mean an operation has to do something it's just just a concept。

So the result type of our operation， as we already mentioned it has to return two values。

 the first value is in type S， type S， like the name type here is irrelevant we can like call it like I don't know。

Blah， no， bla is not a good name， like P S， for example。

 So the type of the first first return type has to be4 S。

Of type dialect and the second one has to be type C of the same dialect。

 we don't have to always stick to our custom types we can like， for example， do I don't know。

 I ate here。Nothing prevents us from doing that， I'm going to show you more example。

 but just for demonstrations。And finally， a location， every operation in。MLIR can have a location。

It's better to have a location actually， in the engineers。

 I remember that they stated that they have to have a location。

 but like I didn't use a location in in SL IR and it works just fine， but。

It's kind of pointless not to have location like。It would be ridiculous anyway。

 the location can be in different formats， for example right now for the blow operation we actually used a call site location so。

In the actual source code of the like that ser file in line 10 and column 8 in function main。

 we have we're calling something that。That something kind of translates into this block operation right so that's something that we have might be a like a function call or whatever。

 but this like we can actually preserve the storage location where we like where cause。

This operation to be generated and whenever we have an issue or we want to report back to user inform of error or some other formats or warningar or whatever。

 we can use this location and use that source manager that I mentioned earlier。

 we're going to have another episode about that one。

 we can use all these together to generate a report to user to the user。

Let's have a look at another example。Excuse me。This time about blockss and regions。

So this is how we define functions in。MLIR function that a sign symbol means like this is like a symbol。

 global symbol we can address to it from other places in the same module and this function takes like two arguments that first on should be an I64。

 the second one i1 and returns an I64 and here this here liberation is actually。

Is the start of a region， that's how region works in MLIR， like as I mentioned。

 like blocks of coding like regular languages like C++ or Java。

And our region count of several blocks， this is how we define a block， right？

That carriage sign with the name of the block， the arguments of the block。

 basically you have to read about the blocks and regions。

 but how it works is you can kind of think of it as input to the blocks if for example like we can pass values to a block as we do here right we call the block。

 we not call we jump to block 3 B3 and we pass this input。To that block， right？嗯。

Like this SSA form comes from here， we pass it to block 3。

 block3 is here so that SSA form there would be this C in here and then do some stuff as you can see in B actually I added this thing later now I can see the issue here。

 this thing should not be here。Because。Because it's a branch。

 it already means like jump to that block and the operation there would be a like a vase。

So when we move to this block， if I rename this thing C。Stay here。 And it's fine， yeah。

So block number three already has like a operation that that operation has its own region and its own block。

 so we can nest them as。As we as we like and。This way we can actually it will like LLVMIR doesn't have any of this。

 it only has some blocks if you know how if， for example。

 if you want to model an if condition in LLVMIR，Oh， it's hard。

It's actually for that level of abstractstruction， it's really good。

 but for a higher level of abstraction we need。Better tools。 And this is the better tool。So。

LetLet's think of， I don't know。If a statement in a lease， right， So if a statement， not。

 not if a statement， let's find a better。And let's have a micro macro right right。

 Let's have a macro called no， no， no， let's asative。 So in in in a list if works like this。

 like we have a condition。And。And then， block。And finally， an elsepl。没有。

So if you want to use LLVMIR to model this， it would be like。

There's a way to do it and it's like a common way to do it。

 but that if like the if condition that we have here is like a higher level condition like in a higher level language so it makes sense to you like in LVMIR with the blocks and regions like this this would be like a region this one would be a region and we can just pass these two region and we can have like a operation called if for example let's rename these two。

I don't know to。During dot if for example， if OP， and then we can have two regions。

 one for the then block and one for the elses block。

 each of them can have its own set of operations and things like that and we can pass them around and then use the pass manager to optimize them and it's pretty neat actually。

Okay， moving forward， some real example on。Using the Serin compiler。

We can use the following command line to actually generate this this source here， this S SLIR here。

 just to show you。I already did it。Let's change it to SL IO， actually。And generate as you can see。

 I already moved it to the other to the org5， but oh by the way this as I mentioned this interface is going to go away。

 the new interface is different so I'm going to create a branch for this episode in this in this branch。

 this behavior is preserved， don't worry。Okay， let's look at what we have here as you already know the module is the unit of compilation in both LLVMIR and MLIR。

 so we have a unit of compilation called user and the name is kind of optional but I chose to put it there the name of the module directly maps to the name andspace concept that we have and I showed you earlier。

A module has like a region。 And in that region， we can like do whatever we want to compile。

 like to actually， our dial IR resides in the。Module operation。Here， actually， let me show you the。

codeode that we generated from。 So this is the code that we have like a main function that returns like a function that anonymous function itself returns 3 another function called main main  one that has three parameters and returns3。

 I randomly just wrote this with no purpose。So this that one translate to this SL layerR。

 So this is SLR or first layer of abstraction， our dialect name here is serene。

I might change it to another to actually SLIR later on because right now we have just one layer in the future we might have more so it's better to have a like explicit name for each part。

On the first line， we have an operation called FN。The name is kind of obvious。

 we use this operation to define a function but。Why didn't we use。The built in function。The idea is。

As I mentioned， we try to map our ASD to operations in SLIR and then decide what to do with them and since it's the first layer of abstraction。

 we just define a new operation that creates a function or。

Deefine like describes a concept of function and like it has a region obviously we when we define this function。

 we assign it to SS form zero if we don't。This thing called value in the API。

 if we don't give it a name， it comes like MLIR。Fill out the name for us like this like incremental integer values。

And。Inside the function， we have another operation called value。

 that value has an attribute with the same name。Integer0 as the value of value it's hard and the type is i64 this thing this0 here is hard coded in right now because as you already know Anna as I mentioned nearly in every episode。

We want to create the minimal working compiler at first。

 we want to finish up the wiring of the compiler so we have all the pieces in place。

 it doesn't do much it like Disc code doesn't do anything。

 but after we come up with that minimal compiler we have all the pieces ready for us to start working on the actual。

Language implementation， so this thing this zero here is hard coded。

And we don't like the value operation doesn't have any input argument。

 as you can see the type is empty and the actual input argument is empty and finally it returns the I64 and I64 so that number two SSA form here must have an I64 value。

One thing that confused me a lot when I started MLIR is what's the difference between？

Input arguments and attributes。So they kind of the name now that I know it。

 the name is kind of obvious， but back then I didn't know and it confused me， so the attributes。

or compile time so they're static right they had you have to prove like you can't pass them dynamically or at least I don't know a way to do it。

But input arguments are runtime， so when we actually yeah runtime is kind of a correct terminology。

We use some other operation to create some come up with some values and we can pass them around as arguments to other operations。

 like exactly like function arguments， we can pass anything to a function argument at run time and we can do the same for operation input argument。

 but attributes has to be aesthetic static and their compile time。And finally。

 we return the SSA number two。For our function operation。 And then the same oh， by the way。

We have an that we have a map of attributes for the fN operation like the arguments。

 there's no argument， the name of that fN function that is main。

 the visibility of it that should be public， these are things that I care about as the。

Dialect author， right， each dialect might have different operations and different set of attributes。

The second one is the same， but for the main one function as you can see it has three input arguments as you saw earlier in the file right3 VY and N and all of them has to be I64 the I64 again is hard coded but we can use like inference later or we come up with a function signature definitions synts to get these it's not important right now let's just keep it and stay on course。

And then when we come up with sorry， when we came up with the SLIR。

 we can transform the SLIR or as I mentioned earlier， lower to other IRs， other dialects， sorry。

 we can do this do it by。This command， let me show you。 So not here， sorry。Visit。Here。

So same command as before， but instead of emitting SLIR emit MLIR。

 the name is kind of confusing right， I chose the MLIR I might come up with a better name in the future。

 but to kind of to point the fact that，This IR level contains everything that MLIR provides no sign of SLIR in this one。

 so we use the pass pass manager and pass infrastructure of MLR to convert this SLIR for S code to the。

To other dialects in this case STD dialect and the B in dial right so remember this function here that we define as an operation it kind of translates to an actual function as you can see like especially in case of main one it has the arguments that we provided earlier。

It's still very basic， but for a showcase it's good enough。And the value operation operator。

 I'm confused that operation， sorry。Translate into the constant operation of STD dialect。

So and then we actually use the same pass infrastructure to。

Lower the STD dialect into LLVMIR LLVMIR is an IR is the last dialect that we want to use this one directly translates into LLVMIR and makes our lives much easier。

 we don't have to work with LLVMIR anymore at least that much。And。

We can use LI emit to LIR actually as you can see here let me use my mouse as you can see here to generate this one into this thing by the way here when we ask screen to emit LIR it already knows how to lower SLIR to MLIR and then how to lower SMLIR to LIR so it happens automatically we just by providing the emit a step kind of we interrupt the compiler at a certain time and were like okay finish up after you generate LIR for me and don't continue and the same here right。

This block of STD dialect directly maps to this block of LVM dialect。

 as you can see like there's a function then constants like it's kind of similar because like。

The dialect we had was quite like the code was quite。Similar sorry， simple as well。But。

One thing to note here is that。As you can see。The funk here。

 the function here looks like an operation right like the syntax。

 the general syntax that I explained earlier， this function here。

 this is like the dialect name and the function looks like an operator but it's kind of different than the general form。

 where is it？It's different than this form， right， but there's some similarities。

 So what happens here is that。Like this is a guess and it's like a kind of a not possible like。

I'm all like 99% sure。This LLVM dial Act。Created its own verifier par and printer。

 So this thing that we see here is actually the result of LLVM dialect printer。

 So since you can have your own par and printer for each operation。

 then you can actually eliminate all unnecessary things from your dialect and make it nicer like this this actually looks nice and easy to read。

 right。So， anyway。When we get to this point and generated the L VMR， then we can again use the。

Pass manager and pass infrastructure to lower the LLVMR to actual LLVMR。

 so we can use the emit IR to actually generate the LLVMOR。



![](img/64f1576f0836b4af49b069f14dabfccf_7.png)

And the code that you see here， like this piece， this piece here is the。



![](img/64f1576f0836b4af49b069f14dabfccf_9.png)

Result of translating and converting the LLVM IR dialect to LLVMIR itself。

 and we can pass like this thing to the LLVMIR compiler and compile like compile it to target code and create a native binary out of it。

 as we do in string compiler， I'm going to talk about it in the future。

 but for now as you can see we have like a。How it works I'm going like we're going to have another episode talking about ElviM specifically。

 but for now just as a quick overview is's like。Saying that we have like a malloc function and a free function external to this module。

 like import them， you know， and then define a main function that returns I64 and returns number three there。

Same thing here with some width function main one， three input arguments， and some metadata。So but。

When we get here， then everything is ready to actually。Generate the target code。

We might again run some passes on the generated LLVM IR as well to do further optimization here as well。

 like on each step we can have some specific passes for that step to optimize the different level of no IRs in different layers based on the semantics of that layer right and finally when we optimize this piece as well。

 we can use the。Pass manager， there's a pass to generate object code out of this one out of the IR and finally by generating the object file。



![](img/64f1576f0836b4af49b069f14dabfccf_11.png)

Our work is kind of done then we use a link here to generate the actual binary don't worry I'm going to talk about all of that steps in future videos like I'm going to show you actual code。

 but needed we needed to know the basics of MLOR to be able to actually understand the。



![](img/64f1576f0836b4af49b069f14dabfccf_13.png)

Code that I wrote for。for the entire IR generation。And finally。

 here is a list of resources that I highly recommend you to actually have a look at the first two or two presentations by the。

MLIR engineers， they're pretty good。嗯。Unfortunately。They're really good。

 but they're quite short so one hour is not enough to talk about MLIR honestly like it takes a long time I read about MLR and LLVM almost every day and I feel that there's like tons of information that I'm missing and I have to read so the docs of MLR are your friend there's。

Good amount of document。But documents but。There's a lot of documents missing as well。

 The language reference describes everything I， I talked about today， but in details。

 it should be your reference for the language like for the ML IR language itself。

 And some information about the basic block， the block concepting compilers， if you need， by the way。

 I already。Mention in the episode1 there's two books for compiler design。

 if you're interested read you have to read those as well， especially the T book is quite short。

 the dragon book is longer but it's kind of the Bible of compiler design。That's it for today， folks。

If you look if you like what I do， please subscribe to my channel and leave a like。

 and if you have any question， please comment。In the comments section of YouTube or reach out to me。

 thank you for stick around and have a lovely time， see you in the next episode。



![](img/64f1576f0836b4af49b069f14dabfccf_15.png)