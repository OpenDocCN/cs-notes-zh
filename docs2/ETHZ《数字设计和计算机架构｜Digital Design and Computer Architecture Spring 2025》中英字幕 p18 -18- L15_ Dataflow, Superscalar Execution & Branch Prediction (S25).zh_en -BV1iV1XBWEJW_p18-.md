# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p18 -18- L15_ Dataflow, Superscalar Execution & Branch Prediction (S25).zh_en -BV1iV1XBWEJW_p18-

![](img/a12acf66b09fffa4c9c52fbc853648b0_0.png)

这。啦都啊。你好。Yeah。你水。Yeah道。啊我。Can we checked out with you， iss working。多差多。そま。呃。我。我我。Yeah。せ。对了。🎼东在去相起。

🎼我天。在。Okay。Let's get this started。Good afternoon everyone。

 welcome to another lecture in digital design and Comp architectureure。My voice is not ideal today。

 I actually lost my voice yesterday when I was teaching in another lecture。

I wasI was really excited in that lecture and apparently I was too excited that caused me losing my voice。

But I will do my best to deliver today also nicely。Last week， unfortunately， we couldn't be here and。

Present in person。Because we were in asLOS delivering four research papers as well as one full day workshop on memory century computing。

But I'd like to know how many of you have watched the two lectures that we premiered。Okay， good。

 good because actually we're going to build on top of them today。And tomorrow。

 so it's really important that you have watched them in the very beginning of today's lecture I'm going to wrap up。

Out of order execution。But essentially， it's very important that you also。

 you have watch it or if you。Havet please do it also as soon as possible。

Today we're going to talk about data flow and super scalar execution。First。

 and then we're going to jump to branch prediction because。Another fascinating topic。

Data flowvy already also covered it a bit actually in detail， in when we were discussing about ISA。

So we had this discussion about should I say control flow or data driven？

And today we're going to also basically talk about that and more or less is actually a kind of reminder for you。

 but then we're going to talk about superscalear execution。

Which is another important topic that people have。Used to confuse it a lot without the rot execution。

Like， for example， people thought that when we talk about super scalar execution。

 we mean super scalar out of order， which should not be cannot be the I mean。

 may or may not be the case。We're going to learn about it today。

And then we're going to jump to branch prediction， as I said。

 which is one of the most important components of our two day computer system。Okay。

 so I provided quite a lot introduction， but any questions？nice。Then let's get us started。

Zoom is not okay。 Okay， now it's okay。So this is what we were in the grand scheme of the things in different microarchitectures。

 and we were actually kind of in the process of out of order execution last week。

 we first actually discussed a precise exception， which I think by now you should know that having precise exception is very important。

In order to one of the main reasons is that in order to be able to debug our systems。

Because whenever you have a kind of exception or interrupt in your execution。

 you should be able to know what was the exact point that basically we moved to an interrupt or interrupt handler or exception handler。

And also when you want to debug it， you should know that basically what happened before at these moments such that you can debug and see what was wrong so having precise exception is really important and that we discussed in detail last week。

And then also we started talking about out of order execution。

Today we're going to wrap up all the order execution very quickly and then we start other exciting topics These are some readings that you can also check。

😊，And then let's review and wrap up all the water execution。

So remember that basically when we want to enable Out order execution。

 we basically need to provide these four things at a very high level。

 we should be able to link the consumer of a value to the producer。

 so that's most important one of the most important parts of Out order execution。

And other important part is， we should be able to buffer instructions until they already ready。

That we have done it， for example， using reservation station。

And we should be able to keep track of readiness of source values of any instruction。

such that when an instruction is waiting in a reservation station。

 we should be able to track the readiness of the opera and once the opera。

 all the opera of that instructions is already ready。

 we should be able to schedule that and then a schedule meaning that we need to dispatch essentially we need to dispatch that instruction to the execution。

And you've already seen that we implemented these ideas， these features by some of these algorithms。

 or some of these techniques， if you will， for example， with register renaming。

 we basically provided to eliminate false dependencies and enabled linking of producer to consumer。

 basically we implemented linking with register renaming。

Another one is buffering in reservation station， which is again in order to implement buffer support and tag and value broadcast in order to track readiness of the opera and wake up and select in order to dispatch。

And I hope you all know all these topics because we had that in our last lecture。Any question。Okay。

 good。Also recall that out of order execution is kind of restricted data flow。

 Why is it restricted because while you are making this。Depending on your instruction， window size。

Basically you are fetching and decoding instruction in that instruction window and then you keep instructions in your reservation station so depending on that instruction window side you should be able and also your rearorder buffer you should be able to understand what are the instructions that they are independent of each other and what are they are ready to schedule or dispatch and then you can easily dispatchion so it's very similar how we handle out of order execution right in out of order execution paradigm we basically we don't say we say that we don't want to think more about controlflow driven of execution we want to be completely data driven so every instructions should be able to execute when the opera already。

Of course， without a order execution， the paradigm that we does discuss。

 we cannot do that completely because our instruction of window size is limited。

So we cannot do it for the entire program， but to some certain limit that have we should be able to implement restricted data flow。

 so that's why we have this kind of concept that out of order the execution is kind of implementation of data flow in the microarchitecture while the programming model is still sequential and control lottery。

And we had this example that once we have this register LS table。And also。

 the status of reservation station for different functional units， we should be able to basically。

Create the data flow graph of these operations。So you can actually also check this in our last lecture that how we basically throw this control flow graph。

 data flow graph out of that reservation station and register table。Also to recall again。

 Out of order execution with precise exception， which we also discussed briefly that in the beginning。

 people started building out of order execution， they didn't have precise exceptions， I guess in。

 for example， IBM 360。Because providing precise exceptions in Out order execution is not really that easy。

 but later on people work on it and then provide precise exception for Out order execution which is super。

 super important， and then you can have high performance high parallelities at the same time you can still have basically programming ease and debugging support because as a result of precise exception。

😊，So the way that we implement is actually kind of the most。The most， I would say efficient。

 not the most efficient， but the most common rate that people are still using。

 so the exact implementation of this can be different from processoror to another person。

 but overall the fundamentals are the same。So basically we have this reorder buffer to support in order retirement of instructions。

And we have a single register file， which is physical register file to store all registers。😊。

And we have this single registerifier for both speculative and architectureural registers。Still。

 we have different separate registerify for in teacher and floating points。

And then we have two register maps in order to store pointers to our physical registerify and this basically map one of them is for future or front end register map which used for renaming and another one is for architecture or register map that used for maintaining precise state。

And this design avoids value replication in reservation station。

 reorder buffer and etc cetera the beginning of the lecture in Ota world there the design that we showed actually at some point you see that we have many。

 many different memories to store registers， but then we come up with this idea that basically we can combine all of them in one physical register and then we need to keep two pointers to map two basically pointer maps essentially。

And this is one of the basically successful Out order machine at the time。

 Intel Pentium Pro that we discussed about it， and this is a general organization of Out order processoror。

And that you have seen。But now I want to make some Christian to ponder。

And I like your contribution here， actually， so why is out of order execution beneficial？

