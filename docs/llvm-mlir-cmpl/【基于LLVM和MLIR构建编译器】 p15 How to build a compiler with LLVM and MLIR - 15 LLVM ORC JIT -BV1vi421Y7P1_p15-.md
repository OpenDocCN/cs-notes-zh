# 【基于LLVM和MLIR构建编译器】 p15 How to build a compiler with LLVM and MLIR - 15 LLVM ORC JIT -BV1vi421Y7P1_p15-

Hey folks， welcome back to another episode of How to build the compiler with LLBM and MLIR H New Year and I hope you had a joyful holiday。

 you enjoyed your holidays today's episode is all about org， the LLBMGt API and quick updates。

During the holiday season， I was working on Jde like always。For past three， four months。

 I tried to make a bare minimum g engine using different approaches。

 as I mentioned in previous episodes。But finally， I managed to get like a。

Finish like a really small minimal and bare bone jet engine。

What it does is it can compile name of spaces， so whenever I add the name of space to it it compiles it eagerly at the time of insertion。

 which is not great but for now it's fine I'm going to make some changes in the future but you know bare minimum and we want to finish up our wiring。

Also， I created the functionality to reload name and spaces。 So when I add a name of space。

 it compiled that。And make it available and then I might need to reload the name ofspace。

 for example， in a rep environment， I want to reimport the name andspace and user might say， okay。

 I want you to reload this name andspace。So it can manage that， it compiles it， make it available。

 and it can manage it like different copies of a namespace because we might have some code referencing to the old version。

When I was working on that like。I had to think about different specifications of serene all the time。

 what if user does this， what if a user does that and stuff like that right it might be the time to actually start writing the ser specification to lay down the ground war to make some solid foundation to make decisions in the future。

So I'm going to do that as I'm going to start doing that。So if you don't know about scheme。

 a scheme is a list， like a really famous list， it's a specification is it quite。Small。

 and it's a nice。 it's a nice language。 I'm going to pick up the。Sches spec。

Keep what I like and add the stuff that is missing and remove the things that I don't like and that would be like the specification for s I'm going to put it in the repo you can if you like。

Of course， like as soon as I started， I'm going to have some sections。

 I'm going to talk about it in some sections of。Future episodes。

 but it would be nice for others to review it and give me feedback as well。

So talking about the Se Jit engine， before we can actually jump to the implementation and what I did。

 we need to have a better understanding of orV2。So what is OrgB2 orgV2 is org the J engine is on request compiler or compileilation I'm not sure。

 the name is really funny when they there's a talk I put the link to it in the description and in the resources section when the author actually。

Explains why they chose the acronym orRC。I found it really funny because we have like L format right right like ELF format for binaries and Dwarf a standard for debugging so they were like。

 okay， we have elses。We have d dwarf。What's missing works。

So that's how they came up with their name orRC， which is really funny。It replaces the old MCG。

 you might come across the MCG name quite a lot in the LLVM source code。Don't bother with it。

 It's the old duplicated G GT API APII in L L VM， Nobody， in my understanding， nobody use it。

 They don't want to use it。 and work is far superior and better。😔，So to learn more about org。

 there's some dogs that I put the link to them in their resources and some examples。

In today's episode we're going to go through some of the examples to learn how it works。

 and then there's the entire chapter and sorry entire section on how to be legit in the kaleidoscope tutorial。

 which is like the official tutorial of LLVM。But I highly recommend to look at the or dogs and examples first because。

Klyidoscope uses a different approach that we're going to cover， obviously。

It's like you need a better understanding to understand of or to understand the kaleidoscope tutorial。

 so I highly recommend to start with orducts。

![](img/8bb683619a38f7c097464957d6c7506a_1.png)

So。When I was going through the documentation， the examples and everything。

 some of this stuff were really confusing to me because I didn't know about some of the terms and terminology in the context of that document。

So I thought， yeah， okay， it be a good it might be a good。

AThing to start with a description of some of the popular terms that you might come across in the documents or examples。



![](img/8bb683619a38f7c097464957d6c7506a_3.png)

It's okay if you don't understand them yet， they're fairly straightforward。

