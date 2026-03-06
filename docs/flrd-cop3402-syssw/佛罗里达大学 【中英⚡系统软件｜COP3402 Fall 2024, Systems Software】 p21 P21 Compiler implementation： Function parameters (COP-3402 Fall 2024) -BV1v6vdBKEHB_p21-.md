# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p21 P21 Compiler implementation： Function parameters (COP-3402 Fall 2024) -BV1v6vdBKEHB_p21-

So I back to System software， I'm going to cover homework 17 right now， so let me take this。

All right， so let's use the。Coach Jen。呃。So definition I should probably Senator。

So this was all covered in the last lecture on local variables。

And also the function implementation lecture。So these are the examples of the prologue， epilogue。

 let to see what else I ask for。Oh yeah， sure。All right， folks definition， prologue。Epilogue。

 assignments and return value。So let's go through each one by one。

 let's start with the function definition。So a function definition is done like this， bless you。

You have the pseudo ops for the declaration。And definition is just a label。

This is what the prologue looks like， it always looks the same。For for every function。

And this is the epilogue， it always looks the same for every function。So let me start。

Constructing the answer here。

![](img/ac4f7550dbb27f1025eb49558cd3136b_1.png)

Okay， so for my funk。That' is the name of the function。I'll just copy assembly file metadata。

And these assembly pseudoops。And the prologue。All right， here's the prologue。And here's the epilogue。

It's all just boilerplate。这个方式。So questions on that， questions on defining the function。

 the prolo and the epi yeah。Do we need to push RBX， Yeah， why do we push RBX？Yeah。

ARBP is a that pointer。For Y RVX。As I don't remember。不 it。it's a pretty。It's a very specific reason。

It's just part of the calling convention that there are some registers that are。

Caller preserved and some registers that are call preserved it's just part of the。

Convention that some registers will be。Saavveed by the caller and somebody else should be saved by the colgue。

So RBX is one of those that needs to be saved by。The colleague。Yeah。Right， function being called。

So that's all our push RVX is for。All right， other questions on the definition？



![](img/ac4f7550dbb27f1025eb49558cd3136b_3.png)

There's over 17。

![](img/ac4f7550dbb27f1025eb49558cd3136b_5.png)

Any other questions on the definition， the prologue and the alogue？Yeah。ぱに。RBA。Well， RAX is。

 I think not。手でない。So RAX does not need to be saved。

So it's one of the scratch registers so you can overwride it RAX is going to be your return value。

 so you will set it。That is everything。哦，是呃。That's a good point， yeah。

 so I think the reason I do this is that in some versions of this I would use RBX。

 so certainly speaking if you don't actually use these registers， you won't need。To save RBX。

But we will eventually use them。Who will eventually use RPX。For other， once we get into operations。

Yeah。あ？Yeah， yeah， you can use any registtry like as long as you preserve， you know， you save them。

All right， so that's the prologue and epilogue。We need the。Assignments and the return value。

So how do we save the return value？That's right。 Yeah， we just save it to RA X。

And RAX is expected to be written the return value for the caller， the function calling this。Well。

 look in RAX for the return value here。All right， and then assignment is what I covered。

Last time in when talking about local variables。So let's see R。

We have these two x equals 1 and red v equals x。And I covered these exact cases， so this is。Oh， wait。

 but we need to allocate the local variables。Yeah。嗯。話し。Yeah， yeah。

 so I'm moving into RAX first and then。Moving it， but yeah。

 you could just move immediate into the memory location。テレビ？It'll be fewer operations。

 so it'll be faster to do it the way you described it because you only have one operation。

 so that would be faster to do that。Okay， so。嗯。To where's that。This will be used in CoN2， yeah。

 this will be used CoN2。Where did you remember。Just check the syllabus。

 I don't remember the due date off the top of my head。All right， so to allocate space on the stack。

There is。Then remember the。ABI， the local variables are stored。Here in the stack frame。

So in order to allocate space。For this。For the three variables that we have。So he's got Var1。

 x and red valve。Then we'll。Create space on the stack。For these local wers， there are three of them。

 they're eight bytes wide each， so we allocate space on the stack。For these three variables。

It makes sense like pushing three times。Pushing  eight bytes three times。Yeah。ペじな。No， it's subtract。

sububtract， so this does。This does， this， it does RP equals RSP minus 24。So it's， yeah。

 it's just subtracting 24 from the stack pointer。So the stack point is a memory address。

 we subtract four from it。And that has the effect of taking the stack pointer， which is here。

After we push with RBX。Moving the stack pointer， three slots， three， eight by slots。Down the stack。

Or on top of the stack to here。Well， why it 24 in this case。Yeah。There are three local variables。

 so you could do more could you could if you know that so there are。

So this is like a simple scheme for compiling these programs if you know these aren't used you wouldn't need to allocate space for them。

 for instance， if they had different types， you may need to allocate more space。

 but I'm giving you just a simple scheme for managing memory on the stack and that's just to give one entry of eight bytes on the stack for each variable that you have。

Okay， and then。To do the assignment。The code is just the code is just here， I just gave you the code。

 so this is to do x equals1。There's a couple ways to do it as yourmate fellow classmate pointed out。

 but this is。One way to do x equals 1。So why？What does this mean。

 what does this negative 16 parentheses RVP mean？Oh sorry， yeah， yeah。

 it's an offset for the base pointer。 so this is how you。

