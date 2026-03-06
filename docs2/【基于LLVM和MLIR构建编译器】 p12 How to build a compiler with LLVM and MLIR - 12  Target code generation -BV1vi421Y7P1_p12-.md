# 【基于LLVM和MLIR构建编译器】 p12 How to build a compiler with LLVM and MLIR - 12  Target code generation -BV1vi421Y7P1_p12-

Hey folks， hope you're having a great time and welcome to another episode of How to build the compiler with LLVM and MLOR。

In today's episode， we're going to talk about target code generation， but before we start。As always。

 updates。In the past two weeks， I was working on the JIT as usual。But this time， actually。

 I'm working on the third approach to creating a J IT。 so I tried it twice before。嗯。

The implementation I end up with ended up with wasn't like。

What I needed like they didn't meet my requirement so I had to start another one I'm going to have I'm going to have a video for each of them because it might be useful to someone they work but。

I needed something else。Also， actually in couple of video， a couple of episodes。

 we're going to get to the JIT topic。Hopefully it'll be done by then fingers crossed but two knows。嗯。

During past two weeks， I was a little bit annoyed with the development process。

 so I ended up writing an EmX list。Library to kind of ease my pain。 and let me show you， actually。

If you navigate oops。If you navigate to resources directory。

 there's an emax directory and there's a file called serene devev。el it's quite simple。

 it's just a wrapper around the builder script which。Withit some inacifications。呃。

If you're an Iax user， you might find it useful and I'm pretty sure you know how to load it already。

Open up a C plus plus file in the。Project and do superC and C， for example。

 to compile superC and B to build the entire project。And finally， to run it， for example。

 either superC or to add the input like to add some flags and stuff like that or control C to run the compiler and as a shortcut to emit something for example。

 let me emit some I as you can see。It works。 and it's much easier。

 I don't like to type commands all the time in my terminal。 I like shortcuts in my。

It makes environment。Anyway， let's get back to the org file。

That was the update and getting back to the main topic of the day。

 so far we created a front compiler frontend based on LLVM that reads。A source code。

Pas it into an ASD， we do some stuff on the ASD to make sure that it's semantically correct and we generate。

Generate some sort of IR based on MLIR， our own dialect called SLIR。

 and then we lowered that SLIR into LLVMIR and yep that was the previous episode。

So by that definition， our work is kind of done， you know， because so a compiler front end is a。

Program that reads the source code and generates some sort of IR。

 but in the real world you can't expect your user to be happy getting some sort of an IR from your compiler and run it through Clang or other compilers that understand the LVMIRs that's not how real world works real world works so。

To be a。Fooll F compiler， we need to actually create an executable for our program。

There's a bunch of ways we can do that， but the common approach is to compile into object files and use a link here to link them together and create an executive。

 but not every language follows the same approach， but if you use CC++ or other languages to that nature。

 they were kind of the same。嗯。We're going to stay with the same。Solution， because it's well known。

 there's tons of documentation around tons of information on the internet to read about and learn about how link here works。

 what is an object file。Vice versa。I included a link to a really， really good resource。

 it's like a 20 part。I say on linkers。The person who wrote the gold linker actually wrote these essays and it's fantastic。

 I highly recommend you to read it。嗯。By the end of today's episode。

 if you're working on a static compiler on a static language like C++。Your wiring is done。

 your compiler wiring is done if you remember from our previous episodes。

 I mentioned this almost in every episode。OurOur first milestone and first goal is to get to a point that we have a compiler that practically does nothing。

But it has all the different pieces in place， they wired up together and they work， right？

If you are working on a static compiler。By the end of today's episode， your wiring is done。

 you have to start like making refinements to each piece of the compiler。

 work on the SLL yard direct。Your own MLI or dialect， make it better。

 add features to your language and that's how it works， right？

Modern languages are not usually that simple。In our case serene is a Lisp and a big part of a Lisp is the macro system or I don't know Lisp in general is like a dynamic nature language。

 I'm not talking about like how typing works in a language but if you know about listsp macros。

 you know that they run on compile time so we have to run some code in the compile time as well。

That kind of。That thing kind of eliminates the purpose of today's episode for us because we don't want to like to generateable executables basically with。

As a like aesthetic compiler。So that's why I'm working on a JIT， but we get that later in today's。

Episode。But before we start to have a look at the code。

 we need to know more about what is an object file。Like how linking works basically。

