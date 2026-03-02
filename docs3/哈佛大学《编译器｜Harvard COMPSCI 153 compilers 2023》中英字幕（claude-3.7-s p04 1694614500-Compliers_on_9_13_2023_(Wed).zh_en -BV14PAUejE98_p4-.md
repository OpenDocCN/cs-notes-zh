# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p04 1694614500-Compliers_on_9_13_2023_(Wed).zh_en -BV14PAUejE98_p4-

![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_0.png)

Hey， everyone。Welcome， let's get started。嗯。Thank you。

 device people for crowding over into the device side of the room。 device free people。

 Enjoy your space。 stretch out。😊，Come for the distraction free environment。 Stay for the leg room。

Okay， first announcements。Homework1， the hello Ocal， Ho Camel， reintroduction to Ocael is due today。

 11，59 PM。 but of course， like with all the homeworks here in this course。

 you can use up to three days worth of late minutes for homework out of your total of 10 late days。

 yeah，10 days worth of late minutes。嗯。We are going to be， we have released homework too already。

That's due in two weeks from today。 the end of Wednesday， September 27。嗯。

As you saw in the email this morning。We will be forming study groups soon。

 I haven't had a chance to actually look at the。Results of people who have submitted to gauge the enthusiasm in the class or the number of opt outs。

 but。Please everybody fill in that form， even if you want to opt out at study groups。

 it's good for me to know that explicitly as I work on matching people up。

 please fill in that form by about 5 PM tomorrow， if you can。Shouldn't take long。

 It's mainly just about the hardest part is just giving an approximation of your availability or preferences for study。

And then hopefully， by the end of Thursday or hopefully Friday morning。

 we'll be emailing some introductions so you can get to know your study group members。As always。

 I encourage you to start earlier rather than later on homeworks。

 and I encourage you to work with your study group to actually find the time to meet with them be it in office hours or otherwise ways and get a chance to work on it together。

🤧。Any questions on the homeworks or anything on the administrative side。

So what we're going to be doing today is continuing to look at X 86。 and in particular。

 our our simplified version of it X 86 light， which is what you'll be dealing with in homework 2。😊。

So the main things we'll be looking at are continuing to。

Gain an understanding of the X 86 assembly machine， our internal model of it。

 And also starting look at how we're gonna represent X 86 code。Within an Ocal program。

 some of what you'll be doing in homework， too。We'll also spend a bit of time talking about calling convention。

 because that's something you'll also need to be familiar with as we go on。

So this diagram we saw last class， a schematic of the X 86。



![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_2.png)

The X 86 machine with memory over here， processor taking up the bulk of this diagram with registers。

 control unit， A L U condition flags， O， FS F， C， F， and so on。 the instruction pointer， R I P。

 and so on。

![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_4.png)

We finished last lecture by talking about addressing in X 86。

 And we talked about the most general form that the an address has consisting of a base plus an index and scale。

 plus a displacement。

![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_6.png)

![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_7.png)

And these examples indicate the various forms of that indirect addressing。嗯。In X 86 lights。

 we really only have。We don't have the full generality。

 And soon we'll see in code how we're representing the limited forms of indirect addressing。Okay。

So the X 86 light memory model。 So we're dealing with 64 B。

 So our memory can be addressed using 64 B。address。So。We have a total of 2 to the 64 Bs in memory。

 and each by is addressable from an address expressed as a 64 B address。嗯。In X86 lights。We are。

Going to be requiring quadalign pointers。 I think I might have misspoken last lecture。

 Somebody asked a question about whether it was bitete addressable。 Yes， it is byte addressable。

 but in our machine， we're going to require the pointers to be quited aligned。

 meaning that we're have to be all the memory addresses have to be evenly divisible by 8。

And what that means is the address we're reading from， we're going to read 8 bytes， 64 bits。

And the next addressable， readable address is。8 boats beyond that one。

This just simplifies your implementation of the simulator， and most programs would， in fact。

 be doing aligned white reads。Which the machinery supports more efficiently。嗯。

One useful machine instruction in X 86 light this is the load effective address L E A and the cures。

 of course， for Quadword。 we're referring to the 8 by addresses。

 And what this does is it essentially takes an indirect。O end。 So referencing a memory address。

But what it does is it puts the computed memory address into the destination。

So L E AQ does not actually access memory at all。All it's doing is computing。

Based on the indirect opera end base plus displacement and so on， the memory address。嗯。OK。

Any questions at the moment about memory addresses， L E A Q， which to be honest。

 you will be learning to love， particularly in homework 3。As。It's essentially a key part of L O VM。

But any questions at the moment doesn't。L E A Q simply computes the address。

And puts the address into the destination register。Yeah。行。Quickly， go over the different。LEA。

Adddversses。Sure。So you might remember last class， we talked about the idea of treating an opera end differently。

 depending if it was a value or a location。With the idea being that when you had no brand。

 that was a value。And that opera end was a memory address。

 What it meant was read the contents of that address and treat it as a value。

Whereas if an opera brand was a。A location。Then what you're doing is you'd evaluate that opera brand by。

 for example， figuring out which memory address it refers to。

But you're not looking at the contents of that memory address。

 It's going to be the location that you put a result into。 For example。

 So this is L E A Q is kind of like that。 The opera hand that it's taking。I N D。

 that first opera end is going to be treated as a location that is。

 it's going to be evaluated to an address。Right， so it's not gonna look inside that memory location to get the value。

 It's simply gonna figure out what the address is。 You can think about that L E A Q as it's simply doing that computation of base plus scale times index plus displacement to get a number and address a pointer into memory。

And it's going to put that pointer that address into the destination。

Which would typically be a register。So if destination is a register。

 then what this means is L E A Q is not accessing the main memory at all。Does that help clarify。