This is how you access RBP minus 16 that address space using this。

 so this is moving whatever the value of RX is into the address space allocated here。

And the convention that I'm suggesting use for the compiler is to。Just allocate。

The offsets sequentially for each。Variable， so v 1 would be negative 8， x would be negative 16。

 red value would be negative 24。Questions on that， if that make sense。Yeah。

So he was like going by like。I think eight by eight， yeah， subtracting eight，tract。Right。

 subtracting8 yeah， so notice that these are negative8 so why is the top of the stack more negative than at the bottom of the stack？

In yeah。The stack goes downward by convention。So the heap grows upwards and addresses as that grow starts at the top and grows downward。

That way you kind of maximize space for both of them。Okay， so questions on this assignment。Okay。

So the other assignment， which is given in class， is this red valve equals。X is assigned to x。

So this move copies， so what variable does this memory just correspond to yeah？This corresponds to x。

And we cop the value of x into RAX， and then we move x into negative 24 RVP。

 which what variable does this correspond to？B thou。

Now this these instructions I don't think could be combined into one。

 I think you have to do loads in store separately， so you would need a temporary register to do this。

And I think that's it， I think that's War 17。Questions on homework 17。Yeah。This is the return value。

 this is for the return value。Oh sorry， the return value is not move 10 higher x it's so yeah， sorry。

 I didn't do the return value yet， so how do we do return X？Yeah。Good， yeah。

 so this is how you access the value of x because it's associated with。I'll set negative 16 from RVP。

 and we copy it into RX， and why do we copy it into RX？Yeah。

 that's the system 5 ABI application binary interface for setting a return value to a function yeah。

どちらは。Yeah， when you see a return instruction in your compiler。

 when you write the code for the return instruction。

 you you'll generate code that will take whatever variable it is or whatever number it is and move it into RAX。

 generate code that will move it into RAX。

![](img/ac4f7550dbb27f1025eb49558cd3136b_7.png)

So I covered this last time where， I mean， this is a different example。If you recall。

 Antler is a parsel generator and when you input a programmer to your compiler。

 Antler will turn this effectively turn this into a syntax tree。

We talked about syntax trees several weeks ago， and itll traverse the tree for you。

And those functions you're writing enter and exit functions for each node， these will be executed。

 these will be run on each node of whatever type node is encountered when traversing that tree。对。私も？



![](img/ac4f7550dbb27f1025eb49558cd3136b_9.png)

ゆち元。Yeah， 100%， so what your classmate very as acuteutely observed is that RAX actually already holds the value of negative 16。

And so strictly speaking， you could save time by not doing that again， yeah。ぐらになう。まれ嘅。無要な。

AndMost of this industry。Absolutely， yeah， actually you yeah， yeah。

 so a very good optimizing compiler would first of all， yeah， first it would notice that。

For every execution of this function， x is always one， rep valve is always one。

 and so you can just return one。And then after that， it would notice that， well。

 these variables are never used。And just eliminate them。And so you could do this entirely。

 you know an optimizing compiler would turn this into just move one into RAX return， yeah。

 100% interested in how that works， take my class next semester or in the spring of any year compiler construction。

 we go into actually the algorithms for tracking， doing register allocation and optimizing in this way automatically。

Mar。Well RAX is a register in the CP， so all registers are available to all programs at all times。

Yeah， this is the， remember from like CDA， I maybe not have going to enjoy that course but。

So remember， this is assembly programming and assembly programming， all you have is registers。

And you have loads and stores for memory。That's all you have for data storage。

Without doing IO to access like disks and peripherals。

But that's the storage you have available to you， so the registers are always available。

The reason RAX is used is just by convention， so if different people are writing functions and they want to be able to pass parameters to each other at the assembly level。

 there needs to be some agreement because there's no naming， there's no naming。

 there's no return instruction like there is in C so instead we define conventions to interoperate with each other I mean just like if you go to plug in your laptop into a socket。

You're participating in a bunch of conventions about voltage and hurttz and things like that。

 you don't know that it's all set up for you but because the electrical grid is has these specific conventions and they differ by country。

The manufacturers know that they can follow that convention。

This is the kind of crux of defining an interface， and that's why it is called the application binary interface because unlike function interfaces applications like APIs。

 which are written in a high level programming language。

 the binary interface is the interface between machine code functions。All right。

 questions on homework 17th。And also I'm realizing I should be restoring RBX。

 which I'm failing to do here， actually， I forgot to restore RBX。

Let's hope that doesn't cause issues， yeah。Oh yeah， so I asked this before。Move Q。

 there are like suffixes for different bit widths， so like8 bits， 16 bits， 32 bits， 64 bits。Usually。

The asmbler will attempt to infer from the size of the argument， so RAX is the 64 bit。

Version of the Reg EAX is a 32 bit， it just it's the same register。

 but it takes take the lower 32 bits。So if you don't put a suffix。

 the asmbler will try to figure out the bit with for you。

 Intel actually has different instructions for 32 bit move， 3 64 bit moves。

 60 bit move because of its backwards compatibility with its prior 32 bit and 8 bit。

 16 bit processors。So just follow the I'll always give you the assembly instruction to use。

 so just follow that and then you shouldn't have any issues yeah。Yeah， right， right， it's copy， yeah。

 it's copy。It's copy， yeah， this is the mnemonic in the Intel world。But yes， it's a copy'。

