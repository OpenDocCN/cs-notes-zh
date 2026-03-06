# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p25 P25 Compiler implementation： Pointer assignment (COP-3402 Fall 2024) -BV1v6vdBKEHB_p25-

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_0.png)

All right， welcome back to System softwareware， so today is the last lecture of the main content of the course we're going to be finishing up the compiler implementation。

And finishing up how we can implement pointers， how we compile code that uses pointers。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_2.png)

So last time if remember， we went over。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_4.png)

Poiner operations and simple IR， they're really just the same as C。

Where we have reference dereference and assignment to a dereference variable。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_6.png)

Questions on the semantics of simple I， questions on the meaning of these。

 I think everyone has seen this in C already。 It has the same semantics， but any questions。

On the meaning of these operations， the IR operations， yeah。Yeah。Yeah。すい。In this stack frame。

 you're saying RVP doesn't have a value。So is RBP in memory or is RBP a register？It's a register。

 yeah， so how is the RVP register assigned and maintained？Who sets RBP？what's that？Well。

 the compiler generates code and what code does it generate to set RBP， When does RBP get assigned？

In the code you generate。Yeah。icular嗰方面。Yeah， well in the function prologue， well。

 it's not the caller， it's the call E that does it。And it's the prologue code， the prolo code assign。

RBP。So this prologue code， this is where RBP actually gets assigned。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_8.png)

So remember， RBP， as long as you've implemented the calling convention correctly。

 RBP will always hold。A pointer to the stack frame。

So you can think of this as an invariant at any point in the program。

 RBP holds a pointer to the stack frame and because the compiler ensures that invariant that condition always holds。

 whenever you generate code， you can always rely on RBP holding a pointer to the stack frame。

That's how all of this pointer stuff will work。嗯。Not explicitly in the language。

But remember strings and characters， those are just so strings are just arrays of characters and characters are just numbers。

 so I mean characters are like eight bit， yeah one byte numbers。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_10.png)

So you'd have to do some cleverness to， Yeah， you'd have to decide on whether you want to put 8 B in every 64 B integer and make an array that way。

 But I actually have an example。 I didn't I didn't go too much into the。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_12.png)

Examples， so I gave you some examples， these are more for like complete compilers。

 these are more for me when I was writing the compiler to Health like。Work out the whole thing。

And I ended up giving you sort of more micro tests for each piece of the compiler。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_14.png)

But we can actually call Malik from。IR。Like this。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_16.png)

And you get a pointer， what is Malik return， Malik returns a pointer， so now x is a pointer。

 and I can play with that pointer， I can add to it。

 like it subtract from it just like any other number。了。I mean。

 you can call the reallic function if you want， is reallicica function or is it a macro。

 and it's probably a function。 Yeah， whatever C function you want to call it is because we follow the。

The system5 application binary interface， we can call functions and get their return values。

Yeah you could call free passing passing the parameter now there are issues with data types you there you'll have problems passing parameters of the right data type。

 so it probably it won't work perfectly with C because of data type widths。But you could。

 you know an assembly， for instance， an assembly， can you work with strengths and characters？Yes。

 right there's no types， but you can work with them because it's just binary data and as long as you can access sort of arbitrary memory using pointers than you can do。

Mostly what you can do in NC。Okay。All right， other questions on。Anything from last time？So just。

 yeah， just， yeah， yeah。Okay， sure， let's see， what did I ask？

IfThe variable x has an offset of negative 24 from the base pointer。

 write x 8664 time code that will result in the address of x being stored in register。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_18.png)

All right， X。Okay， so。Let's look to this example actually have that， so here is。

 I think it was just taken from the example we had yesterday。嗯。

So here is a stack frame for a call to some function doesn't really matter what the function is。

 and you can see that x has offset negative 24 from RVP。Questions on this set up。

So we saw this like pretty much every lecture for the past like several weeks。

 this is the stack frame， RBP holds the address pointing to the stack frame that is pointing to this entry。

And with our compiler， we map each local variable to an entry in the stack frame。

And because we don't know where the stack frame will be the actual address of the stack frame at runtime where we don't have to know。

 it's going to be an RVP， we access variables using what， how do we access variables from RBP？Yeah。

 we use this offset from RVP and there's this。There's this。Syntax in the。嗯。Intel world。

For doing exactly that。 So what does in the context of this function。

 which define these local variables。What does this assembly operation do？Right， access is88。

 why does it access eight？Yeah， exactly， so this is saying take whatever the value of RVP is。

 which is 80。And that value， because of the calling convention， holds a pointer to the stack frame。

And then subtract 24 from it。So you get。56。And get whatever value at memory there is load that value for memory。

 So this is like an indirect load or a load。From memory where you specify the memory address in a register instead of hard coding the actual address。

And it stores that value into the RAX register questions on that。对。に入れ。やな。Instruction stop。問題を疑問する。

I don't know MIPS， so I guess would it take a register？And that register would hold D。Address。

 door out。I don't， I don't know if I just know the Intel world。

 but I'm sure you can do the same thing， probably with several instructions。In the myth， yeah。

Well they哋 homework。For the。Ah yes， so this is an answer in homework。

 this is just making sure you understand this。So the Homer question was。

If the variable x is offset negative of 24， so this is how you would access the value of x。

How do we get the address of X and store that in RX so this doesn't do that， this store is8。In RAX。

