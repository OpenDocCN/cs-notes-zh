# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p16 P16 Compiler foundations： Parsing (COP-3402 Fall 2024) -BV1v6vdBKEHB_p16-

Welcome back to System softwareware today we are。Continuing in compiler Foundations。

 today we're going to talk about parsing， some of the kind of philosophical issues behind it。

 some of the technical introduction to it， and with lots of examples of how we build and write interpreters and compilers。



![](img/3dbce149caa9abe57907c6f46db929be_1.png)

Using this language， the theory of languages。O。🤧So remember last time we talked about before you know。

 this was before the example， we talked about。Cs source file becomes a running program on your machine。

 and this was the picture that I showed。You have your source file。

 it goes through the preprocessor for includes and macros， then it goes through the compiler。

 what does the compiler produce。Assembly when the compiler produces assembly code。

 GC is the tool for doing compiling assembly code。Get assembled gets assembled into a binary object file。

 which has the binary machine code of the instruction set of your machine that you're compiling for Lier。

 what does the linker do？Makes it executable and how does it do that？Yeah。

 it brings together multiple object files and any libraries you have as well as the C runtime。

 which sets up mainine and calls Maine for you。And then how does this executable get turned into a running program？

Well， here on the screen。Yeah， the exact function， the exact function， what does exec do？

Does it create a new process？Changes the running program， that's all it does。

 it just replaces current processes， processes， the memory that stores memory locations that store the program replaces it and then updates the program counter two。

 start running it from the Gidding yeah。Effectively， well， actually。

 since if you're looking at my shell， my S program， you're writing what Bsh does。

When you do dot slash and run it or you run any command， that's a program。

The Ball will call Fork to make a new process and we'll call exec。So yeah。

 this is exactly what happens when you do dot/lash or really just put any program name that's in the path or but that you give a full path to。

On the command line。So my SH is showing you how to use。The kernel use the kernel's loader too。

Actually make a runningburg。What's that？This is not all the kernel， so this part is the kernel。

And these are the system tools。This is part of the tool chain。

 so this is like the system software here。And this is the kernelel。

So the kernel and the system tools are designed to work together to have the right formats。

 to set up everything in the right expected way to make sure that they're all working on the same instruction set。

 the same machine。But yeah， so if you want to see after the system tools， how stuff works。

 at the kernel level， take an operating system course。

 so that'll go into how the kernel itself is designed to give you exec。And other system calls。

All right， so let's zoom into the compiler part， so we're going to be working here。

 we're going to be we're not going to be compiling C。

 we're going to be compiling this custom simplified language that I'll explain next time。

 but we're going to be working in the compiler here。So in the kind of。I've forgot to bring my notes。

In the really simple version of the compiler， there are two pieces of a compiler， the front end。

Processes the input language， and it produces a syntax tree。

And I'll describe what that is in a second， but it analyzes the syntax。

 the grammar of your input file。And stores that as a structure in memory。

 then the back end takes that structured view of your input program and uses it to generate machine code。

I mean well。Yeah， I mean you can think of all modularization this way in any system。

 I mean even like a car engine， you know， you have modules like the transmission。

 the engine that each have a well defined。Function that they do and there's interfaces between them。

 you can think of more of pipe as an instance of modularization rather than the other way around。

So you'll see this probably when you get to processes if you haven't take processes of object orientation。

 that's probably if you haven't seen it before where you'll first see this notion of。

Building software and software architecture where you're building software systems as components that work together。

So you could write a compiler that's like literally separate programs and use Pipe。

to construct the system as these multiple components。

 but in practice people just write these in one language and then use the language tools like objects in order to create these modules。

O。So let me make a very simple diagram of what this looks like。All right， so we have。Our source file。

So in our previous diagram， it just went into the compiler。And what was produced by the compiler？三回。

Right， machine code。Or machine code in an assembly format。So inside the compiler。We can。

Break this down into two。Rough。Phases。The front end。Inputs and the back end。Yeah。

 so what's the input to the front end， it's the source code。And what it produces。Is。A tree。

Representation of the。Input program， it's a syntax tree， just like in human language。

You probably learned about syntax in grammar school。Well， now now out of Mexico but grammar School。

I guess you would historically be taught grammar， like probably Latin grammar or something for the front end produces this syntax tree representation of the input。

And then that syntax tree can then be used to generate machine code。

So that's the kind of like big picture view of compilers。

And now in this class we're going to have a very simple language that we're going to process and I'm going to basically give you the front end。

 antler is the front end so you won't have to write the front end but you'll have to learn how to use it。

And then。The kind of to give away the end here。Generating。

Code from this is basically just tree walking。So in CS1 or CS2， if you learned about trees。

 who did tree reverssals， I think everyone probably did tree revhesal。

So if you learn about tree tra revvers， you'll see a real world application of this for a system tool。

 not just academic exercise， but how we can actually process languages using just basically treewalk algorithm。

Okay， so questions about the overall structure， the really core structure of a compiler yeah。

It is like the。The file。We'll go over that， I'll show an example of how this will actually work using arithmetic expressions。

 we'll go over an example of this。All right， so that's the of any other questions about the kind of course？

ItYeah。Generally， yeah， yeah， so the kind of standard interpreter compiler is designed this way。

Seconding？No， this is all compilers work this way， this is kind of the standard even Java。

 yeah any language you can think of today in programming language works with this way。

 they have a frontend that turns the source code into a syntax tree and a backend that turns that syntax tree into machine code and interpreters work very similarly where they have a frontend to process the language and instead of generating code it evaluates the value of the program so yeah I would say all compilers today now there are large language model AI based approach to translation which don't use this architecture but the current programming language world。