This is something subtle， and you will get。In homework 3。

 you'll very much need to wrap your head around this idea that L E AQ is simply computing an address。

 It's not accessing memory。O。Any other questions？ Thanks for those。Okay。

 we saw in the schematic that by convention， we separate the memory into regions。

A stack which starts off with the high memory addresses and grows downwards towards the low memory addresses。

 Now， of course， as we're going to see soon， the stack is used to help manage calling of functions。

 keeping track of arguments to functions and so on。

 We'll look into that in more detail later in this lecture。

For the purposes of where we are are at the moment。

 which is going through a list of the X 86 light instructions。

 there are two instructions that directly manipulate that stack。So first of all， the RP register。

Is a special register that points to the top of the stack。And we have two instructions， push and pop。

That end up putting a value onto the stack。So push source takes that source up end。Puts it into。嗯。It。

 it decrements the stack pointer。 So essentially creating a new space at the top of the stack。

 And into that space， it puts the source opera end。Okay， the dual operation is pop。

Which looks at the top of the stack， takes that value and puts it into the destination。

And then increases RP by one quadword by 8 B。That is or by 8 changes the address in RP by 8。

I just wanna check。 this is familiar to almost everyone in the class from C S 61， right。

Pushes and pops。 Does 61 use 32 B or 64 B architecture these days。64 bit。 O， cool。

I'll get to update my slides later on，Have a lot of stuff in 32， but。Okay， so。

We're going through the X 86 instructions。 So we'll push and pop。

I want to talk now about condition flags and condition codes。

So you might recall from this schematic that we that the processor has a number of flags。

 An X 86 light， we're only considering three flags。O， F， the overflow flag， S， F。

 the sign flag and Z， F， the0 flag。So X 86 instructions。

 some of them will set these flags as a side effect。 So， for example， the ad instruction。

 when it's adding two numbers together。Based on the result， that's going to set the overfo flag。

 sign flag and0 flag to the result of that addition。The overflow flag is going to be set to one。

When the result is。Too large or too small to fit in the 64 B register。Now。

 I wan to say that the overflow flag is set based at least in X 86 light in X 86 light。

It's set based on sine integer addition。 So or rather treating the values as sine integers。Okay。

 under the two's complement representation。So when we talk about overflow。

 it means that the number is too big a positive number to represent。

Or too small a negative number to represent within our 64 bits。The sign flag is 0。

If the result is positive， one， if it's negative。That is。

 the sign flag is equivalent to the most significant bit。

 which under twos complement is indicating whether or not it's。It's negative。And finally。

 the zero flag is set to one when the result is0。So from these three flags， overflow flag， s flag。

0 flag。We're actually able to figure out the relationship between two opera。

We're able to compare two operas for equality， inequality greater than less than greater than the equals。

 less than a equals。And so on。So let's go through a few of these。 make sure it's clear in our heads。

If we have source 1 and source 2。2 values。And we want to compare them。

What we do is we compute source 1 minus source 2。Okay， the result of that operation。

 source 1 minus source 2。 think about that as setting overflow flags。 if the result is， you know。

 based on whether the result is too big or too small to represent。

 setting the sign flag and setting the zero flag。O。

So if we wanted to know whether source 1 and source 2 are equal to each other。

We can look at the result of source 1 source 2。 And if the0 flag is set， we know that they're equal。

Okay， and that's because source 1 minus source 2 is going to be equal to 0。

If and only if source 1 equals source 2。Anlogously。Not equal。 So 1 is not equal to source 2。

 If the0 flag is not set。The zero flag equals  one。More interestingly， the inequalities。Okay。

 so let's think through greater then。When is source 1 greater than source 2。Okay。

 so let's take a concrete example。 Let's say source1 is。Tin。Soce 2 is 0。

 So source 1 is greater than source 2。10-0 is 10。That fits within our 64 beds。 So overflow is false。

 0。The sign flag is positive。呃，So so zero。And the result was 10。 So the zero flag is， is not said。

And so indeed， that is the case。

![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_9.png)

Soce 1 is greater than source 2。10 is greater than 0 when the overflow flag equals the source。

 the same flag do not overflow in the results positive in this case， and not  zero flag。



![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_11.png)

You can go through and just mentally check other cases for when。Let's say source 1 is a really。

 really big integer close to the maximum integer that can be represented。And source 2 is， let's say。

 a small integer。嗯。Say， the maximum negative number。

And then you can check about how the over flag will be set。嗯。But the result will be。

 will still be correct。Okay， so the cool thing is just from these three conditional flags。

 we're able to have this comparison between two。Two upper ends in a straightforward way。

You can go through and make sure they make intuitive sense to you。

 You will be implementing them and homework too。 So you'll wrap your heads around them in great detail。

But any questions at the moment about how these flags can encode these comparisons。Yeah。

Should we be thinking about。Fals。E as like， signed or。Yes。

 for our purposes think about all of the 64 bit values when we treat them as intes as being signed intes。

 So even if like in a program。Like in the code is like this。Sday in the assembly still。Yeah。

 we're working in X 86 lights for simplicity。 We're assuming that all the values are signed。

 If you wanted to be compiling unsigned 64 bit intes into assembly。

 some things would be a little different in particular， you might need to think。

I'd need to go through and and carefully think through the comparisons to make sure that they make sense。

Somebody didn't know made off the top of their head。

 X 86 has more than just these three conditioned flags。 And so part of them。

 those additional conditional flags， I think， are based on。

Are you doing signed or uns signedigned comparison。有。But for our purposes in class。嗯。Go with signed。

Com。When you have to like。気持ち？Yeah， so let's suppose we were trying to figure out if。You know。

 the minimum integer and， no and the minimum integer plus one， you know， they is， is。Comparing those。

 source 1 is the minimum integer。 I at less than the slightly bigger number。

 This will still work out。 You'll do source 1 minus source 2。Actually， that won't overflow， right。

 because that'll turn out to be nicely in the middle of the range once you。嗯。Yeah， once you do that。

 that'll be close to 0。 But if you do it the other way。

 you can actually get an operation where source1 minus source 2 will overflow。