Any thoughts if you want to summarize。Maybe in one sentence， two sentence。Yes， there is some kind of。

Seeps a depend level。 And if you would break， he would obviously。Not do anything。

 So by re orderdering can kind of still。To avoid the stalls， for example， right？Okay。That's correct。

 actually。So basically by keep executing， by keep the pipeline full。

 your functional units busy with useful instructions， you can avoid the stalls。

 or I would say that more generally you can have latency tolerance essentially。

 so out order execution tolerance latency of multie operations by executing independent operations concurrently。

And that can actually summarize why out of order execution is very much beneficial。

But we should also think about it。 What if all operations take a single cycle。

 if all operations are taking only one cycle， then maybe out of order execution is not。

Beenefficial that much， right？But we know that this is not。

This is usually not the case because of long memory access latencies， for example。

 even when you have cache is also cash， you can accelerate your access。

 but still you might miss in the cache and then you need to spend a lot of time for the memory and we're going to learn a lot focus a lot on memory system in later lectures。

But what if an instruction takes 100000 cycles？Basically。

 how large of an instruction window do we need to continue decoding without a study？

So as basically as much as you want to increase your latency tolerability to basically tolerate longer。

 longer latencies with this idea of outwarded execution。

 you need to enlarge your instruction window such that you have hopefully more independent。

 you can find more independent instructions to keep your pipeline full。😊，Essentially with that。

 so your question is that how many cycles of latency can out of order tolerate and that depends basically on your instruction window size。

 that how many decod but not yet required instructions you can keep in the machine。Makes sense。

So let's also conclude with some advantage and disadvantages of out of order execution。

 so the first one as we discussed is latency tolerance。And the other one， I would say。

 is irregular parallellysis。😊，So out of order execution is very good at dynamically finding。😊。

And exploiting parallel operations in a program。These operations。

 the programr may not also be completelyva of that， or may not think about， okay。

 these instructions or these instruction can be executed in paralleld。

But the out of order machine is very good at that to understand that at run time。

These instructions are independent and we can actually schedule them for the execution and that can exploit a very good parallel release out of your basically programs。

 but at the same time we also have some disadvantages of course we have higher complexity。

So that potentially higher complexity because we need to deal with a lot of this dependency check。

 for example， and the control logic is actually getting more and more complicated when we want to do out of execution and that confront potentially lengthen critical fast delay。

 which in the end will enlarge your clock cycle。😊，And then you need to add more hardware， of course。

 that basically can increase your cost。And we should recall this execution time of entire program that's basically number of instructions times average CPI times clock cycle time。

 So when you have out of order execution， assuming that we don't change the program。

 so the number of instructions is still the same。But， basically。

Out word execution impacts your average CPI basically tries to lower down or reduce your CPI in other words。

 other word execution that tries basically that you execute more instructions in one cycle for example。

 because of the parase。So you have list CP。But it can also increase your clock cycle time。

 So in the end， it might not be beneficial so。That's a very interesting tradeoff here so you might for example be able to increase your instruction window size and also make your control logic more and more complex such that you lower than CPI even more。

 but then you might actually cause a lot of increase in your clock cycle time and in the end that might not really be beneficial for you so designers should be really careful when they are basically working at these tradeoffs for their performance and energy efficiency。



![](img/a12acf66b09fffa4c9c52fbc853648b0_2.png)

We also have an interesting topic on loaded the store handling and out over the execution。

 which is actually quite。Complicated is actually one of the most complicated parts of Out order the machine。

This part is actually optional， so we're not going to test you in the exam。

But we will premiere an optional lecture early next week that covers loaders store handling out over the machine。

 so basic， but I recommend you to watch this lecture because it's going to provide you a lot of exciting insight。

About how。Complicated our today's machines are。

![](img/a12acf66b09fffa4c9c52fbc853648b0_4.png)

Okay， so yeah， these are tradeoffs that you already discussed。😊。

But now I want to jump into data flow at the I。But this can to be an actually a more or less review for you because we already covered data flow in prior lectures。

😊，So yeah， so recall that basically out of ordering machine is restricted data flow and we've seen that。

Data flow summary is that availability of data determines order of execution。

 a data flow node fires when it sources are ready， so that's the only criteria that you have so programs represented as data flow graphs of node essentially。

So data flow at the ISA level has not been as successful。

 people actually have tried that but for many for very good reasons that you can also imagine basically people couldn't make that much progress so they were not that successful the main reason is that it's very hard to debug it's very hard for programmer also to write a code in using a data flow ISA。

😊，And once also you write that quote， when you want to debu it， debugging is a myth。

 which we're going to also see later， right。But that's one of the main reasons that basically data flow at ISL level is not that successful。

 but data flow implementation at the microarchitect level by preserving Phman model semantics。

 as we do， for example， in Out of order execution， have been very successful。

That we all most of the machines that we already have in today's systems。

 they are all actually using that they are all out over the machines， I mean， not all the processors。

 but most of them。And also data flow mapping of programs to reconfigurable hardware substratet such as FGs has also been successful recently。

 people have worked a lot to use FGAs in order to accelerate important applications like machine learning by informmatics and so and so forth so they actually try to generate the data flow graph of the application and then map that data flow graph to the hardware to the FiG that can be translated into circuits and that can provide a lot of performance for them which is very very exciting so in your labs you're using a FiG to be a processor which is a completely different purpose。

That basically you learn how processor works and how a FiJ works combine them and then work that can work nicely for this course。

 but there are also many research going on that people use a FiJAs in order to accelerate important applications。

 as I already said。So you might be interested in looking to such works。

 I think I provided some references to some of these works when I was presenting lab logistics in that lecture。

I guess lecture two or three around that time。Okay。

So this is again recall for you that in ISA level trade off。

 basically we have this trade off that should we use program counter or not。

 so do we want a program counter？Or instruction pointer， some processor or actually some ISA。

 they call it IP instruction pointer in the ISA。So if you say yes。

 you immediately commit to have a controlled driven or sequential execution paradigm。

As we usually do also in Phium my model。But basically in in data flow paradigm， you can say， no。

 I want to be only data driven and then I want to have fully parallel execution。

But then there is a trade off， there are many high level ones like ease of programming。

Which one is easier for average programmers？I think I vote for sequential programming。

Which one is easier for compilation， which one is better for performance。

 for extraction of parallelities。And which one is cause higher hardware complexity。

 So you can actually think about it and。There are a lot of arguments for some of them as well。

 but in general， once you have data flow paradigm， you have much higher parallelities。

 if you can present that at the software with the ease of programming。

 that would be probably very good。Because that provides a lot of parallels for you and extracting paralleles out for outdoor data flow graph in the hardware so is much easier。

😊，Why not now we need to deal with the sequential program。

 so our program is sequentially written and then the hardware needs to dynamically exploit parallellysis out of it So the hardware needs to generate the data flow out of it。

 which is。W is a harder task compared to the fact that you have a data flow graph。😊。

And then hardware is using that essentially。Yeah。So we we can also have this ISA for data load radaroff that we already also discussed advantages is that very good at exploitingre parallels？

But of course， for disadvantages， I would actually say that the most important one is we have no precise state semantics。

