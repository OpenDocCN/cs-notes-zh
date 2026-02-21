# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p11 -11- L9_  ISA and Microarchitecture (Spring 2025).zh_en -BV1iV1XBWEJW_p11-

![](img/4c2de24a448f22f60a4668242a2bce1b_0.png)

对。Yes。Yeah。お。法。でこしで。3是。嗯对。Yeah。Is there everything good live stream， can you hear me？あ。All good。不是。

Can you hear me。How about that？在全部。No。It。Yeah。Can you hear me How it's all green， yeah， okay。Okay。

 good。There's some delay， maybe。Yeah。No， not that one。や。包啊。Thank。そうです。So。我你刚才放的。ま。3手机。で是。怎么组备有了。Okay。

でまさんだ。失礼しはい。啊跟唔啊。Yeah。あいます。ね。しは。好家粉。没问一下。は。そ。Okay。Yeah。ますす。I。Okay， let's start now。

I assume everything is working fine， online， audio， video， everything。Okay。So welcome back。

 looks like we have more people than last Friday， but I'm not sure maybe we're losing people on Thursdays too。

 that's what usually happens。Because people are hopefully watching it online because we will cover some things that you may not get in the books。

Okay， so we're going to continue our journey in ISAs and micro architecture。

 we're going to finish ISA today and then jump into my architecture and we're going to continue building new and new architectures。

 and then we're going to build up to modern systems in several lectures。😊，Let's get started。

 does this work and it didn't work。So this is your last chance。

 meaning last day for this review assignment， if you haven't done so， please do it。😊。

how many people have done it。Okay， that's great。 How many people have not even looked at it yet。

 Oh be shy， that's good。 Well， if you want extra credit， you don't have to look at it。

 but if you want extra credit， it's probably good to look at it， you know。😊，Yeah。

 nothing is required okay， there's another assignment for extra credit。

 which is due a little bit later so I can take a look at that also。😊，Is everything okay online？

I don't see something's moving， so。Is a live stream okay？Yeah， okay。

 maybe my computer is kind of not a case。 Something is not moving， but。Okay。Okay。Yes。

This is the importance of testing， you know I was doing online testing while I'm speaking and existing processor should do more online testing。

 it's always better if you have more more checkers。

 other processors checking what this processor is doing。

 but if the other processors are not checking that and you have a problem also as you can see right？



![](img/4c2de24a448f22f60a4668242a2bce1b_2.png)

So these are all fundamental principles of computation， reliable computation。

 if you want to be reliable， you need checkers， Okay， what's the problem？😊，你对就。Okay。

 you can see me right now， so I don't know why that was not moving。They can see us。Yes。对需要。Okay。

 because there are people， probably some of your fellow students drinking beer and watching this lecture on their sofas or something。

😊。

![](img/4c2de24a448f22f60a4668242a2bce1b_4.png)

Okay。我。Okay， it takes a while， so。在说。な个。

![](img/4c2de24a448f22f60a4668242a2bce1b_6.png)

Okay， I think it's working。 So you just， it just takes no。 it was not working before。

 There was something wrong before， but now it's working。 Yeah。

 it's working now so can get back to where I I was。そ。I need lecture 9 A， not 9 B。

We're not at 9 B yet。电 now。这。はい。好。私。Okay， any questions in the meantime type？



![](img/4c2de24a448f22f60a4668242a2bce1b_8.png)

Anybody has questions on anything， okay？Okay， I think it should be working。Don't panic。

 there's still time。Okay， so the problem is change doesn't get reflected immediately， but wants you。

Fix something which I don't know what it was。It works better。 Okay， there's something right now。

 Okay， let's go back to the slide where I was at。Okay， this is where I was at actually， yeah。

 more assignments but。😊，Okay， well extra assignments。

 so today we're going to finish instructions and architectures I'm going to recommend the assembly lecture assembly programming lecture。

😊，I think you guys should fix it if there's some problem I don't want to stop the lecture anymore。

 I hope you can fix it quickly。😊，It's not sharing， is that the problem？It is sharing， okay。

 not even on Zoom。Okay。We have people attending on Zoom。I hope you're recording in some other way。

So should I wait or should I go？Let's wait because there are a lot of people attending online。I mean。

 normally there's no problem on Zoom， so I don't know what's going on。I need。そです。确。P。Yeah。

 so we do for that。You guys can take your break over。行吗？せ。好然。は。这是什东。没事没是。这个。这。自己的。No。Yes。

Now it's working， I don't know。Okay。Okay， everyone， I hope finally the issue is solved。

So hopefully you remember that we've been looking at different instructions at architecture properties。

 we've covered different types of instructions， we've covered the Wal Neumman model。😊。

We've covered operate data moment and control instructions。

 and we've implemented parts of them in part micro architectureiture。

 but we're going to actually go through the implementation。

 full implementation starting from today later in today's lecture。

 but I want to cover some things in architecture today first。😊，Have you covered instruction formats。

 addressing modes， hopefully those are clear。😡，So you had some readings last week。

 some of those were forward looking， which means we're going to actually cover some of these things this week。

 but I'm not going to divert from the books also， so I will talk about some things that your books don't cover but that are really important for critical thinking。

This is again just a jog your memory we have instruction processing cycle and there are six steps。

 not all instructions go through six steps， you're going to see this again and again multiple times and we have a state machine dictating essentially a computer is really a finite state machine and that finite machine dictates what instructions how you process the instructions specified by the ISA。

😊，We're going to look at a different way of designing a machine later today called single cycle My architectures that doesn't follow this sort of finite state machine。

 this is actually a multicyclemic architecture。We kind of got ahead of ourselves just to show you a better implementation。

 but today we're going to see some other micro architectureecture principles using single cycle。

 so keep in mind that this is a particular implementation， meaning a micro architectureecture。😡，Okay。

 so this was actually the state machine for LC3B full state machine and we've covered different phases over here so we were actually doing some micro architecture except we were not doing it let's say in a very rigorous manner because I want to actually talk about some principles also that will make this state machine look like a very nice processor but this is not exactly how existing processors operate so we will see much more ideas that make things much better and much faster okay this was something that you have seen so you're familiar with this picture and we covered a lot of things in LCC3 and MIPS architecture that I'm not going to talk about today we covered up codes data types addressing modes。

😊，Operated instructions data moment instructions and addressing modes that are associated with them and then control flow instructions finally and then conditional branches。

 conditional control flow so with all of these you should be able to construct programs and assembly and that's the extra lecture assembly programming is about there's a lot more to cover an ISs which I'm not going to cover because we don't have time for things but this is something that we discussed last time when you design an ISA and important choices what should the complexity of your instructions be if you actually make your instructions complex the instructions do a lot of work they do many operations and matrix multiplication for example a string copy a key value store access these are actually very high-level constructs that are very close to the high-level language or another design choices have simple instruction which is when an instruction does little work these are really lowlevel primitives that are much closer to the hardware the gates the boolean logic that we have discussed。

😊。

![](img/4c2de24a448f22f60a4668242a2bce1b_10.png)

![](img/4c2de24a448f22f60a4668242a2bce1b_11.png)

On top of which complex our can be built。And these have critical implications on both software and hardware Of course you can say I'm going to have everything complex instructions。

 simple instructions， then you're actually still pretty complex because you actually have everything right and some Is have everything almost today while everything is too strong but some Is that actually decide to have both simple and complex are actually considered complex ISs this is actually the last slide I stopped that you've seen the slide before this is actually a very important design choice when you design instructions that architecture course are your instructions data types and addressing modes are to the high- levelvel language Java。

 Python， whatever is your favorite language is today C+ plus。😊。

If you have an ISA that's closer to the high level language， you have a small semantic gap。

 you're far away from the hardware control signals。

 the end or not gate the multiplex service register file。

 you're pretty far away because there's a huge thing distance for which you can actually do implementation that actually is interesting because your hardware as a hardware designer now you have a lot of room to play over here。

😊，Whereas if your ISA is much closer to the control signals meaning you primitives like and or nor in fact nor is the only thing you need plus some control flow。

 you need to actually have you can be a minimalist and you can say these are the only instructions that I'm going to have you can get away with a single instruction I'm not going to tell you what that instruction is but it's a single instruction you can convert everything into that not a good design choice because it gives very little room for the hardware designer to optimize things if you look at it so another way of looking at is is how much room there is between the ISA specification and what I can do at the low level here there is very little。

😡，So put another way， if your semantic gap is closer to high level language。

 you have an easier mapping of high level to the ISA， let's work for the software designer。

 more work for the hardware designer。😡，That's a very fundamental tradeoff you cannot get away with and optimization burdens on the hardware mostly there's clearly some optimization burden on the software by deciding what how to map high-le construct written by the programmer to the instructions over here。

 but the bigger distances over here so the hardware designer actually has a lot of room to play。

 meaning they can optimize a matrix amount application in many。

 many different ways and change the latency as opposed to optimizing individual and or not operations and shift operations that may go to the multiply right。