Any language that I could think of that you could probably name uses this。Yeah。Yes。

 we will get into that， we'll get into that more than you probably will。Actually， no。

 the front end has very little impact on the performance of the resulting program。

And that's actually the back end， really， yeah， the back end is really what drives performance。

 I'd say， so the Python back end is not generating cloud。S， it's running the program。

 it's evaluating the value of the program。And so yeah somebody asked me why interpreters tend to be slower。

 I don't have the exact precise answer， my suspicion is because it's a software emulation that's instead of the hardware machine。

 the hardware machine， will run operations much faster than a software program that's running on top of that machine to evaluate。

 I think in general。That's。I don't know if that's scientifically true。

 you can go on stack overflow and see all sorts of arguments about performance in languages。

 but I think generally software emulation is slower generally than hardware emulation for like a similar architecture。

But you know， take it with a grain of salt， prove me wrong if you can find some evidence。Okay。

 so that's the like。Basic。Stucture of a compiler， usually it's divided into。

 let's process the and it kind of makes sense because what does a compiler do it takes an input language and generates an equivalent program in a different language。

 so the front end part is processing that input language。

 the back end part is generating your output language。Okay。So。Perhaps。Confusingly。

 many real world compilers have a so-called middle end。

 which is a very similar silly silly term because I don't know how the middle can be the end。

 but because traditionally you had back end and front end in the compiler so there's this middle end that many real world compilers use and what they。

What they do is here instead of。Going from front end to back end。Their front end。Will generate。

An intermediate representation。This is just so this depends on the。

Language or compiler or interpreter that you're looking at。

But this will be some simpler version of a programming language。

It'll be something incentive of in between machine code， machines have finite registers and very。

 very specific instruction sets， programming languages have high levelvel constructs and types and things like this。

 so intermediate representations， common ones are typically somewhere in between， so for instance。

 L of VM which is a very popular intermediate language for compilers。

Is like a machine where it has registers。But it has infinite registers unlike a machine。

And so this intermediate representation is used in a middle end。To then do some so this part here。

Is the middle end？So那个。Let me put the diagram here。Is this intermediate representation？

And then the intermediate representation is what's passed to the back end。To make your。Assembly file。

So why bother doing this， why bother making a whole other language？And having a separate。

knowF end and back end for that other language in order to generate code from it， yeah。委头。Various。

Yeah， so there's a couple answers there that are both good answers so one is。

If you want to target multiple。If you want to target multiple different architectures。

 so somebody asked me for， do you need a compiler for every language？

AndMy answer was you need a compiler for every front end or every input and output language。

 so if you want to see compiler for X86， you want to see compiler for armM， you need two compilers。

But one way that you can mitigate this explosion of the need of compilers is to instead of compiling to X86。

 you compile to an intermediate representation， and you're still going to need a backend to generate IR intermediate representation。

I'm going to use the areation IR to generate x86 in that， but now when you go to。

 if you want to port it to say arm，You no longer this front end can be reused。

 you can have C to the IR， and then you just make a different back end that generates arm。Arm code。

And so it doesn't completely remove the need to port the compiler， but it makes it easier to do。

Another way to look at it is because this language is not machine code。

 it does not have the idiosyncrasies of different machines。Writing this compiler is actually easier。

 it's generally easier to write a compiler that a front end that goes to intermediate code rather than writing it to go to X 36。

And your colleague also pointed out virtual machines， so certainly yeah。

 this IR doesn't necessarily have to be compiled or used to generate machine code。

 you could just interpret this IR directly。And so when I said， I don't know。

 a couple of lectures ago that most programming language implementation use a mix of compilers and interpreters。

Python the Python interpreter doesn't actually interpret Python code。

 it generates a virtual machine code， it actually is like a compiler to an intermediate representation。

 and then that intermediate representation gets interpreted。

So Java is also something similar where you have a compiler to Java Btecode and that Btecode gets interpreted by the Java virtual machine。

Okay， so yeah， that's all the reasons to use some good reasons to use intermediate representation。

 let's see if I covered everything， Oh yeah， so there's also another important one。

so one big part of what compilers do is optimization instead of just generating so the last time we talked about the assembly language representation of a for loop and whether you actually needed to do jump for a for loop。

 and not in all cases right， you can imagine for loops that have say a constant number of iterations that you wouldn't need a jump for。

 you could just literally copy the body however many times you need to in order to execute that loop。

So what modern compilers do is they try to find more efficient assembly code either in memory or。

Runtime。To make more efficient output programs because there are many。

 many ways to generate equivalent versions of your input program。

 and so the having a middle end allows you to do optimizations that are independent of any particular machine。

 so there are lots of common optimizations that work on basically all architectures and you can make this independent of C and you can make it independent of any particular architecture。



![](img/3dbce149caa9abe57907c6f46db929be_3.png)

So here's a diagram of what that looks like from the LLM world。

 so LOVM is a super popular compiler infrastructure that's used for many industrial strength compilers。

And so here's a picture of its front ends backends and its middle end。

 so LOVM is the originally the name of well， the LOVM IR intermediate representation was the name of the intermediate representation that this guy Chris Latinner designed。

 actually when he was a master student， he designed this so he designed his intermediate representation for compilers。

And that's。Separate and independent of any particular input language or any particular output language。

 it's its own language。And over time， this community has built up several optimizations and analyses that could be done on this IR language。

So that when you want to go create a new compiler， like let's say you want to build your own language。

 you can just make a new front end， you can design the language and then generate LVMIR。

 and now you'll have really a pretty industrial strength compiler for your language。