Which makes debugging a mess， essentially， so one of the main reason that we also wanted precise exception in the past was also for programming and debugging。

So once you don't have， basically you should know that， okay。

 you have a data flow graph and you know that this doesn't work。Or for example。

 you have a data flow graph and then you're executing that。And then you jump you go to interrupt。

 you go to exception and then you want to come back so when you want to come back you basically should know that what are the notes that they already what are the edges that they already actually executed what are what are the edges that they are not yet executed what are the opera that they have been ready and what are the opera that they were not ready so everything basically having all these information is very very hard so that makes the thing that having keeping precise state semantic is very hard when you have data of Lo graph。

And that makes debugging very difficult and interrupttro and exception handling is very difficult。

And at the same time， you might have a large hardware overhead because of tag matching。

 data tiger storage， at some point you might have too much parallelllities。

So that your priority is too much that your hardware cannot handle it， for example。

 you don't have enough number of functional units， so there might be many instructions。

 many operations ready to be dispatched。But your hardware cannot support that many instruction at the same time。

 because for example， you have only， I don't know， five others。

But you want you want to do 10 edition at this moment。

 so basically you need to somehow schedule so that's why in part of how order machine also we have this scheduler that among the instructions that they are ready to dispatch。

 we basically need to schedule select those that can be dispatch essentially。Okay。

 and how to enable mutable data structures， essentially there are a lot of things that they're not that easy。

And this is， we can also think of another way of this tradeoff that is coming from ISA and microarchitecture level。

So there is a similar trade of， as we have seen in control versus data driven execution at a microcurit level。

 so in ISA level， ISA specifies how the programmer sees the instruction to be executed。😊。

So programmers can see a sequential control flow execution order versus programmer sees a data flow execution order。

So we usually see that only the basically sequential control flow execution order in today days's grand scheme。

At micro architectureiture， how the underlying implementation actually executes instruction。

 So micro architectureure can execute。Instructions in any order。

 as long as it obeys the semantics specified by the ISA， which we usually do in Outor execution。

 but in the end programmers should see the order is specified by dis。

If you want to learn more about data flow execution model。

 I would suggest that you check these papers。And we also had some lectures from the past that we go into details。

 a lot of details in Out order execution。

![](img/a12acf66b09fffa4c9c52fbc853648b0_6.png)

Sorry， in data flow execution model that you can learn a lot from them。



![](img/a12acf66b09fffa4c9c52fbc853648b0_8.png)

Yes。But I would also say that this actually a kind of very interesting historical readings for you as well that you can check。

 so this is one of the papers fromle Yle Pat that basically they work on how they can make out of order execution with precise exception。

😊，And basically， there are many， many works。On top of that。

 in order to really make the out of order execution possible for today's computation。

 because having out of order execution without precise exception。

 which if we consider out of order execution as a restricted date of flow， which is， in my opinion。

 which is completely the case。😊，Then providing precise exception on Out order execution is very similar to providing precise exception on data flow right so that's why these papers are really exciting to read。

😊，And there's also this retrospective unrestrict data of flow model that we can also check if you're interested。

Yes。Any question？Okay。So now I want to start going into superscalealator execution。We're gonna see。

A lot of different approaches to instruction level concurrency。 We already seen pipelineing。

We didn't see much fun grainmon trading， I will actually cover it today in a little bit。

But then we also have out we also seen Out order execution data flow。

 and then I'm going to start with superscaleal in later lectures， we're going to learn about V IW。

 which kind of。Genral8。Basically data kind of independent instructions。

 so like in out of order execution， you try to generate create your data flow graph。

At run time at dynamically at the processor and find basically independent instructions to be executed in VLIW people try to do similar thing at the compile time so they try to basically extracts what are the instructions at the compile time that they are independent and they basically pack these instructions together and that make this VLIW very very long instruction so the long instruction but that instruction the pack of many。

 many small instructions and then try to schedule that instructions to the pipeline so essentially your hardware can be very simple here because in hardware you don't need to check dependency in VLIW we're going to learn about VLIW later and after that we're going to see a lot about CD processing and how GPUs are using CMD in order to accelerate many important applications。

不。But what is superscalealar execution？😊，Basically， the idea is simple， we want to fetch， thecode。

 execute， and retire multiple instructions per cycle。So when people， for example。

 say invite superscalear， that means any instructions per cycle are fetched， decoded， executed。

 and retired。I mean， that's the ideal number。You're going to see that in practice you may not get to that end on average。

 which that's one of the reason that basically we need to work on branch prediction and also this control dependence a lot。

 but essentially in superscalealar we also have this kind of dependence issue。

In Out of order execution， we were scheduling， we were basically fetching and decoding instructions in a。

😊，In a con of time， you know， after each other， and then you need to basically check dependencies between instructions that they are coming to the pipeline。

 but that's a para that you can see that in the horizontal so essentially you need to check the dependencies in horizontally。

But in superscalealar， you're fetching， decoding， and executing instruction vertically。

 like completely in parallel， so you need to check dependency actually vertically as。

So that makes your dependence check actually very。Complicated if you want to have superscalealar and out of order execution at the same time。

 which actually most of today's systems are like that。

 they have to check dependency both vertically and horizontal。😊，Okay。Yeah。So of course。

 we need to add hardware resources for doing so and hardware performs the dependence checking between concurrently fetched instructions。

And I want to emphasize that superscale execution and other execution are orthogonal concepts。

So essentially considering that we have access that can be processor in order or out of order and another access that can be scalar or superscalealar。

 scalar， meaning that we fetch thecode the executive retire money instruction at per cycle。

So essentially you can have any combination of that， you can have in order scalar。

 you can have in order super scalar， you can have out of order scalar and out of order superscalear。

😊，You don't see much out of order scalar processor the time， but other than that。

 the other three are actually。Already also available。 Yes， so with the kind of the。

The instructions in a way there are independent instructions and then kind of use scale execution on the。

I couldn't understand the questions。The reason why you combine it is because kind of reshuffle the。

The instructions in order， and then super Yeah， yeah， exactly。

 So when you have when you have super scalealar in order there。Basically pipeline you are still。

Executing instructions in order of the program semantic。

But you might be able to actually schedule more instructions。In parallel。

In superscale you can actually fetch thecode you know in parallel right so if you have this out of order support you can actually select instructions from later you know and pack them as you said actually yeah and then but in the end you need to make sure that you retire them in the program order there because of for new my essentially。

Very good question， Yes， there order processes。Well， because people realize that。

These once you have out of order you have this dependency check you know there are a lot of dependency check that you already have。

 so why not also have this superscalealar on top of it right because you can share a lot of hardware and at the same time in order to really benefit from out of order support it's also important that you have superscalealar such that you have much more parallellysis。

Yeah。C。Any other questions， these were really good questions actually。Okay， good。

So I'm going to show you in order superscalealar processor as an example。

 but you can think of how out of order superscalealar processor can look like we already also discussed a little bit。