😡，Here the burden is a lot more on the software designer。

 meaning the compiler potentially that compiles a high-level language into an instruction architecture or an assembly programmer that does it by hand。

 or a large language model that does it potentially today I don't think there's anything that does it very well today but think about that you're in that you're living that kind of revolution right now can you have a large language model do that for example。

 in an efficient way， so there's more work for the software designer but there's less work for the hardware designer here。

 this could be a good or bad in the sense that now hardware designer cannot not do much how much how many different ways in which can you optimize you can optimize an and operation not a whole lot let's say whereas if you think about a matrix multiply operation there could be many different ways and we're going to see multiple different ways later on so here the optimization burdens on the software。

Hopefully this is clear this is important because it's a really important design choice that you make now the interesting thing is you can change the trade offs and this is a principle that I'm going to introduce is the principle of injection。

😊，As I will tell you later， some famous computer scientists said any problem in computer science or software engineering can be solved with another level of indirect。

So assume that you're stuck with an ISA with complex instructions， data types and addressing modes。😡。

You can change the trade offs。Basically， you can say that okay， people write programs with that ISA。

 fine， they can write them， and I'm going to still execute them but I'm going to do something else in between meaning I'm going to actually have a very simple hardware with a very simple instructions that architecture。

 simple instructions， simple data type， simple addressing mode。

 but in between I'm going to do something else， I'm going to add a level of interaction meaning I'm going to translate。

😡，Yeah， I say that's closer to the hardware， which may be what all of the world's programmers。😡。

Are exposed to to an implementation I say that's really what I'm going to implement internally I'm going to design。

This part， as well as a software and hardware translator。

 I'm not going to expose any of these to anyone。 So the software designer can actually still write in the complex IA that people may have designed for a many number of years。

 yes。I mean， I get what you would ever。喂。Would you have a talk patience。Okay， yes。我话我喺四年。

You answered this question， okay， this will become more clear after we discussed this。😊，Okay。

 so this is one way， so I'm going to show that exactly first。

 but you can take a very complicated in of architecture like88664 that has been designed in 1970s and then over time people added a lot of stuff to it and it's a very complicated architecture you say I'm not going to deal with it completely in hardware。

😊，I'm going to translate it to， for example， arm。Which may be simple。

 it's actually relatively simple or MIps， pick mips。

 I picked arm for a good reason because I'm going to show you had a real system that does it。😡。

Wwhichch is this basically so there is a software hardware aided software translator that takes a program written in a much more complicated IA and translates it to another ISa that's actually public you can write programs in this also but if you have a program that's written in this complicated IA you translate it very efficiently with some hardware support and execute on the same hardware and that's what these systems do other systems also do I'm going to show you more they basically take X36 programs and they can execute them on arm with additional hardware support so the translation is not just in software it's also hardware support does that make sense this way。

Your system can execute programs not written in one。😡。

Language language is the language of the computer ISA。

 but another ISA also so there's a benefit now you actually cover much much bigger software base and if you actually design this software or hardware translator to be extremely efficient which I believe people try to do then you can actually get pretty good performance I don't know how many people have used X86 on this Apple Silon for example。

 yes and you get good performance。😊，Not bad， right？

Another way of thinking of this is this is really a virtual machine。😡。

Meaning have if you have heard of virtual machine， you may not have put something concrete to it。

 but this machine over here that has a software and hardware translator that's executing on an arm processor is really virtually executing the X6 instructions。

 you're basically you're doing translation from one ISA to anotherIS okay so that's one reason and these systems do it。

😊，But now going back to your question， I'm going to answer your question now could all of the other systems also do it。

 meaning Intel and AMD processors， they are stuck with this complicated ISA and the hardware designer says it's very difficult to support everything。

😡，And these keep coming every generation you get new extensions， advanced matrix extensions。

 for example， and there are some things like binary coded decimal very few people potentially use right some different type of data types。

 they become obsolete， but you still need to support them because out of millions and millions of software program is written。

 maybe one person uses them and if you don't support it and this may be very important person meaning they could be actually running this program in a bank。

 they wrote their software in 1980s， the person who wrote the software is not around anymore。

 they cannot change the software because they're afraid that when they change the software。

 something will break。😡，And you need to execute that code， right？

But if you still want to get performance out of it and port it to a new machine。

 you can actually translate this program that's written in X664 complex ISA2 an internal I say that's not visible to anyone in the world except for people who design it。

 These are called secret micro operations。😡，Which is very similar to MIPS， for example。

 let's say there's give a give or take simpler I say this way， the hardware designer's job is easier。

😡，And you can still support all kinds of software， and internally。

 you can have a hardware translator。😡，And people actually have this hardware translator today。

 they write it over time， so once you design this hardware translator。

 you don't need to necessarily change it much。😡，So if you're Intel， AMD。

 you design a hardware translator that translates X6 operations to your internal secret micro operations that are much simpler so that your hardware can become simpler。

😡，You design it over time， you over time incrementally change your hardware translator。

 so you actually amortize the cost of designing this。😡，Ex sense。Okay， so this is beautiful。

 as you can see， and all of these processor do that in their general purpose course。😊。

And that's not only them。There's also NviDdia who they've been designing SOCs system on chipPS essentially。

 and they have arm processors in some of their SOCs， and even with arm。

 they decide to do software translation so that they can actually simplify the hardware even more and also optimize things so NviDdia Demer is one of the at least publicly disclosed versions of arm processors that they have。

 they have a beautiful paper that I'm going to reference。

 they basically take the armISSA use a software translator， very heavily optimized。😊。

And translate that to their own secrets， micro operationss at even lower level than arm。

 So you can see that the IA is actually even simpler。

 so they can make the hardware simple and also they can do a lot of optimizations in the software translate。

 So whenever you add injection。You add capabilities。

 but you also enable opportunities for optimization at that level。

 but of course there's a downside also because this takes time this translation takes time right so people have developed a lot of techniques to optimize that translation。

😡，Okay， this is NVDdia Denvermer， if you're interested， you can read about it。

 but they do a lot of dynamic code optimization over here。😊，Okay。

 these guys are not the first ones to think about this actually they are even earlier works like from IBM in 1970s。

 but I will mention one thing here， this was in late 1990s there was a company called Transmeta which doesn't exist anymore。

 they wanted to compete with Intel at the time which was a very difficult time at the time。

 which was a very difficult task at the time so what they did was they wanted to have XD6 software and they wanted to translate it to internal instructions at architecture that again secret so that they can design the hardware much cheaply and much more efficiently。

😊，And hopefully compete with the performance that you would get with the processor that are designed by Intel。

😡，So what they did is essentially what I just described instead of having so they have X86 as their higher level ISA and then they have a VLIW ISA which we will talk about in lecture 18 or so。

 so patients over there also VLIW is actually a way of thinking of a principled way of designing hardware that's extremely simple。

😊，And they actually designed a lot of things over here so the hardware was very simple。

 they had this chd morphing software which is a virtual machine as we have discussed and everything else was X86 so they tried to compete they have a beautiful white paper unfortunately it was very difficult to compete with Intel at the time so these guys disappeared。

But they tried something new， so the good news is they tried。Okay。

 yeah maybe you can still buy their processors， but it's very old right now， you know 20 years。

 25 years okay so another reason why I'm telling you all of this is there' is a principle behind this and the principle is a very high level principle in and this is the attribution over here we're going to talk about Butler Leson's principles for computer system design later but David Wheeler said any problem in computer science can be sold with another level of indirect。

And this is an example because as you add another level of in you change the trade offs if you have one level you're stuck with the tradeoffs dictated by that level。

 but if you have another level of in now you can actually have more degrees of freedom to optimize we're going to see that when we talk about multicycle micro picturess as well unfortunately injection comes with extra complexity and latency。

😡，It enables you new opportunities， it enables you new trade offs or change of trade offs。

 but it always comes with extra complexity and lantence， so keep this in mind。😡。

So it's very difficult to design a processor with this translation levels that's going to obtain a much better performance than a natively designed processor。

But you cannot design all kinds of processors and put them together right if you want to execute multiple different ISAs。

 for example， as Apple wanted to do， you need to do something like this use injection。😊。

We will see this principle again in virtual memory， again， lecture 2526。

 this is also very commonly used in existing systems。

 we're going to see that memory is not addressed physically actually when as a programmer。

 what you see is virtual addresses and internally the processor translates those addresses to some other address space。

😡，So if this is not clear， don't worry about it， but you'll probably see these in systems programming when you talk about operating systems。

 so we're going to prepare you for those operating systems coming later on。😡，不。

Any more questions on this， so hopefully you guys questions are answered。Okay。

 let me give you one more tradeoff that we actually already covered there are many。

 many tradeoffs over here， but let me pick one number of registers。

 so this is actually a decision that an ISA designer makes how many registers am I going to support general purpose。

😡，This affects the number of bits used for encoding Reg address and we've seen this in LCC3。

 you have eight registers， so you need three bits to encode a Reg address in MIPS you have 32 registers and you need five bits to encode Reg address。

