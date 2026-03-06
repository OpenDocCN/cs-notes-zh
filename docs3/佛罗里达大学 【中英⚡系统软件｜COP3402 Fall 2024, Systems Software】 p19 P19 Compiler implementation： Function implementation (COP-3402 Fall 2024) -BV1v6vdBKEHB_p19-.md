# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p19 P19 Compiler implementation： Function implementation (COP-3402 Fall 2024) -BV1v6vdBKEHB_p19-

And we're recording， so welcome back to System software yeah。So the greater well send this out today。

 he'll send these out。All right， so today we're continuing our lectures on compiler implementation。

 so last time we looked at how functions get emulated。At the instruction level。

 and today we're going to show how to actually write a compiler that will generate assembly code that will give us this。

This function behavior that we want out of the more function。any questions from last time about？

About the behavior of functions， their semantics。How about the answer to the homework？

So if we had a recursive version of factorial。How many stack frames would you have or might you have if you're computing factor Tya？

Well。Ca。ctorial？Yeah， so if you depending on how you implemented factorial。

 whether you test the base cases one or zero。You'll either have a call for F0 or a call for F1。

 but you'll have at least 10 calls for the factorial function， maybe 11 for factorial zero。

 and if you included mainine that would be one of the stack frames so that's exactly the right。

So just to illustrate the point that each call of the function has its own stack frame and why is that。

 why does every call， why do we or what's the function behavior that we get out of doing that？

Fre the collar。So we know where go。Yeah， this is exactly right。

 so each call is treated as its own independent instance of the function。And if we didn't do that。

 if we had local state for the function or we shared state across them。

 this behavior of recursive calls just wouldn't work。

 even multiple calls for the function wouldn't work as expected。

 where the semantics of functions that we expect and we learned and C is that each call to the function gives us a fresh local state for that function。

All right， good other questions on the semantics of functions， seat functions。All right。

 so let's look at how we can actually implement these kinds of functions in our compiler。

So this is where stuff gets really kind of meta， you got to remember that we're not。Evaluating。

 we're not building the stack ourselves in the compiler。

 we're generating code that's going to build the stack。 So I think I kind of already went over this。

 but what are functions， What's a definition of functions。Yeah。Yeah， one you can name。

 name a computation， and there's all sorts of variations of functions in C， you can name them。

 give the types of the input arguments and the output arguments。

And you get this function local state behavior。So how do we implement this local state？

In C functions， yeah。Stack frames， stack frames on every call， okay。

 so we already kind of covered that。All right， so to actually。Implement this in the assembly level。

 there's lots and lots of ways you can do this， so you can arrange parameters and local variables。

 you can arrange these in all different ways。But in order to make sure that if you write a function that I can call it。

In my compiled version of the code。Compilrs and systems will standardize how the stack frame is laid out and how the call is made。

 these are called calling conventions or the application binary interface。

 so the binary here is like the machine code， and there're just conventions。

 there's nothing here you can like reason about there's no particular principles accept that the conventions tell you what the stack frame layout is。

 where do parameters go， where the return addresses go， base pointers， local variables。

 they tell you how to do parameter passing and how to get the return value。

So all implementations of this function local state。

 this stack based function local state will have these attributes。

But how you actually do it is system and machine dependent， it turns out。



![](img/ddbc8774efa72a0058f10611c2f0b711_1.png)

So there's this hopeful website， this OSD website， if you actually want to go build your own operating system。

 this is a great resource that actually walk you through starting to run code on bare metal without a kernel。



![](img/ddbc8774efa72a0058f10611c2f0b711_3.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_4.png)

If you're really interested， but it overviews some of the various。



![](img/ddbc8774efa72a0058f10611c2f0b711_6.png)

ABIs application binary interfaces that different systems have， so for instance。



![](img/ddbc8774efa72a0058f10611c2f0b711_8.png)

And the。And so it depends on what operating system you're on and also what architecture you have。

 so if you're on an arm。Device， the names of the registers are different and you may not have special purpose registers。

嗯。So in the Microsoft world， there are actually， let even look at what the little differences are。

So in x8632 bit， parameters are always passed on the stack， so there's no registers。

 but on system 5 and X8664， as we talked about last time。

There are registers that we pass parameters on and why did we speculate that you might want to pass parameters via registers？

Yeah， just higher performance。But just to illustrate this， just this is a decision。

 this is a design decision， it's not written in stone where these parameters go and you can see that in the Microsoft API they use different registers from a parameter passing。

 so this is really really just a convention， you can see these are the kind of things that are in every convention。

 the return value parameter registers， etc cetera。There's also this notion。

 we won't have to worry about this too much， I'll just give you the code for it。

 but there's also a convention about who saves registers。So when you make that call。

 your function may be using various other registers like RBX and R 12 and all these your function needs these registers in order to run。

And so there's a question about who freezes that state when you call a function and there's just conventions on doing this so scratch registers are ones where the caller cannot expect to have those saved so the caller must save it and there's ones where the caller can expect it to have it saved so for instance in the。

System 5， ABI， the one we're going to be using， the B register。Is expected to be saved by the call。

So they don't worry about too much， these are just conventions just to decide who does what。

 whether it's the caller or the colleague， and just I'll give you the assembly code for doing this so the main thing is we just have to make sure we preserve RBX。

All right， so that's the application binary in interface， any questions on what an A is？

What a calling convention is。It's a quick quiz。I 386 system 5。

 what parameter registers are used in the calling convention？对。None， yeah。

 there's no parameters we're going to be using this one。

 the system 5 x8664 or AMV64 AI this is the one we're going to be using。

 but I'll give you all this information you shouldn't have to I mean you don't have to know this I think few programmers keep this in their mind when they're programming and see but I'm just going to give you the assembly code for doing this but I just want you to be aware that when you go to debug you're going have to be aware of what's happening at the machine level。



![](img/ddbc8774efa72a0058f10611c2f0b711_10.png)

Okay， so those are calling conventions in general， and this is a diagram from this webpage that I showed last time describing the calling convention for X8664。

 system 5， x8664， which is what's used。

![](img/ddbc8774efa72a0058f10611c2f0b711_12.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_13.png)

By Uni most like many Uni style systems， Linux uses this， which is why we're using this on use this。

this is a diagram of what its calling convention looks like， the AMD 64 System 5 ABI。



![](img/ddbc8774efa72a0058f10611c2f0b711_15.png)

So in this calling convention there are six parameter registers。

 so the first six actually I can show here is probably better。

 here's a function that has eight parameters。

![](img/ddbc8774efa72a0058f10611c2f0b711_17.png)

The first six parameters are passed via register， so you can see heres。



![](img/ddbc8774efa72a0058f10611c2f0b711_19.png)

Parameterters A through H， and you can see ABC， the EF， the first six parameters。



![](img/ddbc8774efa72a0058f10611c2f0b711_21.png)

The caller is expected to populate the registers with these parameters to make the call。

And that's because the call lead function。Especially if it's generated by a different compiler or a different developer generated with the same compiler。

 you want to make sure that that function will be able to get the parameters that you send it。

 that's why you have this convention。So the callee will look to these registers for the first six parameters and then the rest of the parameters will be pushed onto the stack so in the I don't know if you remember this from from a computer organization but。