So basically， we need to have multiple copies of database， database that can fetch decode。

 execute multiple instruction per cycle。So here you can see that for example。

 when we have this instruction memory。So here we are fetching two instructions。

 that's why we you can see we have two lines here。And then we need to to the registerify。

 we actually provide。Read and write addresses， we are doubling it。

 so now we have two read and write addresses。And then we need to also have two right enabled for the registerify。

We need to have a。We need to double the output read Port our registerify。

We also need to have two areass， we also need to have two ports for the data memory。

And also we need to have two multipleplxer here， basically two result posts that makes you right your。

To do right back in parallel。So as you can see that needs a lot of hardware， essentially。

And if you do that， you can have idealL IPC of two。

 meaning that you can execute two instruction per cycle in other words， your CPI is one over two。

 essentially。But as I said， you need a dependence deduction between concretecurrenly fetch instruction。

 let's see with an example， so here is a MIPS code。

And we have a basically superscalear in order machine actually。

 this example is coming from your book so you can also check that in your book as well。

 But from this picture you can you should be able to。

So every two instructions that you check they are independent， fortunately in this example。

 so basically you can fetch two instructions， this load word and add together and then you can go to the next step and then here your pipeline you can also fetch the next two and the next two and here we didn't have any dependency and in the end we got basically actual IPC we get two because we could schedule issue six instructions in three cycles yes。

AndI have a question。Yes but。Basically， with， for example。

I assume had an execution of a two at a time， but we can only retire one which cycle kind of our buffal。

multipleNo no， no， we cannot retire multiple at once I mean。

 we can retire multiple instructions at one time if all of them are completely independent so there is a dependency logic for doing that I。

But if these instructions are dependent for， you cannot do that essentially。Yes， yes。

 If you have enough hardware for that， of course。In this example， for example。

 you can see that we have two right back basically port， right？😊。

So that's why we can do retire two together。Okay。Okay， so in this example。

 we could get to idealL IPC that we wanted。 but how about this one。So this example， unfortunately。

 basically this addition。So this load word actually load from this address to register T0。

 and then this addition is actually dependent on this load word because you need to use T0 for this addition。

So that's why you cannot schedule this edition， you cannot fetch and decode addition with this loadboard。

And here is the graph， the timeline of this pipeline， you can also check it in more detail later。

 but essentially you have this load work and then you need to wait for some time and then you can do addition and subtract and then and an or and then storeboard essentially。

So if you calculate， you can see that the actual IPC is 1。2。Which is not really great。

 So we double our hardware and then we only get 20% improvement。Now the question is that。

 can you reorder the instructions to get IPC equals two？好。Anyone。Yes。Put the ads in the end。Yeah。

 I think that should work。But no。I guess that can not work because。This loadboard and this subtract。

 they actually have the same destination register， right？Yeah， yeah。Very need to be both down。Yeah。

 so the solution that I have in my mind， this might also work。

 but that might not be the most efficient solution if you move this or operation。Here。

That could basically work out well， and then you get the IPC of two。

So that's interesting basically your compiler can actually help you so compiler if the compiler is a bit of superscale there。

😊，And also the pipeline steps， compiler can also try to reorder your instructions a bit in order such that you benefit from your sophisticatedcate process。

Okay， so we discuss six fundamental ways of handling flow dependencies in our pipeline lectures and out of order。

 so detect and wait， detect and forward bypass， detect and eliminate。

 detect and move it out of the way， predict and do something else。

The thing is that all these can be employed in superscale processor as。So basically。

 whenever you have dependency check and you need to deal with dependencies。

 you can use any of these also fundamental ways or combination of them actually。

To handle flow dependencies。Let's try to conclude with some advantages and disadvantages。

So superscaleator， of course， it provides higher instruction throughput， higher IPC。

But then we always need to recall this equation so in this equation number of instructions is still the same。

 but the average CPI is getting better， so now we have lower CPI and we have a superscalealar。

 but as a result of superscalealar that you need to do dependency check vertically。

And also the renaming logic， I didn't talk about renaming logic that we also need for superscalealar that could。

 for example， fix the issue for for the previous example that we had this。

The same destination for two instructions。But that renderming logic also needs to be sequential。

Because you might want to issue eight instructions。At the same time， but then you rename one of them。

 basically you rename the first one， and then the second one you need to also rename it。

And once you rename this， the third one， also you need to rename it and then first。

 and then you might need to actually do it for the old eight instruction that you have。

So essentially， your renaming logic is getting sequential。😊。

And that can significantly increase your critical path that in the end， cause lower frequency。

So people actually have tried a lot to pipeline， for example， that renaming register renaming Doic。

 so modern processors are actually heavily heavily pipeline。Actually。

 we need to do a lot of pipelineing once we do superscalealar because super scalar。

 the dependency logic in super scalar， since you are doing it vertically。

 actually you need to do check a lot at the same time。

And that as a result cause longer latency and longer critical path and in order to break that critical path。

 you need to add pipeline stages， and that's why super scattered processor are heavily deeply pipeline actually。

So as a disadvantage， of course， we have higher complexity for dependence checking that require dependence checking between concurrent instructions。

And register naming becomes more complex in an out of order processor once you have out of order processor and suppresscate it essentially。

And that potentially links in critical capacity that can cause longer clock cycle time。And of course。

 we need more hardware resources for this。But the interesting point is that。

Like Intel actually started having super scalar even before out of order。 so this is one of the。

Processor at the time， 1993 intel Pentium that they actually made a superscalealar。

 I guess is actually too white superscalear processor。But this in order。

And Al at that time also they made in order superscalealar。

 but later on basically they combine out of order with superscalealar to make。Basically。

 processor much faster and high performance Alpha also does that to same。But at some point。

 Al didn't continue。For many reasons。That caused Intel basically be the major event there for a long time。

Okay， so what did I want to show here maybe？Yeah， this， for example， from AMD。

They have four way here you can see that from instruction cash they have they are fetching for instructions and internally they they basically。

transranslate these four instructions to six micro operations。

 so that's also something that we have in our modern many of these modern processors that we have some micro operations that instructions that they are much simpler and easier to execute at the ISA level ISA level you might have more complex instructions。

 but there is a translator internally in our processors that translate those complex instructions to easier instructions to handle so。

Here essentially you have， I guess， six white basically pipeline to execute these six micro operationss。

And this is from Apple M1， from Rivers engineering of some people that they wanted to see。

 they wanted to learn actually what Apple M1 has。They realize that probably Apple M1 also has8 white。

 basically superscalealar。And this is one of the most recent out of order design。

That's we have in our markets。And that brings me to the end of lecture 158， any question？Okay。

 I think I'm not gonna start 15 B， let's。I guess have an early break and then we can continue at 350。

😊，是。

![](img/a12acf66b09fffa4c9c52fbc853648b0_10.png)

![](img/a12acf66b09fffa4c9c52fbc853648b0_11.png)

Hello hello good helloC Miro Leo feedback also scan feedback。😊，😊，有得人。Okay。どなね。好。So。ご。そ。Okay。

 let's get us started。Am I aible in soon。Great。😊，So now I want to start。

Discussing about French prediction。Which is one of the most fascinating topic。

 actually in computer system。And this is a basically part of yours is is a very important component that if you don't know how to do it。