😊，So your instructions become bigger clearly if you have more registers。

 but if you have more registers， you can exploit more locality。

 meaning number of values kept them fast storage， the register file increases。

 so your register allocation becomes simpler。😡，But unfortunately， in the architecture level。

 the size， access time and power consumption of the register file increases because you have more registers。

 your fast memory is bigger essentially。😊，So this is a tradeoff。

 large number of registers enables better register allocation optimizations by the compiler or assembler。

 leading you to fewer saves and restore， meaning you get better performance， hopefully。

 unfortunately you get larger instruction size which affects your performance also。

 that may not necessarily be good because if you're fetching larger and larger instruction sizes。

 code essentially that could affect your memory bandwidth for example。

 and caching efficiency as we will see later， and you get larger register file size which affects your latency to access it and the energy to access etc。

😡，And we already saw the tradeoff in LCC3 and MIPS and this is a very fundamental tradeoffs in ISA design and this is one of the reasons why registers are not made general purpose registers are not that many in many ISAs。

 3264 maybe 128 which was the case in Intel IA 64 itenium which another family of debt processors let's say so you don't get more than that。

 but again we will see when we talk about auto order execution and remember that with a level of indirect。

😊，You can change this trade off。At the architectural level at the ISA level。

 you can have few registers and at the microarchitecture level at the lower level。

 you can have many registers and you do a mapping between the few registers at the high level to many registered at the low level。

So we're going to use interaction again， when we talk about auto word execution process。😡，But again。

 patients we're not there yet， there's a lot more to cover on ISAs I'll refer you to some of the lectures if you're really interested。

 but we don't have time to cover more of these trade offs。😊。



![](img/4c2de24a448f22f60a4668242a2bce1b_13.png)

![](img/4c2de24a448f22f60a4668242a2bce1b_14.png)

But I will to cover one thing。Wwhich is a really fundamental tradeoff and it's always good to question things so remember we said we want the one Neman model and architecture and the two major properties of the one Neman model stored program computer and sequential instruction processing we covered this so I'm not going to talk about this in detail again we're going to see this again actually later on stored program program is in memory and there is no distinction between the data bits belonging to the program and the other data you interpret these things based on the control signals。

 which stage of the instruction processing cycle you are in I'm going to pick on the sequential instruction processing so we said sequential instruction processing is a hallmark of one Neyman model you basically process each instruction sequentially and this is enabled well yeah this is enabled essentially a lot of things you finish you fetch execute and complete one instruction at a time and then you go to the next instruction。

😊，This leads to the notion of program counter or instruction pointer。

 which identifies the current instruction and its advanced sequential。😡。

This has enabled a lot of things like it's easy to think about things。

 right you you do only one thing at a time and then you move to the next instruction and the next instruction and the next instruction soundss good。

 right？😡，And I said that this is actually the way most computers are built today。

And there's a recommended reading over here。And this is a picture of one name model。

 Now we're going to question this。 We let's deconstruct this。

 Is this the only way that a computer can process computer programs， And the answer is no。

But qualified answer is it's been the dominant way for general purpose processinging for special purpose processinging。

 we can do other stuff， as we will see later on。So it's been the dominant paradigm of computing for many decades。

😡，But let's now examine a completely different model for processing computing programs。

 and I like this because many books don't cover it， but this is actually a very。

 very important way of thinking about computing and it's the dataflow execution model。

 how many people have talked in dataflow before。😡，Okay， maybe。You're not sure what I'm talking about。

 maybe， okay， that's good。So what is the key idea， one Ne model an instructions is fetched and executed in control flow order sequential unless you have a branch control flow instruction that's why it's called control flow。

 you have a flow of control that's predominantly sequential unless you have a control flow instruction that's changing the program counter。

 right？😡，And you're basically the control flow is specified by how you change the program count。Okay。

 I already said this so in data flow model。😡，And instructions fetch and execute in data flow work。

What does this mean， this means that when all plans are ready。

 think about a similar instruction that we've seen in a， you have two all plans are one and R2。😡。

You don't fetch this instruction when the program counter comes to it。

 you fetch this instruction when you know that R1 and R2 are ready。

 meaning someone has produced R1 and R2。😡，That's the nature of data flow。

 you have some input data to the instruction and when those input data are produced。

 you fetch the instruction and execute it， you produce another input data and that input data is the availability that that input data is signaled to other instructions that are waiting for that input data。

😡，Now， this may be not easy to grasp at first， but it's a very natural way of thinking about how data flows in a system。

 right？😡，Okay。😊，嗯。So basically there's no program counter and I'm going to show you an example of this soon。

 there is no instruction pointer we've deconstructed basically the whole mark of one normalman model at this point。

😡，So what is instruction ordering specified by， well。

 it's not specified by anything that's centralized。

 it's specified by when the data value of of an instruction becomes available。😡。

So there is really no ordering other than the state of low order。😡，Which could be dependent on many。

 many conditions clearly？😡，So each instruction specifies who meaning which other instruction should receive the result。

 and an instruction can fire， meaning gets fetched and executed whenever all of its opera are received。

😡，Meaning that potentially many instructions can fire at the same time。

 so imagine a case where you have you're producing a value。

 you're adding two numbers and those two numbers produce a result and that result is needed by 10 different instructions which could be possible right and those 10 different instructions are already at the same time right it's very fundamentally parallel if you think about it right so that's the distinction over here yes we're going to talk about that more patients because we're going to talk about systolic arrays in later lectures 18 or so。

It's similar to dataflow， yes。Just to but many people don't know sytolic array right now problem so okay consider it one Neman program let's take a look at it this is a one Neman program written in some level of abstraction very low level we add two numbers and then we multiply one number and then x equals v minus w and then y equals v plus w and then z is x times y so A and B are the only inputs to this program。

😊，Z is the only output， right？😡，Really all of the other things it's good to think about。

 and this is sequential clearly， most importantly， what is the significance of the program order here if my goal is to get from inputs to the output。

😡，Maybe I don't really care about the order， right？

I just want to execute this thinging that gives me the output given the inputs right but I've broken it down into instructions because instructions are what I can execute on a computer。

😡，So in a sense， I don't really care about the order。

 except when I'm programming this thing and I'm debugging the program。

 maybe if I did something on or if the software is wrong for some reason， et cetera。😡。

What is the significance of the storage locations， so for example， I created W over here。

 do I really care about W？😡，As a result of the program not really it it's really what this is doing is W is a register imagine this a register this register is getting communicated to the next instruction and this instruction to instructions and those instructions are producing other registers that are getting communicated to this latest instruction and eventually that latest instruction produces a result so the purpose of W X and y over here and also V actually Vw X and y are to communicate。

😡，Data values between one instruction to another instruction， we're using that variable。😡。

Which is expressed as a register in the instructionss at architecture to communicate values between instructions。

😡，Does that make sense？Hopefully， okay。Good， given this。

 this is another way of thinking about this program and this is data flow way。😡。

I don't have registers at this point， at least explicitly， I have input where A B and an output Z。😊。

And this program graphically does exactly the same same thing this program does。

 you can convince yourself and instructions nodes are connected to each other with arcs as you can see。

 so dataflow is inherently a graphical model also were you can express it of course in terms of instructions too which I will show you very briefly。

 but we're going to think about it graphically， so if you think about it。😊，This instruction。

 if A and， A are available when A and B are available， let's assume that somebody inputs AMB。😡。

This instruction can fire。Meaning it can actually execute at that point。

 This instruction can also execute only one B is available。 It's a it's easy multiplying B by2 it。

 it needs only one out print。😡，So this instruction fire when B is available。

 this instruction fire is when A A and B are available， and they produce a result。😡。

And this result becomes available over here， this result and it goes over here to the next instruction and these instructions can fire when both of the their inputs are available。

 so the result of this one and the result of this one， when both of those are available。

 these two instructions can fire and they can do it concurrently。😡。

And this last instruction can fire when its inputs are available， meaning after these instructions。

 finish execution and send their values to that instruction。😊，Okay。

 so this is a way of thinking about， I'm going to get into a little bit more detail。

 which one is more natural to as a programmer。😡，Who says sequential？Okay， who says data flow？Okay。

 that's what I expected。 I always asked this question before I don't know， 20 years or so。

 and I always get the same answer。The question is， is it because of nature versus nurture。

 right it's always good to ask this question also。We always learn this， right？

This is probably the first time you're seeing this in your life。

 so it's natural that this is not natural to you。Okay， okay。

 basically let's go into this a little bit more in a data flow machine。

 a program consists of data flow node。😊，A data flow node fires。

 gets fetched and executed when all of its inputs are ready。😡，In other terminology。

 when all inputs have tokens。😡，So let's take a look at a data flow node ISA representation so this is the graphical representation of a multiply instruction it has two input one output this is the ISA representation theres some output code there is some input argument and theres whether it's ready and there's one other input argument。

 the right one left one and right one and whether it's ready and there's an argument saying that this is the destination of the result this is where the result should go。