But the result of these comparisons will still be correct。

So I encourage you to work it through with an example。To， to make sure that that you understand。

 that you're understanding how the overflow and the sign flag end up。Working， working out correctly。

Yeah， on the same thing， like， as example， source one being like the value0 and source two being the value。

 like negative one。like0 minus negative1。I an overflow flag like， because the result is just。Yeah。

But then in order for it to be like it probably was bigger than。

The flag has the equal sine flag and the sine flag is one。当他。It works out。 You。

 this is helpful to do on pen and paper。 And also when youre implement it。

 you' you'll lac course be writing many test cases， right。Right。Los of nods。

 fantastic to make sure that you're getting this correct。😊，O。Al right。

Continuing our tour of the X 86 instructions。 I'm gonna to start talking about control flow。

But in order for me to talk about control flow， we first need to talk about how code is arranged in X 86。

 So X 86 assembly code is organized into labeled block。Okay， so here we have the example。

 two labeled blocks，1， the first with labeled one。

![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_13.png)

Followed by a list of assembly instructions， the second label block。

 label 2 and another list of assembly instructions。



![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_15.png)

So those， those labels indicate code locations that can be jump targets。

 either through conditional branches or function calls。

What's going to happen is the the linker and the loader are going to replace those labels with the actual address of the code。

 So conceptually， you can think of those labels as really being like an address。

 just an address we don't know yet。When you refer to a label and assembly code。

 as if you're referring to that address and the linker and loader will take care of。

 take care of replacing it。嗯。An X 86 program normally starts by starts execution at a special code label called in Maine。

So think about this as the main function of the C program， that's the entry point of it。

That's what's going on in the S 86 code。 It's starting execution at that label called mean。Okay。

 so with this idea of labeled blocks， we can start talking about control flow。For control flow。No。

 dear。 We had a piano in there。And second。嗯。Okay， so control flow。

 you can just directly jump to a label， jump to an instruction。 that's called a non conditional jump。

But many jumps are conditional。 Now， the idea of a conditional jump is。Typically， done as a。

Two step process。 First of all， you do a comparison。 So CM for compare Q， the quad suffix。

 comparing source 1 and source 2。

![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_17.png)

嗯。

![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_19.png)

And what this does is it computes source 2 minus- source 1。

And sets the condition flags appropriately。Then based on those condition flags。

 there's a whole lot of different jump instructions。



![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_21.png)

JCC。We're using to stand in for actually a collection of about six different instructions。 Ju equal。

 jump， not equal， jump less then， jump less than or equal and so on。

 So for each different condition code。

![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_23.png)

And essentially， what that conditional jump does is it if the condition is satisfied。That is if。

Source 2 was less than source 1。Then， it will jump to。啊。The the opera end， the source opera end。

 which will be a label。an address in the code to jump to。 Otherwise。

 it'll simply fall through and start executing the next assembly instruction。嗯。

So there's an example there。 Comp Q R C X， R A X。And then if they are equal， it jumps to underscore。

 underscore true label。Right， so that would be something that you might translate an if statement to。

If P equals bar， then， and you have some code。That word might get ultimately translated into assembly like this。

 comparing to opera ends if they're equal jumping to a piece of code to execute it。

One subtlety about the comparison， because we're using A T and T format。

 and because comparison is essentially a subtraction operation。

The way that the subtraction instruction is written is subtract destination source and a computes source minus destination and puts that in the destination。



![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_25.png)

The comparison here。Comque source 1， source 2 is actually comparing source 2 and source 1。

So if you compare source 1， source 2 and then do a jump less then。

 what you're meaning is jump if source 2 is less than source 1。



![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_27.png)

Okay， so there's just a subtlety there。But you'll will be writing test cases and making sure you get it the right way around。

One additional instruction that we have is set BCC destination。 the B here stands for Bte。

 And what it's gonna do is take a look at the condition code equal， not equal less than and so on。

 and just set the lower bit of the destination based on the condition。



![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_29.png)

![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_30.png)

So this provides at the assembly level a way to compare two values。

And then get that result of the comparison and actually manipulate it as data。 if you wanted to。

 for example， have some value that is explicitly representing with a。呃。呃。

Explicly representing the result of the comparison。

Any questions about these comparison operation and the jump， Yeah， William。Make sense。

 because that B is a D I that the same thing as a queue。Sat or different。あけせ？Not an now X 86 light。

 There is not a at Q。I can't remember enough about X 86 to know what variations of the set。

The said operation there are。Yeah， Kenny the lower。Yeah。So remember that in next 86 light。

 we're dealing with 64 bit values or which is 8 B。Okay， each by being 8 bits。

And so our registers are 8 B worth。Of information。嗯。If you remember from 61。

 these bytes are kind of ordered from the most significant by。

Through to the least significant by where when we interpret those bytes as assigned ins are affecting how。

What entity do we。Those， those8 by represent。 So the lower by here is simply the least。

 the8 least significant bits。嗯。Yeah， does that help？ Okay， thanks。All right。

Any more questions on condition， on comparisons， conditional jumps。Okay。

 some more control flow instructions。 unconditional jump。

 jump source simply always jumps to the opera end， the source opera end。嗯。

There's special support in X 86 for function calls。 So there are two instructions here， call。

 Q and Re Q。So core Q is takes a source opera end， which is the label。

 which is the entry point of the function that we're invoking。So， it does。Essentially， two things。

 It takes the current instruction pointer。And pushes it， pushes it onto the stack。

 So that is it's going to be modifying the RP pointer。

To reduce RP by 8 and store the instruction pointer into this into that new element at the top of the stack。

 And then it's going to jump to that it's， it's going to set the instruction pointer to that opera end。

