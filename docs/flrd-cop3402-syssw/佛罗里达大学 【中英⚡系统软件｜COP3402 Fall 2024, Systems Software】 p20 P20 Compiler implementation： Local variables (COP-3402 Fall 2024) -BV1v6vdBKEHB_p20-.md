# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p20 P20 Compiler implementation： Local variables (COP-3402 Fall 2024) -BV1v6vdBKEHB_p20-

back to system software， we're in the middle of looking at how functions get implemented by the compiler by translating to assembly code last time we looked at last week we looked at functions kind of abstractly in the computing world and we looked at how we can actually implement functions in assembly and today we're going to show how we manage variables how we manage local variables to functions。

How we generate code so that we can read and write。

Memory locations that are associated with these variables。呃。And let's see homework 16。

 shouldll go over homework 16。What's that？Oh you did， okay， so if you went to lab。

 he would have done it for you， so let's just go over quickly。

 kind of a quick review of function implementation。

Which assembly instructions make up the prologue of the function？我怎么我别我别人不会想告。And call。

So yeah it's not not enough to look at this， yeah， it's the push saving the old base pointer。

 setting the new base pointer。And saving the call saved register。

Now this function has no local variable， sos that part of the prologue is not there。

 which instructions are the epilogue？Yeah。なり？Yeah。That's right yeah。

 yeah I don't I don't know if the return is actually included in the epilogue or not I'm actually not sure。

 so if you said either I either is fine， but this is definitely part of the epilogue restoring the。

Tearing down down the stack。And restsoring the old base pointer。I forgot to pop RBx。

 I hope we should do that as well。Okay， what's the function call，'s call？Of course， oh yeah。

 what does enter return generate？嗯。Which move there's three moves here。

Copying data into the RX register， according to our calling convention and its System 5 AMD64 applicationplication by interface。

 RX should hold the return value when you return from the function。Questions on on any of this。不在哪有。

Questions on any of this。Okay。Okay， so let's quick review what's a function in the computing world and the programming language world。

Yes。否则。Yeah， it's like a set of instructions， you can name them， there might be anonymous ones。

 and they have inputs and outputs。That's basically what the simplest version of a function is。

How do we implement functions， but specifically ones that have their own local state and work with recursion？

We use the stack， yeah， we use the stack we have， and what do we use the stack to do？

What does the stack hold for each function？And is that for each function？

For each call to the function， so every time there's a new call， we generate a new stack frame。

And the tricky part about this is that's not allocated at compile time so we can't just。

Decide on one memory location for function， the functions local variable x。

We have to generate code that will make this memory location when the program runs。

 and that's the tricky part about implementing these functions that we're not。

Figuring out what the memory allocation will be at compile time instead。

 we're generating code that will cleverly。Do the d allocation of memory at runtime when that code runs。

 but we're actually not going to know where or how many frames of the stack we't necessarily need。

ぜと本でき。よせか。Oh so yeah， Malk does go under the heap。But the stack is not managed by MalC。

They're separate。参にか。They do what。通ての。Well， the stack frames are different for each call of the function。

的这个。Even for the same function， you'll have multiple stack frames for the same function。

Like in the factial case。So they call factorial。Right， theyre the same shape， yeah yeah。

So wait sorry what's your question？せさす。Yeah， that's exactly the right， yeah。

 as we talked about last time what we' talk today， because we require or at least in C C requires the developer to tell you how many variables you have and what types they are。

 and that's exactly right so that compile you can know at compile time very easily exactly how much space you need for each stack frame。

And that does indeed make it easier to generate code that creates these stack frames so yeah that's exactly right there are schemes where you do use the heap for functions as well。

 for instance in functional languages where the lifetime of function can exist past past the lifetime of the stack but that's more advanced topic you look at how functional languages are compiled functional languages functions themselves are also values that can be passed around。

Including functions that have been。嗯。Have。Have in scope variables from their parent function。

 but this is kind of an advanced topic， how you actually do that and that might can involve the heE。

But anyway， for our C like functions， we use a stack。

 we have one stack frame activation record for each activation or instance of the call。

And so we looked at last time co generation for what I might call simple functions have no parameters。

 no locals， just constant return values。And we gave you this example in Co N1。

 where we just have one simple IR function called mainine。

It calls funk and assigns whatever its return value is into a variable。

 I call this phoievar because for Cogen1 you don't have to actually support variable assignment。

And we have a second function here called funk， which just returns five。So if I call Maine。

 what's the return value of Maine？1，Yeah， so it calls funk， gets return to value5。

 but it doesn't do anything with it， and then just returns 10。So the approach to doing co generation。

