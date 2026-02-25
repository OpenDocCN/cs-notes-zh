# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p05 -P05-Lec 05 - Compiler Correctness; Booleans (Interpreter).zh_en -BV1zQ27BeEfF_p5-

Alright， hello， everybody。 We're gonna go ahead and dive in because last time we were here。

 we didn't quite manage to finish up unary operations。 And so we are gonna be trying to do that。

 I'm sorry， we couldn't see today's topics up here。 Okay。

 so these are today's topics versus things first。 We're gonna finish up those unary operations。

 We're gonna talk about compile time versus runtime。

 We're gonna talk again about compilers versus interpreters。

 Were gonna talk about how we persuade ourselves that our compilers correct。😊。



![](img/a731a27b73cf71306fa9d09a4da0c5a8_1.png)

We're going to talk a bit about Booles。 And I think we'll probably add them into the interpreter today if all goes well。

 Probably not into the compiler。Here we are， we have been thinking about， oh， sorry。

 before I dive in on content。😡，Quick reminder， even on weeks when there are no homeworklash programming projects do there are still drills。

 Please still fill in the drills that we know how y'all are feeling about all the various topics。

 we can make sure that everyone's on the same page。

 So now let's finish up that task that we had started。

 and we had decided some things about how we wanted to actually implement unary operators。

 So in particular， we had decided about the outputs， hopefully the outputs are uncontroversial。

 But we had also decided some things about what would or would not be satisfying implementations。

 And I want to remind ourselves that one of the things we decided would not be satisfying was if we just went ahead and tried to do this computation at compile time。

 and then just popped the answer associated with doing that computation。

 if we just popped that into the compiled code directly。

 And the reason we decided that wasn't okay was because we might eventually want to take some input maybe we were gonna go ahead and read something from a file or we were gonna ask the user to type some input。

 And if we were gonna be getting some input。😊。

![](img/a731a27b73cf71306fa9d09a4da0c5a8_3.png)

![](img/a731a27b73cf71306fa9d09a4da0c5a8_4.png)

Then we knew we would be in trouble if we were trying to precompute everything and we had no way to actually have the assembly itself do the addition。

And so I'm going to run us through a visualization that we are going to see a number of times over the course of the semester of what is happening on our machines when we are running our assembly。

And this will basically be a picture that we draw that is going to get increasingly complicated as we understand more and more about what our processor is doing。

 but for now we have a quite simple one， but I still want to just talk us through what's happening when we run this assembly。

 which is the assembly that we actually want to om in order to implement the program that we talked about up here of a 150。

And you can see that if you take a look at this assembly。

 it sure looks as though what it's doing is coming up with 50 and then doing the addition right there。

 and we'll find out that that is， in fact， exactly what's happening。

 So the first thing that happens is we see a label。 that turns out not an instruction。

 we don't have to do anything right That's not something that actually goes to the processor。

 That's something that we're using as sort of a little helper for ourselves and we will eventually figure out how we can use it to jump to the line that comes after。

 which is in fact， an instruction。 So what happens when we run this instruction。 Well。

 the only thing that happens is we come up with the value 50 and we decide to put it inside the register RAX。

 So I'm going to go ahead and write that like this inside RAX right now， we have the value 50。

And now if we go on to that next instruction right here， we can see， okay。

 all we're going to do is replace whatever is in RAX right now with whatever was in RAX plus 1。

 which is to say the value 51， and then we go ahead and we actually return control to whatever called us。

 which in this case is going to be our C runtime。Feeling pretty comfy about this assembly。Amazing。

 let's make sure that our compiler can actually emit it， so let's turn back to our compiler。 oops。

 let's plug in my laptop to the projector so that we can see where we were with our compiler。😊。



![](img/a731a27b73cf71306fa9d09a4da0c5a8_6.png)

![](img/a731a27b73cf71306fa9d09a4da0c5a8_7.png)

Lovely， okay， so we left it in a little bit of a weird spot actually。

 so we can take a look here and see that we had figured out this sort of wrapper function that we were gonna want。

 The reason we decided we wanted this raper function was because we figured out that if we started trying to have the nu case here and then the add one case we were gonna end up having this repetitive boilerplate。

 which was going to get in the way of some of the things we were doing。 And so we decided， okay。

 let's extract that boilerplate out， let's put that in this little compile helper function。

 And what we'll have in here is some of the same things that you'll see right。

 we have that global entry thing。 We have that label entry thing and we have that thing that is actually returning control to the runtime。

 But then in the middle， what we're doing is actually pretty simple。

 We're just making this call to compile X。 And what we will expect compile X to do。

 is make sure that whatever assembly is going to put the answer associated with evaluating our program。

 Whatever assembly is going to get that value inside R X had better come from a call to compile X。😊。

So let's go ahead and fix up what we've got in here。

 Let's ignore add1 for a moment because we're not still totally sure what to do there。

 but we're pretty sure what to do with a number。 So let's go ahead and remove the parts of this that we no longer need right we're no longer putting the boilerplate right here We just need to go ahead and move that immediate value into RAX and in fact we no longer need to do the string concatenation stuff because all of that is being handled out here at compile。

So okay， we now have what we want inside that little helper for handling numbers。 But of course。

 the reason we were doing all this transformation， the reason we started working with our nice representations of assembly。

 but also our nice representations of S expressions。

 which do turn out to be for symbolic expressions。 That is what the S stands for。

 The reason we were doing all of that was that we could have sort of nicer stuff happening in here。

 which would make it easier for us to write the next thing。 So let's go ahead and extend to that。

 Let's do list。Sam。Add one。 and what I want you to do is discuss with the folks nearby。

 what do we want to have。On this next line， right， when we are handling and add one expression。

 what is。The assembly that we want to emit。Go ahead and discuss for about a minute。All right。

 so I'm going to ask you to hum this line that I've put in here that says add。

One to whatever is an REX right now， is that going to be sufficient， hum if you think that's it。

 we're done？Hum， if you think not so much。Yeah， I totally agree right so we at first better make sure that whatever's an RX right now represents the argument right。

 we haven't used AG and in fact， oh Caml's even warning us that we haven't used Arg。

 so what could we do to make sure that the value that is associated with evaluating Arg is getting put in RAX？

😡，Go ahead and discuss for 20 seconds with poll's nearby。All right。

 I'm hearing the answer that I hope to hear。Which is we actually already have something whose role is to put the value of a particular expression inside RA X。

 We already have something， and that is compile X。 So if we go ahead and just make our recursive call here。