But what we really want to do is get， what's the address of x 56， 56 stored？Did X。Yeah。していただ丈。Okay。

なて。えチ？Did I have T1。 So I just stopped it just to put it in RX。

 So you're moving on to the full instruction， which is good。

 So just to reiterate what your classmate said。We sorry， not RBX， we take。

 so instead of asking Intel to the processor to load from memory， the address given by RVP minus 24。

We want what that address is， so internally the process is computing that。

 but this instruction is just going to do a load from that address。

 we want the actual address itself。And that's not stored anywhere explicitly。

 but we can compute it in the same way that we know that we can use an offset from RVP to access。

The value of x。We can use that same information to compute the address of X。So to do that。

 we take RBP and move it into some register。And then we add the offset from RVP for x to RAX。呃，这。

You're done。 You've solved the homework。So what's that。Yeah。

 that's how you compute the address of a variable。In assembly or generate code to do it。

An assembly for any stack frame layout or for any stack frame position in memory， yeah。Okay。

 so let's so we have a question。So what happens if we instead of so like this， right， de referenced。

RVP。In this example， what would RAX hold at this point？8。Okay， so we have a couple of questions。

 we have 80。Old RVP。Who says RBP or the value of RBP？Who says old RVP， good， it's old RVP。

So remember， in this example when we did move RVP to RAX。This copied our thisied the value oh sorry。

 this copied the value。That RVP， so remember， RVP is a register， not not memory， so registers。

They're just named and they hold 64 bit data。So the value of RVP is 80。

So when you copy the value of RBP into RAX， RAX is now 80。

If you do an indirect copy that is you load whatever the address of our that RBP holds。

 you load its that value and memory， you're going to get whatever the old RBP is into RAX。

 does that answer your question？

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_20.png)

Questions on that。The difference， so these parentheses in assembly really is like dereference。

 dereference of a register。So you either have the register value itself。

Or the value of memory that the register points to。So this is what makes RVP a pointer。

 the fact that you look up。It's you do a load from the address that that register holds。

So remember whether it's an address or an integer or a character。

 the machine has no built in representation that records whether something has specific data type。

 that's all kind of an artifice created by the programming language。Instead。

 it's whatever instruction you give to the machine， that instruction will interpret。

The value is being an address or an integer。There's no characters or strings at the machine level either。

 characters are also just numbers。Yeah。If you could friends。不高。我不大け。

Do you mean you kind of do like a double parentheses？But again， subscribescribe again。Like this。

 like two sets of parentheses。Like doing this。I don't think I don't think so， I think yeah。

 I don't think the processor has supports that， you'd have to first。

 that would be like a double pointer， right？You'd have to just do each pointer operation separately so you have to put that in RX and then do another。

Like offset from whatever RAX is。Id， I don't think you can do both of this。But yeah。

 good question This would be like basically saying RAX is an array or if x。

If x is at negative 24 and your language has some operation to access index 18 from or index negative 18 from that variable。

 that's how array indices work。Aray and remember arrays are really just pointers。And when like in。

See， if you were to say。Give me the negative 18th well。It's a little different， because the。This is。

 well， okay， so let me give an example that's separate from the assembly one， but when you say x。

 give me the second index of x， so first of all， which which element is this。Yeah。

It's a third element， so what's really going on and what you could actually just trans basically translate this to is x plus2。

Dreference。It's the same thing。And translating this to our offset level。

 this is where data types come in。 This is really like。呃。the offset in bytes is however wide x is。

 so if it's an integer on a 64 bit machine。This。X offset is 64。呃。Okay， now I'm confusing myself。

 64 bits right or two bytes， no， what am I saying here？So each character is four bytes。

 so this would be four times two。8 bys。So you would do eight。Offset from RAX。Assuming REX holds。The。

 the。あ。The value of x， which is was importanter。Anyway， what's that。Whatever。はいそうすて。Yeah。

 I think even， the point arithmictata that as well。

 it multiplies it by the Bi width or the by width of the data type。

So that's where it does differ a little from assembly where assembly you're dealing with byad addressing。

And in C， they're using the data type， the width of the data type， but anyway。

Don't worry about this too much。 You don't have to worry about this。 If you want to like。

 as a bonus project， implement， say， an array index in simple IR。

 you could do that or implement a compiler from。Another language， too。Simple IR that uses a andice。

 you could do that as well。But this is a good。呃。Transformation to keep in mind about what's really happening with a arrays。

 they're really just a syntactic sugar forer pointer manipulation。这に。グ？じ0。I think you probably could。

 the type checker may complain。Actually， yeah， I think you can do that。

 I depends on what the C type trackcker does。 I can't remember if it'll， It might warn you and say。

 hey， you didn't declare this as an array。But technically， yeah， yeah you could totally do that。

 you could take any pointer and access it。Using array syntax。Modern compilers may complain to you。

 especially if there's a strict checking turn on， but yeah， yeah， you can do that。

The converse is true or the inverse is true here。All right， so any other questions on homework 21。

 this is the answer to homework 21 just to be clear， I know we went on a lot of tangents。

 but this is the answer too。Homework 21。You just generate assembly code that does the computation of the address from RVP and the offset。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_22.png)

That's the last homework， so I asked the grader to just give everyone credit for。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_24.png)

22， 23 and 24 because I really wanted the homeworks to like be one point each。

 but you all just get free credit for。22， 23 and 24， we lost those days。Okay。

 and that was the that was the first step in getting the or implementing the。Reference instruction。

 So to get the reference in order to。Get a reference to X。

 We need to figure out what its address is to figure out its address。 We generate code。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_26.png)