Basically， you should kind of forget about having a pipeline out of over there。 systemystem。

You're going to see actually very soon the motivation of the study， but we're going to show。

If we have a branch prediction， which is not。I create enough。And that enough。

 you're going to see how much we need actually。Basically， the performance we get is very， very low。

And that's。Makes a lot of inefficiencies。This topic is actually still alive and people are doing research。

 cutting edge research in branch prediction。One of our flagship conferences in computer architecture Ica。

 which this year is happening in Tokyo， Japan， they they are holding another。

Basically addition of branch prediction championship。

So many researchers in all the world they are actually they are trying to compete for that。

 they're going to actually come coming off with many different branch prediction algorithm algorithmms they're going to submit and they're going to say。

 okay， who one is the best。And that shows actually how much this topic is very important。

In order to provide good performance for out of ordering machine， pipeline machine。

 and so on and so forth。Okay， but we actually have seen branch prediction also a little bit in prior lectures that I'm going to use those actually just to start and review。

 but we're going to get to a more advanced topic very soon。Okay。

 so now we know that we already covered data of flow and superscalealar execution and now we want to jump to branch prediction probably we are not we should we are not able to finish it today and tomorrow we're going to continue from what we left of today。

Okay， so basically the idea for branch prediction is to handle control dependence in our system。

And this is a kind of preca for you to just jog your memory。

 so our question is that what should the fetch PC be in the next cycle？

And the answer is that the address of the next instruction。Which is correct。

 but this is not really helpful answer。So the main question is that basically， okay。

 how should I get that instruction？First of all， all instructions are controlled dependent on previous ones。

Any thoughts， why？For branch instructions， it's clear right you have a branch instruction and you don't know what would the next one。

you are not sure if the result is going to be taken。Or not taken， we're going to see a lot today。

Maybe an exception。Exception， yes， that could be， yeah， one of them。

Another one which we haven't seen actually in MIPS， but is actually possible in some other ISAs。

That not all instructions have the same links。So in MIPS， for example。

 we know that instructions are tail to beats。Whi 4 bys and。

All the time the next instruction assuming it's not a controlled instruction like a branch。

 the next instruction is PC plus4 right so we know that but there are some ISAs that basically your instruction might be1 byte to I don't know。

 16 bytes。And then basically， you need to decode， you need to fetch this instruction， decode it。

And then realize， okay， this instruction is for example， four bytes or six bytes。

 then the next instruction I need to basically go to PC plus6， for example， to fetch that。

So that makes basically these ISAs are very hard to handle， I mean。

 there are ways to improve the performance for them as well。But essentially。

 all instructions are control dependent。If the F instruction is a noncon flow instructions。

 next F PC is the address of the next sequential instruction。

Which is easy to determine if we know the size of the fetch instruction， which is usually the case。

 for example， for MIPS ISA， but might not be the case for some other ISs。

If the instruction that is fetched is a control of flow instruction。

 then how do we determine the next fetch piece？Because we want to branch somewhere。

 we might branch or remain not branch， but basically we are not sure。

 so we don't know from which path we need to fetch。In fact。

 how do we even know whether or not the fetch instruction is a control flow instruction？So you。

 you fetch。And then you move to decods stage。😊，And in that decoded step， you realize that， okay。

 this is， for example， a branch instruction and you might， for example， predict， okay。

 that I want to。Fetch from PC plus4 but this is too late because once you are in the decoder step you want to fetch the next instruction right so fetch and then when this instruction in the decoder step I need to do fetch for the next one。

 but this is if we don't do that basically is already too late。

We have many different types of branches in our system， let's look into these types。

You already read in youre array of conditional branches， that direction at the fetch time is unknown。

What are these conditional branches， for example in MIPS we have branch equal branch not equal。

 these are conditional branches right and the number of possible next fetch addresses is two。

Which you need to calculate that based on the PC and relative addressing that you have in your I。

You might have also some unconditional branches like jump in MIPS for example。

 so these are always taken， so predicting about taken or not taken at least is easy for these basically jumps for these branch types because they are unconditional。

But again， you need to calculate that target address， you should know that target address somehow。

To which position you are jumping， essentially。You might have call branch also return。

 so these call and return are used when you are using functions， for example， your SM code。

 and then you might have also some indirect branches like jump register that again is always taken but to where you're jumping is actually depends on the value that's stored in a register。

So you need to basically execute that jump， fetch that read that register value。

 and then set the PC to the correct position。So you can see that the number of possible next fish addressess is actually also quite different here。

So if I want to summarize essentially this branch prediction or。

Control flow dependence is actually quite worse for conditional branches and also worse for indirect very hard to handle for these two in the in the between we can do it easily I mean not's completely easy but there are ways to handle it much easier。

But let's see how to handle control depends， so critical to keep the pipeline full with current sequence of dynamic instructions。

We know that and the potential solutions， if the instruction is a control flow instruction。

So one way is to install the pipeline until we know the next fetch address。This is a solution， but。

I think we should call it a non solution because we don't want to stop。

Another way is to guess the next switch address， which is the topic that we're going to talk about today using branch prediction。

 we're going to guess。Another way， which has been employed in some ISAs， I think like MIPS。

 employee delayed branching。Which is not a great idea。

 we're going to learn about it probably tomorrow。But essentially with this branch delay is slow。

 they are trying to change the semantic of branch somehow that there are some instructions that they add after the branch instructions that these instructions should be scheduled for sure。

So basically， the compiler needs to find some instructions that they are independent of the result of that branch and put these instructions after that branch。

And then we always execute those， so basically you are dependent on the result of that branch。

 you're dealing that by running executing some instructions that they are independent of。

 but we're going to learn about it later， you're going to see that this is not a great idea because in the end it doesn't work well when you have conditional branches for sure。

 for example。Another way which I really like is actually do something else with fine grain multi trading。

 I will cover it a little bit today。Another way is to eliminate control flow instruction using predicated execution。

 we're going to also see a little bit today as well， but maybe more later。

And we can fetch from both possible paths if you know the address of both possible but basically we call it multipas execution。

 so once you have a branch you basically fetch from either or passes like for example。

 you have a conditional branch and you keep fetching from taking pass and also not taking pass and you execute and once you know the result of result of that branch。

You basically， you need to flush。The instructions that you fetch。From the wrong path， essentially。

But you are just executing those this call as speculation execution。

 so you you are only executing them speculatively， but you are not committing these instructions it's very important that we should not commit these instruction because that might be in the wrong pass。

😊，People actually have used this。Also architectural optimizations to cause some security actually effect on the system。

Because there are some ways to leak some information when you are in the wrong path。Spulatively。

 but you are still in the wrong past。Okay， I'm going to start with this stall。

And I want to show you that why is not a good solution。So by install， basically。

Assuming that we stall for 50% of the cycles so in this example we consider that we have nonconl flow and unconditional branch instruction so every other instruction is unconditional branch instructions so basically we know that we're going to branch we're with unconditional branch we know that we're going to branch to that address but we don't know the target address essentially。

So we do fetch thecode and then we need to， we cannot fetch the next instruction because we know we don't know the。

You don't know that。The correct address。So here we need to install and then we delay the fetch。