😊，On AG， that is going to make sure that the value associated with actually evaluating Arg that it is going to emit the assembly instructions that are in charge of putting that value inside RAX。

So let's first go ahead and make sure Ocal knows we're allowed to call this recursively。

 And then let's go ahead and do our list concatenation to make sure that whatever comes out of this call gets mashed together with this edition and will be good to go。

 Are there questions about this。We feel good about our recursive call。Amazing， okay。

 so now I think we're probably all going to be able to guess what sub1 is going to look like。

 So let's go ahead and do that real quick。😊，And then let's make sure that this is how to actually work for us。

 So let's do Dunne U。We will open。Our compiler。Un let's compile and run。Add one。

Our programming language has been extended。 It is no longer just numbers。 we can do computation。

So here we go， we can oops， I've mixed it up with sub one。

 let's make sure that I actually saved the file after doing that。So let's do。Oh。

 that's how I mixed it up。 I added too many parentheses。 Okay， great。

 so we can go ahead and have these nested calls。 That's all fine。 That's totally fine。

Any questions about how we have implemented addition and subtraction here？

Our first add1 sub1 unary operation。Yes， so right now we I guess yes。Oh， I love this。

 So this is something we're going to be reflecting on later in the class session。

 What kinds of values do we have access to right now。

 Can we have anything other than numbers as the type。😊。

Of the values that we are actually manipulating in our programming language。Yeah， I agree。

 So the only thing we've got right now is numbers。 so we don't have to do anything presently to check if we've got a number coming in。

 But if you remember the slide that I showed at the beginning of class。

 we might have something coming in soon。Okay， amazing。 So let's go ahead and step back for a moment。

 I'm going to bring us back to our whiteboard。 And I'm going to have us reflect for a bit on。😊。



![](img/a731a27b73cf71306fa9d09a4da0c5a8_9.png)

Basically what we mean when we're talking about a compiler versus an interpreter because we're about to complicate our story a little bit。



![](img/a731a27b73cf71306fa9d09a4da0c5a8_11.png)

So we have these three columns on this diagram。I'm sorry， three columns， I mean。

 because we have sort of this thing on thes this thing on the。And it's not working。Okay。

 there's the thing on the left of this line， that's the first column。

 there's the thing in the middle， and then there's the thing on the right。

 so everything that's inside the blue box represents the things we have to do in order to use a compiler to get a value associated with the program right everything that we see on the right side is what we have to do in order to use an interpreter to get the value associated with the program。

And so what I want us to think about right now is actually a couple things。 I want us to think about。

Basically， what is happening when we use these。 So I'm going to turn to。Yeah。

 let's actually turn to this slide and what I want you to do is come up with with someone nearby when we are talking about each of these three columns。

Is the stuff that is happening in that column happening at compile time or at runtime Now we've talked about these phrases a little bit a couple times now。

 but always sort of been passing。 And so now I want to say that they mean exactly what the names sound like right Comp time is the time that we are compiling a thing runtime is the time that we are running the thing and we are going to use the terms static and dynamic also to talk about these So if we are describing something as static that is almost universally going to mean that we are talking about something that is happening at compile time。

 if we use the term dynamic that is almost always going to mean something that is happening at runtime And so what I want you to go ahead and discuss with folks nearby for each of these three columns is is this process The thing that is depicted in the column Is that happening at compile time or at runtime Go ahead and discuss。

でもじねい。All right， so let's go ahead and decide for this column right here。

 do we think this is happening at compile time， home for compile time？For runtime。I totally agree。

 right This is compilation。 It really it says it right in the name at this point when we are using the compiler。

 we are using it to pop out a program that is compile time What about this middle column Do we think that this is compile time home for compile time。

😊，Hum for runtime。I totally agree。 And so this is one of the things that's so weird about using the compiler。

 right， is at this point， we have a representation of the program that we are trying to run。

And we could throw away every copy of our compiler。 right， We can just toss that in the trash。

 Sump on and destroy them all。 We might not have that compiler anymore。

 And we could still run this program。 And That's totally fine because we now have the representation of everything we need in order to run that program。

 It doesn't have to interact with the compiler at all。 We've got the。

 the representation that we are going to use。Okay， and now onto this third column。

 do we think this is happening at compile time， Hber compile time？Hum for runtime。Yeah， I agree。

 right， at this stage we are actually running this program。But this is a little bit kind of mind。

 Beny， right， Because surely at some point， the processor has to come into play。

 which means something must have made those ones and zeros。 Where did those ones and zeros come from。

 How did we get those ones and zeros。How do we manage to even get out this value 42。

 if not by using the processor， if not by somehow having a compiler in the mix that produced something that we could send to the processor And so that's what I want us wrestle with for a moment If you have a piece of paper。

 go ahead and pull out your piece of paper， if you don't have a piece of paper。

 just jot some notes to yourselves about what we think is going to be in this orange box。

 but I'm going explain what we're thinking about here so I've sort of broken open what's happening inside the compiler versus what's happening inside an interpreter。

 and I'm going to sort of talk us through the stages bit by bit。

 And then I'm going to ask you to try to come up with what's going to happen inside the interpreter。

So here we go， we've got a program written in 64 or 164 L， right。

 our little scheme that we're making， it is written there。

And that is one of the inputs along with this file we have written compiled do M right。

 that is just an Ocal program right so we wrote some Ocal inside compiled。

m and we fed that along with this program in the programming language that we are inventing。

 we fed both of those into the Ocael compiler。😡，The Oamml compiler says， okay。

 I can take these inputs and I can actually use that to produce some assembly。

 we've seen it appear inside program do S。RightAnd then that assembly that we see inside programs。

 we can do various transformations to come up with machine code。

 and then we can pass that machine code off to your X 86 processor of choice。

And now we get this nice little answer 42。Right？So that's how we go from a program to a value in compiler land when we are using a compiler。

So this， I think， makes it pretty clear where we are getting that assembly that we're eventually running。

 right？😡，In some ways， it's a little bit wacky because it does seem like the Ocael compiler is involved somehow。

 but ultimately we know that this program that we wrote compiled。 ML is emitting assembly。

And that's the stuff that's eventually going to actually run on the X86 processor。

So I think it's kind of clear where the ones and zeros are coming from here， yes。😡，Seing the is。