That。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_28.png)

Compututes RVP plus whatever its offset is。And then as your fellow classmate pointed out。

The rest of the instruction semantics is to save that address into whatever the lefthand side variable is T1 in this case。

 and so that just works like any other assignment where we store the value into the address associated with T1。

Questions are没。And then dereencing use this。So this is what I think someone else is asking about。

This parenthesesis syntax without an offset will just be effectively offset of0。

 as somebody pointed out， and this will load the。Memory at the address given by RAX。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_30.png)

So this assembly instruction is how we're going to implement dereence。

 so T2 equals the dereence of T1。So without any data types。

 there's nothing enforcing that T1 is a valid address。But just like an assembly。

This is going to assume that T1 is an address and try to dereference it。

 try to load the value at that address。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_32.png)

And just as a refresher， I think I did this at the very end， so let me go over this again。

 So this is the same stack frame that we have before。We're doing T2 equals star T1。

So we're trying to assign T2。To not the value of T1， but the value that T1 points to。

It happens to point to X， but there's nothing explicit that says that it just has an address in this field。

So the assembly to do that is to first。And let me write down again。What these steps look like？

So the first instruction is to move。Negative， actually， let me just， let me do it this way。

Since my writing is very bad。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_34.png)

So this is trying to compile。This instruction。So T1 is here， T2 is here。

When we do move negative 40 RVP， so what variable corresponds to negative 40 RVP？This is T1。

And we move the address or the value。The value。This is 56， so this is。After this happens， RAX holds。

The value 56 questions on that。This is the regular store a load of a variable that we've。

That we've used before for like enter assignign。In this instruction。

 this doesn't take the value of RAX， but it uses RAX as an address and does a load from memory。

That's what。That's the D reference， that's the D reference。

 so it takes whatever value RAX has in this case， 56。And it。

Uses that address to do a load for memory at address 56， so what's at address 56？The value A。

So after you run this instruction。R BX hold8。So we store whatever value is at the address given by RX and RBX。

That address is just whatever the value of T1 was， because that's what a pointer is。

 pointer is just a regular variable that happens to hold an address or happens to hold a number that will be interpreted as an address。

All right， and then finally we take whatever RBX is and we store it here。

 so what variable does this correspond to？Yeah， T2， so this is T2 T2 has negative 48 offset。

 and then after I run this store， this move。How will the state of registers and or memory change or not change？

What won't change or what will change。 Let's start with what will change。

 What will change in this whole picture。月三年。能啲 two become。So effectively T2， but what is so yeah。

 so we said that this is T2。So what， okay T2 becomes8， but how does the memory or registers change？

So yeah， we know semantically T2 is supposed to come8， but there's no notion of T2。

At the machine level。Yeah。P I think doing just。When那个。Yeah， yeah。

 so maybe I'm splitting hairs a little bit。But my point is that it's not T2 that gets changed。

It's this entry， this， this address 32 that gets changed。 Now， at the compiler in the compiler， we。

 we correlate or we make a mapping from T2 to that address。

 And then I'm splitting heres a little bit。 But the state of this machine changing is not T2 because there's nothing in the machine that corresponds to T2 at the assembly level。

 It's this space。In memory that now changes， so this instruction takes whatever's in RVX。

 which is eight right now。And it loads it into this memory address given by RVP minus 48。Which is 32。

 so RBP is 80。Minus 48。Is 32。 So this is the address that gets loaded。And this now becomes eight。

So sorryrry for splitting heres a little， but I just wanted to make it clear that the assembly level the only things you can change are registers and memory besides IO。

 but the code that we generate， we're just kind of be changing the state of memory。And registers。

So now， yeah， so the address。And so just to violate my own splitting hairs， T2 will now equal8。

 but it's really the address address 32。I don't how to say this。32。In memory。Now equals8。

Questions on this。Yeah， so at least for the sake of this clause， it only other stores and dresses。

We all start everything else。Yeah， yeah， basically， yeah， I mean， addresses our values， but yeah。

 in terms of the semantics of the language， we only have 64 bit integers。And addresses。

 those are the only data types。That we're dealing with， but remember。

Everything in the machine is just integers or binary data。

 and all kinds of data can be represented with those bits。

 so the notion of types in the programming language，Is not physically embodied in the machine。

Like in a kind of strict sense， but you can always encode。

Data just like when you download a picture or listen to music。

 that's all being encoded as binary data。And your programming language doesn't probably doesn't know about。

 say， bitmap images or。You know， music data， but you can still process it with an algorithm to interpret it as that kind of data。

All right questions on。This。So it's just like an assign between T1 and T2 except。

We take the value of T1 and first。Do an indirect lookup。

 we do a load from that address that T1 has and then store it into the left hand side T2。

What will happen if you were break to do an instruction？This is RBX。Because that is out of。

Out of the stack， so you'll just do a lookup into some memory location。

That some other memory location， so it's the same question as like what happens if I get do an out of bounds access of an array？

If that memory space is accessible， you'll just get that value。

You'll get the value of that memory location。So for instance， like yeah， maybe it was address 100。

Or you you know， I mean， you could write in simple IR if you wanted， you could say。T1 equals 100。

 and then you could just dereference it if you like， just like in C， you can do the same thing。