😊，Not a register。An instruction an arc basically arcs are encoded this way is this is an arc that's encoding a connection between one node and another node so it's a graphical representation as I said so let's take a look at some more node and we're going to have some fun so you can build a full graphical programming model using this so that's a conditional node in other words branching right what does this do you have an X input。

 a data input and an f input， a control input。😊，呃。And what this does is， and then there's a one arc。

 two arc， and then full arc。When， when the control input is false。So this node fires。

 meaning it gets fetch and executed when both of its inputs are ready X and F in this case。

 what happens is when it fires it checks the control input if this is false。

 then x is communicated from the input to this false arc over here okay if this was true。

 then x would be communicated to the true arc over here。😡，Makes sense。

 so basically your flowing data data input comes based on the control input。

 whether or that it's true or false， the data input goes one direction or the other direction。😡。

Which means that it hopefully enables the firing of some other node。😡。

Right depending on the situation okay so let's take a look at how you can generate the false and true。

 So this is a relational node。 you basically have two inputs and in this case it checks greater than you could actually have many different relational node。

 If left input so this node fires when left and right inputs are both ready。

 meaning they have tokens somebody has produced those data inputs。😊。

And if left input is greater than the right input， you get a true token at the output。

 Otherwise you get a false token at the output， and now you can connect this thing to the input of this conditional if you wish to now there is a more complicated note。

 how many of you have seen barrier synchronization。In parallel programming， Yeah。

 maybe how many of you have not seen it。 Okay， that's what I expected also。 Okay。

 you're so far following the expectations。 so basically this' is a way of doing synchronization。

 I will not delve into it because we're not going to use it also。

 but you will see it in your life at some point。 The idea is。😊。

You want to basically ensure that all fs produce their results before proceeding to the next part of the program。

 so your program consists on many tasks and then you go into another tasks when the previous task has finished。

 when do you know the previous task has finished， you have the data outputs of all previous parts of the data flow graph。

😡，And that's what this says， this barrier synchronization。

 meaning in this case you have three inputs， three outputs。

 when you basically send the inputs to the respective outputs only when all of these inputs have data available to them。

 so if only two of them were available， you wait you don't send the outputs to the next part。😡。

If only zero， again， you wait。Only when all three of them have the data inputs。

 you actually send the data to the next test so that next to the outputs， you fire this instruction。

 send the data to the output so that you can process with the next part of the data flow graph。Okay。

 if you didn't understand it， don't worry， but you'll see it later on。Okay。

 let me ask you this question。This may be again overwhelming to begin with if you have not in dataflowlow before。

 but this is a very simple data flow program， it's not the best way of implementing the function that you're going to discover in dataflow。

 let me walk you over tell but basically we have two inputs。😡，One is n over here。

When is one hardwired to one initially n is a non-neg integer and we have one output over here out and the question is what is the value of out I need to give you a little bit more information actually we can walk through things a little bit this is a note that basically tests as you can see thiss a branch node we have C there's a boolean value produced over here but n gets copied over here as you can see so there is something coming up from the previous part。

 this basically says in the kind of the next iteration select the next n it could be done in other ways。

 but this is how it's done in this particular case so n gets copied and when n is available it gets copied to here and then here and you check whether n is greater than zero with this node and it becomes true or false clearly and you copy that boolean value to here and here so you can see that there are copy notes or instructions。

😊，And this bulloleing also controls here， as you can see， and N was here， So you check whether。

So this was n is greater than 0 right so n gets input to this branch node if and this boolean is true if n is greater than0。

😡，If n is greater than zero， basically you take and the input n goes out over here and then it gets copied again。

 as you can see over here， and then it gets decremented at some point。😊，And then it gets multiplied。

 this is still n， it gets multiplied by something coming out of here。😡，Remember。

 this was checking n is greater than0。 if that's true n gets multiplied by one， right。

 So I get n times one。AndW which is n again， and then n gets。Back cycled into this over here。

So in the next iteration， you get n over here and there's a decremented n over here in the next iteration。

😊，So you keep repeating what I just said， so I didn't explain what this is。

 this is really destroying the token， meaning if this boolean is false。

 the data input coming here over here， so this node fires when the data is available here and this input is also available there are two data tokens that need to be available when both are available this node fires and if this boolean is false。

 then that data input gets killed， meaning it doesn't go anywhere meaning you'd kind of terminate this thing over here and the output is specified by here。

😡，Okay， I kind of gave you an overview of what this is has anybody figured out what it does yet？😡。

Yes。😊，Quick question。 Yes， the difference between our VR now and the， the other one。

pThere tracks a condition that is quiteceivable。 You mean this one and this one。

The other oneGreat than zero it just one result and the other one does nothing。

The meaning this one you mean no， this is actually a comparator note。 So if you go back here。

 this is a relational note， it basically decides whether you get a true or false。Output。

So so you can see， yeah， yeah， it's basically， it's greater than zero， right talking mark to zero。

 basically， it's a yeah， okay， yes。😊，Okay， we have a taker。You say un factorial， anybody else？

Have you figured out yet or？Yes。Okay， another amctorial。People are processinging。

 you're as simulating the data flow machine， anybody else？😊，Who says M factorial。

 This computes M factorial。 Okay， that's good， so。Who says something else。Don't be shy。Okay。

 basically this computes n factorial so you guys are right that's good。

 so I'll go through this but essentially what happens let's take a look at it quickly initially one and n are ready。

😊，One is ready over here， but this thing is not ready so this node cannot fire I'm going to execute like a data flow machine right and is' ready that's the only input to the coppy node so this this node can fire so basically copy n over here and then over here。

😡，Let's take a look at what happens here n is ready over here， meaning you have a token over here。

 but this is not ready yet， so this cannot fire you're waiting。😡，So n is over here。😡。

And this node can fire because it has only one input and it's going to evaluate n greater than 0。

 So if n is greater than 0， you get。呃。A true over here， right， Let's assume n is greater than zero。

 Okay， you get true over here。😡，So now that true gets copied over here， this is true。😡，This is true。

Now this node can fire and this node can fire because one input over here is one and true。😡。

If this is true， that means this one gets propagated over here， right。

 it doesn't go out to the output。😡，And because this is true n gets propagated to the true part so itt get it doesn't die。

 let's say it doesn't get killed so now you have n over here and you have one over here and that n gets copied over here。

 you multiply 1 and n and that multiplication gives you n clearly n times one is n and at the same time you decrement n you can see that a lot of things are happening in parallel right but I'm sequential when I'm describing it I cannot describe in parallel I have not figured out how to do that yet but essentially this is n minus1 so now we're kind of going to the next iteration。

😡，This is M minus1 over here， M minus1 gets copied again in the next duration。

 and I have n over here。😡，So I do the same thing basically。

Which means that I copy n minus1 and this is n -1， assume that it's greater than0 again。

 I copy it again， so this is true， this is true， so I get n over here。😡。

I get n minus1 over here because these are all true。🎼Now I multiply n times n -1。

 which goes over here， and I decrement n -1， which is n -2。 Okay， in the next iteration。

 I do the same thing with n -2 over here。 And here I I have n times n -1， okay。

So the next iteration will produce assuming n is greater than assuming n minus2 is greater than0。

 again， you get n times n minus1 times n minus2 over here。😊，Until。

The value that's over here is not greater than zero in which case you'll get false in these boolean paths and once you get false in the boolean path。

 the value over here gets killed， none of these execute because there's nothing that's coming out and the value over here gets passed to the false path and that is M factorial n times n minus1 and n times to et cetera right if n was actually。

Not greater than zero to begin with。You would get one in the output right that's the easy case and that's actually the definition of factoria。

😡，Does that sound good？Okay so you first you now have seen your first data flow program this is actually how a lot of FPGs and accelerators can be programmed today。

 they have data flow interfaces， graphical interfaces which we're not going to talk about a lot in this course you're going to use FPGs for a different purpose。

 but you could actually instantiate this in an FPGA so this has been very successful there's another reason there's another place where we will see data flow graphs when we talk about auto over execution。

😡，Actually， all existing processes execute like this。😡，Except they don't do it。

 they don't expose those instructions to the hardware， to the programmer。😡。

They actually convert your sequential instructions to something like this internally。😡。

whichch is fascinating so they use a level of injection with a concept that we've seen。

 they take your sequential program code and they convert it to this。

 you write am factorial and you write， of course， assembly code and they get converted to something like this。

And they get executed whenever the instructions are available whenever the data for instructions are available at a given time。

 so we're going to see that concept out of word execution theyre on lecture 15 16 or so。

 and this is the principle with which essentially all general purpose high performance microprocesors operate。

😊，And that's why it's really important to know this model。Do you have a question？No。还不方。Okay。

 we can talk in the break， so let's take a break right now。

 let's be back when the bell rings and then we're going to continue a little bit more trade offs and then start micro architecture。