I'm pretty sure you know about all this since you're watching like a compiler， video series。

 you're interested in compilers， theres like。H chance that you know about this kind of stuff。Sorry。

 but just in case as a refresher， let's have a look at what is an object why。So。

Object files are binary files and there's like three different entities in an object file。Symbols。

 relocations and contents。So。When we compile。Some code into a machine code。

 for example in serin if you remember from episode I can't actually remember which yeah episode 7。

 the unit of compilation in serene is name andspace but in LLVM it's a module so when we generate the LLVMIor LLVMIR for a name andspace it contains a module and when we compile that module to the machine code it ends up being on an object file。

In an object file， we have some symbols， each symbol describes something global in our measure in our name andspace。

For example， when we write a function。The function has a name and a body。

 we actually compile the function into machine code， and then we use the name， we man the name。

And use it as a symbol to refer to that body， right， to refer to that body。

So that's pretty straightforward， just heads up symbols。Are different than least symbols。

 So when in the source code when you come across expressions and symbol expressions。

 they're different theyre on there's like a least concept。

 this symbol that we are talking about today is like a object file and executable and like。

I don't know what to call it actually low level concept， maybe。嗯。Each symbol has a name and a value。

 the value is actually an offset in a content that the machine code lives in。

When we have the definition of a symbol， when a symbol has a valued， we call it a defined symbol。

 a defined symbol is what we actually define in our source code as well。Same example。

 a function with a definition is a defined symbol， we have the definition。

 we have the machine code for that symbol。But sometimes we use symbols external to our source code。

 either we import them from another object file or module or name aspace， they're all the same。

 but in different layers。Or like we use like a shared library， static， library， whatever。

 we don't have the definition。We called those symbols， undefined symbols。

Another entity and an object file is relocation。Relocations are computations that we perform on the content。

They take some extra information we call them added。Relocation as an example。

 it would be like set this location in this content to this value of this symbol plus this add。

 right， so it's kind of like operations and modifications to contents。

When during the linking process， the linker actually applieslas the relocations on the contents and try to resolve the symbols。

Resolving a symbol means finding the definition of that symbol。

When we like define symbols are obvious， we have the definition。But in case of undefined symbols。

 if the linker can't find the definition， most in most cases。It's going to raise an error。

Deppen on the relocation type and the symbol type， it might be okay to ignore undefined symbols。

But the last concept is contents。So contents are chunk of like a。

F of machine code that we compile when we compile the LLVMIR into some machine code。

 that machine code ends up in a content。So。Basically， when we start an executable file。

 when we a process。We load some stuff into memory。And contents are what memory should look like during the execution and during when we start the process。

 right？It a memory map of a chunk of memory is like a content。

They have size type and obviously an array of bytes representing the instruction。

 machine instructions。And we have like different section in contents。

We have like a take section that contains the generated code， the generated target code。

 we have the data section。that contains the initial site the initialized variables and read only data or R data contains like string literals。

 Port tables， switch tables and things without nature。

We talkingal about protocol tables way in the future and finally the BSS section。

 there's like more sections but。Common one。Contains like uninitialized variables I managed to pronounce at this time。

嗯。Basically， when we on the debug mode， when we compile。Our application， the PS is usually there。

 but when we strip the binary。We actually purge the BSs and assume zero for all the value variables as the value。

嗯。But。The object file itself is just a bunch of entities。

 the main important thing is the linking process。So basically during the LinkedIn process。Liiner。

 the job of the linker is to resolve all the symbols and then create a create a executable binary out of the。

Different object files that we have。So。A link here usually read all the object files。

 read the contents of every object file as the raw data and then。

Try to figure out like what's the length of each content and。

The linker will create like a table called the symbol table。

 try to resolve all the undefin undefined symbols in that table and make sure that we have the definition for all the symbols or at least we know how to get them。

 for example， in case of a shared library since we don't know about the target machine。

 not the target machine actually。There's a little bit of confusion there since we don't know where this binary is going to run。

 like on what machine on what physical machine， what platform， what OS， blah， blah， blah。呃。

Usually for shared libraries the link here will。Add some code to the executable code dynamic linker that figure out and link the undeified symbols in their run time。

 only for those symbols that we mark them as external and。

We dynamically link them against our binary。It's not related to our topic of the topic of today。

 but just。Just in case it's nice to know about， by the way， on the。

On that link that I actually added to the resource section， the link here essay， you can find bugup。

The things that I'm describing today is like。Four parts of that essay。