And you'll just get 100 will probably give you a siteych fault because I don't think the OS or the kernel will allow your process to access memory there or if you're trying to write it。

 you'll be able to read it。Actually， even maybe not。But it'll just literally do what you ask。

 it'll dereference that memory address and get whatever value is there。

There are protections in the hardware level to prevent you from accessing certain memory addresses。

But without that， you'll just access that memory。So this is exactly what happens when you have like a buffer overflow。

In sea or， when you access an array out of bounds。Most compilers are not going to stop you because it's very hard to check that。

At compile time。And then the seed language technically calls this undefined behavior。

Which means the compiler is free to do whatever it wants。

And it usually does the easiest thing for the compiler。And it's really supposed to be on you。

 the developer did not do that， but what'll end up happening for most compilers is it'll just access data out of the bounds of that。

Of that array， and it may end up being data from another array and may be unallocated data。

And then your program won't behave as you expect because you weren't supposed to do that。

 it'll change， it might change behavior every time you run it or it may give you unexpected behavior。

Yeah。Do them like the first。These two lines， the second one。倒れたい。まいいだ。

So let's do the version where you don't dereference it。

 let's see what happens to when you don't dereence it。 So the first step is the same。 R X equals 56。

And with the dereference， RBX equal to 8， what would RBX equal instead？When you move RAX to RBx。

 RAX is 56， what will RBX be now？56 right so if RAX is 56 and you move RAX to RBX。RBX is now 56。

So that's。Here， that's like this address。 but we're not dereencing it。And then。How will this change？

We RBX is 56。 so now what will。The memory address associated with T2 Yeah， it'll be 56。

 so this will be assigned to 56。 Does does that make sense？

So we're just copying the value of T1 instead of。Going to the memory address that it points to。Okay。

 so that's a review from last time and I know actually at the end of class。

 I guess I sort of quickly went through the rest of that。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_36.png)

Do you referencing a pointer？So now let's look at。Assigning。To a pointer。Let me get the。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_38.png)

So let's look a pointer assignment。So in this case， we're not loading from a pointer。

 we're storing to a pointer， we're storing to the dereenced。Address of a pointer。

So the advantage of this is T1 is expected to be an address or it was treated as an address。

And we take whatever the value the right hand side is， and we store it at the address given by T1。

 we don't store it in the stack frame。Location associated with T1。

 but we take whatever the value of T1 is。And go to that address and store the right hand side。

Questions on this。Okay， so this is our same program。Just to refresh you， we have x equals 8。

 y equals9。We get the address of x stored in T1。 so remember T1 now holds the address of x。

 not the value of x， the address of x in our。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_40.png)

In our machine here， T1 holds 56 because that's the address of x。

And then we assign the dereference of T1， which is8， and we assign that to T2。

And then the next instruction is to take。Is to assign to the pointer。

 the address that T1 points to assign 11 to it。So how will this picture change after？The instruction。

 star T1 equals 11 yeah。Yeah。80。WhatWhat sets RVP？要不知。No， who sets RVP？The callee， yeah。

 the callee sets it every time， so this is an example of what RBP might be at runtime。

The code we generate is independent of what value RVP is， the actual value of RVP。

 but this is a snapshot of a single call。To the first。I made it up。

 I made up 80 for this particular call to have a concrete number。Right， right， right。

 so after we do star T1。Do an assignment to the de referenceence of T1， assign it to 11 how will。

This picture change， how will the stack frame change？なこのメジゃソしと。TheSo。

So you're saying the negative 40 offset of。So why negative 40？Becauseさ。没 just说去。

So you're saying this will change to 11。What if I have， say？Okay， okay， good。 Yeah。

 So if I said T1 equals 11。Then this slot would change to 11。Star T1。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_42.png)

Right， so it takes the address that's at T1 and stores whatever value we gave it。At that address。

So T1 holds address 56。So we do a de referenceence assignment that's going to store not overriding T1's address。

 but overwriting whatever address that T1 has。T1's address is 56， which is here。

So that's going to update this value。That's going to update this value。2。11。Questions on this。

 questions on this。Behavior。And then I guess just to finish it out， when we say T3 equals x。

What's the value， how's this going to change yet？Second， second。I set 1 more construction。

Right exactly so 11 will be stored at the memoryory address associated with T3。

 so this is how normal assignment works， non point assignment works。

And notice that we never reassigned x here， this is what pointers the consequence of pointers。

 we never reassigned x explicitly。But because we had a pointer to its address。

 we could reassign x's actual value， the value of the meist address associated with x。

 we could reassign it through that pointer。Which is why assigning。X to T3 now makes T311 and not 8。

As it might look。By looking kind of sort of。Niveively at the code。Questions， questions on this， yeah。

Our values so and。So if you sees 11， how does know that that's not an interesting pointing to？



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_44.png)

It doesn't， it doesn't， so if we had then written another instruction。Like。Star。T3。Equals x。

Then the machine would take 11， go to that memory address。And store to it。

And so without memory protections， I mean this is because you as the programmer like an assembly。

 are free to read and write for memory locations as you like。

 this is the process model that you have your own address space and you can read and write data however you like。

Poiners are just a kind of a data type。For us to help us recognize the difference between those two。

Rather than at the assembly level， you'd have to use either a straight up register copy or a load or an indirect load from a register。