Deleting this data somehow in the source Reg。All right， other questions on War 17。



![](img/ac4f7550dbb27f1025eb49558cd3136b_11.png)

Okay。So that okay， so hopefully have some sense of hopefully the the， so first of all， the AB， how。

Functions are implemented at the binary level。And the conventions that are used for。

Passing parameters， saving local variables。And entering and exiting functions。呃。

Hopefully you have some sense of how high level language like simple IRC。

What it looks like in assembly or at least a an assembly version of that program that will be equivalent in its behavior。

At the machine code level。And hopefully have some understanding from COgen1。

 which I hope you've started。About what it looks like in a compiler to generate。

 to automatically translate。Take this simple IR's input and automatically generate assembly code that is equivalent。

And it just works by defining just like we did for infi to postfi on our grammar based translation。

It just works by defining a snippet of code that should run on each node in your syntax tree。

During a traversal of that tree。So enter function will。

So Aler will traverse the tree for you when it sees。

The function node at the beginning of the trarsal。Your code should literally print this assembly code。

But substituting the name based on the name of the simple IR input program。

And when Aler does enter call， your version of enter call should generate。This code。

 at least for Code Jen。But so far for CoJ。We'll do parameter passing today how that works and same for return and same for exit function。

So questions on those three pieces。So when we write a compiler， we've got to know the input language。

 we got to understand the behavior of the input language， understand how the output language works。

 at least for the subset of language we're going to use。

And also understand this concept of writing a program that translates between the two so remember。

 our compiler is not trying to figure out the answers。

 it's not trying to figure out what the program computes。

 it's trying to generate a new program based on it that will do the same thing at runtime。All right。

 questions。All right， so let's go on to parameter passing。And this is the last end。

Equally nitpicy part of this AI parameter passing， it a little bit of a pain。

 that's why I tried to make it its own lecture， but it's the last piece in our A and once you've got parameter passing working。

Then function calls will work。And even more amazingly is that you'll actually be able to call C functions properly。

 and C functions will be able to call your simple IR functions。

And I'll hopefully I'll have time to show that at the end of the class that once you get this A right and your compiler is generating code following the AI。

 you'll be able to link with C programs。O。So， let's get into the。Lecture。Okay。

 so just as a quick review。What's a function in this context？Well， procedures。Yeah。

 set of instructions， it's a set of code。Often has a name and it has an input and output that's defined。

How do we implement them， how do we make sure that local state works the way we expect with recursion in our sea like functions？

The stack， we use a stack frame on each inplication of the function， and so we went over this many。

 many times the components to the stack frame。Is it the caller or colee that sets up the green part？

好为。要靠我。Color， yeah， so the colorer sets up the parameters。

And the return address because the caller has that state。

At the time of the call and the blue stuff here is set up by the call lead。

 So this is what the prologue sets up， the prologue sets up the rest of the stack frame and by convention。

 the green and the blue together are the stack frame for。The function being called the calllie。

 this whole thing is the stack frame these are just conventions， these are definitions。

 you could certainly design your own interop， your own A if you like this is the convention that's used in lots and lots of machines。

 lots of units like machines。So parameter passing away and local variables are there's out of space allocated for local variables in the stack frame by the colonlie。

Okay， so how are parameters passed？So do we use registers or do we use stack for parameter passing in System 5 API？

And we all let's get someone new， yeah。这个。Registers， who says registers？Thiss that stack。Both， yeah。

 it's both。 that's the that's the trick。 So it's passed through registers and stack。

 Could we make an A that only uses registers to pass。Parameters to functions for C like functions。

Yeah。You would need to limit them， so in C like languages。

 I don't think there is a limit or at least not a limit that is restricted by the number of registers。

嗯。And so no， if you wanted to see like function with with an unlimited or unlimitedbounded number of arguments。

 you would have to use the stack。 you'd have to use something besides registers because registers have a fixed finite amount Ram is。

Not well， there is actually system dependent bounds on RA that they're very， very large but。Yeah。

 for most machines， the amount of RA you have is far， far larger than the amount of regis you have。

Okay， so in this APII uses both。The。Old 386 AB。For system further than the Uni like world actually wouldn't use parameter registers it would just use the stack。

And so this is one wrinkle of。Following the 64 bit AI is that。

The developers of this decided to use parameter registers as well。嗯。

Likely for efficiency for many functions， I don't know how they came up with six。

 maybe they looked at real world code and said know 90% of functions have six or fewer， I'm not sure。

 but anyway， we have to contend with this so that we can follow the system 5 API and actually have interop with C functions。

Okay， so I actually cover this already， kind of recover this。Just now， by local variables are。

Created by allocating space。 here。 Local variables are created by allocating space on the stack。

That scene in the。In the AB here。You can see local variables being allocated on the stack here。

Any questions on lookover I need to close some of this？To much stuff over it。

So any questions on local variables， any questions from last time？



![](img/ac4f7550dbb27f1025eb49558cd3136b_13.png)

36。Yeah， so why was x16， negative 16 instead of a negative 8？Yeah。えて最フ。Yeah， we had three parameters。

 Var1 was the first one。That's why， so in the convention I'm giving you， I mean。

 I think technically the function is free。To use its stack space， however it likes or not use it。