Or if you want to port C to your new architecture， say you have a new machine that you built。

 then you can use reuse this entire front end and middle end infrastructure and just change the back end in order to generate different machine instructions。

 or if you want to explore different optimizations。You can use this architecture。All right。

 so one sort of a little quiz here， so how many front end languages are depicted here？Five， right。

 how many back end architectures are depicted here？ so how many compilers do we have here？Okay。

 how many unique？Pairs of input and output languages do we have？25， right， five times five。

So if we were to write a compiler for each one of these combinations， we need 25 compilers。

But with this architecture， we only need five front ends and five back ends so you know and then we have to write this middle end。

 so we have much less work in order to build new compilers。W whatever。

So I think there was a project to try to convert Java to IR。

 but Java is kind of designed around its own bycode language and its own virtual machine。

 so you could in principle compile Java to machine code。But yeah。

 people typically just it has its own compiler architecture for compiling to Java Bte code。All right。

 questions， questions on this。Yeah。So it's not necessarily better。

 it what it's better for is if you have many input languages that if you want to build lots of different compilers。

 support lots of different input languages and lots of different back end architectures。

This is less work because you can reuse existing work from other compilers。So better or worse。

 it's sort of hard to say that absolutely， if you have an engineering goal。

One of your goals is to support many different front ends and many different backends。

 this is a good architecture for that because you just write less code。

 you have less duplication if you want a super customized interpreter compiler like Java for instance has its own specific backend。

 its own specific virtual machine then and this was also developed after Java was developed there was no reason for them to port their work to LLVM this IR is also while it is technically independent of any frontend。

 it's very much designed originally around Ct languages and。Compiling to machine code。

 so it's not necessarily the best for say Python interpretation。



![](img/3dbce149caa9abe57907c6f46db929be_5.png)

All right， so here's a textbook diagram of the phases of a compiler。

If you're interested in actually the full compiler flow and how to actually build this。

 take my graduate compilers class， I'll just throw this up here and yeah we don't have to buck about this you you won't have to do much about that this so take my graduate compilers class if you want to actually dig into the details of。

A full compiler。Okay， so let's get a little philosophical here。What does this mean？Okay， so it means。

It means order of operations so I hear two times3 plus one I hear order of operations， so okay。

 so that's what it means and what's the results， what's the end value of that？Seven， okay。

 some people say anyone say anything different？Number anyone ever program in like Fortran。

 like the 1950s Fort before？Probably not right so that forran did not have the order of operations we learned in school。

 it would actually compute this as one plus two， three times three。

Just to sort of illustrate to you that we've got some built in interpreters in our head all right let's do another one this one like you'll see this on the like the internet sometimes what does this mean or what's its value okay。

 what's its value and what does it mean what's that nine。这个？

So we get one answer that says do the prehees first。That's three and then multiply by two， right。

 six and then it's one， we had another answer that was what was the other answer？

Because six divided by two is three。Who's right， who thinks they're right？

So just to kind of illustrate for you that in order to interpret the meaning of this。

 you have some rules in your head， it may be implicit， but you have some rules， right？😡。

Now to really highlight this。What does this mean？逆に。Korean。Who here actually knows。

 who here recognizes it？So we have one probably Chinese speaker， nativeative Chinese speaker。

 or Japanese speaker。Someone want to take a guess what this means。Yeah。で一？two like。Okay。

 so somebody is saying the meaning of this is one， two and three， all right。

 so the person actually knows this， what does this mean？Oh Japanese， okay， all right。

 well that was no， there's no Chinese speakers。Can't read okay， so no Chinese read， oh。

 somebody's using an app to do this， what's it mean？One plus two times three。yeah。

 this is one plus two times three in Chinese， and what I want to illustrate to you is that everyone had really strong opinions about all this means。

 but no one， everyone was like， what does this mean？

So just to point out to you that these symbols to a particular interpreter has a meaning。

 and it actually has the same meaning as this coincidentally。😡。

And to you all who learned the Arabic numbers， I mean， Chinese students also learn。

 everyone learns the Arabic numerals。Think worldwide right who's learning math this has a particular reading。

 but the point is is that these symbols themselves。

 so there's no intrinsic meaning to these symbols because。

This means to someone the same as one post two times three， but to most of actually all of you。

 you have no idea what this meant because the symbols themselves don't have any intrinsic meaning now you have mnemonics like well this is a single dash。

 these are two dashes， these are three dashes and so you can use that as kind of a mnemonic to help you remember it's a very kind of physical descript symbol。

But the symbol itself has no intrinsic meaning。😡，I argue now you could now take it with a grain of salt。

 argue with me， tell me if you think differently， but they don't have intrinsic meaning according to so says me to what gives symbols meaning？

So yeah， go ahead go。这嘅。夜来不睡服。なげ。いせの？I guess， just like。で。ち番我だけ。Yeah， so what Susan said。

 which is I think exactly right， one way that you ascribe meaning is you define rules。

That interpret the meaning of the language and this is exactly what we're going to build a machine to do so we kind of human for humans language is very much if not built in。

 it's probably built in， it's at least kind of implicit you don't really think about when you saw it this you didn't really think all right well this is a straight line and it has。

It maps to the value one， you don't really think of that。

 you just kind of automatically in your head， start computing it。

But that's why I showed you this to say like well that kind of stumps you right。

 but if you had a set of rules and this is very close to Tring's thought experiment。

 the Chinese room thought experiment that if you had all the rules and you could apply those rules。

 you could actually fool someone to thinking that you spoke Chinese or you understood what this meant。

And so we're going to do something very similar when we build our compiler。

 we're going to because the machine itself is not going to understand it any any symbol。

 but we're going to write a set of rules that's going to interpret the meaning of this now we're going to interpret the meaning by translating to assembly but you could also interpret the meaning by producing the resulting value that would be an interpreter。

