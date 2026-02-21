# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p16 -16- L13_ Precise Exceptions (Spring 2025).zh_en -BV1iV1XBWEJW_p16-

![](img/93c341352f9e2a7f235d712166f3478d_0.png)

Okay， so let's start， so just to give you an idea， do we have a pointer？



![](img/93c341352f9e2a7f235d712166f3478d_2.png)

Yeah， maybe you can bring it。Okay， just to give you an idea。

 we covered my architecture fundamentals before Easter last week is Easter of course。

 and then we covered pipelinelining and then we covered a lot of issues in pipeline processor design。

 data forwarding， bypassing control dependence prediction。

 basically control and data dependence handling， including fine grain multi threading。

 the people remember all of this。Hopefully it's good yeah。

 so many many issues in pipelineing so basically pipelining instruction execution introduces a lot of issues as you have seen and we've tackled some of those issues we're going to tackle more of those issues actually soon。

😊，To date， precise exceptions， how do you maintain state。

 how do you recover state that's going to be important。

 especially when you're pipelining instructions and doing multicycle execution as we will see and hopefully today later today we will start with out of board execution which is dynamic instruction scheduling。

😊，And then I don't know if he will cover load store handling。

 which is the most hairy part of a microproster design today。

 but maybe I'll give you an additional lecture just for your information we'll see readings we still continuing you've seen these readings how many people have read the Smith and Soie paper。

😊。

![](img/93c341352f9e2a7f235d712166f3478d_4.png)

Anybody don't be sure。 okay， I see has some hands。 That's great。 Do you like it。😊。

Is it good also okay yeah this is an introduction to superscalear process your books don't do a great job unfortunately in this it's a bit sad that books don't cover it in enough detail Okay anyway we'll cover it in more detail so remember this is where can people hear me in the back I hear an echo quote。

😊，Is it only me， it's all good。 Okay， if it's all good， no problem and it's all good online。

 it's also no problem。 So this is where Muhammad kind of started。

 but he didn't finish because he didn't have time。 We're going to talk about preserving sequential semantics and Woknowman architectures especially。

😊，And this is a slide that Muhammamed mentioned， but basically imagine a system where not all instructions take the same amount of time in the execute stage of the pipeline。

 this is possible because you can have multiple different functional units that you send the instruction to one instruction goes to an adder another instruction goes to a multiplier another instruction goes to a load unit for example。

 and your pipeline or at least the backend of the pipeline after an instructions is decoed it may look like this so this we're going to see machines like this。

 all of the machines are like this today basically some instruction may take only one cycle。

 some other instructions may take four cycles， some other instructions may take eight cycle。

 some other instructions may take hundreds of cycles let's say in the execution。😊。

And the functional units may be pipeline or not pipeline。

 so basically all of the principles that we discussed can apply to the execution and it also pipelineing。

😡，呃。Now if you actually have a system like this， you can let independent instruction start execution on a different functioning it before a previous long latency instruction finishes execution。

 for example， you fetch an instruction， you decode it。

 it happens to be a multiply and this multiply is going through the multiply pipeline and then you fetch an instruction another instruction and decod it。

 it happens to be an a instruction and this a instruction is independent of the multiply pipelining says that you should be able to continue execution of this a instruction which is independent and you send it to this functioning it。

 but then this a instruction finishes quickly whereas the multiply is still continuing。😊。



![](img/93c341352f9e2a7f235d712166f3478d_6.png)

![](img/93c341352f9e2a7f235d712166f3478d_7.png)

Now we have a problem， right， multiply takes four cycles， it's older， a instruction takes one cycle。

 it's younger。😡，What do you do if the item instruction finishes。

 do you write its result to the register file？😡，Now that was the question Muhammad asked last time and that's the question over here basically。

 how do you arbitrate the writing of the results to the register file so that you actually preserve the semantics of the Woon Neumman model。

 which is really sequential instruction processing， right？😡。

So based on what we've discussed with the one Neman model。

 you should not let a younger instruction write its results into the register file or memory because otherwise you' would be breaking the sequential instruction semantics and that's absolutely true in fact this becomes even more problematic with what we're going to discuss which is exceptions and it interrupts because it makes these out of order writing of the results visible to the programmer if you do the wrong thing if you break the sequential semantics reason。

😡，So let's take a look at this example that we covered briefly last time。

 essentially instructions can take a different number of cycles in this execute stage， for example。

 we see the difference between an integer a which is one cycle and the execute stage and integer divide which is eight cycles I just want to amplify this in existing clusters a divide can take 40 cycles。

 maybe 50 cycles， an a can take one or two or three or four cycles， basically at high frequencies。😊。

Now if you look at this picture this picture shows the execution of instructions。

 you fetch thecode and then you dispatch and we're assuming all of the instructions are independent of each other over here。

 that's why you have a nice pipeline that's filled。

 but some instructions take eight cycles in the execute units divide for example。

 and the next a instruction takes only one cycle and writes this result。😊。

Into the register file happily next instruction also writes as the result in the register file。

 next instruction also writes in the result of the register file in consecutive cycles。

 but this poor instruction has not written its result into the register file yet。😡。

So if you remember， well last lecture to your mom had asked you the question。

 what is wrong with this picture of one known in architecture， essentially this is what's wrong。

 this right？😡，Viols the sequential operation semantics right because this instruction has written its result into the register file before a prior instruction has completed that's true for this instruction as well。

 this instruction as well and this instruction as well and this instruction as well all of these instructions violated the sequential instruction semantics we should not have written their results into the register file basically。

😊，Makes sense， right？O。So that's a legalistic answer as you all right this is a contract between the hardware and the software and the programmer assumes that these instructions should not write their results into the register file before a prior instruction is complete now that's what we you'd expect but then you should always ask the next question is why does it make sense why do we have this legal let's say contract if you will between the hardware and the software and that's basically going to be because of precise the notion of exceptions let's take a look at that basically。

😡，The problem really happens if this divide。Is not supposed to finish。Or has some problem， let's say。

 and one problem with divides could be the。You could be dividing a number by zero， right？😡。

And if you divide a number by zero， what do you get？😡，For those of you， math gu out year。Anybody。

You get an undefined value or not a number， basically right。

 you should not divide by zero essentially。😡，That's called an exception。Basically。

 there's an exceptional condition that the instruction produces and it may happen that the value that you're dividing by zero。

 and if you actually have this sort of problem， the program should not continue。

 the program should exit with an error。Or the programmer figures out that there's a divide by zero and does something else with the program。

 the programmer can catch this exception actually， there are mechanisms that you can actually add to the program where the programmer attaches that you're dividing by zero and does something else because it fixes up the value。

 for example。😡，If you're programming actually you will may know this how many people you have used try catch blocks or catching exceptions and programs okay there you go now you know what this is about basically you can actually you could catch exceptions to the higher level。

 but they get translated to these lower level exception catching mechanisms。😊，So basically。

 if you have an exception like how many of you people have caught the divideoid by zero exception。

 okay， some of you and you would like to catch that， right？😡，Yes。

 you don't want the program to continue。But when you catch that。

 you don't want the later instructions to have written their values into the register file because otherwise you'll have to be dealing with a mess。

😡，Because something has completely out of order， right？When you catch that。

 you really need to know what your state is in the program so that you can recover back and do something better with the program essentially。

😡，Okay， so that's basically the reason of that that's that's one of the major reasons why we want precise exceptions so okay。

 I mean Muhammad， I think showed you pictures of the analogy that I used last year when I was actually teaching this course basically I see this term as an exception causing instruction。

😊。

![](img/93c341352f9e2a7f235d712166f3478d_9.png)

That's had some failure essentially and you can see that that's tram 11 I think well maybe not here and then there's another tram that's delayed because this exception needs to be handled for this tram to continue and this second tram may have nothing to do with the first tram basically right and then there are other cars that are delayed as you can see that because of this exception causing instructionss and you can see that that's tram 11 and the other tram is delayed in the back and then you can see that this is still going on。

 I'm walking as you can see。😊。

![](img/93c341352f9e2a7f235d712166f3478d_11.png)

And it's still going on。 And then， finally。The instruction is resolved and exception is handled and then the instruction can continue I don't know if this was the exception causing instruction this may need to be relabeled but basically you can see that because one instruction or one tram caused a problem another tram in the back could not move right and this is an exceptional condition I'm going to use this to motivate something else later on but here I'm motivating an exceptional condition maybe not be the perfect analogy but it's really an exceptional condition maybe the tram at a power failure maybe one of the door was not operating right that was a problem with that particular tram and the later instruction could not move on okay so the analogy holds in the sense that exceptions or interrupts are actually unplanned changes or interruptions and program execution。

So for the trim it was an unplanned weight over there at the station。

 that it could have been somewhere else also， but in programs this also happens basically。

 and there could be two major reasons。😡，This could be due to some internal problems in the execution of a program。

😡，Essentially this called an exception divide by zero is internal to the program right this divide instruction is part of the program and it's got a divide by zero error。

 it just happened that you're dividing by zero。😡，But it could also be external。

 completely external events that need to be handled by the processor， these are called interrupttros。