And then again， we need to delay the fetch， delay the fetch。And basically。

 you can see that you are increasing the execution time a lot basically。

 you cannot keep your pipeline full as a result of control dependence that you have。

So that's why stling is not a good idea and we don't need to go into in more detail because this is really a bad idea and no one wants to use it actually。

Okay， but we can do something else which has been employed a lot， for example， in GPUs。

And they are doing fun grain monrating， but what is fun grain monrating？So the idea is simple。

 we you want to fetch from a different trade every cycle。

 such that no two instructions from a trade are in the pipeline concurrently。

So the idea is that once I have many threads。I can and these threads are independent。

I can basically schedule instructions from different threads in the pipeline and I don't need to check control dependence across these instructions。

 sorry not control dependence， like any dependence check across these instructions because these instructions are coming from different threads that they are independent。

And also once we have a control dependence， for example。

 there is an instruction from a trade that is a branch。

 so I cannot fetch continue fetching and decoding from that thread context。

 but fortunately I have other traits， so having scheduled instruction from other threads。

So that's the idea of fine grain multitra， but of course， in order to make it possible。

 you need to have context of all these threads on the on your hardware ready。

 meaning that you need to have registers for all these threads。

 you need to program con for all of them。And your register file should be large enough to house all these register values。

 yes。Because GPUs they they。So the idea there is that they wanted to we're going actually have a lecture on GPU as we go into detail of that。

 but very briefly the idea in GPU is that they want to make the hardware simple so they don't want to deal with a lot of these control dependence and dependence checking and forwarding paths I mean all these things that we have in out of order execution and they want to provide these latency hiding supports by doing fine grain multitraing so we have many。

 many threads in GPU like for example in one core we might have 2000 threads。

And then we can basically context switch across these threads very， very fast。

Such that we can hide latencies。Why do we want to keep in simple because more threats。

To basically to allocate more area to compute。Because in Out order execution。

 if you check some papers and some reports from the actual hardware， you can see them。

significant part of the processor is actually allocating to the control legendt。

And in GPU they want to do compute as much as possible。

 so that's why they want to have simple control logic and fine grain multitra is actually a good way to simplify your control logic。

Yeah。Very good question。Okay， so basically hardware has multiple trade contexts。

 PC and registers per trade， and trades are completely independent。

And no instruction is fetch from the same thread until the prior branch instruction from the thread completes。

Essentially， the good thing is that no logic needed for handling control and data dependencies within the thread。

😊，And we have high trade level throughput， and overall you might do。

 you will have a good throughput out of your process。But single thread performance suffers。

So if you want to use this idea， find grain multi tradingd。

Across threads that are completely different from different applications。

Then that might not be a very good idea because you might actually cause some application to delay a lot。

But once you have many traits that they are still independent。😊。

But they are from the same application。Then the overall this idea is contributing to the better truthput of your system。

嗯好。hihi is the case again for GPUs。And extra logic for keeping trade context， as I already mentioned。

 and throughput loss when there are not enough threads to keep the pipeline full。

 so there might be the cases that you cannot find enough number of threads。

 enough number of eligible trades that you can schedule instructions from。

So just to give you the basic idea， basically we need to here we have program Con。

We need to basically add instances to our program counter。

 we should have program counter per trade context essentially， so if you have for example。

 four traits that you want to do fun grain multi tradingding you need for program counters and also you need to increase your register file。

 essentially you need to have register space for every trade that you want to have in your hardware。

Yeah， so the idea， as I said， is a fetch from different trade every cycle。

 such that no two instructions from a trade are in the pipeline concurrently。

 and that can totally control and data dependence resolution latencies by overlapping the latency with useful work from other traits。

That improves pipeline utilization。And improves trade leverage throughput， as we discussed。

And you can learn more about from these papers， actually。

 these are the first papers that introduced the idea of fine remonrating。

Here is an example that basically we have four， for example。

 program counterors and we also have four general purpose registers in our registerify。

Here also an example for San Niara that essentially you have multiple program counters。

 you have also bigger registerifier and so on and so forth。Okay， so as an advantage。

 basically no need for dependence checking， which is great。😊。

Only one instruction pipeline is coming from a single trade， so we don't need to check that much。

Known need for branch prediction logic。Because you are tolerating the latency of branch resolution。

 branch instruction resolution by issuing instructions from different traits。

Otherwise we have to basically basically otherwise bubble cycles used for executing useful instructions from different threads。

 so that's another good thing。And improved system throughput。

 latency tolerance and pipeline utilization。As disadvantageous， extra hardware complexity。

And that reduces also a single thread performance， of course。

And resource contention between threads in caches and memory。

And that's why actually memory system is one of the most important parts of the system and is actually still the bottleneck。

And that's why we're going to allocate a lot of parts of this course also in future in later lectures to memory system。

 which is not even enough as well， but we will try to cover as much as possible。

And dependent checking logic between threads may be needed still for load of store。

 but I will let you know let you read， watch that optional lecture if you want。

 and then you can guess why we need that。Okay， so if you want to learn more about funing multi trading。

 you can actually watch this lecture。And there are some lectures from the past about fun Mon。

 but we're going to also get back to funary multi to when we talk about GPU hardware。

Because they are using this idea a lot in their architecture。Okay。

 but now our focus is for branch prediction because we want to guess the next address。

So control flow instructions， branches are frequent in some reports like 15 to 25% of all instructions。

And the problem is that next fish address after a control flow instruction is not determined after end cycles in a pipeline processor。

 and that end cycle is actually your branch resolution essentially that you want to you need to spend to understand the result of your branch。

If we are fetching W instructions per cycle in a super scal system。Then actually a branch mispre。

 meaning that you started fetching instruction from the wrong pass can lead to end multiply。

N times W wasted instruction slot。And that's why actually the good accuracy of branch prediction is important。

 I'm going to show you with this beautiful example。😊，Assume that we have 20 pipeline stages。

Whi is not also quite that many stages compared to what we have in today's systems。

 today's system has much more many more stages actually in the pipeline。

And we have a super scalar system which has five， basically five whites essentially。

And another assumption is that one out of five instruction is a branch。

And each five instruction block ends with a branch。

So how long does it take to fetch 500 instructions？Assuming that we have branch prediction。

 which is 100% accurate。This one is easy to calculate and take care。Also。

 I assume that we don't have any data dependence， so everything's ideal here。

So what's our ideal IPC here in our five white superscalealar processor？5， right。

And then we have 500 instruction， meaning that we can finish them in100 cycles。

Meaning that our IPC is5。It is great。嗯。Now assume that so essentially we have no wasted work。

 now assume that our branch prediction accuracy is 99%。Which is still actually very good。So。

 in this case。In one%。So we have 100 branches， right。

 because we said that each five instruction block ends with a branch。

And we have 500 instruction in total， so in total we have 100 branch instructions。

And we are predicting one% of that wrongly， meaning that one branch is to predict is going to cause us to go to the wrong path。

So you need， this is your overhead。We have 20 pipeline stages and there is one instruction in the wrong path。

 so 20 times one， that's your waistted work， essentially 20 cycles。