So there's a couple of kind of some philosophical background to this。

 if you ever heard the expression， the moon versus the finger pointing at the moon。

 so symbols are not the thing they represent they're pointers to them。

 if you've ever been confused by pointers in C， you probably have the same problem because if you try to like subtract the pointer where you're subtracting the address。

 not the value。And so you can think of symbols as like pointers to something pointingers to something else。

 there's also a kind of famous expression the map is not the territory。

 you know if you rip a map you're not going to cause an earthquake right the map is just a representation of the world and in kind of science philosophy of science generally make like mappings to the world that have some preservation of behavior so know when you have an equation that computes say the path of a ball through space。



![](img/3dbce149caa9abe57907c6f46db929be_7.png)

You have some preservation of some behavior of that movement of the ball。

 but it's not actually the ball， it's just a math equation that describes。



![](img/3dbce149caa9abe57907c6f46db929be_9.png)

Okay， questions on that thoughts on that disagreements that there's sort of a philosophical assumption there's little to kind of prove here。

But is a philosophy that sort of is the basis of building buyers？Okay。

 and so in our world for programmingming languages。

 we saw this same thing when we looked at building a really simple compiler last time。

 remember we read in an ASCI character，But just to kind of。Refresh your memory。These ASCI characters。

 even the ASI character for the number one。

![](img/3dbce149caa9abe57907c6f46db929be_11.png)

Ha had the decimal value in the machine， in the machine's representation of numbers。

 when it represents that ASCI character one， it uses the decciimal value 49 or the binary data that's equivalent to the decimal value 49。

And so this also illustrates how the symbols themselves don't have the meaning that you expect。

 it's just a symbol。And in our compiler， what do we have to do in order to interpret or interpret that？



![](img/3dbce149caa9abe57907c6f46db929be_13.png)

That ASCI number， do you remember what we had to do？The remember。

 I just subtracted zero I subtracted the AS over zero， we just converted it。

 we converted the ASI symbol one into the machine value one。

We had to convert that that's kind of a very basic interpreter of a symbol。

I guess a kind of fun bonus exercise would be to write a compiler that takes Chinese to do that or a little calculator that takes Chinese characters and use Unicode to do that。

Okay， questions on this， questions on yeah。No。Oh yeah， yeah， yeah， yeah。

 there's a bunch of these like so called esoteric languages like brain F。As a popular one。Yeah。

 so this goes back to the core of what computation is， so to reference Tring again。

 he came up with his Tring machine to try to describe。What computation was。

 and it turns out that there was other attempts to define computation like the Church's Lada calculus。

 they've been proven equivalent， and I think the languages that we programming language that we use also are equivalent to these machines。

 so yeah， you can use lots of different representations to express the same computation。Okay。

 questions on symbols versus meaning。So it's kind of a deep philosophical issue。

 but the main thing I want to point out at least from the machine point of view。

 is that these symbols have no intrinsic value to the machine。

 they are ASI codes that a program will draw a blyph。

screeneen for you and that you as a compiler writer will have to interpret in the way that you want it to the way that you define so you could define a language where this ASI symbol means division if you wanted。

 that might be confusing because everyone sort of expects this to mean addition。

 but you could define that you could define this symbol here to mean 70 if you want or to mean in a string you could define it however you're like yeah。

皆さいさが。Yeah， so if you have one symbol that means multiple things。

 that's actually a really good segue into syntax， but perfect meaning languages do have different meaning right so in some languages the plus symbol means concatenation。

Depending on the type， right， so like in Python， for instance。

 has anyone ever programmed a language where plus is concatenation？not many。

 so C has very little of this overloading of operators where。

The only overloadning it has is that plus plus mean you can use it for floats and you can use it for integers。

 right？At the machine level， are these the same assembly operations， a floating point addition。

 and an integer addition？No right， they're different operations。

 but in C that same symbol is being used for both， so you do have this case actually quite a bit in languages。

Yeah， so each language defines its own meaning of its symbols。

 there's like a shared lineage of a lot of these languages。

 but like your colleague pointedted out there are these esoteric languages like Mo and Bra F。

That use a very restricted set of symbols to be able to express computations that you can do in other languages as well。

Do you mean the ambiguity that we read about？Yeah， so as Terrence Power pointed out of the book。

 ambiguity is kind of annoying for development， for programming languages。

You might imagine a language that would allow ambiguity。

 but in the programmingm language that I know of， ambiguity is removed。

 so the languages are unambiguous or at best the language of diviners will say this is undefined behavior。

And the compiler can do it ever at once or just never do that。

I don't know if that's really ambiguity， but it's up to the language designer to say what the language will do and with deterministic computation。

 it's usually easier for a programmer to know that there's only a single meaning of that set of symbols。

Now， in that if you read， the reading， they also pointed out there you know。

 there is ambiguity in language like you can never put too much water in a nuclear reactor。

 which is kind of a scary end。Silly one， which has two meetings， right？

Put as much water as you want or you。Don't put too much water in the reactor。

And we'll talk about ambiguity， syntactic ambiguity as well， just in a bit。不点哎。

Think from a programming language design point of view。

 it'd probably be confusing for your developer if different compilers did different things with the same construct。

And that does happen with C because mostly because of undefined behavior。等会儿啊。All right。

 so let's talk about syntax trees。All right， so who did sentence diagraming in school？

ThisThis is never done before I feel like there's fewer and fewer people who knows what C diagram is。

あオッケー。So not many， all right， so let's diagram this sentence。What's that。Yeah， basically， yeah。