But the convention I'm recommending you use is to just allocate these in order。In order given to you。

 and this is actually why the IR I designed the IR like this because the local virus is declared right after the function。

 so right after the epilogue you literally just count the number of these and then create a subtraction Actually。

 I think it gave you code to do this already。Did I get the cut， I can't remember。But yeah。

 that's all it is。Okay， any other questions on local variables？

And so why do we translate the name of the variable to in the assembly world because similar world we can't just use variable names。

 what does it get translated to yeah？Yeah， I'll say from the base point yeah exactly okay。

 so that's local variables now let's go over how we can pass parameters。All right。

 so remember the caller， the function calling you。And the one being called。

 they have to work together to agree on where this information is being stored。

So the caller will pass these values via the registers。

For the first six parameters and then start pushing。The remainder onto the stack。

And according to our calling convention in reverse order。So thanks to Brent for pointing this out。

 he actually implemented Cogen2 and pointed out that I put these in the reverse order。

 we always make these little mistakes， so notice here that we have eight parameters here。

 a through H。H is the last parameter。But notice that H was pushed first， it's higher on the stack。

 it's higher in memory， which means it's lower on the stack and it was pushed first onto the stack。

So in this convention， the last parameter is pushed first and then the next to the last。

 all the way up to the seventh parameter， and then for the rest of the parameters those get put onto the registers。

 these particular registers in this order。That's all just defined by the convention。

There's nothing to learn here， it's just。Defined by the connection。Yeah。No， not necessarily。

 it's just where they get put on the stack frame。So you can always use RBP with an offset to randomly access any part of the stack frame。

That's a good question， so how does RBP access parameter G？

So we access the local variable with RVP minus8， yeah。You do plus， yeah。A do plus。

So these are pushed， so RBP is kind of in the middle of the stack frames。嗯。

RBP is set to the entry that has the old RBP by convention， this is how our prologue is set up。

And so if you know that the callerb may use this convention。

You know that it put the return address just before RVP。RBP plus 8 and you know that the parameters。

 any parameters will come before that on the stack， so RBP plus 16， RBP plus 24， et cetera。

 for all the number of parameters。Yes。いざ。The value to ourP deal。Any values。Yeah。

 so you don't actually have to do this attraction yourself。

 so you can just use this special operaand that。X 86 provides you just put the offset here and then in parentheses。

 put RVP。

![](img/ac4f7550dbb27f1025eb49558cd3136b_15.png)

And that will just happen for you， yeah。So rent member registers are not RAM。

Registers are physically separate storage units that are。On the processor die itself。

 whereas RAM is that I mean hopefully you've opened up hopefully everyone here has opened up a machine before and seen physically where these components are。

 but the RAM is like a RA stick like a SA or a dam I don't know what the technology is today I'm not an EE。

 but it's a physically separate device。That is on a separate bus and on a separate part。

Of your computer， I've actually nowadays in。And nowadays they actually are bundled together on like mobile chips。

 I should have a PC bias here， but is a physically separate device with physically separate storage。

And I mean， did you learn about the memory hierarchy？You know， RAM versus registers versus cash。

 et cetera， so expensive， close to the chip fast。Memory。

 there's less of that all the way up to the disk， which is very large， very slow。

And Ram is in between that。So you know you've registers， cash， RAM， disk。

In the kind of current memory hierarchy today， and it goes from。Decreasing speed and increasing size。

So RAM and registers are they're physically separate things and you need。

 and so I guess what kind of conflates this is that in the Intel world。



![](img/ac4f7550dbb27f1025eb49558cd3136b_17.png)

The same same instruction mnemonic， the same name of the instruction is used for both register copies and also stores and loads。

 so like I don't know the right terminology， but technically speaking in RAM you have stores and loads。

put and get data in the register world， I guess they're called copies。To kind of distinguish it。

 but it's literally physically different hardware。And so registers are not in a stack orientation。

 they're individually named， you have a set of them。And Ram is just addresses。

 you have to tell the address。The whole point of maintaining RVP is so that these addresses will be relative to RVP so that we can find them because we can't unlike the registers。

 which are named。We can't at the machine level name a Ram location in Ram。

 it's just a number we have to tell the memory bus to go store。

 do a store load for us store load for us Does that Does that make sense？It can't。

 it can't access RPP because you can't these， I mean， at least on。This chip。

 the registers are not memory map they' not。Addressed via。A RA memory location， they're accessed。

F had adjust the number of the register。So this is like CDI stuff。

 so too bad that they maybe didn't cover that well。嗯。Yeah， don't know how else to say it。

Without going down to like the architecture numbering level， but the registers are numbered。

 there's a fixed number of them。And you can access them through instructions。RAM。

 you give it an address and there's a separate little chip that will translate that address into some machinery that will actually go out to your RAM chip。

And。Either get or set the data on that chip。And it's numbered。

 a sequential number in byte addressed memories， the number of the byte。In Ram。

So I think it's probably confusing that in the Intel world。

 you have the same name of the instruction。But this move， this move immediate。

 is actually a different instruction from this store instruction。So this is a move immediate。

 this is a store。Which is also different from。 I don't I don't。 Oh yeah。

 which is also different from。This copy between registers。So this does not involve RA at all。

 it's just copying data between two registers on chipI。This is doing a store。