It's okay to not understand them just yet， but it's good to have them like somewhere in your mind。

 okay， I heard that name before I don't know， I know some stuff about it and little by little they're going to make sense to you as we go。

Okay we go on our journey in the sourceco。

![](img/8bb683619a38f7c097464957d6c7506a_5.png)

The first concept is the execution engine execution session。

 and actually I should have included the execution engine as well。

 which is like the name is kind of self explanation。Really obvious， right？

But execution session is a session that describes a running Jit program right it contains everything from Jit Dilis error reporting and like。

Basically how the meization work and everything in that area。

 so like an execution session is just a running Jit engine when you run your Jit。

 you have this execution session。Then we have Jit addresses that are just simple。

 it's just a wrapper around the like address type， you know， it's a pointer type， right。

 it refers to an address。

![](img/8bb683619a38f7c097464957d6c7506a_7.png)

In the GiTT code， so when you compile some code， put it in memory。

 a Git address points to any code that you already compiled。



![](img/8bb683619a38f7c097464957d6c7506a_9.png)

We have GiitTlibs， which is a class represents a GT code。

 like a dynamic library that we store our GT code in it。

 each GiitTlib like in our case kind of map to a name a space， so a name a space。

Compillies into a when you compile a name and space， it's going to end up in a jit dial。

In current implementation， we might have multiple G dial leaps for one name and space why we'll see in the future。

Basically， you can think of it as a symbol table。When we compile some code。

 we have some symbols that refers to some chunks of code， right， chunks of compiled code in memory。

The Gi diallib contains the table of those symbols for like if we take C or C++ as an example。

 each Giit diallib can be like a shared library， or a static library or whatever an entity that has some symbols that we want to link with other stuff。

By the way， no， no， it's too soon to talk about that。We have materialization units that so。

When we compile some code and we put it in a Jit dial leavess。As I mentioned， like。

 we have some symbols。For example， in our current situation that we eagerly compile Lama spaces。

 as soon as I put something in the GiitT engine， it compiles it。

Put it in memory and make it available， by make it available。

 I mean you can look up symbols in that compiled code， right？

But that might not be something that we want， like eagerly compiling everything at the insertion time might be good when we want to have our G running on compilation time。

 but on runtime， it's going to have like some performance issues and user will notice some latencies depends on how big the how big the code is。

 but。In order to address that or came up with some ideas that let us actually lazily resolve symbols。

 so a matter is oh it's really hard for me to pronounce this one， materialization you。Is。

Like is the solution for ORC to provide a kind of a way say to tell the di that， okay。

 heres the symbol and I hold the definition whenever you need the symbol。

 just let me know I'm going to materialize it for you， boy it's really hard。嗯。

So that's the purpose basically behind them。That way whenever we add some name andspace or a LVM module or whatever into our jet engine。

 then we create the symbol table， but we don't provide the definitions of those symbols so Giitilelibs knows what symbols to contain basically but it doesn't exactly know where the definition is whenever we look up a symbol。

 then we can use the materialization unit need to actually compile the symbol at request and put it on memory you know。

It makes the G to run faster and just compile whenever we need something。



![](img/8bb683619a38f7c097464957d6c7506a_11.png)

But in order to track those， we need another。Entity called materialization responsibility that tracks the materialization units。

 right， oh boy。It's really hard to pronounce it and it keeps popping up。So anyway。Basically。

 they work as a bridge between jet dye leavess and materialization units。

They provide a way for the jitile leaps to know whether the materialization failed or succeeded for some symbols and vice versa。

So this is actually like these， the combination of these three concepts are really strong， right。

 like really good and we can do a lot of stuff with them。By default， if we use them。

 we get compilation on request on symbol lookout time like whenever we add the code and we look up a symbol it like digit code origin goes and compiles the like look up the material materialization unit for that symbol compiles the code put in memory and return a reference a pointer to it right。

 but we can do it even laziier than that as we as we're going to see in the future or provides a。

Way to actually just compile whatever we need when we call it even look up time。

 we just get when we look up a symbol， we don't compile it。But when we want to use that symbol。

 and like if it's a function call it， then it goes and compile， find the metaization。

 you need compiles that put it in memory and。Basically call Latinimot。