What's the subject of the sentence？The boy， who says the boy is the subject of the sentence。

 who thinks it's something different。Okay， so even those who never did sentence diagramming。

You still sort of know about this sentence structure， right。

 you know that there's in English at least。The subject is usually first。

 at least some type of sentence。こそ。s嘅。That is an article。It's not a proposition。

 two is not a preposition。But we can call this a subject phrase。

So I'm not an expert in English or language grammar。

But I'm going to call this whole phrase the subject。Yeah。

 and that's actually a really good point is that you could actually break down。

The subject phrase into smaller pieces， which we'll see， all right， what about the verb？the。

 where's the verb？We， right， so here's our verb or verb phrase。So degenera only has one。

 what about the object of the sentence？Yeah。Store， so I'm going to call to the store。

The object phrase， what kind of object is this direct or indirect？

It's really a shame that nobody learns grammar anymore。Who says indirect object。

 who says direct object？It's indirect because there's a preposition saying to the store。The boy went。

AmAm I wrong？Am I wrong， is the right， who says indirect？Nobodys。

I'm pretty sure it's the indirect object。不。I think。😊，So if you said the boy went the store。

 that would be a direct object， I think。Okay， well let's I have a different one。

 the boy eight at the store， is the store indirect or direct？

Indirectrect what if the boy ate lunch at the store。Lunch is direct at the store is indirect。

 so I think it's indirect anyway， there's be questions on this， don't worry about it。

But I want to point out for you that you can。Create this。Hiererarchical tree。

Of the sentence is syntax， so a syntax diagram is really just。

OrA sentence diagramming is really just syntaxs。It's breaking the words down into groups that are associated with the parts of the sentenceus。

In a sentence。So in the current understanding of English grammar。

 if you said like the boy and the girl went to the store， you mean like that， there's two subjects。

So。So how would we solve that， how would we solve two subjects？What's one way to solve it？私さ。Yeah。

 we could take our subject phrase。And we could break it up into， say。Let's say， it's a。And phrase。

And we could have two pieces of this an phrase。The boy。The word and。And the girl。

So we still have a single subject in our sentence。But we can further break down the subject part of the sentence into multiple pieces。

With new descriptions of what does constructs in the language mean or what their structure is。

Does kind of make sense， does this look familiar has anyone's really seen this have seen this before？

Wow， not many， no grammar， who's learned a foreign language。

 a language that's not their native language。You didn't learn about grammar in that language。

 you learn about grammar right you learn like parts of speech like this is a verb， this adverbs。

 yeah， so these are the names of the syntactic constructs in human language。

And if you've nevert done this before， you can represent us as a tree where。

You have a single root of this tree like the sentence。

And several patterns of structures that represent the different types。

Of utterances or expressions that you can say。In that language。And so yes。

's one of your colleagues asked about。The interpretation of words in this language。

 So let me give you an example of where syntax。

![](img/3dbce149caa9abe57907c6f46db929be_15.png)

Matters or syntax is kind of real in a sense， so here's another sentence the boy leaving his leaving behind his friend went to the store。

So what is the subject of the verb went？😡，W doingho's going here？

If I said the boy leaving behind his friend went to the store。If I say that to you。

 if he didn't read it， if he didn't it， if I just said the boy leaving behind this friend went to the store。

 who's going to the store？😡，The boy， right， so if I said the boy leaving behind。

His friend went to the store。Doesn't quite sound right， right。

 like it's not quite something's awful about that。So。Comas， so you don't say commas right。

 like nobody says the boy， comma leaving behind his friend， commma went to the store。

 so you didn't have to have the commas to hear that the boy is the subject， right？😡，Anyone disagree？

Or if I said the boy walking fast went to the store。What's the who's going to the store。

 did fast go to the store？Or did the boy go to the store？The boy， right？So yeah。

 I know like looking at it， yeah， yeah， go ahead。We're talking about。反国平。

So the went doesn't have an object at all， you' saying？Okay。I'll take， I don't know。

 I'm not an English grammar expert。Okay， so。All right。

 two things to point out here is that I think most of you， if you heard this sentence。😡。

You would understand that it's the boy going to the store， right， not his friend。😡。

The boy leaving behind his friend went to the store。Because you can kind of。

 even though this is a single sequence， if we just looked at this part here， you would think， well。

 a friend is going to the store， but I think most。At least native English speakers would not interpret this as his friend went to the store。

 agreed， disagreed。Kind of agree。Or if I said the boy walking fast went to the store。

No one would think fast。Was going to the store， right？

So somehow you are understanding the fact that this here， and even some of you said， well。

 you corrected me saying， well， put comms， right？😡。

So that means you understand that this is a separate clause from the boy who went to the store。😡。

But there's nothing here saying， here's the subject， the boy。

 here's this modifying clause leaving his friend。Here's now the verb， nobody said that right？

But you were still able to grasp that the boy and went。Were the connected parts of the sentence。

Makes sense， you got it， right， you still got it Now one theory， this。

 the kind of Chomsky linguistic theory is that we have a built in ability to use grammatical language and that when hearing this。

 you'll actually。Kind of no or in speaking this， you'll be able to kind of pause your sentence the boy went to the store。

Push that onto the stack， so to speak， and starts saying some other parts， saying some other clause。

 and then come back up。Pop the stack， so to speak， and continue talking about what the boy was doing。

And this kind of stack based or weight holding state， while you go on pro language。

 this is exactly how computer languages， programming languages are processed。In the machine。

And the reason this is possible to kind of， I didn't。I forgot to link to this。

 but so Chomsky is kind of。

![](img/3dbce149caa9abe57907c6f46db929be_17.png)

