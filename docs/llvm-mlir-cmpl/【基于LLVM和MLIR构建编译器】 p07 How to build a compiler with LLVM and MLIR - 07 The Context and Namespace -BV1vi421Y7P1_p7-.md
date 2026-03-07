# 【基于LLVM和MLIR构建编译器】 p07 How to build a compiler with LLVM and MLIR - 07 The Context and Namespace -BV1vi421Y7P1_p7-

Hello and welcome back to the channel。In the previous episodes of how to build a compiler with LLVM and MLIR。

 we had a brief look over the different So systems， different pieces of。

Compiler like the reader or parer， the abstract indexry and the semantic analyzer。

But we had to skip over some of the core functionality and core concepts just because they deserve their own episode。

So in today's episode， we're going to have a look at the sharing context， the name of space。

 and the environment。But before we get it started， I have to mention that because the setting compiler is under heavy development and because how the development process is going on。

 I have to go back often I have to go back and make big changes to different subsystems。

 for example at the moment I'm working on the JIT and I had to change how the name of spaces work。嗯。

So everything that we talk about today might change in the future and I'm going to document those changes and create new episodes for any major change describing the rationale behind the change and explain how they works。

How they work。Okay， so with that being said， let's start today's episode by talking about the name of spaces。

Naming spaces or。Kind of the most important concept in the Syrian language itself。

Because name and spaces are the unit of compilation in the Ser compiler。

Basically talking about a conceptual name and space。

 it is a mean to categorize different names into different buckets in order to avoid name collisions and stuff like that。

Some of the modern lis like closure supports nameless spaces。

Namous spaces are really important in closure as well。But in the。

The difference between name andspace and let's say。

 a module in a language like Python is that in serene name ofspaces are the unit of compilation。

That means whenever we wants to。Compilr program that is written in serene。

 The compiler will understand only the name of spaces。 So we。

 we would ask the compiler to compile the name ofspace who for us。

 It knows how to look up the name of space who in the file system or。Maybe in the future。

 in a zip file or something like that， it knows how to retrieve the name of space and it knows create how to compile that name and space into a target。

Let's say let's assume we have a C compiler when we give it a C file。

 it reads the file and generates an object file for us that contains the target code for that given file。

In the Ser compiler we still can pass a file to the compiler and ask it to compile it for us。

 but we're going to use namelessspaces instead。In a real example。

 we would ask the compiler to compile the name of spaceF for us。

 the compiler knows that how to look up the name ofspaceF in the file system。

 it tries to load the file with namefo。 Srn for example。

 it tries to read the file and create the abstracts in text read。

runund the semantic analyzer on the ASD and finally generate the target code for us and create the object while corresponding to that name of space。

 and then we might have more than one name and space which is usually the case and we're going to link these name of space on the object layer and create a bar area from them。

So that's the main purpose of naming spaces。嗯。Right now they're quite bare minimum。

 but in the future we will see more and more from them。They usually map to a file on the file system。

 but that's not always the case， for example， in a rep environment。

 we can create a name of space on the fly， add some stuff in that name of space to some stuff。

 and then drop it or compile that namelessspace that doesn't have any corresponding file on the file system in an object file。

 right？And finally， a name and space obviously keeps the scope the environment。

 environment and the scope are the same， but I mean， it keeps the state of the name and space itself。

Another another concept that we're going to have a look at today is the serene context。

 Here's a confusing part。 So if you read the source code。

 you' will see that we have three different contextes。 One is the serene context。

 the Lium context and the MLIR context basically they kind of。They are the same concept， but。

For three different things， the serene context is the global state of the compiler for the serene compiler。

It's the owner of the other two contextes。Right now， it's kind of very minimum as well。

It's going to hold any global estate in the future at the moment it holds the name of space tables that I'm going to show you in a bit。

 it might hold the primitive types in the future and things like that。

The LLVM context is kind of the same， it plays the same role for creating LLVM for generating LLVMIR and MLIR obviously again does the same thing but for generating MLIR。