And you still need to run 100 instructions in the current path。

 assuming that you don't have any control flow and sorry， any data dependence issue。

 so you're going to get to 120 cycles。Which means that you have 20 extra the person extra。

Instruction fetch and your IPC is going to be something around4。

So by reducing the accuracy of branch by only 1%， branch prediction by only 1%。

We're going to see that we are seeing that actually our IPC decreases from five to four。

But the seal is good。The setting is that having 90% accuracy is not good。

Even though the 90% accuracy seems accurate。And we're going to see that how much work we need to do in order to get 90% accurate create branch prediction。

So when you have 90% accurate， then meaning that 10 branches is going to cause you in the wrong pass。

 so you have 20 pipeline stages times 10， which is 200。

And you need to also spend 100 cycles on the correct pass。

 and then you're going to get to 300 cycles。And if you calculate it。

 you're going to see that your IPC is5 over 3， which is 1。6。So your IPC degraded from 5 to 1。6。

But your branch prediction is only degraded by 10%， which does not seem that much。

 but actually is a lot。I don't want to even show the 60 person accuracy。😊。

Your IPC is even less than one。So that's why actually why branch prediction is a really important problem and how much we need to work in it and need to make the accuracy close to 99% actually。

 we cannot probably get to 100%。But we should try to get to 99%， 98%， something around that。

Any question？Is it interesting？Okay。So let's see basically what we're going to build on to make branch prediction。

So here is another example， but I'm going to actually go over it a little bit quickly is a code。

Here you have a branch instruction。If you basically。Just stock。

After this branch until the resolution， you're basically going to have a pipeline like this。

 essentially。So you cannot do anything， and then at some point you can start with this edition。

And then you're going to get to some basically cycles。 But with branch prediction。

 if you predict that correctly， you can actually get to。This timeline。

Which you are saving a lot from2 of cycles to eight cycles， even for such a simple and short code。

But the problem is also the misprediction penalty， sometimes you mispred it。So here， for example。

 you predicted that we need to fetch from the next。Address。

 meaning that you predicted that this branch is not taken。

But it turns out that this is actually taken， so you need to flush what you have in your pipeline。

And then it starts switching from basically。The correct path。

And that's something we always also need to consider that。Basically。

 in order to improve your branch prediction efficiency。

 there are two ways I mean it's not so in order to reduce the control dependence overhead。

 you need to improve your prediction accuracy branch prediction accuracy at the same time you should also try to reduce your missed prediction penalty so there are two angles in that and people should should be careful about considering these two angles actually at the same time。

So let's start with one of the simplest way we always guess next PC is PC plus4。

 so always predict that the next sequential instruction is the next instruction to be executed。

 this can be actually easily implemented in MIPS right。

This is a form of next fetch address prediction。So how can we make this more effective？

There is several ideas。actually what what does it mean to make it more effective。

 basically want to make how we want to make sure that most of the time our next PC is PC plus4。

 meaning that our branch prediction accuracy is better。

Here is very simple branch prediction mechanism that we always guess that next PC is PC+4。😊。

So one idea is that we want to maximize the chances that the next sequential instruction is the next instruction to be executed。

So the software can actually help us doing that that basically the software can lay out or compiler。

 lay out the control flow graph。Such that the likely next instruction is on the nine non taken passover a branch I'm I can show you actually。

Do we have time for that？Yeah， we have is， you have something。Okay， so。I'm going to mute projectors。

And here I need to stop share， right？

![](img/a12acf66b09fffa4c9c52fbc853648b0_13.png)

こ。

![](img/a12acf66b09fffa4c9c52fbc853648b0_15.png)

So assume that a we have some codes and then we get to if。



![](img/a12acf66b09fffa4c9c52fbc853648b0_17.png)

![](img/a12acf66b09fffa4c9c52fbc853648b0_18.png)

X， we want to go to the。Block of instruction A and else， we go to the block of instruction B。

 and then we have block of instruction C， for example。So。

The control of photographgraph can be something like this， I call this。Let's make it also here。

 also D。So you have a block of instruction that you can call it D。And then you have E。

You have a block of a。And then， B。Sorry。And then C and then essentially B。

So once you have a branch here if。Basically， if it's correct， you go here， if it's not。

 you need to go to the。To this。And after finishing this， you need to go back to C。Right。

So here if your branch is taken。The next。Essentially if your control flowgraph is like this。

 you know if basically we have these instructions in the memory。

 so if your branch is taken the next instruction is always actually the sequentially the next one right so if my branch is taken I want to execute this part right and then I'm going to basically execute instruction from here which means PC plus4 works with here。

😊，But assume that compiler realized that with some profiling， for example。

 realize that actually this branch is most of the time not thick。

Meaning that most of the time you're actually taking this pass， you go to the B。

 and then you go to this C。Meaning that you'll get to。

This issue that your PC+ for prediction is not working well。So if that's the case。

 compiler can try to place reorder your control flow graph a bit。Meaning that's put D here。And then。

 go to the。嗯。B。And then， see。And then， we have。A he。And this a can go back basically。

So from this branch， we might need to go。Here， and when we are done with A， we need to go back to C。

Correct。😊，So if this branch is most of the time not taken。

This code is gonna provide better performance， Not this code。

 This control flow graph is gonna provide better performance。

So that's the way that compiler can help you to reorder。

Or basically make your control flow graph nicely based on the probability of your branches if they are taken or not taken。

 such that your PC plus4 prediction works better。Any question？嗯。Good。



![](img/a12acf66b09fffa4c9c52fbc853648b0_20.png)

嗯。Any help？

![](img/a12acf66b09fffa4c9c52fbc853648b0_22.png)

Okay， so yeah， basically a compiler can try to do that and this profile guided code positioning that you can also check this paper from PLDI in 1990。

Hardware can also try to do that， actually people have implemented in for example。

 Intel has a technique trace cache that they try to reorder basically。

 make a trace of instructions that they are likely to be continuous and that can improve your branch prediction performance。

Yeah， cash traces of executed instruction。我。Other ways to improve the performance of PC+ for prediction is。

 for example， get rid of control flow instructions or minimize the occurrence。So how we can do that。

 one way is to get rid of unnecessary control flow instructions。

 we can combine perdicates or using paradicate combining and test only once。

So when you have some instructions like E and elses， you can actually make an instruction that。诶。

Basically， there are a lot of these ifLs and ifLs， you have a lot of these instructions。

So you can try to combine all of these conditions and say that if。

 for example x and y and z and so on so， then I'm going to execute this part of code so you make it more accurate and with that you need to do a lot for that predication you need to basically calculate a lot of deal with a lot of conditions to make sure that you need to run this if or not but the good thing is that you don't have that many of these control flow instruction in your code so you can reduce if else。

AndBy doing such things， for example。And then you basically can also convert control dependence into data dependencies using predicated execution。

That we're gonna also。We may see it actually later。Okay。So with this always a PC plus4， for example。

 we can。Have a good performance， but。When a branch resolve realized that branch target instruction K is fetched。

 all instruction fetch scene they are in the wrong pass so basically instruction I and J。

 they are on the wrong pass， so we need to flush them。

 so there should be a way in the pipeline to flush instructions。

 so we flush them and then we continue from the correct pass。