That is the next thing it's going to do is start executing at the beginning of the function。嗯。Ritcue。

Return is what happens at the end of a function。It pops off the value at the top of the stack and puts that value into the instruction pointer。

And what this effectively does is return control flow to。To the points， to the caller site。

The point in the code that invoked the function。Any questions so far。

 And I appreciate this is recap for almost everyone in the class。Okay。

 let's actually take a look at how we're going to represent this。



![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_32.png)

In code。Soir。Okay， so this is code that's close to。What you'll be looking at homework to。

 it's uploaded on canvas if you wanna take a look at and play around for with your by yourself。

 what we're doing here is setting up some Ocal types and data structures that we're gonna use to represent X 86 lit code。

 So let's。Let's walk through this。 Is this big enough for you to see in the room。Great， okay， labels。

 Remember， we have labeled blocks。 Labels are just gonna be strings。

We're defining the type quad to be into 64。 So 64 bit integers。

 one of the built in primitive types in Ocal， fantastic，64 B。😊，Signed。嗯。

We're going to be defining opera ends。Different kinds of operas。

Immediate opera can either be a literal value。Of a quad quadword，64 B value or a label。

We have a whole lot of registers。In X 86 light。Named here with the data type。

Where each data constructor takes no arguments。 Okay， so R I P， the instruction pointer， R A， R A X。

 R B X， and so on。 his RP， our stack pointer。That has that is treated special。

 and general purpose registers R 0 weight through to R 15。We can define our operas for instructions。

They're either an immediate opera end that is a literal or a label， a register。

One of the registers we just enumerated。And these last three， the different forms of indirect opera。

 memory addresses。We have only a limited form of indirect addressing an X 86 light。

 The first one end one is simply an immediate address。So this is essentially displacement only。

There's no base。 there's no index in scale。So this is great for referencing a label when we're using a label to refer to a memory location or a hard coded memory address as an immediate。

😊，Second form of indirect addressing is simply a register。

So this is the memory form where we just have a register by itself。The basery just about itself。

 And what it's saying is。It's referring to the address of the pointer that's in the register。

 The register contains a pointer some location。 This opera R is talking about that location。嗯。

The third form in X 86 light is。Displacement， plus space。Okay， so a register plus a constant offset。

 sorry， an immediate。An immediate offset。The instructions that we have in X 86 light are enumerated by this op code data type。

So they're listed here。 We've covered all of them in the preceding few slides。

 covered some of them at the end of last election and the rest here， move， push， pop。

 load effective address。嗯。I we didn't talk about increment and decreement directly。And so on。

You'll note that we have for the conditional jumps。

 we actually explicitly have six instructions for the different kinds of conditional jumps。 Ju equal。

 jump not equal， jump greater than jump greater than or equal。

 jump less than jump less than or equal。All right。In our representation of assembly。In Ocal。

 an instruction is a pair of an op code。And a list of opera。Okay。

 so different instructions will take a different number of opera ends。

The design choice we've made here is to simply use a list。

To make sure that every instruction has a list of operas for some operations。

 that list should be empty， for some of them， there should be exactly one element of the list for some。

 there should be exactly two elements in the list and so on。Okay， any questions up to this point。

Yeah， I guess I was wondering about that design choice。

Why we decide on that instead of using instructors as part of？是来里去。Sp。Yeah， as。

 as we'll end up seeing in the code when you do the simulator。

 this will make some things easier and some things harder。

And it's the same if we went with the other design choice of having。

 instead of having a separate data type for op codes and a separate type for instruction。

 if we just had a single type for instruction with different。Data constructors。

 free chop code and the。And their opera。You could make that work out， but some things would be hard。

 for example。It'd be harder to look at the op codes in isolation from the instruction。嗯。讲。So it's。

 it's a design choice。That we made。 Yeah， medicine。Registers。Does that referring to like。

The actual address school registers。See。Yeah， so this I And D2 form of the argument。

 You can go back and look at the slide， but the indirect form would be where we say， you know。

parentrenheses register， and their register is like the base register。

 So the idea of this indirect opera end is when you're treating it as。嗯。A destination。

It's referring to the memory address that is simply the contents of the register。哎。

If you're referring， if this opera brand is interpreted as a value。

What it means is that you take the， the contents of the register。That's the memory address。

 Then you'll go to memory and read the contents of that memory address。And it'll be the。

 the value stored in the memory location。这是。So the way to think about it is these in direct operas。

Identify a memory location。And then。And then depending on whether the opera is being used as a。

Location or as a value。It like be。The memory address itself or the contents of that memory address。

Well the the contents of the location that is addressed。Or that is pointed to。Does that clarify。

 Okay， thanks。Okay， any other questions before we get into the more complex data structures。O。

We had define a。Parametric type。Alpha labeled。Right labeled something。

 And we'll see what we'll use in just the things that we'll instantiate alpha the parameter with。

 But the key thing is that this is a record that has three fields， three components to it， a label。

Right， so that's why it's a labeled thing。It has Boolean。

That's indicating whether or not this labeled thing is global or not。

 Global essentially means whether or not it can be referenced from another object file。Right。

Or whether it's just something internal to this object file。 So， for example。

 you might have some of the functions might be marked as global。

 meaning that other code from other source files， from other object files are going to be able to invoke it。

Other labels might not be global， meaning they're just internal lonely。

 Maybe they're the destination of a jump for the else branch of a conditional。

 There's no reason why anyone external to this piece of code needs to be able to jump to that。

The final part of the record is a value of type alpha。Yeah。So。嗯。Pro almost there。

Let's jump to this one。An assembly program。Consists of two things。It consists of a list。Of。

🎼Labeled instructions。 by that， I mean。呃。Alpha here is being instantd with instruction list。