Great question。 So this question is about our compile and run helper。

 where we have sort of pulled together both the process of doing compilation and the process of running。

 and that is exactly the process that we're showing right here。

 right So when we see that we're first running the compiler。

 And then we're going ahead and immediately running the program using the computers process。

 That's sort of talking about both the compile time process and the runtime process。

 So this whole process， right， getting to the machine code。 That is。

 let me actually use a thing to point to this， right， This is all happening at compile time。😊。

This is all happening at runtime， we can choose to just go ahead and run those in sequence。

 and that's what's happening inside compile and run or helper function。😡，Yes。

 everything about this image is exactly what's happening when we use compile it。

So does anyone like have any questions about where those ones and zeros are coming in， Like。

 we're all like pretty sure that they're probably inside here。Hopefully we're pretty sure about that。

Okay， great。 So now I want you to focus with someone nearby on what's going to happen inside this orange box。

 right， I'll draw one of the boxes inside here。 So we're going to have an Ocal program called Interterp。

😊，Dot M L， right， That's going to be one of the things involved。 We'll have that box inside。

 Where are we getting the ones and zeros， Fill in the rest of this box so that it's clear where we're getting the ones and zeros。

要求到一块。せて。All right， so we're starting to quiet down， so I'm going to start talking through。

The pieces that are happening here。Right。So we've got this OCMl compiler。

If we think about what the OcaMel compiler is doing。

It is in charge of figuring out how to turn a program， an Ocael program。Into ones and zeros。

And so when it gets as input， this Ocal program。Right， interpret M。

 we are like in our heads when we are writing an interpreter for our scheme。

 we're like this file that I'm writing， this is the interpreter。

 But from the perspective of the Ocal compiler， that's just another Ocal program。

 It knows how to turn Ocal programs into ones and zeros。

 So when we get in interpret M as o as one of our inputs。

 And we also get this sort of input that's taken into the program itself。

 we can go ahead and turn that into the ones and zeros。Machine。Code。

That then we get to run on the computer's processor。And that's totally fine， right， It is OCel。

 the implementation of OCel， however， that was implemented that has to figure out how to turn this OCel program。

Into a bunch of ones and zeros。 And from the perspective of O Camel。This sort of interpret。

 MLl program we have that doesn't care what it is， it doesn't care that we are seeing that as an interpreter。

From its perspective， one more O camel program， no problem。Should we feel yes？

I love this right so if we think back to when we were talking on that very first day about what is the type of a compiler。

 what is the type of an interpreter， we said， okay。

 the type of a compiler is some input program to some output program。That's sort of what's happening。

 we're getting a program in and we're getting a program out。The interpreter， on the other hand。

 is taking a program as input。 I'm sorry， I'm gesturing the wrong way for y'all。

 It's taking a program as input， and then a value is coming out the other side。

 And so that will be the role of our interpreter。 It is supposed to go ahead and calculate。

 analyze this program that it's getting as input and just pop out the value associated with running it。

Make sense。Yeah， it is a little mind bendy。We have other， yeah。找。need to like do all that。

 like breaking up and putting it back together， given like we have better。

The linker is just to make sure that the different parts of our program can talk to each other。

 right， so by default， our little C program right that we've actually used to make the runtime。

 it has its assembly that's generated。 We have our assembly that we've generated。

 We just have to make sure that those two can talk to each other。

 That's all we're using the linker for。 Could we like one shot。咁排呢个是个。It's just like。Oh。

 I love this question？即咩。So I think this question， Well， okay。

 I might not understand this question all answer the question I think you're asking。

 So I think the question is， do we need to have the runtime。

 What if we just generated all of the assembly ourselves that way we would already know how to talk to itself and we could just run that。

 And that would be totally fine， There are some things that are really。

 really annoying to directly implement an assembly。

 And if we don't care about how having lowlel control over how those things are implemented。

 it makes more sense to put them in the runtime， if we don't care about being able to really explicitly control the particular assembly that's gonna get emitted for this thing。

 we usually pop that in the runtime。 And so for that reason。

 it is useful to go ahead and have these two separate components that we then link together。

But it's not really a big deal， right， This is this sort of blinking process is very easy and mechanical。

 not a huge， yeah。Yeah。In。St need to know them like specs。I love this question。 So this question was。

 this interpreter， you know， we're thinking of it now as just being an Ocael program。

 Does it need to know what hardware you're going to be running on。😊，And the answer is basically no。

 right， assuming our Ocamel compiler or whatever it is that we're using to actually implement our language。

 assuming that that tool that we are using in order to get the ones and zeros can make the ones and zeros for whatever processor we're actually going to run it on。

 We're good， right， Like we don't have to have specialized the interpreter for X 86 the way we are specializing our compiler for X 86。

So yes， it can be agnostic to what it's going to be running on as long as the program that we are actually using to compile it because there's a compiler that's going in feeding it in right as long as that tool can figure out how to run it on the hardware we're targeting。

Yeah。Oh， I love this question。 So this question is， could we actually sort of hook these up together。

 right， say I want to go ahead and implement my my little scheme by writing something that compiles it to Python and then the Python interpreter is going to run Well。

 the Python interpreter was written in some other language And so that language， right。

 whatever was actually used to write my Python interpreter。

 that's the thing that's going be in charge of producing the ones and zeros there。

 absolutely is that the question Yeah， we can do all kinds of ways of linking this together。

 like we can put compilers and interpreters and all kinds of sequences that it's totally fine。

Now recall that the interpreter， its goal is to actually produce the value。

 and so in some ways that's supposed to sort of bottom it out。

 but the thing that actually produces the ones in zeros for getting that value out of the processor。

 right that can be doing all kinds of things。I love this question。

 when should we use a compiler versus an interpreter？

There's sort of the the first draft answer of this， which is in general。

 because you get low level control over the assembly that you're emitting or the low level language that're emitting。

 you don't have to admit assembly when you're writing a compiler because you get a lot of control over exactly how the program is going to run。

There are some performance benefits to implementing your language of the compiler Now on the other hand。

 it is usually a lot harder to reason about a compiler than to reason about an interpreter。

 This is not universally true， but this is often true and so often if you are looking for something that you can pick up really quickly and you can really quickly make an implementation for a language you might be looking at an interpreter。

If you are looking at I want to make something that's gonna be super high performance。

 you might be looking for a compiler， but this is not a hard and fast rule right so you can absolutely make interpreters that are very performant。

 something that came up the other day was this idea of just in time compilation and that we can figure out that this part of our program is being run a lot and so we can do some compilation inside the interpreters So there are things we can do to make interpreters fast。

 there are things we can do to make compilers easy to reason about And so this is sort of a general guide for when we're reaching for these。

 but basically one of the goals of this class is you will understand more about the tradeoffs between these by actually implementing them。

 So you will have a much better instinct for when you want to reach for one versus the other by the end of this class。