😡，These are fundamentally very different， although in a Woknowman architecture today the handling of them are very similar。

 but I want to make sure that you understand the fundamental difference because these are really different concepts in the end。

 because handling of them may be different in different architectures that's the reason why it's good to understand that these are different so external event could be for example a power failure you have a power well in the tra the example doesn't work but in the machine over here you're exitating a program and then you have a power failure because your battery ran out that's an external event to the program。

😡，That has nothing to do with the program that you have written as a programmer。😡。

And you cannot really deal with it， right as a programmer。

 because it's completely external while your program is running。😡。

But the machine has to deal with it， because if a program is running while the power failure is coming。

 then that program should not。😡，Continue but should go into a state where it could be continued later after the power failure is handled in some ways。

 so that's the example of an interrupt another example of an interrupt is a network packet。

 for example， coming from an ethernet controller or the wireless controller and you need to handle that network packet processing somehow that's an external event coming。

😡，And if your program is completely independent of that network packet。

 that has nothing to do with your program， clearly， right？😡。

But your machine need to be interrupted to process that packet in some way so that you can actually make progress in the entire system。

 right？So that's the difference between exception and interrupts and these are actually going to we' were going to go into a little bit more detail in terms of how they are different but both of them in the end require。

😊，Stopping of the current program。😡，At some point， as we will see they are different in exceptions of interrupts and also types of exception interrupts。

 but when you get to divide by zero for example you've got to stop the program right away。

 so exceptions are actually very critical， you need to immediately stop the program almost。😡。

And then you need to save the architectural state somewhere to make sure that you have not lost any data in the program。

😡，And then you need to transfer the state or switch to some other control。

 this called handling the exception or interrupt， you have a special interrupt or exception handler that handles the interrupt。

 for example， you can have an exception handler that's written by the programmer handle divided by you。

 you can have an exception handler that's written by the system designer handle。

 potential power failure， battery running out。😡，Another interruptop handler for packet processing。

 for example， a packet has arrived or somebody pressed the keyboard。

 how do I handle that so that's a keyboard interrupt handler for example。😡，So there are many。

 many interrupt handlers that you need to do， and then if possible and make sense。

 you return back to the program execution。😡，This may or may not be possible clearly right。

 but this is something we try to do if the program is reable or continual depending on the nature of the exception or the interrupt。

Does this make sense？So basically， this is how we handle exception interrupts in a one known architecture。

 but interrupts fundamentally can be handled slightly differently and we may discuss that later on。

 for example， if remember， we discussed the notion of data flow in the past data flow。😊。

Really doesn't have the notion of an interruption， if you will。

 it's everything is a data flow graph and you need to make sure that interrupts are actually handled like a data flow graph as well。

😊，Okay， maybe I don't want to go into that right now Okay so let's let's take a look at examples I'm giving you some examples but exceptions are internal to the program it could be divide by zero。

 it could be a value has overflowed such that it cannot be represented by the number of bits allocated to a register for example it could be an undefined upcode basically the machine fetches a binary value that's not an upcode and it tried to decode it and。

😊，It gives up。That could happen if someone has ever written a wrong program。

 let's say it could be some access protection or general protection exception this may happen when a program is trying to access a memory location that it doesn't have permissions to access it's actually very useful to implement these exceptions so that you implement some basic security primitives in your system and we're going talk about that when we talk about virtual memory but hold on to that because we have not been talking about memory a whole lot so far in lecture 25 or 26 you will see that it could be a page fault and again well see that when we talk about virtual memory page fault is actually when you're trying to access a memory location that's not inside the physical memory。

😊。

![](img/93c341352f9e2a7f235d712166f3478d_13.png)

![](img/93c341352f9e2a7f235d712166f3478d_14.png)

Again， this is intrinsic to the program， a load or store instruction may trigger this page fault。

 but it's not in your physical memory and we will see why it may not be in your physical memory when we talk about virtual memory。

 so hold off on that， but it could be on disk and then there needs to be a page fault exception that's handled by the operating system and the operating system brings the page or the data that you need from the disk into the physical memory to make sure that your program actually works。

😡，So we have not talked about that so if you're not understood anything related to the page faults that's fine。

 we'll cover general protection and page faults later on so you can see that these exceptions can be internal to the program。

 some of them can be extremely bad like potentially divide by zero you get a zero value divided by it you didn't anticipate it and you don't have a handler for it to fix it then the program basically needs to be halted stopped right。

😡。

![](img/93c341352f9e2a7f235d712166f3478d_16.png)

![](img/93c341352f9e2a7f235d712166f3478d_17.png)

But page fault is actually useful because that enables you to use memory that is bigger than your physical memory。

 and that enables larger programs essentially。😡，Okay， these are， as you can see。

 all internal to the program related to the program。😡，But interrupts are completely unrelated。

 for example， an IO device， a keyboard， as I mentioned earlier。

 or a camera need service may need some service and it basically sends a signal saying that I want。😡。

Some interrupt Tr to be executed so that you can take my video feed right or whatever network right it could be more periodic system timer for example。

 periodically operating system may have a timer that basically interrupts the processor and does some maintenance tasks。

😡，It could be power failure this is clearly quite high priority and then it could be a machine check it's called machine check but there could be some error inside the system this gets detected and you normally don't want to move the system forward if there's an error that gets detected you want to handle that error and that's why it's called a machine check check the machine basically to make sure that theres nothing wrong in the data values etc ceter right so these are just examples and you can come up with many。

 many others。😊，So is this distinction clear， exceptions were syn jobss， Okay， great now。

Basically the main distinction comes from the cause。

 exceptions are internal to the running thread and interrupts are external as a result this determines when they are handled as well。

 for example exceptions are usually handled when they're detected and known to be non speculative so non speculative means the instructions that actually supposed to execute because we have some speculative instructions that are not supposed to execute yet right。

😡，Because we're doing branch prediction。 remember， the control prediction that we discussed in the pipeline processor。

 we're going to do more of that in a couple of lectures。

 So you need to make sure that you really need to handle that exception。

 it's a true exception and also usually you need to handle it right away。😊。

Inraps on the other end can be handled by convenience， meaning somebody。

 some network package is coming， for example， you don't have to immediately handle that。

 you can buffer it for some time and then handle that after some point。

 so there could be some interrupt handlingling latency。

 so it really depends on the nature of the interrupt。😡。

Except for very high priority ones like machine check or power failure that usually need to be handled immediately because if you don't handle the power failure right away。

 you may actually lose some data right because our program there's at least one program let's assume that there's at least one program is executing in your processor and your battery is about to fail and you get the signal from your battery saying that。

😡，I'm going to lose power， you'd better saveve some of the state of the program so that you can actually restart the program later on when actually power comes up if you don't handle at a very high priority you may lose that opportunity to save the state basically。

😡，Okay， so and then the priority of the interrupt versus the exception is different because the clause is different。

 so the priority of the exception is essentially the same as the priority of the process because it's really internal to the process on the other end the priority of the interrupt really depends as I just mentioned right。

😊，Power failure is very high priority。 It maybe it's actually perhaps the most。

 it' perhaps the highest priority thing in the system。

 It doesn't matter who's running what I got to handle this power failure， right。😡。

As opposed to a network packet received， well， maybe it's not that important right。

 because there are other mechanisms that are also handled in the network。

 maybe somebody is going to retransmit that packet right if you actually especially if the higher level protocols cover for that packet loss if you actually lose a packet in the end ideal you don't want to lose a packet。

 but this also shows that this's not that critical there are other ways of handling a potential packet loss if you cannot deal with it for whatever reason。

 because the machine maybe overload it。😡，Okay and then the handling context。

 I'm not going to talk about this well maybe I'll talk about。

 but basically exception is handled in the context of the process。

 that's why as a programmer you can try and catch an exception and fix the exception。

 handling exceptional situation， whereas the handling context of the interrupt is a system because it has nothing to do with the process in general。

 so interrupt are actually handled mostly by the operating system whereas the exception handlers can be written by the programmers。

😡，Although there are vanilla exception handlers that are provided to the programmers。

 if the programmer doesn't supply their own exception handler in exceptional conditions。Okay。

 so I think I've made this clear。So okay， what does precise exceptions or interrupts mean so for the purposes or the rest of this lecture I'm going to keep exceptional interrupts very similar because they're handled similarly in a Wonoy architecture。

 maybe if you have time， we can discuss the differences at the end。😡。

But what does it mean for them to be precise this basically means that you should obey the vneman model sequential semantics that we have learned several lectures ago。

 essentially the architectural state which consists of program counter memory and registers should be consistent or precise when the exception and interrupt is ready to be handled so what does that mean this means because of the sequential instruction semantics。

 you have an exception causing instruction。😊，All previously previous instructions in the program order should be completely finished。

 retired， that's also called retired。😡，Meaning they should have updated the architectural state completely。

😡，And no later instruction should be retired， meaning should have updated the architectural state so you should really have a clean slate between the exception causing instructions and later instructions if you will so retired commit just to define it。

 you finish execution and update the architectural state that's the definition some people also called graduate I don't like graduate that much but and mostly retired and commit is used。

 so let's take a look at this example， you a bunch of instructions if you want to look at the precise state if this divide for example。

 if you want to look at the precise state if this divide is supposed to cause an exception。

 there should be a precise state over here or if this a basically you could draw this precise state between every instruction this means that all instructions before the divide have finished and no instructions after the divide have finished。