Code。嗯。That is it， let's have a look at the source code for each of those。

 let's start by the context that setting in context， sorry。

So to begin with we already know about the expression class， the node class。

 they represent different pieces of the ESD we have to kind of。Deefine them here as well。

We have an enum here that is called compilation phase。

 it represents the current compilation phase of the compiler。

So in previous episodes we saw how we can ask the compiler to generate only to dump only the ASD or the result of the semantic analyzer。

 and in the future you'll see how we can ask the compiler to just generate the SLIR or different IR representations that we have。

With this inum， we can set the current operational and compilation phase of the compiler。

 we're going to see how we use it in a bit。Here is the serene context。

 the main class that holds everything is the owner of everything。

 we usually pass a reference to this， we create a serene context in the highest block basically in the main function of the compiler and we pass a reference to different pieces that might need the context。

As you can see， it's the owner of the LVium context and the MLIR context。It has a pass manager。

 what is a pass manager， we're going to talk about it probably in the next episode or the episode after that。

It basically is a pass manager for MLIR， let's e it for now。There's a string to the target Tri。

 if you don't know what target Tri is， just Google it， it's super simple。

 it's just a string thing that what's the type of the machine that I'm running on。

 like what's the vendor or what's the like。Oper like not the operating system。

 but different information about the current machine。Then we have a function member。Is that an s。

Sorry。We use this function to register a new name and space with the context。

And we have another function called set current naming space or current Ns that marks namem and space with the given name NS name to the current Ns。

So the the concept of current name and space in the context is like。嗯。So for different name ofspaces。

 we need we any given time at any given point in time， we're processing a name ofspace。

 we're trying to compile a name ofspace， right？We set the name of that name and space as the current name and space of the context。

 so at any point in time we would know what name and space we're compiling right now。

We could have instead of name， we could have like hold a， I don't know。

 a shade pointer or like a raw pointer to the name and space， but。

I didn't put much thought of into this， but I mean， if we in the future。

 if we want to have a multitd compiler， we we might want to avoid using pointers or we need to have like mus of some sort or things like that。

Keeping a string is simple enough， every thread can actually look up the current name andspace on its own and every thread might have like its own current name andspace。

 you know， but let's just skip that for now， it's a minor detail。

Gt current name ofspace obviously returns a shared pointer to the current name ofspace getNS is like a getter function member function for retrieving a name ofspace from the name ofspace table。

Obviously the constructor of the serene context， super simple， it gets。Sorry。

 it gets like an MLIR context to create that。Pass manager sets the compilation phase by default to no optimization。

 we can set it later obviously and then here we try to load two MLIR dialects。

 the first one is the Serene dialect which is our main dialect for SLIR and standard dialect。

What are dialects and how do we use them， we're going to talk about them probably in the next episode but let's escape over them now there's a you do here like I added this thing for debugging some of MLLR code that I was writing I was working on previouslyly yeah I know I have to remove it but just to remind myself what I wanted to do here。

 I keep it around。And finally， we set the target triple。

Right now we just look into the current machine， we're like， okay， we want to compile the input code。

To the target for the current machine， for the machine that we're running on。

 but in the future we should be able to set the target architecture and like basically the target machine。

 we might want to compile for arm， for example， on a X86。But for now。

 we just compiled for the current machine。Set the operation phase， as I mentioned earlier。

 we just set the compiler phase to a phase。The dish。I if I'm not mistaken is no optimization， yeah。

 like it's here。If we want any other phase rather than that。

 we have to set it via this member function。And then。Obviously， the get function。

And they get optimization level。We're going to look at it。In a bit。So the private members。

The target phase， obviously the storage for the compilation phase。

 we have the name of spaces or the name of space table。This is just a map from。

Name a space names to the shared pointer to that name ofspace。