![](img/8bb683619a38f7c097464957d6c7506a_13.png)

It's pretty nice and the API is really simple to understand。

 probably we're going to take a look at it in the next episode。



![](img/8bb683619a38f7c097464957d6c7506a_15.png)

Memory managers， we might not come across this one just yet， but with it simply。

 it's just a class that takes care of your memory management， that G engines memory management。

Like memory allocation， the allocations and stuff like that， equilibriumbri by default have look。rry。

 I guess two memory management managers， I might be wrong， but。

There's one that is quite simple and covers most of the use cases called。Sorry。Section Me manager。

 we're going to use it in the future。But yeah， just to know what it does。



![](img/8bb683619a38f7c097464957d6c7506a_17.png)

Finally， we're going to talk about layers quite a lot。The design， like all。

Design and API is around layers。 So whenever we create jet engine。

 our engine is like a container for several layers that link to each other， I should avoid the。

termm link here because it might make confusion they connect it to each other in a certain way and create they create a kind of like a data pipeline we put something in it it processes it compiles it links it and does some other stuff based on the layer configuration that you have like what layers do you have in your pipeline and let spit out some result or。

Make something happen for us。Layer is just a concept like an abstraction thing in orrc quite nice。

 I'm really impressed with the design of org to be honest， I actually mentioned this in that。

In the Discord channel of the Jeit。Or can in LLVM discord super impressed with the design it's so flexible。

 so easy to understand it might at first it might you need to get your head around it a little bit because other than related that stuff there's other things you need to know and that was my case like I needed I need to understand some of the things that。

Kind of were outside of the chiit context to understand the whole thing but when I studied them like the design is really impressive。

 I'm really impressed by the design。And two more concepts and terms to talk about one is resource tracker。

 that is the answer the orRCs answer to kind of obviously resource tracking。

 it tracks the compiled code。Whenever you add a module to your G you can， not you can。

 you'll track it with the resource tracker， it happens automatically if you use any highleve API artwork。

 but if you want to create your Jit engine，Kind of from a scratch。

 it's not from a scratch but don't use any high level API that we're going to have a look at in the future episodes as well。

 you need to utilize the resource tracker， you can remove the compiled code using resource trackers and stuff like that。

And there's a TreadSafe module which is the same as LLVM module。

 it's just a wrapper around there it's a container that makes it threadreads safefe。

 that's it quite simple， so just because of this TreadSafe modules I had to module I had to make some changes to ser code to actually use TreadsSafe modules in instead of normal modules。

 which makes sense， that will be or one of the biggest components that we have we have to play nicely with it。

P the termin analogology out of the way， let's see。Some of the high level API out of work。

So as I mentioned， it or provides the layer based design that let us create our own J。

But it provides two already built jet engines that。We can use。

And we're going to look at the implementation later， we might scrap the surface today。In later times。

 were going to jump deeper。One is LLGt and the other one is LL lazyGt。LG。

 it just already made and ready to use J engine， uses org API。

 you can customize it to a certain degree， we'll see it in action。嗯。It's it's not lazy。

 so whenever we add some LLVM module to it and when we look up a symbol it's going to compile the code for that。

Symbol in lookup time。But L Lagit， which kind of inherits from LG， is the same。

 but just laziier whenever we want to use a symbol， like call symbol。

 it's actually going to compile it。

![](img/8bb683619a38f7c097464957d6c7506a_19.png)

We have two major solution to create the Jit。 like there's actually three solutions。

 which that third one is。S set of another one， we can't really call it three， but anyway。

 one is to actually wrap LG or oh I made a mistake here。



![](img/8bb683619a38f7c097464957d6c7506a_21.png)

Yeah。LLG or L lazy G so many else。 That's the first approach that actually the current implementation of things is jet engine is based on this one。

And the second approach that we can take is to write our own G engine using the or APIpi like instead of using LLGt or L lazyitt。

 we can create a new one that works just like them but with different layers or different setup whatever right I did that one as well。

 it's in the repository。Not complete yet， but。Just a hunch in my head in the future。

 we're going to have a combination of these two together。

 so we're going to have our jetit engine and a wrapper on that jet engine。