By convention， the stack grows downward， heap grows upwards， stack grows downwards。

 did you all learn this， stack grows down， he grows up， okay， more or less。

So what makes this what also is a little confusing。

 which you have to keep in mind is that when you push something onto the stack。

 so this is the current stack before we make the call。

 this brown section here is the callerss stack frame is in there somewhere。

When we push we're actually subtracting an address。

 we're actually subtracting an address from the stack pointer。

 so the stack pointer RP SP is for stack pointer， that's a register that holds。

A pointer to the memory location that is the top of the stack。And when you push onto the stack。

All that happens is a move， moves whatever data you're pushing onto the stack into that address into the next address into the stack and then decrements。

 actually my decrement first and then looking at this。

 it looks like it decrements first and then copies the data onto the stack at that new address。

With me so far on this， does make sense？And you'll get a really good crash course in what pointers actually do at the machine level when're using C。

 so these registers like RSP， they're just registers they just hold numeric binary data。

 but what they mean to the instruction set is a pointer。

 they're meant to hold the address and memory of the top of the stack。But yeah。

 just keep in mind that you've got the stack growing downwards whenever you push the memory address of the top of the stack。

Goes down， it's subtracted。Okay， so the chour。In green， the one who's calling this function， my funk。

Passes the first six parameters， copies them into these registers。

 remember this is Justice convention， and then any subsequent parameters get pushed onto the stack。

So here we've got H and G being pushed。And then the caller will use the call instruction。

 remember last time all the call instruction does is it takes the current instruction pointer。

 that's the address of the current line of code that you're executing。

And it pushes the next line of code， so the code that's how we freeze the state part of the state of the caller。

 this is the next address that you're going to execute in the calling function， the caller function。

So this address gets saved onto the stack so that later， so why is that saved onto the stack？

WhyWhy do we save the return address onto the stack when we make the call yeah was it yeah。

 so you can jump back to it so you can branch back to the calling function so if we have main calling my funk。

In order to freeze the state of main， we want to save its stack frame。

 but we also want to know where to continue executing in Ma and that address。

 that instruction pointer， that address that contains the next instruction in the main function。

That gets pushed onto the stack next and that gets done for you when you use the call instruction in x86。

 so that gets pushed onto the stack。And as soon as you do call。

 pushes the address onto the stack and then branches to the MyFk code。So here in light blue。

 this is where the myFk side of the calling convention starts happening。

 this is where the epilogue of the function starts running。So the first thing it， yeah， yeah。よア？

AhThat's a good question。So any guesses on how？呃。MyFk will be able to access， well。

 how can it access say， so Zz is a local variable for my funk。 so how can it access Z Z。Yeah。Yeah。

 so you can do some pointer， which you might call pointer arithmetic and C。

 you take this address of the base pointer， which is pointer to the current stack frame and you just add and subtract。

The amount that will get you to that variable， the question is this is not happening at compile time。

 right， how does the compiler know how many， how far to go。

 how far to go from the stack frame in order to find those variables。Or can we know？Yeah。んであありがい。

Vitable then know how much that because every long。right。ノートでたや。え不は。He just atract。我员。あ。あ、いっぱい。

That's exactly right， so if you didn't hear your colleague。

 we know at compile time because the developer has told us the data types。

And because these data types have a well definedfin precision，- I mean it's machine dependent。

 but it's well defined， we can compute at compile time。

 we know exactly how much and because the compiler is the one that is generating these push instructions。

The compiler knows exactly how far away， at least from this space pointer。

 at least from this once it has the address of the stack frame， it knows exactly。

How far away each of these variables are going to be and that's actually the key is that because you're the compiler writer and so you're the one generating code that's going to be pushing onto the stack and so you're going to generate code that you know the first six are going to go to register so you'll generate code to move those into register and then you're going to generate two pushes。

 one for H and one for G and because you as the compiler writer wrote code to generate that。

You know and you know exactly how many parameters they're going to be。

 you can actually at compile time compute exactly the offset of those variables in memory。

Questions on， that makes sense， so yeah， very good， That's exactly right。

 can this is what you can determine at compile time yeah。十そ。どんどんまウ。This is not the kernel boundary。

 so that's a good question， so this is a boundary between two user space functions。

The kernel boundary works a little bit differently the way the calling convention works because you have to go into a different processor mode。

 it's done a little differently， you trigger an interrupt。

 take an operating system of course to learn about this。

 but you trigger an interrupt which causes it's basically an event that causes a kernel process to start running and there's different ways to pass data back and forth between the kernel news space。

There are something they're called stubbs， wrappers in sea， which are used for the system calls。

 but then there is a different process for transferring control between the two。But yeah。

 this is just between two user space applications， like when you call printf。

Where you call a library function， this is the calling convention that gets used because both of those are operating in user space when you call library functions。

So system calls versus library functions， system call transition to the kernel。

 library functions like print F， FEed， these are user space calls in them they may call the kernel。

 but when you call them from ERRC program they're being called with this convention。

 so that's a good question yeah。There。It depends on whether it's a system call or a library call I can't remember depends on the man page they're on。

 I think the directory ones are actually library calls， that call， the cis call。

 the man page actually says don't use the like it recommends against using the cis calls for directories。

Was it the same thing， I think all the dearer ones， so if it's man3， that's a library call。

 man two are system calls and some other the ones that are going to have a special subub function that then will transfer control to the kernel。

 the library ones are user space so that just like when you write your own C function。

 user space to user C function， which uses this convention。Yeah， you have a question。ですで。のめき。いんな？

Where is。AThat's a good question so well so how can we do this so if at compile time we compute these offsets so the compiler will have this information right you can store this the Python program。

 the actual running compiler program can compute all these offsets。

But there's no table here that says what the offsets are。

 so how can we I'll ask you since you answered so well before。

 can you think how the compiler can ensure that the right offset is used that compile time this' is a little bit of a trickier question。

 I don't want to put you on the spot but if anyone wants to answer yeah。If wants。我自己开。For8。はいかい。しさは。

You can。Yeah I mean that's a good start， so actually one way to think of this is that。

Since these are fixed constants。😡，And also remember that Xx， you know these variables。

 they don't have any meaning at the machine level， remember， these are like ASI symbols。

So what actually happens is the compiler translates this symbol into just an offset。

And so whenever you have an operate and we'll talk about this next week。

 whenever there's an operation on a variable， an assignment or a use。

 it's not like the assembly is generating a label because labels are for。Like branching。

 it's actually just going to generate。A code that will hard code this offset。So this。

 like whenever there's an assignment to Xx， the compiler is going to translate that to an assignment to RB minus8。

And so there's actually a special instruction in the Intel world that will do this like a single instruction that will let you do this computation。

It's called register indirect offset addressing or something like that so you know risk instruction sets don't necessarily have this but cis complex know instruction sets。

 whatever they're called have these actual helper instructions that are designed for making it easier to write compilers with fewer instructions and so yeah that's a really good question but it all comes down to the fact that what we can compute at compile time we can compute a compile time what these offsets will be and then our compiler knows that so when it does the translation will exploit that knowledge in order to generate code that will behave like the original C program did you have a question。