😊，So that's basically real for normal machines。We didn't still exist basically。没。Okay。Let's continue。

Okay。So now you have a data flow program， if I ask you something similar in the exam。

 you should be able to do that also right， hopefully。😊。

And we've had interesting exam questions in the past where we give you a data flow graph and ask you。

What does this program do？I guess you guys should not be worried about exams right now。

 but you will see similar things in your homework， this is fun。😊，For multiple reasons。

 one is this is a very interesting way of thinking about execution of a program and execution model。

😊，And the other thing is， this is actually real。 As I said， you could actually take this。😊。

Design circuits directly into hardware with this， or you could actually convert a control flow program to a data flow program internally without exposing what you do to the programmer and that's the dominant way as I said so okay let's talk about the ISA level trade off quickly basically program counter do you want a program counter in the ISA if you say yes you are probably doing control driven sequential execution and you've already seen this。

And we're going to assume this for the rest of these lectures， if you say no。

 you're probably doing data driven parallel execution and instructions is executed when all its opera and values are available。

 and that's data flow。😊，And this leads to a huge slew of trade offs。

Many high levelvel ones which one is easier to program for average programmers but you need to educate the programmers so that they can program in this data flow manner in fact people try to do that initially like one Neumman proposed his model or their model in 1940s and then in 1960s these smart people came up with the data flow model and they said this is a better way of designing processor because you actually get much higher performance you can unleash a lot of parallelism and they tried extremely hard to get this model unfortunately it was very difficult to move the software programmers to program this way because it was very difficult everybody was very used to the sequential model whereas data flow was very hard。

😡，How do you compile into it after someone programs it can you actually convert a control flow program to a dataflow program purely with a compiler possible but not easy which one has better performance where can you extract parallelism better right and we will see that actually later on what is the hardware complexity of each of these again these questions are not necessarily easily answerable because we can use interaction as we will see later on so this was the ISA level tradeoff in the ISA level you can say I'm dataflow and everybody needs to deal with it not an easy thing you can make a similar tradeoff at the My architecture level。

😡，We're going to talk about ISA versus micro architecture very soon。

 but micro architecture is an implementation of an ISA IA specifies how the programmer sees the instructions to be executed。

 I said this many times micro architecture。😊，Is how the underlying implementation actually executes the instructions。

😡，And micro architectureiture doesn't have to do exactly what the ISA says internally until it reports the results to the software。

 meaning it changes the architectural state internally， you can do something completely different。😡。

IA for example can say programmer is a sequential control flow execution order or programmer see a data flow execution order let's assume the second one is tough ISA says programmer is a sequential order micro architectureure can execute instructions in any order as long as it obeys the semantic specified by the ISA when making the instruction results visible to the software so in the end programmers should see the order specified by the ISA whenever they stop the program for example or whenever something let's say bad happens。

😊，But。Micro architectureure can be executing in data flow order right and that's what essentially all micro architectureures today do all high performance micro architectureures do。

😡，They obey the One Neyman model， they guarantee the One Neyman model to the software programmer。

 but underneath they play a lot of tricks to execute instructions in parallel like a data flow graph in fact we're going to see how an out of order machine operates。

 we're going to look at the registers inside the machine， internal registers。

 not the architectural registers， internal registers and by looking at those registers you will be able to construct the data flow graph like we have seen earlier。

 just by looking at the registers you will reverse engineer them and you will say okay。

 this is the data flow graph that's that's in the machine。😡，And in some cases。

 you can also map that back to a control flow sequence， but not always， as we will see again。😊。

Does that sound like fun？Okay。So we're going to get back to one Neman Ma。

 if you' want to learn more about dataflow， these are some interesting papers。

 there are many other papers and I have some old lecture videos that talk about this。😡。



![](img/4c2de24a448f22f60a4668242a2bce1b_16.png)

![](img/4c2de24a448f22f60a4668242a2bce1b_17.png)

Okay， so let's get back to oneno model， so all major instructor that architectures today use this model for general purpose computing。

 but underneath the execution model of all implantations。

 meaning micro architectures is very different。😡，So we're going to see pipeline and instruction execution。

 even this breaks the one Neman model， One Neman model says you cannot start。

Another instruction before you finish the previous instruction。Before going into data flow。

 forget about data flow， just pipeing instructions。

 starting the next instruction before the previous one finish finishes。

 this a very old concept developed in 19 late 1950s actually。

 we're going to break that even before we get out of work execution。😡。

Multiple instructors at a time one Norman Wal says you cannot execute multiple instructors at a time。

 underlying micro architecture executes multiple instructions at a time， okay。

 we're going to see that Auto order execution I mentioned。😊。

Well Nooma model says instruction and data caches， there's no caches but instruction and data memory are unified internally we're going to break down into separate places so that we can actually design a much better。

 much faster processor so we're going to violate this Wal No model internally a lot。😊。

But we're not going to expose it to software basically what happens underneath that is not consistent with the One Neman model is not going to be exposed to the software otherwise you you're violating the contract right the contract is this is what the software programmer assumes it's one Neman model underneath I can do anything I want to optimize for performance。

 efficiency， reliability， whatever you want to optimize for cost。😡。

As long as you don't break the contract， and that's the key difference between ISA and my architecture。

😡，So let me go back to this definition of computer action ISA。😊。

So this is actually a definition that we had used in the past。

 this is an ISA plus implementation definition。When people talk about computer architecture。

 they may mean many things。This is one of the many things this's actually a very broad definition it's really the science and art of designing。

 selecting and interconnecting hardware components and designing the hardware software interface to create a computing system that meets some goals。

 functional performance， energy consumption costs and other specific goals we've seen this before。😊。

A traditional， I say only definition is like this， it was provided by Jean Amdal。

 who actually designed a lot of high performance processes at IBM。

He basically says the term architecture is used to describe the attributes of a system as seen by the programmer。

😡，That's basically the hard interface between the hardware and software I。

e the conceptual structure and functional behavior as distinct from。😡，Micro architecture。

 which is the organization of the data flow and controls。

 the logic design and the physical implementation。😊，Okay， so basically， let's take a look at this。

 I'm going to repeat some things and then we're going to have some more fun。😊。

So I say they agreed upon interface between the software and the hardware。

 this is what the software the compiler assumes and the hardware promises again， that book4000。

5000 page book that describes what the software should assume In other words。

 what the software writer needs to know to write and debug system or user programs and there are many software writers in the world。

 some of them write operating systems， some of them write user level software I say cater to all of them。

😡，Meaning it specifies what the hardware looks like and should obey how it should behave to different users。

 different programmers myure is really a specific implementation of an ISA。😡。

This is not visible to the software。😡，Microprocessor is usually ISA micro architecture circuits together。

😡，And when people say architecture today， it's usually ISA plus micro architecture。

 so they don't have a distinction， like what I said in the previous slide。😡，Okay。

 now let's talk about micro architectureure， as I said， this is a specific implementation of the ISA。

😡，And the question is， how do we implement the ISA。

 this is what we're going to be concerned with for N lectures。😊。

Until we talk about some different models of execution。

There can be many implementation of the same ISA， for example， MIPS， your favorite ISA。

 because you're going to use this in your labs， had many。

 many implementations and they decided they have a lot of zeros in their implementations。

 micro architectures， not everybody does that。😡，Our 10，000 was one of the heavy machines。

 as I may discussed later， x86， which is a very successful ISA。😊，Clearly。

 it's had many implementations and I haven't updated it in a while。😊，Power， which is an IBM ISA。

 had a lot of implementations also。Arm has a lot of implementations。Alpha， which is the dead IA。

 unfortunately， has a lot of implementations。 There's risk five right now。

 It has a lot of implementations。 It's open source。

 So it enables actually a lot more implementations。 It's open source in many levels。

And then there's the Z architecture from IBM which is actually a very interesting architecture。

 it has a lot of implementations， this is one of the most complicated architectures that we have today also。

 and then who knows what else。😊，So clearly， we can have many implementations without changing the ISA much。

 you can actually execute the same program。😡，On MIPS R 2000。

 which is going to be very slow because it has one implementation that's relatively slow。

 let's say it doesn't employ the concepts that we're going to talk about our 10000。

The same program can execute on our 10，000， except it's going to be much faster because the smart designers at the low level at the micro architectural level。

😡，Did what we're going to discuss in the like and lectures， they've optimized hardware。😡，Okay。

 with principles， as we will see。Okay， let's play this game。

 what is part of IA versus micro architectureiture？Well， we're going to play the game before。

 but I think I like later， but I like using this analogy。So how many of you drive cars？Okay。

 I think I asked this question before because we had the Swiss traffic light， right？

This is a different reason though I asked the question。

 probably you're familiar with something like this unless you're driving a self driving car。

 how many of you drive self driving cars？Okay。Good， don't trust them yet。