Oh， very interesting question。 So does it have to do with the syntax。 So， no， right。

 we can invent a compiler and an interpreter for the exact same language。

 Nothing stops us from doing that。Is one harder than the other。Bless you。

So is a particular kind of syntax going to be harder for a compiler versus an interpreter or harder for an interpreter versus？

H。Make ways。Oh this question might be about what language should we use to implement an interpreter。

 What language should we used to implement a compiler。 Yeah。

 so all of the same stuff that we have talked about in the context of why we have used Ocal for this class。

 it's all the same deal right so like if we care about the compiler itself running really quickly。

 maybe we would actually choose a language that we know is going to run fast like it is implemented in such a way that the programs that we write in it are going to be efficient。

 So if the compiler speed itself， not the output program speed， but if the compiler speed matters。

 we might choose a language that we know is going to be very fast。In general。

 mostly were picking based on what is going to help us write the particular kinds of。

Programs that we need to write right it's sort of the same way we choose a language for any kind of program that we're writing like do we think it's going to make it easy to create a program that has the characteristics we wanted to have？

Okay， so now we have wrestled with how we can use an interpreter。

 even though the interpreter is not necessarily going to be popping out something that is visibly assembly instructions。

 right， We are not going to see that assembly representation of the program ourselves。

And I now want us to turn to something a little bit different。 So I want us to。

 it's going to seem like a left turn。 I promise it's going to connect。

 I want us to talk about how we can persuade ourselves that our compiler is correct So I'm going to turn us for a moment back to the compiler that we just looked at and what I did to try to persuade all of you that this compiler was correct is I ran these programs right。

 I ran add 1 sub 143。 I ran add1 sub1 sub 143 as like， look doing the right thing。

 don't y all believe we that it is correct。

![](img/a731a27b73cf71306fa9d09a4da0c5a8_13.png)

![](img/a731a27b73cf71306fa9d09a4da0c5a8_14.png)

And so what I would like you to do right now is hum， if you think that this is persuasive。Hum。

 if you think this is not so persuasive？Absolutely， I love this skepticism。 right If GCC was like。

 yeah， yeah， we try to out a couple programs。 the new version looks fine。

 Like we would probably not be feeling super comfortable with that。

 We like to think that our compilers are being evaluated， validated。

 you know checked more thoroughly than that。 And this makes a lot of sense because errors in the context of a programming language implementation are super high stakes In the worst case。

 a bug that we have left in our programming language interpretation。 whether that's a compiler。

 whether that's an interpreter can actually end up introducing bugs into all of the programs it is used to compiler interpret。

 And that's a really bad outcome。 sometimes this means planes crashing。

 sometimes this means I don't know， websites going down and people losing a lot of money。

 the various ramifications can change， but we have some reason to think that programs are kind of doing stuff out in our world that matter and that introducing bugs in them is bad。

 And again， if a compiler or an interpreter。😊，them if the language implementation is introducing them。

 it can potentially be putting bugs into all the programs written with that language。

 So I want you to discuss with folks nearby for about two minutes。

What should we be doing to persuade ourselves that this compiler or any compiler is correct？😡。

All right， I want you to start yelling stuff out， what do we got？Checking it。Oh。

 checking against another language implementation， love that。😊，I'm hearing formal verification。

 I was expecting that from this chair and I'm the of the classroom， yeah。

 absolutely formal verification， I love it。Testing， yeah， absolutely， right。

 We often when we think about trying to persuade ourselves that our software is correct。

 we are often thinking about testing。Okay cool。 So that's giving us some strategies。

 I'm going to talk us through these strategies and what might be the pros and cons of them。

 right So I think testing is a supernatural version of sort of the first instinct right so we can do basically the automated version of what I was doing up here when I ran things on a couple examples。

 We can write unit tests for individual elements of the compiler。 We can write particular program。

 run the assembly output and say that we expect a particular value So that's all good。

 compileilrs are interesting because they're actually these two different ways for us to think about what it means for the compiler to be correct。

 We can think about actually examining the program that comes out the other end。

 or we can think about running the program that comes out the other end。

 Both of those could be interesting ways of operationalizing what we mean when we say testing。😊，嗯。

We could definitely do， especially the thing of looking at the， the text， the。

 the text of the output program， especially when we're thinking about optimization。

 whether an optimization breaks things。 So these are reasonable ways to test。

 And testing is going to be part of our answer。Exまて how you aboutな。I'm so glad you asked。

 We're getting to that in a moment。 So before we get into how we automatically prove。

 let's first think about how could we prove just by sort of。😊，Our sort of standard pencil and paper。

 right， So one thing that we could do is just stare at it for a really long time and persuade ourselves that is doing the right thing。

Right， like this seems like sort of a weird strategy。

 but that is actually a huge part of how we usually persuade ourselves that various programs are correct is we have looked at it。

 and we sort of trust that it is doing more or less the right thing。

 Maybe we step through line by line。 Maybe we use some paper and pencil proofs。

 So it's not that that's sort of not part of the story But I think what your question was about was could we do a formal mathematical proof。

 a machine checkable mathematical proof。 And the answer is absolutely yes。 So traditionally。

 program verification was super expensive， super computationally intensive。

 actually pretty difficult for programrs to get working。 The idea with formal verification is。

 in addition to the program that you were trying to verify。

 you write this other program and the purpose of that other program is to persuade the computer that this program you have already written is correct for some definition of correct。

 So you first have to think really hard and write。 what would it mean for this to be correct。

 And then you have to write this whole fancy formal verification program where the the goal that it is doing is。

rying to persuade some kind of proof system that your program is indeed correct in our context that would be your compiler is indeed correct。

 And so for a long time， that was really expensive and really hard to do。

 And we just could not figure out how to extend that two programs that's complicated as compilers。

 But then a little while ago， like over the last couple decades。

 we started to get a lot better formal verification。 we've gotten really good tools for it。

 And so now we even have a formally verified compiler Comp if you're interested in looking at what a sort of formally verified compiler looks like。

 look at Compt。 it's really interesting， they years later did this really cool test where they were testing a bunch of different implementations of the same programming language in order to figure out by sort of comparing the answers that they got out of those different implementations comparing those to find bugs in the various different implementations of that same programming language。

 and they found bugs in all the implementations exceptt a formally verified parts of Compt have been formally verified。