😊，And then the divide can be handled the exception that the divide can be handled So why is this useful because a programmer now can make sense out of the program right if this divide calls an exception the programmer knows that R3 is not updated with this ad R two is not updated with this divide R7 is not updated with this ad basically nothing after this divide has finished and everything before this divide has updated the state so they can actually reason about what。

😡，Happened and how this potentially can be fixed。😡，Okay。Yeah have questions feel free to interrupt。

 that's an interrupt basically right。If I have a problem， then I will take an exception， so I mean。

 this is my exception， for example， I handle my exception because my mom tells me that I need to drink some water。



![](img/93c341352f9e2a7f235d712166f3478d_19.png)

Could be called the dry mouth exception。

![](img/93c341352f9e2a7f235d712166f3478d_21.png)

But your interruption could be I don't know a shouting student exception right shouting student interrupt right okay okay so basically how do we check for we're going to so in the end you should check for and handling exceptions in pipelineing how do we check for and handle that in the end there are multiple steps we follow right when the oldest instruction is ready to be retired and is detected to have cause and exception the control logic needs to take some actions。

😊，So what is this action， first of all， it needs to ensure that architectural state is precise。

 like we defined earlier。😡，Register file PC and memory， remember。

 architectural state is always like that。😡，You need to ensure that all younger instructions are flushed from the pipeline。

 remember， we have a pipeline。😡，We have the oldest instruction that calls an exception because you need to check the oldest instruction because all of the younger instructions are speculative。

😡，So we have not defined this very well so i'm going to talk about this quickly。

 so if you have a pipeline the oldest instruction that's ready to write to the register file is the only one that is guaranteed to execute all of the younger instructions are specd because the oldest instruction may cause an exception right？

😡，So you should make sure that the oldest instruction is the one that's to be checked for retirement。

 and if it caused a problem， meaning if it's going to have an exception，😡。

Or if there's an interrupt that you need to handle at that point in time。

 you ensure that the architectural state is precise and you flush all the younger instructions in the pipeline so that they do not update the architectural state。

😡，Flush means we've seen the pipeline flush， you actually invalidgate the registers right。

 pipeline registers as we discussed。And then you need to save the PC and the registers as specified by the ISA。

 so the instruction that architecture needs to specify how to handle an exception or in。😡。

Because this is really necessary for someone to write software right either system software or regular software。

 so there needs to be some support in the controller。

 the control logic takes the program counter and the registers and saves them to some place specified by the ISA usually it's part of the main memory stack as we will see briefly。

😡，And then the control logic redirects the fetch engine to the appropriate exception or interrupttent linguity。

😡，Now what does this mean basically， let's say you have a divide by zero exception。

 this control logic called the exception because it saw that there was a zero， you're dividing by。

 and then it basically completes all of these three steps and then basically redirects the PC sets the program counter to an exception handling routine。

😡，And that exception handling routine can be a specialized routine for a divide by zero。

 or it could be a general routine， basically you you always switch to a particular location that's usually in the system code and that you start executing that system code and then there needs to be some place where you check what kind of exception am I dealing with。

😡，Okay， there are multiple approaches to this which I'm not going to go into that goes into more detail than needed。

 if you will， but there are different kind of interrupter exception handling architectures also。

 whether you go to a general purpose routine and then check the cost or whether you immediately go to a specialized routine。

 there are trade offs， but we're not going to go into that。😡。

Does that make sense okay so as I said interrupts and exceptions need to be defined in the ISA these are part of the ISa they have to be implant by the my architecture and this is actually a very beautiful definition description from Intel's X8664 ISA manual these ISA manuals actually very beautiful books in my opinion sometimes they' are very hard to read but sometimes they're beautiful like this let's take a look at one example part over here I'm actually going to read it。

😊，Because these folks actually are very good at distinguishing between interrupts and exceptions nicely。

 not all ISAs do， unfortunately， but let's take a look and also they describe it nicely when an interrupt is received or an exception is detected。

 the currently running procedure or task is suspended while the processor executes an interrupt or exception handler。

😊，When execution of the handler is complete， the processor resumes execution of the interrupted procedure or task。

 the resumption of the interrupted procedure or task happens without loss of program continuity unless recovery from an exception was not possible or an interrupt caused the currently running program to be terminated。

😡，So it's not always possible to get back to the program basically。

 for various reasons that are not detailed， but you can guess what they are。😡，Okay。

So let's go back into this， why do we want precise exceptions a little bit before we start adding more complexity to our machines？

So as we discussed earlier， one of the reasons is legalistic semantics of the one Ne model I say specifiedifies it so you need to obey that right and that's absolutely true。

😊，But this's kind of a cop out answer in a sense， then the next question becomes， of course。

 why does thenoy and I say？Sp right， because it's easy for the programmer basically because that's the answer。

😊，Why then then the next question is why is it easy for the program and then we're going to answer that in the next bullets if you will but let me mention that one Ne model specifies precise exceptions but data flow model doesn't specify any such thing right because in data flow model there is no ordering of instructions anyway exception still happen you may have a divide node remember the nodes in data flow these bubbles you may have a divide by zero and exception happens。

😊，Then how does the programmer debug that thing？it's a huge data flow graph。

 you don't know what is executed and what is not executed。Right。

 and this is exactly the reason sequential semantics has been very successful。

 whereas data flow at the。😊，ISA level visible to the programmer has not been successful because when you get an exception。

 for example， it's very difficult to in a data full machine， the programmer。

 it's very difficult for the programmer to delineate a state basically。

 whereas precise one Neman is very easy。😡，So that's the reason actually of the next few bullets。

 if you will also basically this ate software debugging because you know exactly which instruction finished and which instruction did not finish and there's a clean state sequential execution。

😡。

![](img/93c341352f9e2a7f235d712166f3478d_23.png)

![](img/93c341352f9e2a7f235d712166f3478d_24.png)

So when an exception happens， you can basically go and debug it very easily。😡。

Well now imagine in contrast， we did not have precise exceptions if we go back to this， where is it？

😡，If he did not have precise exceptions then we I should have gone in a faster way okay there you go these instructions have written when this divide instruction generated divide by zero exception。

 these instructions may have written their values， some other instructions may have written their values now if that's the case the program has no idea right。

😊，There's no contract if you will。😡，The programmer。Needs to somehow figure out what has happened。

 They need to reconstruct how the machine has executed the program。

 and this is not this is what we don't want programmers to deal with。😡。

The programmer should not worry about what instructions executed in the machine and what instruction did not finish and what instruction updated the register file and what the instruction did not update the register file that's why we have this precise exception semantics that saysPror you don't need to worry about what the machine did I'm going to guarantee you that this instruction that called the exception after after this instruction no instruction is finished and all of the instructions prior to this instruction have finished so that's the reason for the sequential execution semantics actually and that's perhaps the major reason。

😡，For most major reason， let's say。Okay， so it ate software debugging， basically。😡。

Now can you debug it without this， of course you can。😡。

But you'll pull your hair hair out probably for days and days， basically it'll be hard。

You can do anything in the end as long as you know what's happening because this is a deterministic system in the end you can reconstruct what has happened。

 but it's extremely costly and expensive。In fact， one of the processors。

 IBM built Out of order execution， IBM's early Out of order processor。

 we're going to talk about that in the next lecture or maybe later part of this lecture。😊。

They basically chose not to have precise exceptions， they basically said。

We're not going to support precise exceptions to our machines and that machine did not get used much essentially that was a very bad business decision in the end。

 it was a beautiful machine but didn't support software divbugging easily。😡，Okay。

 so there are other reasons why you want precise exceptions。

 you can enable easy recovery from exceptions as we discussed。

 you can easily say flush all of the instructions in the pipeline。

 they're not important because you're not you have a precise state right and then you can come back to the program counter。

 you don't need to fix up any state base。😡，I'm going through this relatively quickly because there are actually other details that I don't want to discuss necessarily。

 you can restart the process relatively easily basically you know exactly where to start the process。

 right？😊，This program counter calls the exception， and if I restart at the same point。

 I'm going to execute this instruction， the next instruction and the next instruction。

 next instruction， and I'm guaranteed that none of them already executed right if some of them actually have executed had executed。

 then you have to deal with that somehow it's a mess。😡。

But now you're guaranteed that none of the later instruction are executed。

 so you can actually start restart the process at the program counter that is called the problem。😡。

Or that you kickeded out of the machine， let's say， at that point in time。

And also there are other benefits。 this is actually very similar to debugging in a sense。

 but for example， you may have an unimed upcode or software implement up code。

 You didn't implement this。😡，And let me give you an example， for example。

 you don't assume that you don't have a multiplication instruction in your ISA。😡。

Which may happen initially MIPS didn't have it and you say that I'm not going to implement multiplication。

 but I'm going to in hardware， but I'm going to have an instruction。😡。

And this instruction will be executed by the software。

 what does that mean when whenever I see a multiply instruction， I'm going to generate an exception。

😡，And this exception is going to take me to an exception handler that's going to do exactly multiply using add shift shift an add basically and then you're going to return from the exception and get the value that's perfectly possible that's actually done with complicated instructions multiply of course is present here but for example。

 you may have a floating point operation that you don't want to implement in hardware because hardware is costly you basically whenever you see a floating point operation that calls an exception。

 you go into an exception handler that executes a floating point operation using the integer operations it's lots of instructions。

 but you can do it。😡，So basically this way you can actually implement some instructions that are actually not inside the hardware and again。

 with precise exceptions， you can do that with imprecise exceptions。

 it's very difficult to do because you're not guaranteed what you don't know what's executed and what's not executed。