So whenever we process the name ofspace， we need to register it with the context。

 we need to let the context know that we process this name asspace。It works as a cache as well。

 so let's say we process the name ofspace F later on we come across another name ofspace that has a dependency to name ofspace F so we look into the name ofspace table to figure out do we have that name ofspace already registered。

 did we already process that name ofspace If yes just use the key or the name of the name ofspace which is in our case isF retrieve the pointer and do whatever you want with it。

Otherwise， we have to load it somehow， either go to the file system or some other means that are not important at the moment。

And finally， the storage for the current name and space。Okay。Also。

 we have just one official way to create a name of space。

 the function makes sorry to make a ser context and that is make certain context that returns a unique pointer to an object of type ser context。

Now let's have a look at the implementation of。😔，Context。本て。😔，Yeah的。As you can see。

 the insert is quite simple， just put the name of space。

 the share pointer to the name of space into the name of space table and use the name property of N S as the key。

Gettin is the same， just look it up in the table， if it exists， returning it。

 otherwise and return an null pointer。This is simple as well to set set the current N we just。

Set the storage point to hold the name of the new current name of space。

The thing is I chose to return bull here because like right now there's no way that setting a the current name ofspace might fail。

 but in the future， we might need to kind of prevent setting the current name ofspace to something else in under like certain circumstances。

 but for now it just a way for myself like I'm trying to remind myself my future self that we might want to actually fail and prevent setting the current name ofspace here。

 that's why I did this。Get the current name of space again。

 look into the name of space I forgot about this one this one actually we have to look into the name of space table。

Using the current name and space name as the key and just retrieve the pointer and return it。

As always。Replace。诶。As。うん。In。1 time。Check， we don't want any insert。I forgot about this one。嗯。Okay。

 set operation phase。 this one is a little bit。Might seem a little bit odd， but I bear with me。

So as you know， as I mentioned earlier， we might have different phases for the compiler。

We might operate on different phases。Basically here we sets the target phase。

 that's obvious and depends on the phase that we want， we need to do some other stuff。For now。

 we only have to do two different things。If we wanted to operate on any phase higher than generating MLIR that includes generating lower IR。

 LLVMIR， compiling to object code， compiling to NAT to target code anything in that area。

 we need to add a new pass， what this passes， don't worry about it。

 we're going to have another episode about the pass management and MLIR passes。

 like even LLVM passes。Basically， what's going on is this path is responsible for。

I'm doing air code right now， but this pass is responsible to air code lowering theLIR dialect to another dialect。

 either a standard dialect or any other type of dial that we might need like I have to change the name as well。

 but that's what it does。And if we were operating on any level higher than LIR， which is lowered IR。

 we need to add another path that is responsible for generating to lower everything to。LVMR。

That's all we meaning to know about this function and these passes， what are passes。

 I'm going to create another episode on those so it's safe to escape them right now。And finally。

 at the optimization level。Like any other compiler， no optimization is00 or。Nothing basically 01。

02 and finally 03 depend on the compilation phase that we're in。I know。Finally， make your in。

 just create a unique point， easy PC。

![](img/c135c62f4d82ba624692e31ae1d99790_1.png)

Now let's have a look at the name andspace。

![](img/c135c62f4d82ba624692e31ae1d99790_3.png)

Onces too fast。So。Again， some of the things we have to define some of the things from the AST and other pieces that we use on the Na ofspace here。

Also， we need to create two new。Types， maybe module and maybe module or。Maybe module。

 as the name suggests， is a result of type unique pointer to LLVM module and pool。

If you like if you can recall from previous episodes result is just the is a type that either holds a successful case or a failure case in this case。

 the successful case will have the type a unique pointer to a module and the failure case would be a。

Value of T Boolean。Why Boolean， because I'm kind of lazy。

 it should be errors that it should be like an error type， but I mentioned this earlier。

 Im not at the stage I'm not reached that stage to write the error yet。

 I need to finish the JIT first and then you like create the entire error。Error system， subsystem。

 so to that point I'm just using a boom here as a place hold later later on I'm going to change it。