About like。Bing。Related to this。How do they count the death frame？How do you count the stack grant。

 did that' like any mean the homework question？So the homework question。

 so we talked about it before， so what was how did we count the stack frame for the homework question？

上下。Yeah， a number of function calls， one stack frame per function call， so if you factor of 10。

 you have 10 function calls plus F0 in mean。Okay， so that's how the compiler knows。

 because the compiler is the one generating the code。

 that can exploit whatever knowledge it has about the code in order to do its generation。O， yeah。

 yeah。What happens to be big concursion？こ聞こえがつ。嗯哼，我的。Would the offset be the same？🤧咳。

That's a good question so what I didn't quite talk about yet is that these so these are offsets from the base pointer。

And those offsets are fixed for every call to the function because the function has a fixed number of。

Parameterters， which I'll have fixed bit with。The question though is how do we know what so these are relative to this RVP pointer。

 how do we know what the RVP pointer should be？So the next question is how do we make sure that this pointer？

Is correct that it's pointing in the right spot。And that's actually the next that's the first thing that the call lead does。

 the function being called to， so after the call the call will push the return address so that we can unfreeze the instruction pointer。

And then branch to my funk。The very first thing myF does by convention is it saves the old。RBP。

 so the old base pointer is up here， so remember the base pointer。

 the kind of invariant or the the thing that the compiler wants to make sure is maintained。

Throughout execution is that the base pointer always points to the current stack frame。

And so this is again where we have these special purpose registers that can help compiler writers。

 but the key is that you want to save one register to always point to whatever the current stack frame is now it's easy to now if you have that done then and you know that the offsets are always fixed then you're done right you just say whatever the base pointer is。

 use a fixed offset from the base pointer to get to the locals and parameters as long as you know that RBP is always pointing at the current stack frame。

So then the trick is， how do you make sure that RVP is always point to the current stack frame？

And so the way that's done is you take whatever the old one is， assuming the old one is correct。

You push that onto the stack， and why would we want to push that onto the stack？Yeah。

Exactly so we can recover the caller's stack frame。

 so this is very much like recursive reasoning where you have a base case and then you have a recursive case。

 the recursive case here is that we assume the current base pointer is the caller and then we push it onto the stack so that will guarantee that when you pop you'll have the caller's base pointer and so to make sure that we're at the current base pointer we just by convention save whatever the current stack pointer is。

To be the base pointer。So。呃。Yeah， okay， I'll show it here I'll show this example。

 I'll show another example again with another。I'll do it on a whiteboard。

 but just to get through this， so before we call the function， the stack pointer is here。

And then we push the locals stock pointers here。We make the call stack pointers here， okay， RP。

 stack pointers here where I'm wing the arrow。When we save the old base pointer。

 the stack pointer is here。So to set the new base pointer for the new function call， we just say。

 okay， whatever the current stack pointer is， we just copy that into the base pointer。

So by convention， the base pointer will be pointing to kind of the middle of the stack frame。

Just because of how it's constructed and when you set the base pointer， it's just a convention。

 but just remember that right after the function is called。

 saves the old base pointer and then sets whatever the current top of the stack is。

 which is like halfway through the construction of the stack stack frame， it just says， well okay。

 whatever my current stack pointer is。Asign， copy that to the base pointer。Does it make sense？

Is it I mean？呃。Let me show this in a diagram。

![](img/ddbc8774efa72a0058f10611c2f0b711_23.png)

Before I move on， I want to make sure。This is clear。Yeah。

 and I'll show this more later with a fuller example。Let's say I already have a stack frame here。

And RBP is already pointing。To the middle of my stack frame。 so this is my。Stack frame for Maine。

And then when I go to make the call， I push locals， or I push parameters， or I push parameters。

And then I push the old RBP， so whatever this address is。

 let's say it's like let's just number these addresses。I take whatever the old base pointer is。

 it's pointing to address one， and I save it here。I save it， so here's my locals， this is son local。

 local。

![](img/ddbc8774efa72a0058f10611c2f0b711_25.png)

And then when I transfer control， and then， oh yeah， there's the return address。



![](img/ddbc8774efa72a0058f10611c2f0b711_27.png)

And then when I transfer control to the callee。I first thing I do is I push the old base pointer。

 I push the old base pointer， and what's the address of the old base pointer？Address one。

 so I push that value here。AndBut now I'm running my current function。

 but my base pointer is pointing to main stack frame。So how do I make sure， oh yeah。

 so what I also forgot to mention here is that my stack pointer is pointing here。

Because this is the last thing I pushed。So my stack pointer was here， push， push， push， push。

 stack pointer is now pointing。At this memory location that holds field base pointer because that's what I just pushed。

So then what do I do to update the base pointer to be my current function？Yeah。Yeah， exactly right。

 so I copy seven into the base pointer and so what that does conceptually is it makes the base pointer。

Point to this memory address， does that make sense？So yeah， literally RBP will hold the address7。

 RSP holds address seven。This old RBP held address one。

 and so now my you know RBP is no longer address one， RBP is seven， which is pointing here。

Does that make sense， does that make it clearer？And then I go on and then I continue constructing my stack frame inside of my call。

 which consists of allocating space for local local variables， sorry these were parameters。

Which are also local variables。And so once I've done that， I now have my。

Stack frame for my call callee。You know this RSP。Gets pushed to whatever the top of the stack is。

And so now I've got this。My machine is set up to where the base pointer is pointing to my current stack frame and of course my stack pointer is at the top of the stack。

Yes， exactly right， so a stack trace would file and you know there's other debugging information that goes in。

 but yeah， and so what。So when we go back to return to the callur。

We can tear down this stack and then we have an address to the old base pointer so we can update our old base pointer。

But if you notice what this does。If I had a new function call inside of my funk。

The base pointer would then be updated here。And it would be address7， the old base pointer。

 the Colliier base pointer， and so notice that if you look at this stack。那个呢。Put this here。

What these base pointers do is they create a chain。Of pointers。

That if you just follow the base pointer back down the stack without any offsets。

 you can just immediately trace。The entire stack。of base pointers by just following。

 sometimes this is called the I think dynamic linkage or something aesthetic linkage。

 the dragon book has a different turn for this， but if you could just follow the base pointers。

 you'll see the whole chain of function calls， and you can certainly use this to unroll the stack with additional debugging information about the function that's being called but yeah。

 this is like the stack trace is。The set of function calls that you have on the stack。Yeah。

 that's a good good question。All right， other questions on the baseball， yeah。それが。当して。ごて況ます。

The function parameters。So yeah， sorry I call these locals， these are， so the parameters are here。

And they're also， where else are they in the system 5， x86 is4， yeah？



![](img/ddbc8774efa72a0058f10611c2f0b711_29.png)

In registers， yeah， so the this is just the convention of system5， X8664。

 the first six parameters are copied to registers first。

And then the remaining parameters are't pushed onto the stack。Just the convention。

You can imagine doing this in very， very different ways。You can push all the parameters on the stack。

 and that's probably easier to write a compiler for。不。All right， questions on。Managing the stack。

Or how this calling convention works。So we've got two special purpose registers in the Intel world。

 RBP for base pointer， RSP for stack pointer， and then RIP for instruction pointer。

 but you don't have to manage that yourself， it gets managed by the call and return instructions。