So definitely formal verification。 we had that answer back there as well。

 A approach in our context because formal verification is still fairly hard for programme to apply。

 we are going be doing something a little bit different。

 which was actually the first answer we got and I think is a really good answer which is we are going to go ahead and have a reference interpretation a reference interpreter a reference implementation。

 something that we can look at we are going to be able to persuade ourselves somehow that it is correct and we are going to say if our implementation of our compiler matches with this reference implementation。

 then we have persuaded ourselves that it is correct。😊。

And so what does that mean about how we should implement our reference implementation？ Well。

 it probably means that we should implement it in a way that's going to be so， so。

 so easy for us to reason about it。 We are going to be able to look at it and be really pretty confident that it is doing the right thing because we want to be able to point to it as this is the source of truth about our programming language。

And so what does that probably mean based on the discussion we just had about how we might pick whether we're doing compiler versus an interpreter。

 Well， probably for our reference implementation， we're going to want an interpreter because it is going to be a lot easier for us to reason about it most of the time。

And so that is the approach that we are actually going to take over the course of this class。

 we are going to actually have a reference interpreter that we are designing building right alongside our class compiler。

 and so you will start seeing the interpreter in that repo that is tracking the course compiler。

 you will see the interpreter as well， it will usually be a simpler way of reading and understanding what the language is doing and you will also be doing the exact same approach in your homeworks。

😊，And so what we will be doing is always checking interpreter risk compiler。有没有事？再来看。

You make mistakes。くさい。You might think like their work。I love this question。 So this question was。

 could we just go ahead and go out there and find an existing implementation of the language and use that as a reference implementation？

 And the answer is yes， if you were building a language that has been built before on the other hand。

 if you're inventing a new programming language maybe you're building this implementation because you just want a more efficient or a more memory efficient like there's maybe there's some reason that youre reimplementing existing programming language But a lot of the time you are trying to implement a language that isn't actually implemented out there in the world。

 in which case that approach might not work so good， and in fact。

 that's even going to be the case for us right because we are growing this language incrementally So there actually isn't。

 well okay， I've written one， but there actually isn't a reference implementation out there for our language at sort of each stage there's various scheme implementations that implement a superet of the things that we are implementing。

 But yeah， in terms of the specific language that we are implementing。We don't have that match。Very。

 very good question。Okay， yes。Can you ever be fully certain？这边确。

With a reference interpreter or a reference implementation。

 can you ever be fully certain that you are correct？😡，I would argue， no， right。

 So the reason that we think this is a good way to be fairly persuaded is because we know a lot about how to write interpreters and how to write interpreters in a readable way。

 And so if you look at the interpreter that we are going be developing we are going to be doing nothing to make it efficient。

 We're not going be doing anything to try to make it do fancy stuff or make the programs work well。

 like we are going to be doing the simplest possible thing。 The thing that's easy for us to read。

 and that is basically how we are going to be making that argument to ourselves。

 that we have landed on something that is correct， right we are going to look at it。

 we're gonna to do this thing of looking at it really hard being like that looks to me like it is doing the right thing and then we're gonna to see for many test cases。

 which hopefully we have chosen intelligently for many test cases whether we're getting the right answer。

 But there are two ways that could go wrong， right， Like maybe there's a test case。

 we didn't think to include there。That doesn't look good for us， or maybe we have in fact。

 implemented the interpreter the reference and implementation in some wrong way。

 and both of those could go wrong and lead us atray。 So if you really， really。

 really want to persuade yourself that a program is correct and that applies in this setting。

 that applies in whatever setting， you want to be using formal verification。

So that's why Comp didn't have any bugs。Other question。Okay。

 so I promised that our interpreter was going to be easy to write and easy for us to reason about。

 Let's go ahead and see if that's actually true。 Let's try it out。So。

It's going to have a lot in common with the structure of our compiler。

 so let's go ahead and take advantage of that。 let's copy this。Let's go ahead and make our new file。

Interptt Ml。Great， okay， so what are we not going to need Well。

 we're not going to need this assembly library anymore because we're not emitting assembly here。

 we're just trying to get to the value so let's go ahead and get rid of that。

We're still going to need to express when the program that the programmer tried to pile in isn't actually something that we can handle。

 So let's leave that in。 Let's rename this。 Let's go ahead and call that interex。

Because we are now interpreting the expression。Do we want to produce a directive list。

 I would argue no， anyone want to yell out what we might want to produce if we are trying to get the value associated with the program？

I hear inth。 I totally agree。 I like that。 So let's get an inch。

 What's the int that we should get if we have seen a number。I'm hearing N。 That sounds good to me。

 right？ That's the number that we see。 That is the value that we're interested in。 I like it。

 Let's do N。 What about for this edition。 What do we want to do here。😊。

We certainly don't want to call it compile X anymore， we're not trying to interact with our compiler。

 the last thing we want is to bring in any bugs that our compiler has into our reference implementation。

Hey， let's do the recursive call that makes sense here。

 so let's recursively call Inter X on Arc and then probably we're going to want to go ahead and add one to that right so let's go ahead and communicate about what's happening here。

Let's interpret it， then let's add one to it， and we're going to do the same thing but with subtraction for what follows。

Let's do that。And let's see what happens when we try it。And let's open interp。

And instead of compile and run， let's do。Inter X。Oops。

 you know what we're going to want a little wrapper around this because inter X， as we can see。

 is taking an S expression， I don't want to write an S expression。

 Let's give ourselves a little raper。Let interpretp。Program。String。And let's have it string of int。

 right we want to go ahead and actually pop out a string on an interp X。Pse。Program。

So hopefully it's clear what's happening here， we're using our same S expressions library in order to actually parse that string that well get as input。

 we go ahead and call string of eventch on it， and that's going to give us the output associated with the entire program。

So now that we've got that in place。Try this again。Let's go。Back to our interpreter。

And instead of compile and run， let's do interRP。Great。SoOkay。

 I promise that building up our interpreter would be a lot easier than our compiler。

 hopefully that feels truey all， hopefully you do feel like you can look at this program and sayYep。

 looks to me like that is in fact interpreting our language。するち態。Why are we recursively calling， oh。

 why are we recursively calling inter X？Instead of calling Arg plus one， Yeah。

 so say that Arg was nu N， right， N N has type Sx。It does not have type int。

 So if we tried to just add plus one， right， if we just tried to add one to R。