Was to whenever we see this function declaration。We declared it an assembly with those pseudoops。

 give it a label to jump to， generate the prologue， and once the body is done。

 we generate the epilogue， that's what the exit function。That antler gives you does。

When there's a call， we just generate the x86 name call because there's no parameters here and when there's a return。

 we generate a move instruction to RAX so why do we have a move instruction to corresponding to our return statement？

とについぶ。Yeah， so this is the calling convention that we're given that if you want to return to value and you want other C functions to interoperate with you。

 you store the return value in RA。So this return statement does not exactly correspond to the return in the X66 world。

All right， so let me step through that cogen， this is really like cogen1。呃。There is。Okay。

 so let's let me step through。The co generation here。Okay， and we see function main。

 what do we generate？For function main。At compile time， so at run time， yeah， stack will be created。

 but what assembly code do we generate？In our compiler when we see a function declaration main。Yeah。

Yeah， so we'll create the assembly declaration， the label to branch2。And the prologue。Okay。

 so that's this code here。This is what gets generated。That's right。

This is what gets generated by Maine。それそろ。So whenever you have mean。That generates。This。

Declaration of Maine and the prologues。So that's enter function。In。Program。Okay。

 what about this call， so remember in Code Gen1， you don't have to support return value。

 so what gets generated？When we have a call。s thatWhat gets generated when we have a simple IR call？

Yeah， just there's just an assembly。Instruction called call。And because we've used the same label。

As the name of the function that was given to us， we can just use that label。For the x 86 call。

 So this is the x86 call， not the Ir call。 Now， there'll be more to do with this if once we have。嗯。

Once we have to deal with parameters and。Recurrent values。

 but that's all we need to generate for CoN1。And what about return。

 what do we generate when we have a return？Yeah，不 that。h， not right，あ。Exactly， yeah。So remember the。

Behavior of return in。The X86 world is storing a value to RAX because that's the calling convention。

The rat is really part of the epilogue， you can't return until you've torn down the stack。

And prepared。The stack for the return， yeah。Yeah， these so they you mean the enter function， Yeah。

 that's exactly right so this is。Enter。Color here。This is enter call。And our return。

IR instruction corresponds to a move and assembly because we want to store this。Value in RAX。

 whatever their value is。The exit function happens when。We reach the end of our function block。

 so this is the function block and at the end of it。Antler will。Ca。Exit function。For us。

And what happens on exit function， when we're done processing。

 we're done compiling the entire function。对。So yeah， good memory of the epilogue， yeah， the epilogue。

Which is， and I'll post it here。The epilogue。Which， as your。Fellow classmate remembered is。move。

 restore the old base pointer， I'm sorry restore the old stack pointer， restore the old base pointer。

 and then call the X86 return and what does the X86 return instruction do。

 it doesn't copy a value to RX， what does it do。Doesn that remember， was it？这个。啊，直接。

It takes you yeah， it takes you back to the caller and the way it does that is it pops the return address off the stack and then branches to that address。

 so return it doesn't behave quite like return in C in C。

 it's taking the value and replacing it replacing the call E at the caller site and also restoring Cl of control。

 return in the X86 world all it does is pop the return address and branch to it， that's it。

 it doesn't do any value saving or transfer for you， that's what the move instruction does。So。

 this is。Andter return。So questions on this， questions on this co generation。イメで？れ在に。Oh yeah， yeah。

 for， so i types are for immediates。Yeah， that's right， you use a different operaand。Yeah。

 and there's a whole bunch， there's like a huge number of move instructions in the Intel world。

And we're going to see another one of those today。There are I， I was thinking of meant like I add。

 there's integer versus floating point instructions， but that's a different story。Questions on this？

So hopefully this is a helpful guide to。What code Gen1 will do and I've given you like the Python code for for doing this。

 so most of this is just let me actually take out this。Comment here， this is maybe not。

The least confusing thing。So your your implementation of these four functions are almost entirely just going to be literally printing out this text。

 the only place where it's not printing out this text is，嗯。When it。I guess I can't highlight。

Is when it oh I can't do that is when it uses a name given in the IR so when we declare a function。

 we ask the developer to give us the name and we use that name in these three spots here when we generate the function definition and prolo and assembly and same for the call when we generate the call。

We used whatever name was given to us。In the syntax street given to us by the developer。

And for the return as well， whatever number was given， we just plug it in here。

But all the rest of this is literally just you just literally put that string in Python and print it in Python。

In the way I show you in just what is it out file dot right？This one。The exit function。Yeah。

 this so exit function will Okay， so the reason this happens is。

What antler is really doing under the hood is it's creating a。Syntax tree。

That consists of a trying to remember。My grammar。We have。

A unit as the root of the tree underneath a unit。Is a function？Underneath a function is。Many things。

 it includes the function keyword。It includes some name token。And the。