Another reason that I'm not getting into the error subsystem right now is that I'm reading about different facilities that LLVM has to work with errors to kind of come up with a good design for the error subsystem so I postpone the decision making and development process to the future for now I use the Boolean value as the placeholder。

What is the LVM module？Definitely we're going to talk about it in the next episode， but for now。

You can think of it as a unit of compilation for LLVM so it kind of makes sense to think that each name of space has a map like maps to one LLVM module in normal circumstances but in a rip environment it might be one name of space mapping to many LLVM modules。

 but for now one name of space， one LLVM module。And we have another type called maybe Mo Lo。

 moduleul Lo or module operation is the root operation in MLLR， what operations， what is？

Moule operation， I'm going to talk about that one in the next episode as well。Sorry。😔。

But basically module operations since MLIR works on top of LLVM。

 module operation is kind of the LLVM bay to describe an LLVM module and they kind of represent the LLVM operation。

 sorry， the MLIR module operation represent the LLVM module and it translates to to an LLVM module。

Anyway， it's too much module for now。Let's move on。

 And you can see the name and space class is kind of simple as well。

 It holds a reference to the current ser context。It has a bullion， to， to kind of。

Indicate whether the name of space is。Iitialized or not， we have an atomic counter called FN counter。

So。In Syria we might have like definitely we have some anonymous functions， for example。

 we might have something like this。I'm writing a ser code， a pseudo code， presenting serene。

For example， let's define a function with one argument x that returns。multi。

 it increments by1 and return the value， right？This thing is an anonymous function。

 it doesn't have a name， but we kind like it doesn't have then have a name。From user perspective。

 from the compiler perspective， it must have a name。

 we have to be able to point to this function with a name somehow， right？So。

Usually how it works is that different compilers generate a name。

 generate a unique name for any anonymous function。

We do it like usually the case is we hold we keep a counter and every time we use a we see a anonymous function。

 we increment that counter by one and use that counter as part of the name of that function so that like in different languages it works differently but in serene for example。

 my plan is to use something like，Sorry。Like serene， oops， serene。If and。And the counter。

 for example。The value outcome counter might be three right so this would be the name of the third or fourth anonymous function in the name of space that's why we keep a。

Atomomic counter。Just to generate unique names for anonymous functions and it's atomic because in the future。

 if we have multiple threads actually processing one name and space。

 we don't want to make mistakes and generate duplicates。And finally。

 the content of the name and space。Which is the ASD that represents the source code of that namespace。

Each name and space have a name， it must have a name， so let's talk about closure for a second。

Enclosure， when you want to create a new file， when you want to create a new name andspace。

 you use the NSSS special form and you say like oops，fo。 bar。And then if you have any dependency。

 you load them here and things like that， right this food out bar is actually the name of the current name and space。

We might have another naming space， called Fu do。Bs， for example， right， so。

The very closure loads the name and space from the file system is to look at the full directory for a file called Bo。

clj we're going to do the same because like it's super simple and kind of obvious。

Programmers are used to this kind of center to。This kind of process to load the module or name a based on directory and files。

The entire thing would be the name of the name and space。

 so who do boss is the name is the current name。Okay。

 and it might be optionally mapped to a file name and I guess I already talked about the。

LLVM optional type， it either holds a string or LLVM non。

 so in this case for namelessspaces we can provide a filing。Okay， we have two environments。

 what are environments， I'm going to talk about them shortly。

 but environment actually is a concept coming out of the original list paper by John McCarthy。

You can think of it as an scope right so we have an environment for the called the semantic environment。

 another one called S table。I might need to change the symbol table because we have another concept called symbol table for the JIT at the moment。

 so it might get a little bit confusing but for now it's fine as I mentioned。

 if I change it I'm going to document it and have an episode about it。都。The first environment。

 which is the semanta environment， is the mapping from strings。Two ASD notess。

So the e string itself is like would be the name of that node， or for example。