The thing that is in charge of actually getting the value associated with a sub expressionpression in our language is interex right that's the thing that we actually need to use in order to get an Ocael value out the other side in order to get in this instance。

 an int out the other side。上 up。Yeah。😊，接是。How does it know the difference between the two ends that are right next to each other？

Is that about these two ends？So this is actually us naming whatever is actually used， right。

 Like this is us saying call this thing N。 And then when we want to refer back to it。

 we use that same name。 Yeah， so these matches right， they're very powerful。

 We're using them for control flow， but we're also using them for naming。

 They're combining all of it。All right。So I would say that now we're ready to actually， oh， sorry。

I love this so if we take a look at what is actually happening inside here right so what we expect to have inside our list。

 if you remember when we can we actually take a look inside SX right now this is gonna be annoying to look at hopefully not Yeah it actually is gonna be kind of annoying to look at。

Okay， yeah， this is fine。 So you can kind of see what's happening here。

 but basically what's happening is inside our type。

 we have three ways of constructing an S expression。

 right three constructors just the same as all the other types that we made we have numb of int in this case。

 we have Sim of string， and then we have the list right LST of a list of the same type right sort of that recursive thing。

 And so it's saying that every item that's inside this list had better also be an S expression。

And so if we take a look now at InterML and we take a look at what's happening here， well。

 this is one of those lists， right， And so yep， the first item was made with that SIim constructor。

 We don't know which specific constructor was used to make Arg。

 but we do know that it's going to have type Sx。等着。Amazing， okay。

 so now I think we are ready to use this。 Our very simple reference implementation。

 We can use that in order to actually go ahead and do this differential testing that we talked about。

 I think I did actually introduce its name。 I'm so sorry when we talk about using a reference implementation。

 We were talking about differential testing。😊，So let's go ahead and make ourselves a diF test function down here。

 so we're back in our compiler now， let's do let DF test what it will take in as input is the examples we will use for actually doing our testing。

And that will be a list of strings representing those programs。

 and then we'll want to go ahead and say let results。Results。And they spelling truly is dreadful。

 let results equal list map。function and what are we going to want our function to do Well we're going to want it to run both the compiler and the interpreter on the same input program。

 So for a given example program， let's go ahead and have it make a pair right So this is our syntax for making pairs。

 compile and run X。Inter X Y compile and run well because we are going to be comparing the outputs right we talked about the fact that we might want to compare assembly。

 we might want to compare that other representation of the program。

 but in fact that's not what we're going to want here because there's no reason to think that the assembly that the Ocal compiler is making for our interpreter is going to have anything in common with the assembly that we are making in our compiler and so we just want to compare those values。

And let's make sure we've actually opened inter so that we're allowed to use it。Terp。

So now we should be allowed to use interpret as not complaining anymore。 Great。

 So now we've got our results。 What do we actually want to do it with。

 So we're going to call that on examples。 That's our input right there。 And then in。Nope。

 not in there。In list up for all。Fan。R 1， R2。 so if we've got this pair coming in。

 what do we want to do with it， Well， we want to see if the values are the same Now you might not be used to using single equals here。

 right， that's a little bit weird， you probably used to using double equals when you're doing comparison for our purposes in Ocal double equals gives us physical equality whereas a single equals gives us structural equality you almost never want physical equality So within this context of this course。

 you're probably not gonna be using that double equals。 You get used to using the single equals。

And so that we're going to go ahead and apply to results。

And that will give us basically whether every single pair， right。

 we're going to go ahead and do this for all in order to check whether every single pair of compiler input with compile sorry compiler output。

 inter output， whether those actually match。So let's go ahead and actually call that on some examples。

 let test。What do we want to call it on， let's do。55， let's do。Add one。Sub 1， 30。

And let's see how it all goes。Open it up again。And let's call test。



![](img/a731a27b73cf71306fa9d09a4da0c5a8_16.png)

Okay， great， we got back true， which means that for these two examples。

 our interpreter and our compile and run did in fact agree。

 Now this is not a great implementation of diIF tests， so for example。

 we might in fact want to test on programs that we are intending to cause exceptions right。

 something that wouldn't actually be allowed by our compiler we might want to actually use that in DF tests so you are going to have a better infrastructure for doing differential testing in your homeworks。

 but this is good enough to give the general idea of what's happening。

So let's go ahead and take our five minute break， We'll come back together at 440。

 I'm sorry the five minute break came so late today。Hello。Yeah。

Do like a special topics course in spring， you seen you've done like a youth center。

interesting I think it's a really nice class， it is mostly for PhD students so you have to be pretty comfortable doing research but as long as you're co with that。

I mean， I'm a grad student haven you're fine Yeah， no I think it's a really fun class and I was wondering。

😊，Like the entireverse。You combined both the compilation of the。Addd execution。

Let me go ahead and say yes about that because it made me a bit confused about yeah。

 so we want to run both in order to actually。

![](img/a731a27b73cf71306fa9d09a4da0c5a8_18.png)

Like how get a value out and how it be comparable to the interpreter。

 but in terms of which part is which。The part that I'm highlighting in purple here that is compilation time the part that I've highlighted in pink that's runtime Yeah but the compilation and execution of the O Caml code itself that's all happening at compilation time Yeah but why is this one step？

Why is this one step Because we're executing our chemical if you first have to compile it and then execute it and to me it would be more natural to have them set Oh to show that the computer's processor is also happening in here and that how we're actually getting this assembly Yeah that would be totally fine。

Thanks， yeah。Alo had I quick question Yeah， and you were just talking about like the differential testing in the homework。

I some like raised。Exception。So like in the homework， one of the examples is like raising us stuck。

Exception， and that takes like a construct， and I was just wondering。

Does it matter that the actual like。Say S expressions are the same between like。

A compiled and executed version， I feel like an interpreted。Version， or is it just that me？Aor。Yes。

 seriously。Or exactly。It's hard for me to think of a situation where you would be okay with。

The expression， the subexpression associated with the error being different。Right like in general。

 the order of operations can matter right and so if we're going down the leftmost sub first in the interpreter。

 but the rightmost sub first in the compiler， like maybe we are still figuring out a way to actually have the compiler emit the code for the leftmost first is like maybe we figure out some way that's actually going to work for us。

 but it's really hard for me to imagine， in fact， a case where we would be cool with that。

No that makes sense because I it's like specifically something I'm like running into for the very of the homework。

 and I'm like wondering if I'm just kind of like。Getting away with it， because like。でしの。Its like。