Yeah there are a lot of robustness issues probably okay but basically when you drive a car what you care about is what pedal I press to accelerate accelerate and what pedal I press to break and how do I move the steering wheel right there's an interface over there that's the architecture instructions that architecture of the car you press the gas pedal it accelerate。

 you press the brake it accelerates I hope and there's sometimes unless it's automatic there's a clutch also which you use to change the gear right so these are actually very common。

😊，A very common interface。And these stayed the same。But cars have evolved over the years， right？😡。

Internals of the engine implement the acceleration， for example， over the gas pedal。😡，As a user。

 meaning the programmer or the fear of the car。You don't think about how the engine actually does the acceleration。

 right？You write the program meaning push your foot on the gas pedal and the thing accelerates and you expect some acceleration based on that right so there's low battery over here so we have another issue。

😊，嗯。I hope you guys have it because I don't have it。Okay。

So implementation can be various as long as it satisfies the specification， right？😊。

Meaning you can have many different cars， but the user doesn't need to change。😡，Makes sense。Now。

 if the user needed to change， then there's a problem。😡，You introduce a new car。

 you change the interface， then you may have a lot of crashes on the road， right？So you see。

 it's difficult to change the interface。Meaning ISA is much more difficult to change。😡。

Does that make sense， we have the same problem in software as we will see。😡。

But let's before going into that let's talk about the a instruction adder implementation and software again in ISA In at architecture。

 we have an ad instruction， that's an instruction and we've seen that in the In at architecture。

 but you can implement in many different ways you have actually seen some implementation of the adders when we talk about combinational logic。

😡，You can have a ripple carry adder right You can have a carry look ahead ater and I've shown you pictures of that。

 you can have many， many different types of adders， carry select adder， et cetera， et cetera。

 Actually your book chapter 5。2。1 covers essentially a lot of adders。

Is there something that we need to do？Otherwise， this is going to probably die at some point and that's not going to be good。

So X86 similarly has many implementations， right， you have IA。

 you have lots of instructions over here。😡，And。😊，People do different things。

 They may actually have different add in all of these different implementations。

So essentially because theres a lot of software that gets written that assumes these instructions micro architectureure is easier to change。

 you just change the hardware， the software doesn't need to change and performance improves so as a result we have very few ISAs but many micro architectureectures。

😡，Hopefully this makes sense， right？We have very few ways of doing acceleration that's exposed to the user。

 but internally， we have many different types of engines。😡。

Right some of them are controlled by electric some of them are controlled by mechanical components。

 et ceter， it's usually a combination of both。😊，Okay， yeah go ahead。那必须去。啊。Okay， any questions？

I already answered the why over here。So these are some of the documents that you can look at。

 as you can see the number of pages over here， that's actually old。😊，4800。Actually。

 this is not the full thing an arm is actually， even though it's a simpler ISA。

 arm is still 4000 or so。So why are these ISA so complex because they need to specify a lot of things right it's not just the instructions we've seen just the instructions and memory so far we haven't seen a lot about memory we haven't seen a lot about instructions but instructions we've covered more or less。

 let's say。😡。

![](img/4c2de24a448f22f60a4668242a2bce1b_19.png)

O codes addressing mode data types， instruction types， formats， registers， condition code。

 we covered that right you cannot see it but I see it right now so you will figure it out。

 I don't know maybe Zoom people see it， let's see if the zoom people see it。😊。



![](img/4c2de24a448f22f60a4668242a2bce1b_21.png)

![](img/4c2de24a448f22f60a4668242a2bce1b_22.png)

I'm very curious。NoZoom people are not seeing anything right now。Or maybe my computer， okay。

 Zoom people are seeing something。 that's good。Okay， it's all good， okay。Okay。

 so okay now you see it basically in memory there's a lot more we've seen some things we haven't seen everything there's virtual memory management actually at least hundreds of pages are dedicated to virtual memory management and the ISA and we're going to talk about that in lecture 2526。

😊，We're going to talk about interrupt exception handling a little bit。

 but there is a lot of detail over here that need to be exposed to the programmers。😡，Access control。

 priority privilege， these things we have not talked about that yet。

 we're going to talk about that in virtual memory briefly。

 how do you do input output to the computer？😊，How do you do threat management if you have multiple threads。

 how do you actually take care of them How do you do power management， thermal management。

 how do you do error correction when an error happens in a computer， how do you handle it。

 who does it get exposed to How should the user handle it So all of these issues need to be specified in the IA right otherwise user expect something if it's not specified then。

😡，They will get something that's not working potentially， right。 So there's a lot in the Is。

 and that's one of the reasons why these are 5000 pages and probably it's not 4，800 anymore， right。

Actually， these are combined volumes of only one through four， so there's actually multiple。Okay。

 there's a longer version， 5000， and I didn't update it because I cannot keep updating these things。

 There's the arm。 it's also almost as big， even though x86 is a much more complicated ISA。😊，Then arm。

 you can see that the number of phases are very similar。

And you can find more risk five is actually a young ISA。

But I recently checked that they're already at 700 pages。

Even though they start developing so they're going to get there don't worry it's a young guySA right now but over time as more baggage gets added to the ISAs as more things right now risk five is easy because they don't specify a lot of things right and over time they figure out oh we need to specify this we need to specify that oh error correction how do we specify that or we should add these instructions because this is too slow right this is what has happened since 1970s to X 86 for example？

😡，So this is a good bedtime reading for those of you who may be interested in this sort of bedtime reading okay now let's play the game that I wanted to play a bit actually in the next slide I've already said this my characters is an implementation of the IA on specific design const and goals in other words anything than hardware without exposure to software and we're going to see a lot of these。

😊，We're going to do pipelining， different kinds of instruction execution， memory access。

You may not know all of these and you don't need to know。

 but we're going to see a lot of these actually in this course。😡，Let me pick one thing over here。

 for example， voltage and frequency scaling that's interesting modern processors run at some sort of voltage。

 as we have seen in lecture one。😊，And you can actually determine the clock frequency there's a maximum clock frequency you can run at based on the design that you have based on the critical path analysis。

 timing analysis that we have done， right？😊，So all of those are there。But to save energy。

 you can reduce the clock frequency and you can reduce the voltage。😡，Who does that。

What's the questionite？You can see the programmer can do that。

 I'll expose instructions to the programmer instructions。

 the programmer can use those instructions to reduce the voltage。😡。

Do you do that during your program？Not you， but an operating system designer can do it。😡。

Because there's a system designer that designs the operating system that sees all the programs that's running。

 that sees the battery level， maybe of this thing， for example， right， and that says。😡。

I don't want to waste more battery， the user said it's in battery saving mode。

 so I'm going to use this instruction and I'm going to communicate to the hardware that it should reduce the voltage level to I don't know whatever volts and reduce the frequency and the user told me that this is tolerable because I'm in low power mode right？

😡，Now that is exposed to the ISA right， as you can see。

 and that has to be specified in this document。😡，Okay。Of course。

 micro architecture can do it also internally， meaning micro architecture can say， oh。

 I don't need this fast execution at this point because of these things that I monitored。

 I'm going to reduce the frequency， reduce the voltage。😡。

Now the downside of this is micro architectureure may not know information about the program that's running back。

 so you could do things micro architecturally but you may not have enough information to do things。

 you could do things at the ISA now the programmer has some responsibility。

 some programmer has some responsibility， but they have a lot more information and this is also going to be another tradeoff at the software level。

 you have a lot of information about the program and the system especially if you're monitoring the system characteristics。

😡，And if you have actually instructions to control what the micro architecture is doing。

 you can optimize the system much better。😡，Whereas if you don't have that much control at the hardware level。

 as a micro architect， you're designing the hardware。

 if the software doesn't provide you some information about what is going on at this point。

 you may actually not be able to optimize that much。😡。

So systems companies that design both the software and the hardware and the ISA。

 they are at a very big advantage because they have the entire stack to optimize。

 they can actually figure out what's going on at the software level。

 they can design the interface and they can actually optimize what's going on in the hardware so you're at a very unique position if you can actually do all of those at the same time whereas if you're a company that's designing just the hardware for example。

😡，You're limited， you expose an interface and somebody else designed the software。

 and you may not be able to optimize in our stack， so this will become more and more clear as we discuss。

 yes。😡，What are secure software fishes also on low low temperature of frequency。Say it again Yes。

 essentially all CPU cores today can change the voltage and frequency。

They can do dynamic voltage and frequency scaling both at the my architecture as well as ISA levels。

Okay， so there's a lot as you can see over here， okay， let's play the game finally。

I'm going to give you a couple of things and ask you whether this' is a property of ISA and my Arch architecture。

 I appreciate quick answers。Up code of an ad instruction， who says ISA？Who is this Mike Clark'st？

Okay， I8 wins。Because clearly， there's an upco that has to be specified in the document。

 a way of thinking about it does it have to be specified in the document？😡。

Type of adder used in the ALU， whether you use a bit serial add， ripple carry adder。

 carry select adder， who says this ISA？Nobody， well one person who says it's my qua， Okay。

 my qua wins now caveat。You may be correct if someone puts that into that document。