It includes several other things， including the return。So what exit and En do is。

 if you remember several lectures ago， how did we write a translation。

 how did we write the translation from Inf to postt using our grammar based approach。

 our tree based approach。Yeah。Yeah， you traverse the tree。And on each of these nodes。

 there's a rule for how you generate the output。And so you're doing the exact same thing in your compiler。

 except all the tree generation and rule calling is done for you， the traversal is all done for you。

You just have to write instructions on what happens on each node。嗯。

And so that you can do both preor and post order style transformations。

 antler gives you both enter the name of the node and exit the name of the node。

So when enter will be executed， so there's always a tree traersal of a complete tree revverersal of a tree。

You know， from left to right on the children。And whenever you enter the node。

Enter function as called。And after enter function is called all of the children are processed。

 so the function keywords， name， locals， et cetera， return。

And then once all the children have been processed and we're back in the parent。

 then exit function is called。So this gives you this nice nested structure to function to where we can put code that comes before the body。

In enter and code that comes after the body and exit。Does that answer your question？

So I didn't go too much into the details of Antler， I just kind of gave you the instructions。

 but that's what's behind enter and exit and I think for all everything except exit function。

And I'm even thinking that maybe I should have designed it so that you didn't even need exit function。

 but all the rest are just going to be entered if I'm remembering， right？For this IR。

 you won't have to ever use exitO again， so you can think of it as just one rule for each node when you traverse。

It tras the tree。All right， that's a good question though， all right， questions on how Cogen1 works。

Okay， so this is similar， Ill leave it that as an exercise to you to work out or test it in your cogen。

So this is compile time。This is what your compiler does。

But the tricky part to wrap your head around is that no actual stack frames are being created here。

Your compiler is literally just printing out text， it's literally just printing out this text as a string。

The compiler doesn't have。Any understanding of what this text is。

 you as the rule writer are writing the right， the correct assembly output for each of these constructs。

 but the compiler has no sense of what is happening with this at runtime。So this is compile time。

Runtime。Is what the computer does when it executes the assembly code。

 the assembly code that your compiler generated。 And at this point， your compiler's work is done。

 The compiler is not doing anything else at this point。 Now， it's all up to the。

Operating system and the machine。To execute your assembly code。

 and if your compiler is written correctly， it will execute and give you the same input and output for each function。

That the meaning of your input program would give as well。Does that make sense， this distinction。

 compile time？This is。This is when your compiler runs， so this is the runtime of the compiler。

But we call that compile time in the compiler world to distinguish it from runtime。

 that is the runtime of the output program when the output program runs。So let's work out what。

This just to illustrate again， how functions work。At runtime。

 the functions that we generated so cleverly with our stack allocation， how these work。

At when they actually run on the machine。Just to review。

What the machine does with this assembly code。O。All right， so in order for this to be kicked off。

 the C runtime actually calls mainine for you， that's why mainine is a function because。

You can think of it as the system itself calling your main function。

It's a little out of scope of this class， but you can just think of when you exec。Your program。呃。

What Exec will ultimately do is end up calling Maine for you。

So there is stack a stack frame effectively being set up for Maine。

 but let's just pretend that main is， there's no arguments being passed to it and we're starting with a fresh stack。

So we call me and there's no。There's no。Local variables here as well。

So here's our stack and we grow downwards。With our stack。

We call Ma in what is called do in the X86 world。What does the call instruction do？Yeah。

It creates a new stack frame for the return address。

So there will actually be a return address back into the C runtime。Don't worry too much about this。

 I have links to details if you actually want to see how the sea runtime works。

And then what does it do， so it pushes the return address and then what does call do？

And how does it call it？Yeah。Well， even before we get here。

 how do we get to the first instruction of meeting？Well， there's no tree here， right。

 this is the assembly code， yeah。Yeah， so what call does， call is really a branch instruction。

Call is very， very similar to a branch instruction it's a branch instruction that first pushes the next address。

 the next IP， the instruction pointer in the intel world， and it branches to this。This。Line of code。

In the binary file， now we talked a little bit about linking and how de executables machine code。

 and there's a linker table that tells you where all the functions are。But when Maine is called。

It's effectively a branch to whatever memory location。

Main's instructions are stored in your executable file， which aren。Put in memory by exec。

So call will change the instruction pointer。To be the first instruction of Maine。

So now we're actually executing Ma。So what's the first thing that happens in Maine？

We push the old base pointer。So， let's say。We have。RBP is pointing somewhere。Up the stack right now。

And when we push it， we save。A pointer。To the old。RVP stack frame。

 the stack frame that it's pointing to。This kind of pseudo stack frame of the sea runtime and then what's the next instruction？

And here's a pointer to our stack pointer because after we push。