Classic phrase here。To show the difference between， say。The boy leaving behind。

 his friend went to the store， the reason that that sounds off if his friend is the subject。



![](img/3dbce149caa9abe57907c6f46db929be_19.png)

It's because Kmsky believed that there was an internal built in capacity for this grammar。



![](img/3dbce149caa9abe57907c6f46db929be_21.png)

And he illustrated this with two sentences。So he had one sentence。

 colorless green ideas sleep furiously。Sounds kind of right， right。

 it sounds grammatical because we have a subject， we have a verb， we have an adverb here。

But this sentence here， furiously sleep ideas green colorless。

Even though both of these are really nonsense， basically right， like what does this mean。

 he tried to design a sentence that would have no meaning。

 you know how can you have a colorless green， how can you have an idea that has a color。

 how can you sleep furiously， so he tried to design a sentence that was grammatical but meaningless and contrasted with a sentence that was ungrammatical。

To point out that when we as humans hear this grammatical sentence， it sounds right， right。

 it sounds like a correct sentence， or at least it has some correctness to it that sentence2 doesn't have。

Make sense。No， yes， no， getting some skepticism， what's your skepticism？没有。No skepticism， yeah。

I mean here， yeah， because you're already assuming that sleep must be an adjective just because of what because of its position in the sentence。



![](img/3dbce149caa9abe57907c6f46db929be_23.png)

So syntax can be thought of kind of informally as just。



![](img/3dbce149caa9abe57907c6f46db929be_25.png)

How kind of legal orderings or groupings of words？And in fact， when we looked at our。



![](img/3dbce149caa9abe57907c6f46db929be_27.png)

Arithmetic expression。The reason that you could interpret。

This sequence of words as an independent multiplication was because of the syntax you had in your head about arithmetic operations because these are grouped in a certain way in order right like the you have the operation in between。

The symbols for numbers， you could interpret that as multiplication， so I didn't say。One， two。

 three plus multiplication。Which there are other interpretations of。

But you were able to understand that the relative orderings of these words。

 how they were ordered together and grouped。Actually it was connected to the meaning。

 you use that to ascribe meaning to that， so it's not enough to just know the meaning of each individual symbol。

They're relative positioned to each other and how they're grouped。

 also we also use that to ascribe meaning。2， simple。Little less skepticism。So this this。

Chmsky in view of linguistics is kind of the minority view these days in linguistics。

 but he used this as evidence。

![](img/3dbce149caa9abe57907c6f46db929be_29.png)

that there was an inborn human capacity for grammatical language that as I currently understand。

 has not been demonstrated in other animals， language has been。

 but this kind of grammatical structure of languages， as far as I understand。

 I'm not an expert in this has not been demonstrated other。All right， questions on。

What syntax trees are？You guys with me on this？You guys with me， okay。

I'm not sure if you're wrapped with attention or not confused or just bored， yeah。

How are they broken that。那が。So yeah， so how you actually design a human language grammar。

 that's like a project that's been long abandoned， people use statistical approaches to analyze human language now like natural language processing。

They kind of combine grammatical and statistical approaches， but far as statistical。啊。

But this grammatical view of language is preserved in the compiler world where we use it to actually process unambiguously input languages。

But you could do that for human language。It would be hard because we had a huge grammar。

 there are sentences of a single word。So you have to like enumerate all of them。啊Yeah。Yeah。

 exactly right， exactly right， so that gets into the next part， so any other questions about this。

 this just notion of syntactic structure。Regardless of the philosophy behind it， that we can diagram。

These。I show here， we can diagram。These sentences， we can name the syntactic structure。

And associate them with the ordering of words in our language。Okay。

Not whether not sure that I can't read the room， everybody looks very stone faced。Okay。

 so just to kind of highlight the connection between syntax and meaning。

Is that you can have the same word store。There are two sentences here。

 the store is closed versus squirrels store acorns for the winner。Maybe not， I guess they do it here。

 do they do it to Clark here， it's the same word， right， it's the exact same symbol。

And you would have no idea what its meaning is without its relative ordering， right。

 so what is the meaning of store here？Yeah it's a shop that sells stuff right。

 and here does the store mean in a shop that sells stuff？No。

 it means to squirrel away or to place things for future use。So the meaning depends。

 at least in part on the structure of the sentence。All right。

 so let's get back to the programming language world and look at。Arithmetic expressions。

So let's make a let's try to make a syntax treat for this。

 even though we don't have like a grammar yet， you probably have a grammar in your head of what this looks like。

 So let me draw a。Syntax tree。For this。Arithmetic expression。So at the root。

 I'm just going to call this an expression， let me use E。To make this an expression。

And so let's say an expression has a left side， and operator。And a right side。第二。

That's very closely related， so in fix a PostF， you could think of it as a translator or a compiler between two representations。

 so if you who did in fix a PostF？Oh great okay， okay， so this is very much related。

 I don't know if you did a tree to tree tree， a syntax trees of it， you just wrote an algorithm。

 right？So implicitly in your algorithm， you are actually parsing。That in fixed notation。

 And you were using a stack to hold on to， just like in the。The example of。

The contentious example of。The boy leaving behind his friend went to the store。

 you can think of a similar approach to the in where you used a stack in order to hold onto one of the sub expressionions in the language。

This tree representation is just， it's just another way to represent that holding of subexpression values。

So okay， well， actually， before I draw the tree。How would you？How would you。

 let's say if you wanted to write an assembly program write or do this on a calculator。

🤧How would you compute this value？Let'sSo this is inF， this is inF， this is inF right。

 so how would you compute this yeah？Okay， so what operation would you do first here？

So you would do nine plus three and get。12， and then what would you do？全。And you'd save that result。

