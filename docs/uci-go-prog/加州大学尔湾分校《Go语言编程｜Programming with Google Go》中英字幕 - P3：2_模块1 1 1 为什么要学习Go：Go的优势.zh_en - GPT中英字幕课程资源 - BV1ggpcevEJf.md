# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P3：2_模块1 1 1 为什么要学习Go：Go的优势.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

🎼。

![](img/a83ea71a34e9685410d87bd94a6cc29a_1.png)

🎼う。🎼Yeah。So why should you learn go What's unique and good about the go language。

 I'll go over some of the highlights of that。 Different people have different opinions。

 but there are certain features that are pretty uniformly understood as being advantages of the go language。

So some of the advantages of go first runs fast。 okay that's always a good thing。

 and I'll talk a little bit more detail in these slides about why it runs fast and faster than what right It doesn't run fast than everything。

 but it runs fast in a lot of things and we'll talk about why。Garbage collection。

 is's another feature that in similar languages， meaning languages that run fast， like go does。

 they don't have garbage collection。 So garbage collection is a really useful feature。

 I'll describe what that is。Simr objects。 Now this could be an advantage is disadvantage。

 but the idea is that go is essentially object oriented， although some might disagree。

 but it has this concept of objects。And these objects are generally the object orientation is a little simplified as compared to other languages。

 so this is good， it makes it easier to code， you don't have to use these complicated features。

 of course you never had to use them anyway， but it makes it faster and simpler to use so now somebody might argue that look。

 these features are useful features I wanted them but go is actually a simpler object oriented implementation than you would see in other languages like say C++。

😊，And another feature of go is that it has concurency。

 efficient concurrency implementation built into language。

 so there are a lot of these concurrency primitives that are built into the language and that are efficiently implemented and we'll talk about those。

😊。

![](img/a83ea71a34e9685410d87bd94a6cc29a_3.png)

So to start off with， let's go into that code running fast thing and tell you why that is the case。

 And to talk about that， we've got to talk about a little bit about languages in general differences between languages。

 So I've got these three very broad categories of languages。For machines。 So one is machine language。

 next is assembly language。 Next is high level language， right， And that's a really big category。

 But let me explain machine language。 start off with that is the the lowest level language。

And it's directly executed on the CPU on the processor。

 So the machine language instructions are very， very straightforward and simple。 you know， add。

 multiply， you know， add might add to register contents， put the result in another register。

 something like that。 very small steps， each machine language instruction。Now。

 and this runs directly on the processor。So so there's that。 there's assembly language。

 an assembly language is basically machine language， almost a one to one mapping to machine language。

 So in machine language， say you had an ad instruction that might be represented as a sequence of zero and1。

 1，1，1，1，00，0，0， that might be an ad op code for an ad。 So in assembly language。

 you would use the word A D D so it maps one to one to the machine language equivalent。

 but you can read it because it's English。 Now it's concise English and I would argue it's hard to read but it's English mnemonic。

 So a human could read that and could write that if you wanted to。

 and people do sometimes if you want something to run really。

 really fast then and really efficiently， then you'll write it directly in assembly language。

You know， that's outside of the scope of this class， that's hardcore， I will call it。

 that is not something we're going to really cover in this class。

 but sometimes you do write directly in assembly language。So there's assembly， machine and assembly。

 and assembly language is basically a one to one mapping to machine language， not completely。

 but very close。So fundamentally， they're the same complexity， they're the same language。

 but assembly language is easier to read。Now as high levell languages， that's everything else。

 that's a broad category。 A high levelvel language is a language that essentially humans commonly use to program in。

 They are much easier to use than assembly language or machine language they provide you with lots of abstractions that any program would be used to。

 for instance， variables assembly language and machine language do not have variables。

 they have memory and you can put stuff in it， take stuff out right and there's no idea of a type or anything like that and assembly language。

 machine language， but high levelve languages provide that to you right if statements now assembly language。

 machine language they have conditional branches and so on。

 but these are generally much harder to use than your standard if statement that you would see in any normal high levelve language or loops or four loops。

 things like this。 you can create these things in assembly and machine language。

 but they are harder to write than they would be in a high level language So high level languages are basically everything that most people program in。

So one thing， so you can imagine these different categories now the languages that we're talking about。

 go， go is of course， a high level language in this set of list in this three categories。

 it would be considered high level。Remember that term high level is subjective， okay。

 but I'll call it high level， so all software， what I have highlighted in the slide。

 all software needs to be translated into the machine language of the processor to be executed。

So what that means is。If you've got a processor or of some kind I7 or whatever processor you're working with。

 that processor does not know C or Java or Python or go or C+ or any of those。

 right All it knows is its own machine language， say X 86 machine language if it's an Inbase processor right or an AMD or something like that。

 So it knows that machine language。 So in order for the code to execute on the processor。

 it has to be first translated into the machine language of the processor。So even if it C， Python。

 Java， whatever it is has to be translated。 So there is this software translation step that has to go on。