We update the stack pointer to be the top of the stack， so what's the next instruction。

 we copy the current stack pointer into the base pointer。So this updates。

The base pointer to now point to。This part of the stack。So RVP now points to。

This entry in the stacks， it's basically the middle of the main stack frame。

And what's the next thing we do， we push whatever the value of RVP is。So this is going to be the。Old。

All right， sorry， RBX。And what happens to the stack pointer after we push？

Stack pointer gets updated to whatever the new， so all push does is it does a move。

 a store to memory and then increments the stack pointer。By by the width of whatever you're pushing。

So questions on this prologue， behavior of the prologue in the stack yeah。Move is copying。

So what's more useful seeing arrows for pointers or actual like concrete numbers？Arrows， okay。

 so let's keep arrows， let me go through these steps。One more time。

When we're here at the first instruction before we execute the first instruction。RBP。

Is pointing somewhere。Earlier in the stack。And our stack pointer is pointing here at the top of the stack。

So we push RBP。The old RBP， whatever this RBP is。Gets。

copiied onto the stack and RSP is updated to be the new top of the stack。

Now before and then when we execute this move。It copies。Whatever this stack pointer is into RVP。

 so RVP now no longer points to somewhere off the stack。

 now it points to the current top of the stack， the same place that RSB points to。But is copying。

Whatever the value of RP is and copying it into RBP。

So if you prefer the arrow sort of pointer based approach。

 that means these two have the same memory address。this is memory address。Zero，4。

Then both of these now have the value。Zero x。Zero4 is probably not a good。Addres he is。

That's just say， decimal 8。I'm just going to number these。With just a decimal integer。

 So now both of these。Have the address8。Yeah。Why do we save the old base pointer？And' remember。

So we can get back to the callers。Sack， we'll see that when we enter funk。

Was there other question over here？Okay。And then we call push RBX that just。

That just saves the old value of this register， we're not even going to use it here。

 but it's required for the。Colllin mentioned。Okay。So now we finish setting up our stack frame。

For men。So this is Maine's。One call of Maine's stack frame。All right， what about call funk。

 what happens when we run call funk？Okay， but what are the two steps at the yeah。

 machine level that happens yeah？Right。Exactly right。

 so what the call instruction but the two steps it does in the X86 world is it saves the return address。

电咩。Which is going to be this return address。 So if this is。Line 1，2，3， four， say this is line four。

 then this says line  four。Well， this is a different memory space。This would be something higher。

 let's say， it's like 104。Then it saves the basically it saves the address of this instruction in memory。

That's what call does， it saves that and then it branches。

 so if this arrow is our instruction pointer， it then branches the fuck。

 which puts us at the beginning， the first line of。Questions on this。So here is our。

Saaved stack frame on the stack for。Ourre call to Maine。And this。Execution of call。

 pushing the return address starts creating the stack frame for fununk。

Where does Cal say the return address do to the stack？So call pushes。To the stack and all this。

Updates。RSP。To be。Whatever the new top of the stack is。

And so this is starting to construct the stack frame for funk。Right， yeah。

 save inside bunk stack frame， say inside the stack frame of the call Lee。

Because we're going to have a I mean。This is the calling convention。

 you could imagine doing this in different ways。Probably possible。

Whether you consider this part of the collar or the calllie is almost。Irrelevan at this point。

 it's stored onto the stack。At this point， know when you first make the call。

But it's considered part of the。Call lease stack。Okay， so let me。Yeah。

That when there returns how to go call one04 again。系了。Oh sorry about that， yeah。

 this should be like 105。So it actually stores current instruction pointer plus one instruction。

So good， yeah， that a good that's a good point so it actually。Recors the next instruction pointer。

 I guess you could make the return add one to it， but I think the current X86 instruction set adds one to the return address to find the return address。

Or adds one instruction to it。Okay， so。Our stack pointer is here。

 our base pointer is still on the old stack frame， on main stack frame。

So what's the first thing that happens in funk？We push the old art base pointer， which is here。So。

Since you like the pointer？Diagrams， this points to。This memory location， this is what RBP。

 the address RVP has eight。So this is storing the address8 on the stack。

And RSP gets updated to whatever the top of the stack is。Questions on that， everybody good so far。

And now we execute the next part of the prologue。Whi just copies the current stack pointer。

 which is pointing to。Adddres 11， and it copies that into the RVP。Register。

So that has the effect of making RVP。Point to the same memory location that RSB points to both of these point two。

Adddres 11， so these have the address in this in the register， the register is holding。Addres 11。

Questions， questions on that。Okay， so then we push。Whatever RBX was。

This is just part of the calling convention， and this updates RP leaving RVP to continue to point to。