😡，O。Any questions？Okay， I've motivated a lot， but I think this is really important because this goes to the core of the hardware software interface also。

 so we kind of pulled back from the we were looking a lot into my Arch sector。

 exceptions and interrupts actually pull us back to the hardware software interface。😡。

Exception interrupts are actually going to be a lot more important。

 especially for cyber physical systems， like these systems are not that cyber physical。

 but if you actually have things like I don't know the drones for example。

 or brain machine interfaces they're all cyber physical it's all about interrupts from the outside so a lot of the pressing that you do is actually based on what's coming from the outside so handling these interrupts actually is going to be more important and there will be a lot of exceptional conditions also。

😊，Okay， so now the question is basically this is a good thing， we want precise exceptions。

 how do we ensure it， how do we make sure this works in different types of machines so we're going to take a look at single cycle multicycle relatively quickly and then we're going to talk more about pipeline。

😊，So in a single cycle machine， instruction boundary is the same as cycle boundaries so the problem doesn't exist if you want。

😡，An instruction is guaranteed to be finished in one cycle。

 so there's no possibility of violating sequential execution semantics。

Because one instruction is finished， the other instruction doesn't get started before the previous instruction finished。

 so there's no problem here。😡，In a multi machine。It's not that big of a problem。

 but we need to do something special basically， how do we actually go to the interrupter exception handler？

😡，So you need to add special states in the finite state machine。

 remember the finite state machine that specifies the behavior of the multi cycle program。😊。

You need to add a special state， well multiple special states to the control finite state machine that lead to the exception interends。

 I'm going to show you some pictures， but your book actually covers this nicely。

 let's say it doesn't cover what's really interesting， which I'm going to cover later on。

 but basically your book has a nice treatment of exceptions in a multicycle architecture。😊。

But it can be used for interrupts also。😡，Basically you switch to the handler only at a precise date。

 what does that mean before fetching the next instruction once you finish the previous instruction check for the interrupt check for the exception or interrupt and if there's an exception or interrupt go to a special state。

 which is the exception handling routine we're going to take a look at that。😡。

So this is actually what' how your book modifies the multie data path that we studied。😊。

Basically you have you need to add some special data pass components like EPC register your book ads。

 which holds the exception causing PC this is the program counter that caused the exception remember the divide instruction potentially cause register is holds the cause of the exception I think in this particular case there are two possible causes one is overflow in the ALU basically the value that's generated as an AL result cannot be represented with the number of bits that are in the word。

😊。

![](img/93c341352f9e2a7f235d712166f3478d_26.png)

![](img/93c341352f9e2a7f235d712166f3478d_27.png)

And then there should be another exception over here。

 I think it's an undefined up code exception which is not visible over here as far as I can see。

 but you will see it in the next slide。😊，So basically there's a cause register and then there's an exception handler that starts at address this address and the system so this is a general purpose exception handler so what happens is when an exception happens the cause is set。

😊，And the exception causing PC is set record an EPC and then the is machine jumps to the exception handler and this exception handler later checks what kind of exception is it by querying this EPC sorry。

 this cause register。Okay， does that make sense？So you need to modify the finite state machine。

 if you recall several lectures behind， this was the finite state machine that we constructed。

 actually， most of this we constructed for a multicycle MIPS architecture from your book。😊。

But basically， that finite state machine that we constructed is now modified to support two exceptions。

 overflow and undedefined instruction。Now let's take a look at the undefined instruction。

 so this is the fetch state， if you remember， you go into the decode state and then there's some control signals clearly。

😊，If the up code is others， meaning it's not defined。

 it's not any of those things that you're supporting， then you go into a special state。😡。

The state state 12 is called undefined。And the special state does something interesting。

 basically it sets the PC right signal， it sets to interrupt code to one。

 meaning it's an undefined instruction interrupt， well， exception。

It sets the cause right to one and EPC right to one what does that mean basically cause right as you're writing the exception cause and then EPC write as you're causing you're writing the program exception EPC register with the program counter that actually is pointing to the undefined instruction right and then PC sources11 and that means that if you look at this data path modification you jump to the exception handle so after the state。

The next program counter is the exception handling。

 so you've jumped to some location in the program that's actually dedicated to the system and system is going to execute the exception handling and it's going to check what kind of exception happens at this point。

 it has no clue， but。😡，The exception is recorded in this calls register。😡，So。As a result。

 MIPS architecture adds a special instruction MFC0， it's a terrible name。

You can read the book to figure out what that is， but it's I think。诶。

Androller zero co processoror zero， I forgot these two other ones， something from coprocessor zero。

 it's a messy name basically， but basically copy it's used to copy the exception cause into a general purpose register。

Basically what it does is this special instruction takes this course and copies it into a general purpose register。

 I'm going to show the not pipeline， the modifications to the data path after this。

So this is how the exception handler can figure out whether it's an overflow or an undedefined instruction essentially。

 and then it can take some action accordingly。😊，If it's an undefined instruction。

 of course you have to stop the program right， but you may actually do some bookkeeping saying that oh there's a particular instruction that people keep using as undefined instruction right who knows right the system can actually do a lot of recording for example right？

😡，Okay， so that was the example of undefined instruction undefined op code exception let's take a look at another exception over here。

 so this happens when you have an art type operation and when you have an art type operation you have the ALU result over here。

😊，If there's an overflow， you go to the state， if there's no overflow。

 then you basically go to the right back state。😡，So if there's an overflow。

 you go to a special state where you don't write to the register as you can see， right？😊。

So this is the overflow and here you do a very similar thing。😊，You set the program counter。Source。

To exception handler， so the next instruction to be executed is the exception handler。

And then you write the program counter interrupt code or exception cause here is the overflow which is zero。

 and then you call write an APC right so basically these two states are very similar。

 they're basically setting up the exception handling mechanism so that you jump to the exception handler and then you have the correct exception cause recorded in the cause register which we defined already over here。

😊，Does that make sense？So basically， all of the possible exceptional conditions in your system will need to be encoded in your finite safe machine so that you add these states that。

😡，Take you to the exception handler in a graceful way。

 graceful may meaning what we have discussed earlier。

 you should not update the architectural state with the exception causing instruction。

 you should not do this， you should do this。😊，Because there is a problem with the instruction and you should make sure that you go to the exception handler。

 which will do some stuff。嗯。Okay。So you can see there is more that needs to be done。

 This actually needed。 These are the modifications that need to that are needed to take the。

Exception cause and this cause register and place it into a general purpose register。

 so we're complicating the data path right？You can see that this data path supporting MFC zero so let's take a look at this let's read this from your book basically in summary an exception caused the processor to jump to the exception handler the exception handler saves registers on the stack this is specified by the MIPS architecture。

😊，Then uses MFC zero instruction to look at the calls and respond accordingly when the handler is finished it restores the registers from the stack copies the return address from EPC to blah。

 blah using MFCC zero and returns using jump register to K0 basically what this is saying is if the handler is finished successfully you return back to the program。

Because you save the program counter right， you basically， this is the exception causing PC。

 you return back to the exception causing PC， assuming you have gracefully handled the exception。😡。

This doesn't always happen， of course， if you have not you are not able to return to the program。😡。

What the exception handle there does is it kills the program， it says I cannot execute this program。

 it has an undefined upcode， et， right？😡，It can skip up down define off code or off code also， right。

 that's a potential fix to the problem， but it doesn't always work semantically nicely。😡，Okay。

 any questions？Okay， so you can read about this in your in your book clearly now what I'm going to talk about is more advanced and it really happens when you have this notionional multicycle execution this brings about more complications。

😊。

![](img/93c341352f9e2a7f235d712166f3478d_29.png)

![](img/93c341352f9e2a7f235d712166f3478d_30.png)

It doesn't it doesn't happen in this sort of pipeline here you need to have pipelining plus multicycle functional units。

 basically instructions can take different number of cycles in this execute stage。

 such that some of them actually complete execution out of order。😡，Now。

 if some of them complete execution is not out of order。😡。

You should really not finish those or update the architectural state out of order。😡。

That's the problem， basically。Then the question becomes， what do you do， right？😡。

These instructions are finishing early compared to prior instructions。

 and clearly you should not update the architectural state based on everything we discussed。😡，Okay。

 so what do you do， one thing you can do is this。Basically。

Don't make sure that this problem doesn't happen。meaninging。

If you have a particular instruction that takes eight cycles in the execute unit。

 make sure every instruction takes eight cycles in the execution stage。

This is the worst case solution that's kind of similar to the single cycle architecture that we discussed right earlier。

This is， I will say， a non solutionol because but basically it shows a problem。

 it shows a precise exceptions problem because。😡，You can see that the rights are happening in order right the update of the architectcticural state is happening in order。

 but unfortunately this fast instruction at instruction is taking as long as the slowest instruction。

 in fact， every instruction needs to take a。😡，As fast as the slowest instruction basically。

 that's the problem basically， the worst case instruction latency determine all instructions latency。

😡，This should really remind you of the single cycle architecture and why we actually got rid of it earlier。