Okay， now this translation step， it can go on in one of roughly two ways。It can be compiled。

 It can be a compilation or interpretation now compile a compile language is a language where the translation from the high level language to the machine code happens one time before you execute the code before you deploy the code happens one time so like in C C plus plus go Java partially there's a compiler and you compile the code。

 So somebody writes the source code， they compile it and then they execute it。

 and they execute the compiled executable the compile executable is basically machine language code plus other this stuff。

 but it's basically machine language code So the idea behind a compile compile language is the key thing we want to bring out anyway is the fact that this translation occurs once It doesn't occur while you're running the code It happens before you run the code And then when you run the code you are just running the machine language instructions directly because they're already compiled into machine language by the compiler。

So the other way to do this is interpreted interpretation， an interpreted language。

 what happens is instructions are translated while the code is executed。😡，So。😊。

If you got so so what happens is it happens， it adds time to the execution， right。

 because every time you see an instruction and say Python， that code。

 that instruction has to be translated into machine code on the fly。

And that takes a certain amount of time just to do that translation。

 so in addition to actually executing the instruction。

 you've got to do this translation from the instruction into the equivalent machine code。

 so that slows you down。😊，So the translation occurs every time you run the Python code， say or Java。

 right， the Java Bte code， I put Java as partially in both categories because Java。

Java has it's compiled， but it generates what's called Btecode， not actual machine code。

 and then the Bte code has to be interpreted at runtime。

 So there's an interpreter also the Java virtual machine。

 but these interpreted languages require an interpreter to be executing while you're running your code because it has to be doing this translation as you execute the code。

And so that slows you down。Now this is trade off between compile code and interpreted code。

 The first level of this trade off one big difference you can see is that compile code is generally faster to execute。

 That's because you don't have to do the translation every time you run the code so it's going to be faster Now there are people who would argue the opposite but generally compile code is a lot faster。

Now on the other hand， though interpreters make coding easier。

 So the thing about interpreters is that the interpreter itself。

 that program that is doing the translation of your code， it can help you。

 It can handle things that you as a programmer don't want to handle for instance。

 in Python I don't have to declare my variable types。

 I can just start using a variable and the interpreter will say it looks like he's using it as an integer and make it an integer So that's something that the programmer doesn't have to think about。

Another thing that interpreters commonly have。Often have is memory management。 In fact。

 almost always they have this。 They can manage their memory。 And by that， I mean。

 getting rid of variables and other pieces of data when you're not using them。

 So when you use a variable， that variable has to go into memory somewhere。 and that memory。

 if you keep making variables and using a memory space， you will eventually run out of memory。

 things will slow down， you run out of memory。 So you have to manage your memory。

 that is when you're done using an object， you want to get rid of that， delocate it from memory。😊。

And that happens automatically in an interpreted language。 So the interpreter handles that。

 So that's a good thing about interpreters。 So go is a good compromise between this compiled and interpreted type of language。

 It's a compiled language， but it has some of the features。

 some of the good features of interpreted language， specifically it has garbage collection。

 So garbage collection is the automatic memory management that I'm talking about。

 So this memory management， you know where should memory be allocated。 So I say， I need a variable X。

 Where should it put it in memory， What type of memory should it put it in。😊。

We'll talk about that a little bit later。 But also when when am I done with that memory Because when you're done with the memory。

 you can get rid of a memory， You don't have to use it anymore。 You can use it something else。

 So that's what I talk about memory management。 That's what I mean。 And this happens automatically。

 The garbage collector can figure that out。 It says， oh。

 it looks like this program is done with variable X。 I will free that memory now。

 And that happens automatically。Manual memory management is hard。 Okay， and， you know， this is。

If you've ever done C or something like this， you know this。 decate memory too early。

 if you stop using it too early， then you'll have false memory access because you still need it。

 So you'll use the memory that's already delocd and errors crop up because of that。

 Also if you decate too late， then you're wasting memory。

 you can have what's called a memory leak where you have more and more memory that's not actually being used。

 but it's being blocked up because your machine thinks it's being used So memory management manually is very difficult and there are lots of errors。

 security errors to So go has a garbage collection package included garbage collection garbage collection code included。

 So when it compiles your code， it also compiles garbage collection into your code automatically。

And this is typically only done by interpreter。This is a compile way。

 which actually has garbage collection， which is a really good feature。 Now。

 downside is that it slows down the execution a bit， but it's an efficient garbage collector。

 so it doesn't slow it down much。 And you get a lot of advantage out of having this automatic garbage collection。

😊。

![](img/a83ea71a34e9685410d87bd94a6cc29a_5.png)