But usually they don't put that into a document， this's an implementation choice。

 if you put that into the document， actually it's not very principled。😊。

We're going to see that later on when we talk about branch handling there' are some things that are clean if you actually put this implementation to the do you could there's no question right in the end the answer to this could be all yes or no。

 but the reasonable or dominant answer is for this this is part of themic architecture because you won't see it in any IA for good reason okay number of general purpose registers part of ISA。

😊，Okay， part of my qua picture。Okay， part of ISA wins because you have to have the general purpose registers and the instruction and coding as we have seen right and that has to be specified how many of these。

 how many bits you need to specify it etc ceter， you still need to implement in myQu architecture so it nice to be into momentum but it has to be in the ISA okay otherwise the programmer cannot program it。

😊，Unless you don't have general purpose registers in your ISA， which is also possible。

 but that's not the norm， let's say right， you could only operate on memory for example。😡。

You just do a memory， memory， memory memory always。

 but that doesn't exist in existing I says for the principles that we have discussed right memory is too slow。

Okay， number of cycles to execute a multiply instructions。

 how many cycles does it take to execute a multiply instructions？😡。

Or pick your favorite instructions， who says ISA？Okay， who says my architecture。

 okay my architecture wins again and again this is not always the case。

 this is actually in general purpose dominant ISAs， this is part of this is not specified。

 but we will see some execution models later on like very long instruction word architectures where they specified as part of the ISA。

😊，Okay， number of port of the register file。😡，How many ports do you have to access to basically concurrent the access multiple registers？

Two registers， four registers， five registers， one register。注册在IC。Okay， who says my architecture。

 Okay， that's a more trick question in the end， this is really part of the my architecture also the reason is。

😊，The number of registers and instruction accesses is part of ISA like an ad instruction needs two registers and a one output register。

 a destination register， but how you implement it at the lower level is up to you as a designer。

 you can have only one port to the ISA and serially read。😡，Different registers。

 right and serial write different registers as opposed， you could have 10 parts of the register file。

 you could only use two of them at a given time， right。Okay， this will become more clear。

Whether or not the machine employs pipeline instruction execution， you don't know this yet。

 but who says， who thinks this is ISA？😡，Who thinks this is micro architecture。 Okay。

 you got the hang of it。Program counter I say。Mike architecture， okay， that's good。

 I think you guys have got on the hang of it and this is usually a nice question in the exam easy bonus points maybe。

😊，Not exactly this， of course。 So okay， I already said all of this。 So essentially。

 I say micro architectureure is an implementation of the IA under specific design constraints and goals。

 Let's talk about design point。 And then what is the design point。

 It's essentially the design constraints and their importance。

 These lead to this leads to trade offs in both IA and micro architecture， essentially。😊。

So are there many example constraintss that we have？Discuss and we may discuss later on。

 but keep this in mind。Today， when you design a system。

 you have a bunch of considerations and you may actually rank some of these， for example。

 cost may be the most important thing， energy may be the most important thing。

 time to market may be the most important thing， if that's the case。

 maybe you opt for a simple design right？😡，So there are a lot of design considerations and design point is determined by the problem space。

 meaning the intended users and market in general， this's also the application space。😡。

So application but I don't want to spend a lot of time over here。

 but just to say that today there are many applications。

 so this is a paper from 2001 it talks about some applications but there's a lot more applications today and think about executing all of those applications on a general purpose computer this is why we have a lot of specialized designs today。

😡，And applications will increase so we're going to cover a lot of trade offs in computer architecture and we've covered actually ISA level trade offs。

 quite a few of them， including very high level ones。😡，Starting。

 I don't know how much time we have Well we still left some time starting soon。

 we will cover some micro architectureectural level trade offs。

 but there's also system and test level trade offs that I kind of hint at earlier how do you divide the labor between hardware and software。

 for example， who does the clock who does the power management right。

 Who changes the frequency and voltage， These are actually system and test level trade offs。

 they have implications on the ISA， they have implications on the micro architecture also and when you design a system。

 you need to think about all of these in the end。😊，And this is what's really is exciting。

 I think when you're designing a system， if you have control over all of these。😡。

You actually have a lot of room for creativity on doing something that's really new。

So I define computer architecture as the science and art of making the appropriate trade offs to meet the design point。

 that's a much more concise definition。😊，And。😊，This is not just science or engineering。

 unfortunately，😊，You cannot predict everything in the future。

 So you're designing this thing over here。But you have to make some decisions that you cannot model into the future because we don't really fully know what will happen。

 you don't know the applications， you don't exactly know the users。

 you don't exactly know the market。😡，So you may have actually have some old applications。

 you design your systems to customize old applications。😡。

And then some new applications come two years later after you pushed your product to the market that are very different from the application that you designed your computer system for。

😡，Now， your computer system is not very good， potentially。😡，So it's good to think about this， right。

 this is why you need to be creative like an artist。😊。

So that you can actually do something that's that is potentially flexible to cover different applications so clearly there are applications that are designed from the up I think I've shown this slide earlier。

 but essentially the demand of the users change that's the key。😊，It's good to think about this。

And ISA may not be very capable of doing this This is why ISs get extended people have been adding。

 for example， multimedia extensions which we will cover later on vector extensions。

 matrix extensions over time to cater for different applications initially it started with image processing and media。

😡，But over time it became customized for machine learning today you have everything essentially you have very different kind of accelerators。

😡，Okay， I will conclude this part of the lecture with an analog from macro architectureiture because I like thinking about macro architecture or real building architecture also。

😊，So if you think out about building architecture， future is not constant either。

 you design a building。😡，For example， this building is designed for as a lecture hall。

 but this could change internally， you could change it to something else potentially right if the application changes。

😡，And people have done that many times， maybe the analogy ends at some point。

 or take it with a grain of salt。So people have used for example。

 meals as a theater restaurant and conference room some of you may have been to Mo the and Bru how many have people have been there okay you know that in its original architecture was intended for something else right but over time it evolves so the workloads evolve users evolve and if the architecture can be changed that' would be nice in the building architecture you can reconstruct part of it that's the good part when you bake the hardware if you don't have enough configurable team maybe you cannot change things not much right so it's good to think about that the hardware software interface it's kind of like the interface to this building。

😊，Okay， these are some other examples in Zurk， you can take a look， you can figure out where this is。

 this is this building。😊，Close to zeal and then there's another my favorite example for in Pittsburgh where I used to live at Carnegie Melley University。

 this is a church。😊，It's really they called the church Boworks。So it has a lot of good beer。

Maybe some people over there are watching our lectures right now with beer。Okay。

 i'm just kidding okay so that's the end of this lecture we're going to start my qua lecture soon。

 but I will recommend to you to look at our lecture on assembly programming it's a very short lecture。

😊。

![](img/4c2de24a448f22f60a4668242a2bce1b_24.png)

![](img/4c2de24a448f22f60a4668242a2bce1b_25.png)

It's covers some of the things that you have seen in programming。

 That's why I normally don't cover it。But it will be useful in your labs， especially。Later on。

Because in the labs you're going to write some MIPS programs and you're going to get them to work and getting them to work could be made easier if you actually watch this lecture。

 you could also learn in other ways， of course， but this lecture could be useful。😡，Okay。

 any questions， we're going to switch to this other thing。

 the other lecture because we still have time。😊，Do you have any questions？同。



![](img/4c2de24a448f22f60a4668242a2bce1b_27.png)

I have some additional slides too that you can use， but I will not go through them right now。

So how do we switch to the other one do I just share？This is lecture 9 a。 I don't know what this is。

you know the location of these lectures better than me。

Maybe next time I use my computer and I know everything。Yeah。嗯。Any questions？我。这3。嗯。



![](img/4c2de24a448f22f60a4668242a2bce1b_29.png)

Okay， well good。 Yes， Okay， cool。 thanks， Okay， so let's get started on my qua picture a little bit。

 and then we'll continue this tomorrow and essentially multiple weeks。😊，But it's good to get started。

 as assuming Zoom allows us to do。So I'm going to cover some fundamentals and we're going to jump into some designs。

So this is what's coming。Essentially， we've covered。ISSAs in the labs。

 you're going to cover some assembly programming。😊。

Now we're going to go into the implementation in more detail。😊。

And then we're going to cover a simple implementation to begin with single cycle implementation。😊。

And then we're going to go into multi cyclee and pipelining， a lot of issues in pipelining。

 and then we're going to build up the out of order execution and issues in out of order execution。😊。

Does that sound good？So if we're really over here right now。

 we're not going to change anything at the ISA level。😡，We' are at the implementation level。

And there are some readings you can take a look at them。

 some of these are actually very short parts of Harris and Harris for example。

 and some of these are not even covered at Pe and Patel so this is a soon after multicycle micro architectureects we're going to actually diverge from the books。

😊，Because unfortunately some of these books don't cover some of these fundamental concepts that are really important today。

 okay， this is micro architecture， you remember now let's talk about how to implement the ISA。

 essentially micro architecture is an implementation of an ISA。😊。