Where we just left it， we left it at the whatever the stack pointer was before。

 this is where RVP is currently pointed to。All right， any questions， questions on us？All right。

And here we have move immediate 5 to RAX， what did this correspond to in simple IR。

 which instruction yet？Good， yeah， this was the return。

 and so the RAX register is now going to hold the value five， doesn't do anything with the stack。

Could potentially store this on a stack， but this current calling convention does not do that。

And now what part of the function is this？Epilogue good， so what does the epilogue do。

 what's the first thing it does？对。That's right， so it updates RSP to be whatever our BPP currently is。

This has the effect of destroying whatever this function pushed onto the stack。

It's reversing this move， so you can see it's the opposite of move RSP to RBP。

 this is move RBP to RSP， so it undoes whatever stack stuff you put on the stack here。

It effectively pops it now the data stays there， but because the stack pointer is here。

 any future pushes will overwrite that。So we can think of this as tearing down the stack or popping from the stack。

And then we pop RBP。What does this do， how does this change yeah？Good， yeah。

 so what this does is it takes whatever value is at the top of the stack。What just so happens to be。

The old base pointer that we pushed。Because we popped all of the stuff that we put on the stack after we pushed the old RVP。

And now we just take that old RVP and pop it into RVP， which has the effect of restoring。

RBP to be Maine's base pointer。Yeah。No， the top of the stack right now， so the top of the。

So before we started the epilogue。The top of the stack was here。And RVP was here。

So when we popped this， well， when we did this move， this has the effect of。

Ppping everything off of the stack after。Where RVP is pointing to。Yeah。

 it effectively removes 12 because our stack pointer is now pointing lower or well。

 higher in the address than the stack。So you'll no longer access this through kind of official means。

So now the stack point in the base pointing at the same spot and this spot this part of the stack frame is what was holding the caller as means。

Base pointer。So now that we're here， whatever we pop。Whatever we pop into well now have this value。

 so we pop it。Into RBP， this has the effect of restoring RBP to you know， to assigning to8。

 This has the effect of restoring RBP to be the。Base pointer we had before we called funk。Questions。

Pretty good so far， I hope。嗯。And then finally。So now when we do that pop， now RP。

Is pointing at the return address， the stack the entry on the stack that holds a return address。

 so when we call return or return does。Is it pops RSP？

And then branches to whatever this return address is。

This return address is 105 so it ends up starting restoring the instruction pointer to be this address and then continuing to execute。

 that's how we restore both the stack frame and the position。

 the line in the main that we want to call next。Yeah， 11 to 10， 11 to 10 is because of this pop。

10 to nine is because of return。Return pops the return address and then branches。So just like call。

 so these are all inverses of each other， so call pushes the return address， then branches， return。

 pops the return address， and then branches。And。The epilogue and the prologue are like inverses of each other。

The prologue pushes stuff onto the stack， the epilogue pops that same stuff from the stack。

Restoring the state of the pointers。In a process。All right， questions， yeah。Not the stack frame。

 but the。So the stack frame consists of multiple entries， I don't know what you。Yeah， the stack yeah。

 every time you call pop the stack pointer is adds one。Because the stack grows downwards。

In address space， so pushing the stack subtracts the stack pointer。By。

Eight bytes popping ads eight bytes。One entry into the stack。All right， questions， questions on that。

Hope that clears some stuff out but the main distinction here is compile time where there's no stack frames involved at all here directly。

 or're just generating code。The cleverness comes from generating code that will at runtime exhibit this。

Stack frame management behavior， that's the really the hard part about compilers。

Is ensuring that this will happen at runtime， even though at compile time。

 we're not literally computing。These addresses or these sets of stack frame。

We're generating code that will。Generate those snack。All right。So that was the runtime behavior。

So 20 minutes get a little break， I know that's probably maybe it's warping your head a little bit exercising your brain a bit。

Step through it， follow the instructions and it' hopefully it'll make sense and in CodeN1 I've given you the code to generate and then you can test。

 you can use GDPB also to step through， just test to make sure that this is what's happening。

At runtime after you generate the code。Okay， so let me show how local variables work。

So where are local stored？For when you have function local state and C like functions， yeah。Well。

 the API tells you how to store them and in our API， where do they get stored yet？Okay， fert well。

 okay， so some locals are stored there。Stack， yeah， and the stack frame。So locals。

 strictly speaking to， the locals are stored on the stack frame and in our IR。

 all locals will be stored on the stack frame。So recall the ABI。Probably should have linked to the。

Yeah， here's the A， so recall our AB。Just showed this in our diagram where we have the return address。

 the saved RBP， the locals。Are stored here on the stack frame。

In functions that have local variables after the prologue。

We allocate space on the stack for any local variables that we have。In our function。