So that is， it's a labeled block of code。It's a label with a list of instructions。开。

And this first part， the text part of the assembly program。Is a list of these labeled blocks。

This is the code。Right， this is all of the code of our program。 a list of labeled blocks。

The code inside， those instructions inside the blocks might be referring to those labels。

 jumping to them and so on。 Some of the of these labeled blocks， the label might be global。

 maybe because it's the entry point， say of the main function that somebody else is going to jump to。

In addition to the text portion of the assembly program， this list of labeled blocks。

An assembly program also has a list of labeled data。Okay， so here。

 data is either going be quad words。So immediate values or constant strengths。

And the reason for this is。You can think about an assembly program as being in these two parts。

 The text part is the code， The text segment， as it's also known， is where the code lives。

 The data segment is where you essentially have global variables and some constant values。

 like constant strings。And that's exactly what our data type construct is capturing。

 It can either be a constant string， or it's going be 64 B value of some kind that。

That can be read and unwritten during execution。So this is kind of the key thing。

 an assembly program。 Allright， It's got a text and a data section。

 Tex is a list of labeled blocks of， yep， of labeled blocks。 The data is a list of labeled data。

Any questions at the moment about these data structures。🎼Okay， yeah。The instruction data type。

 how do we enforce？So like some of these articles will take。My condition such as， oh。

 this opera takes like。Yeah， how， how do we enforce that the instructions are well formed that。

That it has the right number of arguments for the， of of operas， rather for the given op code。嗯。

We're not going to do it statically。 So we're not going to do it just by looking at it。

So we can do that。By examining the data structure。 and you can imagine a past to make sure that it's syntactically well formed。

 or maybe when we're in the process of simulating an X 86 program。

 we would complain through an exception if we have the wrong number of opera。同。Okay。

 in this code here， once we have an assembly program， there's some stuff we can do with it。 right。

 we can print it out nicely。 So here is a whole bunch of code that essentially focuses on taking one of these data structures and being able to print it out in a nice way printing out registers。

 printing out immediates， printing out opera ends with， you know。😊，Prefixing。

A dollar owe to immediate。two immediate opera ends and so on。嗯。Printing out up codes elegantly。嗯。

Here is an example in our code。Of being able to nicely and easily match against the op code and then do something with。

The list of arguments。That's all the same。 So if we use a data constructor here。

It'll be harder for us to factor out this common piece of code。

 Do this thing for all of the opera ends of the。Of the constructor。嗯。All right。Let me just。

Let me jump to in just a6， showing you some output of this code。

 One quick thing is we can also set up some nice。嗯。

Functions that help us in O Caml write things that look a little closer to assembly。 So， for example。

 we're using this2 to dollar sign。As a way of constructing an immediate argument of a literal is it kind of looks a little more like a assembly code where we're using a dollar sign in front of a literal。

But here， for example， is a data structure。That is an assembly program。So it's。嗯。

It's a record that has these two components， the text portion and the data portion。

The text portion is a list of。Labeled blocks。That is labeled instruction lists。 So here we see。

This is a constructor。Block for setting up one of these things。

So we're passing in the label name here， fo。 and here's a sequence of instructions， X or move。

 return。Here's another block called main Excelor moveve return。 Here's a data block。

EWith two labeled pieces of vder， bears and quacks。Bs is。EContains the literal 99。

Qus contains a string。 Hello world。嗯。We have a main program here that's simply going to。

Take that program， P 0 that I just showed you and print it out as a string。So， let's take a look。At呃。

Let's do this today。Great， so。We're just building this program。 And now if we run it。It was simply。

Take that assembly program and produce a nice string representation。Right。

 so let's take a look at the string representation。Of the program。

 this dot dot dot text here is indicating the beginning of a text segment。

Within that take segment are。These two labeled blocks。One labeled fo， one labeled main。

 each of them containing a few instructions。 instructions are nicely formatted。

 We've got the op code tabbed over to then the list of opera ends。

 So this is kind of a standard way of formatting assembly code。

The dot data indicates the start of a data section。This is indicating that the label Bs is global。

 meaning it can be accessed from other。From other object files， and。

We're saying it takes the quad value in 99。This is declaring quacks to be the string hello world and again。

 globally accessible。So one of the things we can actually do is take this assembly code。

And pass it to an asler。Right， and to guess。And then we can actually run it。Well。

 we need a little bit more support in order to run it。 I'll actually run a different program。

 which is maybe a bit more interesting。Let's go back to。

The 686 do M L file P1 is another example program。P 2。Is going compute factorial。

 So we'll take a look at this。嗯。P 2 actually takes an argument here in。

Which is what we're going compute the factorial of。 Note that this argument is an o camel argument。

And what we're doing is we're using in。Right here。So what this is doing。

 this notation is actually taking that function，$20 sign， constructing an immediate literal。

Passing in the Ocal integer in。嗯。And using that as one of the opera ends of move。

So this is essentially how we're going， you know， encode。Our argument。 So let's。

 we could do P 2 with， let's say，5。

![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_34.png)

嗯。

![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_36.png)

Can。不是呃。Do that again。And run it。And here's the program that does factorial。

 Here is the take section。 Heres the label。fact。Here is a label un school program。

Which is moving the literal5 into RDI。嗯。Moving one into R S I。

 which is gonna be the accumulator where we store the result and then calling T。Right。

 so it's calling the function fact。And then F is going to recursively。Compute the factorial。

It's going to take the argument。An R S I put in R X。 R SI here is the accumulator。

It's going to compare one to RDI。That is the thing we're competing factorial of。If it's equal。

That is， if we're compute factorial of one。We're all done。 So we're gonna jump。 If so。

 we're gonna jump to exit， which simply returns from the function。Otherwise。

 what we're gonna do is multiply。RD I。The number we're taking the factorial off with the accumulator。