And do the subtraction So's two operations here， right？So we can capture that in a tree。With。呃。Me。

Do it this way。So。So here we did the 12 first。We did the left side first。

So if we just had nine plus three。We could。Capture the syntactic structure of this as an expression that contains a left side。

 a right side， and an operator。Yeah， let's say E means expression。

 just so I don't have to write expression in my terrible handwriting every time。

So let's say E does a nascent expression， just like we said， subject。😡，So nowhere in this expression。

 does anyone say this is an expression。😔，But we can name the syntactic structure。

And recorded explicitly in this tree， just like we did with sentence diagraming。So we can say。

 all right， an expression consists of。A left side， a right side， and an operator。

So we can start defining the structure of this expression explicitly。By naming what the structure is。

And defining a kind of schema for what it looks like。So we can say， all right。

 an expression consists of some left side， so let's say it can consist of a number on the left side。

 an operator， I's say it's always plus。And a number on the right side。

So we can make a kind of template to represent。What all syntactic structures？

Look like for these expressions。ItKind of makes sense， it's a little template that says， well。

 can expression is a number， operator number。So here I mean， an means。

Now if we want to have multiple operations in a single expression we can expand out the meaning of expression。

 so here in this expression we actually have two operations。

 but implicitly there's a saved value here that we never really say we don't tell anyone， okay。

 here's an expression， first do。This one and save its value。

Nobody ever tells you that right you do that in your head。

 and so we can make these structure of this explicit by defining this。

Kind of template that it describes what all of these syntactic structures look like。

So to capture that intermediate result， we can also allow expressions to have another expression。

As one of its。Opers。And so here I can say， well， all right。

 we have a template for E can have E on the left hand side， a minus operator， and a number。

That kind of makes sense， so this E here has an E on its left hand side。

Has a number on its right hand side。And it has an operator。That's a second symbol in its structure。

Questions on that， does that kind of make sense？Yeah。Exactly。

 you're defining rules that capture all the possible syntax。

 you're defining syntax rules for this language。So you can kind of。

Philosophically assume that in your head， you're kind of processing all of this grammar implicitly。

At least that's what a machine is going to do。Processing the grammar implicitly and then using that syntactic structure in order to interpret the meaning。

Of this。Of these symbols， remember， the symbols don't have meaning on their own， yeah。一个。かで収に。出身。

Right， so yeah， so actually when you get if okay good who learned about regular expressions。

 think this is indireet， I don't know if it's required for this place。

 so not everyone learned about it， so regular expressions are a formal way to describe languages。

 so languages are just sequences of strengths。And an expression defines constraints on what legal strings are in that language。

Now， if you take big discrete， you'll learn that regular expressions cannot express syntactic structure。

They're not powerful enough to do that because they're finite， they have a finite amount of state。

 these grammars require an unbounded amount of state yeah。変んでこれ。Anywhere， anywhere。Oh。

 the principles of orientation， they teach it okay， so that's also not required for this class。

 so I can't assume yeah yeah。I think I won't have time to do it here， take big disc， take disc too。

But it basically comes down to matching parentheses。

 so you can ever write a regular expression that will match an arbitrary number of parentheses because you always have to grow the number of discrete states that you need to represent it。

It's called the pumping Lemma is a proof。Dispro of it。

 so take big discet and you'll learn all about that。Okay， so let me。

 let me clean up this grammar a little bit。 So let's make。A much simpler version of the grammar。

 let's just say。Any。Any expression is。An E followed by an operator， followed by another expression。

And let's say an E can also just be。A number。And let's define my operators to be plus。

 I'm going to use a little regular expression syntax here plus。

Or minus or multiplication or division。Everybody with me on to answer any questions on this？

I'm just using this pipe to mean or。And let's say a number is。Single digits， yeah，1，2，3，4。

All the way up to nine。So this is a kind of template that describes the syntax of all possible expressions。

In my arimetic expression language。And so using this。

I can take any expression in my language like one plus two。Times three。

And I can figure out how these expressions are grouped together。

And whether they actually are an expression， so if I had another symbol here。Like a carrot。

Because this carrot is not in my grammar。Or if I have an expression like one， two， five。

This is also not in my grammar because I only have single digits in my grammar or if I had one， two。

 five。Plus。For instance， five。Plus times3。This can't be represented in my grammar， right。

 there's no way to represent this in my grammar。So this defines not only what the legal expressions are。

 but also。Removes all non expression。Sentences。Okay， so let's show how this。

 how we can derive a tree for this expression。So the way this works is you start。

At the first symbol in your language。And you can think of this as a schema that defines what the children nodes are of your tree。

 so E will always have， in this case we kind of have to guess which one to use。

 but let's say we guess right and say， well all right， it's going to be E followed by an op。F byい。

Question so far with me so far。Can use this as a little template to tell us what the children of our tree are。

And then here， E can either be another one of these E E expressions or a number。

 which one should we pick？😡，Let's say another E， okay， so E followed by up。Followed by another E。

What about this E here or actually， let's continue to illustrate， what about this E？

Should we use this first rule here or the second rule？Second rule， so why， why the second rule？Yeah。

 if we did the second rule， there wouldn't be enough numbers to fill in all of the parts of the tree。

So there are algorithms structure of doing this we're going to do this very informally， Okay。

 so numb and that nu， we can just pick the first number in our in our sentence op is obviously going to go to。

The plus here， now what about this E？Num， who says numb？What about E E？So if we did E E。

We'd end up with。Three E's， and there's only two numbers left so。It wouldn't work out。

So I'll leave this as an exercise for you to figure out why it wouldn't work out。

 but if we have this as a numb， that numb，Maps to two。