So after that prologue， we're going to just push enough space onto stack to hold all of our local variables。

Questions， questions on this。Okay， so let's show。

![](img/b83f00d1bb2a099d09e8e73a043b9d1a_1.png)

This example here。So remember， the stack frame is what's created at runtime。

 but it helps to diagram what this stack frame will look like because as some of you correctly observed。

 the stack frame will have the same structure， have the same size。For our functions at runtime。

So for this function， the stack frame will have。We don't have any parameters。

 but it will have the return address。Just like before， it'll have the old。

Base pointer just like before。呃。Am I forgetting anything？So return address all days Twitter RBX。

 let's forget about that for now。And it'll have whatever the local variables are and conveniently in our language。

The developer has to just give us a list of the local variables。

 so there's three local variables here。And in our language， our simple IR。

 all the variables have the same size。all the same bit with and they all happen to correspond to one entry on the stack frame。

 so all we do is we push or allocate enough space on the stack frame for each of our local variables。

Now， conceptually。This will correspond to v1 x。And RE Val。But in our Gene assembly code。

 there's no need for actually storing these symbols anywhere。These symbols will， for instance。

 so X86 assemblyly will not process these symbols there， they correspond to memory locations。

But you can think of these as corresponding to。呃。to the variable names that the developer gave us。

 but really we're just going to allocate enough space for them and then use some clever tricks to keep track of which space corresponds to which variable when we generate code。

So questions on this。Kind of stack frame template that we have for。My fuck。

So that's what the stack frame will look like。So the question is， how do we translate these？

AsI strings， these are just ASCI codes。 How do we translate these into something that we can use to store。

Data during the runtime of our program。We talked about this a little last times。

 I don't remember yeah。Exactly right， yeah， so the key trick here is that because we've maintained this space pointer。

 we've maintained in a pointer。To this stack frame。

We can translate these variable names into offsets from the base pointer。

It's because we know exactly how many variables are going to be， we know what their bit width is。

We can replace whenever we see a usage of those variables， a store or a load to those variables。

 we can replace it with。RBP minus some offset for that variable。

And what we're going to end up doing at compile time， so this is the runtime view。

 but at compile time。We're going to construct the table called a simple table。That's going to store。

For each symbol。Or each variable name。It's going to store。The offset from RBP。

So I think the first offset' is going to be negative 16 of them remembering right， how I design this。

Actually， let me double check my code。Oh no， starts of negative8 starts negative。

あ you can't see that。All right， so what the simple table will'll hold each of our。

And this is remember， this is a compile time， it will hold a mapping from the variable name to an offset from RBP。

So in our language， each of our variables is eight bytes wide。They're all the same width。

And so we're just going to in our compiler， keep track of these offset sets for each of our variables so that when we have assignments or usages of those variables。

 we'll be able to translate that variable name。Into a move instruction that will。

Compute the address from。Looking at RBP。And adding one of these offsets。

 their negative offsets will add them。

![](img/b83f00d1bb2a099d09e8e73a043b9d1a_3.png)

So that's why we have this。That's why in the calling convention diagram， we've got RBP minus8。

 RVP minus- 16， et cetera。Corresponding to these variables。 So questions so far。

 questions so far on that。Yeah。Yeah， so that's a good question。

 so in our language all variable declarations come at the top and in the original C language。

 all local variables had to come first。So the compiler will just first look for all your local variables first and then do its allocation。

But it ends up being the same thing， it's just a little syntactic sugar for putting all your variable declarations at the top。

In C， sea like languages。Okay， so the way we do this is in our function prologue。

 we're going to generate some assembly code that's going to give us extra space on the stack。

We're going to use push， or in our case， we're going to subtract to just subtract them all at once。

And then whenever we see a usage of that variable name， we're going to translate it into。

Computations of this offset。So that we can。Read and write to these memory locations relative to the base pointer。

So the key trick here is that we don't know what compile time what the actual address of the stack frame is going to be。

But we've cleverly generated this epilog and prologue to make sure that RBP is always pointing to the same spot in the current stack frame。

Because of that， we know that we can always use the same offsets for these variables。Okay。

 so that's the simple table， did the stack frame for this。Okay。

 so let's look at what assignment looks like in assembly with this scheme。So in our MyFk program。

 we have an assignment of X。To immediate value one。So how do we store？An immediate value to register。

 This is the assembly code for doing that。 You say move。Immediate。

 this is the syntax for an immediate value into a register。So now we have our value into RX。

 The question that becomes is how do we move whatever the value of RX is。

 And I think there's a move immediate into memory as well， but how do we move something into this。

Offset。And it turns out that X86 actually has a special operaand you can use to do all this computation for you。

 so let me walk through some of the different addressing modes in X86。