We're going to decrement RDI。And we're going to call fact again。So that is， we're going to。

Compute the factorial of n -1， essentially。When we return from this call。

We simply fall through to the next instruction。 So we're going to return。Okay， so。Little hand wavy。

But hopefully， you can see how this really short segment of assembly code is computing the factorial of5。

Okay， if we start executing from here from under school program。嗯。

I've got another piece of code written in C， run time dot C。 Yeah， guess。Oh， sorry。

 I should have pointed out this。The dot the data segment is empty here。seeSo we have。

 we have the tick section。And the data section。 And but we don't have any label data in this。Oh。

 this is indicating that the label underscore program is globally accessible， globally available。

 So what that means is that we're gonna have some。Other code。

 this code here that I'm gonna look at runtime dot C。Which is going to invoke the function program。

Which。There's not worry about the details， but essentially。

 that's going to resolve to when that C code is compiled down into assembly code。

 It's going to be looking for the label underscore program。And， of course。

 that label underscore program is not gonna be defined inside the source file runtime dot C and so inside the object file runtime dot O。

But the linker and the loader are going to combine those things together and resolve it。

 And essentially， when the linker and loader is resolving these symbols， these labels。

It needs those labels to be marked as global in order to be used referenced elsewhere。Alright。

 let me check and use the make file。Yeah， so I have a make file that is。嗯。Going to。

Take that runtime dot C。And compile it。Into。Runtime dot S。

So this is the result of compiling that run tone dot C， run tone dot S。

You know that this is the main function。And we're not。

 we're not gonna worry about this for the moment。 But you'll see that in here。

 it's calling the program function。So if I jump back to runtime do C。You can see within Maine。

 it was calling program。I'll just note that when I use GCC to compile it。

 I'm actually running on an M1 chip。 Apple Sil。 It's actually based on the arm architecture。

 It's kind of Apple's minor customization of the arm architecture。So， but in this course。

 we're doing X 86， Intel X 86。 So I had to tell GCC that I wanted to produce X 86 code。

This is sometimes sometimes known as cross compilation。

 That is the machine that I'm doing the compiling on。

 I'm actually compiling it for a different platform， for a different architecture。Luckily。

 it's relatively straightforward to do with many compilers。

 And here you can see I simply did that by passing in。This flag here saying， GCC。

 please know that I want to compile for X 86。And then it turns out that the Apple computers are able to interpret X 86。

 X 86 machine code。With a， if you're interested in the technology they use is called Rosetta。

And it lets me essentially execute both arm code and X 86 code on the same machine。

Any questions at the moment Will I。jump through this。The， the call queue。Rose。どした。Yes。

 so remember that what call does， the Q suffix is talking about Quadword。

 So we're dealing with the Quadword registers。 But what call does is it pushes the current instruction pointer onto the stack and then jumps to the target。

就。Looking at the， you're not calling。So that's that what that's good like like。 No。

 it does actually call rent for every call， yeah。嗯。So what's what's happening is。

Make this a little bigger。So we enter the function。And then we say， was the argument equal to one。

 if it is， then we jump to here in return。If it isn't。We recursively call factorial。

 So if we were writing this in C， this would kind be like， if n is greater than one， then。嗯。

Return factorial of n -1。It's essentially what's going on here。

And then inside this invocation of call， thatll jump into here。嗯。问。

When this calls to factorial returns。We'll fall through to here， and we'll do a return。

So this does unwind the cool stack appropriately。I为操。You only exit。

So even though there's a label here。The order of the instructions is important， and。

The next instruction to execute after call Q， that is after the call lead returns。

 it falls through to the next assembly instruction， which is return。

So this is one of the key things that。These labeled blocks， they're actually in the list。

 and it's important they're in the list because thats actually gives you because some of the instructions will depend on falling through to the next instruction。

 which might be the first instruction of the next labeled block， as is the case here。Potentially opt。

Yes， we will talk much later in the course about optimizations。

 And this is what's known as a tail call。 The last instruction in this function is actually calling another function。

 So， yeah， we could be really sophisticated and save ourselves some stack overhead。

 So management of the stack。Yes， we could do that。Yeah， terms of his about the。

 I think his point was just every time。Call the call staff increases by bid。 we do affect。1表演。Yes。

 you might run out of memory。With this recursive call。 Yeah， was， was that your point， Sorry。

 that I misunderstood it。Question what is the no asynchronous and？

This is to produce simple assembly for purposes when。嗯。在。You might touch on it later in the course。

 but more complex control flow， for example， exceptions and exception handling。

 has some interesting data structures and produces some different assembly to handle those things correctly。

 So my recollection is no unsynchronous on one tables is really about don't bother producing the data structures to unwind the stack in a asynchronous way。

 But somebody who is more of a lower level person。Dren， feel free to correct me。O。

 basically do no compile basically just produce a very simple， this is the minus00。

 minus00 is the no optimizations。Optimisation level 0， the un synchronous。

 no unynchronous on wine tables is， I think， related to exception handling。嗯。

But feel free to post on Ed and myself or somebody in the class run the course staff can can give you a more definitive answer。

Okay。Let me just呃。So what we're gonna， what we've done now is taken the output of our。

O camera we representation of assembly program。 We printed that out to assembly。

 and we actually put that into the file， Prog dot S。We compiled runtime dot C to runtime dot S。

And now with this command， we actually got GCC to link them together。

 GCC is kind of smart enough to know based on the files that are coming in。

 which thing it should invoke。 So here it's taking in these two assembly files It's giving them to the asmbler G A S to turn them into machine code to object files and then invoking the linker and loader to combine those object files into an executable。

 And that executable is。Progue， so we're going run Prague。And we get  a and 20 factorial 5， hooray。😊。

So， we went from。An o cameral representation。Of a program， the computes factorial。