All right， so the stuff in green is it the caller or the colee that pushes this data？Yeah。

 collar good and then the stuff in blue， collie， yeah。

And so they both work together in order to construct the full stack frame for the MyFk function。

 so that might be a little counterintuitive， you would think。

What's that the green stuff is the part so this stack frame， this whole stack frame is for my funk。

But half of the stack frame or part of the stack frame is constructed by the caller because the caller knows the values of parameters。

 it also knows the return address。And the second half of it is set up by the call lead because it knows its own base pointer。

And it knows the previous base pointer， its own base pointer， and it knows its locals。嗯。Values。

All right， yeah， yeah good。第。Yeah， RSP is the stack winner， in other the top of the stack。

Now it's just a pointer so when you pop from the stack， the data is not deleted or anything。

 it's just by convention， this is the current top of the stack， but if you call push again。

 it's going to overwrite whatever data you had on there。Yeah。Yeah， sure， so the return address。

 so what's the return address， where does this point to？This is the caller's next instruction。

 so this is telling you， so when mainine is running。

 so Maine is a sequence of assembly instructions and you have a call instruction。

 which I'll show an example of this soon。And then when you want to resume Maine。

 you have to resume it after the function call for our function of semantics。Like in factoria。

 when you call factoria， you pause the parent call。And call the child and when that's done。

 you return exactly to the space where you've just left off factorial。

 so this return address is the address and memory of the next instruction in the caller。

So this is how you will be able to continue executing the caller function。

By going back to this address， and this is managed for you by the call and return instructions call will。

Both put the return address on the stack for you and also that jump to the function address。

And return will pop that address off whatever it is on top of the stack。

 and we'll branch to that call。And so if you ever heard has anyone ever heard of stack overflow attacks or buffer overflow attacks。

 probably heard of these？So the crux of this is。There are operations in C that if you have a buffer overflow。

 like let's say X X。Is a string or it was easy as a string？

What direction do you know what direction arrays go in memory。

 are they positive in memory number or negative？They're positive， yeah， they're positive offsets。

 so it' easy is a string。And it's only meant to hold three slots。In memory and you give it 10 slots。

You can actually end up overriding the RBP and the return address。

And that's what a stack smashing attack does is the attacker will exploit a buffer overflow in a C program。

 a buffer overr， in a C program in order to blow away the return address。

 and then through some very clever tricks。They can attempt to replace that return address not with some random place in memory。

 which will cause the processor to say well， I probably likely will not be able to interpret these instructions。

 but instead to jump to an address that's under the attacker's control。

 that's some code that the attacker control and so the classic ways to not only overwrite the return address but also overwrite。

The stack with。Instructions with assembly instructions and try to get the return address to jump back。

To the code that the user passed has input and then take control of the machine。

 execute a shell code， execute shell code。So this understanding these calling conventions will help you understand probably one of the most classic and prolific software security attacks like ever in computing history。

This is the classic stackming attack， and it all comes from this calling convention。

Now there's like there's defenses against this these days。

 so the original version of the Staation attack。I've showed it in class before。

 probably won't have time this time as like especially， you can see like a past lecture。

 you have to turn off a couple of protections in order to actually get it to work。

 but you can get it to work on your own machine。And use it to do like privileged escalation or get shell code running。

嗯嗯。All right， any questions on the calling convention， any more questions on the calling convention。

 hopefully they're all good on this so you know use this diagram。

 this is from this this guy's website， I think it's a really really good diagram， use OSD。

 whatever you need a reminder you don't have to keep this in your head。



![](img/ddbc8774efa72a0058f10611c2f0b711_31.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_32.png)

Pro。Okay， so let me get into that， let me get into that next。



![](img/ddbc8774efa72a0058f10611c2f0b711_34.png)

So yeah， I'll show this exactly with an example so here is a。



![](img/ddbc8774efa72a0058f10611c2f0b711_36.png)

Complete。Assembly program。For what function is this a main function。

So let me go through each piece of this。So these dot prefixed assembly instructions。

 these are called pseudo ops， they're not really they don't correspond to machine code instructions。

 these are for various metadata about the assembly program like in this case。

 what the name of the source file was， there's other properties of the binary that you want to say。

 don't worry about these， I've given these to you， I've given you code to generate these。

 this text is saying we're in the text segment which is where the program code goes in a binary。嗯。

These are more pseudoops for describing a function， you don't have worry about those。

 I also give you these， you just have to generate these。

And then a function is really nothing more than just a label， an address in memory。

 that's really all a function is at the assembly level。And so in assembly code， you can name。

AYou can name a label， you don't have to give an actual memory address。Okay。

 so this the this is the metadata for the assembly file， and this is how you declare。

 so to speak a function in assembly， you just use these pseudo ops here and then give a label for the so when you did MIPS。

 did you have labels for branches？Okay， so it' okay， they're all familiar with this yeah。Okay。

 so yeah and we'll see it we way into a call， but kind of at the machine level you're branching to an address。

 but at the assembbller will allow you to name addresses and actually because the code because remember we talked about linking。

 the address of the actual function may differ in the final executable file and in memory so the asemmbler and the linker will handle this for you by using relative addressing。

 so at the asemler level you just have to give a name to a location in the source code for for branching yeah。

嗯。そじ。No， we're not using MIPS， we're generating x 8664， so this is all X8664 assembly code。

So I just ask this because that's what you learn in computer organization All right。

 so here's the prologue。This is what the prologue looks like for our simple main function。



![](img/ddbc8774efa72a0058f10611c2f0b711_38.png)

So recall what does the prologue okay， so the prologue of the function is that the green section of the stack or the blue section of the stack。

It's the blue section because remember， the caller sets up this part， the first part of the stack。

The callee。Seets up the remainder of the stack， so when the function when the call lead gets called。

 this is the first code， so if main is getting called。

 this is the first code that gets run when you call main。



![](img/ddbc8774efa72a0058f10611c2f0b711_40.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_41.png)

So the caller， the code for doing this is what the function call does。



![](img/ddbc8774efa72a0058f10611c2f0b711_43.png)

The function definition is the call E is the call E code， does it make sense？



![](img/ddbc8774efa72a0058f10611c2f0b711_45.png)

I'll show a full example with like a function call as well and you'll see why that's the case。

 but so a little trick question that the call Lee， its prologue sets up the rest of the stack。

Because that's the code that first starts executing when you do the transfer of control to the function。

前でだ。でございます。

![](img/ddbc8774efa72a0058f10611c2f0b711_47.png)

Then by the way。This metadata。So well technically this is done。

 this is the so called compilation unit。🤧。In C a compilation unit you think of it as one like assembly file or one object file can have multiple functions in it in my simple IR that I've given you there's one function per compilation unit。

 one function per assembly file， so in this language yeah there's one function per file but in C in general no you can have multiple functions in the same file so this is just setting up the a single assembly file and a single object file。

And this is setting up a single function， so you can have more than one of these。でさ。Oh oh no， no。

 so these are， remember， this is the output program that the compiler generates。

So this is literally the assembly file that will get produced by your compiler。