For example， memory our patients can take， I don't know， hundreds of nanoseconds， right？

So does really make sense to have each function unit to take worst case number of cycles and the answer is it doesn't in the end。

 but this is a solution， not a good solution。😡，So that's why we're going to talk about supporting precise exceptions in better ways。

😡，And the key question we're trying to answer is how do we support precise exceptions in the presence of instructions completing out of program order that is going to become exacerbated when we talk about Out of order execution。

😡，Which is going to actually do other things。But there are four major solutions to this problem I'm going to especially focus on the reorder buffer if you have time I will mention history buffer in the out of order execution lecture well briefly discuss future register file there's also checkpointing but all of these all of these actually are employed in today's systems maybe history buffer is not that employed today but these are actually employed in existing processors so at least three out of the four are employed in existing process so existing processor actually much more complicated than what we have just seen over here and we've just complicated as multicycle machine right。

😡，Okay。😊，So let's jump into the reorder buffer if you want to learn more about test buffer future register file checkpointing。

 you can certainly look at old lecture videos， also see the backup slides I'll leave them over there。

 as I said maybe I will cover the basic idea and we'll get back to it maybe。😡。



![](img/93c341352f9e2a7f235d712166f3478d_32.png)

![](img/93c341352f9e2a7f235d712166f3478d_33.png)

So I think before jumping to reorderable for this is a great time to take a break。😊。

Let's take a break until。15 past okay， I think it's time to get back。So just to remind you。

 we're going to try to answer this question， how do we support precise exceptions in the presence of instructions completing out of order？

And the first maybe the only solution that we're going to go into depth is going to be the reorder offer。

And the idea here is very simple， except it's going to add a lot of complexity to the back end of the pipeline。

 as we will see the idea is basically complete instructions out of order。😡。

But reorder them before making the results visible to the architectural state， in other words。

 update the architectural state in order， but store the results of these instructions somewhere。😡。

My architecturally that and this place is going to be called every order buffer。😡。

Does that make sense， we don't we still update the architectural state in order in the program order。

😡，But the instructions will write their results out of program order and the machine will keep executing。

That sounds good。So basically we're going to introduce this thing called a reorder buffer after an instruction completes its rights as result into the reorder buffer reorder buffer is actually a hardware structure that keeps the instructions in sequential order。

 these are all of the instructions that are in the machine。😊。

And you only update the register file or memory when the instruction is the oldest instruction in the reorder buffer。

😡，Okay， that's the idea so you sequentially update the register file based on the initial ordering of the instructions。

😡，And this implementeds a circular queue in hardware we're not going to go into a whole lot of detail。

 but this is how it works basically， that's the idea， that's the concept concept。😡。

So how do how do we go into the next level basically when an instruction is decoded。

 remember decoding is in sequential order， you fetch the instructions in sequential order。

 you decode them in sequential order， so when an instruction is decoded。😊。

You have not seen later instructions yet。 that's good。

 So you reserve the machine reserves the next sequential entry in a special buffer called the reorder buffer that's over here。

 We're going to see the structure of it in a bit more detail。😊，When an instruction completes。

 meaning finishes execution in the function unit， it writes as a result into the reorder buffer entry that was allocated to it。

 this could happen out of order。😡，Remember the earlier picture where we showed。This， not this。

Basically， this instruction completes earlier than an older instruction。

 so this instruction can write its result into the reorder buffer。😡，Earlier than an older instructor。

But that's not a problem because reorder buffer is not visible to the programmer reorder buffer is purely micro architectural construct。

😡，Okay， so that's the idea。So when an instruction completes its rights as result in the reorder buffer entry。

 it could be out of order now when an instruction is the oldest in the reorder buffer and it has completed。

😡，Without exceptions and you're not going to handle any interrupts at that point in time。

 you move the result or control logic moves the result of that instruction。😡。

From the reorder buffer to the register file or memory that's when you update the architectural state so only the oldest instruction updates the architectural state and you keep doing that for the next oldest。

 next oldest next oldest so that's the essentially this way。😡，You can enable。

Architectural state to be preserved。Precisely。But you also enable out of order completion of instructions。

😡，Now that's the good thing you get higher performance and you also have。

One Romanman semantics to be obey。😡，Okay so let's take a look at this I'm going to show you an example of this。

 but this is a hardware structure reorder buffer is a hardware structure that keeps information about all instructions that are decoded but not yet retired or committed as we have discussed so it's a circular queue in hardware in this case you see an 16 entry buffer you have as with any circular queue you need to have pointers to the oldest instruction this is pointed to the reorder buffer entry that contains the information about the oldest instruction in the machine or head。

😊，And then there's a tail pointer which points the youngest in instruction。And this can be empty。

 of course， and there needs to be some semantics that needs to be satisfied with empty cues。

But basically that's the idea， so you need to have entries。

 you need to have each entry has some fields， for example。

 the validale valid means that there's an instruction allocated to this reorder buffer entry。😊。

If there's no instruction in the machine that's decoded。😡，Then。All of the entries are in。

 all of the entries are zero。And then the next part can be the destination Reg ID。

 which destination register is this instruction writing to。

 this is the value of the destination register， what is the value that this instruction wrote to the destination register？

😡，Is this value actually trusted， meaning did the answer actually write this value？😡。

Because you allocate the reorderable entry at the beginning when you actually decode the instruction。

 but then it takes some time for the instruction to write the results。😡。

For an a instruction for example， it takes some number of cycles right for a multi instruction takes some other number of cycles so when the instruction actually writes to the destination register it goes and finds its reorder of entry because it has allocated it knows what what reorder of entrys it has。

😊，it's been allocated， it basically sets the written and bits to the destination register and writes the value over here this happens after the instruction finishes execution after it gets out of the functional unit。

😊，Okay and there could be other fields that I will briefly mention in the next slide basically there could be other fields。

 for example store instructions which we're not going to deal with in this lecture you need to have the store address right because you need to update the memory also in order in program order so you need to have the address of the memory location that you're going to write to you need to have the data of that you're going to write to in that memory location this is a valid bit of the reorder buffer basically is there an entry here the program counter of the instruction that's used for exception handling you jumped this is basically you need to save the exception causing program counter just like we did in the multicycle MIPS architecture and then there's a field that says the instruction generate an exception。

😊，Because you need to record that information also right because reorder buffer contains instructions that may have been executed that may not be the oldest yet right because an instruction。

😡，Let's say let's go back to this picture over here。But for example。

 this instruction may finish much earlier than other instructions， as you can see。

 some other instructions， you need to record whether it's caused an exception over here。😡。

And then you handle that exception and that instruction becomes the oldest instruction if it ever becomes the oldest instruction in the machine。

😡，So that's why you need to keep all of these bookkeeping about what happened to the instruction while it's executing in the pipeline。

😡，And there are valid bits for the register and data value， for example。

 is the destination register value written， meaning has the instruction finished execution？😊。

And is the store address or store data have been generated again I'm not going to talk about stores and stores and loads in this particular case。

 but they complicate the reorder buffer so basically just to summarize you need everything that's required to correctly reorder instructions back into the program order。

😡，Update the architectural state with the instructions's results if the instruction can retire without any issues。

😡。

![](img/93c341352f9e2a7f235d712166f3478d_35.png)

When becomes the oldest instruction in the machine？

And handle an exception interrupt precisely if an exception or interrupt needs to be handled before retiring the instruction basically you need everything that's needed to support this that's why this reorder buffer is relatively large。

 let's say。😡。

![](img/93c341352f9e2a7f235d712166f3478d_37.png)

For every instruction that's decoded， but not yet retired。😡。

Once an instruction updates the architectural state and gets retired。

 you delocate the reorderable entry for that instruction so that a new instruction can be brought into the machine。

😊，By decoding。Does this make sense？Okay， good。So you need to have valid bits to keep track of the readiness of the results and find out if the instruction has complete execution。

 that's what the purpose of these Val bits over here are and that's essentially what I showed over here destination register written is essentially a valid bit saying has this instruction written to the destination register and if so。

 then the register value over here is the register value that the destination that this instruction produced。

😊，Okay， now we're going to go through an example， but before we go through the example。

 what does this accomplish， what does accomplishes this picture basically？😡。

So what does this picture say this picture says。😊，These are all independent operations。

 basically the same picture that I showed you earlier， everything was independent over there。

 the result of an instruction is first written into reorder buffer when the instruction completes。

 for example， this instruction has one cycle execution。

 it writes as a result into the reorder buffer when it completes。

 it doesn't update the architectural state reorder buffers micro architectural。

 so if we have not violated the one Neman model or precise exception semantics。😊。

But the result of an instruction is written to the register file when the instruction is the oldest instruction to the machine。

 that's what this right is。😡，So you can see that。The oldest instruction over here writes to the reorder buffer first and the next cycle there's some logic that checks whether the oldest instruction is finished。

 it takes the value from the reorder buffer and writes into the register file and now you can see that the rights are back in program order so if you're updating the register file and program order register file and memory but we're going to look at the register file most。

😡，So then the question is， there are some values in the reorder buffer that are produced by these instructions if there's a dependent instruction。

😡，How does it get that value？😡，idealdeally， we would like to supply that value to the dependent structure because these values are already produced so that we can make progress。

😡。