You know you can think of these data types as sort of translating into assembly operations。

 different assembly operations， does that answer your question？🤧Okay。

 so that's the behavior of doing this dereference assignment。In simple IR。

 so let's see how to do this in the assembly level。Okay。

 so what assembly instruction can store a value？To an address。

So we saw when we did the dereference load， how to load from an idea。

 how can we do and how can we store to an address？E records。Well yeah， we'll do that。

 but how would we do the store， how would the store， how would we do this update？

T2 or wait which update I'm confusing myself here， Yeah how would we do this？This update。

So it turns out it's the same thing。That we saw when loading。From a dereenced pointer。But we just。

Put it in the destination opera。 so you can use the same syntax， the same operation syntax。

In assembly。 But instead of loading from an indirect register address。

 we store to the indirect which address。 Yeah， yeah， you just store。

To the dereferenced address instead of loading from the dereence address。So this is kind of a。

Easy part of assembly， but Intel assembly， but also the kind of confusing part is that all of these move operations look really similar syntactically。

 but sometimes they're doing a register copy， sometimes they're doing a memory load。

 sometimes they're doing a memory store， sometimes they're doing some offset loads in stores for you。

But if you just remember that when you put parentheses around a register。

 it means do a load or a store。At the address given by the register。

Then hopefully remember that as long as you remember the right second opera is destination。

 this is doing the reference assigned。If we're on this side， it would be the dereference load。で。Yeah。

 yeah， assuming it already guilty the address， so knowing this instruction now that's let's actually build。

Ascetic sequences of instructions that will implement。This simple IR instruction for us。 So we'll。

 we， yeah， we'll want to。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_46.png)

Get the value that we want to store into RBX。And get the address that we want to store to in RAX and then do the move。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_48.png)

All right， let's so this is。I thought I updated this， but I didn't。 so let's just。

 let's just go through the。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_50.png)

Let's go through it。Yeah， no， let's just go through it。Okay。So just like before。

We get the value of T1。And save it into an address， or save it into a register。

 so now RAX holds the address or holds the value of T1。It the value of  T1， just like any assignment。

Anytime we want to get the value of a variable。This is how we do it in。In the Intel assembly world。

 so just a quick refresher， what does this negative 40 mean， why is it negative 40？Yeah。

 it's the offset for T1。In our symbol table。And at runtime， that's going to be。

The offset from RVP that will hold the stack frame entry4 that we'll use for T1。Okay。

And then so the order doesn't really matter between these two instructions。

And this is the way I wrote my compiler。Here I'm storing the value。

 the right hand side value into RBX。You could certainly do an immediate load or immediate store if you wanted。

 you could reduce the number of operations or swap these arounds。

 this is how I wrote my compiler to do it。So now we've got RAX holding the value of T1。

Which is the left hand side variable name， and we have RBx holding。The value of the right hand side。

 which is 11。All good on this， questions on the state of the machine right now。

RAX holds the value of T1。RBX holds 11。And now this is where we use that indirect store。

We're not copying。11 to the entry of T1 to that stack frame。

We're copying it to whatever the address T1 had， so this is whatever REX its address。Store。

The value of RBX to RAX， the address RAX。All right， let's take a look at this in our。In our machine。

 so let me。Put the state back to where it was before he ran this instruction。呃。

Can anyone not read this？Is this too small。Just one， okay， let me。Put it here。全部から。Okay。

 so here's our assembly。Here's the state of our machine。All right， so negative 40 RVP。

 which memory address does this correspond to？T1， this while it's right here negative 40 here or 40。

 it's actually 40， just so happens that because RVP is 80 and we subtract 40。

 it's actually memory address 40。All right， so now what's the value of RAX？

Looking at this state of memory， what's the value of RAX after yeah？Yeah， what's up？

So it is the memory address of X， but nothing in the machine knows this， we know it。

But just looking at the。State of a machine。Because this。Corresponds to address 40 here。

This is the offset for T1。This move instruction loads whatever the value in address 40 is and loads it into RAX。

 so the value here at address 40 is 56。So this 40 is。80 minus 40， that's why it's 40。

So now RAX holds 56。And for this instruction， what does R BX hold？11， yeah， it holds 11。All right。

 question so far here。So we've set up or two temporary registers for ourselves RAX。

 which holds the value of T1。And RBX， which holds。The right hand side of our instructions。

 So remember， we are trying to。Compile。This instruction。So this is。Getting the value。Of T1。First。

 not star T1， but T1。And getting the value of 11， the right hand side。

And now this is where all the dereference magic happens。Remember， RBX is 11 here。RAX is 56。

So how does the state of the machine change， either registers or memory。

 how does the state of the machine change when we do move RBX to parentheses， RX？Yeah， up there。

Secondga。So how does the state of issue， so tell me the address of in memory that changes。

What address and memory changes here， so these are the addresses in memory。

 so which of these addresses changes？56， address 56。So we know it's x。

But the literal machine instruction has RAX being 56。

So there's nothing in the machine that knows that 56 is associated with x， our compiler knows that。

 but the generated code doesn't。So this just takes whatever。Value is in RAX right now。

 which is 56 and stores。RBX into that address。So this will。Overrite， the current value8 with 11。

Questions are this。All right， so that's。Pointer assignment。Let's do。Let's do one more。Exercise。

 let's do star T1。Equals T2。So slightly more complicated。The reference assignment。

So what instruction yeah？Yeah， I mean， remember， they're all just values。So we could。

 I mean we could dereference it， there's nothing in our language stopping that。