So this is not runtime， yeah， so this is the main thing to wrap around， this is not runtime。

 this is compile time， this is the program that gets generated。

And then these instructions are not being run yet run once you assemble and link and run the assembly file。

These will get executed。But yeah， this is the main trick to wrap your head around is that this is not the stack creation。

 this is code that creates the stack， it's not literally the stack itself。Yeah。

So these are registers， these are registers， yeah， so so yeah I probably failed to make that clear so this is called the AT& T syntax for assembly。

 there are two， at least two syntaxes for Intel assembly。嗯。In the AT&T assemblyly syntax world。

So I mean， you learned computer A， right， there are registers。

There's a finite number of those that the processor can access to copy and move data from。

And then there's， you know， like mainine memory。In the assembly code in the AT&T syntax。

 you can refer to these registers by their name prefixed with a percent sign。

 so whenever you see percent side something， that's a register name。

 that's one of the registers in the Intel world。So RBX is a register。And you know yeah。

 also I probably been make it clear either that the you know the first on every line of an instruction。

 a real assembly operation， you have a mnemonic， the name of the assembly instruction that you'd like to run followed by its arguments。

 so this is a push instruction for pushing onto the stack。

 there's a move instruction for moving in the Intel world there's like a lot of different variations of move。

 this is moving data between to what are these arguments here。

The registers and another push instruction。Another peculiarity of the AT&T syntax is that the destination register is on the right。

So this is moving whatever is in the stack pointer to the base pointer。You might see Intel syntax。

 which swaps them， which makes things just ultra confusing。

 but this is the the destination remember an AT&T destination on the right。Okay。

 so this is the code that's going to be generated for。For a main function。

 so this is just a static assembly file and at runtime when you call main。

When the processor executes the instruction of Maine， it will start constructing the stack。Okay。

 so here's the prologue。And so recall what the prologue of the function does， so the callre sets up。



![](img/ddbc8774efa72a0058f10611c2f0b711_49.png)

The parameters and the return address， and then transfers control to the callee。



![](img/ddbc8774efa72a0058f10611c2f0b711_51.png)

And this is a colleague like Maine。And these are the first instructions that run when it's called。

 so after calling。

![](img/ddbc8774efa72a0058f10611c2f0b711_53.png)

So this green stuff is the caller。

![](img/ddbc8774efa72a0058f10611c2f0b711_55.png)

Once it transfers control， it's literally branching to this label。

 it's branching to the address that's represented to this label and starting to execute code。

 That's why the first part of the call E function。Is setting up the rest of the stack frame？

So caller has its own code when it does a call， it sets up part of the stack。

 transfers control to the function， just jumps to the label。

 and the first part of a function sets up。The rest of the stack。Questions， questions on that so far。

Okay， so remember what we need to do to construct the rest of the stack according to this callinging expansion。

 what's the first thing we do in blue？The callee was the first thing we do？Well。

 return address is saved by the call function， that's done by the col， so it's in so why it's green。

 so it's。やっていた。Yeah， so we first saved the old base pointer， so remember in our diagram here。



![](img/ddbc8774efa72a0058f10611c2f0b711_57.png)

The base pointer was pointing at whatever the caller was。Whatever its base pointer was。

 and the first thing we do is to push the old base pointer onto the stack。



![](img/ddbc8774efa72a0058f10611c2f0b711_59.png)

So when we call push RBP that。That takes the old base pointer and pushes it onto the stack。

So the second thing we do， so the base pointer， if you remember in this example， the base pointer。

 after you push it， the base pointer still pointing to the parent' stack frame。

So the next thing we do is we take， we want to update the base pointer to its new address and that address。

 how do we know what the new address of the new stack frame is？Well， it's okay， so I had done more。

Let me put this back into the state。Of the。Of the call。So we make the call RVP is pointing here。

R SP is pointing here。And when I push RBP。Yeah，Exactly， we use the stack pointer。

 so we pushed the old。RBP， which is one。And when you push。

 the stack pointer is updated to whatever this top of the stack， the new top of the stack is。

So in order to get the new base pointer， we just copy whatever the current stack pointer is into。

The base pointer， whatever the address of。The current stack pointer is we copy it into the。

Base planner。Questions on that， does that make sense？So that's what these instructions do。

 We push the old base pointer。And then we move or copy whatever the RSP is to the destination Reg。

 which is RBP。And so at this point our stack。And our registers look like this。

RSP and RVP are pointing to the same spot。The contents， remember， RBP is an address。

 you know this contains address 7。The contents of it are whatever the old RVP was。

 the old RVP was address one。So I don't know， I think this makes pointers a little bit easier to think about because you a register contains an address。

And that's definitely not data that's on the stack。

When you copy data from an address from a register onto the stack。

 if that data in the register was an address then you've pushed。A pointer under the stack。

 So that's why this。Old RBP is conceptually a pointer to the old stack frame because it just contains an address that was the RBP previously。

Great， questions， questions so far， yeah。Yeah that's really a good question。

 this is the like bit width of the I can't remember why I did this for the stack。

 I think because I wanted the stack to have like a specific bit width to it。

But it should be able to be inferred from the arguments。

 the asmbler will infer the bit with the organ， so basically there's like a move instruction for almost every bit with。

You can move just eight bytes or maybe 16 bytes， 32 bytes of bits rather。

 and so there are different instructions for those。If there's sort of a data type。

 so RP refers to the 64 bit registers， but on X86 ESP will refer to the same register but only the first lower 32 bits of it。

 so don't worry too much about this like details of Intel it also I'm not super familiar with I just kind of worked it out but Q I think is the 64 bit。

 64 bit one。But even here I didn't even put the queue， I think。

 because it will infer it from the assembler will infer it from the width of the register。Okay。

 so there's the prologue， we save the old base pointer。

 we update the new base pointer by copying this whatever the stack pointer is。

 which is pointing to the new stack frame。And then why do we push RBX， what's the point of this？🤧う。



![](img/ddbc8774efa72a0058f10611c2f0b711_61.png)

This is a super subtle question if you were paying attention very， very closely before。

These are registers that。According to the calling convention， the callee is supposed to save yeah。

Would it be a second？Oh， sort of so if the caller。

![](img/ddbc8774efa72a0058f10611c2f0b711_63.png)

In the compiler world， it's easier to think of variables as being associated with memory locations。

 kind of like they have H and G here， but when doing computation。

 you have to move some of that data into registers to do operations， even in the entire world。

 for some operations。so typically the compiler uses registers as a kind of optimization。

For operating on variables。And so what compilers will tend to do is they'll try to keep variables and registers for as long as possible。

 so you know if you have a program with 1 thousand00 variables in a function。

 you only have say 32 registers well you won't be able to hold all variables and registers at all times this is called the register allocation problem so you'll need to swap in and out variable data into registers while you're executing the code if you happen to call a function during that process well that complicates things even more because the function is doing its own register allocation。



![](img/ddbc8774efa72a0058f10611c2f0b711_65.png)

So the conventions。Just define which registers are callee saved and caller saved Scratch registers are ones that the caller。

 I'm sorry， the callee is allowed to blow away。Preserve registers are ones that the col is not allowed to blow away。

 basically。So it's just by convention， you could have a convention that says。