To the memory via the memory bus， and this is also just in processor。Does thatDoes that make sense。

 Does I answer your question。A little bit。So。These parametersors。Just by the name of the register。

 so in the same way we can copy from RBX。So yeah， let me get through the parameters then you'll see because I actually show the code that we use to access these and you'll see these are just names of registers just like RVP We'll do this for Code Gen2。

 that's right yeah。

![](img/ac4f7550dbb27f1025eb49558cd3136b_19.png)

Okay， so， so let me actually show an example to show what this looks like。So just keep in mind。

 first six are in registers。The rest are on the stack reverse order。Okay， so let's take。Let me say。

 yeah， I'll put this example。Okay， so let's take this function here。え。It's called PRm test。

 it has two local variables， X and in PRm。It has one parameter， that parameter is in parameter。

So notice that the parameters are a subset of local variables。

So this IR design makes it really explicit that parameters are also local variables。

 just like Earl C did。And in our language， when we designate certain variables as being in Paras。

 then the compiler will generate code that will go and collect those parameters from the registers end stack。

QuestQuestions on this so far， questions on the IR so far。

So you declare what your local variables are， you declare which of those local variables are parameters。

And then we just have code we saw last time， an assignment from the parameter to x。

 and then a return of x。Questions on that， questions on it， yeah。No。

 it's fine to go to the stack afterwards， it's fine we'll see how it works and here's a main that calls PRam test。

So I just have AC and RV here for like complete this， but it has one additional local called RE Val。

That calls parameter test with a single parameter for the immediate value7。

And it saves that result in rep valve。Okay， so you think I have this。Having me started with。Yeah。

 okay。All right， so before I look before we look into the。Assembly code。

Let's just see how the stack will be allocated from this call， so here's the same code。

 here's our parameter test that takes in one parameter。Assigns it to X and then returns x heres our。

Function made that we'll call that。呃，方式。Okay， so let's assume Maine has been called already。

And it already has its parameters and everything。All right， so remember our AB。

 how is this parameter？呃。Seven being passed。Yeah。Be a register。

So if we look at our calling conventions。RDI， the Reg RDI is what passes this value。So， I had。

It's kind a little different。 That's okay。Okay， so we have the RDI register。

What call first does is it sets RDI to be7。And there's no other parameters。

 so what's the next thing that gets pushed onto the stack when we make the call。Return address。

So here's the return address。And then we transfer control to PR test。It's a pram test。

Does its prologue， which sets the。Base pointer， RVP， the old RVP。

And then allocate space for local variables， there's two here。So we have space for X。And in Para。

And then the convention I'm going to give you for this compiler to make things really simple is we。

Copy the first thing PRms does is it copies all of the parameters into their local variables。

So for Reg allocated ones， we'll copy this data into。It's memory slot for local variables。

 so the benefit is this you don't have to do register allocation。

 you don't have to keep track of the fact that some variables are in registers， some are in。

Local variables， instead， you can just treat all variables the same parameters and non parameters。

Then we'll call， we'll sign x to in parameterm， that'll set x to N parameterm。

And then for the return， we set RAX to。Whatever the value of x is。So， this is the。Full stack frame。

At the end of calling pram test。Qu状 yeah。So that's what when you generate the call， it will。

Go through the list of your parameters and copy them to the appropriate registers so yeah so when we do this call。

Will take each of the parameters。And copied them into。The registers。In the order。

 in the order as defined by the A。All right so questions on this so far。Yeah。So similarly。

 pointers are just memory addresses， so there are no pointers to registers。Yeah。RDI。No。

 RDI has the value of7， which is what we。The parameter。

Value of the parameter so if you're talking about pointers， RP is pointing here。RVP is pointing here。

 so this is the old RVP。O O。So just remember RVP and RSP。

 those are the registers that will be hold memory addresses， those are the pointer。

But the other registers we'll just use for data actually until we get to pointers。

 that it'll make things even more confusing， but let's build up to it。All right。

 questions on this so far。All right， so let's look at some。

Let's look at what the code looks like to do this。All right。

 so let's take a look first at the code for。Main。

![](img/ac4f7550dbb27f1025eb49558cd3136b_21.png)

All right， so here's Maine。So just like before， we have the prologue， we have space for。locals。

We have its parameter handling。We have。This code is different。



![](img/ac4f7550dbb27f1025eb49558cd3136b_23.png)

Let me get the actual code I have here。Oh okay， I sorry， I know I changed this。So I think my。

My grammar doesn't permit immediate values as parameters2。Functions， so it actually。

It does need to be。

![](img/ac4f7550dbb27f1025eb49558cd3136b_25.png)

Assigned to some variable first and then。Apologies for that。

So it's a safe function except we assign7 to a prem first and then pass it。So， here's what the。

Assembly looks like。So this is all basically boilerplate， our prologue。Allocating space for locals。

Okay， so this is our assignment from seven to perm。And here's our function call。So here's RDI。Here's。

The register that by convention should hold。The first parameter。RDI。

And so this is negative 32 because PRm is the variable that we're。That holds the first argument。

So we're calling PRm test on this variable called PRm。It's 32 because8 negative8， negative 16。

 negative 24， negative 32。Its parameterm is a local variable it has offset negative 32。