But in terms of like the semantic of our original input language， yeah。

It's not meant to be an address， it's meant to be an address。Numb， all right。

 so let's let's generate assembly code that willll implement。This statement。

 which is assigning the value of T2 into。The address stored。In T1。Yeah。最し聞てよ。Okay， so。

Same thing that we did before， and actually let me show the other code because that's probably make it a little easier。

We load the value of T1 into RAX。And so what does RAX now hold？見せていく。RAX holds 56。

So we're loading the value of T1。Okay， so we load the value of t1 at RX。Yeah， yeah， should do。

 what can we do next？あて。对自己。わび。も思い出てく。So we won't be able to do a load in the store at the same time。

 So let's do these， let's do these one at a time。どだ。Okay。So RAX。RX holds 56。

And what will the value of RBX be after this？11， okay。So what's supposed to be？So right now。

 T1 before this operation。T1。Equals 56。And T2 equals 8。

So what will be the value of variables after we run？This and I guess x x is 11。不在。remains the same。

 the1 remains the same。といいかもし。So you're saying this assigns T211， this statement assigns T2 to 11。

srry eleven1。AhYeah， so it's this is assigning this is an assigning T2。

 this is assigning the address associated with T1。 So well， what's the state of the machine after？

Excellent L equal 8。That's the state after this instruction。And so this is loading。

The address of T1 into something。 But we actually want to do the opposite。 We want to store to it。

 So what's， yeah， what's the next instruction。け定バを。Okay， so how do we get the value of T2？マの。

So the allet is 48， actually， this is the address， so this is loading。呃。T 2。Into yeah， let's use RVx。

 so now RVx。Load the value of T 2 into RB X。 So now what's RB X equal。eight。Okay。

 so now we can update， update the elements。 So how do we， how do we do that， someone else yeah。そ的な。

Move percent RB， is it like this？Normal RVX。Like this。 So we're storing RBX。

 which is holding the value of T2 into。第一。Address of RAX。So I'm running out of tech space here。

The address of RAX is star， this is like into star T1。What's that？Yeah， I think that's right。

It's same is same as up here。So it's the same thing as this。

 except the only difference is we load the right hand side value from a variable。

But the rest of the instead of instructions can be the same。You get the address。

Or we get the value of T1。And then do an indirect store。Into the value of T1。All right。

 so let's see what the machine does after we do。Star T1 equals T2 and make sure it actually comports with。

The state changes that we wrote here。All right， so we load。Negative 40 offset into RAX。

 so that's 56 so indeed RAX will be 56 at this point。And then we load offset negative 48 from RVP。

Into RBX。And that indeed is eight， so RBX will now hold eight。

And then we store RBX into the address 56， so the address 56 is here。And RBX。Is8， so this will。

Overwrite。The memory address 56 with。えい？And because that。

Is the memory address associated with X in our compiler and the semantics of our input language。

 indeed eight will now be。X will now be equal to8。Questions on this。So yeah。

 take some time to wrap your head around。These instructions and as I said before。

 the tricky part here is that。In some sense， these variables are pointers， they're not pointers。

 they're references， the compiler manages。呃。Which address they're associated with in the stack freight？

But what distinguishes that from a pointer is that a pointer is when you take the address and store it in one of these memory locations。

 when you store some value that is meant to be used as an address。

And theres different syntax and different operations。

An assembly for allowing you to do this kind of indirect。Loads and stores。

From a value in a register or I mean that value is an address， from an address in a register， yeah。

よ可。Exactly， exactly。Exactly exactly， so you can really think of this as the assembly version of like star T1 in the assembly world and in like I get probably MIps or other instruction sets that have you know more simple like a reduced instruction set。

 this may have you may have to do this multiple steps I'm actually not sure I don't know MIPS。

But assembly， if I give you single pointers。They also have to be registers。

 you know you can't do a dereference of like you couldn't put parentheses around this and do a dereference of an address load。

So it doesn't give you the full。Power that say C has or even S IR has。

Because you have to first take these values and put them into temporary registers。But yeah。

 this parenthesesis is the assembly version of dereference。All right， questions， questions on this。

All right， so choose your own adventure， should we go over code Gen4。

 or should I just go through the whole code example and go through all the state changes？

Who wants to see all the state changes in the example？No。😊，Who was the Zcogen for？All right。

 let's see Co Gen4 first and then first time we'll do that as well to put it all together。

That was really like a placeholder for because I wasn't sure what to do， I wasn't sure about timing。

 how that would work， I think it was going to be putting them a whole compiler together actually。

Is what I intended。All right， let's look at Co Gen4 first。

So the instructions are really similar to Coach N3 because I just copied them from Coach N3。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_52.png)

But I've given you。Another template， the template is really similar to Cogen3 where I've given you local Vars and assignment already。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_54.png)

And then these are the only three functions you need to implement。And in terms of code size。

 this project is actually really short。But because of all this。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_56.png)

And all this， it's a little harder to wrap your head around because you have to really be careful with。

 am I doing of loading the value of a variable？Or am I like dereferencing that value as an address。

 So it'll be a little tricky to get it right， I think。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_58.png)

But actually， the code is deceptively small， Its very short code。 There's not a lot of。

Conditional code you have to do。You just generate these templates and fill in the pieces yeah。ななで。

やがございま。I mean， yeah， if you， if you totally get all of these， yeah， probably yeah。

 probably if you get these。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_60.png)