Combined with some handy C code to print out the result nicely。And actually。

 we were able to execute it on this machine。Cool。Any questions。8pe。

What is this main mangling with the underscore instead of math？No， that's a C。Specific thing。对。

I guess say gender to disagree， gender speaking。 doesn't make all names， so。Why。

But I wonder if it's cross calculation。I don't think it's。

 I don't think it's a cross compilation issue。Last time I taught the course I had an until machine。

 I did not change the code except for adding that architecture flag。Hm。😔，Good question。呃。

I think in general， one of the things you'll find is that there's often a lot of convention involved with with compilation。

 one， of course， just being how you use the machine。

There's no reason you have to use a stack and a heap。In X 86 machine， some early languages did not。

 Some early languages did not allow recursive functions， did not allow dynamically allocated memory。

 But most languages these days use that structure。 there's this issue about compatibility between pieces of code that are compiled separately within the same language and in different languages。

 So most。Practical languages you want both separate compilation。 I want to be able to compile。

 let's say， a C program food do C by itself into an object file。

 later on compile something else and have them work together。 And that means we need conventions。

 we need standards for for example， which labels we're going to use when at the C level we refer to a function or to a or to a global variable how does that get translated to assembly code。

 We have similar issues when we want interoperability between languages。

 Most practical languages have some mechanism to do external calls to somehow invoke a foreign function interface。

 So， for example， an Ocal， you can invoke C code。You need to be a little careful about it。

 You can generate your Ocal code so it can be invoked by C code。And so on。

 And most languages want to do this for a variety of reasons， maybe because。

The only code base that makes effective use of a GPU is written in C。

 And so in Python and you're writing a code in Python， you want to use that effective GPU code。

 You need to be able to invoke C code。 So these issues of name mangling are kind of one of the details that have to be sorted out and sorted out carefully we' not gonna talk about a much。

 But But it will say they're the kind of conventions that kind of need to be agreed on and can get into the details。

 Again， feel free to post on it。 I think this would be interesting to dig into why in this example we are saying it I don't know if it's a Mac thing。

I using by。I'm using this。So I don't know how much of the system 5 API is。Is being used here。嗯。



![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_38.png)

Right。This is pretty much stuff we've covered。As weve walked through this。u。

This is kind of just recapping thus， the code and data segments that or text there should be on the code part。

嗯。嗯，Just in terms of layout。

![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_40.png)

Typically， the code and data go on the low memory addresses and the heap grows upwards from there。

 Sta starts off and the high memory addresses grows downwards。



![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_42.png)

嗯。As we talked about stack being used to store local variables for a function and vacation and the return address of a function so that we can return from the function call。

 and as I was mentioning， most languages end up using this model of heap and stack to to do things。

 and as a result， this is。The architecture is kind of optimized for this idiom。

But about 10 minutes left。跟那。Let me do a quick walk through of。Essentially， it's stack。 Yeah， okay。

Want to be working。It just。嗯。You will be writing programs that can use the he。

 but you're not going to be implementing runtime heat management。

 So we'll just be using essentially an external call。To to allocate memory for us and， and free it。

And that's pretty common， most。呃。Some languages do write their own heat manager。

 The Ocal one is actually pretty interesting。 We'll touch on some of the details of the Ocal heat management system。

Later on in the course。Have。😔，All right。I think we're pretty comfortable with this idea from 61。

 that。When we need， we need to store stuff as our program executes。

 some of these are global variables。 Some of these are arguments， past to procedures。

 Some of these are local variables used by a particular function ofvocation。

 and each invocation of the function will need its own copy of those variables。K。

wing the machine itself。The kinds of locations that we have available to us are on the whole registers。

There's a small number of them， but they're really fast。Or memory。

 which we have a lot of memory locations。 as you can see。

 these are some slides from 32 bit days where memory is large but slow。 And then of course。

 there's a whole lot of things going on in an architecture to try and alleviate the slowness of accessing memory through caching in various ways。

😊，嗯。In order to。Insantiate this idea that we need to pass arguments into functions and functions need to be able to have copies of local variables in order to perform their computation。

 that we have calling conventions that is ways that we。

Cons for specifying the locations of arguments when we invoke a function and forgett the values returned by a function。

嗯。Did you cover a callee and caller save registeristers in 61。Nots fantastic。 So， you know。

 that registers are either a designated caller save。 That is。

 if the coreer wants to preserve the values in them。

 they're responsible for saving the value of that register away before invoking a call and call save。

😊，That if the， that the callee must make sure that the value in that register is restored by the time it returns。

 meaning if it wants to use it， it has to save it away。嗯。呃。

And then the calling convention about how to manipulate the stack。

 how to make sure that the stack is appropriately managed。

 can be either cooler cleans up or coolly cleans up。嗯。Advantages and disadvantages to both。But。

Pointing out that with the coreley cleaning up， if your function has a variable number of arguments。

 it might be a little harder for the callley to say。

 remove those that argument build area off the stack。嗯。So for 32 but X 86。

 here are some of the calling conventions。So呃。What are the useful ones to talk and do your argument order on the stack。

 You typically do it。 You're building the arguments from right to left on the stack。

 Some of the arguments are gonna be passed in registers。诶。

But if there's more than fit in the registers， then they're going be on the stack。Way。

 right to left order。不能。ItStacked backwards， but it could still go left to right。But it's like。

If you push down。Rightrite to math。It's like a first。O。So why is that useful。

 So why is it useful that by the time we invoke the core Lee。

The thing at the top of the stack is the first argument to the function， because in some ways。

 it's counterintuitive for the chore。 It means the corere。嗯。Might end up evaluating the arguments。

In the reverse order than you'd expect， right， that they evaluate the last argument first so they can push it on the stack。

 then the second last push on the stack and so on。 So what's the advantage。

Of when the core Lee is invoked， the first argument is at the top of the stack。而且这是每个。