The caller must always save all registers itself by pushing them on the stack or howeverever wants to save them or putting them back into memory。

But this is the。Current calling convention that some are allowed to be overwritten by the function that's being called and some must be saved。

So ESP and EBP are of course ones that must be saved right you don't want to blow that away for the caller because then you'll lose the base pointer。

 you'll lose the stack pointer EBX is by convention and I can't remember what these are for actually。

These are like index registers or something。Or second registers or something like that。

Does that kind of answer your question？So yeah， the registers are not one to one mapped to variables necessarily。

But yeah， you could think that if you could think of it。

 you could think of it in that terms that if the caller had associated variable X with register EBX or RBX。

 then when it makes a call， this convention says the callee must restore the value of EBX RBX when it returns。

 so yeah， you could think of it that， you could think of it kind of in that sense。

Is there another question over here？

![](img/ddbc8774efa72a0058f10611c2f0b711_67.png)

All right， all right， so I think。I feel like people are getting this。

 this is one of the more intricate parts of understanding compilers。

 so somewhat somewhat are getting it。All right， so here's our prologue。

 so that's what the prologue code looks like。And just remember。

 this is code that's generated by the compiler， the compiler is not generating this。

The compiler is generating code that generates the stack frame。

That's the confusing part about compilers your compiler is not。

Figuring out what the whole set of stack frames is going to be。Like the stack。Trace for the program。

 all it has to do is reason about an individual functions， stack frame， construction and destruction。

It's very much like recursive reasoning where。Because each function。

 it's like because each function is guaranteeing that RBP will always point to the current stack frame。

 you can ensure that recursive applications。Of that function will be correct。Same thing in factorial。

When you write the recursive step of factorial， you can write it before factorial is written。

 that's the kind of confusing part about recursion is that the way you make it work is that you just assume first factorial is written correctly just like in math。

 I think you learn this discrete if you have taken discrete right？

You write the in your recursive step， you make the assumption。

That the recursive function is already correct。When you write the proof of it or when you write the program。

In yeah exactly when you do induction when you do exactly when you do an inductive proof of a recursive program or a recursive function。

 it's the same as in recursion， you write the inductive step as saying I'm going to assume that F is correct。

 I'm going to assume that it's correct and it's the same failure。

 I'm going to assume that RBP is correctly managed by the by the caller。

And the caller also assumes that the call E correctly manages RBT RBP and because of that invariant because of that that。

Yeah。

![](img/ddbc8774efa72a0058f10611c2f0b711_69.png)

Assumption that every function makes， you can guarantee that your stack frame will be correctly constructed。



![](img/ddbc8774efa72a0058f10611c2f0b711_71.png)

No matter what your recursive calls are， no matter what order， the functions are called。

So that's a little bit more of a mathy way of explaining it。



![](img/ddbc8774efa72a0058f10611c2f0b711_73.png)

So but that's the main trick of compilers is that you generate code that preserves invariance。

 that preserves the behavior。Of the input program and also preserves。

You know the semantics of how you implement it preserves the behavior of the assembly program。

All right， so that's the prologue。嗯。Here， so for the first cogenn project there's no parameters。

 parameters make things a little more complicated， so you won't have to support parameters。

 this is all the function call looks like for calling funk from me， it's literally just a call。

In assembly and then the label of the function you're calling。



![](img/ddbc8774efa72a0058f10611c2f0b711_75.png)

And so recall that the call function。All right， so to make this even a little bit more confusing。

That prologue constructed。

![](img/ddbc8774efa72a0058f10611c2f0b711_77.png)

The main stack frame。But when we make the call， so this is main， when we make the call。

 we start constructing。The call these stack frame， because remember。

 the collarer main can starts constructing the first half of the stack frame of my fun。

So what does call do， call， so anyone remember what call does， the call instruction does。



![](img/ddbc8774efa72a0058f10611c2f0b711_79.png)

第二。Ah but it does down to a label， but it does something else。It save yeah， exactly。

 it saves the return address first。So yeah， I mean， I'm sort of jumping ahead to the full example。

So this is Maine's stack frame。This is funk's stack frame。

 so when Maine gets called whatever its caller is。Which in the case of like kind of a。Uix world。

Would be start， So this is the。Kind of call lure。Part。Of the stack frame。This is the call E part。

So when Maine gets called。The caller puts the return address on the stack and then does the branch jumps to Maine and that's when mainine takes over and starts constructing。



![](img/ddbc8774efa72a0058f10611c2f0b711_81.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_82.png)

It's part of it。The skip dead。

![](img/ddbc8774efa72a0058f10611c2f0b711_84.png)

So after Maine gets called， that's when Maine starts constructing。

 it's the rest of the stack pointer， so this is the old RBP。And then when main calls a function。

 the first thing it does is it sets up the stack frame， so if there's no parameters。



![](img/ddbc8774efa72a0058f10611c2f0b711_86.png)

What does it do to set up the stack frame？What does the caller have to do to set sec frame？

Except for parameters， if doing so parameters， what does it need to do？



![](img/ddbc8774efa72a0058f10611c2f0b711_88.png)

Just the return address， yeah， so and that's what the call instruction does。

 the call instruction first pushes the return address。And then transfers control to fun。

Funk also has a prologue that does the exact same thing。I'm sorry， return address is not here。

The return address is inside of the functions。Stack frame。

 and when you transfer control to the function， the funk。



![](img/ddbc8774efa72a0058f10611c2f0b711_90.png)

What's the first thing it does when it gets called？



![](img/ddbc8774efa72a0058f10611c2f0b711_92.png)

谁。Where it does the prologue， what's the first thing in the prologue。



![](img/ddbc8774efa72a0058f10611c2f0b711_94.png)

Yeah。Base pointer。So the first thing it does， so this is the。Coer part。And then the callee part。

First thing it does is it sets up。The base pointer saves the old base pointer。



![](img/ddbc8774efa72a0058f10611c2f0b711_96.png)

So I know know it's a little confusing you step through it。

 you'll see that the caller and the call you have to work together to construct the stack frame。

 and it has this recursive nature to it because every time you do the call。

 there's another stack frame。Construction。

![](img/ddbc8774efa72a0058f10611c2f0b711_98.png)

Okay， so that's what call does， call sets up。They call these， funks， stack frame。

 start setting it up。And then once it's done。The know what happens once the call is done so when what happens to the stack frame when？



![](img/ddbc8774efa72a0058f10611c2f0b711_100.png)

The call he has done yeah。やっていく。Exactly， exactly right。

 so it tears down or like updates the stack pointer。To remove the locals。

And then it restores the old base pointer， pops off the old base pointer， sets the base pointer。

And then it's done， it can return now。Because the green part was set up by the caller。

So when you call return， the return function， so this is the。



![](img/ddbc8774efa72a0058f10611c2f0b711_102.png)

This is the end of the。This is the prologue， let me put return value aside for a second。

This is the epilogue， this is the part that。Tears down the stack。

 so we take the current base pointer and assign it to the stack pointer Why do we do that。

 Why does that tear down the stack。So remember when we。否责。The function is done。

 and remember when we set the base pointer we did it by assigning the stack pointer。