But depends on how things are going to go。I'm going to have a look at the source code right now。

 but really quick some resources。I'm going to put the link to them。

 You cannot actually use the slide that I put the link in the description or。Anyway。

 I'm going to add the links to the description as well。There's three talks by Lang Hames。

 he's really amazing， I'm not sure but I guess he's the main author of or， I might belong。

 don't take my word for it， but no matter what he's really good， he's amazing， really helpful person。

 he helped me a lot as well and these three videos are amazing I highly recommend you to watch all three kudos to him。

 just a thank you。So。That's a helpful guy。So。Let's have a look at what we have。

 like some code actually。

![](img/8bb683619a38f7c097464957d6c7506a_23.png)

If we jump to the LLVM project on LLVM examples。There's a OrRCB2 example， right。

 there's a bunch of stuff in here， but there was another thing here I missed oh yeah。

 how to use not how to use GT actually is based on NG which you don't want。 Oh yeah， how to use LLG。

Like the simple as possible。

![](img/8bb683619a38f7c097464957d6c7506a_25.png)

Example。So as you can see， there's some documentation here。We have some function。

 we're going to like we have some function like add one in like C plus plus function， right？

C or C plus function。That we want to add to our G and then call that function with number 42。



![](img/8bb683619a38f7c097464957d6c7506a_27.png)

![](img/8bb683619a38f7c097464957d6c7506a_28.png)

So。Just help like a helper function to create a demo module for for example。

 it just creates a function called add1 and like adds the entry block in the entry block it kind of create the LLVM IR for the function that we saw。



![](img/8bb683619a38f7c097464957d6c7506a_30.png)

![](img/8bb683619a38f7c097464957d6c7506a_31.png)

![](img/8bb683619a38f7c097464957d6c7506a_32.png)

But on the main function， as you can see， it's like quite short， or is like really amazing。

 that's what I said about the design and how impressed I am。We set up the LLVM fair。

 set up the native target assembly printer and stuff like that。 set up the。

Kind of CI arguments like CL package， I don't know whether I talked about it already or not。

But it's a utility library in LLVM that helps you to kind of create nice CLI tools。



![](img/8bb683619a38f7c097464957d6c7506a_34.png)

Yeah。Deines the parameters that your program can accept and stuff like that。Here's the real magic。

It creates we use something called LG P layer。And the function on， like on that object called create。

 to create the actual L L G。 We're going to look at it in a bit。 But what it does， it's kind of a。

Lit builder we can set set up different aspects of Lit we are the allit builder like a custom compiler layer or things like that。

 you know， we're going to have a look at it。So。After this。

 like it's going to be like if there's an any error， just exit like a spit out error or and exit。



![](img/8bb683619a38f7c097464957d6c7506a_36.png)

We're going to end up with。Unique pointer to Lit， as you can see on the top right。



![](img/8bb683619a38f7c097464957d6c7506a_38.png)

And we created like a demo LLVMR module。For the add function and finally we add that module to our GT engine。

 as you can see there's a function called add IR module。



![](img/8bb683619a38f7c097464957d6c7506a_40.png)

I'm going to show you show you the implementation real quick。

 but that's how we add LLVM modules to our。GT engine and if you notice they create the demo module。

 retain the thread save module that's how。Like。That's the module that always kind of work with。

 not regular LLBM modules and the thread save modules are as I mentioned just the wrapper。

It provides some functions that can take a Lada as the input that lets you actually work with the wrapped LLVM module。

Anyway， when we add the module to our engine， it's ready to use。

 we can look up the symbol that we have so。

![](img/8bb683619a38f7c097464957d6c7506a_42.png)

With the lookup member function， we can look up any symbol。 When we look it up。

 it's going to compile。Iev a module into target code and make it available to us so if anything happens we're going to exit on error。

 otherwise we're going to have have something in like as you can see on the top right the type of add one the is G evaluated symbol evaluated symbol means this thing is already compiled right？



![](img/8bb683619a38f7c097464957d6c7506a_44.png)