![](img/93c341352f9e2a7f235d712166f3478d_39.png)

That's the idea we're going to see that and we're going to see actually this enables a whole new world because reorder buffer is actually accomplishing something。

😊。

![](img/93c341352f9e2a7f235d712166f3478d_41.png)

That's even more interesting than you may imagine， it's not just about reordering， as you will see。

 it's also about renaming the registers and that's going to be the core of out of order execution。😡。

But we're going to get to that soon。So hopefully this picture is clear。😡，Now。

 this picture is beautiful because we have preserved the precise exception semantics what Norman model。

But we have not given up finishing the instructions result。

 let me go back to this picture where if that was not true。😡，Remember。

 so clearly the first one this was not true this caused， this violated the semantics。

 we fix the problem by making everything worse case， bad idea。😡，Now reorder buffer fixes the problem。

By decoupling。The sequential execution semantics from actually writing of the result writing of the result is micro architectural sequential execution semantics is architectural at the end。

 So now this enables higher performance because we can enable reading of these values that are written by instructions。

😊，Because there might be some dependent instruction， we're not showing that in this picture。

 but we're going to see that soon， but we have not violated the semantic sources， okay。😊。

Any questions？Okay， so basically the question we're going to tackle now is this。

 what if a later instruction needs a value in the reorder offer and we're going to see that this is really going to happen in auto of word execution so the next sector is going to really exacerbate it or now vary with me because I'm not going to give you like maybe examples you're not going to be completely satisfied with because otherwise it'll complicate the example significantly。

 but hopefully you will see the idea。😡，So basically one option is one option will be this instruction。

 let's say， wrote its result into the reorder buffer if a later instruction comes。😡。

Which may be over here， actually。And it needs that value because it's dependent on this instruction。

😡，What do you do one option is basically stall the operation， stall the pipeline。😡，Well。

 this is not very satisfying because if you stole the pipeline fine， yes， it's an in order machine。

 but the result is produced already。You can actually get it from the reorder buffer right why I stole the pipeline basically so this is not an option we're going to be satisfied with so a result a better idea is basically read the value from the reorder buffer。

 but then this brings the question about how and this complicates the machine a little bit more。😡。

Okay so let's take a look at this so how do we access the reorder buffer so this is a pictorial view so you have an instruction cache。

 you fetch the instruction you decode the instruction。

 you place the instruction to the reorder buffer。😡。

And we want to check where the source registers are coming from。

 the source register can come from the register file。😡。

The source register may be in the reorder buffer or the source register may come from the Ypass pass。

 so basically when an instruction is being decoded。😡。

There could be multiple different places where the source register。

 one of the source registers may be available。Or it may not be available yet because there may be some instruction that's going to write to that register in the pipeline that has not produced the value yet。

 it could be nowhere。😡，Well the up to date value may be in nowhere。😡。

It could be in the register file， this means that theres no other instruction that's executing that's going to write to that register。

😡，Because the instruction has already written to the register file and retired。

 it's out of the machine。😊，It could be in the rewardorder buffer， the value that you need。😡。

This means that the instruction that you're getting the value from has written into the reorder buffer。

 but not complete， it is not retired yet， but the value is available。

 so this instruction should be able to get it or it could be in the bypass path。😡。

hich is very similar to the pipeing bypasss that we have seen or forwarding passs last time I'm going to ignore the bypasss for now。

 but you really need it for higher performance also。

 but the fundamental operational principles of forwarding passs don't change based on the reorder buffer。

 but now we complicated the machine a little bit by adding this reorder buffer。😡，So okay。

 ignore the bypasss for now， bypasspass means that basically you can get the value immediately after it's produced from somewhere right before it gets written into the register file order reorder buffer。

 so it's actually a faster forwarding mechanism that happens in the back end of the pipeline。😡。

So let's ignore that。😡，Even a register file and reorder buffer basically complicates the machine together。

So register file so how do you let's take a look at how do you access register files I'm going to introduce multiple concepts over here actually。

 which is interesting by complicating the machine we're actually tackling multiple different things so register file is you index the register file with register file a register ID which is the address of an entry so you know this from the instruction decoding is called random access memory。

😊，Which is good， right， this inspection access is Reg 3， you use Reg 3 as the address。😡，Now。

 your order buffer is not like that。😡，Because we order buffer。

You don't query the reorderable for using Reg3 right the instruction that's being decod needs Reg3 as we will see also。

😡，But reorder buffer is not organized like that。 The reorder buffer is organized like this is my oldest instruction and this is my youngest instruction。

 this is the sequence of instructions in program order。😡，Where is Register3 over there？😡。

That I need the register three I need。 well， let's go back。It's actually somewhere。

It's actually encoded in this destination register ID。😊，In one of the entries， maybe。

So it's actually somewhere you can find it， but this requires a very different type of search。

 if you will， you cannot just index the reorder buffer and get the value you're looking for。

 you really have to do a search。😡，So this brings us to another hardware structure that you have not seen before。

 how many of you have seen content addressable memories？😡，Probably no one。

 so this is also used in real hardware。😡，Basically here。

You search all of the entries with a particular value in this case Reg3 for example。

 I'm going to show you this with an example because otherwise it's very hard to understand。

 but basically if you really want to get the value over here you need to have a content thatable we're going to fix this problem later on so don't worry but I think it's important to you see the reason why this is content that isable initially so if we need to search the reor buffer the register ID which is part of the content of an entry that's why this is called content that is。

😡，The address。The address that is actually that the instruction that I are ordered with is not what you're searching the reorder buffer with。

 you're really searching it with some other key and you're trying to find whether that key matches some content in each of the entries。

😡，Okay， so let's make sure this actually makes sense with an example over here so I'm going to go through this example that's going to be useful for the next lecture also so please try to understand it well next lecture meaning out of word execution basically we're going to have a register file。

😊，Register file has available each。EachEach register has a valid and each register has a value remember the v。

 we actually had a v if an instruction is going to write the register， it says a valid to zero。😊。

Right because later instructions should not get that value until that value gets updated we show this in pipelineing that's why you develop it。

 it's the same value， but basically。And then we order buffer also as a valid。

 whether the entry is valid， whether the destination register is written。

 if the destination register is written， what is the value of the destinationest register and this is the destination register ID that the instruction that's allocated to that entry is writing to and again we have all this to youngest instruction。

 these are just pointers they don't indicate initially this is empty。😊。

So initially all registers are valid， so initially all of these when you start the machine。

 for example， all of these should be one and they should have some reasonable values that are loaded when you load the program。

😡，In the register file and the reorder buffer should be empty because you are not finished an instruction。

 you're not decod an instruction yet。😊，Now let's simulate this program。😡，Again。

 it's not going to be the ideal example， the real example is going to come in the Out order execution lecture。

😡，But this is going to prove some points that are going to be important for。

 especially out of word execution， but also handling precise exceptions。

 so we're going to simulate the simple program， most of it at least。

 and we're going to see what happens to the registry values。😡，So to be able to do that。

 I think it's better to use this。

![](img/93c341352f9e2a7f235d712166f3478d_43.png)

Okay， okay， so this looks good。Do I have enough colors， three colors， I don't know， maybe not。Okay。

 so basically initially all of the registers are valid in the register file and the reorder bufferemp let's make sure that's the case so initially all the registers are valid one one。

 one， one one and initially reorder offer entries are invalid let's do that。😊。

It's kind of boring to do that for all of them so i'm going to skip them so all of them are zero basically and then the pointers need to be fixed also all this equal to youngest for example。

 so youngest pointer needs to be there okay。😊，Now let's simulate this， let's fetch this instruction。

 this multiply instruction。😡，Multiply instruction is going to be decoded while it's being decoded。

 it figures out it needs to access register one register to you index the register file。

 register one valid great， so there's some value over here， let's call one。

So you take value one and then you also index register file register two， evaluate valid， great。

 So there's some value that you can trust over here。

So the first multily instruction can go and execute。😡，呃。

After this so while it's being decod you do this right you read the register file but now we also introduced the reorder buffer while the multiply is being decoded you need to allocate our re orderorder buffer entry for it well you take the first empty entry which is the oldest over here or youngest so there needs to be some pointer management that you need to do also well。

😡，Something is happening here。Okay， our pen is dead alreadyy。Okay， basically。

 the machine sets this entry valve bit to one， which means that there is a multiply instruction over here。

😊，Register three is the destination Reg ID。Destination register value is not ready yet。

 destinationest register is not written yet， so I don't care what this is。

 this is zero right and then theres some bookkeeping that Im not going I'm going to ignore。😡。

So that's what needs to happen when multiply is being decoded， something else needs to happen。

 multiply needs to tell everyone that our three is is not。😡，Viled anymore， right？

So that later dependent instructions are not going to get whatever garbage value there， right？😡。

Because multily is going to produce that value。So at this point we decoded multiply。

 that sounds good， right？😊，Okay， so now let's decode the next instruction。

 The next instruction is the second second multiply over here。 I'm going to use red for this。

 I guess。😊，So what does this multiply do it basically first checks are three is available， no。😡。

So it cannot execute basically。😡，Is our four available， it's available， that's good。

 let's say that this is four so it gets a value four that's fine we're going to get back to this not execute soon。