So what will this do so move RAX and RBP， this will just blow away RBP， we don't want to do that。

 we want to keep RBP instead we want to overwrite the value that RBP is pointing to。

And the way you do that in the X86 world AT& T syntax is to put parentheses around the register。

 so this is basically a pointer de reference。This is a point of de reference。

 this is what it looks like in the X86 world。So this will not copy to RBP， this will derefer。

 this will look up the value of RBP。And then use that as the address for a store， a memory store。

So this will overwrite。Whatever RVP is pointing to now we don't want that either because RVP always points to in our current scheme。

 always points to the old base pointer。So X6 gives us yet another addressing mode。

 actually they're really all the same addressing mode。

 but gives us another way notation for doing this， and this is the notation that we're going to use。

So if we want to write to a memory location that's pointed to by RVP， but has some fixed offset。

We wrap RBP in parentheses and put the offset as a prefix to it。

This is just the AT&T syntax of this opera end。But this is just。Computing for you。

 whatever RBP plus negative 16 is。And then going to that memory location and storing whatever your source opera is in that memory location。

Questions on this， this is just something， this is just the instruction set。

 it's the Canada convention they use， just have to know it， yeah。

This is getting whatever the value of RAX is， the register RAX is。

And storing it into the memory location that can be found by taking RVP。Taking its value。

 subtracting 16。And then that's the memory location that the store is going to happen。

So XD6 World move is used for both registered copies and memory stores and memory loads。

 and like MIPS I think you have different instructions for that。But in X86。

 through all the same instruction just changed the opera。So why do we move it REX first？

So I think for immediate value， I think you can just do an immediate store。

 I do it this way when generating it because I want enter it's my implementation of enter assigned。

 you could certainly do that， but I gave you the implementation of enter assign。For the project。

And'm just I'm trying to be clever and。

![](img/b83f00d1bb2a099d09e8e73a043b9d1a_5.png)

In writing a。But so I wanted my sort of assembly template code。To be the same for like。

whether it's an immediate or whether it's another variable。

 and so I kind of just have a Python string that holds whatever the opera end is and copies it into RAX。

So okay， so the problem is， is that you can't do a load in a store in the same instruction。

If we're going to see next how to copy between variables， you have to do two operations。

 you have to first load from the variable and then store to to the other variable that you're trying to store to and so I just wanted the assembly code to look the same for both immediate stores and。

Store then copy， but you could certainly in your own compiler if you wanted to implement and or assign yourself。



![](img/b83f00d1bb2a099d09e8e73a043b9d1a_7.png)

![](img/b83f00d1bb2a099d09e8e73a043b9d1a_8.png)

You could do this in one call， move immediate one， two。The memory location here for the。

 you could do it that way。So but this kind of sets up the。

The next instruction that we want to compile when you say like x equals y。Okay。

 but any questions about this assembly instruction？



![](img/b83f00d1bb2a099d09e8e73a043b9d1a_10.png)

So this does exactly what we want it to， we want to take whatever the address of RBP is。

 give it a fixed offset。And store or load from that memory location。

You can also think of this as like an arrayy reference。And in fact。

 though they're all point to references or rate references， they arere all translated the same way。

Okay， so this is what my version， my version of enter assigned what its compilation looks like。

 So whenever I see。X assigned to some number。I move immediate that number into RAX。

 and then I move RAX into。Some offset from RVP。And we just look at our symbol table to figure out what number to put for the offset。

So we take x， we look it up in the symbol table， it gives us negative 16， so we just place it here。

And we take whatever this ASI number is and just copy it here to be an immediate value。

It's just a register。 Yeah， this is a kind of yeah， multi general purpose register in the。Like 861。

 I think it's historically the ad or register， but yeah， this is just a register。

 so you can certainly do this in one instruction if you like， I did it in two。Questions on this。

 this translation， yeah。Yeah， I think you can say move one into negative 16 parentheses RVP。

 I think that's legal。I'm pretty sure， actually， I don't know。

So I'm no assembly expert just enough to。Write write a compiler。All right， so let's see how we。

Can compile。This variation of assignment。 So here we're assigning from one variable X。

 we're taking its value。And storing it in red valve。So in our stack。

 we want to take whatever the value of x is here， and we want to copy it。To red valvell。

So in MIPS that would have to be both a load and a store。

To make that work and the same thing in the X8D61， I don't think you can do a load in a store in one move instruction。

So how do we copy the value of an exit memory location， we use this exact same addressing mode。

But from in the source argument。So we look up x's offset negative 16， we construct this operaand。

 which takes the offset from the base pointer and gets its value for memory。

 and we copy it into RAX just like we did with move immediate， but we copy。