sort of happens to work but what if we replaced our addition and multiplication with a weird addition and multiplication that also print stuff so that the programmer can see it right like is that okay？

Yeah， that's what I was thinking and that's just why。点就可以了。In general。

 we really want like we want as much parallelism between not parallelism， but parallel structure。

 parallel behavior。And we are going to see cases later where that really is going to matter。

 We're going to run into that in the context of building up the course compiler of whoop。

 we did it wrong。I really want them to match forgot。

If you construct a case where you can persuade yourself that it really doesn't matter。

 I'm actually super interested about that。I mean， I no pressure。

 right know that's like that's a brain teaser Yeah， yeah， no you think about it。

But you make a great point。Like that probably indicates that something deeper is wrong。Yeah。

So in general。That's what I was thinking， but I think just happy。僕给你 알て。Yeah。系即。別のビは。一しだい。36。会。这个多。

The時をを。저는 이제 누구 있어。They're seeing。キャして。chargeBTL。So like it's not。And the stop。

Actually I know it's kind。没当。I'll be actually created this。工能方面啊。やし。どて私は。Coor free。我下。I don't。

It didn't make sense。はいてはも。Alright， so going forward， when we add a new feature to our language。

 when we add it to the compiler， we're gonna make sure we also add it to our interpreter。

 And that's how we're going persuade ourselves that we are， in fact， correct。

 We are going to start practicing that immediately。 In fact， often。

 we're going to find out that we can figure out some of the ideas we're trying to work through as we design a new language by first implementing it in the interpreter and then figuring out how to do the same thing in the compiler。

 So often we will actually start by implementing it in our reference interpreter and then move on to compiler land。

😊，嗯。And so basically， for the rest of class， when we start talking about what it means for our compiler to be correct。

 we are going to mean that it does the same thing as our definition interpreter。

 so we want to be pretty sure about it。Okay， which brings me to our next topic extending the language the more。

 So we are about to add Booleans。 So we mentioned the topic earlier of what kinds of values are even available to us right now in the compiler and we decided that the only thing we actually have numbers That's all we've got so far right even when we're doing our addition our subtraction what's coming out the other side of those also numbers So numbers are the only values that our programs are working with and now we're going to go ahead and start adding in some other values。

 and so we're in particular going to add the new type of Booles。

 our programs are going to start being able to use Booles。

And I think probably some of the programs that we're going to be able to write once we have access to Booles will have answers that you can sort of predict pretty easily。

 so I hope everyone is looking at this and saying well that should be false and that should be true。

 but I want you to go ahead and discuss with someone nearby What about these two programs What should be the values associated with those。

我被道。可以。they call a cat。So there are a bunch of reasonable possible answers here right in Python zero is like false and other numbers are like one。

That's fine。In C， there aren't any booles， all we have is numbers， so not zero gives one。

 not one gives zero。It's just a design decision。 right， None of this is handed down from the gods。

 We get to decide what we want these programs to do。

We are building towards a language that looks a lot like listsp， a lot like scheme。

 you probably noticed that from the S expressions。 and so we're going to go ahead and adopt the same thing that scheme does。

 and in scheme， there is no such thing as a falsey value right the only thing that behaves like false is false。

That's it。And so again， this is just a design decision。

 There's nothing saying that there's one way to do this that is right or wrong。

 As long as the programmer understands what's happening， it's all good。

 And so we're going to go ahead and choose to do that。 We could have picked something else。

 but we're going do this just to match other lespy languages。嗯。

It is in the end 164 line going to look quite a bit like Lisp。 So if you have used it in the past。

 you might find that writing programs in our particular language that we're implementing might be a little bit easier。

And so we're going to make it look like schemes not。

 which is to say we are going to have this be false and this be false because everything that is not true。

I going to be sorry， everything that is not the Boolean value false is going to behave like true。

 And so if this is like true and this is like true。

 then this said better be false and this said better be false。So that's what we're going to do。

So far， so good。Okay， cool。 Now， there are some other things that are going to be a little bit wacky。

 So what would we like to have， I think， probably like0 applied to0。

 We're probably all guessing that should be true。What about nu？Applied to false。So。This is kind of。

Wacky， right， think about in Oak Camel。Go ahead and discuss， in fact with folks nearby。

 would it make sense to have an operator like Numb question mark in Ocael。

 what would we be applying it to， what would we be doing？All right， so hum。

 if you think it might make sense to have this an Ocal。H if you think not so much。Oh okay。

 some confusion。 Co。 Yeah， so I'm gonna go ahead and vote for this doesn't make sense in Ocael。

 So why does this not make sense， right， if we think about all the things we've been doing to persuade Ocael that what we've got in a particular program location is of a particular type。

 That's the reason right， we know at compile time that this value that we've got there at a particular location in our program text is going to have type。

 whatever， fill in the blank。 And so it doesn't make sense for us to have uncertainty about what type is represented by a particular thing。

 right， we will know that at compile time。 And so this。Is getting at the idea of。

 if you've ever heard the term statically typed language versus dynamically typed language。

 The language that we are implementing is a dynamically typed language。 So at runtime。

 we are going to be able to figure out what type we're dealing with。At compile time。

 we're not necessarily going to know， so let's bring back that image that we have of compile time versus runtime。

So here's our compile time versus runtime and we decided that this was compile time and this was runtime and this was runtime right So if we already know types。

At this star， right if we already know types at compile time， that is a statically typed language。

Like O Cam， right， we can be just looking at our program text。 we haven't run the program。

 Our editor can already， you know， we hover over a particular value and our editor can tell us what type that is。

 That is a statically typed programming language。On the other hand。

 if we can sort of look at a program and not necessarily know what type or thing is going to have。

 okay， dynamically type language， like the one that we're implementing。

And so having an operator like numb question mark makes sense if our language is dynamically typed like listsp like Sche does not make a lot of sense for something like O Camel。

 because we already know at compile time， why would we need to check at runtime？

So far so good on compile time versus runtime， static versus dynamic。

 statically typed versus dynamically typed。😊，Yes。😊，Yes， exactly。 So this this question was。

We are going to want something like numb that would check what type we have in the text of the program。

 We would only want to have that in the text of a program if we were writing a program in a dynamically typed language because otherwise we would already know it compile time。

 what type a particular you know if we're looking at a particular piece of the program text and we sort of circle something in that text we should already be able to figure out before we ever run the program what type that thing that we have circled has and so we would never need something that runs at runtime that checks what type it has because already know it's already baked into the program。