And that leaves star as the up and this E as another nu。For three。So Darre deriving this is。

A tricky algorithm to itself， but seeing this tree， does this tree make sense？😔，For our rules。

 we sort of get the connection between the trees and rule yeah。AOkay。

So what does order of operations have to do with this here？😔，So this， so okay。

So why is the plus first here？对呀。多拳。Okay， so this grammar is correctly。Psing。

We can make a tree for this sentence here， so this grammar doesn't have anything about order of operations encoded in it。

Now your objectiveing because you want order of operations。

 but in order to understand why we have order of operations。

 let's see how we can actually interpret this tree， actually ascribe meaning to it。

 so the syntax part gives us the grouping orderings of words， how they relate to。

The grammar constructs in our language， but in order to。Finish acribing meaning to this。

 we need to interpret it somehow we'll compile it， so let's do the interpreter approach of this。

 so let me give you a very simple interpreter algorithm for this。

We walked the tree in a post order fashion。And if there's a leaf。Notode。

We just translate its symbol value to its math value。So I'm going to denote that。Like this。

Now this looks very tautological， but just think this is the ASCI code and this is the machine code。

 so this is the ASCI。Representation。And this is the。Machine code representation。

 so I'm going to translate the ASI representation to the machine code representation。

When I see a leaf node， when I see this numb node。And when I see an expression。

What I'm going to do is I'm going to take the。Expression on the left。We're going to take its value。

And I'm going to take the expression on the right。It's value。And I'm going to。

Computer function that corresponds to the operator。To get its value。对。Well。

 it's going to end up being recursive， right？When I'm here。

 I need to get the value of the left side and get the value of the right side in order to get the value of the left side。

 I need to pause。and evaluate the value of E so to value at the value of E。

 I need to get the left side， I have a rule here that tells me how to evaluate that left side if it's a nu。

And that tells me that its value is， let me use a different color here。

 its value is machine code one。Because I just convert the ASI code to machine code and its right value is machine code2。

I just convert the ASI symbol of two to machine code2。And then in order to evaluate E。

 I take whatever the operator is， which is plus。And I use that as a function to compute。One plus two。

 does this syntax look uncomfortable to you？All right， let me do this in a different way。

To make this。Less。Uldly。So if I havent。And up。Let's say that I take plus and I convert it to the add function and minus and I convert it to subtract function that seem a little better。

So I'll make red to be。My machine。And black to be the ASFI。So here。

Is converted into the ad instruction。And then the rule for E。It's to take whatever the app is。

 take whatever the value of the left is， take whatever the right is， and apply。

The function to those two。Values。Questions on this， questions on us。This is confusing。对呀。

You mean the calculator project homework？The homework will be making a grammar。

be writing your grammar。So okay， so to review， we start at the top， we do a post order traversal。

When we reach a leaf。We look at the rule for how to interpret。Eum。

So the rule is to turn that ASI value into machine code。We do that for both leaves。

Turn that askCI value into machine code。When we see an up。We convert that into。

A function that corresponds to the operation that we want to do， this could be， for instance。

 assembly code for're translating this。And then the rule for。See。This E op， actually， let me yeah。

 we could write the rules here， that would probably make it clear。

 but the rule for E when it's E op E。Is to construct。This function call。

From whatever the app is and the two values on the left right。Questions on that， on that。

Seems like it's clear to some， maybe not clear to others。All right， so continuing this， how do we。

Get the value of this year。We we take whatever the value of the right hand side， left hand side is。

Whatever the value of the right hand side is。So the value on the right hand side is what based set our rules。

It's three because this rule tells us。To convert。呃。An ASI number into its machine therapy。

And how do we compute the value of this E？We take the op。

Converted that ASI symbol into some function that's actually going to compute the value。

And we could represent this in a number of ways we could either leave this。

Add in place or we could compute it on the fly here。Let's say we just lead it into place。Then。

This is what。The resulting。Value of this tree is going to be yeah。How would I okay。

 so optimizations would look at this representation and try to change so for instance。

If we can compute， add one plus2 at compile time， we can just compute it and then convert this into。

Mot。Three plus or mo three times three。So that would be an optimization， right this？呃。

Function that's this call that's produced by your tree and then converted into another call that has fewer operations。

 that would be an optimization。Okay， questions on this basic idea of traversing the tree。

And converting。Or interpreting each symbol。Of leaves。And。

Interpreting the meaning of these constructs in terms of some computation。

Any questions on that process of traversing the tree and computing the value？

Of this expression by traverse in the tree。So if you did the in fixed to postfi。

 you did something very similar， you actually traversed that tree although you did it in a very shorthand way by using a stack。

 but you effectively traverse this tree and your output was not the value。

 your output was a translation。Of that treaty and so maybe maybe next time I can start with that to kind of give you a basis so who's done the in fix the postscript before。

 how many people have done it， who's not done it？Okay。

 so seems like everybody had This is basically the same thing。 So next time let me frame。

 let me make a note to frame that。Next time since you all have that。

As a basis to frame that as this kind of translation。



![](img/3dbce149caa9abe57907c6f46db929be_31.png)

Okay。So all right， so for homework， you've got this。



![](img/3dbce149caa9abe57907c6f46db929be_33.png)

Exercise to write this grammar do your best I know I didn't like go over in detail the grammars but do your best to write a grammar similar to what we have now for reverse Polish notation feel free to start the CalC project you don't need to understand parsing to do it you can just copy the work and then next time let's finish up parsing and then I'll show the inter representation we'll get started on our compiler project All right thanks everybody。



![](img/3dbce149caa9abe57907c6f46db929be_35.png)

![](img/3dbce149caa9abe57907c6f46db929be_36.png)