So we get some， let's say， reference to the compiled code and then we can use get address of that evaluated。



![](img/8bb683619a38f7c097464957d6c7506a_46.png)

Sim what to as you can see on the top right again to get a Jit target address。

 it's just a J address right it points to somewhere in the compile code in memory。And then since。

We know it's a function that takes just one integer。 We cast it to a function pointer。

 a function pointer that returns an integer and takes just one integer。

 this This is due to the fact that we know。The signature of add one if we have a like a。Sorry。

 if we want to create a generic jet engine， there's no way that we know。

For sure that it what's the signature for each function that's why we have to do some other stuff to figure out okay what is this function that I'm going to call what's the return type。

 how many parameters that it take what what are the types of parameters and stuff like that but for now since we know。

The signature of add1， that's why we cast it to a function pointer。

 and then we call the function pointer that we created here。And we call it with number 42。

 take the result and just print the result。

![](img/8bb683619a38f7c097464957d6c7506a_48.png)

Pretty simple， easy to understand and that's how。Fantastic orchis， super easy。

 super simple Let's have a look at。The jit builder。



![](img/8bb683619a38f7c097464957d6c7506a_50.png)

So it's just a class with a bunch of functions in it。



![](img/8bb683619a38f7c097464957d6c7506a_52.png)

Right， and。どとは。😔。

![](img/8bb683619a38f7c097464957d6c7506a_54.png)

Where is it hang on。Oh， there's it's。

![](img/8bb683619a38f7c097464957d6c7506a_56.png)

Be here。No no， no no， which point。😔，Kay。

![](img/8bb683619a38f7c097464957d6c7506a_58.png)

So。

![](img/8bb683619a38f7c097464957d6c7506a_60.png)

Oh， yeah。

![](img/8bb683619a38f7c097464957d6c7506a_62.png)

嗯。Okay。So this is actually like it has a mechanism that provides some member functions for us to。

Make changes to the Giit engine that we like LG engine that we want to create For example。

 we can set the executor process control。 we're going to look at look at what it is in the future or we can set the execution session set the target machine be there like if we want to G for another target machine then rather than the default or we can set the data layout。

 object layer linking layer， what is object linking layer， we're going to see in the future。

 basically it's responsible for linking the。

![](img/8bb683619a38f7c097464957d6c7506a_64.png)

![](img/8bb683619a38f7c097464957d6c7506a_65.png)

![](img/8bb683619a38f7c097464957d6c7506a_66.png)

![](img/8bb683619a38f7c097464957d6c7506a_67.png)

![](img/8bb683619a38f7c097464957d6c7506a_68.png)

Jitt leaves that we have in the。

![](img/8bb683619a38f7c097464957d6c7506a_70.png)

In our jet engine。We can create a function actually。

 we can kind of customize the compilation layer at like a different compilation layer that works to our need。

 for example， instead of compiling。

![](img/8bb683619a38f7c097464957d6c7506a_72.png)

L LV modules， we can compile。I don't know some other thing like ASDs or stuff like that if we provide a custom compilation layer。



![](img/8bb683619a38f7c097464957d6c7506a_74.png)

![](img/8bb683619a38f7c097464957d6c7506a_75.png)

And set the platform set up what is platform we're going to see if we use a concurrent compiler。

 which of course is going to be another。

![](img/8bb683619a38f7c097464957d6c7506a_77.png)

Like a replacement for a normal compiler layer。So we can use different compiler layers right。

 if we use a concort compiler layer， then we can set up the number of threads here。



![](img/8bb683619a38f7c097464957d6c7506a_79.png)

![](img/8bb683619a38f7c097464957d6c7506a_80.png)

And you got the idea， right， so we have finally the create。

Function that actually creates the Lit based on the configuration that we asked for。



![](img/8bb683619a38f7c097464957d6c7506a_82.png)

The same bill class exists for the LLlagiit as well。

 so as you saw we can customize it to some degree， which is nice。

 but if we need anything more than this we have to create our own jet engine。

Let's have a look at another example。There we are。 Okay， examples。



![](img/8bb683619a38f7c097464957d6c7506a_84.png)

Now， this one might be nice。