And so this is how we set。The parameter to our call to PR test。P that yeah。おわ。The last spot。



![](img/ac4f7550dbb27f1025eb49558cd3136b_27.png)

So this is just the offset of the local variables， so however many are here。However。

 many are here in the local Ver Decation。This will determine what the offset is。No。

 if I had reordered this and put PRm here， then it would have offset set negative 24。



![](img/ac4f7550dbb27f1025eb49558cd3136b_29.png)

Yeah。I second嘅 second。先ぜば。一一で。呃。So I'm making an assumption， so ArgC is an integer。

 it's nots supposed to be 32 bits， ArgV is a pointer。Which。I don't know the planer with， what's that？



![](img/ac4f7550dbb27f1025eb49558cd3136b_31.png)

Well， Arr is a pointer to。

![](img/ac4f7550dbb27f1025eb49558cd3136b_33.png)

A list， so it's whatever the width of a pointer is。But I think probably can you do 64 bit。

 I think you can do 64 bit addressing。

![](img/ac4f7550dbb27f1025eb49558cd3136b_35.png)

But at either rate， even if it's only using by8 bits。

 there's really no harm into allocateating into a spot with 64 bits。



![](img/ac4f7550dbb27f1025eb49558cd3136b_37.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_38.png)

So I'm being handwaving， I'm being like。

![](img/ac4f7550dbb27f1025eb49558cd3136b_40.png)

嗯。Expedient here when handling these arguments。You can always assume all variables at all times or eight by。

It'll make things a lot easier。So we're not going to call like C library functions。

 we'll call C functions that we write。To that'll wrap library functions， it'll make things easier。

 but yeah， good question。Okay， so questions on how we set the parameter for our call to PRm test。

 so we haven't called PR test yet， we're in Ma。And Maine's assembly code will set the parameter by copying whatever the parameter's value is into。



![](img/ac4f7550dbb27f1025eb49558cd3136b_42.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_43.png)

This RDI register， why is it the RDI register？Yeah。Because just wear the fruit。

It's in the convention， it's the A。Okay， so when we have all so this only has one parameter or this function。

 so we don't need to do any stack allocation at all。

 it's kind of kind of the benefit of having register allocated。Parameterters。

 we don't have to do any memory operations。And then once all the parameters are set up。

 we can issue the call just like we did before in parameter list functions。



![](img/ac4f7550dbb27f1025eb49558cd3136b_45.png)

And this will save the return address and transfer control to the PR test function。



![](img/ac4f7550dbb27f1025eb49558cd3136b_47.png)

Now assuming PRm test is written according to the convention。It will eventually branch back。

To us in Maine。And start running this。Code。So。So this is my very expedient co generator。

 this is adding zero to RSP， so it does nothing to RSP。But if you have stack allocated variables。

 this will restore the stack pointer。So this is my lazy way of writing this code， so it works。

 so it's the same for every function call， but you could optimize this away by not putting the ad。

 but here I'm adding however many stack allocated variables we have the number of bytes。To RSP。

 I'm adding zero， so itt doesn't have any effect on this uncorrectness。

So this is restoring the stack， there's nothing to restore， so it's add zero。And then finally。

 what does this instruction do？So we've called our function and the next thing we do is removing RAX to some memory location。

 yeah。Very good that's the return value， this is how the return value gets saved because remember。

 as I harped on over and over and over， RAX is by convention where you store the return value in a function call so when we're in the caller when we're done calling that function。

 if we want to make use of this later and we want to save it and we have it our developer told us that we want to save it。

 they want to save it into a local variable。An easy way to handle this is just immediately move RAX into whatever variable was asked of us。

 so this is red valve， it has offset negative 24， so we after the function call is done we immediately save the return value。

 which is an RAX into our local variable。

![](img/ac4f7550dbb27f1025eb49558cd3136b_49.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_50.png)

完生休すね。Destinations on the right yet an AT&T syntax， the destination's on the right。

So questions this questions on this so far， so we've got the parameter passing。

And the return value collection here。Yeah。No， no， call does not， you mean this call？No。

 this does not at all what is called do in the Intel instruction， what does it do？Yeah。

 it saves the return address， pushes it on the stack， and then branches， that's it。

Does not pass parameters， does not save return values for you。

ThatThat's all done via registers in memory。According to our convention for for saving it。

 so for parameters， we pass verse six on via registers and the return value we save via a register。

So there's one parameter and there's always one return value in our language。Questions on this。

 questions on this。Okay， so that's how the call error works。

Caller science parameters beforehand and then after the call is done， restores whatever stack it。

It stack changes it made。And then saves the return value。So let's look at the。

Caly the function being called。So here is the。Here's PRam test。So this is all boilerplate。

 this is the prologue， and the definition of the functions。This is。

Let make sure I have the right function here。Here's our allocation of local variables。Okay。

Here's our epilogue。All right， so here is the。Relevant part for handling input parameters。

So there are lots of ways to implement functions， there are lots of more efficient ways to do it。

I'm giving you a very， very simple schema that'll work for all functions， all types of functions。

 it won't be the most efficient， but it'll be the easiest I think to write the compiler for。

So remember， we're in the call Le now， we're in PRm test。

So what PRm test does after it's set up its prologue after it's set up its local variables。