So we just reverse that process， we just say all right。

 the base pointer was actually the old stack pointer before we started pushing locals。

 so in order to tear down the locals， we just。

![](img/ddbc8774efa72a0058f10611c2f0b711_104.png)

We just invert what we did in the prologue， the prologue copy the stack pointer or the base pointer。

So we reverse that by copying the base pointer to the stack pointer。

That now tears down the locals from the stack。And then we。

Pop will copy whatever data is on top of the stack， which is now our old phase pointer。

 it's the reverse of push， so you can see here that we have push RBP and moveve RSB RBP。

 this is the exact inverse。We move RBP back to RSP and then pop off RBP because we pushed it at the beginning。

So it's the exact inverse， remember first in， last out， we invert this process。

And what return does return pops off。Return pops off to return the dress and jumps to it for you。

 so you don't have to handle that part。And then that goes back to the。Colllor。Questions on that。

 yeah， yeah。Well， this is for all function calls， the doing it this way ensures that each call has its own stack frame and allows for recursion to work as we expect。

All right。Hopefully I've twisted your brains a little bit trying to reason through this once you step through it it's not too bad and you can just follow the assembly instructions so one last oh yeah yeah。

🤧。We can go over that。Return about， yeah that is exactly what I was going to go to next。

 so the thing to notice here is that the return instruction is not like a return statement in C。

 return statement both transfers control to the callur， but also sends a value to it。

That's not how it works in the assembly world， the assembly world roll return does is pop off the address and jump to it。

 so if you want to pass a value this goes back to the calling convention。



![](img/ddbc8774efa72a0058f10611c2f0b711_106.png)

The return value by convention is passed through。A register。And so in our。Convention。

 this is in Reg A RAX。

![](img/ddbc8774efa72a0058f10611c2f0b711_108.png)

So the return statement in our language is going to just set that register。

 it's not going to actually transfer control， it's just going to set the register。

It's the epilogue of the function that transfers control。ちたれた。こや。



![](img/ddbc8774efa72a0058f10611c2f0b711_110.png)

Oh so well only one return re will be used at a time， so yeah if the callerer wants to also use it。

 it's going to have to overwrite it once it's done with the return value。Yeah。

 so these are not like in parallel， they're like linearly called。

 so at least yeah not in this framing。

![](img/ddbc8774efa72a0058f10611c2f0b711_112.png)

来了来。All right， questions on that。Yeah。So we'll go over parameters next week。

 it makes things a little bit more tricky， but all you really do is you have to add code here in order to copy the parameters to registers or push them onto the stack before the call。

Oh for the return。So the reason is the locals get handled by restoring the stack pointer。

But the parameters were handled by the collar， so it's the collar that has to。おい時間。

So this is the tricky part， so shows a call this both a calller and the call E。

So once the we'll talk about parameters， but basically you push parameters before the call and pop them after the call。

That's how it's going to work， but we'll get there， we'll get there。Okay。

 so I think we kind of already went over the stack frame stuff。 So let me give you a preview on the。

 let me let me go over the project for。 So any questions on。How this function calls work yeah。

Concepts， does it apply to like to most？I know the registers and stuff are different。Yeah， yeah。

 yeah， yeah， whenever yeah， whenever yeah， yeah， most yeah。

 mobile systems will have an application binary interface。

 an interface for how to call functions between a convention that the compiler and the system will use。

Yeah。Yeah， this is the classic way to do it for compiled languages to like machine code。Yeah， I mean。

 there's not a huge amount of diversity in like processor architectures these days。

 right it's like X 86 or armed。are probably the vast majority， at least for consumer devices。

 but I think even any any and C is like all over the place， so this is the semantics of a C function。

 how C function works。Yeah。The caller will get that value so you as the compiler writer。

 like when you write a function in C and you write a return statement。

 you don't care what the caller does， right？Like the when you write the call E function。

 you don't have to consider how the caller is going to use it， you just return it。

So it's the same thing here， you just set this value and it'll be in the register when controls transferred back to the call。

And so it's up to the caller to handle this return function we'll talk about that when we talk about like variables and calls next week。

Our variables is in two weeks。All right， so that's the calling convention， you know。

 take some time to wrap your head around it， it's a short piece of code。

 but it's sort of sort of dense， how this actually works。



![](img/ddbc8774efa72a0058f10611c2f0b711_114.png)

All right， let me go over the project。

![](img/ddbc8774efa72a0058f10611c2f0b711_116.png)

So everyone is at least ready to get started on it。



![](img/ddbc8774efa72a0058f10611c2f0b711_118.png)

So in this version of the project， all you'll have to do is。Compile。

Functions that compile programs that define functions and call functions， that's it。

 so let me give you a full example， So this is the most you're going to have to compile yeah。



![](img/ddbc8774efa72a0058f10611c2f0b711_120.png)

Oh， yeah， sure。So this is the most amount of。Constructs you're going to have to compile。

You'll compile functions， function declarations， return values and calls。

 and you won't even have to handle variable assignment。

 so the syntax of the language requires storing the return value。

 but you can ignore it for this project because I just want you to get generating this。

You knowProlo and Appleloin getting function calls interoperate and if you get this working you'll actually be able to call C functions。

 you can actually write and I'll show examples when we get to the full compiler。

 this is the same ABI that the C compiler uses so we can actually call C functions and C functions can call your functions because we follow the AI。

Yeah it will， so I have some so I'm assuming everyone's going to get Cogen1 right I might be wrong。

 but the other ones I have ways to be able to grade it without you getting every part right so I tried to break so it's actually going to be like four separate reos。

It's really gratifying， I think to have a full compiler working and you can do this if you like at the end and compile it all together。

 but we're going to try to grade them separately。But yeah。

 the second one does kind of entail the first one， but I hope the first one is， what's it？Yeah。

 all four of our。哦，不为来看。

![](img/ddbc8774efa72a0058f10611c2f0b711_122.png)

With each other。It is， but it sort of penalizes you if you get the codegenn3 right。

 but you didn't get codegenn2 right。

![](img/ddbc8774efa72a0058f10611c2f0b711_124.png)

They're divisible， they can be divided up one and two you may have problems div it up。

 but I'll try to make sure everyone gets cogen1 right。



![](img/ddbc8774efa72a0058f10611c2f0b711_126.png)

The code for it is pretty straightforward， but you have to understand the calling conventions。



![](img/ddbc8774efa72a0058f10611c2f0b711_128.png)

So the most you'll have to compile is programs that look like。



![](img/ddbc8774efa72a0058f10611c2f0b711_130.png)

This。And you'll only have to do the call part， you won't have to save the variable。

So you'll just have to compile programs to look like this。

 and then this is an example where we have two functions that one calls each other。

 so mainine calls funk andk and you only have to return constant values。

And this is what the code looks like when you generate。We need generate these programs。

 so this is generating main， this is generating funk。



![](img/ddbc8774efa72a0058f10611c2f0b711_132.png)

So you can see that this looks exactly like。The code that I just showed you actually。

 it is the same code that I showed you。

![](img/ddbc8774efa72a0058f10611c2f0b711_134.png)

All right， so to do this。

![](img/ddbc8774efa72a0058f10611c2f0b711_136.png)

Without any the details of antler。