These snippets of code like these， there's really only three templates。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_62.png)

Yeah， if you grasp all those and you're already familiar with Python and plugging in the variables。

 yeah it could be very quick， I don't want to say it and we cooked for everyone， but yes。

 I think you could do it in 15 minutes if you grasp all this for sure。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_64.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_65.png)

It could be very fast。But you got to test it， make sure it works， test different variations of it。

 but yes， you could do this quite quickly after you wrap your head around what these are supposed to do。

Questions on the template， it's just like CoN3。And just like Co Gen3。

I've designed the grading so that you don't have to have the full compiler。And when you submit it。

 you should just only submit these three。With a template， I think I said this last time。

 but if you want another bonus project， make a full compiler for the bonus project。

 put all the pieces together into a single codegen dot pi。

 and then you'll see the magic of having a full compiler and the thrill of seeing。The hlk about。

 Yeah， you can do that as a bonus project， too， But you got to like get all of them right and。

 you know， show some of the。 I've given you a bunch of more sophisticated。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_67.png)

Examples like this Malic example。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_69.png)

So one cool part is you'll actually be able to use like Malck and play with pointers if you get all of this stuff working right。

 so this is function calls， this is arithmetic operations， this is pointer operations。

 you get those all working， you'll be able to do some。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_71.png)

Fairly full featured programs， yeah。Because I think I I don't know， I did like four bytes。

 I don't know， or maybe I did four entries。And then eight bytes。

As you can see without data types or any specification。

 the meaning of this don't mean of these data types gets lost because it's all just binary data。

 I think I intended this as like a four entry array or something。

And then you could like do some point arithmetic to actually access the other elements of that array。

So yeah， use that as a potential bonus project， putting all these pieces together。

And showing me that these examples work。But anyway， for Cogent 4， yeah， these are all you have to do。

And just like with。Operations， you can really just print out an assembly template。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_73.png)

So this is not a template， but you can kind of reverse engineer the template from this。

 you just need to plug in。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_75.png)

The variable， the right hand side variable or the immediate value。And do this。

 and then you're basically done for assignment。it's the same for reference and dereference。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_77.png)

Let's see what else is here， so I gave some descriptions of you know I gave you the examples of。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_79.png)

Of all of these。Just like we had in class。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_81.png)

This is not a template， but this is an example， it can create a template from it。

 this is an example of ref。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_83.png)

Exle of assigned Ds， these are the same examples we had in class。

And just reminders about how to get offsets， how to do the array stuff。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_85.png)

It's just a pointer to handling variables。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_87.png)

And that's it。 So I gave an example here of this is the example from class。 So this is are the full。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_89.png)

Code example from class。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_91.png)

The same directions for testing it with the wrapper。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_93.png)

So just make sure you restrict yourself to pointer operations like this one is only pointer operations and assignment so you can restrict yourself to that。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_95.png)

When testing。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_97.png)

And that's pretty about chip for Cogen4， everything else is the same。There's a self check here。Oh。

 I didn't update this self check， oh I got to update that。But yeah。

 so it's everything's the same as Co Gen3， questions on Co Gen4。Questions on pointer reference。

 pointer D reference， de reference assignment。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_99.png)

All right， let's go through the entire。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_101.png)

Example， which is a little intimidating。Okay， so I probably should have， oh yeah， actually。

 I do have this here。So here's our。Yeah， I guess we're just to kind of do all of it。So。Yeah。

 let's just go through all the instructions， you know， it'll do all the assignments。

 all the references。So my compiler， I put some little debugging output。

Is this clear that this assign8 to x is the same as this x to8， that's pretty clear， right？All right。

 so let's assume the whole stack frame is set up， let me reset the stack frame here。To have。

To be at the point where we've。Call the function and set up the stack frame。

 and then let's go through each of these instructions。And see how our state gets updated。

And actually， I might as well put the。Registers here as well。O。

So assignment from an immediate just works by loading the immediate value to RAX and then storing that RAX value into the address associated with x。

You don't have to， yeah， you could do that I did this because I just wanted。

 I wanted to be able to make this a template that was always the same。for every variation。

 but yeah you don't have to do that All right， so after move8 to RX。

 how does the state of our machine change， so I've added registers to our state。

 this is our memory and our stack frame， this is registers， how does the state of our machine change。

Yeah。あこつが。All right， so that's。你が。Good， so the offset from RVP， 80 minus 24。Which is here。

 this is 80 minus- 24，80 minus 24 is 56， it's address 56。

So RVP minus 24 in our actual running machine because I'm just assuming that we're at address 80 here。

Is address 56 now gets assigned to whatever RAX is， which is eight。

Questions on these two instructions。So immediate store of8 to RAX and then store of8 to negative 24。

 Why is it negative 24？That's the offset so in our compiler。

Our local vars will associate each variable with an offset from RVP。

 that's how we store function local state。All right good， so let's go to the next instruction。

In our compiler， yeah， the data type for every variable and the data of the width is 64 bits。

 so it's always8 bytes just to make things easier。呃。

It's pretty straightforward to use other bit widths。

 but it makes the compiler a lot more annoying to write。

 you have to save the data type and it's a little more tricky to write。Okay。

 so this is the exact same code except different values， so we move nine now into RAX。

And store RAX into now offset negative 32。From RVP， which is 48。

So you notice how we're blowing away the register state。