Whereas if we are in a dynamically typed language， that's not known at compile time， right In fact。

 often it cannot be known at compile time， there may be no way to find out in which case we might need to actually run something at runtime。

 right using a language construct that the programmer can actually use。

 we might need to run something at runtime that checks what type it has。I love this question。 Okay。

 so since we are implementing our language using O Camel。😊。

Are we ever going to use something like nu question mark in the course of writing our compiler our interpreter No。

 right like we have already seen that we can go ahead and do these things where we're saying this right like I'm hovering over this part of my compiler program and it's telling me what type it has。

 So we as the compiler and interpreter writers will never write something like nu question mark。

 However， the programmers using our language that we are creating for them， right。

 they may want to write numb question mark。😡，And so we will in fact。

 be implementing a numb question mark operation that they get to use in order to check the types of the things in these programs that we are then compiling。

Got it。Amazing question yes so this question is we will check types using the assembly code that is omted by the compiler Yes exactly right so if it is happening at compile time。

 that is something that is being executed using our Ocal program something that we will have written to do this in our sort of Ocal language program that we're writing whereas if it's something that's gonna to happen at runtime。

 that means that we have emitted assembly that is going to be able to do it and so this is an example of something where we are going to be emitting assembly that is going to be able to do it。

😡，So price are good。Yeah， we're really having to navigate that compiler interpreter， compile time。

 runtime， and all these various sort of mixed up ideas today。Okay， cool。

 So I think we have at least enough time to start putting this in our interpreter。 So let's go ahead。

And try that。Great， let's swap back to。Our interpreter。So here we are in interpreter land we have。

So far， only integers。 so we could go ahead and do something like。Sim。True maps to。One。

 but we decided we're not going to do that， right， We really do want to have only false。

 only the Boolean value false actually behave like false。

 which means we're going to have to have something that actually represents that value。

 So I'm thinking we probably don't want this to be an int anymore。

I want you to discuss with folks nearby。 what do we want it to be， discuss for half a minute。

I'll give you a hint， what's a trick we've pulled before。All right。

 I heard people mentioning this in the past。We might have wanted to create a new type。

That sounds good to me。 Let's do the same thing again。 Let's have a new type value。

 We can have multiple constructors for it， number of int or boolean of bo that looks okay to me。

 that seems like something that we might like to have as our return value here in the context of our interpreter。

😊，So now we're going to go ahead and just represent those explicitly。 What do we want to do here。

 Well， probably that's pretty clear just from the fact that we know that's going to be a number。

 so let's go ahead。And write number N。 Okay， but now this is a little bit weird， right。

 because it kind of looks as though we've got something coming in and the exact same thing coming out。

 right， we've got this numb N thing。 Then we're turning in number n thing， No， different， right。

 Because remember that nu N has type S expression， right， just like our program that comes in。

 type S expression， whereas this on the right hand has type value。

So we're taking in things that have type S expression and we're putting out things that have type value。

So okay， that's looking good so far。 We haven't actually implemented bullole that Let's take care of our numbers first。

 So what do we want to have here， Well， we're probably gonna do something that looks relatively similar to this。

 But where exactly do we put that number constructor， Go ahead and discuss for 20 seconds。😊。

How we will fix this line。All right， so first， let's yell out what type will inter X applied to Arg have？

Hint， hint。We can go ahead and just read that off our program。

 our program says that if we make a call to Inter X。

 the thing we're going to get back is going to have type value。So what do we do if it has type value。

 can we just immediately add one to it？Yeah， all right。

 So probably let's do the thing we've been doing where we check if this is the kind of thing to which we can add one。

 So let's go ahead and do。Match Inter X A。With， in fact， let's。

Go ahead and give this expression a name just so we can actually refer to it later。 So as E。

 let's go ahead and pop this all inside。Here， so when do we want to go ahead and do this？ Well。

 if we know that this is， in fact， a number， then we are good to do something pretty close to this。

 right， So if it is a number。Great， we can go ahead and actually do our addition in that situation。

 We're going to have to actually apply it to N rather than to this whole call， right。

 So let's do number。😊，Applied to n plus1。 that feels good。What if it's anything other than number？

Yeah， we don't know what to actually do in that situation， so let's go ahead and say。Lookops。Raise。

That expression， E， so that's why we bother to actually go ahead and name it as E。So okay。

 I want you to real quick， oh sorry， question。Are you able to do the matching on the number type in the first expression？

Oh， I think I understand the question。 Okay， so if we were up here。

 could we already do the match on the number type here， Great question。 So what type does AG have？

Right， Arg is an S expression。 So if we evaluate add1 n。

 we're gonna to get back a value that will be created with the constructor number。

 but our S expression is simply going to have something that looks like LST add1 R right。

 So we do need to actually use interpret X in order to get back the value associated with that expression before we can go ahead and do the match with number because it's not immediately obvious looking at something like add1 add1 add1 n right Like we could look at that and no。

 okay， well， that's gonna be a number right， But in order to actually figure that out。

 the interpreter is going have to actually evaluate it and say， okay， yeah。

 the value I got back was indeed a number。Okay， cool。 discuss real quick。 Do we have time for this。

 Okay， we don't have time to actually fully finished since I'm so sorry。

 I keep trying to catch this back up， but what we're gonna do is at the beginning of next class session。

 we're going to go ahead and real quick wrap up adding our new value type inside the interpreter and then we'll get to add Booles inside become compile pilot。

😊，I thought we were going to catch up。I thought we were gonna I just have a question about Yeah I read a lot of languages are like the compile written in that language works I know right Yeah how do we first do it Yeah where's like the base case like like I' know Yeah so if you remember that very first session when we talked about how rust for the first compiler for Ru was written in Ocal and then they had after that point a working implementation of Ru So at that point they then switched to writing the rust compiler and rust。

Now the very first compiler where we get that right so the very first compiler had to be written in something that could be run directly on the processor right so you had to write that in the ones and zeros because the output is like machine code you used to use that like actual machine code。

In the future to run Oh okay Well and then you get a new right。

 like once you have the rust implementation of rust now you can actually run that in order to get a new implementation of rust and now you can run that one。

You know what I mean， see like we just keep going okay。

 its called bootstrapping if you want to look it up morerap？Iify something about this absolutely one。

 but maybe one of these ones。Yeah， this one right here right so yeah is this top section the compiler or is the compiler of the entire thing so the purple section is the compile time process。



![](img/a731a27b73cf71306fa9d09a4da0c5a8_20.png)