The first thing it does is to copy all of the registers into。

The stack frame space for their local variables， for the local variables。



![](img/ac4f7550dbb27f1025eb49558cd3136b_52.png)

So remember， we created space for X and N parameterm on our stack when we in our prologue here。

This is what the subtraction does， it created space on a stack floor。

At least two variables here it's 24 because of the。16 by alignment that。This connection requires。嗯。

But the first thing that happens after you have the prologue done is to just copy all the parameter data into their local variables。

 so why RDI。is it RDI？That's yeah， that's the convention for the parameters。

 and so that's why these two functions can work together because they both agree on what parameter comes first。

What's that。For what？中にそ。呃。Because it's inpm x is negative 8， and then in ParaM is negative 16。哦。

All right， so here's how we save the parameter in our callee function and the function being called。

Questions on this， on this。And then we think we covered it before， but here's the assignment。

That we talked about last time。This sets the return value， so this。



![](img/ac4f7550dbb27f1025eb49558cd3136b_54.png)

If you look at our code， our code said，Re whatever the value of x is。X is the first。

Entry on the stack， the first local variable， so it has offset negative8。



![](img/ac4f7550dbb27f1025eb49558cd3136b_56.png)

And we copy that into REX because y REX。That's the convention， yeah。

 that's the convention the system5 convention is to use REX return value and RDI for the first problem。

Yeah， absolutely you could。 So this is the same question as like compiler optimization。

 So the real reason is that writing。Sir member。You're compiler。

 you're not compiling a single program， you're compiling any program。And so it's much。

 much harder to write a compiler that will be optimized for lots of different cases。

 so you may have one where it's not that simple of a program， that may be computation。

And so it's much easier to write a single compiler algorithm that will work for all cases。

And so the kind of technique of doing this is to make very。

 very local decisions on each compiler function， so this is the function for enter return。

In order to write an enter return that would know that x is the same as in ParaM。

 it would need information that enter assigned sign had。So it's much， much easier to write this。

At least I argue， much much easier to write this， making the fewest assumptions possible。

Or I should say the strongest assumptions are possible。The simplest assumptions， yeah。This one。

 so this， I think is so this is because the the 16 by alignment that。The system 5 API requires。

 this caused me lots of bugs when I was writing the compilers before， but yeah。



![](img/ac4f7550dbb27f1025eb49558cd3136b_58.png)

Oh， that's 60 versus 24。🤧。Yeah， so this is like this 16 by alignment。

 I have no idea why I try to look on stack overflow， but this system 5 APII requires a。

16 byte alignment。So if you push one variable。Then you have to push in。Yeah。

 and it depends on what's being pushed before。Whenever it functions is being called it's。

 it's assumed to be on a 16 by boundary we have to maintain that and so it actually wouldn't break here。

 but if you make other calls， you may break stuff。

![](img/ac4f7550dbb27f1025eb49558cd3136b_60.png)

So I've given you that code to compute that， so you don't have to worry about that because it is really a pain。

 but yeah。Okay， so this is how we receive parameters or at least one parameter and write the return value questions on this。

So hopefully this isn't too bad right， so if we know that RDI is our parameter and RAX is our return value。

When we make the call。We just make sure that we copy whatever data the developer told us they wanted。

 and they told us they wanted perm。To be the parameter。So we make sure that data is an RDI。

And we can assume that the data for the return value is in RAX。

 and we can use whatever variable the developer told us REVll。To store that return value。

So this let's look at when we have multiple， so this is my expedient writing the same code for every input program so some input programs will have stack allocated parameters and this will make sure that that stack gets popped stuff gets stopped so this really doesn't change any state at all it's a wasted operation changes this。

So， so that's our call so if everyone's following the same convention。Call PRm test。

 the main function can assume that RX holds a return value。And we can see that in our。

Pm test function。We assume that the caller has used RDI as the first parameter。

And we satisfy its assumption。About where the return value is by setting REX。Questions on that。

 questions。Yeah。So， for the call。In this case， when there's a single parameter。By convention。

 we use RDI to pass the parameter。The caller main。We'll store whatever value the developer asked the compiler to store。

 So it'll store。The value of parameter。And we know where the value of prem is because of our。

Stack frame trick or stack frame offset trick。And because we assume that per test is following the convention。

 we know we can retrieve the return value from RX。

![](img/ac4f7550dbb27f1025eb49558cd3136b_62.png)

And store it in the variable that the developer asked us to store them。



![](img/ac4f7550dbb27f1025eb49558cd3136b_64.png)

But now。Questions on that， everybody clear on that？And then inside a PRm test。

Because it assumes that Maine followed the calling conventions for parameters。

Use you' look at RDI to get the value of our parameter in parameter local variable。

 which is declared as one of the parameters。And to satisfy the convention for returnturn values。

 we take whatever the developer asked us to return the value of x and save it into the RAX register。

かシす。Thequi。Because of the convention that's the convention。

 So as long as everybody agrees on the same convention it almost doesn't matter。

 it really doesn't matter what the convention is， what matters that there is a convention。

That everyone follows。 doesn't matter whether it's R X or RBX。 This is the convention。

And so as long as everybody's following the same convention。

Your function calls will operate as expected。

![](img/ac4f7550dbb27f1025eb49558cd3136b_66.png)