Meaning how do we design a system that obeys the software software interface？😡，So。

It's good to also think about system can be solely hardware or a combination of hardware software。

 so we recall call the translation of ISAs right that we discussed at the beginning of the lecture。😡。

So an ISA can be converted into an implementation ISA like many people do today。

 we're not going to do that in the rest of the lecture。

 but you should really think that it's done by everybody today for a good reason。

 not everybody but every like high performance general purpose system manufacturer。😡。

So if we will assume completely hardware implementation for most lectures。

 we may get back to this translation later on。😡，So how does basically we're going to tackle the question。

 how does the machine process instructions？😡，What does pressing an instruction mean we'll assume the one Neman model also right so this is what a pressing instruction pressing means in the one Neman model you have some architectural state meaning programmer visible state。

 memory program counter， general purpose and special purpose registers。😡。

Before an instruction is processed。😡，And then you take the instruction， process it。😡。

And produce an architectural state prime， it's really the architectural state after the instruction is processed。

😡，And processing an instruction is really transforming the input architectural state to the output architectural state prime。

 according to the ISA specification of the instruction， so you're not alone。

 somebody specified what this instruction should do and that's the ISA。😡。

We're going to process the instruction based on that specification right basically it's very simple。

😡，And we've already kind of seen this， right， AS， AS prime， this is current state， next state。

Essentially， it's a finite state machine， right？😊，Okay。

 so one Neyman model sequential instruction processinging， the just a reminder。

 what is architectural state， we've already seen that also in the One Neyman model。😡，Essentially。

 Miami， program counselor and Regs， special purpose， general purpose。

Instructions and programs specify how to transform the values of program or visible state。😊，Okay。

 so let's take a look at the process instruction step， as I said。

 I say specifies abstractly what the architect state prime should be。

 given an instruction on the architectural status's input。😊，Meaning， if you think about it。😡。

Every instruction specification is part of the specification of an abstract finite state machine where state is the programmer visible state。

 and the next state logic is the instruction execution specification。😡。

And it can implement the next state logic in many different ways。And then you produce a state prime。

 which is the programr visible states's updated version after you process the instruction through the next state logic。

😡，So from the ISA point of view， there are no intermediate states。😡。

Meaning AS course as prime based on the instruction semantics and specification Act But micro architectureure。

 we have a lot of freedom， and we will exercise that freedom。

More and more as we study micro architectureiture。Okay。

 so there's one state transition for instruction from an ISA point of view。

In micro architectureecture， we implement how ASS is transformed into AS prime。

 and there are many choices in implantation we can take。😡，For example。

 we can program our invisible state to optimize the speed of instruction execution。

 we can have multiple state transitions for instruction。😡，One option is very simple。

 do what the ISA says， we're going to see that this is not a good idea。😡。

This is not practical to implement。But I will cover it because this is the simplest way of thinking right ISA says this。

 I'm going to do exactly that transform architectural state prime to architectural state transform the input architectural state to architectural state prime in a single clock cycle and this is now the clock cycle。

 which is the machine clock cycle that we have discussed earlier in timing and verification etcter。😡。

Like。1 gigahHtz， for example， right， that's the clock frequency。We will see that this is a bad idea。

😡，And we're going to use principal analysis techniques to analyze that there are not that many bad ideas。

 it's always trade offs so I've also asked you the question right when is this a good idea for example。

 there are very small constraints set of cases this could be a good idea。But the more， let's say。

Easier to implement and better idea for performance and efficiency in general is this。😡。

When you actually， and this is what you have seen actually in the finite state machine that we have seen with LC3。

 for example， going from architectural state before instruction to the architectural state prime。

 as specified by the ISA， you take multiple clock cycles。😊。

So you transition to some intermediate state in the finite state machine。

 and this is a much better way of designing systems。😡。

But it's good to go through the bad way of designing systems first before we actually design the better way and we will incrementally design better and better and better and better ways for some definition or better。

 right？😡，So basically， what this does is you take architectural state。😡。

And transform it to architectural state plus some micro architectitectural state one in one clock cycle。

 you process part of the instruction， let's say fetch， for example， or part of the fetch。😡。

And then next clock cycle， so you can see that we're not changing the architectural state。

 that's critical， right？😊，And in the next clock cycle。

 you do some more operations to execute the instruction and you transform this state to architectural state plus another micro architectitectural state。

You're not done yet with the instruction， you do some more things to finish the instruction execution or try to finish the instruction execution。

 so you transfer architectural state that state to architectural state plus some other micro architectectural state。

 and finally you do a little bit more to finish the instruction and you transform this AS plus micro architectectural state3 to architectural state prime。

😊，So you really update the architectural state only at the end of the instruction execution。😡。

So this is the difference between architecture and micro architectureit， essentially， you expose。

 you change what is visible to the programmer， memory， registers， program counter。

 only at the end of the instruction execution， as you can see。😡。

Everything you do internally is not visible to the program。😡，Okay。😊。

This way you're really obeying the instruction semantics and ISA specification。Okay。

 and we're going to see multiple ways of doing this。

So let's take a look at that very basic instruction processinging end。😡，え。Very basic。

 but not very realistic under many conditions， so each instruction takes a single clock cycle takes it。

We use only combinational logic to implement the instruction execution。

 there are no intermediate programmer invisible state updates。

 so we're actually looking at choice one over here。😊。

So we take the architect state at the beginning of the clock cycle。

We process the instruction in one clock cycle。And we produce an architectural state at the end of that clock cycle。

 according to the instruction specification。And we've seen this kind of before。

 right this is a simple sequential logic。😊，And you can actually look at a single cycle machine looks like this。

You have some state that's called ASS。That ASS is input to combination logic and you get AS prime。

And at the end of the clock cycle， this latch or this flipflop or this set of flip flops or memory in general store AS prime。

Makes sense， right？ You've seen this before。 That's good。 So that's why we built a lot of things。 I。

 if I actually started this way。😊，Meaning we didn't have some digital design， this would be magic。

 but none of this is magic to you right now。😊，You know exactly how these things are done now we're going to build on this。

😡，And you also know， what is the clock cycle time determined by？Basically。

 the clock cycle time is determined by the longest path in this combination logic or critical path right。

 longest delay path in the combination， and we did that timing and analysis in the timing amorification lecture。

😡，We're not going to do more of that analysis， we're going to do at a higher level analysis right now。

 but this combination logic here， the maximum delay path that is determined by the combination logic plus the setup and hold times of the registers。

 etcter。😊，And that is your critical path now I can ask the question。

 assuming this is the way you implement an ISA and ISA has many， many instructions。😡。

Which instruction causes the longest critical path， that's another way of asking。😡，Basically。

 what is the critical path of the combination logic determined by？😡。

There are some instructions that could take much longer in the combination logic than some other instructions。

 for example， a very simple instruction Xor can take very little in the combination logic。😡。

But if you have an instruction like multiply， it could take longer。

Now your clock cycle is determined by the worst instruction that you could implement。😡。

In combination logic， right， So it's the worst case。

 And this is going to be the Achilles heel of this design。

 Each instruction takes a single clock cycle。 All state updates are made at the end of the instruction execution。

 The huge disadvantages the slowest instruction you can implement。😊。

Determines your cycle time so you have a long in general。

 a very long clock cycle time imagine that you have a complex ISA。

 you have a matrix multiply instruction。😡，That could take a very long time。

 it is actually a very difficult to implement in a single clock cycle。

 it becomes unrealistic at some point。😊，Okay multicycle machines。

 you break instruction pricing into multiple cycles or stages。

 state updates can be made during an instruction execution。

 but architectural state updates are made at the end of an instructionss execution and we will see the reasoning for this later on also but one reason is one Neyman model right we have to obey the One Neyman model。

So the advantage over single cycle is now。There is no slowest instruction doesn't dictate your cycle time。

 the slow stage determines your cycle time and you can actually arbitrarily decide what your stage is。

 you can say my clock cycles should be 500 gigahertz。😡，Which is not the case today。

 but you can't say it。And you can design your logic such that every clock cycle takes that long and you can break down every instruction's execution。

😡，To clock cycles that are of that ground layer。 So as a designer。

 you have a whole lot more freedom this way， whereas in the first case。

 you don't have a lot of freedom。There is some work that you need to do and some instructions inherently take a very long time and you're stuck with those instructions because you cannot break them into multiple clock cycles。

 right？😡，Okay。呃。So basically in the next lectures we're almost at the end of this lecture we're going to essentially design machines that go through processing these instructions and remember we already covered this we have six steps of instruction processing and this is basically instruction processing cycle we're initially going to not break this into clock cycles but later we're going to break this into clock cycle so in the next lecture tomorrow we're going to pick up from here and then gradually we're going to do better and better so see you tomorrow。

😊。

![](img/4c2de24a448f22f60a4668242a2bce1b_31.png)

Yeah。