![](img/8bb683619a38f7c097464957d6c7506a_86.png)

那我还得有可能。So this one is another example that dumps the compiled object into compiled code into an object file。

Again， some CI parameters and。That's it like where to store the dumppan and stuff like that。

 not important。

![](img/8bb683619a38f7c097464957d6c7506a_88.png)

St up the LVM。Set up the CLA interface。

![](img/8bb683619a38f7c097464957d6c7506a_90.png)

Create the G engine this time we don't do like previous time we're not doing any customization to our JT engine and exit anroll。

 so J here would be our GT engine。

![](img/8bb683619a38f7c097464957d6c7506a_92.png)

Then we look into like。Obviously if user provided the input that we want if the Doje object is true。

 then we get the transform layer object transform layer。

 it's one of the default layers in LLG right and then we add the transform function which is like okay basically。

What it does is whenever cheat compiles anything and pass it to the to the object linking layer。

 then it。Does its magic and after that it calls our callback to let us know that， okay。

 I compiled the thing， here's what you need， right？



![](img/8bb683619a38f7c097464957d6c7506a_94.png)

![](img/8bb683619a38f7c097464957d6c7506a_95.png)

So。If you look at oh， it's actually already built functioning。



![](img/8bb683619a38f7c097464957d6c7506a_97.png)

![](img/8bb683619a38f7c097464957d6c7506a_98.png)

Already built class in LLVM， right， it's just aer helper class that。



![](img/8bb683619a38f7c097464957d6c7506a_100.png)

Dumps the input。Dumps the compile code into an object file right and when we do that then like like before we can add the module。

 create a module， parse it to。

![](img/8bb683619a38f7c097464957d6c7506a_102.png)

Just add one example， if we have a look at it， it's just like a LLVN module in textual format。



![](img/8bb683619a38f7c097464957d6c7506a_104.png)

So we can add that module parse it and add it to our engine like this。

 we move the TreadsSafe module M to our GiT engine using add IR module。

 and then exactly like before we look it up， we get the address for the looked up symbol cast it to a function because we know the exact signature we cast it to a function pointer and we call it。



![](img/8bb683619a38f7c097464957d6c7506a_106.png)

When we call this thing， actually in time of lookup since it's LG， it's going to compile the code。

 the compiler layer is going to compile it， pass it to the link layer。

 it does the linking that is necessary and finally it's going to call our call back in the object transform layer。

That is going to actually dump the object into an object file。



![](img/8bb683619a38f7c097464957d6c7506a_108.png)

嗯。Here。

![](img/8bb683619a38f7c097464957d6c7506a_110.png)

So if like if you look at the implementation of that dump object file as you can see the callback that we have gets just a unique pointer to a memory buffer。

 it has to return a unique pointer to a memory buffer as well it's like the linking object linking transform layer passes the unique pointer to us do your business and give it back to me right that's what happens here I'm not going to go into details but what happens is it's going to get the identifier of the memory buffer。

 create an object file from it and dumping on disk。



![](img/8bb683619a38f7c097464957d6c7506a_112.png)

![](img/8bb683619a38f7c097464957d6c7506a_113.png)

![](img/8bb683619a38f7c097464957d6c7506a_114.png)

That's it and return the a move back the memory buffer you can actually create your call back to whatever you want in this and that's the beauty of the orRC basically highly customizable you can do anything with it the layer implementation is pretty nice pretty unique let me see if we can I will look at another example Oh yet this one is nice too。



![](img/8bb683619a38f7c097464957d6c7506a_116.png)

![](img/8bb683619a38f7c097464957d6c7506a_117.png)

![](img/8bb683619a38f7c097464957d6c7506a_118.png)

So same example， but this time we want to add initializers and the initializers for our module sorry。

 Git dial。

![](img/8bb683619a38f7c097464957d6c7506a_120.png)

Again， some LVIR module， but we have initializer and the initializers in this module。



![](img/8bb683619a38f7c097464957d6c7506a_122.png)

Same setup。 create digit par like。Come up with some LLVM module， Tread safe module and add it to the。

Jit engine， like we see that pattern all the time。

![](img/8bb683619a38f7c097464957d6c7506a_124.png)