Whatever the value of X's memory location is。Into RAX。Quさね。So this is the load。

 whereas if you swap these arguments， that's the store。So this is how we load。The value of x。

Into a register， temporary register。And then how do we store RAX into？

Whatever the memory address for RE valve is。Move it into what？Location red F。

 so how do we construct the argument yeah？Yeah。Okay， good。

 so your classmates said move RAX to negative 24， y negative 24。Yeah。

 exactly so that's the offset that we've allocated for RE valves value。

 so we remember we allocated enough space on the stack for each of our local variables。

We record an offset from the base pointer for each of those local variables so that we don't have to know the exact memory location at runtime。

 but because the stack is the same size every time we call the function。And so whenever we see a。

 so I'll just show the full thing here， whenever we see a variable。

 we can effectively just translate that variable if it's on the right hand side。

 we translate that into a load。By looking up its offset in our symbol table。

And computing the opera end to load is value based on that offset and to register。

 and whenever we have a variable on the left hand side， we want to store to that memory location。

We again look up the offset in the simple table and construct the opera end to refer to that memory location based on base pointer relative to the base pointer。

And we just put it on the right hand side for a store， so we're going to load from x。

 whatever its value is into RAX， and then we're going to store that value into whatever the memory location for red Val is。

Questions on that， yeah。the destination。Destination is always on the right in the AT&T syntax world。

 destination is on the right， sources on the left。Pice should I made that a little clear， but yeah。

 in the AT&T syntax of the Intel world， the super confusing part is if you look at Intel syntax。

It swapped， the destination is on the left， like an equal sign kind of。Yeah。

 this creates some ramifications for like add and subtract。Yeah。

 so sources always on the left in the AT&T world， AT&T syntax world destination on the right。

 so we do a load of x's value and then a store to RE valves value。

And so that's basically all you need to do for local variables， you update your prologue。

To allocate space for each local variable。And you don't even really， I mean。

 I'll show the prologue as well， but you can just。Generate code that will subtract the stack pointer。

And in compile time， you just keep track of which variable you want to associate with each offset for each of those memory locations that you'll push onto the stack at runtime。

And then whenever you see a variable usage， at least for simple assignment， whenever it's a load。

Well，I mean， whatever it is you look up the offset and construct this operaand。

 this relative offset from the base pointer， and whenever it's a load。

 you put it on the left hand side to some temporary register， whenever it's a store。

 you put it on the right hand side。Copying from a temporary register。All right questions on that？

Okay， so let me show what the whole assembly will look like。I think I have it here。Somewhere。

Actually， it's in code Gen2 let me let me show code Gen 2 before。



![](img/b83f00d1bb2a099d09e8e73a043b9d1a_12.png)

We end。

![](img/b83f00d1bb2a099d09e8e73a043b9d1a_14.png)

Over。The second thought is actually out there， I'll just generate it again。

So I have some debugging stuff in here。So the top is exactly the same， we have the same prologue。

Here is how we allocate space on the stack。So we have three， eight byte entries。

 so we just subtract three times8 from the stack pointer that will give us。This extra space。

One of the stacks that these are。This is space for our locals。This subtraction。

Is what at runtime will allocate that space？Here's our assignment of1 to x。

So in my version of En assigned， which I've given to you。

 we move immediate into RAX and then we store RAX into the offset corresponding to x。

Which is negative 16。And then for this for our assignment of x to red valve， we first load X。

Into a temporary register RX， and then store into the memory location associated with Red Val。

 which we get by looking up it's offset in a simple table。Questions on that。

The rest is the same because we tear down the stack by just。

Overriding the stack pointer to whatever the base pointer is， and that will just。

Kind of automatically remove whatever we pushed on the stack。After。Updating the base pointer。

Questions。Okay， so CodegenN2， I put up the project already。

It's similar to code Gen1 except you need to support local variables and you need to support parameters。

 Now I've given you the code to compute to create the symbol table and to allocate the offset it's a kind of a pain in the X66 world because you have to align the stack to 16 bytes for some annoying reason and you'll get seg faults if you don't that。

 so I just gave you the code to do that so you'll have the。Simple table given to you。

 you just have to do lookups into it and you'll have the correct subtraction to the correct amount of bytes that's given to you a sign is given to you so you can see how to test between a name and a nu。

How to generate code， and then you'll you know function and exit function。

 these are the same as code Gen1。Call will be slightly different we'll talk about that next time。

 how to pass parameters but you'll have to generate code for we'll talk about parameters we'll talk about parameters next time you'll have to update and return and parameters but yeah we'll cover that next time but if we want to get started I'll need to look at this descriptions complete and that's 120 thanks all take care。

Yeah think。

![](img/b83f00d1bb2a099d09e8e73a043b9d1a_16.png)