We create a new binding from a name like fo to a value of a new like to an expression。The key。

 when we want to put that bindinging into our semantic environment。

 we use the string through and the value obviously would be the node that represents that expression。

 right？We use the semantic environment for our semantic analysis phase。

 if you remember from the previous episodes， when we want to define a new binding。

 I'm going to go back and show you the code， actually let's do it right now。

What was the file name death the CP yeah。Then I' hear。As you can see the CTx is the ser context。

 you already know get current name and space return the current name and space that we're processing。

 then we have the semantic environment that we're talking about at the moment。

 it has a function member function called insert symbol。

So insert symbol gets an string and the value， the a string is the binding name that the if you remember。

 here's the binding， binding is a symbol， binding binding binding here。As you can see。

 bindinging is a symbol， so it must have a name。We use the name of that symbol and assign the like encrypt binding from that name to the analyzed value。

 which is the。Kint of the result of the semantic analysis phase running on the value of the definition。

 right？And we put it in the semantic environment。Then later on。

 we use the semantic environment to figure out whether something is defined in the current name space or the current scope or not and。

R if it's not raise an error or otherwise continue what you're doing， you know， it's basically anco。

UFor example， just to give you an example， when we we have a function call， actually。

 I don't know if I already implemented that or not。Let's have a look。Let's have a look。

 I guess I did， yeah。So later on when， for example， we have a function call。The we look at the first。

We look at the first element of the list of the list， sorry。

 to have function called if if you recall from the previous episode is like。啦。

One right this pla here is the name of the function we are trying to call and this is the first argument right so what happens here is we try to cast the first element that b to a symbol if it was a symbol。

 it means it like it's a symbol that points to a function。

 not points like lets let's not confuse ourselves with pointers that refers to a point to a function right。

That like that name is assigned to a function， so we look into the current name of space and the semantic environment of that name of space and look up that name。

Is there such thing in our semantic environment？If it was good， continue。 if it wasn't。

Like it's a semantic error， we can't resolve the symbol name b to anything right so we can fail the semantic analyzer。

 that's how we use the semantic environment。Going back and the symbol table works the same。

 but it works in a different phase of the compilation。

It's a mapping from string refs to MLIR values What is MLR value and where do we use symbol table it's coming up in the next episode order one after that。

Finally， the constructor of the name is space， as you can expect， a reference to the Ser context。

 a name for the name of space and an optional file name。We have another function to get。

 we have like a couple of function to get and set the content content of the name space like the ASD。

Another function to just increment。Coter， the function counter。

Get the reference to the sharing context and two of the most important functions。Excuse me。

They generate function and compile to LLVM function。I'm not going to talk about them in this episode。

 they're part of our discussion about LLVM and MLIR that I'm going to start on from the next episode。

But basically generates some kind of MLIR。A you are。Depens on the compilation phase。

 the return module operation might be in SLIR， MLIR， LIR， one of these three right。

 and finally the compile to LLVM calls generate inside of it。

 generate the IR compile that IR and convert it to LLVMIR and finally return LLVM module containing the LLVMIR。

Also， we have another member function called drawn passes。

It runs the pass manager on the given module operation。

 we're going to talk about it in the future episode as well， it's not important at the moment。

 a dump function that dumps the name of space for debugging purposes， finally the distract。Also。

 we have not just one official way to create name and spaces that is make name and space。

 It takes a reference to the context， the name， the file name and。

A Boolean value indicating whether this function has more has to set the current like the name of space that it's going to create as the current name of space in the context or not。

Let's have a look at the implementation， name space。企。Creating a name and space is simple。

 just some initializing some values。 and if the file name has had the value。

 just set the file name to that。Value get name get three simple， set three is kind of simple。

 The only thing that we do is if we already initialized， we fail naming spaces are kind of。

Ass to be mutable。It's a decision for now it might change in the future because as I mentioned I'm working on the JIT at the moment and I don't know whether I want to keep Na ofspaces as immutable entities and when every time I add a new expression to the name of space just generate a new name of space。