And that definitely comes at the price of lower performance and lower efficiency。

So let's see very quickly an analysis， even though we have seen a more general analysis also before。

So in correct yes， we have no penaltyty and incorrect guess， we have two bubbles。

 assuming the pipeline that we have shown。And another assumption is that we have no data dependency related resultss。

20% control flow instructions。And 70% of control flow instructions are taken。Meaning that yeah。

 I can show actually here your CPI is going to be one plus。

Your waste network work and your waste network work is essentially。20% times 70%。

 this is going to be 14%， which is 14% of instructions you need to you're causing bubbles and you're causing two bubbles。

And with that， if you categoryka， you're going to get to CPI 1。28。So this 0。14%。

 we can call it as a probability of wrong gas。Because this is the amount 20% is actually the total number of branches and in for 70% we are actually guessing wrongly because our guest is always not taken that we want to go to the next one。

Next sequential address， so this is the probability of wrong guesses and this is the penalty for wrongous。

 which is the miss penalty overhead so it's very important that we try to reduce both in order to have a good performance。

And we have covered actually a lot in our previous lectures。

 how we can reduce the branch a mis predictiondiction penalty and you can check from prior lectures。

对。Okay， but now we want to move to enhance branch prediction。

So the idea of a branch prediction is to predict the next fetch address to be used in the next cycle。

 such that we can have no wasted cycle on correct prediction。

 and that requires three things to be predicted at fetch stage。

Whether the fetch instruction is a branch， so this is the we want to know that if we are our fetch instruction is a branch。

And whether or not basically we want to understand the direction if the branch is going to be taken or not taken。

 this actually more or less the case for conditional branches， because for other branches。

 we know that they're going to be taken， for example。And。Also。

 we need to understand the branch target address if taken， so for conditional branches， if taken。

 we need to get the target address for unconditional branches。

 we know that they're going to be taken， but at least。

 but still we need to find the branch target address。

So the observation is that target address remains the same for a conditional direct branch across dynamic instances。

Which is correct right so when you have a conditional direct branches you can always calculate your target address relatively to your PC right you go you jump for example if you instruction up or few instruction down so you can always calculate your target address and that going to remains the same because。

The PC for that branch is the same and then your relative address coding is also the same in your instruction。

 so your target address is going to be the same。And then we can store the target address from previous instances and access it with a PC。

And we call this branch target buffer， there is a buffer that we add in order to keep the target addresses that we have calculated in the past。

 but we keep them and reuse them in future instances of these branches。So here how we do it。

 so we have a predictor which we're going to also learn a lot how we can design it。

 but there is a predictor for direction whether or not it's taken。And there is also another table。

 which is a branch target buffer。Which kind of a cache of target addresses？

There is a program so based on your program counters。

 you access your BTB and also your direction predictor。If you hit in your BTB。

 meaning that you have already resolved， you had this branch before and you capture the branch target address。

So you get the target address from your BTB。And then if it is taken。

 so basically you need to end taken and this heat。Then you can actually input this selector of this mos and then the maxs is going to be PC。

 one of them is PC+ next instruction or the target address， which if it is taken and heat is correct。

 we need to take the target address。And based on that， you get the next three charges。

You can also make it more sophisticated that we can learn we will learn actually tomorrow that by adding global branch history。

 so another observation is that which direction earlier branches wins so if we include the direction that other branches take in the past to our decisioning using this global branch history that can actually improve a lot of performance and provide much better accuracy for our direction predictor and that makes a lot of difference and we're going to see later actually tomorrow。

So we。We have， as I said， traits to be predicted， whether the fish instruction is a branch。

 the direction of the branch and also branch target others。

So the Tone can be accomplished using a BTB。The first one can be accomplished again using a BTB because once you execute one branch instruction and you add it to your BTB。

 then with that PC you can when you look up your BTB and you find that branch。

 you find that PC in your BTB， you realize that okay。

 this was a branch instruction so this can be easily done。

Or we can also store branch metadata bits in an instruction cache memory that partially decoded instruction so that's also another way of implementation。

You can easily also do it with your BTB。But then the second is， how do we predict the direction。

 There are some compile time。嗯。That we call them static。Always not taken， Always taken。

Backward taken and forward not taken and profile based likely direction。

And there are also some runtime techniques that hardware is trying to do。

 and these runtime techniques are very important and many of today's systems having some sorts of these hardware techniques。

So let's start with some of these aesthetic branch prediction。Always not taken。😊。

It's quite simple to implement no need for BTV， no direction prediction。And we have seen that。

 right we say that like the next is PC+4 for example。But accuracy is actually quite low。

 30 to 40% for conditional branches。And we also discussed that compiler can help you。

 but to make it more effective， but thus compiler can not do magic also for you。

 so in the end the accuracy if you always want to predict not taken is not going to be great。

Always taken again we don't have direction prediction so we know that's our prediction logic is whenever I see a branch I consider that always it's going to be taken so there is no prediction logic。

This provides actually better accuracy。😊，Because statistically。

 people realize that many of our branches are actually taken because we use loops a lot。

 so and we have a lot of these back branches that basically we loop back and we need to basically these branches are taken。

So basically backford branches that loop branches are there are usually taken and backford branch。

 the target of this is lower than the branch PC。And also people try to basically come up with some other type of prediction like back taken whenever I see a branch。

 like the backford branch， I predict it as a taken and whenever I see a forward branch。

 I predict as not taken， so that also provides a little bit better accuracy。

Any question on this a static implementation？Okay。So compiler can also help you to do providing。

 so in your incompr can also you can input some data set to your compiler and then compiler can run your code。

And then based on that data set and profile based can assess and can calculate the accuracy。

 basically the probability of taken or not taken per every branch instances。

So this is good because perb branch prediction is more accurate than schemes in previous slide is accurate if profile is representative。

 of course， the profiler should be representative。But this requires hint bits in the branch instruction format。

 so you need to change ISA and the compiler needs to add some of these hint bits to let me finish this slide and then we done。

the compiler needs to add these hints to the instruction to hint the hardware that is going to be probably taken or not taken。

And the accuracy depends on the dynamic branch behavior like this taken， not taken is going to be。

 for example， 50% accuracy。😊，And this one taken not taken。

 taken not taken this in the end also cannot get better than 50 accuracy， 50% accuracy。

 so in the end on the behavior of dynamic branches， your accuracy is very dependent。

And accuracy depends on representativeness of profile input set。

 so the input set that you provide for your compiler needs to be really representative。

 otherwise you might get by us。In some wrong price。 So when you have this taken， taken， taken taken。

 and in the end， some not taken。If you bias your predictor a lot with the data set that caused this kind of behavior。

 you're going to， for example， predict that branch mostly 90%。

 but maybe in a real scenario when your application is executing。

 there's a different behavior and you might actually get to 10% agree。

So it's important to think about it。Okay， so I think I will stop here and we will catch up tomorrow。

😊，And see you all tomorrow。

![](img/a12acf66b09fffa4c9c52fbc853648b0_24.png)