😊，呃。And then it allocates an entry in the reorder buffer。

 so this is a red multiply over here just to make sure you can， oh， you cannot see。

 I can see it good。😊，So it's going to right to register 11。😡。

Which unfortunately doesn't exist over here， but it's not that important， that's why it's Regtry 11。

And then Reg 11 is clearly not available yet because it's being this instructions is being decoded。

 and it's going to basically set Reg 11 to ind over here so that later instructions are not going to get the garbage value over here that's not useful anymore because it's going to be rewritten with this。

😊，O。😊，So the上 good。呃。But let's imagine a case where so basically， later instructions。

Are not going to get this value r3 after this first destruction wrote over here， right？Now。

 let's imagine a case where there was some separation between these instructions。And。This multiply。

Want to read Arch。Okay， where could this r3 be r3 is not here because this was zero and this multiply。

 let's say this instruction had written this R3。😊，So let's assume that this multiply instruction wrote to its R3 and there's some value over here。

 I don't know，1568 I just made it up I don't know why。呃。Now this value is here。

It's not in the register file， this means that this instruction has written it to the reorder buffer。

 but it didn't write it to the register file yet for whatever reason， right？😡。

Now let's redcode this multiply instruction in this new scenario。

 if you redcode this multiply instruction， what we do is we check R3 is it here。

 not it it's not here。😡，Now， if you want to check whether it's somewhere here， what do we need to do？

😡，Well， we need to basically look for。Whether an R3 exists。

Earlier then this instruction somewhere in the reorder buffer。😡，So what does that mean basically。

 we need to search the content of the reorder buffer under destination Regtry ID。😡。

And compare whether that content is equal to R3。 So we have this multiply R3。😡。

We need to check whether this R3 is equal to。😊，Whether this value over here is equal to this three。

 if it's equal， then this is the R3 we may be looking for。😡。

Not quite not necessarily right because there might be some earlier instructions but we didn't show that over here so you will see that later on。

 so basically what you can do is you can actually check you can compare all of the entries in the your buffer to the end to the register ID you're looking for。

😡，And if there's a match。That means that you may possibly be looking for this register value。

 and if that's valid， then you can get this value over here， right？😡，Does that make sense？

But the problem is。You need to do this comparison for all entries here。

 I gave you a cooked up example where these two instructions were quite close to each other。

 but if these instructions were far away from each other。

 there would be lots of valid entries over here and they could be writing to our three as well potentially so each actually this instruction needs to find。

😡，The latest definition of R3， latest instruction writing to R3。

 that's older than this instruction and get the value from that。Does that make sense？

So you should not get any R3， any value of R3 from the reorder buffer。

 you should really get the latest one that's before this instruction。😡，O。😊。

So okay if you didn't understand it I'm going to give you another example soon okay so this is why this content is visibleable but before I move on I should basically say that if you're searching for R3 in the reorder buffer。

 if you're searching for any register in the reorder buffer actually you need to have comparators to this destination register ID field so this is one you need to compare entry0 you need to compare entry1 you need to compare entry2。

 you need to compare entry3。😊，Yeah and then you keep doing that basically you have 16 comparators that compares whether this register you're reading is actually written by any instruction over here。

😡，If that's true， then the entry must be valid。And the value must be valid and this must be the latest definition of r3 before this instruction so there's an ordering also unfortunately。

 so it's actually a priority based comparison logic that needs to be implemented so that this instruction can get the right R3 if it's in the order buffer so this is the content addressable search this is why it called content。

😡，Addressable， I don't know if you can see that。You're searching。This memory structure。

With part of the content that's inside the memory locations。

 you're searching for a particular content。😡，And in this case。

 the content is the idea of the destination register， but there are also some special cases。

 this needs to be valid， this needs to be valid， and this R3 needs to be the oldest youngest R3 that's older than the instruction that you're looking for。

 so it's really an age-based content addressable search and it's a complicated data structure if you will。

 you can do this in software clearly you can do this in software clearly you can do this in hardware also and hardware exists to do that in some machines。

😡，Is this clear？Okay， good， so let's let's take a look at I kind of divrged a little bit to show you the content of dis search。

 but let's keep decoding these instructions tomorrow or later today。

 probably tomorrow we're going to do a lot more decoding of these instructions in a let's say。

 much more methodical way。😡，But let's take a look at what happens to add R 5， R 6 R 3。

 There's something else interesting over here。 This add R 5 R 6 R 3。 Okay。

 I think I run out of all my colors right now。 this when it's decoded。

 it basically checks whether R5 is there。 It's there。 That's good。 It's valid。 R6 is there。

 It's there。 It's well。 So it basically takes those values。😊，It sets r3 to zero。

 well it's still zero， that's good， so R3 is still not trusted。😊。

And then it needs to allocate another entry over here。😡。

In the reorder buffer because it's being decoded， now this entry， the destination is R3。😊。

Something interesting is happening。So another RFV came over here， it's not valid yet。😡，Okay。

So now another r3 is inside the reorder buffer， so there could be multiple definitions of R3。

 as you can see in the reorder buffer。😊，But not in the register file， register file is only one r3。😡。

But in the reorder buffer in the machine， there could be actually many。

 many instructions writing chart3， all 16 instructions can be writing chart3。😡，Semantically。

 that may not make sense from a program perspective， but it's possible， it's not disallowed， right？

Now there's something interesting happening， this is a micro architectural structure and this is an architectural structure。

 architecture has used you only eight registers。😊，And we said that this is limited。

It's limited by the instruction and coding if you remember the ISA elect。

But we want it larger because if you actually have registers close to your processing units。

 it's faster。Well， how do we get larger？Well， this how we get larger。Basically， this R three。

Is being renamed to reorderable friendly。😡，Now， your architecture doesn't provide you arteries。

 well micro architecturally， I can have mini arties。😡。

Because they're completely independent of each other。 This R3。 remember。

 it has nothing to do with this R3， This there right after right dependence。

 if you remember or output dependence。It's a false dependence， it's not a true dependence。

The only reason these two instructions are writing to R3 is because there are not enough registers in the ISA。

But now we've kind of overcome that limitation。😡，You basically say this R3 is going to be produced at this location。

 this other R3 is going to be produced at this location。😡。

And they're really different R threes semantically。

So this is how a reorder buffer actually enables a renaming of registers。

 and this' is going to be very， very important in the next lecture。😡。

So that's the reason why I wanted to actually go through this。

 but now actually take a look at this R3 let'ss take a look at this instruction。

 there's a reason why this source is R3 here now this this ad instruction is sourcing R3。😊，NR8。

So it looks at R3 when it's being decod， it's zero。😡，It looks at R8， it's one。

 it's not that important， it gets value 8 from there and R 12， it sets R 12 to0。😡，Well。

 I travel as in basically。And then it's allocated to this entry。It's writing to R 12。

And the value is not readyant。Now while it's being decoded。

 if you really want to try to get the value of R3， you need to search the reorder buffer while this is being decoded。

 this is zero so the value cannot be in here。😡，Where's the value here， well I need to do that search？

😡，So what are three should this instruction get？😡，This is this instruction over here so it should get the latest definition of R3 older than this instruction。

 so it should really get the value from here right conceptually。Conceptually， that's makes sense。

 It should not get this value of R3。😡，Right。That makes sense then the question is how do you search for it。

 well that's the content addressable memory that's age based。😡。

So whenever you actually compare this R3 value to every single location， there will be two matches。

 these two will match。😊，And their entries are valid。This is valid well。

 we just made it valid earlier， this is invalid。This instruction should not get the value from here because semantically that's wrong。

😡，It should really get the value from the youngest instruction that's older than this instruction。

 which is this one that's defining R3。So there needs to be logic to ensure that。😡。

And that makes this content at search extremely expensive。

 That's why we're going to eliminate it in the next slide。Does that make sense？Okay。

 so this example actually shows a lot of interesting things。

 content the concept of content addressable memory and also how to actually search for it and how to avoid this sort of hardware。

 let's say。😊，Was there a question， okay？Okay。So let's try to make this picture better。

So I'm going to share the screen again。I can find it。No， I need to do something else。Which is in two。

 I guess。Okay。Okay， that can remain there now， I guess。Okay。

 so basically we're going to get back to this register renaming， but we have an issue over here。

 which is we index the register file nicely using the register file ID， we can get the value quickly。

 but if the value doesn't exist over there we need to do this content it this will messy search on the reorder buffer。

😡，And this is actually very hardware intensive。And as the reorder buffer size grows in today's machines。

 reorder buffer size can be actually more than0， which is interesting。😡，呃。

That search becomes even more expensive， so we want to eliminate this expensive search。😡。

So that's why people have the developed up ideas， so how do you simplify the access to this reorder buffer。

 the idea is use index。😡，What does this mean， access the register file first。

 you don't access these in parallel， you access the register file first。

 check if the register is valid。😡，And then access the reorderable for next。😡，And now if you do this。

 the reorder buffer does not need to be content addressable if you do some things under the access the register file first correctly。

Okay， so what does that mean so if the register is not valid。😊。

Register files stores the idea of the reorderable entry that contains or will contain the value of the register。

😡，Now we're going to actually complicate this register file a little bit to make the reorable for access simple。

 so we're going to see this also with an example soon。😡。