That might work， I have no idea at the moment， but when I'm thinking about the radical environment。

 it's kind of。Put me in a weird situation。I can't decide yet I don't have enough data enough input to make that decision。

 but for now we treat it as an immutable entity so we set it once， set the environment once。

 set sorry set the ASD onces and later on if we already had the ASD we're not going to do anything。

Also， as you can see here。The name and space would be the owner of the ASSD， right。

 so we move the ownership to the tree attribute and we're going to own the ASD。

Create a name of space。That function that we use actually， it's better to。

Move the same to the bottom。Really quick。 Yeah， because， you know， it's easier。

For our eyes to track the changes。What it does is to call the make Sha to create a shared pointer for the name and space。

Get the pointer inserted in the use insert ands as we saw earlier。

 inserted into the context and if the set current value flag was true it true， then set it。

 try to set it and finally return the pointer， nothing special， right？Okay， let's move on。

 We saw the ce， as well。Increment the next fM encounter is super simple this is simpleella I'm not going to talk about the generate method here and also run passes or compile to LLVM in fact。

 because you need to know more about LLVM and MLIR so they deserve their own episode as well next episode we're going to start talking about LLVM and MLlIR。

 but for now let's just keep them。The dump function is quite simple。

 generate the module if the module was there just。Dump it called dump on it。 That's it。 done， right。

But let's have a look at the final piece of the puzzle， which is the。Environment。It's super simple。

 like literally it's just a class that has two template types。K and V。

 So as you saw how we used it in the name of space。

 K here is the type of the key and V is the type of the value。

It has a just like keeps a pointer to the parent so environments can have like a hierarchy of we can have like a hierarchy of environments。

 each environment might have a parent。Basically the root e scope of the name of space doesn't have any parent。

 so that's how we figure out whether an environment is the parent environment or not is the root environment or not if it doesn't have a parent。

 so it must be their root environment。And it has like a storage which we call pairs for it's like a dense map。

 dense map is like a map type in LLVM if you're interested to know how like what is a dense map and why we're using it looking into the LLVM programming manual。

Basically pair the pairs attribute is just a storage for our bindings。

The constructors are nothing special， we have just two methods， the sorry two member functions。

Look up and insert symbol， as you can see， the lookup is。

Is a function that returns an optional value。Optional， I already talked about it。

 it might return a value of type V or LLVM N。So we pass a p of type K2。To this function。

 it looks it up first in its own storage， if it found any value， it returns it otherwise。

 if it has a parent， it looks up the value in the parent so this way we kind of keep looking into our parent till we get to the root environment and in the root environment if we didn't find the key we just simply return on。

Insert symbol is quite simple， it just gets a key and a value and stored in the storage in the pair。

Oh sorry， this is not a pair from our attribute， this is the attribute， this is like the sundt pair。

and retain successes upon finishing the operation it's kind of redundant to do this here。

 but again in the future we might do more stuff in insert symbol that might cause the whole operation or inserting operation to fail so for now we don't have anything to that causes the failure so we just return success。

One thing that you should know is that I already mentioned it in the docs in the comments above。

 if we have as like let's say we want to insert keyfo with the value in an environment if the keyF exists in the parent environment by adding by inserting the fo in current environment we're shadowing the parent one。

 so if the value of fo in the parent environment is4 for example and we are inserting，With。5。

 the value of5， then in the current environment， the value of who is5hi not4。

 That's kind of obvious for at least users， but it it might confuse some users。

We'll see it in action in the future when we get to write some serene code itself。Okay。

 I guess that's it for today， we talked about some of the missing pieces from the semantic analysis phase and now you should be able to actually read the entire semantic analysis code and understand it quite easy。

Thank you for sticking around and please subscribe to my channel if you like my work， leave a like。

And shareha your feedback with me。Thank you and have a great day。



![](img/c135c62f4d82ba624692e31ae1d99790_5.png)