![](img/ddbc8774efa72a0058f10611c2f0b711_138.png)

You only have four functions to write。And so actually I have the same example。

So this assembly file metadata， you'll use the enter unit function， so I've given you this already。

 so you can just copy this。

![](img/ddbc8774efa72a0058f10611c2f0b711_140.png)

This template。This Python code， you can just copy this。

Hopefully the indentation will work because this is text and you only have to implement these four functions。



![](img/ddbc8774efa72a0058f10611c2f0b711_142.png)

Enter function， exit function， enter return enter call。

 and I've given you a little mapping here between what parts of the assembly file correspond to which parts which functions you implement them in so enter unit is given to you。

And this just you know generates this this code here， so notice here that it's you know in Python。

 this is just writing to an out file and this is just text。



![](img/ddbc8774efa72a0058f10611c2f0b711_144.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_145.png)

So keep in mind that compiler is literally just generating text， it's not running anything。

 it's all computing of value。It's literally just read text。And print text。

 so it's printing out this exact text。

![](img/ddbc8774efa72a0058f10611c2f0b711_147.png)

That is in the。嗯。The pseudo ops of the compilation unit。So for the function label。

 you'll do this in enter function。And the only thing that changes between programs is this name Maine。

So you'll generate a string。Let's see how much。Let's see how much I。



![](img/ddbc8774efa72a0058f10611c2f0b711_149.png)

K remember how much I gave you？So you'll generate a string。

And in order to figure out what the name of the function is in the input program。

You just use CTx name， so this is the part of the tree that holds the name of the function from the input program。

 and so you use that。To fill in， I think of this as a template where you just fill in。

The name of the function here， and then the prologue is identical for all functions。

At least without local variables， it's the same for all functions。 So you can just。Hard code。

 this string。Being print out。And enter function。没嘢。一证据。All you know it strings， yeah。

 so you'll literally just you can just literally copy this。



![](img/ddbc8774efa72a0058f10611c2f0b711_151.png)

And you can check out the you can kind of。Draw some inspiration from how this is done in Python。

 you can have multilined strings in Python。And this is how you can insert。A variable into the string。

 you use these curly braces， and I think I write this in the instructions as well。

 you can use these curly braces to do it， so this will just print yeah。What's it it's like F string。

 yeah， it's like F string， except you can actually put the variable name inside。

 you don't have to do the whole like F print F thing。

So between curl braces and note that these you use these triple quotes to have a multiline string。

 and this quote is actually being print out。So you won't have to use quotes in what you bring out。

 But so what that means is you can actually just literally print this out， you know。

 the first step you can do is when you write enter function。

 you just literally say self that out file this string。



![](img/ddbc8774efa72a0058f10611c2f0b711_153.png)

I would do that first if you get that working， you're already like a third of the way there。

then the only thing to do next is just to。Parameterterize this part of the string here。

 you just say curly braces and then， you know。

![](img/ddbc8774efa72a0058f10611c2f0b711_155.png)

Ctx。 name because that gives you the name of the function。



![](img/ddbc8774efa72a0058f10611c2f0b711_157.png)

For these three spots， and that's it， inter function is done。

And so now you have a compiler that will generate。For any function given。

 it'll generate the label of it and then code that will create the prologue。



![](img/ddbc8774efa72a0058f10611c2f0b711_159.png)

So like in terms of a program， this is not that complicated right。

 you just literally print out a string， it's the working out of the pro epi in the stack frames。

 that is the complexity here。

![](img/ddbc8774efa72a0058f10611c2f0b711_161.png)

So exit function will run once you've。So， it's。Yeah only have four minutes。

 but it's basically a tree traversal of the simple IR tree。

 and then the exit function runs after you've seen all of the children of the function。

So exit function you just print out the epilogue and this is just hard coded。

 this epilogue is going to be the same for every function so you literally just print this out to the file。

 self thought out file do right this string。AndThat's no parameterization， no。

 just literally hard code this string。Pretty simple， right as a compiler。

 sort of it's working out what you print out if that's the hard part。

 but the actual compiler itself is literally just printing text， just printing assembly text。



![](img/ddbc8774efa72a0058f10611c2f0b711_163.png)

So for calling functions， this is also pretty straightforward。



![](img/ddbc8774efa72a0058f10611c2f0b711_165.png)

It's just call。

![](img/ddbc8774efa72a0058f10611c2f0b711_167.png)

Factctorial。So I've given you a little code to figure out from the tree。

 which of the names is the function name。So， this。I think I showed the IR a little while ago the grammar of the IR。



![](img/ddbc8774efa72a0058f10611c2f0b711_169.png)

I put this。And so you can sort of learn this as you go， but the way the grammar works is that。嗯。

The syntax of a call is for some name for the variable to store。The assignment operator。

 the call keyword， a name of the function of n0 or more names of the parameters。

 well I'll go into this a little more next time when we have to do more complicated constructs。

But in antler you can just pick out which of these names you want。

 you can just treat this as an array of names which I give to you。

 and I tell you which index will contain which parts of the construct， so just run this code。

 write this code。

![](img/ddbc8774efa72a0058f10611c2f0b711_171.png)

And just get used call1 in order to get the name of the function。 And so in order to generate this。

 you literally just print out。Call and then whatever this name is。That's it。



![](img/ddbc8774efa72a0058f10611c2f0b711_173.png)

To do the call。So return value is similarly simple， you just print out a move。



![](img/ddbc8774efa72a0058f10611c2f0b711_175.png)

Immediate to RAX。

![](img/ddbc8774efa72a0058f10611c2f0b711_177.png)

To get this value， it's the same idea， I've given you code to do this。

 you just use this CTX operaot text。

![](img/ddbc8774efa72a0058f10611c2f0b711_179.png)

Just use that variable and you'll be able to get this number。



![](img/ddbc8774efa72a0058f10611c2f0b711_181.png)

From the tree。We'll go into a little more detail next time about how we actually how the tree actually works。

 but if you just follow the schema，Literally just print this out and then parameterize the text of the immediate value using CTS and opera text。

 so this code here， this CTX， this is just antler's library for getting the text that's on the parse tree that's all it is that I'm giving you the actual Python object to use to get that text。



![](img/ddbc8774efa72a0058f10611c2f0b711_183.png)

But you know， start out by just printing out the built in text。

 don't even worry about the parametervaitization yet and see if you can get a working program that just literally prints out assembly。



![](img/ddbc8774efa72a0058f10611c2f0b711_185.png)

For these four functions， enter function， exit function。Call enter call and enter return。

 so these are the four functions here。

![](img/ddbc8774efa72a0058f10611c2f0b711_187.png)

So you have the actual assembly text to print out and then once you get that working。

 parameterize it， use the format string to。Have the function names that are for the call and for the definition。

All right， questions on that in our last minute。So try it， ask questions next week and off hours。

 ask me next time in class， I hope that's pretty straightforward， I hope everyone will get this one。

Yeah yeah he did the project he did the project yeah he's going go over it you got ask yeah go to lab and he he will show you this as well so I hope everyone will get this one I tried to make this one pretty straightforward so yeah all right everyone have a good one。



![](img/ddbc8774efa72a0058f10611c2f0b711_189.png)