This that essay is fantastic if you're interested in this kind of stuff make sure to read that one so after the symbol table and resolving all the symbols。

 the linker will kind of concatenate all the contents together from all the object files。

 sort them by type and apply all the relocations on them and finally we when we had all the symbols figure out when we had all the relocations apply to the contents we not be the link here will actually write the result into an executable file。

Sorry。Depen， of course the format depends on the OS and the platform in Linux。

 it would be like a ELF format L format。嗯。So the thing that I described is kind of like an AOT time ahead of time compilation。

 we have JIT as well。I talked about it in previous episode， I always mentioned JIT。

 but I didn't say what it is， so JIT is just in time compilation。For AOT， we read the source code。

 we go through the entire process and we end up with an executable file ahead of time。

 but the JIT is kind of different， JIT we give it some， we give it the source code。

 it compiles that piece of source code under flyly in runtime。So if you're working on。

 as I mentioned earlier， if you're working on a static compiler， AOT is what you're looking for。

But being able to AOT some piece of code doesn't mean that you don't need a JIT or having a JIT doesn't mean you can't do AOT。

 you actually can run the JIT on compile time to do something for you and that's what we're going to do for the macro system we have to run the JIT on compile time。

 run some functions， let the user have control over the compile time with macros and finally AOT Day result into an execut。

 but our approach when we're using a JIT is different than what I'm going to show you today。

With that in mind。いい。And。As I mentioned in almost every episode。

 since our first milestone is to have a airborne compiler with like a basic functionality that has all the pieces in place wired up and ready to go。

The code that I'm going to show you today is going to go away like next episode like I'm just going to show you how we can actually compile to object files and link everything together but we're not going to use this piece of code so it's like a really nasty piece of code it's literally dirty but since it's just for demonstration and we're not going to use it。

 it's okay。So。Let's have a look at。😔，De code。So I kind of try to avoid showing you。

The sernc sea file。Just because。Almost all the things in this file is going to go away as soon as we get the JIT down。

 we figure out the entire compiler functionality。We're going to kind of delete this file and start over based on the。

terInterface that we have。Then。So basically there's a function called what is it， yeah。

 dump as object？The rest of this file is just like parsing the command line and decide what to do when we want to dump an object or compile to the target code and have the executable file we we call this function we pass it and name ofspace if you remember from the previous episode a name ofspace contains the ASD and it has a function called compile to LLVM so this function here generates a。

generateerates a module， a maybe module that contains the LLVMI or representation of our ASD。

We check for our maybe module to see whether it contains a module or there's an error if there was an error or be piped。

Priinnt something and return， I didn't print anything here and the minus one for status code is just useless we can since we're going to throw away this code。

 it's not important。We move the modulele into modulele， obviously we have the context。

This is like the serene context。We set the triple target so if we look at this thing。

It's just on a string。 and we sit in the constructor of the。S context。

And if you look at look at how we act like what is a triple， so a triple is just an string。

 I'm pretty sure you saw it already in your operating system， but it's like CPU type。

 vendor type and an operating system， it means like what platform are we like trying to generate code for right？

So。Going back， we have the triple set in the module for the module。

Then we create a target machine out of that triple right so it's like okay。

 the target machine is an entity in LLVM， it's like LLVM target。

 we use it to generate target code for that specific target。We check it for errors。

 then we set like a CPU， what type of CPU we want to generate for what features do we support right now。

 I'm not using any specific。Feature and we use it like a generic CPU。We have some options。

 if we want to pass any option to the pipeline， we use it like this。

 also we have like a relocation model。A target a pointer to the target machine when we create the target machine actually like this。

嗯。Oh yeah， we use like a unique pointer for it and we set the data layout so。So far。

 we describe the machine that we want to generate the code for it can be like a X86 it can be。

Orm can be whatever， what and different。Operating systems， that's how we define it。And finally。

 we set the data layout， data layout is like how do we want to lay out our like action？

That's really obvious， it's like for this specific platform。

 how should we lay out the data in memory， right， that's like kind of the format we need to use for the memory。

And finally。We get the target file that we want to use as an output。This is not really special。

 right， we create。We construct a path for the object file。

 we installed like we use a stream to write to the object files and finally if there wasn't any error or anything。

We use the pass manager and the pass to generate the object file。As you can see。

 the target machine was our target platform， there's a function called add passes to emitit file。

This thing actually creates the pipeline to generate object file out of module。