All right， everybody， everybody with me。All right， so let's move on to a。

Slightly or a more complicated example that has more parameters。

And that's in here for the sake time I was just going to get- so this is an example I gave you four。

For testing。So here is our， I have the full thing down here， okay。Let let me show PRm test first。

 so this is a different version of PRm test that has。8 parameters， just like our。

Our calling convention examples， so we have eight parameters here。

All it does is take the C parameter， copy it to x， and then return x。Questions on this code。

Everybody got on this code， so it takes eight parameters。Instead of one。

And we have a main function that looks long， but it's very， very simple。

It calls PRm tests with eight parameters。It passes， it declares its own local variables A through H。

It's just a coincidence of the same name， it doesn't matter that it's the same name。

 and it passes all of these when it calls PRm test。

And just to make sure all these have a different value， which is useful for testing。

 we just assign each of these a different number one through eight。So that's all function does。

 it just sets eight variables， assign them all different number。

 and then passes all of these two parameter test questions on this。Yeah。三倍ぐい。

That's a bit of an advanced topic， but basically the compiler will use its type system to figure out which version of function of the function to call so at the binary level。

 they are different functions。And then it's just kind of bookkeeping to keep track of which one it is。

 and it uses the type system to figure it out， just like the assembr does。

 thesr maps a move to a different actual move instruction。Okay， so let's look at the call lure first。

 let's look at main first。So all this stuff up here， this is the same boiler platelate prologue。

 setting up local variables， et cetera， all the assignments， so these are all the assignments。

 so this is the relevant part here。This is the call。So you can see now recall the conventions， RDI。

 RSI， et cetera。These are just the conventions， these are hard coded。

 I've given you like a Python list， just hard code those。

And you can see that the first six parameters。So negative 32 is a， negative 40 is B， et cetera。

 these are all copies into those six registers。With me on this so far， so just like before。

 instead of moving just into RDI， we have six eight parameters。

 six of them go into the first six registers to the six registers。Questions on this。

These are the parameters， these are the parameters in parameters， this is the call to PRm test。

So we're copying the main local variables a through。Exactly， so the remaining two parameters GNH。

Are pushed onto the stack， so this negative 32 is a， et cetera， negative 80 is G， negative 88 is H。

And notice that these are pushed。Backwards， they're pushed in reverse order and again this is just the convention。

 the convention is to push parameters in the reverse order。

 I think it's just nicer that like G comes before H in the memory hierarchy。

 I think that has a lower offset。I think that's why， but it's just the convention。

So there's the push onto the stack。And this is why I had that ad instruction so after the call。

The stack is now back because of the convention， the stack is now back to what it was before we made the call。

 so this a 16 will pop these two parameters off the stack。Yeah。Probably not。

 most stacks are set to be much larger than that， so if you had 100 parameters there'd be the first six will be here and then there'd be 96 pushes。

And then it would be add 96 times8。So these are local variables， remember。

 so local variables are stored on the stack at negative offsets from。The stack frame pointer。

So these this is saying push local variable A， some local variables are translated into this offset argument。

 offset from RVP， and this is saying push A。Into the first parameter。Or not push。

 but copy A into the first parameter slot， which according to the convention。

Is these six registers in this order？Yeah。This is before the function it's called。Yeah。

 so this is copy to the register pass parameters， these is the stack pass parameters。

 and then we do the call just like before。And assuming the call is following all the conventions。

 once it returns， we tear down the stack， we pop these two， which is what this ad instruction does。

 and then we save the return value just like before。So it's exactly like this example。

Except we have more parameters。All right， so let's take a look at what the col PRm test looks like。

So it's the same as it's。Template for the prologue and everything is the same。

I remember before we copied one。Register parameter into the local variable。

 Now we just do that six times for all of the six local variables。

 So here are six copies from those six registers into the corresponding offsets for the local variables。

question thatね。So just like before， we moved RDI into these spots for a local variable。

It's all again to the convention， yeah， it's convention。

 so because both the collie and collealie have the same convention。

We'll correctly have the order we'll have the correct order parameters。

And then for the stack allocated ones。It looks suspiciously like。An assignment。

 It's just like assignment， except we're going from the。Positive。Offets。

 which are where the parameters are to our negative offsets， as or our local variables are。

We're moving。The parameter， which is in a positive offset from the stack frame into RAX and then copying that value into our offset for the local variable。

Yeah， I think you do at the entire world， I think you have to store it load separately。

 I'm pretty sure try it， but I'm pretty sure you do， Yeah， maybe I'm wrong。Well for our compiler。

 we're got to do all parameters， we all parameters for the A。

 you would have to do all parameters because there'd be no way of them knowing which ones are needed or not。

 because you declared it to say these are the parameters you'd have to do all parameters。Okay。

 and then so those are and then the then it's the same thing， the return value is set。And that's it。

 so it's the same as this example， except we've got two stack allocated parameters。Okay， so。

Take a look at CoN2 CoN2 is starting today you can copy your code from Cogen1 let me know cover off hours if you have issues with Cogen1 Oh Brentt will cover did you cover CoN1 last week he'll cover Cogen2 tomorrow so all right everyone that's 120 take care thanks everyone and have a good weekend。

拜拜。いや。

![](img/ac4f7550dbb27f1025eb49558cd3136b_68.png)