嗯。Yeah， it's great like you have two flags for an initializer flag and the initializer。

 oh this part is kind of important。As they mentioned。We。

 we might have one or more jit lips in our jet engine。Depends on the implementation that we want。

 depends on our needs， we have to we come up with some mapping between Gi die leavess and our unit of compilation。

 which is which in Serene is just a name of space so right now。

Just as a like assumption which is kind of false， but it's okay for now。

 let's say each name of space maps to one Giit dial loop right so by doing this we're going to get the main Giitta what's the main Gi dial depends on the implementation for me the name of space that I'm in it is the main one at the moment right it returns the。

Git dial that we have and then we use define member function to define a symbol。

 that's how you define a symbol in your jit dial actually。

You don't need to do this when you add this stuff， it's already like your G knows how to look up at stuff in your。



![](img/8bb683619a38f7c097464957d6c7506a_126.png)

In your compiled code， but for example， in this scenario， we were going to have a an absolute symbol。

 What's an absolute symbol we'll see in the future， but for example。You're going to say， yeah。

 when you want to use some external functions and stuff like that， you can use absolute symbol。

 a symbol that the address doesn't change if I'm not mistaken。

We're going to mangle the name like what Manler does is just to change the name based on the platform or your own rules by default。

 on Linux it doesn't make name and it doesn't make any change to the name but on Mac OS probably creates either like underline or anything something like that to the name。

 I'm not sure， but basically it makes sure that your name is。Mel is the name based on your rules。

Put it in sorry and look it up in the memory。Oh it doesn't look it up in the memory。

 we use the man layer to kind of change the name and then interact with the memory just because we don't want any name colleg or stuff like that。

 but for us it's less issues since we have name and spaces。And finally， here we're saying that， okay。

 I'm going to define an absolute symbol called initializer round flag。



![](img/8bb683619a38f7c097464957d6c7506a_128.png)

And the address of it would be a G address from pointer pointer to the flag that we defined here。

 So we kind of。I I have to avoid using the term link here。

 but we we're kind of connecting the definition of symbol initializers around flag to the one that we have defined in our own code。

 so we compile some code from LLVM。IR and put it in memory and we have some code that we have relies on our C+ plus code in memory as well this way we can kind of connect them together we define a symbol with the address that points to an address in our own。

Memory section。

![](img/8bb683619a38f7c097464957d6c7506a_130.png)

嗯。Nobody segment， sorry。Yeah， we do the same with the initializer run flag as well。

 again we use a pointer to an object that we have in ourC++ code。

Not L LVM module itself like this is a nice way， for example。

 a use case of this would be whenever or ser， whenever we creates the standard library。

 some of the functionality might need to be implemented using C++ we can just use regular C++ and compile compile it use this approach to kind of connect a symbol to each definition that we have C++ rather than compiling it to L LVMIR and then to the target code just or like to use the print function or whatever。

 right？And then since we just use the initialize and the initialized function on the Gileip that we have on the main Giip。



![](img/8bb683619a38f7c097464957d6c7506a_132.png)

![](img/8bb683619a38f7c097464957d6c7506a_133.png)

嗯。

![](img/8bb683619a38f7c097464957d6c7506a_135.png)

We're going to see a pattern like this quite a lot right now we use it for absolute symbols。

 but if for a lazyit which we're going to have a look probably in the next episode this one is。

Quite long on its own。We can't define lazy symbols or re exportport symbols or some other types we'll see in the next episode hopefully。

I guess that's it for today， folks。

![](img/8bb683619a38f7c097464957d6c7506a_137.png)

I'm going to put all the links in the description。I hope it was useful to you that GT stuff is a little bit。

Confusing， at least it was for me to begin with， I'm getting used to it more and more。

 but it's really amazing。 it's going to be a major part in our compiler。

 so we're going to spend more time on it hopefully。We're going to get to see the surgeon code soon。

If you have any feedback for me， please share and if you like my work。

 please subscribe to the channel and consider supporting the project as well。

I hope you have a great time and see you on the next episode。



![](img/8bb683619a38f7c097464957d6c7506a_139.png)