But basically we're going to map a register file entry to a reorderable f if the value so when an instruction is decod。

 it checks whether the source register is there in the register file。

 if the value bit is one for the source register that's great。

 you get the value from the register file， if the valid bit is zero。

 the register file will contain a tag a pointer so the reorderable entry that's going to produce that value。

😡，And this way you can direct the index into that reorderable front without doing this messy content addressable search。

😡，And this is how you can map a register to a Euro Reggi file maps the register to a Euro entry if there is an inf instruction writing to the register。

😊，So let's take a look at that basically we're going to add this tag to the register file。

 and this is going to have pointers to the reorderarrene that's going to produce the value for that register。

😡，So maybe we should simulate this。The same thing。But a different simulation。Okay。

 I'm going to go through this relatively quickly because it's going to be the same simulation except we're going to have tags that'll simplify things。

 so how do we go back here？😊，Doockkey cam。That doesn't work， stop sharing。Is that better， okay？

So now let's do this。😡，So initially， all registers are valid。

The same thing and all reorderable entries are invalid Okay。

 you can fill the rest we're going to decode this instruction， multiply r1 r2， go star3。

 you get the value in r1 that's good it's there you get the value in R2 that's good that's there this instruction can execute reset register to0 basically meaning it's not valid because this is going to produce the value。

Now we allocate a reorderableren for this multiply。😡，And then it's going to right to register three。

 that's good。😊，And then， well， it hasn't written it yet， so it's zero。

This value is not trusted anymore， but we're going to do one more thing that's critical。

 which is really set the tag of the register to reorder buffer for entry0。😡。

Now what does this mean basically this means that register  three is going to be produced by the instruction。

😡，That's being tracked and reorderable entry zero。😡，So if anyone。Once this register3 after this。

Should look into your order entries0。😡，That's my index。

 I don't need to do this messy content addressable search。

What I've done is I've linked all future references to Register3 to reorder buffer MP0， telling them。

😡，I don't tell the value for you， go check reorderable entry0 if it's there， take it。😡。

Because that's the instruction that's producing your value if it's not there， wait for it。

 it's going to produce it and get it from there。😡，So that's the idea over here and this is purely there's no content addressability over here anymore so let's take a look at how this works basically this multiply now sources register3 it now knows that it needs to wait for reorderable entry0。

😡，That's great。Register4 is available so it takes four fine and then it does the same thing to register 11 makes it I don't know invalid。

 but it sets the tag to reorder buffer entry1 because it's going to store register 11 into reorder buffer entry1 when it finishes so anybody who source register 11 should look into in reorder buffer entry1 so let's do this very quickly for the next instruction also。

😊，R5 r6 when we're decoding it this is good r5 and r6 are valid so you get the values and you can execute now we're going to write R3 there's an interesting thing that's going to happen here R3 is still invalid。

 but now this reorderable entry0 is not going to be orderable entry30 anymore because this instruction is going to be allocated to entry2 register3 it's not ready yet。

😊，But anybody who wants register fee after this point。

 after this instruction should look into your entry2。松は。

We were decoding instruction in sequential order， this instruction overwrt Regtry 3 and later instructions whose source Reg 3 should get the value from reorder buffer entry0。

😡，Now， in other words。What we've done is renaming， we've renamed register entry 3。😡。

Inter reorderable F too。Does that make sense？Now you can keep renaming the same register many。

 many times this way， and this is going to form the basis of Auto order execution tomorrow。

But let's go back to finishing these slides。 So hopefully this is clear。

 You're going to see this again tomorrow。 if it's not clear， I floating meeting controls。Okay。

 I need to do something else。Which is this。Okay， it's the same slide。So this is real。

 so as you can see， this is actually Intel Pentium Pro which is the first really commercially successful automotiveor execution processor。

 and you can see that this is the register file。😊，It's called the， well， it's called actually。

 this is the mapping table， this is the tags that I showed you。😡，And these are the eight registers。😊。

And basically， if an instruction is sourcing a register zero。😡。

This is an index that tells you register zero is in the register file， architectureure register file。

 or it's coming from reorderable entry x。😡，So they basically separated the tag from the register file over here。

 but it's essentially the same constant。😡，So what I've shown you is real as you can see。

 and we're going to make it a little bit different later on tomorrow and this is Intel Pentium Pro。

 which is interesting to look at because at that time they didn't have enough transistors they could put on a chip so they put the whole L2 cache in a separate chip as you can see。

😡。

![](img/93c341352f9e2a7f235d712166f3478d_45.png)

![](img/93c341352f9e2a7f235d712166f3478d_46.png)

Okay， so basically one of the major concepts that you've covered today is。

This registertry renaming with our order buffer I want to emphasize this a little bit more because this is going to be very important tomorrow what we've done is this output an antidependencies if you remember them we're going to look at them in the next slide also they're not true dependenceencies the same registry refer refers to values that have nothing to do with each other。

😡，And the main reason why this happens is because you don't have enough registered IDs in the ISA。😡。

Now we have what we have done is rename the register ID to the reorder buffer entry that will hold the register's value that's going to produce that register。

😡，This is， you can think of that renaming the register ID to a reorderable French ID。😡。

We're going to see tomorrow renaming the architectural Reg ID to a physical Reg ID。😡。

And after you do this renaming， reorder about franchise ID is used to refer to the register。😡。

So this is micro architectural， this big register file or big reorder buffer micro architectural。

 it's not visible to the programmer， but underneath we get rid of these dependencies。

 these false dependencies that exist because we don't have enough names。😡，Tomorrow。

 we're going to introduce the term reservation station。 So you'll also see that。

 So this eliminates anti and output dependencies。 The only thing that you really need to know。

To deal with is really flow dependencies， which is really the true dependencies。

 right and we actually know how to deal with them kind of very linking them through these reorder buffer。

 So this also gives the illusion that they are actually a large number of registers。

 You may actually architecturally have eight registers。 if your reorder buffer is 1000。Internally。

 micro architectualally inibly to the program， you actually have thousand registers internally。😡。

That's beautiful， I think。So remember basically these are the data dependence size。

 the only true data dependence is the first one because you really need this value。

 the second instruction that really needs the value that's produced by the first instruction。

 these are all false depends they be eliminated using register renaming。😊。

Which is a way of eliminating them without changing the instruction of architecture。

So this is for you to do basically you can actually do this example on your own I've added some loads and stores also it's basically very similar to what we have done but for you to do so basically this is what you construct you construct an in orderder pipeline with a reorder buffer what we're doing is we have in orderder dispatch an execution so you have you decode and you allocate things into a reorder buffer when you're decoding。

😊，You have auto order completion of instructions， but you write the results into the order buffer。

 you write the result micro architecturally first and then commit to the architectural state when the instruction becomes old。

 so have in order decode dispatch execution， we're going to define dispatch later on more carefully auto order completion of instructions。

 but in order retirement in program order。😡，So we're preserving the sequential semantics of the onen and ISA。

So what happens in De， do you access the register file in the reorder buffer。

 allocate the entry in the reorder buffer for the instruction that you're decoding。

 you check if the instruction can execute， if the instruction can execute。

 meaning that it doesn't have any dependencies， it has a value， the values that it needs。

 you dispatch the instruction dispatch is basically taking the instruction and putting into a functional unit so that it can execute seamlessly。

😊，During execution instructions can complete out of order， as you can see out of program order。

 no problem， because when the instruction completes， you write the result into the reorder buffer。

 which is a micro architectural structure， you don't update the architectural state。😡，And you really。

 there's an asynchronous process， so the retirement and commit is an asynchronous process。

 there's a finite machine or control logic in the back。😊。

That checks whether the oldest instruction is ready to finish basically。

 if it doesn't have exceptions， if it doesn't have exceptions and it's ready to finish。

 meaning it also already has its result generated its rights。

 this control logic takes the result from the reorder buffer and puts it into the architectural register file or memory。

😡，Because memory is handled similarly， except it's just huge。And if it doesn't work that way。

 unfortunately， if there's an exception， for example。

 then this control logic flushes the pipeline and starts from the exception handler just like we discussed earlier。

😡，And that's the final pipeline that we have built today。

Let me quickly cover the trade offs of this reorder buffer。 Well， we have very little time left。

 but basically this is conceptually simple for supporting precise exceptions。😡。

And it also can eliminate false dependencies， it can link instructions， as we will see。

 unfortunately。😊，You basically need to access the reorder buffer。 It adds more complexityClearly。

 there's more hardware， but it add also complexity in the sense that you need to get the results that are yet to be written to the register file。

 this requires content addressable memory or indirect。Content addressable memory is very complex。

 that's why we do in direction， but indirect actually increases the latency a little bit。

 but it's actually at least not as complex。😊，People have developed other solutions to eliminate some of these disadvantages。

 but they also get rid of some of the advantages somewhat and they complicate the system history offer future file checkpointing they're all actually the solutions that we don't have time to discuss but again you can see the lecture video from past years and also the backup slides so this is lecture video and there's actually a lot more elaboration on it if you're interested。

😡。

![](img/93c341352f9e2a7f235d712166f3478d_48.png)

![](img/93c341352f9e2a7f235d712166f3478d_49.png)

Okay。So if you have actually readings Smith and Soy paper covers some of this。

 but probably not to the extent that we have covered today。😡。



![](img/93c341352f9e2a7f235d712166f3478d_51.png)