Quite a straightforward。And finally we use that pass that we created here right this is like a pass manager and a pipeline it creates a pipeline for us Finally we run that pipeline on our module and flush the output file。

The most important thing here is， since it's a like。I can't say su code。

 It's like a just a really simple demonstration of how。We can create object files。

 I use just one module， but usually when we import other na spaces and stuff like that we have more objects。

 we have to run the pipeline on each module to generate a specific object file for each module or name a space。

And finally， by the end of this by here， actually， when we get to here。

 we have our object files created。But if we want to actually compile the entire thing and finish the entire process。

 we need to link it。Link the object files this together there's like two approach to do that I have the I have both of them here。

I commented out one of them， the other one is。I actually wrote the code。We have two options。

The first one that I used here， I know it's nasty， it's hard coded， pair with me。

 its just for today's episode， I'm going to get rid of it。

 so it kind of doesn't make sense to put any extra effort on it。So the first approach is to actually。

Use the link here directly。Either you can asspon another process。Call a linker， do your stuff there。

 or in。In LLVM the official linker is LLD， it has like a really nice interface you can actually link aesthetically against the LLD code and like bake the linker inside your compiler。

 like what I did here which in my opinion is the best approach and。Li link the object files yourself。

But， you need to。Provide the arguments that LLD needs。Since we are using it as a library here。

 it supports the same argument as a command line LLD。I hard coded everything here。

 like the library an object files I have to。Link again to generate the binary to look for the shared object or static objects vice ver up。

And finally I call the LLD for an E format to link my object files。

And I pass the object file like this right， this is the object file and I say the output should be this file here。

But obviously in your implementation you have to kind of be more elegant。

 this is not something that you want to do in your code。

 you have to guess you have to find different places that，嗯。Like on the target platform。

 you can find the object files or shared libraries， things like that。

 you have to kind of figure out what platform you're linking for and things like that。It's up。

Up to you to do that， another approach。Is to use。C compiler， right， it's easier to do it。

 So the code that I have here if I。

![](img/c8463a46d22af1897aa413b8f3ac86aa_1.png)

Uncommented， actually。

![](img/c8463a46d22af1897aa413b8f3ac86aa_3.png)

So。What it does， let me do this。 What it does is to use the clang driver to call to a clang and。

Ask Kang to deal with the linger。It's easier because you don't have to guess like you have to do。

 you don't have to do the setup I for the LLD， like give it the different paths on the platform。

On the target platform to find the libraries and stuff like that。

 it's easier to let Kang or the target C compiler do it。But the downside is you're now。Of course。

 depends on how you call a C compile。 I use the driver you might call it like a you might directly asponum。

Process and find like Gcc or clang or whatever。 and then do it that way。 But in any cases youre。

of your compiler needs another compiler it kind of your compiler depends on another compiler。

It's not nice right if as a user when I use a compiler， I just want it to work。

 I don't want to like have another compiler for。So both of them can work together somehow。

I like it would be more complicated and it since you have to now link against the clk driver and stuff like that it's going to make your。

Compilr size， much， much bigger。But basically what you have to do is to construct a driver object that then you you can construct arguments like before like how we did for LLD and then create a compilation。

 compilations are like jobs， build create the job for that compilation and then finally execute the compilation。

 check for the errors and you're done right it's easier because you don't have to figure out what flags you need to use with the link here。

But at the same time， you're dependent like you make dependency on other。Compilrs。So。

In my understanding， and。Based on stuff that I' read and talk to people about it。

 the best thing to do hands down is to use the linker to interact with the linker directly and even better than that is to use the LLD library。

Use LLD as a library， that's the best thing to do， it's not as big as a K driver。



![](img/c8463a46d22af1897aa413b8f3ac86aa_5.png)

It's easy to use， but you have to figure out some technicalities for your link here。

 I'm going to include both of this approach in the。



![](img/c8463a46d22af1897aa413b8f3ac86aa_7.png)

呃。Branch for E 12， but again， since we're not going to use this approach and we're going to use JIT to do all this。

We're not going to use it。This entire file is going to go away when we actually finished the J I。So。

That's it for today， guys。I have nothing more to add。

just read the link your essay it's fantastic if you have any question if you have any feedback please reach out to me。

😊，If you liked my work， please subscribe to the channel and leave a like if you're interested in contributing to serene。

 reach out to me or join our mailing list。And have a fantastic day。 See you on the next episode。😊。



![](img/c8463a46d22af1897aa413b8f3ac86aa_9.png)