There is actually a reason why it's， why it's useful to anyone medicine。顔にそす。So。Thection。

Do you mean that the core Lee is able to add more variables。This， that's not the reason。

That's not the reason why we typically do the right to left order of arguments。

 The stack will grow downwards。 But I think if you had the arguments in the other order。

 you'd still be growing downwards with your local variables。Pa。So see。在。前の。

Its either has the length first or terminated by no point here， but either way。

The thing is that the caller knows how many that's passing。

 so it can do whatever fianglo needs to do， but the col is like that a lot more to figure around。

 that's exactly right。A number of languages， including C。

 You can evoke functions with a variable number of arguments。And so what that means is the core Lee。

Would typically not know a priorityi how many arguments there are on the stack。

The way that these functions are typically written is that the first few arguments。

Indicate in some way how many more arguments there are。

 or it might be an no terminated list or something like that。 But a common way to do it is。

 for example， with print F。Right， the first argument is a string。

And that string contains placeholders where you're going to replace values。

 And you should have one argument for each placeholder value that's going to be replaced。

So what this means is that the implementation of printf can take its first argument， the string。

Start going through that first argument。 Hey， I've got a percent S。

 I know that means I'm gonna have a point to string。 Then go to the stack and get the next argument。

No， the。Keep on going through the string。 Oh， I need an integer here that I'm gonna format on this way。

 Take the next argument。And so a lot of the time when you have these variable argument lengths。

 often it's the first arguments that are indicating how many arguments there are or telling the call how many it's going to consume。

 And that right to left order is well aligned with that otherwise。

It would be more complicated or more burdensome or more overheads for the caller to communicate to the callee。

 How many arguments there are。嗯。I've got some slides that you can look at to refresh you on stack frames。

I'm not gonna go over them in detail here， but here are some example code showing four functions that are invoking each other。

 one of them recursively and just kind of talking through how we end up manipulating the stack frames using these two pointers。

 the base pointer to the stack frame and the stack frame and 32 bit it's the register EP in 64 buts RSP。

 but that year is the same between the base pointer and the stack pointer is the current frame。

 And as we end up invoking functions。We add stack frames， stack growing downwards here。

 When we return from a function， we're popping it off。And then， of course。

 we get to reuse portions of the stack。 If we return from one function and call another。

 we're using the same addresses for a new stack frame。测完。Cool。Sorry， let me go back。

 And so this is a。Just refreshing you on what a stack frame layout is like。嗯。

So you can think about it as between EBP， the base pointer and EP， the stack pointer。

 This is our current stack frame。 and we have。嗯。

![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_44.png)

Just above EBP， we have the return address。Right， so that was pushed there by a call instruction。

And above that， we have the argument built。 So the arguments that the caller is passing to the cally。



![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_46.png)

The way that the co is implemented， they typically push the old base pointer onto the stack。

And update the base pointer to establish a new stack frame。

 they might save away some registers for the core save registers that they want to save away。

 And then if they have more local variables that can fit into the registers they're using。

 they might be using some of the stack to store local variables that it needs to access。

Right so that's the saved registers plus local variables。



![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_48.png)

And then if this function， if this stack frame wants to。



![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_50.png)

Invoker call Lee。It would construct the arguments for the cally。Getting ready to make a call。嗯。

I'm not gonna talk through the， the function call and the function return。嗯。

These are familiar from 61。 You can look through these。This slowly different for 64， B。

But I don't get around to updating my slides。呃。And we can take a look at some 32 B X 86 code that implements。

嗯。呃。These functions implements a function call here。嗯。And how it operates。

 pushing on arguments onto the stack and right to left order， Per the call。

 which pushes the return address on。And so invoking the k Lee。Right。

 with the first part of the assembly code of the call E。Setting up the stack frame。

 pushing the old DBP。啊。Updating UBP at EP。Pushing a cool save register。Performing the computation。呃。

And then cleaning up at the end of the function andvocation。 So that is restoring。

The call needs have register。Restoring the old stack frame。And then。performingerform a return。

And here's a handy little cheat sheet that shows kind of stack frames of the caller callley。

 And if the callley were setting up to call another function。 Again， this is 32， but。

 but the the concepts are are pretty similar。 and then。呃，合同表的呃。System 5， AM D，64 B A BI。Essentially。

 theyre calling in conventions for X 86。This is some of them。 They're not quite all of them。

 Some of them we're going to be ignoring in this class as much as we can， for example。

 making sure stack frames are suitably aligned at addresses is something well try and gloss over。

And the。We won't really be digging into this red zone that is allowing a function to write over pieces of memory freely without needing to modify the the stack pointer。

Okay， there was a bit of a very quick recap over the， the structure of the stack frame。

 Please feel free to post on it。 If you have questions， review your 61 notes if that's helpful and。

Yes， you'll end up getting much more familiar with it over the next couple of assignments。

Any questions before we wrap up。Yeah， well。 So Windows is listed here。

So with the program that you compiled。worth。Good question。 I don't actually know。

haven't used Windows for a long time。If anyone is going through this class using Windows。

 feel free to reach out to core staff。 If you have any trouble setting things up。

 sometimes the setup of these lower level tools can be a bit challenging on a Windows system。

Thanks so much， everyone。 Please remember to fill in the form。

 student info form and the study group survey form。 and I will catch you all on Monday。😊。



![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_52.png)

し加。Yeah correct extension。Yeah， I question sure。最所。しさ。はいください。かわなん。rights。嗯 yeah。は没。でまわ。系啲样。

And this is a variety。Linux， I guess I should be more specific doesn to vary。So。Iす。所い感じだ。我せ。十分。さすが。

Micro。Guarantees most。Thereoom plus parts by。对，ぱよか。さ。好那。今。



![](img/73f6ec77e7f9e91311fa53aa2a02f1a6_54.png)