But our stack frame is keeping track for us all of the variables state。Okay。

 and now here's where we get our first pointer operation， we take the reference of x。

 so this is remember。T1 equals ampersand x， so this is the reference of x。Into T1。All right。

 so remember， in order to get so references we want to get the address of x， and so to do that。

 we generate code that will compute that address at runtime because remember。

 we't know what the actual address is， we know what its offset is。

And we know that RVP will hold the stack frame so we can generate code that will compute this address for us。

So the first。Instruction copies RVP into RAX， so now what's the value of RAX？80 good。

Next instruction， we add negative 24 to RAX， so now what's the evaluating。56。Good。

And then we store whatever RAX is into。Offet negative 40 from RBP。

 so offset negative 40 from RBP is address 40。That corresponds to variable TI。

And now what's the value in this address？56， so it stores whatever RAx is into。This memory address。

All right good， so that's how the address of X got stored into T1's memory location。

So now we have the D ref of T。 so this is T2 equals star1。 So this is where we're dereencing T1。

And storing the value into T2。So D ref T1 to T2。So first thing we do is take offset negative 40。

Which is the offset associated with T1。And we load its value into RAX。

 so what is the value in RAX now？Still 56。 So the machine will actually do this copy for you。

 I think it's not going to optimize it way for you。 You could write。

AAnother pass in the compiler to go over this code， because you can see here we have。

Move RAX negative to 40， then negative to 40 RDX， optimizing thers will actually notice this and remove it for you。

But our compiler。Making it easier to write doesn't do any of this trickery。

So this extra instruction while seemingly meaningless， makes sense in the context of our compiler。

Because Df is a separate operation。 So what we first do is we copy。The value here into RAX， which。

Just overwrites it with 56 again。All right， so here's what of our。Dereference operations。

 So what how does the state of this machine change？After this， yeah。Okay， so why is it8 because 56？

These parentheses say load from whatever address is stored in RAX。



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_103.png)

Addres 56 is stored in RX， so it loads whatever that value is in RBX。That value is 8。

 so now RBX holds eight。And then here we have a store from RBX into offset negative 48。

So offset negative 48 from RVP is this address 32， so how does the state of this machine change after the highlighted yeah？



![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_105.png)

Yeah， the memory address associated with Q2， which is address 32 now holds。え。All right。

 good question so far so far。Yeah， so basically like so it kind of changed the as the offset changes。

Address and like how do we get when the address to the？So remember this this。

Whenever you have a load or a store using this syntax， this is saying。

 get whatever the value of RVP is， which is here 80。And subtract 48 from it。

And that address computation happens inside the processor。

And whatever the value of RBX says will be stored at that address。

So here in the state of our machine， RVP is 80。And we're asking it to go to an offset of whatever RBP。

 so 80 minus 48 just 32。And store in that memory location。So stores8。Okay， so let's finish this up。

So now we're at the。Assigned DF， I call it， so we're doing star T1 equals 11。All right。

 how does the state of machine change when we run this highlighted instruction？た。Sa嘅。Okay。

 Rx is still equal to 56。And that's because we asked the machine to go to the offset from RVP of negative 40。

 which is address 40。Take whatever its value is。And store it into the Reg REX yeah。发分这。Right。

 so our next instruction will store。1even into RBX， so it'll overwride eight。And store 11。

And then here we see。Another one of our pointer de reference operations。So， yeah。Yeah， yeah， good。

And store。Good， so this will。Take RBX， which is now 11。

And it will store it in the address given by RAX。 RA X is 56。 So the memory address 56 is here。

And it'll store RBX， which is 11 here。对。えと？If you dereence RBX。You wouldn't necessarily get an error。

 it would just load or store address 11。Well， it's down here， right， it's down here in memory。Well。

 I mean， these machines are byte addressable， so you can address individual bytes。I think， yeah。Yeah。

 so you can you know you got to keep in mind that。There's no distinction in a machine level between numbers。

 addresses， integer strengths， it's all just binary data， it's the operations that distinguish them。

And yeah， when we program， we think in terms of these data types。But。

At the actual like physical machine level， these are being mapped encoded in numbers。

 even the op codes themselves， even this assembly code。Is mapped into binary data。

And you could dereference binary data， this is why you get seg faults and like buffer overflow issues。

 you get seg faults because you're dereferencing stuff to an address that you don't have access to the machine machine restricts your access to。

 but if you have access to it， you're going to get a silent failure and just。

Your code's not going to work as you expect， but at the machine's point of view。

 it's doing exactly what you asked it to do。Okay， let's finish this out so any other questions on the pointer operations？

All right， so let's finish this out， let's do x equals t3。I think that's what the next thing is。

 yeah， or sorry t1 equals x。All right， so what's the result in the machine after running this。

 yeah I think you got it run the first。RAX is 11 good。

 so this is saying load from negative 24 offset from RVP， RVP is 80， minus 24 is 56。

 so it loads this value into RAX， finally overriding it with something different。Okay。

 what about the next instruction？Yeah。も一度映か約。先なで。あり？Good， yeah， so RVP， again。

 we're storing RVP offset negative 56， which corresponds to T3 in our compiler， that's address 24。

And we store whatever ourX has， which is 11 in this case， we store it there。All right。

 questions last one questions all right so you have Co Gen4。

 this is the end of the content for compilers next we go over the final and have a good weekend everyone。

 take care。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_107.png)